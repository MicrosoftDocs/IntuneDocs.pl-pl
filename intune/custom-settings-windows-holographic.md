---
title: Niestandardowe ustawienia urządzeń z systemem Windows Holographic for Business w usłudze Microsoft Intune na platformie Azure | Microsoft Docs
description: 'Utwórz profil niestandardowy w celu użycia ustawień identyfikatora URI OMA dla urządzeń z systemem Windows Holographic for Business w usłudze Microsoft Intune. Ustawienia dostawcy usług konfiguracji zasad dostępne do użycia to: AllowFastReconnect, AllowVPN, AllowUpdateService, UpdateServiceURL, RequireUpdatesApproval, ApprovedUpdates i ApplicationLaunchRestrictions.'
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 4/26/2018
ms.article: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7272e8e088ae2c2ecad1756233281c42a80a279b
ms.sourcegitcommit: 2061f7a442efc96c8afd5db764d11531563c7e39
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "32328082"
---
# <a name="custom-device-settings-for-devices-running-windows-holographic-for-business-in-intune"></a>Niestandardowe ustawienia urządzeń z systemem Windows Holographic for Business w usłudze Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

 Profil **niestandardowy** usługi Microsoft Intune dla systemu Windows Holographic for Business umożliwia wdrożenie ustawień OMA-URI (Open Mobile Alliance Uniform Resource Identifier), których można użyć do sterowania funkcjami na urządzeniach. System Windows Holographic for Business udostępnia wiele ustawień dostawców usługi konfiguracji (CSP). Aby zapoznać się z omówieniem dostawcy usługi konfiguracji, zobacz [Introduction to configuration service providers (CSPs) for IT pros](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers) (Wprowadzenie do dostawców usługi konfiguracji dla specjalistów IT). Aby uzyskać informacje o konkretnym dostawcy usługi konfiguracji obsługiwanym w systemie Windows Holographic, zobacz [CSPs supported in Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens) (Dostawcy usługi konfiguracji obsługiwani w systemie Windows Holographic).

Jeśli szukasz konkretnego ustawienia, pamiętaj, że [profil ograniczeń urządzenia z systemem Windows Holographic for Business](device-restrictions-windows-holographic.md) zawiera wiele wbudowanych ustawień i nie wymaga określenia wartości niestandardowych.

## <a name="create-the-custom-oma-uri-profile"></a>Tworzenie niestandardowego profilu OMA-URI

1. Aby rozpocząć pracę, postępuj zgodnie z instrukcjami w artykule [Configure custom device settings in Microsoft Intune (Konfigurowanie niestandardowych ustawień urządzeń w usłudze Microsoft Intune)](custom-settings-configure.md).
2. W obszarze **Tworzenie profilu** wybierz pozycję **Ustawienia**, aby dodać co najmniej jedno ustawienie OMA-URI.
3. W obszarze **Ustawienia niestandardowe OMA-URI** kliknij przycisk **Dodaj**, aby dodać nową wartość. Możesz również kliknąć przycisk **Eksportuj**, aby utworzyć listę wszystkich wartości skonfigurowanych w pliku wartości rozdzielanych przecinkami (.csv).
4. Dla każdego ustawienia OMA-URI, które chcesz dodać, wprowadź następujące informacje:
  - **Nazwa ustawienia**: wprowadź unikatową nazwę dla ustawienia OMA-URI, aby ułatwić jego identyfikację na liście ustawień.
  - **Opis ustawienia**: opcjonalnie wprowadź opis ustawienia.
  - **Typ danych**: Wybierz spośród opcji:
    - **Ciąg**
    - **Ciąg (XML)**
    - **Data i godzina**
    - **Liczba całkowita**
    - **Liczba zmiennoprzecinkowa**
    - **Wartość logiczna**
  - **OMA-URI (z uwzględnieniem wielkości liter)**: wprowadź identyfikator OMA-URI, dla którego chcesz podać ustawienie.
  - **Wartość** — wprowadź wartość, która będzie kojarzona z wprowadzonym identyfikatorem OMA-URI.
5. Gdy skończysz, w obszarze **Tworzenie profilu** kliknij pozycję **Utwórz**. Profil zostanie utworzony i wyświetlony na liście profilów.

