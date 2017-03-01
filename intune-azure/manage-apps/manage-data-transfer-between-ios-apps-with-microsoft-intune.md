---
title: "Zarządzanie przesyłaniem danych między aplikacjami systemu iOS | Wersja zapoznawcza usługi Intune Azure | Dokumentacja firmy Microsoft"
description: "Wersja zapoznawcza usługi Intune Azure: zapoznaj się z tym tematem, aby dowiedzieć się, jak możesz użyć funkcji systemu iOS Otwórz w oraz zasad zarządzania aplikacjami mobilnymi do zarządzania przesyłaniem danych między aplikacjami."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d10b2d64-8c72-4e9b-bd06-ab9d9486ba5e
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c09c0b5d76a3035b2af82fe32d4b6c6e35d06baf
ms.openlocfilehash: 4ad494b42313e064a2d5ecc8056e19a522cfe051
ms.lasthandoff: 02/16/2017


---

# <a name="how-to-manage-data-transfer-between-ios-apps"></a>Zarządzanie przesyłaniem danych między aplikacjami systemu iOS
## <a name="manage-ios-apps"></a>Zarządzanie aplikacjami systemu iOS
W ramach ochrony danych firmowych należy upewnić się, że przesyłanie plików jest ograniczone do aplikacji zarządzanych przez Ciebie.  Aplikacjami systemu iOS można zarządzać następująco:

