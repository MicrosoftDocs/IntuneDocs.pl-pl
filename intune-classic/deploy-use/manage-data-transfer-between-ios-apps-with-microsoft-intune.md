---
title: "Zarządzanie przesyłaniem danych między aplikacjami systemu iOS | Microsoft Docs"
description: "Skorzystaj z tego tematu, aby dowiedzieć się, jak możesz użyć funkcji systemu iOS Otwórz w oraz zasad zarządzania aplikacjami mobilnymi do zarządzania transferami danych pomiędzy aplikacjami."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3a4515c1-b325-4ac1-9f0a-45ac27e00681
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: e71ebacec9d7b890b41e7650c8c50f42952c6326
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---

# <a name="manage-data-transfer-between-ios-apps-with-microsoft-intune"></a>Zarządzanie przesyłaniem danych między aplikacjami systemu iOS za pomocą usługi Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="manage-ios-apps"></a>Zarządzanie aplikacjami systemu iOS
W ramach ochrony danych firmowych należy upewnić się, że przesyłanie plików jest ograniczone do aplikacji zarządzanych przez Ciebie.  Aplikacjami systemu iOS można zarządzać następująco:

-   Zapobiegaj utracie firmowych danych dzięki skonfigurowaniu zasad ochrony aplikacji dla aplikacji określanych mianem **zarządzanych przez zasady**.

-   Możesz też wdrażać aplikacje i zarządzać nimi za pośrednictwem **kanału zarządzania urządzeniami przenośnymi**.  Wymaga to zarejestrowania urządzeń w rozwiązaniu do zarządzania urządzeniami przenośnymi. Mogą to być aplikacje **zarządzane przez zasady** lub inne zarządzane aplikacje.

**Zarządzanie funkcją Otwórz w** dla urządzeń z systemem iOS umożliwia ograniczenie przesyłania plików między aplikacjami wdrożonymi za pośrednictwem **kanału zarządzania urządzeniami przenośnymi**. Ograniczenia zarządzania funkcją „Otwórz w” są ustawiane w konfiguracji i wdrażane za pomocą rozwiązania do zarządzania urządzeniami przenośnymi.  Ograniczenia są stosowane w przypadku zainstalowania wdrożonej aplikacji przez użytkownika.

##  <a name="manage-data-transfer-between-ios-apps"></a>Zarządzanie przesyłaniem danych między aplikacjami systemu iOS
Zasad ochrony aplikacji można używać z funkcją **zarządzanie funkcją Otwórz w** systemu iOS w celu ochrony danych firmy na następujące sposoby:

-   **Urządzenia należące do pracowników niezarządzane przez żadne rozwiązanie do zarządzania urządzeniami przenośnymi:** można ustawić [ustawienie zasad ochrony aplikacji](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) na wartość **Zezwalaj aplikacji na przesyłanie danych tylko do zarządzanych aplikacji**. Gdy użytkownik końcowy otworzy chroniony plik w aplikacji, która nie jest zarządzana przez zasady, pliku nie będzie można odczytać.

-   **Urządzenia zarządzane przez usługę Intune:** w przypadku urządzeń zarejestrowanych w usłudze Intune przesyłanie danych między aplikacjami z zasadami ochrony aplikacji a innymi zarządzanymi aplikacjami systemu iOS wdrożonymi za pośrednictwem usługi Intune jest automatycznie dozwolone. Aby zezwolić na przesyłanie danych między aplikacjami z zasadami ochrony aplikacji, włącz ustawienie **Zezwalaj aplikacji na przesyłanie danych tylko do zarządzanych aplikacji**. Funkcja **zarządzania funkcją Otwórz w** umożliwia sterowanie przesyłaniem danych między aplikacjami, które zostały wdrożone za pomocą usługi Intune.   