## <a name="recommended-custom-settings"></a>Zalecane ustawienia niestandardowe

Następujące ustawienia są przydatne w przypadku urządzeń z systemem Windows Holographic for Business:

### <a name="allowfastreconnecthttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-authenticationauthentication-allowfastreconnect"></a>[AllowFastReconnect](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-allowfastreconnect)

> [!div class="mx-tableFixed"]
> |Identyfikator URI OMA|Typ danych|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Authentication/AllowFastReconnect|Integer<br/>0 — niedozwolone<br/>1 — dozwolone (ustawienie domyślne)|

### <a name="allowupdateservicehttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-updateupdate-allowupdateservice"></a>[AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)

> [!div class="mx-tableFixed"]
> |Identyfikator URI OMA|Typ danych|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Update/AllowUpdateService|Integer<br/>0 — usługa aktualizacji nie jest dozwolona <br/>1 — usługa aktualizacji jest dozwolona (ustawienie domyślne)|

### <a name="allowvpnhttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-settingssettings-allowvpn"></a>[AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)

> [!div class="mx-tableFixed"]
> |Identyfikator URI OMA|Typ danych|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Integer<br/>0 — niedozwolone<br/>1 — dozwolone (ustawienie domyślne)|

### <a name="requireupdatesapprovalhttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-updateupdate-requireupdateapproval"></a>[RequireUpdatesApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)

> [!div class="mx-tableFixed"]
> |Identyfikator URI OMA|Typ danych|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Update/RequireUpdateApproval|Integer<br/>0 — nieskonfigurowane. Urządzenie instaluje wszystkie odpowiednie aktualizacje.<br/>1 — urządzenie instaluje tylko aktualizacje, które zarówno można zastosować, jak i znajdują się na liście zatwierdzonych aktualizacji. Ustaw te zasady na wartość 1, jeśli dział IT chce kontrolować wdrożenia aktualizacji na urządzeniach, np. wtedy, gdy przed wdrożeniem jest wymagane testowanie.|

### <a name="scheduledinstalltimehttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-updateupdate-scheduledinstalltime"></a>[ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)

> [!div class="mx-tableFixed"]
> |Identyfikator URI OMA|Typ danych|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime|Liczba całkowita z przedziału 0–23, gdzie 0 = 0:00, a 23 = 23:00.<br/>Wartość domyślna to 3.|

### <a name="updateserviceurlhttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-updateupdate-updateserviceurl"></a>[UpdateServiceURL](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

> [!div class="mx-tableFixed"]
> |Identyfikator URI OMA|Typ danych|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Update/UpdateServiceUrl|String<br/>Adres URL — urządzenie sprawdza dostępność aktualizacji na serwerze WSUS pod określonym adresem URL.<br/>Nieskonfigurowane — urządzenie sprawdza dostępność aktualizacji w witrynie Microsoft Update.|

### <a name="approvedupdateshttpsdocsmicrosoftcomwindowsclient-managementmdmupdate-csp"></a>[ApprovedUpdates](https://docs.microsoft.com/windows/client-management/mdm/update-csp)

> [!div class="mx-tableFixed"]
> |Identyfikator URI OMA|Typ danych|
> |---|---|
> |./Vendor/MSFT/Update/ApprovedUpdates/*GUID*<br/><br/>**Ważne**<br/>Musisz przeczytać i zaakceptować zaktualizowane Umowy licencyjne użytkownika oprogramowania (EULA) w imieniu swoich użytkowników końcowych. Niewykonanie tej czynności jest naruszeniem zobowiązań prawnych lub umownych.|Węzeł zatwierdzania aktualizacji i akceptacji Umowy licencyjnej użytkownika oprogramowania (EULA) w imieniu użytkownika końcowego.<br/><br/>Aby uzyskać więcej informacji, zobacz [Update CSP](https://docs.microsoft.com/windows/client-management/mdm/update-csp) (Dostawca usługi konfiguracji Aktualizacja).|

### <a name="applicationlaunchrestrictionshttpsdocsmicrosoftcomwindowsclient-managementmdmapplocker-csp"></a>[ApplicationLaunchRestrictions](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp)

> [!div class="mx-tableFixed"]
> |Identyfikator URI OMA|Typ danych|
> |----|---|
> |./Vendor/MSFT/AppLocker/ApplicationLaunchRestrictions/*Grouping*/*ApplicationType*/Policy<br/><br/>**Ważne**<br/>W artykule dostawcy usług kryptograficznych funkcji AppLocker są używane przykłady XML. Aby skonfigurować ustawienia przy użyciu profilów niestandardowych w usłudze Intune, należy użyć zwykłego kodu XML.|String<br/>Aby uzyskać więcej informacji, zobacz [AppLocker CSP](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp) (Dostawca usługi konfiguracji AppLocker).|

