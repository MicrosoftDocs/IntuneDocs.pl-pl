---
title: Korzystanie z urzędu certyfikacji innej firmy przy użyciu protokołu SCEP w usłudze Microsoft Intune — Azure | Microsoft Docs
description: W usłudze Microsoft Intune można dodać dostawcę lub urząd certyfikacji innej firmy, aby wystawiać certyfikaty na urządzeniach przenośnych przy użyciu protokołu SCEP. W tym omówieniu aplikacja usługi Azure Active Directory (Azure AD) przyznaje usłudze Microsoft Intune uprawnienia do weryfikowania certyfikatów. Następnie należy użyć identyfikatora aplikacji, klucza uwierzytelniania i identyfikatora dzierżawy aplikacji usługi AAD w konfiguracji serwera protokołu SCEP do wystawiania certyfikatów.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 07/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ee5a39ee8a146fbc6a85a9f4438b8e14a408a735
ms.sourcegitcommit: e8e8164586508f94704a09c2e27950fe6ff184c3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2018
ms.locfileid: "39321730"
---
# <a name="add-partner-certification-authority-in-intune-using-scep"></a>Dodawanie urzędu certyfikacji partnera w usłudze Intune przy użyciu protokołu SCEP

W usłudze Microsoft Intune można dodawać urzędy certyfikacji innych firm. Te urzędy certyfikacji mogą dostarczać certyfikaty na urządzenia przenośne przy użyciu prostego protokołu rejestrowania certyfikatów (SCEP, Simple Certificate Enrollment Protocol). Ta funkcja może wystawiać nowe certyfikaty i odnawiać certyfikaty na urządzeniach z systemem Windows, iOS, Android i macOS.

Proces używania tej funkcji składa się z dwóch części: interfejsu API typu open source i zadań administratora usługi Intune.

**Część 1. Używanie interfejsu API typu open-source**  
Firma Microsoft stworzyła interfejs API, który integruje się z usługą Intune w celu weryfikowania certyfikatów, wysyłania powiadomień o powodzeniu lub niepowodzeniu i używania protokołu SSL, w szczególności fabryki gniazda protokołu SSL, do komunikowania się z usługą Intune.

