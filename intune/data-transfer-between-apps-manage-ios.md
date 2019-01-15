---
title: Zarządzanie przesyłaniem danych między aplikacjami systemu iOS | Microsoft Intune
description: Informacje na temat używania zasad zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune do zarządzania przesyłaniem danych między aplikacjami.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d10b2d64-8c72-4e9b-bd06-ab9d9486ba5e
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 50df69377afe053b1c10474fdda334a6e6792e27
ms.sourcegitcommit: e9ba1280b95565a5c5674b825881655d0303e688
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54297268"
---
# <a name="how-to-manage-data-transfer-between-ios-apps-in-microsoft-intune"></a>Jak zarządzać przesyłaniem danych między aplikacjami systemu iOS w usłudze Microsoft Intune

Aby chronić dane firmy, ogranicz przesyłanie plików tylko do aplikacji, którymi zarządzasz. Aplikacjami systemu iOS można zarządzać następująco:

-   Zapobiegaj utracie firmowych danych dzięki skonfigurowaniu zasad ochrony aplikacji dla aplikacji określanych mianem **zarządzanych przez zasady**. Zobacz [wszystkie aplikacje zarządzane przez usługę Intune, którymi można zarządzać za pomocą zasad ochrony aplikacji](https://www.microsoft.com/cloud-platform/microsoft-intune-apps)

-   Wdrażaj aplikacje i zarządzaj nimi za pomocą **kanału zarządzania urządzeniami przenośnymi**, co wymaga rejestracji urządzeń w rozwiązaniu do zarządzania urządzeniami przenośnymi (MDM). Możesz wdrażać aplikacje **zarządzane przez zasady** lub inne zarządzane aplikacje.

**Zarządzanie funkcją Otwórz w** dla urządzeń z systemem iOS umożliwia ograniczenie przesyłania plików między aplikacjami wdrożonymi za pośrednictwem **kanału zarządzania urządzeniami przenośnymi**. Ustaw ograniczenia *zarządzania funkcją Otwórz w* w ustawieniach konfiguracji i wdróż je za pomocą rozwiązania do zarządzania urządzeniami przenośnymi.  Ograniczenia są stosowane w przypadku zainstalowania wdrożonej aplikacji przez użytkownika.

##  <a name="use-app-protection-with-ios-apps"></a>Używanie ochrony aplikacji w przypadku aplikacji systemu iOS
Zasady ochrony aplikacji są używane z funkcją **zarządzania funkcją Otwórz w** systemu iOS w celu ochrony danych firmy na następujące sposoby:

-   **Urządzenia pracowników, które nie są zarządzane przez żadne rozwiązanie MDM:** można skonfigurować zasady ochrony aplikacji z ustawieniem **Allow app to transfer data to only Policy Managed apps** (Zezwalaj aplikacji na przesyłanie danych tylko do aplikacji zarządzanych przez zasady). Zachowanie funkcji *Otwórz w* w aplikacji zarządzanej przez zasady przedstawia tylko inne aplikacje zarządzane przez zasady jako opcje udostępniania. Jeśli użytkownik próbuje wysłać plik chroniony przez zasady w formie załącznika z usługi OneDrive przy użyciu natywnej aplikacji poczty, nie można tego pliku odczytać.

-   **Urządzenia zarządzane przez usługę Intune:** w przypadku urządzeń zarejestrowanych w usłudze Intune przesyłanie danych między aplikacjami z zasadami ochrony aplikacji a innymi zarządzanymi aplikacjami systemu iOS wdrożonymi za pośrednictwem usługi Intune jest automatycznie dozwolone. Aby określić sposób zezwalania na transfer danych do innych aplikacji, włącz ustawienie **Zezwalaj aplikacji na przesyłanie danych do innych aplikacji** i wybierz preferowany poziom udostępniania. Aby określić sposób zezwalania na odbieranie przez aplikację danych z innych aplikacji, włącz ustawienie **Zezwalaj aplikacji na odbieranie danych z innych aplikacji** i wybierz preferowany poziom odbierania danych. Funkcja **zarządzania funkcją Otwórz w** umożliwia sterowanie przesyłaniem danych między aplikacjami, które zostały wdrożone za pomocą usługi Intune. Aby uzyskać więcej informacji na temat odbierania i udostępniania danych aplikacji, zobacz [Ustawienia relokacji danych](app-protection-policy-settings-ios.md#data-protection-settings).   

-   **Urządzenia zarządzane przez rozwiązanie MDM innej firmy:** można ograniczyć transfer danych tylko do zarządzanych aplikacji za pomocą funkcji **zarządzania funkcją Otwórz w** systemu iOS.
Aby zapewnić, że aplikacje, które wdrażasz za pomocą rozwiązania do zarządzania urządzeniami przenośnymi innej firmy, również będą skojarzone z zasadami ochrony aplikacji usługi Intune, skonfiguruj ustawienie nazwy UPN użytkownika według opisu w sekcji [Konfigurowanie ustawienia nazwy UPN użytkownika](#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm). Gdy aplikacje są wdrażane z ustawieniem nazwy UPN użytkownika, zasady ochrony aplikacji są stosowane do aplikacji po zalogowaniu się użytkownika za pomocą konta służbowego.

## <a name="configure-user-upn-setting-for-microsoft-intune-or-third-party-emm"></a>Konfigurowanie ustawienia nazwy UPN użytkownika dla usługi Microsoft Intune lub rozwiązania zarządzania mobilnością w przedsiębiorstwie innej firmy
Skonfigurowanie ustawienia nazwy UPN użytkownika jest **wymagane** w przypadku urządzeń zarządzanych przez usługę Intune lub rozwiązanie do zarządzania urządzeniami przenośnymi innej firmy. Konfiguracja nazwy UPN współdziała z zasadami ochrony aplikacji wdrażanymi z usługi Intune. Poniżej przedstawiono ogólną procedurę konfigurowania ustawienia nazwy UPN oraz ogólny opis wynikowego środowiska użytkownika:

1.  W witrynie [Azure Portal](https://portal.azure.com) [utwórz i przypisz zasady ochrony aplikacji](app-protection-policies.md) dla systemu iOS. Skonfiguruj ustawienia zasad zgodnie z wymaganiami firmy i wybierz aplikacje systemu iOS, wobec których należy zastosować te zasady.

2.  Wdróż aplikacje i profil poczty e-mail, które mają być zarządzane za pośrednictwem usługi Intune lub rozwiązania do zarządzania urządzeniami przenośnymi innych firm, korzystając z poniższych ogólnych instrukcji. Opisano to również w *Przykładzie 1*.

3.  Wdróż aplikację z następującymi ustawieniami konfiguracji aplikacji:

      **key** = IntuneMAMUPN, **value** = <username@company.com>

      Przykład: [‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]

4.  Wdróż zasadę funkcji **Otwórz w** przy użyciu usługi Intune lub dostawcy rozwiązania do zarządzania urządzeniami przenośnymi innej firmy na zarejestrowanych urządzeniach.


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
   |ManageEngine Mobile Device Manager | IntuneMAMUPN | String | %upn% |


### <a name="example-2-end-user-experience"></a>Przykład 2: Środowisko użytkownika końcowego

1.  Użytkownik instaluje aplikację Microsoft Word na urządzeniu.

2.  Użytkownik uruchamia natywną zarządzaną aplikację poczty e-mail, aby uzyskać dostęp do poczty e-mail.

3.  Użytkownik próbuje otworzyć dokument z natywnego programu pocztowego w programie Microsoft Word.

4.  Po uruchomieniu aplikacji Word użytkownik otrzymuje monit o zalogowanie się przy użyciu konta służbowego. Konto wprowadzone przez użytkownika musi być zgodne z kontem określonym w ustawieniach konfiguracji aplikacji dla aplikacji Microsoft Word.

    > [!NOTE]
    > Użytkownik może dodać swoje konta osobiste i używać ich z aplikacją Word. Zasady ochrony aplikacji nie mają zastosowania, gdy użytkownik korzysta z aplikacji Word poza kontekstem służbowym. 

5.  Po zalogowaniu się ustawienia zasad ochrony aplikacji są stosowane do aplikacji Word.

6.  Teraz transfer danych zakończy się pomyślnie i dokument zostanie oznaczony tożsamością firmową w aplikacji.  Uznaje się, że dane są używane w kontekście służbowym i ustawienia zasad mają zastosowanie. 

### <a name="validate-user-upn-setting-for-third-party-emm"></a>Weryfikowanie ustawienia nazwy UPN użytkownika dla rozwiązania zarządzania mobilnością w przedsiębiorstwie innych firm

Po skonfigurowaniu ustawienia nazwy UPN użytkownika zweryfikuj zdolność aplikacji systemu iOS do odbierania i spełniania wymagań zasad ochrony aplikacji usługi Intune.

Na przykład ustawienie zasad **Wymagaj numeru PIN aplikacji** jest łatwe do przetestowania. Jeśli ustawienie zasad ma wartość **Tak**, użytkownik powinien zobaczyć monit o ustawienie lub wprowadzenie numeru PIN, zanim będzie mógł uzyskać dostęp do danych firmy.

Najpierw [utwórz i przypisz zasady ochrony aplikacji](app-protection-policies.md) do aplikacji w systemie iOS. Zobacz [Weryfikowanie zasad ochrony aplikacji](app-protection-policies-validate.md), aby uzyskać więcej informacji na temat testowania zasad ochrony aplikacji.


### <a name="see-also"></a>Zobacz także
[Co to są zasady ochrony aplikacji w usłudze Intune](app-protection-policy.md)
