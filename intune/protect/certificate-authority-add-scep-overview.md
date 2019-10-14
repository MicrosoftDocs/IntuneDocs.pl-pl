---
title: Korzystanie z urzędu certyfikacji innej firmy przy użyciu protokołu SCEP w usłudze Microsoft Intune — Azure | Microsoft Docs
description: W usłudze Microsoft Intune można dodać dostawcę lub urząd certyfikacji innej firmy, aby wystawiać certyfikaty na urządzeniach przenośnych przy użyciu protokołu SCEP. W tym omówieniu aplikacja usługi Azure Active Directory (Azure AD) przyznaje usłudze Microsoft Intune uprawnienia do weryfikowania certyfikatów. Następnie należy użyć identyfikatora aplikacji, klucza uwierzytelniania i identyfikatora dzierżawy aplikacji usługi AAD w konfiguracji serwera protokołu SCEP do wystawiania certyfikatów.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e8df5f46f411a6aee1c3040fa4a1a37fb49d5fb2
ms.sourcegitcommit: fca2670142c083d7562c0a36547a6a451863e315
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/08/2019
ms.locfileid: "72036437"
---
# <a name="add-partner-certification-authority-in-intune-using-scep"></a>Dodawanie urzędu certyfikacji partnera w usłudze Intune przy użyciu protokołu SCEP

W usłudze Intune można korzystać z urzędów certyfikacji innych firm. Urzędy certyfikacji innych firm mogą dostarczać urządzeniom przenośnym nowe lub odnowione certyfikaty przy użyciu prostego protokołu rejestrowania certyfikatów (SCEP) i mogą obsługiwać urządzenia z systemem Windows, iOS, Android oraz macOS.

Proces używania tej funkcji składa się z dwóch części: interfejsu API typu open source i zadań administratora usługi Intune.

**Część 1. Używanie interfejsu API typu open-source**  
Firma Microsoft stworzyła interfejsu API do integracji z usługą Intune. Ten interfejs API umożliwia weryfikowanie certyfikatów, wysyłanie powiadomień o powodzeniu lub niepowodzeniu i używanie protokołu SSL, w szczególności fabryki gniazda protokołu SSL, do komunikowania się z usługą Intune.

