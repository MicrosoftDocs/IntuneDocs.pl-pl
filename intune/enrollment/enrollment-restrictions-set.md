---
title: Ustawianie ograniczeń rejestracji w usłudze Microsoft Intune
titleSuffix: ''
description: Ograniczanie rejestrowania według platformy i ustawianie limitu rejestracji urządzeń w usłudze Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/17/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 78f79a734d0a7b4901b2248b20abd9d304926dd2
ms.sourcegitcommit: e75718ee6cf93c0e6c915f2776b785fe8db9f7e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/10/2019
ms.locfileid: "74955511"
---
# <a name="set-enrollment-restrictions"></a>Ustawianie ograniczeń rejestracji

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Jako administrator usługi Intune możesz utworzyć ograniczenia rejestracji i nimi zarządzać. Ograniczenia te definiują, które urządzenia mogą zarejestrować się do zarządzania przy użyciu usługi Intune, m.in.:
- Liczba urządzeń.
- Systemy operacyjne i wersje.

Możesz utworzyć wiele ograniczeń i zastosować je do różnych grup użytkowników. Możesz ustawić [priorytet](#change-enrollment-restriction-priority) dla różnych ograniczeń.

>[!NOTE]
>Ograniczenia rejestrowania nie są funkcjami zabezpieczeń. Urządzenia, na których złamano zabezpieczenia, mogą błędnie podawać swój charakter. Te ograniczenia stanowią optymalną barierę dla niezłośliwych użytkowników.

Konkretne ograniczenia rejestracji, które możesz utworzyć, obejmują poniższe:

- Maksymalna liczba zarejestrowanych urządzeń.
- Platformy urządzeń, które można zarejestrować:
  - Administrator urządzenia z systemem Android
  - Android Enterprise — profil służbowy
  - iOS
  - macOS
  - Windows
  - Windows Mobile
- Wersja systemu operacyjnego platformy dla administratora urządzeń systemu iOS, Android, profilu służbowego systemu Android Enterprise, systemu Windows i Windows Mobile. (Można używać wyłącznie wersji systemu Windows 10. Pozostaw pole puste, jeśli dozwolone jest użycie systemu Windows 8.1).
  - Minimalna wersja.
  - Maksymalna wersja.
- Ogranicz [urządzenia, które są własnością prywatną](device-enrollment.md#bring-your-own-device) (administrator urządzeń systemu iOS oraz Android, profil służbowy systemu Android Enterprise, tylko systemy macOS, Windows i Windows Mobile).

## <a name="default-restrictions"></a>Ograniczenia domyślne

Ograniczenia domyślne są automatycznie zapewniane w przypadku ograniczeń rejestracji dla typu urządzeń i liczby urządzeń. Możesz zmienić opcje domyślne. Domyślnie ograniczenia mają zastosowanie do wszystkich użytkowników i rejestracji bez użytkowników. Możesz przesłonić te ustawienia domyślne, tworząc nowe ograniczenia o wyższych priorytetach.

## <a name="create-a-device-type-restriction"></a>Tworzenie ograniczenia typu urządzenia

1. Zaloguj się do [centrum administracyjnego usługi Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) > **Urządzenia** > **Ograniczenia rejestracji** > **Utwórz ograniczenie** > **Ograniczenie typu urządzeń**.
2. Na stronie **Podstawowe** wypełnij pole **Nazwa** i opcjonalne pole **Opis**.
3. Wybierz przycisk **Dalej**, aby przejść do strony **Ustawienia platformy**.
4. W obszarze **Platforma** wybierz opcję **Zezwalaj** dla platform, dla których chcesz zezwolić na to ograniczenie.
    ![Zrzut ekranu wybierania ustawień platformy](./media/enrollment-restrictions-set/choose-platform-settings.png)
5. W obszarze **Wersje** wybierz minimalne i maksymalne wersje, które mają być obsługiwane przez dozwolone platformy. Ograniczenia wersji mają zastosowanie tylko do urządzeń zarejestrowanych w aplikacji Portal firmy.
     Obsługiwane formaty wersji obejmują:
    - Administrator urządzenia z systemem Android i profil służbowy systemu Android Enterprise obsługują wersję major.minor.rev.build.
    - System iOS obsługuje wersję major.minor.rev. Wersje systemu operacyjnego nie mają zastosowania do urządzeń firmy Apple rejestrowanych przy użyciu programu Device Enrollment Program, usługi Apple School Manager lub aplikacji Apple Configurator.
    - System Windows obsługuje tylko wersję major.minor.build.rev dla systemu Windows 10.
    
    > [!IMPORTANT]
    > Platformy Android Enterprise (profil służbowy) i Administrator urządzenia z systemem Android mają następujące zachowanie:
    > - Jeśli obie platformy są dozwolone dla tej samej grupy, użytkownicy zostaną zarejestrowani przy użyciu profilu służbowego, jeśli ich urządzenia go obsługują. W przeciwnym razie zostaną oni zarejestrowani jako administratorzy urządzeń. 
    > - Jeśli obie platformy są dozwolone dla grupy i zostały ulepszone dla określonych i nienakładających się wersji, użytkownicy otrzymają przepływ rejestracji zdefiniowany dla ich wersji systemu operacyjnego. 
    > - Jeśli obie platformy są dozwolone, ale są blokowane dla tych samych wersji, użytkownicy na urządzeniach z zablokowanymi wersjami zostaną przekierowani do przepływu rejestracji administratora urządzeń z systemem Android, a następnie zostanie im zablokowana możliwość rejestracji i pojawi się prośba o wylogowanie się. 
    >
    > Należy pamiętać, że ani rejestracja przy użyciu profilu służbowego, ani jako administrator urządzenia nie będą działały, jeśli nie zostaną spełnione odpowiednie wymagania wstępne rejestracji w systemie Android. 
    
   > [!Note]
   > System Windows 10 nie udostępnia numeru wersji podczas rejestracji, więc jeśli na przykład wprowadzisz kompilację 10.0.17134.174, a urządzenie korzysta z kompilacji 10.0.17134.100, urządzenie zostanie zablokowane podczas rejestracji.

6. W obszarze **Własność użytkownika** wybierz opcję **Zezwalaj** dla platform, na które chcesz zezwalać jako urządzenia będące własnością użytkowników.
7. Wybierz przycisk **Dalej**, aby przejść do strony **Przypisania**.
8. Wybierz opcję **Wybierz grupy do uwzględnienia**, a następnie użyj pola wyszukiwania, aby znaleźć grupy, które chcesz uwzględnić w tym ograniczeniu. Ograniczenie ma zastosowanie wyłącznie do grup, do których zostało przypisane. Jeśli nie przypiszesz ograniczenia do co najmniej jednej grupy, nie będzie mieć żadnego efektu. Następnie wybierz opcję **Wybierz**. 
    ![Zrzut ekranu wybierania ustawień platformy](./media/enrollment-restrictions-set/select-groups.png)
9. Wybierz pozycję **Dalej**, aby przejść do strony **Recenzja i tworzenie**.
10. Wybierz pozycję **Utwórz**, aby utworzyć ograniczenie.
11. Nowe ograniczenie jest tworzone z priorytetem tuż nad ograniczeniami domyślnymi. Możesz [zmienić priorytet](#change-enrollment-restriction-priority).


## <a name="create-a-device-limit-restriction"></a>Tworzenie ograniczenia limitu urządzeń

1. Zaloguj się do [centrum administracyjnego usługi Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) > **Urządzenia** > **Ograniczenia rejestracji** > **Utwórz ograniczenie** > **Ograniczenie limitu urządzeń**.
2. Na stronie **Podstawowe** wypełnij pole **Nazwa** i opcjonalne pole **Opis**.
3. Wybierz opcję **Dalej**, aby przejść do strony **Limit urządzeń**.
4. Dla opcji **Limit urządzeń** wybierz maksymalną liczbę urządzeń, którą może zarejestrować użytkownik.
    ![Zrzut ekranu wybierania limitu urządzeń](./media/enrollment-restrictions-set/choose-device-limit.png)
5. Wybierz przycisk **Dalej**, aby przejść do strony **Przypisania**.
6. Wybierz opcję **Wybierz grupy do uwzględnienia**, a następnie użyj pola wyszukiwania, aby znaleźć grupy, które chcesz uwzględnić w tym ograniczeniu. Ograniczenie ma zastosowanie wyłącznie do grup, do których zostało przypisane. Jeśli nie przypiszesz ograniczenia do co najmniej jednej grupy, nie będzie mieć żadnego efektu. Następnie wybierz opcję **Wybierz**. 
    ![Zrzut ekranu wybierania grup](./media/enrollment-restrictions-set/select-groups-device-limit.png)
7. Wybierz pozycję **Dalej**, aby przejść do strony **Recenzja i tworzenie**.
8. Wybierz pozycję **Utwórz**, aby utworzyć ograniczenie.
9. Nowe ograniczenie jest tworzone z priorytetem tuż nad ograniczeniami domyślnymi. Możesz [zmienić priorytet](#change-enrollment-restriction-priority).

Podczas rejestracji urządzeń BYOD zostanie wyświetlone powiadomienie dla użytkowników, gdy osiągną limit liczby zarejestrowanych urządzeń. Przykładowo w systemie iOS:

![Powiadomienie o limicie urządzeń w systemie iOS](./media/enrollment-restrictions-set/enrollment-restrictions-ios-set-limit-notification.png)

> [!IMPORTANT]
> Ograniczenia limitu urządzeń nie dotyczą następujących typów rejestracji w systemie Windows:
> - Rejestracje współzarządzane
> - Rejestracje obiektów zasad grupy
> - Rejestracje dołączane do usługi Azure Active Directory
> - Zbiorcze rejestracje dołączane do usługi Azure Active Directory
> - Rejestracje rozwiązania Autopilot
> - Rejestracje Menedżera rejestracji urządzeń
>
> Ograniczenia limitu urządzeń nie są wymuszane dla tych typów rejestracji, ponieważ są one traktowane jako scenariusze dotyczące urządzeń udostępnionych.
> Limity stałe dla tych typów rejestracji można ustawić [w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/device-management-azure-portal#configure-device-settings).


## <a name="change-enrollment-restrictions"></a>Zmiana ograniczeń rejestracji

Możesz zmienić ustawienia ograniczeń dotyczących rejestracji, wykonując poniższe czynności. Te ograniczenia nie wpływają na urządzenia, które zostały już zarejestrowane. Za pomocą tej funkcji nie można zablokować urządzeń zarejestrowanych przy użyciu [agenta usługi Intune na komputerze](../fundamentals/manage-windows-pcs-with-microsoft-intune.md).

1. Zaloguj się do [centrum administracyjnego usługi Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) > **Urządzenia** > **Ograniczenia rejestracji** > wybierz ograniczenie, które chcesz zmienić > **Właściwości**.
2. Wybierz opcję **Edytuj** obok ustawień, które chcesz zmienić.
3. Na stronie **Edycja** wprowadź odpowiednie zmiany i przejdź do strony **Przejrzyj i zapisz**, a następnie wybierz opcję **Zapisz**.


## <a name="blocking-personal-android-devices"></a>Blokowanie urządzeń osobistych z systemem Android
- Jeśli zablokujesz rejestrację urządzeń prywatnych administratora urządzeń z systemem Android, prywatne urządzenia z profilami służbowymi systemu Android Enterprise nadal będą mogły być rejestrowane.
- Domyślnie ustawienia urządzeń z profilami służbowymi systemu Android Enterprise są takie same jak ustawienia urządzeń administratora urządzeń z systemem Android. Po zmianie profilu służbowego systemu Android Enterprise lub ustawień administratora urządzeń z systemem Android nie jest to już możliwe.
- Jeśli zablokujesz rejestrację urządzeń osobistych z profilami służbowymi systemu Android Enterprise, jako profile służbowe systemu Android Enterprise będzie można rejestrować tylko firmowe urządzenia z systemem Android.

## <a name="blocking-personal-windows-devices"></a>Blokowanie urządzeń osobistych z systemem Windows
Jeśli blokujesz rejestrację urządzeń osobistych z systemem Windows, usługa Intune sprawdza, czy każde nowe żądanie rejestracji systemu Windows zostało autoryzowane jako rejestracja firmowa. Nieautoryzowane rejestracje będą blokowane.

Następujące metody kwalifikują się do autoryzacji jako rejestracja firmowa systemu Windows:
- Rejestrujący użytkownik korzysta z [konta menedżera rejestracji urządzeń]( device-enrollment-manager-enroll.md).
- Urządzenie jest rejestrowane za pomocą rozwiązania [Windows AutoPilot](enrollment-autopilot.md).
- Urządzenie zostało zarejestrowane w rozwiązaniu Windows Autopilot, ale nie jest to opcja „Tylko rejestracja w rozwiązaniu MDM” w oknie Ustawienia systemu Windows.
- Numer IMEI urządzenia znajduje się w polu **Rejestrowanie urządzenia** >  **[Identyfikatory urządzeń firmowych](corporate-identifiers-add.md)** . (Nieobsługiwany w systemie Windows Phone 8.1).
- Urządzenie jest rejestrowane za pomocą [pakietu aprowizacji zbiorczej](windows-bulk-enroll.md).
- Urządzenie jest rejestrowane za pomocą obiektu zasad grupy lub [funkcji automatycznego rejestrowania z programu SCCM dla współzarządzania](https://docs.microsoft.com/sccm/comanage/quickstart-paths#bkmk_path1).
 
Poniższe rejestracje zostały oznaczone jako firmowe przez usługę Intune. Ale ponieważ nie oferują one administratorowi usługi Intune możliwości kontroli poszczególnych urządzeń, zostaną zablokowane:
- [Automatyczne rejestrowanie w rozwiązaniu MDM](windows-enroll.md#enable-windows-10-automatic-enrollment) przez [przyłączenie do usługi Azure Active Directory podczas konfigurowania systemu Windows](https://docs.microsoft.com/azure/active-directory/device-management-azuread-joined-devices-frx)\*.
- [Automatyczne rejestrowanie w rozwiązaniu MDM](windows-enroll.md#enable-windows-10-automatic-enrollment) przez [przyłączenie do usługi Azure Active Directory z ustawień systemu Windows](https://docs.microsoft.com/azure/active-directory/user-help/user-help-register-device-on-network)*.
 
Następujące metody rejestracji urządzeń osobistych będą także blokowane:
- [Automatyczne rejestrowanie w rozwiązaniu MDM](windows-enroll.md#enable-windows-10-automatic-enrollment) za pomocą polecenia [Dodaj konto służbowe w oknie Ustawienia systemu Windows](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network)\*.
- Opcja [Tylko rejestracja w rozwiązaniu MDM]( https://docs.microsoft.com/windows/client-management/mdm/mdm-enrollment-of-windows-devices#connecting-personally-owned-devices-bring-your-own-device) w oknie Ustawienia systemu Windows.

\* Te urządzenia nie są blokowane w przypadku zarejestrowania w rozwiązaniu Autopilot.


## <a name="blocking-personal-ios-devices"></a>Blokowanie urządzeń osobistych z systemem iOS
Domyślnie usługa Intune klasyfikuje urządzenia z systemem iOS jako własność użytkownika. Aby można było sklasyfikować urządzenie z systemem iOS jako należące do firmy, musi ono spełniać jeden z następujących warunków:
- Musi zostać zarejestrowane przy użyciu numeru seryjnego lub numeru IMEI.
- Musi zostać zarejestrowane przy użyciu funkcji automatycznego rejestrowania urządzeń (znanej wcześniej jako program Device Enrollment Program)


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