### <a name="deletionpolicyhttpsdocsmicrosoftcomwindowsclient-managementmdmaccountmanagement-csp"></a>[DeletionPolicy](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp)

> [!div class="mx-tableFixed"]
> |Identyfikator URI OMA|Typ danych|
> |----|---|
> |./Vendor/MSFT/AccountManagement/UserProfileManagement/DeletionPolicy|Integer<br/>0 — usuwanie natychmiast po powrocie urządzenia do stanu bez aktywnych użytkowników<br/>1 — usuwanie po osiągnięciu progu pojemności magazynu (ustawienie domyślne)<br/>2 — usuwanie zarówno po osiągnięciu progu pojemności magazynu, jak i po osiągnięciu progu nieaktywności profilu|

### <a name="enableprofilemanagerhttpsdocsmicrosoftcomwindowsclient-managementmdmaccountmanagement-csp"></a>[EnableProfileManager](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp)

> [!div class="mx-tableFixed"]
> |Identyfikator URI OMA|Typ danych|
> |----|---|
> |./Vendor/MSFT/AccountManagement/UserProfileManagement/EnableProfileManager|Boolean<br/>True — włączone<br/>False — wyłączone (ustawienie domyślne)|

### <a name="profileinactivitythresholdhttpsdocsmicrosoftcomwindowsclient-managementmdmaccountmanagement-csp"></a>[ProfileInactivityThreshold](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp)

> [!div class="mx-tableFixed"]
> |Identyfikator URI OMA|Typ danych|
> |----|---|
> |./Vendor/MSFT/AccountManagement/UserProfileManagement/ProfileInactivityThreshold|Integer<br/>Wartość domyślna to 30.|


### <a name="storagecapacitystartdeletionhttpsdocsmicrosoftcomwindowsclient-managementmdmaccountmanagement-csp"></a>[StorageCapacityStartDeletion](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp)

> [!div class="mx-tableFixed"]
> |Identyfikator URI OMA|Typ danych|
> |----|---|
> |./Vendor/MSFT/AccountManagement/UserProfileManagement/StorageCapacityStartDeletion|Integer<br/>Wartość domyślna to 25.|

### <a name="storagecapacitystopdeletionhttpsdocsmicrosoftcomwindowsclient-managementmdmaccountmanagement-csp"></a>[StorageCapacityStopDeletion](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp)

> [!div class="mx-tableFixed"]
> |Identyfikator URI OMA|Typ danych|
> |----|---|
> |./Vendor/MSFT/AccountManagement/UserProfileManagement/StorageCapacityStopDeletion|Integer<br/>Wartość domyślna to 50.|

## <a name="find-the-policies-you-can-configure"></a>Wyszukiwanie zasad, które można skonfigurować

W tabeli [CSPs supported in Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens) (Dostawcy usługi konfiguracji obsługiwani w systemie Windows Holographic) znajduje się pełna lista wszystkich dostawców usługi konfiguracji (CSP) obsługiwanych w systemie Windows Holographic. Nie wszystkie ustawienia są zgodne ze wszystkimi wersjami systemu Windows Holographic. Tabela w artykule poświęconym systemowi Windows zawiera informacje o wersjach obsługiwanych w przypadku poszczególnych dostawców usług konfiguracji.

Ponadto usługa Intune nie obsługuje wszystkich ustawień wymienionych w artykule. Aby dowiedzieć się, czy usługa Intune obsługuje dane ustawienie, otwórz artykuł dotyczący tego ustawienia. Na stronie każdego ustawienia znajdują się informacje dotyczące obsługiwanych operacji. Aby ustawienie mogło być używane z usługą Intune, musi obsługiwać operacje **Dodaj** lub **Zastąp**.
