---
title: Korzystanie z pochodnych poświadczeń dla urządzeń przenośnych w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Pochodne poświadczenia mogą służyć na urządzeniach przenośnych jako metoda uwierzytelniania dla sieci VPN usługi Intune, poczty e-mail, profilów Wi-Fi, aplikacji oraz protokołu S/MIME i szyfrowania. Pochodne poświadczenia są implementacją wytycznych NIST dla publikacji specjalnej 800-157.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/31/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c4d0772f9a0afce0607d0193bfb82ea6bd22709d
ms.sourcegitcommit: d2d18eef64bcf16eec1a48fcb67f1362537c0245
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/02/2019
ms.locfileid: "73445324"
---
# <a name="use-derived-credentials-in-microsoft-intune"></a>Korzystanie z pochodnych poświadczeń w usłudze Microsoft Intune

*Ten artykuł dotyczy urządzeń z systemem iOS*

W środowiskach, w których do uwierzytelniania lub szyfrowania i podpisywania są wymagane karty inteligentne, można teraz używać usługi Intune do aprowizowania urządzeń przenośnych w certyfikat pochodzący z karty inteligentnej użytkownika. Ten certyfikat nosi nazwę *pochodnego poświadczenia*. Usługa Intune [obsługuje kilku wystawców pochodnych poświadczeń](#supported-issuers), chociaż jednocześnie można używać tylko jednego wystawcy na dzierżawę.

Pochodne poświadczenia są implementacją wytycznych National Institute of Standards and Technology (NIST) dla pochodnych poświadczeń weryfikacji tożsamości osobistej (PIV) w ramach publikacji specjalnej (SP) 800-157.

**Implementacja w usłudze Intune zapewnia następujące korzyści**:

- Administrator usługi Intune konfiguruje dzierżawę do pracy z obsługiwanym wystawcą pochodnych poświadczeń. W systemie wystawcy pochodnego poświadczenia nie trzeba konfigurować żadnych ustawień specyficznych dla usługi Intune.

- Administrator usługi Intune określa **Pochodne poświadczenie** jako *metodę uwierzytelniania* dla następujących obiektów:

  - Typowe typy profilów, takie jak Wi-Fi, VPN i poczta E-mail, w tym aplikacja natywna poczty systemu iOS

  - Uwierzytelnianie aplikacji

  - Podpisywanie i szyfrowanie S/MIME

- Użytkownicy uzyskują pochodne poświadczenie, używając swojej karty inteligentnej na komputerze w celu uwierzytelnienia u wystawcy pochodnego poświadczenia. Wystawca wysyła następnie do urządzenia przenośnego certyfikat pochodzący z karty inteligentnej.

- Kiedy urządzenie otrzyma pochodne poświadczenie, jest ono używane do uwierzytelniania oraz do podpisywania i szyfrowania S/MIME, gdy aplikacje lub profile dostępu do zasobów wymagają podania pochodnego poświadczenia. 

## <a name="prerequisites"></a>Wymagania wstępne

Przed skonfigurowaniem dzierżawy na potrzeby korzystania z pochodnych poświadczeń należy się zapoznać z poniższymi informacjami.

### <a name="supported-platforms"></a>Obsługiwane platformy

Usługa Intune obsługuje pochodne poświadczenia w następujących systemach operacyjnych:

- iOS/iPadOS

### <a name="supported-issuers"></a>Obsługiwani wystawcy

Usługa Intune obsługuje jednego wystawcę pochodnych poświadczeń na dzierżawę. Usługę Intune można skonfigurować do pracy z następującymi wystawcami:

- **DISA Purebred**: https://cyber.mil/pki-pke/purebred/
- **Entrust Datacard**: https://www.entrustdatacard.com/
- **Intercede**: https://www.intercede.com/

Aby uzyskać ważne informacje dotyczące korzystania z różnych wystawców, zapoznaj się ze wskazówkami dotyczącymi konkretnego wystawcy<!-- , including the issuers end-user workflow-->. Aby uzyskać więcej informacji, zobacz [Planowanie na potrzeby pochodnych poświadczeń](#plan-for-derived-credentials) w tym artykule.

> [!IMPORTANT]  
> Jeśli usuniesz wystawcę pochodnego poświadczenia ze swojej dzierżawy, pochodne poświadczenia skonfigurowane przy użyciu tego wystawcy nie będą działać.
>
> Zobacz [Zmiana wystawcy pochodnego poświadczenia](#change-the-derived-credential-issuer) w dalszej części tego artykułu.

### <a name="company-portal-app"></a>Aplikacji Portal firmy

Zaplanuj wdrożenie aplikacji Intune — Portal firmy na urządzeniach, które będą rejestrowane na potrzeby pochodnego poświadczenia. Użytkownicy urządzeń używają aplikacji Portal firmy do uruchamiania procesu rejestracji poświadczeń.

Jeśli masz urządzenie z systemem iOS, zobacz [Dodawanie aplikacji ze sklepu z aplikacjami dla systemu iOS do usługi Microsoft Intune](../apps/store-apps-ios.md).

## <a name="plan-for-derived-credentials"></a>Planowanie na potrzeby pochodnych poświadczeń

Przed skonfigurowaniem wystawcy pochodnych poświadczeń należy poznać poniższe zagadnienia.

### <a name="1-review-the-documentation-for-your-chosen-derived-credential-issuer"></a>1) Przejrzyj dokumentację wybranego wystawcy pochodnych poświadczeń  

Przed skonfigurowaniem wystawcy zapoznaj się z jego dokumentacją, aby zrozumieć, jak jego system dostarcza pochodnych poświadczeń do urządzeń.

W zależności od wybranego wystawcy może być konieczna obecność personelu w czasie rejestracji, aby pomóc użytkownikom ukończyć ten proces. Należy również przejrzeć bieżące konfiguracje usługi Intune, aby się upewnić, że nie zablokują one dostępu niezbędnego do ukończenia żądania poświadczeń przez urządzenia lub użytkowników.

Może być na przykład włączony dostęp warunkowy blokujący dostęp do poczty e-mail z niezgodnych urządzeń. Jeśli użytkownicy są informowani o rozpoczęciu procesu rejestracji pochodnego poświadczenia za pomocą powiadomień e-mail, mogą oni nie otrzymać tych instrukcji, dopóki nie zostaną spełnione wymogi zgodności z zasadami.

Podobnie niektóre przepływy pracy żądania pochodnych poświadczeń wymagają użycia aparatu urządzenia do zeskanowania kodu QR na ekranie. Ten kod łączy urządzenie z żądaniem uwierzytelnienia skierowanym do wystawcy pochodnego poświadczenia dysponującego poświadczeniami karty inteligentnej użytkownika. Jeśli zasady konfiguracji urządzeń blokują użycie aparatu, użytkownik nie może ukończyć żądania rejestracji pochodnego poświadczenia.

Informacje ogólne:

- Jednocześnie może być skonfigurowany tylko jeden wystawca dla każdej dzierżawy. Ten wystawca jest dostępny dla wszystkich użytkowników i obsługiwanych urządzeń w dzierżawie.

- Użytkownicy nie zostaną powiadomieni o konieczności rejestracji pochodnych poświadczeń, dopóki nie zostaną względem nich zastosowane zasady wymagające pochodnych poświadczeń.

- Powiadomienie może nastąpić za pośrednictwem powiadomienia aplikacji Portal firmy, za pośrednictwem wiadomości e-mail lub obu tych metod. Jeśli zdecydujesz się na korzystanie z powiadomień e-mail i korzystasz z dostępu warunkowego, użytkownicy mogą nie otrzymać powiadomienia e-mail, jeśli ich urządzenie nie jest zgodne.

### <a name="2-review-the-end-user-workflow-for-your-chosen-issuer"></a>2) Przejrzyj przepływ pracy użytkownika końcowego dla wybranego wystawcy

Poniżej przedstawiono kluczowe zagadnienia dotyczące poszczególnych obsługiwanych partnerów.  Zapoznaj się z tymi informacjami, aby się upewnić, że zasady i konfiguracje usługi Intune nie blokują użytkownikom i urządzeniom pomyślnego ukończenia rejestracji pochodnych poświadczeń od konkretnego wystawcy.

#### <a name="disa-purebred"></a>DISA Purebred

Zapoznaj się z [przepływem pracy użytkownika wystawcy DISA Purebred](https://docs.microsoft.com/intune-user-help/enroll-ios-device-disa-purebred). Poniżej przedstawiono najważniejsze wymagania dotyczące tego przepływu:

- Użytkownicy muszą mieć dostęp do komputera lub kiosku, gdzie mogą użyć swojej karty inteligentnej w celu uwierzytelniania się u wystawcy.

- Na urządzeniach, które będą rejestrowane na potrzeby pochodnego poświadczenia, musi być zainstalowana aplikacja Intune — Portal firmy.

- W celu [wdrożenia aplikacji DISA Purebred](#deploy-the-disa-purebred-app) na urządzeniach, które będą rejestrowane na potrzeby pochodnego poświadczenia, należy użyć usługi Intune. Ta aplikacja musi zostać wdrożona za pomocą usługi Intune, aby była zarządzana i mogła działać z aplikacją Intune — Portal firmy. Ta aplikacja jest używana przez użytkowników urządzenia do ukończenia żądania pochodnego poświadczenia.

- Aplikacja DISA Purebred wymaga [sieci VPN dla aplikacji](../configuration/vpn-settings-configure.md), aby mieć pewność, że aplikacja będzie mogła uzyskać dostęp do aplikacji DISA Purebred podczas rejestracji na potrzeby pochodnego poświadczenia.

- Podczas rejestracji użytkownicy urządzeń muszą współpracować z aktywnym agentem. W miarę postępu procesu rejestracji użytkownik otrzymuje tymczasowe jednorazowe kody dostępu.

Aby uzyskać informacje na temat pobierania i konfigurowania aplikacji DISA Purebred, zobacz sekcję [Wdrażanie aplikacji DISA Purebred](#deploy-the-disa-purebred-app) w dalszej części tego artykułu.

#### <a name="entrust-datacard"></a>Entrust Datacard

Zapoznaj się z [przepływem pracy użytkownika wystawcy Entrust Datacard](https://docs.microsoft.com/intune-user-help/enroll-ios-device-entrust-datacard). Poniżej przedstawiono najważniejsze wymagania dotyczące tego przepływu:

- Użytkownicy muszą mieć dostęp do komputera lub kiosku, gdzie mogą użyć swojej karty inteligentnej w celu uwierzytelniania się u wystawcy.

- Na urządzeniach, które będą rejestrowane na potrzeby pochodnego poświadczenia, musi być zainstalowana aplikacja Intune — Portal firmy.

- Konieczne jest użycie aparatu urządzenia w celu zeskanowania kodu QR, który łączy żądanie uwierzytelnienia z żądaniem pochodnego poświadczenia z urządzenia przenośnego.

#### <a name="intercede"></a>Intercede

Zapoznaj się z [przepływem pracy użytkownika wystawcy Intercede](https://docs.microsoft.com/intune-user-help/enroll-ios-device-intercede). Poniżej przedstawiono najważniejsze wymagania dotyczące tego przepływu:

- Użytkownicy muszą mieć dostęp do komputera lub kiosku, gdzie mogą użyć swojej karty inteligentnej w celu uwierzytelniania się u wystawcy.

- Na urządzeniach, które będą rejestrowane na potrzeby pochodnego poświadczenia, musi być zainstalowana aplikacja Intune — Portal firmy.

- Konieczne jest użycie aparatu urządzenia w celu zeskanowania kodu QR, który łączy żądanie uwierzytelnienia z żądaniem pochodnego poświadczenia z urządzenia przenośnego.

### <a name="3-deploy-a-trusted-root-certificate-to-devices"></a>3) Wdróż na urządzeniach zaufany certyfikat główny

Zaufany certyfikat główny jest używany z pochodnymi poświadczeniami w celu sprawdzenia, czy łańcuch certyfikatów pochodnego poświadczenia jest prawidłowy i zaufany. Zaufany certyfikat główny jest wymagany, nawet jeśli nie jest bezpośrednio przywoływany przez zasady. Zobacz [Konfigurowanie profilu certyfikatu dla urządzeń w usłudze Microsoft Intune](certificates-configure.md).

### <a name="4-provide-end-user-instructions-for-how-to-get-the-derived-credential"></a>4) Przekaż użytkownikom końcowym instrukcje uzyskania pochodnego poświadczenia

Utwórz i przekaż użytkownikom wskazówki, jak rozpocząć proces rejestrowania na potrzeby pochodnego poświadczenia, oraz poinstruuj ich, jak nawigować w ramach przepływu pracy rejestracji pochodnego poświadczenia u wybranego wystawcy.

Zalecamy przekazanie adresu URL zawierającego Twoje wskazówki. Ten adres URL należy określić podczas konfigurowania wystawcy pochodnego poświadczenia. Będzie on dostępny z poziomu aplikacji Portal firmy. Jeśli nie określisz własnego adresu URL, usługa Intune udostępni link do ogólnych informacji. Te informacje nie będą obejmowały wszystkich możliwych scenariuszy i mogą nie być odpowiednie dla Twojego środowiska.

### <a name="5-deploy-intune-policies-that-require-derived-credentials"></a>5) Wdróż zasady usługi Intune, które wymagają pochodnych poświadczeń

Utwórz nowe zasady lub zmodyfikuj istniejące, aby używać pochodnych poświadczeń. Pochodne poświadczenia zastępują inne metody uwierzytelniania używane w aplikacjach, sieci Wi-Fi, sieci VPN, poczcie e-mail oraz podpisywaniu i szyfrowaniu za pośrednictwem protokołu S/MIME.

Unikaj wymagania użycia pochodnego poświadczenia w celu uzyskania dostępu do procesu będącego częścią procesu uzyskiwania pochodnego poświadczenia, ponieważ może to uniemożliwić użytkownikom ukończenie żądania.

## <a name="set-up-a-derived-credential-issuer"></a>Konfigurowanie wystawcy pochodnego poświadczenia

Przed utworzeniem zasad, które wymagają użycia pochodnego poświadczenia, należy skonfigurować wystawcę poświadczeń w konsoli usługi Intune. Ustawienie wystawcy pochodnego poświadczenia obowiązuje w całej dzierżawie. Dzierżawy obsługują jednocześnie tylko jednego wystawcę.

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) i przejdź do pozycji **Konfiguracja urządzenia** > **Pochodne poświadczenia**.

   ![Konfigurowanie pochodnych poświadczeń w konsoli](./media/derived-credentials/configure-provider.png)

2. W polu **Nazwa wyświetlana** podaj przyjazną nazwę dla zasad wystawcy pochodnych poświadczeń.  Ta nazwa nie jest widoczna dla użytkowników urządzenia.

3. W polu **Wystawca pochodnych poświadczeń** wybierz wystawcę pochodnych poświadczeń wybranego dla dzierżawy:
   - DISA Purebred
   - Entrust Datacard
   - Intercede  

4. Podaj **Adres URL pomocy dotyczącej pochodnych poświadczeń**, aby udostępnić link do lokalizacji zawierającej niestandardowe instrukcje ułatwiające użytkownikom uzyskanie pochodnych poświadczeń dla organizacji. Instrukcje powinny być specyficzne dla organizacji i przepływu pracy, który jest niezbędny do uzyskania poświadczenia od wybranego wystawcy. Ten link będzie widoczny w aplikacji Portal firmy i powinien być dostępny z urządzenia.

   Jeśli nie określisz własnego adresu URL, usługa Intune udostępni link do ogólnych informacji, które nie będą obejmowały wszystkich scenariuszy. Te ogólne wskazówki mogą nie być odpowiednie dla Twojego środowiska.

5. W polu **Typ powiadomienia** wybierz co najmniej jedną opcję. Typy powiadomień to metody informowania użytkowników o następujących scenariuszach:

   - Zarejestrowanie urządzenia u wystawcy w celu uzyskania nowego pochodnego poświadczenia.
   - Pobranie nowego pochodnego poświadczenia, gdy bieżące poświadczenie jest bliskie wygaśnięcia.
   - Skorzystanie z pochodnego poświadczenia na potrzeby zasad uwierzytelniania sieci Wi-Fi, VPN, poczty e-mail lub aplikacji oraz na potrzeby podpisywania i szyfrowania przy użyciu protokołu S/MIME.

6. Gdy wszystko będzie gotowe, wybierz przycisk **Zapisz**, aby ukończyć konfigurację wystawcy pochodnego poświadczenia.

Po zapisaniu konfiguracji można wprowadzać zmiany we wszystkich polach z wyjątkiem pola *Wystawca pochodnych poświadczeń*.  Jeśli chcesz zmienić wystawcę, zobacz [Zmiana wystawcy pochodnego poświadczenia](#change-the-derived-credential-issuer).

## <a name="deploy-the-disa-purebred-app"></a>Wdrażanie aplikacji DISA Purebred

*Ta sekcja ma zastosowanie tylko w przypadku korzystania z wystawcy DISA Purebred*.

Aby móc korzystać z wystawcy **DISA Purebred** jako wystawcy pochodnych poświadczeń dla usługi Intune, konieczne jest pobranie aplikacji DISA Purebred, a następnie wdrożenie jej na urządzeniach za pomocą usługi Intune. Użytkownicy korzystają z tej aplikacji na swoich urządzeniach w celu uzyskania pochodnego poświadczenia od wystawcy DISA Purebred.

Oprócz wdrożenia aplikacji za pomocą usługi Intune należy skonfigurować w usłudze Intune sieć VPN dla aplikacji DISA Purebred.

**Wykonaj następujące zadania**:
  
1. Pobierz [aplikację DISA Purebred](https://cyber.mil/pki-pke/purebred/).
2. Wdróż aplikację DISA Purebred w usłudze Intune.  Zobacz [Dodawanie do usługi Microsoft Intune aplikacji biznesowych dla systemu iOS](../apps/lob-apps-ios.md).
3. [Utwórz sieć VPN dla aplikacji](../configuration/vpn-settings-configure.md) DISA Purebred.

## <a name="use-derived-credentials-for-authentication-and-smime-signing-and-encryption"></a>Korzystanie z pochodnych poświadczeń na potrzeby uwierzytelniania i podpisywania oraz szyfrowania za pomocą protokołu S/MIME

**Pochodne poświadczenia** są obsługiwane przez następujące typy profilów i cele:

- [Aplikacje](#use-derived-credentials-for-app-authentication)
- [Poczta e-mail](../configuration/email-settings-ios.md)
- [VPN](../configuration/vpn-settings-ios.md)
- [Podpisywanie i szyfrowanie S/MIME](certificates-s-mime-encryption-sign.md)
- [Wi-Fi](../configuration/wi-fi-settings-ios.md)

  W przypadku profilów sieci Wi-Fi *Metoda uwierzytelniania* jest dostępna tylko wtedy, gdy **Typ EAP** jest ustawiony na jedną z następujących wartości:
  - EAP – TLS
  - EAP-TTLS
  - PEAP

### <a name="use-derived-credentials-for-app-authentication"></a>Korzystanie z pochodnych poświadczeń na potrzeby uwierzytelniania aplikacji

Pochodnych poświadczeń można używać do uwierzytelniania opartego na certyfikatach w witrynach i aplikacjach internetowych. Aby dostarczyć pochodne poświadczenie na potrzeby uwierzytelniania aplikacji, wykonaj następujące czynności w konsoli usługi Intune:  

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) i przejdź do pozycji **Konfiguracja urządzenia** > **Profile**, a następnie wybierz pozycję **Utwórz profil**.

2. W polu **Nazwa** wprowadź przyjazną nazwę profilu.

3. W polu **Platforma** wybierz opcję **iOS**.

4. W polu **Typ profilu** wybierz pozycję **Pochodne poświadczenie**.

5. Wybierz przycisk **OK**  a następnie kliknij pozycję **Utwórz**.

6. Wybierz pozycję **Przypisania**, aby wybrać grupy, które mają otrzymywać zasady.
 
Użytkownicy otrzymują powiadomienia w aplikacji lub w wiadomościach e-mail w zależności od ustawień określonych podczas konfigurowania wystawcy pochodnych poświadczeń. Powiadomienie informuje użytkownika o konieczności uruchomienia aplikacji Portal firmy w celu umożliwienia przetworzenia zasad pochodnych poświadczeń.

## <a name="renew-a-derived-credential"></a>Odnawianie pochodnego poświadczenia

Pochodnych poświadczeń nie można rozszerzać ani odnawiać. Zamiast tego użytkownicy muszą skorzystać z przepływu pracy żądania poświadczeń, aby zażądać nowego pochodnego poświadczenia dla swojego urządzenia.

Jeśli skonfigurujesz co najmniej jedną metodę w polu **Typ powiadomienia**, usługa Intune automatycznie powiadomi użytkowników, gdy bieżące pochodne poświadczenie osiągnie 80% swojego okresu użytkowania. Powiadomienie przeprowadza użytkowników przez proces żądania poświadczeń, dzięki czemu mogą oni uzyskać nowe pochodne poświadczenie.

Gdy urządzenie uzyska nowe pochodne poświadczenie, zasady, które korzystają z pochodnych poświadczeń, są ponownie wdrażane na tym urządzeniu.


## <a name="change-the-derived-credential-issuer"></a>Zmiana wystawcy pochodnego poświadczenia

Na poziomie dzierżawy można zmienić wystawcę poświadczeń, ale w danym momencie w dzierżawie może być obsługiwany tylko jeden wystawca.

Po zmianie wystawcy użytkownicy zostaną poproszeni o uzyskanie nowego pochodnego poświadczenia od nowego wystawcy. Wykonanie tej czynności jest wymagane, aby użytkownicy mogli skorzystać z pochodnego poświadczenia na potrzeby uwierzytelniania.

### <a name="change-the-issuer-for-your-tenant"></a>Zmiana wystawcy dla dzierżawy

> [!IMPORTANT]  
> Aby móc korzystać z pochodnych poświadczeń od wystawcy, który został usunięty, a następnie od razu ponownie skonfigurowany, należy mimo wszystko zaktualizować profile i urządzenia. Pochodne poświadczenia, które zostały uzyskane przed usunięciem wystawcy, tracą swoją ważność.

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) i przejdź do pozycji **Konfiguracja urządzenia** > **Pochodne poświadczenia**.

2. Wybierz pozycję **Usuń**, aby usunąć bieżącego wystawcę poświadczeń.

3. Skonfiguruj nowego wystawcę.

### <a name="update-profiles-that-use-derived-credentials"></a>Aktualizowanie profilów korzystających z pochodnych poświadczeń

Po usunięciu wystawcy i dodaniu nowego należy zmodyfikować każdy profil korzystający z pochodnych poświadczeń. Ta reguła obowiązuje nawet w przypadku przywrócenia poprzedniego wystawcy. Każda edycja profilu wyzwala aktualizację, nawet proste zmodyfikowanie *opisu* profilu.

### <a name="update-derived-credentials-on-devices"></a>Aktualizowanie pochodnych poświadczeń na urządzeniach

Po usunięciu wystawcy i dodaniu nowego użytkownicy urządzeń muszą zażądać nowego pochodnego poświadczenia. Ta reguła obowiązuje nawet w przypadku dodania tego samego wystawcy, który został usunięty. Proces żądania nowego pochodnego poświadczenia jest taki sam jak w przypadku rejestracji nowego urządzenia lub odnowienia istniejącego poświadczenia.

## <a name="next-steps"></a>Następne kroki

[Tworzenie profilów konfiguracji urządzeń](../configuration/device-profile-create.md)
