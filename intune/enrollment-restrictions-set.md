---
title: Ustawianie ograniczeń rejestracji w usłudze Microsoft Intune
titlesuffix: ''
description: Ograniczanie rejestrowania według platformy i ustawianie limitu rejestracji urządzeń w usłudze Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 97543ec74225ef86208000bccb2a8ad7852dd9c1
ms.sourcegitcommit: b96568a77d3cb6f602e7577446996fe7dde169bd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2018
ms.locfileid: "51610060"
---
# <a name="set-enrollment-restrictions"></a>Ustawianie ograniczeń rejestracji

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Jako administrator usługi Intune możesz utworzyć ograniczenia rejestracji i zarządzać nimi. Ograniczenia te definiują liczbę i typy urządzeń, które mogą zarejestrować się do zarządzania przy użyciu usługi Intune. Możesz utworzyć wiele ograniczeń i zastosować je do różnych grup użytkowników. Możesz ustawić [priorytet](#change-enrollment-restriction-priority) dla różnych ograniczeń.

>[!NOTE]
>Ograniczenia rejestrowania nie są funkcjami zabezpieczeń. Urządzenia, na których złamano zabezpieczenia, mogą błędnie podawać swój charakter. Te ograniczenia stanowią optymalną barierę dla niezłośliwych użytkowników.

Konkretne ograniczenia rejestracji, które możesz utworzyć, obejmują poniższe:

- Maksymalna liczba zarejestrowanych urządzeń.
- Platformy urządzeń, które można zarejestrować:
  - Android
  - Profil służbowy systemu Android
  - iOS
  - macOS
  - Windows
- Wersja systemu operacyjnego platformy dla systemów iOS, Android i Windows oraz profilu służbowego systemu Android. (Można używać wyłącznie wersji systemu Windows 10. Pozostaw pole puste, jeśli dozwolone jest użycie systemu Windows 8.1).
  - Minimalna wersja.
  - Maksymalna wersja.
- Ogranicz urządzenia prywatne (tylko z systemami iOS, Android, macOS, Windows, profilem służbowym systemu Android).

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

Możesz zmienić ustawienia ograniczeń dotyczących typu urządzenia, wykonując poniższe czynności. Te ograniczenia nie wpływają na urządzenia, które zostały już zarejestrowane. Za pomocą tej funkcji nie można zablokować urządzeń zarejestrowanych przy użyciu [agenta usługi Intune na komputerze](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune).

1. Zaloguj się do witryny Azure Portal.
2. Wybierz opcję **Więcej usług**, wyszukaj usługę **Intune**, a następnie wybierz usługę **Intune**.
3. Wybierz pozycję **Rejestrowanie urządzenia** > **Ograniczenia rejestracji**.
4. W obszarze **Ograniczenia typu urządzenia** > wybierz ograniczenie, które chcesz ustawić > **Właściwości** > **Wybierz platformy**. Wybierz pozycję **Zezwalaj** lub **Blokuj** dla każdej platformy na liście.
    ![Zrzut ekranu zezwalania na platformę lub jej blokowania](media/enrollment-restrictions-set/platform-allow-block.png)
5. Wybierz przycisk **OK**.
6. Wybierz pozycję **Konfiguruj platformy**.
    ![Zrzut ekranu konfigurowania platform](media/enrollment-restrictions-set/configure-platforms.png)
7. Wybierz minimalną i maksymalną **wersję** dla wymienionych platform. Obsługiwane formaty wersji obejmują:
    - Profil służbowy systemu Android obsługuje wersję major.minor.rev.build.
    - System iOS obsługuje wersję major.minor.rev. Wersje systemu operacyjnego nie mają zastosowania do urządzeń firmy Apple rejestrowanych przy użyciu programu Device Enrollment Program, usługi Apple School Manager lub aplikacji Apple Configurator.
    - System Windows obsługuje tylko major.minor.rev.build dla systemu Windows 10.
8. Wybierz pozycję **Zezwalaj** lub **Blokuj** dla **urządzeń osobistych** w przypadku każdej platformy na liście.
9. Wybierz przycisk **OK**.

### <a name="blocking-personal-android-devices"></a>Blokowanie urządzeń osobistych z systemem Android
- Jeśli zablokujesz rejestrację prywatnych urządzeń z systemem Android, urządzenia z profilami służbowymi systemu Android nadal będą mogły być rejestrowane.
- Domyślnie ustawienia urządzeń z profilami służbowymi systemu Android są takie same jak ustawienia urządzeń z systemem Android. Nie będzie tak w przypadku zmiany ustawień profilu służbowego systemu Android.
- Jeśli zablokujesz rejestrację urządzeń osobistych z profilami służbowymi systemu Android, jako profile służbowe systemu Android będzie można rejestrować tylko firmowe urządzenia z systemem Android.

### <a name="blocking-personal-windows-devices"></a>Blokowanie urządzeń osobistych z systemem Windows
Jeśli blokujesz rejestrację urządzeń osobistych z systemem Windows, usługa Intune sprawdza, czy każde nowe żądanie rejestracji systemu Windows zostało autoryzowane jako rejestracja firmowa. Nieautoryzowane rejestracje będą blokowane.

Następujące metody kwalifikują się do autoryzacji jako rejestracja firmowa systemu Windows:
 - Rejestrujący użytkownik korzysta z [konta menedżera rejestracji urządzeń]( device-enrollment-manager-enroll.md).
- Urządzenie jest rejestrowane za pomocą rozwiązania [Windows AutoPilot](enrollment-autopilot.md).
- Urządzenie jest zarejestrowane w rozwiązaniu Windows Autopilot, ale nie jest to opcja „Tylko rejestracja w rozwiązaniu MDM” w oknie Ustawienia systemu Windows.
- Numer IMEI urządzenia znajduje się w polu **Rejestrowanie urządzenia** > **[Identyfikatory urządzeń firmowych](corporate-identifiers-add.md)**. (Nieobsługiwany w systemie Windows Phone 8.1).
- Urządzenie jest rejestrowane za pomocą [pakietu aprowizacji zbiorczej](windows-bulk-enroll.md).
- Urządzenie jest rejestrowane za pomocą [funkcji automatycznego rejestrowania z programu SCCM dla współzarządzania](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview#how-to-configure-co-management.md).
 
Następujące rejestracje są oznaczone jako firmowe przez usługę Intune, ale ponieważ nie umożliwiają administratorowi usługi Intune kontroli na poziomie urządzenia, będą zablokowane:
 - [Automatyczne rejestrowanie w rozwiązaniu MDM](windows-enroll.md#enable-windows-10-automatic-enrollment) przez [przyłączenie do usługi Azure Active Directory podczas konfigurowania systemu Windows](https://docs.microsoft.com/azure/active-directory/device-management-azuread-joined-devices-frx)\*.
- [Automatyczne rejestrowanie w rozwiązaniu MDM](windows-enroll.md#enable-windows-10-automatic-enrollment) przez [przyłączenie do usługi Azure Active Directory z ustawień systemu Windows](https://docs.microsoft.com/azure/active-directory/user-help/user-help-register-device-on-network)*.
 
Następujące metody rejestracji urządzeń osobistych będą także blokowane:
- [Automatyczne rejestrowanie w rozwiązaniu MDM](windows-enroll.md#enable-windows-10-automatic-enrollment) za pomocą polecenia [Dodaj konto służbowe w oknie Ustawienia systemu Windows](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network)\*.
- Opcja [Tylko rejestracja w rozwiązaniu MDM]( https://docs.microsoft.com/windows/client-management/mdm/mdm-enrollment-of-windows-devices#connecting-personally-owned-devices-bring-your-own-device) w oknie Ustawienia systemu Windows.

\* Te urządzenia nie są blokowane w przypadku zarejestrowania w rozwiązaniu Autopilot.

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
