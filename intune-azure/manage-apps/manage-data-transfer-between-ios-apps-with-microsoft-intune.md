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
ms.sourcegitcommit: 424fae862592c1ab5b4221fb5ad40a52c39f6760
ms.openlocfilehash: 8846417efd34db32d5a5c872ef438f5a0bc57e36


---

# <a name="how-to-manage-data-transfer-between-ios-apps"></a>Zarządzanie przesyłaniem danych między aplikacjami systemu iOS 
## <a name="manage-ios-apps"></a>Zarządzanie aplikacjami systemu iOS
W ramach ochrony danych firmowych należy upewnić się, że przesyłanie plików jest ograniczone do aplikacji zarządzanych przez Ciebie.  Aplikacjami systemu iOS można zarządzać następująco:

-   Zapobiegaj utracie firmowych danych dzięki skonfigurowaniu zasad ochrony aplikacji dla aplikacji określanych mianem **zarządzanych przez zasady**.

-   Możesz też wdrażać aplikacje i zarządzać nimi za pośrednictwem **kanału zarządzania urządzeniami przenośnymi**.  Wymaga to zarejestrowania urządzeń w rozwiązaniu do zarządzania urządzeniami przenośnymi. Mogą to być aplikacje **zarządzane przez zasady** lub inne zarządzane aplikacje.

**Zarządzanie funkcją Otwórz w** dla urządzeń z systemem iOS umożliwia ograniczenie przesyłania plików między aplikacjami wdrożonymi za pośrednictwem **kanału zarządzania urządzeniami przenośnymi**. Ograniczenia zarządzania funkcją „Otwórz w” są ustawiane w ustawieniach konfiguracji i wdrażane za pomocą rozwiązania do zarządzania urządzeniami przenośnymi.  Ograniczenia są stosowane w przypadku zainstalowania wdrożonej aplikacji przez użytkownika.
##  <a name="using-app-protection-with-ios-apps"></a>Korzystanie z ochrony aplikacji w odniesieniu do aplikacji systemu iOS
Zasady ochrony aplikacji można zastosować z funkcją **zarządzania funkcją Otwórz w** systemu iOS w celu ochrony danych na następujące sposoby:

-   **Urządzenia pracowników, które nie są zarządzane przez żadne rozwiązanie do zarządzania urządzeniami przenośnymi:** można skonfigurować dla zasad ochrony aplikacji ustawienie **Zezwalaj aplikacji na przesyłanie danych tylko do zarządzanych aplikacji**. Gdy użytkownik końcowy otworzy chroniony plik w aplikacji, która nie jest zarządzana przez zasady, pliku nie będzie można odczytać.

-   **Urządzenia zarządzane przez usługę Intune:** dla urządzeń przenośnych zarejestrowanych w usłudze Intune przesyłanie danych między aplikacjami z zasadami ochrony aplikacji i innymi aplikacjami zarządzanymi systemu iOS wdrożonymi za pośrednictwem usług Intune jest automatycznie dozwolone. Aby zezwolić na przesyłanie danych między aplikacjami z zasadami ochrony aplikacji, włącz opcję **Zezwalaj aplikacji na przesyłanie danych tylko do zarządzanych aplikacji**. Funkcja **zarządzania funkcją Otwórz w** umożliwia sterowanie przesyłaniem danych między aplikacjami, które zostały wdrożone za pomocą usługi Intune.   

-   **Urządzenia zarządzane przez rozwiązanie do zarządzania urządzeniami przenośnymi innej firmy:** można ograniczyć transfer danych tylko do zarządzanych aplikacji za pomocą funkcji **zarządzania funkcją Otwórz w** systemu iOS.
Aby upewnić się, że aplikacje, które wdrażasz za pomocą rozwiązania do zarządzania urządzeniami przenośnymi innej firmy, również są powiązane z zasadami ochrony aplikacji skonfigurowanymi w usłudze Intune, musisz skonfigurować ustawienie nazwy UPN użytkownika zgodnie ze wskazówkami w przewodniku [Konfigurowanie ustawienia nazwy UPN użytkownika](#configure-user-upn-setting).  Jeśli aplikacje zostały wdrożone za pomocą ustawień nazwy UPN użytkownika, zasady ochrony aplikacji zostaną zastosowane do aplikacji po zalogowaniu się użytkownika końcowego przy użyciu konta służbowego.

> [!IMPORTANT]
> Ustawienie nazwy UPN użytkownika jest wymagane tylko w przypadku aplikacji wdrożonych na urządzeniach zarządzanych przez rozwiązanie do zarządzania urządzeniami przenośnymi innej firmy.  To ustawienie nie jest wymagane w przypadku urządzeń zarządzanych przez usługę Intune.

## <a name="configure-user-upn-setting"></a>Konfigurowanie ustawienia nazwy UPN użytkownika
Ta konfiguracja jest wymagana w przypadku urządzeń zarządzanych przez rozwiązanie do zarządzania urządzeniami przenośnymi innej firmy. Poniżej przedstawiono ogólną procedurę implementowania ustawienia nazwy UPN oraz ogólny opis wynikowego środowiska użytkownika końcowego:


1.  W portalu Azure [skonfiguruj zasady zarządzania aplikacjami mobilnymi](app-protection-policies.md) dla platformy iOS. Skonfiguruj ustawienia zasad zgodnie z wymaganiami firmy i wybierz aplikacje, wobec których należy zastosować te zasady.

2.  Przeprowadź wdrażanie aplikacji i profilu poczty e-mail, którymi chcesz zarządzać za pośrednictwem rozwiązania do zarządzania urządzeniami przenośnymi innej firmy, **korzystając z ustawień opisanych w kroku 3 i 4**.

3.  Wdróż aplikację, używając następujących ustawień konfiguracji aplikacji: key=IntuneMAMUPN, Value=<username@company.com> [example: ‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]

4.  Wdróż zasady zarządzania funkcją Otwórz w na zarejestrowanych urządzeniach.

### <a name="example-end-user-experience"></a>Przykład środowiska użytkownika końcowego

1.  Użytkownik końcowy instaluje aplikację Microsoft Word na urządzeniu.

2.  Użytkownik końcowy uruchamia natywną zarządzaną aplikację poczty e-mail, aby uzyskać dostęp do poczty e-mail.

3.  Użytkownik końcowy próbuje otworzyć dokument z natywnego programu pocztowego w programie Microsoft Word.

4.  Po uruchomieniu aplikacji Word użytkownik końcowy otrzymuje monit o zalogowanie się przy użyciu konta służbowego.  To konto robocze, na które loguje się użytkownik końcowy po otrzymaniu monitu, powinno być zgodne z kontem określonym w ustawieniach konfiguracji aplikacji dla aplikacji Microsoft Word.

    > [!NOTE]
    > W przypadku zastosowania aplikacji Word w kontekście osobistym użytkownik końcowy może dodać do niej inne konta osobiste, aby wykonać swoją prywatną pracę bez podlegania zasadom ochrony aplikacji.

5.  Gdy użytkownik zaloguje się ponownie, ustawienia zasad aplikacji zostaną zastosowane do aplikacji Word.

6.  Teraz transfer danych zakończy się pomyślnie i dokument zostanie oznaczony jako tożsamość firmowa w aplikacji. Gdy dane są używane w kontekście służbowym, są stosowane odpowiednie ustawienia zasad.

### <a name="see-also"></a>Zobacz także
[Co to są zasady ochrony aplikacji w usłudze Intune](what-is-app-protection-policy.md)



<!--HONumber=Feb17_HO1-->


