---
title: Aktualizowanie usługi Office 365 przy użyciu szablonów administracyjnych w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Użyj szablonów administracyjnych w usłudze Microsoft Intune, aby zaktualizować aplikacje usługi Office 365 do najnowszej wersji, a także wybrać częstotliwość sprawdzania aktualizacji przez pakiet Office. Zobacz klucze rejestru urządzenia aktualizowane po zastosowaniu zasad usługi Intune do aktualizacji pakietu Office.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/17/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cf872387d6e6f4f91af9f074f54695b081b79119
ms.sourcegitcommit: 23e9c48348a6eba494d072a2665b7481e5b5c84e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2019
ms.locfileid: "74549112"
---
# <a name="use-update-channel-and-target-version-settings-to-update-office-365-with-microsoft-intune-administrative-templates"></a>Używanie ustawień kanału aktualizacji i wersji docelowej do aktualizowania usługi Office 365 za pomocą szablonów administracyjnych usługi Microsoft Intune

W usłudze Intune można używać [szablonów systemu Windows 10 do konfigurowania ustawień zasad grupy](administrative-templates-windows.md). W tym artykule opisano sposób aktualizowania usługi Office 365 przy użyciu szablonu administracyjnego w usłudze Intune. Zawiera on również wskazówki dotyczące potwierdzania, że zasady zostały zastosowane pomyślnie. Te informacje ułatwiają również rozwiązywanie problemów.

W tym scenariuszu utworzysz w usłudze Intune szablon administracyjny, który aktualizuje usługę Office 365 na urządzeniach.

Aby uzyskać więcej informacji na temat szablonów administracyjnych, zobacz [Konfigurowanie ustawień zasad grupy przy użyciu szablonów systemu Windows 10](administrative-templates-windows.md).

Dotyczy:

- Windows 10 lub nowszym
- Office 365

## <a name="prerequisites"></a>Wymagania wstępne

