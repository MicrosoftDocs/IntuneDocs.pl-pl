---
title: "Zarządzanie przesyłaniem danych między aplikacjami systemu iOS"
titlesuffix: Azure portal
description: "Skorzystaj z tego tematu, aby dowiedzieć się, jak możesz użyć funkcji systemu iOS „Otwórz w” oraz zasad zarządzania aplikacjami mobilnymi do zarządzania transferami danych między aplikacjami."
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d10b2d64-8c72-4e9b-bd06-ab9d9486ba5e
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2d110a099b4957626d4368c9e63817674d6cfaa2
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-manage-data-transfer-between-ios-apps"></a>Zarządzanie przesyłaniem danych między aplikacjami systemu iOS
## <a name="manage-ios-apps"></a>Zarządzanie aplikacjami systemu iOS
W ramach ochrony danych firmowych należy upewnić się, że przesyłanie plików jest ograniczone do aplikacji zarządzanych przez Ciebie.  Aplikacjami systemu iOS można zarządzać następująco:

-   Zapobiegaj utracie firmowych danych dzięki skonfigurowaniu zasad ochrony aplikacji dla aplikacji określanych mianem **zarządzanych przez zasady**. Zobacz [wszystkie aplikacje zarządzane przez usługę Intune, którymi można zarządzać za pomocą zasad ochrony aplikacji](https://www.microsoft.com/cloud-platform/microsoft-intune-apps)

-   Możesz też wdrażać aplikacje i zarządzać nimi za pośrednictwem **kanału zarządzania urządzeniami przenośnymi**.  Wymaga to zarejestrowania urządzeń w rozwiązaniu do zarządzania urządzeniami przenośnymi. Mogą to być aplikacje **zarządzane przez zasady** lub inne zarządzane aplikacje.

**Zarządzanie funkcją Otwórz w** dla urządzeń z systemem iOS umożliwia ograniczenie przesyłania plików między aplikacjami wdrożonymi za pośrednictwem **kanału zarządzania urządzeniami przenośnymi**. Ograniczenia zarządzania funkcją „Otwórz w” są ustawiane w ustawieniach konfiguracji i wdrażane za pomocą rozwiązania do zarządzania urządzeniami przenośnymi.  Ograniczenia są stosowane w przypadku zainstalowania wdrożonej aplikacji przez użytkownika.

##  <a name="using-app-protection-with-ios-apps"></a>Korzystanie z ochrony aplikacji w odniesieniu do aplikacji systemu iOS
Zasady ochrony aplikacji można zastosować z funkcją **zarządzania funkcją Otwórz w** systemu iOS w celu ochrony danych na następujące sposoby:

-   **Urządzenia pracowników, które nie są zarządzane przez żadne rozwiązanie MDM:** można skonfigurować zasady ochrony aplikacji z ustawieniem **Allow app to transfer data to only Policy Managed apps** (Zezwalaj aplikacji na przesyłanie danych tylko do aplikacji zarządzanych przez zasady). Zachowanie funkcji „Otwórz w” w aplikacji zarządzanej przez zasady będzie przedstawiać tylko inne aplikacje zarządzane przez zasady jako opcję udostępniania. Jeśli użytkownik próbuje wysłać plik chroniony przez zasady w formie załącznika z poziomu usługi OneDrive przy użyciu natywnego programu pocztowego, nie będzie można tego pliku odczytać.

-   **Urządzenia zarządzane przez usługę Intune:** w przypadku urządzeń przenośnych zarejestrowanych w usłudze Intune przesyłanie danych między aplikacjami z zasadami ochrony aplikacji a innymi aplikacjami zarządzanymi systemu iOS wdrożonymi za pośrednictwem usługi Intune jest automatycznie dozwolone. Aby zezwolić na przesyłanie danych między aplikacjami z zasadami ochrony aplikacji, włącz ustawienie **Zezwalaj aplikacji na przesyłanie danych tylko do zarządzanych aplikacji**. Funkcja **zarządzania funkcją Otwórz w** umożliwia sterowanie przesyłaniem danych między aplikacjami, które zostały wdrożone za pomocą usługi Intune.   

-   **Urządzenia zarządzane przez rozwiązanie do zarządzania urządzeniami przenośnymi innej firmy:** można ograniczyć transfer danych tylko do zarządzanych aplikacji za pomocą funkcji **zarządzania funkcją Otwórz w** systemu iOS.
Aby upewnić się, że aplikacje, które wdrażasz za pomocą rozwiązania do zarządzania urządzeniami przenośnymi innej firmy, również są powiązane z zasadami ochrony aplikacji skonfigurowanymi w usłudze Intune, musisz skonfigurować ustawienie nazwy UPN użytkownika zgodnie ze wskazówkami w przewodniku [Konfigurowanie ustawienia nazwy UPN użytkownika](#configure-user-upn-setting-for-third-party-emm).  Gdy aplikacje są wdrażane z ustawieniem nazwy UPN użytkownika, zasady ochrony aplikacji są stosowane do aplikacji po zalogowaniu się użytkownika końcowego przy użyciu konta służbowego.

## <a name="configure-user-upn-setting-for-microsoft-intune-or-third-party-emm"></a>Konfigurowanie ustawienia nazwy UPN użytkownika dla usługi Microsoft Intune lub rozwiązania zarządzania mobilnością w przedsiębiorstwie innej firmy
Skonfigurowanie ustawienia nazwy UPN użytkownika jest **wymagane** w przypadku urządzeń zarządzanych przez usługę Intune lub rozwiązanie do zarządzania urządzeniami przenośnymi innej firmy. Poniżej przedstawiono ogólną procedurę konfigurowania ustawienia nazwy UPN oraz ogólny opis wynikowego środowiska użytkownika końcowego:

1.  W witrynie [Azure Portal](https://portal.azure.com) [utwórz i przypisz zasady ochrony aplikacji](app-protection-policies.md) dla systemu iOS. Skonfiguruj ustawienia zasad zgodnie z wymaganiami firmy i wybierz aplikacje systemu iOS, wobec których należy zastosować te zasady.

2.  Wdróż aplikacje i profil poczty e-mail, które mają być zarządzane za pośrednictwem usługi Intune lub rozwiązania do zarządzania urządzeniami przenośnymi innych firm, korzystając z poniższych ogólnych instrukcji. Opisano to również w Przykładzie 1.

3.  Wdróż aplikację z następującymi ustawieniami konfiguracji aplikacji:

      **key** = IntuneMAMUPN, **value** = <username@company.com>

      Przykład: [‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]

4.  Wdróż zasadę funkcji **Otwórz w** przy użyciu usługi Intune lub dostawcy rozwiązania do zarządzania urządzeniami przenośnymi innej firmy na zarejestrowanych urządzeniach.


### <a name="example-1-admin-experience-in-intune-or-third-party-mdm-console"></a>Przykład 1: Środowisko administracyjne w konsoli usługi Intune lub rozwiązania do zarządzania urządzeniami przenośnymi innej firmy

1. Przejdź do konsoli administracyjnej usługi Intune lub dostawcy rozwiązania do zarządzania urządzeniami przenośnymi innej firmy. Przejdź do sekcji konsoli, w której wdraża się ustawienia konfiguracji aplikacji na zarejestrowanych urządzeniach z systemem iOS.

2. W sekcji Konfiguracja aplikacji wprowadź następujące ustawienie:

  **key** = IntuneMAMUPN, **value** = <username@company.com>

  Dokładna składnia pary key/value (klucz/wartość) może się różnić w zależności od dostawcy rozwiązania do zarządzania urządzeniami przenośnymi innej firmy. W poniższej tabeli przedstawiono przykłady dostawców rozwiązania do zarządzania urządzeniami przenośnymi innej firmy i dokładnie wartości, które należy wprowadzić dla pary key/value.

|Dostawca rozwiązania do zarządzania urządzeniami przenośnymi innej firmy| Klucz konfiguracji | Typ wartości | Wartość konfiguracji|
| ------- | ---- | ---- | ---- |
|Microsoft Intune| IntuneMAMUPN | String | {UserPrincipalName}|
|VMware AirWatch| IntuneMAMUPN | String | {UserPrincipalName}|
|MobileIron | IntuneMAMUPN | String | ${userUPN} **lub** ${userEmailAddress} |


### <a name="example-2-end-user-experience"></a>Przykład 2: Środowisko użytkownika końcowego

1.  Użytkownik końcowy instaluje aplikację Microsoft Word na urządzeniu.

2.  Użytkownik końcowy uruchamia natywną zarządzaną aplikację poczty e-mail, aby uzyskać dostęp do poczty e-mail.

3.  Użytkownik końcowy próbuje otworzyć dokument z natywnego programu pocztowego w programie Microsoft Word.

4.  Po uruchomieniu aplikacji Word użytkownik końcowy otrzymuje monit o zalogowanie się przy użyciu konta służbowego.  To konto robocze, na które loguje się użytkownik końcowy po otrzymaniu monitu, powinno być zgodne z kontem określonym w ustawieniach konfiguracji aplikacji dla aplikacji Microsoft Word.

    > [!NOTE]
    > Podczas korzystania z aplikacji Word w kontekście prywatnym użytkownik końcowy może dodać inne konta osobiste do aplikacji Word, aby wykonać swoją pracę osobistą bez podlegania zasadom ochrony aplikacji.

5.  Po pomyślnym zalogowaniu ustawienia ochrony aplikacji zostaną zastosowane do aplikacji Word.

6.  Teraz transfer danych zakończy się pomyślnie i dokument zostanie oznaczony tożsamością firmową w aplikacji. Gdy dane są używane w kontekście służbowym, są stosowane odpowiednie ustawienia zasad.

### <a name="validate-user-upn-setting-for-third-party-emm"></a>Weryfikowanie ustawienia nazwy UPN użytkownika dla rozwiązania zarządzania mobilnością w przedsiębiorstwie innych firm

Po skonfigurowaniu ustawienia nazwy UPN użytkownika należy zweryfikować zdolność aplikacji systemu iOS do odbierania i spełniania wymagań zasad ochrony aplikacji usługi Intune.

Na przykład ustawienie zasady **Wymagaj numeru PIN aplikacji** można łatwo sprawdzić wzrokowo na urządzeniu. Jeśli ustawienie ma wartość **Tak**, podczas próby uzyskania dostępu do danych firmy użytkownikowi końcowemu powinien zostać wyświetlony monit o ustawienie lub wprowadzenie numeru PIN.

Najpierw [utwórz i przypisz zasady ochrony aplikacji](app-protection-policies.md) do aplikacji w systemie iOS. Zobacz [Weryfikowanie zasad ochrony aplikacji](app-protection-policies-validate.md), aby uzyskać więcej informacji na temat testowania zasad ochrony aplikacji.


### <a name="see-also"></a>Zobacz też
[Co to są zasady ochrony aplikacji w usłudze Intune](app-protection-policy.md)