-   Zapobiegaj utracie firmowych danych dzięki skonfigurowaniu zasad ochrony aplikacji dla aplikacji określanych mianem **zarządzanych przez zasady**. Zobacz [wszystkie aplikacje obsługujące usługę Intune, którymi można zarządzać za pomocą zasad ochrony aplikacji](https://www.microsoft.com/cloud-platform/microsoft-intune-apps)

-   Możesz też wdrażać aplikacje i zarządzać nimi za pośrednictwem **kanału zarządzania urządzeniami przenośnymi**.  Wymaga to zarejestrowania urządzeń w rozwiązaniu do zarządzania urządzeniami przenośnymi. Mogą to być aplikacje **zarządzane przez zasady** lub inne zarządzane aplikacje.

**Zarządzanie funkcją Otwórz w** dla urządzeń z systemem iOS umożliwia ograniczenie przesyłania plików między aplikacjami wdrożonymi za pośrednictwem **kanału zarządzania urządzeniami przenośnymi**. Ograniczenia zarządzania funkcją „Otwórz w” są ustawiane w ustawieniach konfiguracji i wdrażane za pomocą rozwiązania do zarządzania urządzeniami przenośnymi.  Ograniczenia są stosowane w przypadku zainstalowania wdrożonej aplikacji przez użytkownika.
##  <a name="using-app-protection-with-ios-apps"></a>Korzystanie z ochrony aplikacji w odniesieniu do aplikacji systemu iOS
Zasady ochrony aplikacji można zastosować z funkcją **zarządzania funkcją Otwórz w** systemu iOS w celu ochrony danych na następujące sposoby:

-   **Urządzenia pracowników, które nie są zarządzane przez żadne rozwiązanie do zarządzania urządzeniami przenośnymi:** można skonfigurować dla zasad ochrony aplikacji ustawienie **Zezwalaj aplikacji na przesyłanie danych tylko do zarządzanych aplikacji**. Gdy użytkownik końcowy otworzy chroniony plik w aplikacji, która nie jest zarządzana przez zasady, pliku nie będzie można odczytać.

-   **Urządzenia zarządzane przez usługę Intune:** w przypadku urządzeń przenośnych zarejestrowanych w usłudze Intune przesyłanie danych między aplikacjami z zasadami ochrony aplikacji a innymi aplikacjami zarządzanymi systemu iOS wdrożonymi za pośrednictwem usługi Intune jest automatycznie dozwolone. Aby zezwolić na przesyłanie danych między aplikacjami z zasadami ochrony aplikacji, włącz ustawienie **Zezwalaj aplikacji na przesyłanie danych tylko do zarządzanych aplikacji**. Funkcja **zarządzania funkcją Otwórz w** umożliwia sterowanie przesyłaniem danych między aplikacjami, które zostały wdrożone za pomocą usługi Intune.   

-   **Urządzenia zarządzane przez rozwiązanie do zarządzania urządzeniami przenośnymi innej firmy:** można ograniczyć transfer danych tylko do zarządzanych aplikacji za pomocą funkcji **zarządzania funkcją Otwórz w** systemu iOS.
Aby upewnić się, że aplikacje, które wdrażasz za pomocą rozwiązania do zarządzania urządzeniami przenośnymi innej firmy, również są powiązane z zasadami ochrony aplikacji skonfigurowanymi w usłudze Intune, musisz skonfigurować ustawienie nazwy UPN użytkownika zgodnie ze wskazówkami w przewodniku [Konfigurowanie ustawienia nazwy UPN użytkownika](#configure-user-upn-setting-for-third-party-emm).  Gdy aplikacje są wdrażane z ustawieniem nazwy UPN użytkownika, zasady ochrony aplikacji są stosowane do aplikacji po zalogowaniu się użytkownika końcowego przy użyciu konta służbowego.

> [!IMPORTANT]
> Ustawienie nazwy UPN użytkownika jest wymagane tylko w przypadku aplikacji wdrożonych na urządzeniach zarządzanych przez rozwiązanie do zarządzania urządzeniami przenośnymi innej firmy.  W przypadku urządzeń zarządzanych przez usługę Intune to ustawienie nie jest wymagane.


## <a name="configure-user-upn-setting-for-third-party-emm"></a>Konfigurowanie ustawienia nazwy UPN użytkownika dla rozwiązania zarządzania mobilnością w przedsiębiorstwie innych firm
Skonfigurowanie ustawienia nazwy UPN użytkownika jest **wymagane** w przypadku urządzeń zarządzanych przez rozwiązanie do zarządzania urządzeniami przenośnymi innej firmy. Poniżej przedstawiono ogólną procedurę konfigurowania ustawienia nazwy UPN oraz ogólny opis wynikowego środowiska użytkownika końcowego:


1.  W witrynie [Azure Portal](https://portal.azure.com) [utwórz i przypisz zasady ochrony aplikacji](app-protection-policies.md) dla systemu iOS. Skonfiguruj ustawienia zasad zgodnie z wymaganiami firmy i wybierz aplikacje systemu iOS, wobec których należy zastosować te zasady.

2.  Wdróż aplikacje i profil poczty e-mail, które mają być zarządzane **za pośrednictwem rozwiązania do zarządzania urządzeniami przenośnymi innej firmy**, korzystając z poniższych ogólnych instrukcji. Opisano to również w Przykładzie 1.

  1.  Wdróż aplikację z następującymi ustawieniami konfiguracji aplikacji:

      **key** = IntuneMAMUPN, **value** = <username@company.com>

      Przykład: [‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]

  2.  Wdróż zasadę funkcji Otwórz w przy użyciu dostawcy rozwiązania do zarządzania urządzeniami przenośnymi innej firmy na zarejestrowanych urządzeniach.


### <a name="example-1-admin-experience-in-third-party-mdm-console"></a>Przykład 1: Środowisko administracyjne w konsoli rozwiązania do zarządzania urządzeniami przenośnymi innej firmy

1. Przejdź do konsoli administracyjnej dostawcy rozwiązania do zarządzania urządzeniami przenośnymi innej firmy. Przejdź do sekcji konsoli, w której wdraża się ustawienia konfiguracji aplikacji na zarejestrowanych urządzeniach z systemem iOS.

2. W sekcji Konfiguracja aplikacji wprowadź następujące ustawienie:

  **key** = IntuneMAMUPN, **value** = <username@company.com>

  Dokładna składnia pary key/value (klucz/wartość) może się różnić w zależności od dostawcy rozwiązania do zarządzania urządzeniami przenośnymi innej firmy. W poniższej tabeli przedstawiono przykłady dostawców rozwiązania do zarządzania urządzeniami przenośnymi innej firmy i dokładnie wartości, które należy wprowadzić dla pary key/value.

|Dostawca rozwiązania do zarządzania urządzeniami przenośnymi innej firmy| Klucz konfiguracji | Typ wartości | Wartość konfiguracji|
| ------- | ---- | ---- | ---- |
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

Najpierw [utwórz i przypisz zasady ochrony aplikacji](app-protection-policies.md) do aplikacji w systemie iOS. Zobacz [Weryfikowanie zasad ochrony aplikacji](validate-app-protection-policies.md), aby uzyskać więcej informacji na temat testowania zasad ochrony aplikacji.


### <a name="see-also"></a>Zobacz także
[Co to są zasady ochrony aplikacji w usłudze Intune](what-is-app-protection-policy.md)