Upewnij się, że [automatyczne aktualizacje usługi Office 365 ProPlus zostały włączone](https://docs.microsoft.com/deployoffice/configure-update-settings-for-office-365-proplus) dla aplikacji pakietu Office. Można to zrobić za pomocą zasad grupy lub szablonu ADMX usługi Intune w pakiecie Office 2016:

![Definiowanie ustawienia Włącz aktualizacje automatyczne dla pakietu Office w szablonie administracyjnym usługi Intune](./media/administrative-templates-update-office/admx-enable-automatic-updates.png)

## <a name="set-the-update-channel-in-the-intune-administrative-template"></a>Ustawianie kanału aktualizacji w szablonie administracyjnym usługi Intune

1. W [szablonie administracyjnym usługi Intune](administrative-templates-windows.md#create-a-template) przejdź do ustawienia **Kanał aktualizacji**, a następnie wprowadź żądany kanał. Na przykład wybierz `Semi-Annual Channel`:

    ![Definiowanie ustawienia Kanał aktualizacji dla pakietu Office w szablonie administracyjnym usługi Intune](./media/administrative-templates-update-office/admx-enable-update-channel-setting.png)

    > [!NOTE]
    > Zaleca się aktualizowanie z większą częstotliwością. Wartość „Co pół roku” jest używana tylko jako przykład.

2. Pamiętaj o [przypisaniu](device-profile-assign.md) zasad do urządzeń z systemem Windows 10. Aby przetestować zasady wcześniej, możesz je również zsynchronizować:

    - [Synchronizowanie zasad w usłudze Intune](../remote-actions/device-sync.md)
    - [Ręczne synchronizowanie zasad na urządzeniu](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows#sync-from-settings-app)

## <a name="check-the-intune-registry-keys"></a>Sprawdzanie kluczy rejestru usługi Intune

Po przypisaniu zasad i zsynchronizowaniu urządzenia można potwierdzić, że zasady zostały zastosowane:

1. Na urządzeniu otwórz aplikację **Edytor rejestru**.
2. Przejdź do ścieżki zasad usługi Intune: `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\PolicyManager\Providers\<Provider ID>\default\Device\office16~Policy~L_MicrosoftOfficemachine~L_Updates`.

    > [!TIP]
    > Element `<Provider ID>` w kluczu rejestru ulega zmianie. Aby znaleźć identyfikator dostawcy dla urządzenia, otwórz aplikację **Edytor rejestru** i przejdź do elementu `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\PolicyManager\AdmxInstalled`. Zostanie wyświetlony identyfikator dostawcy.

    Po zastosowaniu zasad będą widoczne następujące klucze rejestru:

    - `L_UpdateBranch`
    - `L_UpdateTargetVersion`

    W poniższym przykładzie zobaczysz, że element `L_UpdateBranch` ma wartość podobną do `<enabled /><data id="L_UpdateBranchID" value="Deferred" />`. Ta wartość oznacza, że został on ustawiony na Półroczny kanał:

    ![Przykład klucza rejestru L_Updatebranch w szablonie administracyjnym](./media/administrative-templates-update-office/admx-update-branch-registry-key.png)

    > [!TIP]
    > Temat [Zarządzanie usługą Office 365 ProPlus w programie Configuration Manager](https://docs.microsoft.com/sccm/sum/deploy-use/manage-office-365-proplus-updates#change-the-update-channel-after-you-enable-office-365-clients-to-receive-updates-from-configuration-manager) zawiera listę wartości i opis ich znaczenia. Wartości rejestru są zależne od wybranego kanału dystrybucji:
    >
    >- Miesięczny kanał                — value="Current"
    >- Miesięczny kanał (kierowany)                — value="Current"
    >- Półroczny kanał                — value="Current"
    >- Półroczny kanał (kierowany) — alue="FirstReleaseDeferred"
    >- Tester — szybkie aktualizacje                   — value="InsiderFast"

Na tym etapie zasady usługi Intune zostały pomyślnie zastosowane do urządzenia.

## <a name="check-the-office-registry-keys"></a>Sprawdzanie kluczy rejestru pakietu Office

1. Na urządzeniu otwórz aplikację **Edytor rejestru**.
2. Przejdź do ścieżki zasad pakietu Office: `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\ClickToRun\Configuration`.

    Zobaczysz następujące klucze rejestru:

    - `UpdateChannel`: klucz dynamiczny, który zmienia się w zależności od skonfigurowanych ustawień.
    - `CDNBaseUrl`: ustawiany podczas instalacji usługi Office 365 na urządzeniu.

3. Przyjrzyj się wartości `UpdateChannel`. Wartość informuje o tym, jak często pakiet Office jest aktualizowany. Temat [Zarządzanie usługą Office 365 ProPlus w programie Configuration Manager](https://docs.microsoft.com/sccm/sum/deploy-use/manage-office-365-proplus-updates#change-the-update-channel-after-you-enable-office-365-clients-to-receive-updates-from-configuration-manager) zawiera listę wartości i opis ich ustawień.

    Korzystając z następującego przykładu, zobaczysz, że element `UpdateChannel` został ustawiony na `http://officecdn.microsoft.com/pr/492350f6-3a01-4f97-b9c0-c7c6ddf67d60`, czyli kanał **miesięczny**:

    ![Przykład klucza rejestru UpdateChannel pakietu Office w szablonie administracyjnym](./media/administrative-templates-update-office/admx-update-channel-office-registry-key.png)

    Ten przykład wskazuje, że zasady nie zostały jeszcze zastosowane, ponieważ kanał jest nadal ustawiony na **miesięczny**, a nie **półroczny**.

Ten klucz rejestru jest aktualizowany w przypadku uruchomienia składnika **Harmonogram zadań** > **Automatyczne aktualizacje pakietu Office 2.0** lub gdy użytkownik zaloguje się do urządzenia. Aby potwierdzić, otwórz zadanie **Automatyczne aktualizacje pakietu Office 2.0** > **Wyzwalacze**. W zależności od wyzwalaczy może upłynąć co najmniej jeden dzień, zanim klucz rejestru `UpdateChannel`zostanie zaktualizowany.

## <a name="force-office-automatic-updates-to-run"></a>Wymuszanie uruchamiania automatycznych aktualizacji pakietu Office

Aby przetestować zasady, można wymusić ustawienia zasad na urządzeniu. Wykonanie poniższych kroków powoduje zaktualizowanie rejestru. Zawsze podczas aktualizowania rejestru należy zachować ostrożność.

1. Wyczyść klucz rejestru:

    1. Przejdź do witryny `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\ClickToRun\Updates`.
    2. Wybierz dwukrotnie klucz `UpdateDetectionLastRunTime`, usuń dane wartości > przycisk **OK**.

2. Uruchom zadanie Automatyczne aktualizacje pakietu Office:

    1. Otwórz aplikację **Harmonogram zadań** na urządzeniu.
    2. Rozwiń węzeł **Biblioteka Harmonogramu zadań** > **Microsoft** > **Office**.
    3. Wybierz pozycję **Automatyczne aktualizacje pakietu Office 2.0** > **Uruchom**:

        ![Otwieranie aplikacji Harmonogram zadań i uruchamianie składnika Automatyczne aktualizacje pakietu Office](./media/administrative-templates-update-office/admx-task-scheduler-office-automatic-updates.png)

        Poczekaj na zakończenie zadania, co może potrwać kilka minut.

3. W aplikacji **Edytor rejestru** przejdź do klucza `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\ClickToRun\Configuration`. Sprawdź wartość `UpdateChannel`.

    Powinna ona zostać zaktualizowana przy użyciu wartości ustawionej w ramach zasad. W naszym przykładzie wartość powinna zostać ustawiona na `http://officecdn.microsoft.com/pr/7ffbc6bf-bc32-4f92-8982-f9dd17fd3114`.

Na tym etapie kanał aktualizacji pakietu Office został pomyślnie zmieniony na urządzeniu. Możesz otworzyć aplikację usługi Office 365 dla użytkownika, który odbiera tę aktualizację, aby sprawdzić stan.

## <a name="force-the-office-synchronization-to-update-account-information"></a>Wymuszanie synchronizacji pakietu Office w celu zaktualizowania informacji o kliencie  

Aby dowiedzieć się więcej, możesz wymusić aktualizację pakietu Office do najnowszej wersji. Poniższe kroki należy wykonać tylko jako potwierdzenie lub jeśli urządzenia muszą szybko pobrać aktualizację do najnowszej wersji z tego kanału. W przeciwnym razie pozwól, aby pakiet Office wykonywał swoje zadania i aktualizował je automatycznie.

### <a name="step-1-force-the-office-version-to-update"></a>Krok 1. Wymuszanie aktualizacji wersji pakietu Office

1. Potwierdź, że wersja pakietu Office obsługuje wybierany kanał aktualizacji. Temat [Update history for Office 365 ProPlus](https://docs.microsoft.com/officeupdates/update-history-office365-proplus-by-date) (Historia aktualizacji dla usługi Office 365 ProPlus) zawiera numery kompilacji, które obsługują różne kanały aktualizacji.

2. W [szablonie administracyjnym usługi Intune](administrative-templates-windows.md#create-a-template) przejdź do ustawienia **Wersja docelowa**, a następnie wprowadź żądaną wersję.

    Ustawienie **Wersja docelowa** wygląda podobnie do następującego ustawienia:

    ![Definiowanie ustawienia Wersja docelowa dla pakietu Office w szablonie administracyjnym usługi Intune](./media/administrative-templates-update-office/admx-enable-target-version-setting.png)

> [!IMPORTANT]
>
> - Pamiętaj o przypisaniu zasad.
> - Jeśli zmienisz istniejące zasady, zmiany wpłyną na wszystkich przypisanych użytkowników.
> - Jeśli testujesz tę funkcję, zaleca się utworzenie zasad testowych i przypisanie zasad do testowej grupy użytkowników.

### <a name="step-2-check-the-office-version"></a>Krok 2: Sprawdzanie wersji pakietu Office

Rozważ wykonanie tych kroków w celu przetestowania zasad przed wdrożeniem zasad dla wszystkich użytkowników.

1. W aplikacji **Edytor rejestru** przejdź do klucza `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\PolicyManager\Providers\<Provider ID>\default\Device\office16~Policy~L_MicrosoftOfficemachine~L_Updates`

2. Przyjrzyj się wartości `L_UpdateTargetVersion`. Gdy zasady zostaną zastosowane, wartość zostanie ustawiona na wersję wprowadzoną przez Ciebie, na przykład `<enabled /><data id="L_UpdateTargetVersionID" value="16.0.10730.20344" />`.

    Na tym etapie zasady usługi Intune zostały pomyślnie zastosowane do urządzenia.

3. Następnie możesz wymusić aktualizację pakietu Office. Otwórz aplikację pakietu Office, na przykład program Excel. Wybierz opcję Zaktualizuj teraz (prawdopodobnie w menu **Konto**).

    Aktualizacja trwa kilka minut. Możesz potwierdzić, że pakiet Office próbuje pobrać wprowadzaną wersję:

      1. Na urządzeniu przejdź do folderu `C:\Program Files (x86)\Microsoft Office\Updates\Detection\Version`.
      2. Otwórz plik `VersionDescriptor.xml` i przejdź do sekcji `<Version>`. Dostępna wersja powinna być taka sama jak wersja wprowadzona w zasadach usługi Intune, na przykład:

          ![Sprawdzanie sekcji wersji w pliku XML deskryptora wersji w pakiecie Office](./media/administrative-templates-update-office/office-version-descriptor-xml-example.png)

4. Po zainstalowaniu aktualizacji aplikacja pakietu Office powinna wyświetlać nową wersję (na przykład w menu **Konta**).

## <a name="next-steps"></a>Następne kroki

[Aktualizowanie wartości kanału dla klientów układu Office 365](https://docs.microsoft.com/sccm/sum/deploy-use/manage-office-365-proplus-updates#change-the-update-channel-after-you-enable-office-365-clients-to-receive-updates-from-configuration-manager)

[Overview of the Office cloud policy service for Office 365 ProPlus](https://docs.microsoft.com/deployoffice/overview-office-cloud-policy-service) (Omówienie usługi zasad w chmurze pakietu Office dla usługi Office 365 ProPlus)

[Korzystanie z szablonów systemu Windows 10 umożliwiających konfigurowanie ustawień zasad grupy (szablonów ADMX) w usłudze Microsoft Intune](administrative-templates-windows.md)