-   **Urządzenia zarządzane przez rozwiązanie do zarządzania urządzeniami przenośnymi innej firmy:** można ograniczyć transfer danych tylko do zarządzanych aplikacji za pomocą funkcji **zarządzania funkcją Otwórz w** systemu iOS.
Aby upewnić się, że aplikacje, które wdrażasz za pomocą rozwiązania do zarządzania urządzeniami przenośnymi innej firmy, również są powiązane z zasadami ochrony aplikacji skonfigurowanymi w usłudze Intune, musisz skonfigurować ustawienie nazwy UPN użytkownika zgodnie ze wskazówkami w przewodniku [Konfigurowanie ustawienia nazwy UPN użytkownika](#configure-user-upn-setting-for-third-party-emm).  Gdy aplikacje są wdrażane z ustawieniem nazwy UPN użytkownika, zasady ochrony aplikacji są stosowane do aplikacji po zalogowaniu się użytkownika końcowego przy użyciu konta służbowego.

> [!IMPORTANT]
> Ustawienie nazwy UPN użytkownika jest wymagane tylko w przypadku aplikacji wdrożonych na urządzeniach zarządzanych przez rozwiązanie do zarządzania urządzeniami przenośnymi innej firmy.  W przypadku urządzeń zarządzanych przez usługę Intune to ustawienie nie jest wymagane.

## <a name="configure-user-upn-setting-for-third-party-emm"></a>Konfigurowanie ustawienia nazwy UPN użytkownika dla rozwiązania zarządzania mobilnością w przedsiębiorstwie innych firm
Skonfigurowanie ustawienia nazwy UPN użytkownika jest **wymagane** w przypadku urządzeń zarządzanych przez rozwiązanie do zarządzania urządzeniami przenośnymi innej firmy. Poniżej przedstawiono ogólną procedurę konfigurowania ustawienia nazwy UPN oraz ogólny opis wynikowego środowiska użytkownika końcowego:


1.  W witrynie Azure Portal [skonfiguruj zasady ochrony aplikacji](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) dla platformy iOS. Skonfiguruj ustawienia zasad zgodnie z wymaganiami firmy i wybierz aplikacje, wobec których należy zastosować te zasady.

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
| VMware AirWatch | IntuneMAMUPN | String | {UserPrincipalName}|
| MobileIron Core | IntuneMAMUPN | String | $EMAIL$ **lub** $USER_UPN$ |
| MobileIron Cloud | IntuneMAMUPN | String | ${userUPN} **lub** ${userEmailAddress} |

### <a name="example-2-end-user-experience"></a>Przykład 2: Środowisko użytkownika końcowego

1.  Użytkownik końcowy instaluje aplikację Microsoft Word na urządzeniu.

2.  Użytkownik końcowy uruchamia natywną zarządzaną aplikację poczty e-mail, aby uzyskać dostęp do poczty e-mail.

3.  Użytkownik końcowy próbuje otworzyć dokument z natywnego programu pocztowego w programie Microsoft Word.

4.  Po uruchomieniu aplikacji Word użytkownik końcowy otrzymuje monit o zalogowanie się przy użyciu konta służbowego.  To konto robocze, na które loguje się użytkownik końcowy po otrzymaniu monitu, powinno być zgodne z kontem określonym w ustawieniach konfiguracji aplikacji dla aplikacji Microsoft Word.

    > [!NOTE]
    > Podczas korzystania z aplikacji Word w kontekście prywatnym użytkownik końcowy może dodać inne konta osobiste do aplikacji Word, aby wykonać swoją pracę osobistą bez podlegania zasadom ochrony aplikacji.

5.  Po pomyślnym zalogowaniu ustawienia ochrony aplikacji zostaną zastosowane do aplikacji Word.

6.  Teraz przesyłanie pliku zakończy się pomyślnie i dokument zostanie oznaczony jako tożsamość firmowa w aplikacji. Ponadto plik jest używany w kontekście służbowym i są stosowane odpowiednie ustawienia zasad.

### <a name="validate-user-upn-setting-for-third-party-emm"></a>Weryfikowanie ustawienia nazwy UPN użytkownika dla rozwiązania zarządzania mobilnością w przedsiębiorstwie innych firm

Po skonfigurowaniu ustawienia nazwy UPN użytkownika należy zweryfikować zdolność aplikacji systemu iOS do odbierania i spełniania wymagań zasad ochrony aplikacji usługi Intune.

Na przykład ustawienie zasady **Wymagaj numeru PIN aplikacji** można łatwo sprawdzić wzrokowo na urządzeniu. Jeśli ustawienie ma wartość **Tak**, podczas próby uzyskania dostępu do danych firmy użytkownikowi końcowemu powinien zostać wyświetlony monit o ustawienie lub wprowadzenie numeru PIN.

Najpierw [utwórz i wdróż zasady ochrony aplikacji](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) na urządzeniu z systemem iOS. Zobacz [Weryfikowanie zasad ochrony aplikacji](validate-mobile-application-management.md), aby uzyskać więcej informacji na temat testowania zasad ochrony aplikacji.



### <a name="see-also"></a>Zobacz także
[Ochrona danych aplikacji przy użyciu zasad ochrony aplikacji w usłudze Microsoft Intune](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

