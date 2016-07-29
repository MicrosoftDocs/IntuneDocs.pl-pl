---
title: "Zarządzanie przesyłaniem danych między aplikacjami systemu iOS | Microsoft Intune"
description: "Skorzystaj z tego tematu, aby dowiedzieć się, jak możesz użyć funkcji systemu iOS Otwórz w oraz zasad zarządzania aplikacjami mobilnymi do zarządzania transferami danych pomiędzy aplikacjami."
keywords: 
author: karthikaraman
manager: jeffgilb
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3a4515c1-b325-4ac1-9f0a-45ac27e00681
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c72c8e1a764af73ba4d421ca6637ee91ab7bca0a
ms.openlocfilehash: 52ddcb22b27443b42a365a84f1769e90f1e9e8a0


---

# Zarządzanie przesyłaniem danych między aplikacjami systemu iOS za pomocą usługi Microsoft Intune
## Zarządzanie aplikacjami systemu iOS
W ramach ochrony danych firmowych należy upewnić się, że przesyłanie plików jest ograniczone do aplikacji zarządzanych przez Ciebie.  Aplikacjami systemu iOS można zarządzać następująco:

-   Zapobiegaj utracie danych firmowych poprzez skonfigurowanie zasad zarządzania aplikacjami mobilnymi dla aplikacji, które będziemy nazywać aplikacjami **zarządzanymi przez zasady**.

-   Możesz też wdrażać aplikacje i zarządzać nimi za pośrednictwem **kanału zarządzania urządzeniami przenośnymi**.  Wymaga to zarejestrowania urządzeń w rozwiązaniu do zarządzania urządzeniami przenośnymi. Mogą to być aplikacje **zarządzane przez zasady** lub inne zarządzane aplikacje.

**Zarządzanie funkcją Otwórz w** dla urządzeń z systemem iOS umożliwia ograniczenie przesyłania plików między aplikacjami wdrożonymi za pośrednictwem **kanału zarządzania urządzeniami przenośnymi**. Ograniczenia zarządzania funkcją „Otwórz w” są ustawiane w ustawieniach konfiguracji i wdrażane za pomocą rozwiązania do zarządzania urządzeniami przenośnymi.  Ograniczenia są stosowane w przypadku zainstalowania wdrożonej aplikacji przez użytkownika.
##  Używanie zasad zarządzania aplikacjami mobilnymi z aplikacjami systemu iOS
Zasady zarządzania aplikacjami mobilnymi można zastosować z funkcją **zarządzania funkcją Otwórz w** systemu iOS w celu ochrony danych następująco:

-   **Urządzenia pracowników, które nie są zarządzane przez żadne rozwiązanie do zarządzania urządzeniami przenośnymi:** można skonfigurować dla zasad zarządzania aplikacjami mobilnymi ustawienie **Zezwalaj aplikacji na przesyłanie danych tylko do zarządzanych aplikacji**. Gdy użytkownik końcowy otworzy chroniony plik w aplikacji, która nie jest zarządzana przez zasady, pliku nie będzie można odczytać.

-   **Urządzenia zarządzane przez usługę Intune:** dla urządzeń przenośnych zarejestrowanych w usłudze Intune przesyłanie danych między aplikacjami z zasadami zarządzania aplikacjami mobilnymi i innymi aplikacjami zarządzanymi systemu iOS wdrożonymi za pośrednictwem usług Intune jest automatycznie dozwolone. Aby zezwolić na przesyłanie danych między aplikacjami z zasadami zarządzania aplikacjami mobilnymi, włącz opcję **Zezwalaj aplikacji na przesyłanie danych tylko do zarządzanych aplikacji**. Funkcja **zarządzania funkcją Otwórz w** umożliwia sterowanie przesyłaniem danych między aplikacjami, które zostały wdrożone za pomocą usługi Intune.   

