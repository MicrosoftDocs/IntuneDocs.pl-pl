---
title: Zarządzanie przesyłaniem danych między aplikacjami systemu iOS
titleSuffix: Microsoft Intune
description: Informacje na temat używania zasad zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune do zarządzania przesyłaniem danych między aplikacjami.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/09/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d10b2d64-8c72-4e9b-bd06-ab9d9486ba5e
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 80ae9b3b1ab274e236ad43c52569574718d3eec4
ms.sourcegitcommit: 637375a390b6e34f9c4415c77b99fe2980bbf554
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/10/2020
ms.locfileid: "75839303"
---
# <a name="how-to-manage-data-transfer-between-ios-apps-in-microsoft-intune"></a>Jak zarządzać przesyłaniem danych między aplikacjami systemu iOS w usłudze Microsoft Intune

Aby chronić dane firmy, ogranicz przesyłanie plików tylko do aplikacji, którymi zarządzasz. Aplikacjami systemu iOS można zarządzać następująco:

- Chroń dane organizacji na kontach służbowych przez skonfigurowanie zasad ochrony aplikacji dla aplikacji, które nazywamy *aplikacjami zarządzanymi przez zasady*.  Zobacz [wszystkie aplikacje zarządzane przez usługę Intune, którymi można zarządzać za pomocą zasad ochrony aplikacji](https://www.microsoft.com/cloud-platform/microsoft-intune-apps)

- Wdrażaj aplikacje i nimi zarządzaj za pomocą zarządzania urządzeniami iOS, co wymaga rejestracji urządzeń w rozwiązaniu do zarządzania urządzeniami mobilnymi (MDM). Możesz wdrażać *aplikacje zarządzane przez zasady* lub inne aplikacje zarządzane przy użyciu systemu iOS.

Funkcja **Zarządzanie funkcją Otwórz w** dla zarejestrowanych urządzeń z systemem iOS umożliwia ograniczenie przesyłania plików między aplikacjami zarządzanymi systemu iOS. Ustaw ograniczenia funkcji *Zarządzanie funkcją Otwórz w* w ustawieniach konfiguracji i wdróż je za pomocą rozwiązania do zarządzania urządzeniami przenośnymi.  Ograniczenia są stosowane w przypadku zainstalowania wdrożonej aplikacji przez użytkownika.

## <a name="use-app-protection-with-ios-apps"></a>Używanie ochrony aplikacji w przypadku aplikacji systemu iOS
Zasady ochrony aplikacji są używane z funkcją **Zarządzanie funkcją Otwórz w** systemu iOS w celu ochrony danych firmy na następujące sposoby:

- **Urządzenia, które nie są zarządzane przez żadne rozwiązanie MDM:** Ustawienia zasad ochrony aplikacji można ustawić w taki sposób, aby kontrolować udostępnianie danych innym aplikacjom za pośrednictwem funkcji *Otwórz w* lub *Rozszerzenia udziałów*.  W tym celu skonfiguruj ustawienie **Wyślij dane organizacji do innych aplikacji** do wartości **Aplikacje zarządzane przez zasady z filtrowaniem okien dialogowych otwierania/udostępniania**.  Zachowanie funkcji *Okna dialogowe otwierania/udostępniania* w *aplikacji zarządzanej przez zasady* przedstawia tylko inne *aplikacje zarządzane przez zasady* jako opcje udostępniania. 

- **Urządzenia zarządzane przez rozwiązania MDM**: W przypadku urządzeń zarejestrowanych w usłudze Intune lub w rozwiązaniach MDM innych firm udostępnianie danych między aplikacjami z zasadami ochrony aplikacji a innymi zarządzanymi aplikacjami systemu iOS wdrożonymi za pośrednictwem rozwiązania MDM jest kontrolowane przez zasady ochrony aplikacji usługi Intune i funkcję **zarządzania funkcją Otwórz w** systemu iOS. Aby zapewnić, że aplikacje, które wdrażasz za pomocą rozwiązania do zarządzania urządzeniami przenośnymi, również będą skojarzone z zasadami ochrony aplikacji usługi Intune, skonfiguruj ustawienie nazwy UPN użytkownika według opisu w sekcji [Konfigurowanie ustawienia nazwy UPN użytkownika](data-transfer-between-apps-manage-ios.md#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm). Aby określić sposób zezwalania na transfer danych do innych aplikacji, włącz ustawienie **Wyślij dane organizacji do innych aplikacji** i wybierz preferowany poziom udostępniania. Aby określić sposób zezwalania na odbieranie przez aplikację danych z innych aplikacji, włącz ustawienie **Odbierz dane z innych aplikacji** i wybierz preferowany poziom odbierania danych. Aby uzyskać więcej informacji na temat odbierania i udostępniania danych aplikacji, zobacz [Ustawienia relokacji danych](app-protection-policy-settings-ios.md#data-protection).

## <a name="configure-user-upn-setting-for-microsoft-intune-or-third-party-emm"></a>Konfigurowanie ustawienia nazwy UPN użytkownika dla usługi Microsoft Intune lub rozwiązania zarządzania mobilnością w przedsiębiorstwie innej firmy
Skonfigurowanie ustawienia nazwy UPN użytkownika jest **wymagane** w przypadku urządzeń zarządzanych przez usługę Intune lub rozwiązanie do zarządzania urządzeniami przenośnymi innej firmy w celu zidentyfikowania konta zarejestrowanego użytkownika. Konfiguracja nazwy UPN współdziała z zasadami ochrony aplikacji wdrażanymi z usługi Intune. Poniżej przedstawiono ogólną procedurę konfigurowania ustawienia nazwy UPN oraz ogólny opis wynikowego środowiska użytkownika:

1. W witrynie [Azure Portal](https://portal.azure.com)[utwórz i przypisz zasady ochrony aplikacji](app-protection-policies.md) dla systemu iOS. Skonfiguruj ustawienia zasad zgodnie z wymaganiami firmy i wybierz aplikacje systemu iOS, wobec których należy zastosować te zasady.

2. Wdróż aplikacje i profil poczty e-mail, które mają być zarządzane za pośrednictwem usługi Intune lub rozwiązania do zarządzania urządzeniami przenośnymi innych firm, korzystając z poniższych ogólnych instrukcji. Opisano to również w *Przykładzie 1*.

3. Wdróż aplikację z następującymi ustawieniami konfiguracji aplikacji na urządzeniu zarządzanym:

      **key** = IntuneMAMUPN, **value** = <username@company.com>

      Przykład: [‘IntuneMAMUPN’, ‘janellecraig@contoso.com’]
      
     > [!NOTE]
     > W usłudze Intune typ rejestracji w zasadach konfiguracji aplikacji musi być ustawiony na **Urządzenia zarządzane**.
     > Ponadto aplikacja musi być zainstalowana z Portalu firmy usługi Intune (jeśli jest ustawiona jako dostępna) lub wypchnięta na urządzenie zgodnie z wymaganiami. 

4. Wdróż zasadę funkcji **Otwórz w** przy użyciu usługi Intune lub dostawcy rozwiązania do zarządzania urządzeniami przenośnymi innej firmy na zarejestrowanych urządzeniach.


### <a name="example-1-admin-experience-in-intune-or-third-party-mdm-console"></a>Przykład 1: Środowisko administracyjne w konsoli usługi Intune lub rozwiązania MDM innej firmy

1. Przejdź do konsoli administracyjnej usługi Intune lub dostawcy rozwiązania do zarządzania urządzeniami przenośnymi innej firmy. Przejdź do sekcji konsoli, w której wdraża się ustawienia konfiguracji aplikacji na zarejestrowanych urządzeniach z systemem iOS.

2. W sekcji Konfiguracja aplikacji wprowadź następujące ustawienie:

   **key** = IntuneMAMUPN, **value** = <username@company.com>

   Dokładna składnia pary key/value (klucz/wartość) może się różnić w zależności od dostawcy rozwiązania do zarządzania urządzeniami przenośnymi innej firmy. W poniższej tabeli przedstawiono przykłady innych firm dostarczających rozwiązania do zarządzania urządzeniami przenośnymi oraz dokładne wartości, które należy wprowadzić dla pary key/value.

   |Dostawca rozwiązania do zarządzania urządzeniami przenośnymi innej firmy| Klucz konfiguracji | Typ wartości | Wartość konfiguracji|
   | ------- | ---- | ---- | ---- |
   |Microsoft Intune| IntuneMAMUPN | String | {{UserPrincipalName}}|
   |VMware AirWatch| IntuneMAMUPN | String | {UserPrincipalName}|
   |MobileIron | IntuneMAMUPN | String | ${userUPN} **lub** ${userEmailAddress} |
   |Zarządzanie punktami końcowymi Citrix | IntuneMAMUPN | String | ${user.userprincipalname} |
   |ManageEngine Mobile Device Manager | IntuneMAMUPN | String | %upn% |

> [!NOTE]  
> Dla aplikacji Outlook dla systemu iOS w przypadku wdrożenia zasad konfiguracji aplikacji urządzeń zarządzanych przy użyciu opcji „Korzystanie z projektanta konfiguracji” i włączeniu opcji **Zezwalaj tylko na konta służbowe** klucz konfiguracji IntuneMAMUPN dla zasad jest konfigurowany automatycznie w tle. Więcej szczegółów zawiera sekcja często zadawanych pytań w artykule [Nowe środowisko zasad konfiguracji aplikacji programu Outlook dla systemów iOS i Android — ogólna konfiguracja aplikacji](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/New-Outlook-for-iOS-and-Android-App-Configuration-Policy/ba-p/370481). 


### <a name="example-2-end-user-experience"></a>Przykład 2: Środowisko użytkownika końcowego

*Udostępnianie z* aplikacji zarządzanej przez zasady *do innych aplikacji z funkcją udostępniania systemu operacyjnego*

1. Użytkownik otwiera aplikację Microsoft OneDrive na zarejestrowanym urządzeniu z systemem iOS i loguje się do konta służbowego.  Konto wprowadzone przez użytkownika musi być zgodne z nazwą UPN konta określoną w ustawieniach konfiguracji aplikacji dla aplikacji Microsoft OneDrive.

2. Po zalogowaniu ustawienia aplikacji skonfigurowane przez administratora mają zastosowanie do konta użytkownika w usłudze Microsoft OneDrive.  Obejmuje to skonfigurowanie ustawienia **Wyślij dane organizacji do innych aplikacji** do wartości **Aplikacje zarządzane przez zasady z udostępnianiem systemu operacyjnego**.

3. Użytkownik wyświetla podgląd pliku służbowego i próbuje udostępnić go za pomocą funkcji Otwórz w w aplikacji zarządzanej systemu iOS.  

4. Transfer danych zakończy się pomyślnie i dane będą chronione za pomocą **zarządzania funkcją Otwórz w** w aplikacji zarządzanej systemu iOS.  Aplikacja usługi Intune nie ma zastosowania do aplikacji, które nie są *aplikacjami zarządzanymi przez zasady*.

*Udostępnianie z* aplikacji zarządzanej systemu iOS *do*  aplikacji zarządzanej przez zasady *przy użyciu danych przychodzących organizacji*

1. Użytkownik otwiera natywną pocztę na zarejestrowanym urządzeniu z systemem iOS za pomocą zarządzanego profilu poczty e-mail.  

1. Użytkownik otwiera załącznik dokumentu służbowego z natywnej poczty w programie Microsoft Word.

1. Gdy aplikacja Word zostanie uruchomiona, mamy do czynienia z jedną z dwóch sytuacji:
   1. Dane są chronione przez aplikację usługi Intune, gdy:
      - Użytkownik jest zalogowany na koncie służbowym, które musi być zgodne z nazwą UPN konta określoną w ustawieniach konfiguracji aplikacji dla aplikacji Microsoft Word. 
      - Ustawienia aplikacji skonfigurowane przez administratora mają zastosowanie do konta użytkownika w programie Microsoft Word.  Obejmuje to skonfigurowanie ustawienia **Odbierz dane z innych aplikacji** do wartości **Wszystkie aplikacje z przychodzącymi danymi organizacji**.
      - Transfer danych kończy się pomyślnie i dokument zostaje oznaczony tożsamością służbową w aplikacji.  Aplikacja usługi Intune chroni akcje użytkownika dla dokumentu.
   1. Dane **nie** są chronione przez aplikację usługi Intune, gdy:
      - Użytkownik **nie** jest zalogowany na koncie służbowym.
      - Ustawienia skonfigurowane przez administratora **nie** mają zastosowania do programu Microsoft Word, ponieważ użytkownik nie jest zalogowany.
      - Transfer danych kończy się pomyślnie i dokument **nie** zostaje oznaczony tożsamością służbową w aplikacji.  Aplikacja usługi Intune **nie** chroni akcji użytkownika dla dokumentu, ponieważ nie jest on aktywny.

    > [!NOTE]
    > Użytkownik może dodać swoje konta osobiste i używać ich z aplikacją Word. Zasady ochrony aplikacji nie mają zastosowania, gdy użytkownik korzysta z aplikacji Word poza kontekstem służbowym. 

### <a name="validate-user-upn-setting-for-third-party-emm"></a>Weryfikowanie ustawienia nazwy UPN użytkownika dla rozwiązania zarządzania mobilnością w przedsiębiorstwie innych firm

Po skonfigurowaniu ustawienia nazwy UPN użytkownika zweryfikuj zdolność aplikacji systemu iOS do odbierania i spełniania wymagań zasad ochrony aplikacji usługi Intune.

Na przykład ustawienie zasad **Wymagaj numeru PIN aplikacji** jest łatwe do przetestowania. Jeśli ustawienie zasad ma wartość **Wymagaj**, użytkownik powinien zobaczyć monit o ustawienie lub wprowadzenie numeru PIN, zanim będzie mógł uzyskać dostęp do danych firmy.

Najpierw [utwórz i przypisz zasady ochrony aplikacji](app-protection-policies.md) do aplikacji w systemie iOS. Zobacz [Weryfikowanie zasad ochrony aplikacji](app-protection-policies-validate.md), aby uzyskać więcej informacji na temat testowania zasad ochrony aplikacji.


## <a name="see-also"></a>Zobacz także
[Co to są zasady ochrony aplikacji w usłudze Intune](app-protection-policy.md)
