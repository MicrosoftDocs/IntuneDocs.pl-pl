---
title: "Ustawianie ograniczeń rejestracji w usłudze Intune"
titlesuffix: Azure portal
description: "Ograniczanie rejestrowania według platformy i ustawianie limitu rejestracji urządzeń w usłudze Intune. \""
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d3e3f35648784de860eb7e3f2e203488bc77a96d
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/25/2018
---
# <a name="set-enrollment-restrictions"></a>Ustawianie ograniczeń rejestracji

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Jako administrator usługi Intune możesz utworzyć ograniczenia rejestracji i zarządzać nimi. Ograniczenia te definiują liczbę i rodzaje urządzeń, które mogą zarejestrować się do zarządzania przy użyciu usługi Intune. Możesz utworzyć wiele ograniczeń i zastosować je do różnych grup użytkowników. Możesz ustawić [priorytet](#change-enrollment-restriction-priority) dla różnych ograniczeń.

>[!NOTE]
>Ograniczenia rejestrowania nie są funkcjami zabezpieczeń. Urządzenia, na których złamano zabezpieczenia, mogą błędnie podawać swój charakter. Te ograniczenia stanowią optymalną barierę dla niezłośliwych użytkowników.

>[!NOTE]
>Wspomniane poniżej ograniczenia rejestracji przypisane do grupy i funkcje ustawiania priorytetu są właśnie wdrażane w ramach bazy klientów usługi. Do czasu ukończenia tego procesu możesz nie mieć dostępu do funkcji dotyczących grup i ustawiania priorytetu. 

Konkretne ograniczenia rejestracji, które możesz utworzyć, obejmują poniższe:

- Maksymalna liczba zarejestrowanych urządzeń
- Platformy urządzeń, które można zarejestrować:
  - Android
  - Program Android for Work
  - iOS
  - macOS
  - Windows
- Wersja systemu operacyjnego platformy dla systemu iOS, Android, Android for Work i Windows (mogą być używane tylko wersje systemu Windows 10, pozostaw to pole puste, jeśli dozwolony jest system Windows 8.1)
  - Minimalna wersja
  - Maksymalna wersja
- Ograniczenia urządzeń prywatnych (tylko z systemem iOS, Android, Android for Work i macOS)

## <a name="default-restrictions"></a>Ograniczenia domyślne

Ograniczenia domyślne są automatycznie zapewniane w przypadku ograniczeń rejestracji dla typu urządzeń i liczby urządzeń. Możesz zmienić opcje domyślne. Domyślnie ograniczenia mają zastosowanie do wszystkich użytkowników i rejestracji bez użytkowników. Możesz przesłonić te ustawienia domyślne, tworząc nowe ograniczenia o wyższych priorytetach.

## <a name="create-a-restriction"></a>Tworzenie ograniczenia

1. Zaloguj się do portalu Azure Portal.
2. Wybierz opcję **Więcej usług**, wyszukaj usługę **Intune**, a następnie wybierz usługę **Intune**.
3. Wybierz kolejno opcje **Rejestrowanie urządzenia** > **Ograniczenia rejestracji**.
4. Wybierz opcję **Utwórz ograniczenie**.
5. Nadaj nazwę i wprowadź opis ograniczenia.
6. Wybierz opcję **Typ ograniczenia**, a następnie kliknij opcję **Utwórz**.
7. W przypadku ograniczeń dotyczących limitu urządzeń kliknij opcję **Limit urządzeń**, aby ustawić maksymalną liczbę urządzeń, które użytkownik może zarejestrować.
8. W przypadku ograniczeń dotyczących typu urządzeń kliknij opcję **Platformy** oraz **Konfiguracje platformy**, aby zezwalać na różne platformy i wersje lub je blokować.
9. Kliknij pozycję **Przypisania** > **+ Wybierz grupy**.
10. W pozycji **Wybierz grupy** wybierz co najmniej jedną grupę, a następnie kliknij przycisk **Wybierz**. Ograniczenie ma zastosowanie wyłącznie do grup, do których zostało przypisane. Jeśli nie przypiszesz ograniczenia do co najmniej jednej grupy, nie będzie mieć żadnego efektu.
11. Kliknij polecenie **Zapisz**.
12. Nowe ograniczenie jest tworzone z priorytetem tuż nad ograniczeniami domyślnymi. Możesz [zmienić priorytet](#change-enrollment-restriction-priority).

## <a name="set-device-type-restrictions"></a>Ustawianie ograniczeń typu urządzeń

Możesz zmienić ustawienia ograniczeń dotyczących typu urządzenia, wykonując poniższe czynności:

1. Zaloguj się do portalu Azure Portal.
2. Wybierz opcję **Więcej usług**, wyszukaj usługę **Intune**, a następnie wybierz usługę **Intune**.
3. Wybierz kolejno opcje **Rejestrowanie urządzenia** > **Ograniczenia rejestracji**.
4. W obszarze **Ograniczenia typu urządzenia** wybierz ograniczenie, które chcesz ustawić.
5. Pod nazwą ograniczenia (w przypadku ograniczenia domyślnego **Wszyscy użytkownicy**) wybierz opcję **Platformy**. Wybierz pozycję **Zezwalaj** lub **Blokuj** dla każdej platformy na liście.
6. Kliknij polecenie **Zapisz**.
7. Pod nazwą ograniczenia (w przypadku ograniczenia domyślnego **Wszyscy użytkownicy**) wybierz opcję **Konfiguracje platformy**, a następnie wybierz minimalne i maksymalne **Wersje** dla platform na liście. Obsługiwane wersje obejmują:
  - systemy Android i Android for Work obsługują wersję major.minor.rev.build.
  - System iOS obsługuje wersję major.minor.rev.
  - System Windows obsługuje tylko major.minor.rev.build dla systemu Windows 10.
  Wersje systemu operacyjnego nie mają zastosowania do urządzeń firmy Apple rejestrowanych przy użyciu programu Device Enrollment Program, Apple School Manager lub aplikacji Apple Configurator. 
8. Określ opcję **Zezwalaj** lub **Blokuj** dla **urządzeń osobistych** w przypadku każdej platformy na liście.

    ![Zrzut ekranu przedstawiający obszar roboczy ograniczania urządzeń z domyślnymi konfiguracjami platformy urządzeń i widocznymi skonfigurowanymi ustawieniami urządzeń będących własnością użytkownika.](media/device-restrictions-platform-configurations.png)
9. Kliknij polecenie **Zapisz**.

>[!NOTE]
>- Jeśli zablokujesz rejestrację prywatnych urządzeń z systemem Android, urządzenia z programem Android for Work nadal będą mogły być rejestrowane.
>- Domyślnie ustawienia urządzeń programu Android for Work będą takie same jak ustawienia urządzeń z systemem Android. Nie będzie tak jednak w przypadku zmiany ustawień programu Android for Work.
>- Jeśli zablokujesz rejestrację urządzeń osobistych w programie Android for Work, będzie można rejestrować tylko firmowe urządzenia z systemem Android.

## <a name="set-device-limit-restrictions"></a>Ustawianie ograniczeń limitu urządzeń

Możesz zmienić ustawienia ograniczeń dotyczących limitu liczby urządzeń, wykonując poniższe czynności:

1. Zaloguj się do portalu Azure Portal.
2. Wybierz opcję **Więcej usług**, wyszukaj usługę **Intune**, a następnie wybierz usługę **Intune**.
3. Wybierz kolejno opcje **Rejestrowanie urządzenia** > **Ograniczenia rejestracji**.
4. W obszarze **Ograniczenia limitu urządzenia** wybierz ograniczenie, które chcesz ustawić.
5. Wybierz opcję **Limit urządzeń**, a następnie na liście rozwijanej wybierz maksymalną liczbę urządzeń, które może zarejestrować użytkownik.
    ![Zrzut ekranu przedstawiający blok ograniczeń dotyczących limitu liczby urządzeń z ograniczeniami limitu liczby urządzeń.](./media/device-restrictions-limit.png)
6. Kliknij polecenie **Zapisz**.

## <a name="change-enrollment-restriction-priority"></a>Zmiana priorytetu ograniczenia rejestracji

Priorytet jest używany, jeśli użytkownik istnieje w wielu grupach, którym przypisano ograniczenia. Użytkownicy podlegają tylko ograniczeniu o najwyższym priorytecie, które zostało przypisane do grupy, w której się znajdują. Przykładowo Jan znajduje się w grupie A, której przypisano ograniczenia o priorytecie 5, oraz w grupie B, której przypisano ograniczenia o priorytecie 2. Jan podlega wyłącznie ograniczeniom o priorytecie 2. 

Po utworzeniu ograniczenia jest ono dodawane do listy bezpośrednio nad ograniczeniem domyślnym.

Rejestracja urządzeń obejmuje domyślne ograniczenia dla typu urządzeń i liczby urządzeń. Te dwa ograniczenia mają zastosowanie do wszystkich użytkowników, chyba że zostaną zastąpione przez ograniczenia o wyższym priorytecie. 

Możesz zmienić priorytet dowolnego ograniczenia innego niż domyślne. 

**Aby zmienić priorytet ograniczeń**

1. Zaloguj się do portalu Azure Portal.
2. Wybierz opcję **Więcej usług**, wyszukaj usługę **Intune**, a następnie wybierz usługę **Intune**.
3. Wybierz kolejno opcje **Rejestrowanie urządzenia** > **Ograniczenia rejestracji**.
4. Umieść kursor nad ograniczeniem na liście priorytetów.
5. Używając trzech pionowych punktów, przeciągnij priorytet do żądanej pozycji na liście.