Interfejs API jest dostępny do pobrania i używania w rozwiązaniach w [publicznym repozytorium GitHub interfejsów API protokołu SCEP usługi Intune](http://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation). Używaj tego interfejsu API z serwerami SCEP innych firm w celu uruchomienia weryfikacji niestandardowych wyzwań w usłudze Intune przed dostarczeniem certyfikatu do urządzenia.

[Integracja z rozwiązaniem do zarządzania protokołem SCEP usługi Intune](scep-libraries-apis.md) zawiera więcej szczegółowych informacji na temat używania interfejsu API, jego metod oraz testowania kompilowanego rozwiązania.

**Część 2. Tworzenie aplikacji i profilu**  
Za pomocą aplikacji usługi Azure Active Directory (Azure AD) można delegować prawa do usługi Intune w celu obsługiwania żądań protokołu SCEP pochodzących z urządzeń. Aplikacja usługi Azure AD zawiera wartości identyfikatora aplikacji i klucza uwierzytelniania, które są używane w ramach rozwiązania interfejsu API tworzonego przez dewelopera. Administratorzy mogą następnie tworzyć i wdrażać profile certyfikatów protokołu SCEP przy użyciu usługi Intune. Można również wyświetlać raporty o stanie wdrożenia na urządzeniach.

Ten artykuł zawiera omówienie tej funkcji z perspektywy administratora, w tym omówienie procesu tworzenia aplikacji usługi Azure AD.

## <a name="overview"></a>Przegląd

W poniższych krokach przedstawiono omówienie procesu wystawiania certyfikatów protokołu SCEP w usłudze Intune:

1. W usłudze Intune administrator tworzy profil certyfikatu protokołu SCEP, a następnie kieruje profil do użytkowników lub urządzeń.
2. Urządzenie zostaje zaewidencjonowane w usłudze Intune.
3. Usługa Intune tworzy unikatowe wyzwanie protokołu SCEP. Dodaje ona dodatkowe informacje dotyczące sprawdzania integralności, takie jak informacje na temat oczekiwanego tematu i sieci SAN.
4. Usługa Intune szyfruje i podpisuje wyzwanie oraz informacje dotyczące sprawdzania integralności, a następnie wysyła te informacje do urządzenia przy użyciu żądania protokołu SCEP.
5. Urządzenie generuje żądanie podpisania certyfikatu (CSR) oraz parę pary kluczy typu publiczny/prywatny na urządzeniu w oparciu o profil certyfikatu protokołu SCEP wypychany z usługi Intune.
6. Żądanie CSR i zaszyfrowane/podpisane wyzwania są wysyłane do punktu końcowego serwera SCEP innej firmy.
7. Serwer protokołu SCEP wysyła żądanie CSR i wyzwanie do usługi Intune. Następnie usługa Intune weryfikuje podpis, odszyfrowuje ładunek i porównuje żądanie CSR z informacjami na temat sprawdzania integralności.
8. Usługa Intune odsyła odpowiedź z powrotem do serwera protokołu SCEP i wskazuje, czy weryfikacja żądania zakończyła się pomyślnie.  
9. Jeśli wyzwanie zostanie pomyślnie zweryfikowane, serwer SCEP wystawi certyfikat na urządzeniu.

Na poniższym diagramie przedstawiono szczegółowy przepływ integracji protokołu SCEP innej firmy z usługą Intune:

![W jaki sposób protokół SCEP urzędu certyfikacji innej firmy zostaje zintegrowany z usługą Microsoft Intune](./media/scep-certificate-vendor-integration.png)

## <a name="set-up-third-party-ca-integration"></a>Konfigurowanie integracji urzędu certyfikacji innej firmy

### <a name="validate-third-party-certification-authority"></a>Walidowanie urzędu certyfikacji innej firmy

Przed zintegrowaniem urzędów certyfikacji innych firm z usługą Intune upewnij się, że używany urząd certyfikacji obsługuje usługę Intune. Lista znajduje się w sekcji [Partnerzy urzędu certyfikacji innej firmy](#third-party-certification-authority-partners) (w tym artykule). Możesz również sprawdzić wskazówki dotyczące urzędu certyfikacji, aby uzyskać więcej informacji. Urząd certyfikacji może obejmować instrukcje konfiguracji specyficznych dla odpowiedniej implementacji.

### <a name="authorize-communication-between-ca-and-intune"></a>Autoryzowanie komunikacji między urzędem certyfikacji i usługą Intune

Aby umożliwić serwerowi protokołu SCEP innej firmy uruchamianie walidacji wyzwań niestandardowych za pomocą usługi Intune, należy utworzyć aplikację w usłudze Azure AD. Ta aplikacja przyznaje delegowane prawa do usługi Intune w celu walidowania żądań SCEP.

Upewnij się, że masz wymagane uprawnienia do zarejestrowania aplikacji usługi Azure AD. Lista kroków znajduje się w sekcji [Required permissions (Wymagane uprawnienia)](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal#required-permissions).

**Krok 1. Tworzenie aplikacji usługi Azure AD**

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz kolejno pozycje **Azure Active Directory** > **Rejestracje aplikacji** > **Rejestrowanie nowej aplikacji**.
3. Wprowadź nazwę i adres URL logowania. Wybierz pozycję **Aplikacja internetowa/interfejs API** jako typ aplikacji.
4. Wybierz przycisk **Utwórz**.

Temat [Integrowanie aplikacji z usługą Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications) zawiera wskazówki dotyczące tworzenia aplikacji, w tym porady związane z nazwą i adresem URL.

**Krok 2. Udzielanie uprawnień**

Po utworzeniu aplikacji nadaj interfejsowi API usługi Microsoft Intune wymagane uprawnienia:

1. W aplikacji usługi Azure AD otwórz obszar **Ustawienia** > **Wymagane uprawnienia**.  
2. Wybierz kolejno pozycje **Dodaj** > **Wybierz interfejs API** > wybierz **interfejs API usługi Microsoft Intune** > **Wybierz**.
3. W obszarze **Wybieranie uprawnień** wybierz kolejno pozycje **Walidacja wyzwania protokołu SCEP** > **Wybierz**.
4. Wybierz przycisk **Gotowe**, aby zapisać zmiany.

**Krok 3. Pobieranie identyfikatora aplikacji i klucza uwierzytelniania**

Następnie pobierz wartości identyfikatora i klucza dla aplikacji usługi Azure AD. Potrzebne są następujące wartości:

- Identyfikator aplikacji
- Klucz uwierzytelniania
- Identyfikator dzierżawy

**Aby pobrać identyfikator aplikacji i klucz uwierzytelniania**:

1. W usłudze Azure AD wybierz swoją nową aplikację (**Rejestracje aplikacji**).
2. Skopiuj **identyfikator aplikacji** i zapisz go w kodzie aplikacji.
3. Następnie wygeneruj klucz uwierzytelniania. W aplikacji usługi Azure AD otwórz obszar **Ustawienia** > **Klucze**.
4. W obszarze **Hasła** wprowadź opis i wybierz czas trwania klucza. **Zapisz** zmiany. Skopiuj i zapisz wyświetloną wartość.

    > [!IMPORTANT]
    > Od razu skopiuj i zapisz ten klucz, ponieważ nie będzie ponownie wyświetlany. Ta wartość klucza jest potrzebna podczas implementacji urzędu certyfikacji innej firmy. Pamiętaj, aby zapoznać się ze wskazówkami dotyczącymi wymaganej konfiguracji identyfikatora aplikacji, klucza uwierzytelniania i identyfikatora dzierżawy.

**Identyfikator dzierżawy** to tekst domeny po zalogowaniu @ na koncie. Jeśli na przykład Twoje konto to `admin@name.onmicrosoft.com`, identyfikatorem dzierżawy będzie **name.onmicrosoft.com**.

Sekcja [Get application ID and authentication key (Pobieranie identyfikatora aplikację i klucza uwierzytelniania)](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal#get-application-id-and-authentication-key) zawiera listę czynności wymaganych do uzyskania tych wartości oraz więcej szczegółów na temat aplikacji usługi Azure AD.

### <a name="configure-and-deploy-a-scep-certificate-profile"></a>Konfigurowanie i wdrażanie profilu certyfikatu protokołu SCEP
Jako administrator utwórz profil certyfikatu protokołu SCEP do skierowania do użytkowników lub urządzeń. Następnie przypisz profil.

- [Tworzenie profilu certyfikatu protokołu SCEP](certificates-scep-configure.md#create-a-scep-certificate-profile)

- [Przypisywanie profilu certyfikatu](certificates-scep-configure.md#assign-the-certificate-profile)

## <a name="removing-certificates"></a>Usuwanie certyfikatów

Po wyrejestrowaniu lub wyczyszczeniu urządzenia certyfikaty zostaną usunięte. Certyfikaty nie są odwoływane.

## <a name="third-party-certification-authority-partners"></a>Partnerzy urzędu certyfikacji innej firmy
Następujące urzędy certyfikacji innych firm obsługują usługę Intune:

- [Entrust Datacard](http://www.entrustdatacard.com/resource-center/documents/documentation)

Jeśli interesuje Cię zintegrowanie urzędu certyfikacji innej firmy z usługą Intune, zapoznaj się ze wskazówkami dotyczącymi interfejsu API:

- [Intune SCEP API GitHub repository (Repozytorium GitHub interfejsu API protokołu SCEP w usłudze Intune)](http://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation)
- [Intune SCEP API guidance for third party CAs (Wskazówki dotyczące interfejsu API protokołu SCEP w usłudze Intune dla urzędów certyfikacji innych firm)](scep-libraries-apis.md)

## <a name="see-also"></a>Zobacz też

- [Konfigurowanie profilów certyfikatów](certificates-scep-configure.md)
- [Intune SCEP API GitHub repository (Repozytorium GitHub interfejsu API protokołu SCEP w usłudze Intune)](http://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation)
- [Intune SCEP API guidance for third party CAs (Wskazówki dotyczące interfejsu API protokołu SCEP w usłudze Intune dla urzędów certyfikacji innych firm)](scep-libraries-apis.md)
