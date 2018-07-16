---
title: Ustawianie ograniczeń rejestracji w usłudze Microsoft Intune
titlesuffix: ''
description: Ograniczanie rejestrowania według platformy i ustawianie limitu rejestracji urządzeń w usłudze Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7eee5baebb8373488999a5e75db5288e483379e5
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905822"
---
# <a name="set-enrollment-restrictions"></a>Ustawianie ograniczeń rejestracji

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Jako administrator usługi Intune możesz utworzyć ograniczenia rejestracji i zarządzać nimi. Ograniczenia te definiują liczbę i typy urządzeń, które mogą zarejestrować się do zarządzania przy użyciu usługi Intune. Możesz utworzyć wiele ograniczeń i zastosować je do różnych grup użytkowników. Możesz ustawić [priorytet](#change-enrollment-restriction-priority) dla różnych ograniczeń.

>[!NOTE]
>Ograniczenia rejestrowania nie są funkcjami zabezpieczeń. Urządzenia, na których złamano zabezpieczenia, mogą błędnie podawać swój charakter. Te ograniczenia stanowią optymalną barierę dla niezłośliwych użytkowników.

>[!NOTE]
>Wspomniane w tym artykule ograniczenia rejestracji przypisane do grupy i funkcje ustawiania priorytetu są właśnie wdrażane w ramach bazy klientów usługi. Do czasu ukończenia wprowadzania możesz nie mieć dostępu do funkcji dotyczących grup i ustawiania priorytetu.

Konkretne ograniczenia rejestracji, które możesz utworzyć, obejmują poniższe:

- Maksymalna liczba zarejestrowanych urządzeń.
- Platformy urządzeń, które można zarejestrować:
  - Urządzenia z systemem Android.
  - Profil służbowy systemu Android.
  - iOS.
  - macOS.
  - Windows.
- Wersja systemu operacyjnego platformy dla systemów iOS, Android i Windows oraz profilu służbowego systemu Android. (Można używać wyłącznie wersji systemu Windows 10. Pozostaw pole puste, jeśli dozwolone jest użycie systemu Windows 8.1).
  - Minimalna wersja.
  - Maksymalna wersja.
- Ogranicz urządzenia prywatne (tylko z systemami iOS, Android i macOS lub profilem służbowym systemu Android).

## <a name="default-restrictions"></a>Ograniczenia domyślne

Ograniczenia domyślne są automatycznie zapewniane w przypadku ograniczeń rejestracji dla typu urządzeń i liczby urządzeń. Możesz zmienić opcje domyślne. Domyślnie ograniczenia mają zastosowanie do wszystkich użytkowników i rejestracji bez użytkowników. Możesz przesłonić te ustawienia domyślne, tworząc nowe ograniczenia o wyższych priorytetach.

## <a name="create-a-restriction"></a>Tworzenie ograniczenia

1. Zaloguj się do witryny Azure Portal.
2. Wybierz opcję **Więcej usług**, wyszukaj usługę **Intune**, a następnie wybierz usługę **Intune**.
3. Wybierz pozycję **Rejestrowanie urządzenia** > **Ograniczenia rejestracji**.
4. Wybierz opcję **Utwórz ograniczenie**.
5. Nadaj nazwę i wprowadź opis ograniczenia.
6. Wybierz opcję **Typ ograniczenia**, a następnie wybierz opcję **Utwórz**.
7. W przypadku ograniczeń dotyczących limitu urządzeń wybierz opcję **Limit urządzeń**, aby ustawić maksymalną liczbę urządzeń, które użytkownik może zarejestrować.
8. W przypadku ograniczeń dotyczących typu urządzeń wybierz opcję **Platformy** oraz **Konfiguracje platformy**, aby zezwalać na różne platformy i wersje lub je blokować.
9. Wybierz pozycję **Przypisania** > **+ Wybierz grupy**.
10. W obszarze **Wybieranie grup** wybierz co najmniej jedną grupę, a następnie wybierz pozycję **Wybierz**. Ograniczenie ma zastosowanie wyłącznie do grup, do których zostało przypisane. Jeśli nie przypiszesz ograniczenia do co najmniej jednej grupy, nie będzie mieć żadnego efektu.
11. Wybierz pozycję **Zapisz**.
12. Nowe ograniczenie jest tworzone z priorytetem tuż nad ograniczeniami domyślnymi. Możesz [zmienić priorytet](#change-enrollment-restriction-priority).

## <a name="set-device-type-restrictions"></a>Ustawianie ograniczeń typu urządzeń

Możesz zmienić ustawienia ograniczeń dotyczących typu urządzenia, wykonując poniższe czynności:

1. Zaloguj się do witryny Azure Portal.
2. Wybierz opcję **Więcej usług**, wyszukaj usługę **Intune**, a następnie wybierz usługę **Intune**.
3. Wybierz pozycję **Rejestrowanie urządzenia** > **Ograniczenia rejestracji**.
4. W obszarze **Ograniczenia typu urządzenia** wybierz ograniczenie, które chcesz ustawić.
5. Pod nazwą ograniczenia (w przypadku ograniczenia domyślnego **Wszyscy użytkownicy**) wybierz opcję **Platformy**. Wybierz pozycję **Zezwalaj** lub **Blokuj** dla każdej platformy na liście.
6. Wybierz pozycję **Zapisz**.
7. Pod nazwą ograniczenia (**Wszyscy użytkownicy** w przypadku ograniczenia domyślnego) wybierz opcję **Konfiguracje platformy**. Następnie wybierz minimalną i maksymalną **wersję** dla wymienionych platform. Obsługiwane wersje obejmują:
    - Profil służbowy systemu Android obsługuje wersję major.minor.rev.build.
    - System iOS obsługuje wersję major.minor.rev.
    - System Windows obsługuje tylko major.minor.rev.build dla systemu Windows 10.
  Wersje systemu operacyjnego nie mają zastosowania do urządzeń firmy Apple rejestrowanych przy użyciu programu Device Enrollment Program, usługi Apple School Manager lub aplikacji Apple Configurator.
8. Określ opcję **Zezwalaj** lub **Blokuj** dla **urządzeń osobistych** w przypadku każdej platformy na liście.
    ![Obszar roboczy ograniczania urządzeń z domyślnymi konfiguracjami platformy urządzeń i widocznymi skonfigurowanymi ustawieniami urządzeń będących własnością użytkownika](media/device-restrictions-platform-configurations.png)
9. Wybierz pozycję **Zapisz**.


>[!NOTE]
>- Jeśli zablokujesz rejestrację prywatnych urządzeń z systemem Android, urządzenia z profilami służbowymi systemu Android nadal będą mogły być rejestrowane.
>- Domyślnie ustawienia urządzeń z profilami służbowymi systemu Android są takie same jak ustawienia urządzeń z systemem Android. Nie będzie tak w przypadku zmiany ustawień profilu służbowego systemu Android.
>- Jeśli zablokujesz rejestrację urządzeń osobistych z profilami służbowymi systemu Android, jako profile służbowe systemu Android będzie można rejestrować tylko firmowe urządzenia z systemem Android.

## <a name="set-device-limit-restrictions"></a>Ustawianie ograniczeń limitu urządzeń

Możesz zmienić ustawienia ograniczeń dotyczących limitu liczby urządzeń, wykonując poniższe czynności:

1. Zaloguj się do witryny Azure Portal.
2. Wybierz opcję **Więcej usług**, wyszukaj usługę **Intune**, a następnie wybierz usługę **Intune**.
3. Wybierz pozycję **Rejestrowanie urządzenia** > **Ograniczenia rejestracji**.
4. W obszarze **Ograniczenia limitu urządzenia** wybierz ograniczenie, które chcesz ustawić.
5. Wybierz opcję **Limit urządzeń**, a następnie na liście rozwijanej wybierz maksymalną liczbę urządzeń, które może zarejestrować użytkownik.
    ![Blok ograniczeń dotyczących limitu liczby urządzeń z ograniczeniami limitu liczby urządzeń](./media/device-restrictions-limit.png)
6. Wybierz pozycję **Zapisz**.


Użytkownikom zostanie wyświetlone powiadomienie, gdy osiągną limit liczby zarejestrowanych urządzeń. Na przykład w systemie iOS wygląda ono następująco:

![Powiadomienie o limicie urządzeń w systemie iOS](./media/enrollment-restrictions-ios-set-limit-notification.png)

## <a name="change-enrollment-restriction-priority"></a>Zmiana priorytetu ograniczenia rejestracji

Priorytet jest używany, jeśli użytkownik istnieje w wielu grupach, którym przypisano ograniczenia. Użytkownicy podlegają tylko ograniczeniu o najwyższym priorytecie, które zostało przypisane do grupy, w której się znajdują. Przykładowo Jan znajduje się w grupie A, której przypisano ograniczenia o priorytecie 5, oraz w grupie B, której przypisano ograniczenia o priorytecie 2. Jan podlega wyłącznie ograniczeniom o priorytecie 2.

Po utworzeniu ograniczenia jest ono dodawane do listy bezpośrednio nad ograniczeniem domyślnym.

Rejestracja urządzeń obejmuje domyślne ograniczenia dla typu urządzeń i liczby urządzeń. Te dwa ograniczenia mają zastosowanie do wszystkich użytkowników, chyba że zostaną zastąpione przez ograniczenia o wyższym priorytecie.

Możesz zmienić priorytet dowolnego ograniczenia innego niż domyślne.

1. Zaloguj się do witryny Azure Portal.
2. Wybierz opcję **Więcej usług**, wyszukaj usługę **Intune**, a następnie wybierz usługę **Intune**.
3. Wybierz pozycję **Rejestrowanie urządzenia** > **Ograniczenia rejestracji**.
4. Umieść kursor nad ograniczeniem na liście priorytetów.
5. Używając trzech pionowych punktów, przeciągnij priorytet do żądanej pozycji na liście.