-   **Urządzenia zarządzane przez rozwiązanie do zarządzania urządzeniami przenośnymi innej firmy:** można ograniczyć transfer danych tylko do zarządzanych aplikacji za pomocą funkcji **zarządzania funkcją Otwórz w** systemu iOS.
Aby upewnić się, że aplikacje, które wdrażasz za pomocą rozwiązania do zarządzania urządzeniami przenośnymi innej firmy, również są powiązane z zasadami zarządzania aplikacjami mobilnymi skonfigurowanymi w usłudze Intune, musisz skonfigurować ustawienie nazwy UPN użytkownika zgodnie ze wskazówkami w temacie [Konfigurowanie ustawienia nazwy UPN użytkownika](#configure-user-upn-setting).  Jeśli aplikacje zostały wdrożone za pomocą ustawień nazwy UPN użytkownika, zasady zarządzania aplikacjami mobilnymi zostaną zastosowane do aplikacji po zalogowaniu się użytkownika końcowego przy użyciu konta służbowego.

> [!IMPORTANT]
> Ustawienie nazwy UPN użytkownika jest wymagane tylko w przypadku aplikacji wdrożonych na urządzeniach zarządzanych przez rozwiązanie do zarządzania urządzeniami przenośnymi innej firmy.  To ustawienie nie jest wymagane w przypadku urządzeń zarządzanych przez usługę Intune.

## Konfigurowanie ustawienia nazwy UPN użytkownika
Ta konfiguracja jest wymagana w przypadku urządzeń zarządzanych przez rozwiązanie do zarządzania urządzeniami przenośnymi innej firmy. Poniżej przedstawiono ogólną procedurę implementowania ustawienia nazwy UPN oraz ogólny opis wynikowego środowiska użytkownika końcowego:


1.  W portalu Azure [skonfiguruj zasady zarządzania aplikacjami mobilnymi](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) dla platformy iOS. Skonfiguruj ustawienia zasad zgodnie z wymaganiami firmy i wybierz aplikacje, wobec których należy zastosować te zasady.

2.  Przeprowadź wdrażanie aplikacji i profilu poczty e-mail, którymi chcesz zarządzać za pośrednictwem rozwiązania do zarządzania urządzeniami przenośnymi innej firmy, **korzystając z ustawień opisanych w kroku 3 i 4**.

3.  Wdróż aplikację, używając następujących ustawień konfiguracji aplikacji: key=IntuneMAMUPN, Value=<nazwa_użytkownika@firma.com> [przykład: ‘IntuneMAMUPN’, ‘jannowak@microsoft.com’]

4.  Wdróż zasady zarządzania funkcją Otwórz w na zarejestrowanych urządzeniach.

### Przykład środowiska użytkownika końcowego

1.  Użytkownik końcowy instaluje aplikację Microsoft Word na urządzeniu.

2.  Użytkownik końcowy uruchamia natywną zarządzaną aplikację poczty e-mail, aby uzyskać dostęp do poczty e-mail.

3.  Użytkownik końcowy próbuje otworzyć dokument z natywnego programu pocztowego w programie Microsoft Word.

4.  Po uruchomieniu aplikacji Word użytkownik końcowy otrzymuje monit o zalogowanie się przy użyciu konta służbowego.  To konto robocze, na które loguje się użytkownik końcowy po otrzymaniu monitu, powinno być zgodne z kontem określonym w ustawieniach konfiguracji aplikacji dla aplikacji Microsoft Word.

    > [!NOTE]
    > W przypadku osobistego zastosowania aplikacji Word użytkownik końcowy może dodać inne konta osobiste do aplikacji Word, aby wykonać swoją pracę osobistą bez podlegania zasadom zarządzania aplikacjami mobilnymi.

5.  Gdy użytkownik zaloguje się ponownie, ustawienia zasad aplikacji zostaną zastosowane do aplikacji Word.

6.  Teraz transfer danych zakończy się pomyślnie i dokument zostanie oznaczony jako tożsamość firmowa w aplikacji. Gdy dane są używane w kontekście służbowym, są stosowane odpowiednie ustawienia zasad.

### Zobacz także
[Ochrona danych aplikacji przy użyciu zasad zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Jul16_HO3-->