Interfejs API jest dostępny do pobrania i używania w rozwiązaniach w [publicznym repozytorium GitHub interfejsów API protokołu SCEP usługi Intune](http://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation). Używaj tego interfejsu API z serwerami SCEP innych firm w celu uruchomienia walidacji niestandardowych wyzwań w usłudze Intune przed dostarczeniem certyfikatu do urządzenia przez protokół SCEP.

[Integracja z rozwiązaniem do zarządzania protokołem SCEP usługi Intune](scep-libraries-apis.md) zawiera więcej szczegółowych informacji na temat używania interfejsu API, jego metod oraz testowania kompilowanego rozwiązania.

**Część 2. Tworzenie aplikacji i profilu**  
Za pomocą aplikacji usługi Azure Active Directory (Azure AD) można delegować prawa do usługi Intune w celu obsługiwania żądań protokołu SCEP pochodzących z urządzeń. Aplikacja usługi Azure AD zawiera wartości identyfikatora aplikacji i klucza uwierzytelniania, które są używane w ramach rozwiązania interfejsu API tworzonego przez dewelopera. Potem administratorzy tworzą i wdrażają profile certyfikatów SCEP przy użyciu usługi Intune i mogą wyświetlać raporty stanu wdrożenia na urządzeniach.

Ten artykuł zawiera omówienie tej funkcji z perspektywy administratora, w tym omówienie procesu tworzenia aplikacji usługi Azure AD.

## <a name="overview"></a>Przegląd

W poniższych krokach przedstawiono omówienie procesu wystawiania protokołu SCEP dla certyfikatów w usłudze Intune:

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

![W jaki sposób protokół SCEP urzędu certyfikacji innej firmy zostaje zintegrowany z usługą Microsoft Intune](./media/certificate-authority-add-scep-overview/scep-certificate-vendor-integration.png)

## <a name="set-up-third-party-ca-integration"></a>Konfigurowanie integracji urzędu certyfikacji innej firmy

### <a name="validate-third-party-certification-authority"></a>Walidowanie urzędu certyfikacji innej firmy

Przed zintegrowaniem urzędów certyfikacji innych firm z usługą Intune upewnij się, że używany urząd certyfikacji obsługuje usługę Intune. Lista znajduje się w sekcji [Partnerzy urzędu certyfikacji innej firmy](#third-party-certification-authority-partners) (w tym artykule). Możesz również sprawdzić wskazówki dotyczące urzędu certyfikacji, aby uzyskać więcej informacji. Urząd certyfikacji może obejmować instrukcje konfiguracji specyficznych dla odpowiedniej implementacji.

### <a name="authorize-communication-between-ca-and-intune"></a>Autoryzowanie komunikacji między urzędem certyfikacji i usługą Intune

Aby umożliwić serwerowi protokołu SCEP innej firmy uruchamianie walidacji wyzwań niestandardowych za pomocą usługi Intune, należy utworzyć aplikację w usłudze Azure AD. Ta aplikacja przyznaje delegowane prawa do usługi Intune w celu walidowania żądań SCEP.

Upewnij się, że masz wymagane uprawnienia do zarejestrowania aplikacji usługi Azure AD. Zobacz temat [Wymagane uprawnienia](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal#required-permissions) w dokumentacji usługi Azure AD.

#### <a name="create-an-application-in-azure-active-directory"></a>Utworzenie aplikacji w usłudze Azure Active Directory  

1. W witrynie [Azure Portal](https://portal.azure.com) przejdź kolejno do pozycji **Azure Active Directory** > **Rejestracje aplikacji**, a następnie wybierz pozycję **Nowa rejestracja**.  

2. Na stronie **Zarejestruj aplikację** określ następujące informacje:  
   - W sekcji **Nazwa** wprowadź opisową nazwę aplikacji.  
   - W sekcji **Obsługiwane typy kont** wybierz pozycję **Konta w dowolnym katalogu organizacyjnym**.  
   - W polu **Identyfikator URI przekierowania** pozostaw wartość domyślną sieci Web, a następnie określ adres URL logowania do serwera SCEP innej firmy.  

3. Wybierz opcję **Zarejestruj**, aby utworzyć aplikację i otworzyć stronę przeglądu dotyczącą nowej aplikacji.  

4. Na stronie **Przegląd** aplikacji skopiuj wartość **Identyfikator klienta aplikacji** i zapisz ją w celu późniejszego użycia. Ta wartość będzie potrzebna później.  

5. W okienku nawigacji w aplikacji przejdź do pozycji **Certyfikaty i klucze tajne** w obszarze **Zarządzaj**. Wybierz przycisk **Nowy klucz tajny klienta**. Wprowadź opis, wybierz dowolną opcję w polu **Wygasa**, a następnie wybierz opcję **Dodaj**, aby wygenerować *wartość* klucza tajnego klienta. 
   > [!IMPORTANT]  
   > Zanim opuścisz tę stronę, skopiuj wartość klucza tajnego klienta i zapisz ją do późniejszego użycia z implementacją urzędu certyfikacji innej firmy. Ta wartość nie zostanie wyświetlona ponownie. Pamiętaj, aby zapoznać się ze wskazówkami urzędu certyfikacji innej firmy dotyczącymi wymaganej konfiguracji identyfikatora aplikacji, klucza uwierzytelniania i identyfikatora dzierżawy.  

6. Zapisz swój **identyfikator dzierżawy**. Identyfikator dzierżawy to tekst domeny po znaku @ w nazwie konta. Jeśli na przykład Twoje konto to *admin@name.onmicrosoft.com* , identyfikatorem dzierżawy będzie **name.onmicrosoft.com**.  

7. W okienku nawigacji w aplikacji przejdź do pozycji **Uprawnienia interfejsu API** w obszarze **Zarządzaj**, a następnie wybierz pozycję **Dodaj uprawnienie**.  

8. Na stronie **Żądanie uprawnień interfejsu API** wybierz opcję **Intune**, a następnie wybierz pozycję **Uprawnienia aplikacji**. Zaznacz pole wyboru **scep_challenge_provider** (walidacja wyzwania protokołu SCEP).  

   Wybierz opcję **Dodaj uprawnienia**, aby zapisać tę konfigurację.  

9. Pozostań na stronie **Uprawnienia interfejsu API** i wybierz kolejno opcje **Wyraź zgodę administratora dla Microsoft** oraz **Tak**.  
   
   Proces rejestracji aplikacji w usłudze Azure AD został ukończony.





### <a name="configure-and-deploy-a-scep-certificate-profile"></a>Konfigurowanie i wdrażanie profilu certyfikatu protokołu SCEP
Jako administrator utwórz profil certyfikatu protokołu SCEP do skierowania do użytkowników lub urządzeń. Następnie przypisz profil.

- [Tworzenie profilu certyfikatu protokołu SCEP](certificates-profile-scep.md#create-a-scep-certificate-profile)

- [Przypisywanie profilu certyfikatu](certificates-profile-scep.md#assign-the-certificate-profile)

## <a name="removing-certificates"></a>Usuwanie certyfikatów

Po wyrejestrowaniu lub wyczyszczeniu urządzenia certyfikaty zostaną usunięte. Certyfikaty nie są odwoływane.

## <a name="third-party-certification-authority-partners"></a>Partnerzy urzędu certyfikacji innej firmy
Następujące urzędy certyfikacji innych firm obsługują usługę Intune:

- [Entrust Datacard](https://info.entrustdatacard.com/pki-eval-tool)
- [Wersja repozytorium GitHub EJBCA typu open-source](https://github.com/agerbergt/intune-ejbca-connector)
- [EverTrust](https://evertrust.fr/en/products/)
- [GlobalSign](https://downloads.globalsign.com/acton/attachment/2674/f-6903f60b-9111-432d-b283-77823cc65500/1/-/-/-/-/globalsign-aeg-microsoft-intune-integration-guide.pdf)
- [IDnomic](https://www.idnomic.com/)
- [Sectigo](https://sectigo.com/products)
- [DigiCert](https://knowledge.digicert.com/tutorials/microsoft-intune.html)
- [Venafi](https://www.venafi.com/platform/enterprise-mobility)
- [SCEPman](https://azuremarketplace.microsoft.com/marketplace/apps/gluckkanja.scepman)

Jeśli interesuje Cię zintegrowanie urzędu certyfikacji innej firmy z usługą Intune, zapoznaj się ze wskazówkami dotyczącymi interfejsu API:

- [Intune SCEP API GitHub repository (Repozytorium GitHub interfejsu API protokołu SCEP w usłudze Intune)](http://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation)
- [Intune SCEP API guidance for third party CAs (Wskazówki dotyczące interfejsu API protokołu SCEP w usłudze Intune dla urzędów certyfikacji innych firm)](scep-libraries-apis.md)

## <a name="see-also"></a>Zobacz także

- [Konfigurowanie profilów certyfikatów](certificates-scep-configure.md)
- [Intune SCEP API GitHub repository (Repozytorium GitHub interfejsu API protokołu SCEP w usłudze Intune)](http://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation)
- [Intune SCEP API guidance for third party CAs (Wskazówki dotyczące interfejsu API protokołu SCEP w usłudze Intune dla urzędów certyfikacji innych firm)](scep-libraries-apis.md)
