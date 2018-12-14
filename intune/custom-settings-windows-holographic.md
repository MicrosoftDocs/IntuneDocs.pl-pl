---
title: Ustawienia niestandardowe — urządzenia z systemem Windows Holographic for Business — usługa Microsoft Intune
description: 'Dodaj lub utwórz profil niestandardowy w celu użycia ustawień identyfikatora URI OMA dla urządzeń z systemem Windows Holographic for Business w usłudze Microsoft Intune, w tym dla urządzenia Microsoft Hololens. Ustawienia dostawcy usług konfiguracji zasad dostępne do użycia to: AllowFastReconnect, AllowVPN, AllowUpdateService, UpdateServiceURL, RequireUpdatesApproval, ApprovedUpdates i ApplicationLaunchRestrictions.'
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/06/2018
ms.article: article
ms.prod: ''
ms.service: microsoft-intune
ms.topic: article
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: 2c4e6041f00ad55b18f8b20996da8002f5ce0247
ms.sourcegitcommit: fff179f59bd542677cbd4bf3bacc24bb880e2cb6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/07/2018
ms.locfileid: "53032201"
---
# <a name="use-custom-settings-for-windows-holographic-for-business-devices-in-intune"></a>Używanie ustawień niestandardowych dla urządzeń z systemem Windows Holographic for Business w usłudze Intune

Za pomocą usługi Microsoft Intune można dodawać lub tworzyć ustawienia niestandardowe dla urządzeń z systemem Windows Holographic for Business przy użyciu „profili niestandardowych”. Profile niestandardowe to funkcja w usłudze Intune. Służą one do dodawania ustawień i funkcji urządzeń, które nie są wbudowane w usłudze Intune.

Profile niestandardowe systemu Windows Holographic for Business używają ustawień jednolitego identyfikatora zasobów Open Mobile Alliance (OMA-URI, Open Mobile Alliance Uniform Resource Identifier) w celu skonfigurowania różnych funkcji. Te ustawienia są zwykle używane przez producentów urządzeń przenośnych w celu kontrolowania funkcji na urządzeniu.

System Windows Holographic for Business udostępnia wiele ustawień dostawców usługi konfiguracji (CSP). Aby zapoznać się z omówieniem dostawcy usługi konfiguracji, zobacz [Introduction to configuration service providers (CSPs) for IT pros](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers) (Wprowadzenie do dostawców usługi konfiguracji dla specjalistów IT). Aby uzyskać informacje o konkretnym dostawcy usługi konfiguracji obsługiwanym w systemie Windows Holographic, zobacz [CSPs supported in Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens) (Dostawcy usługi konfiguracji obsługiwani w systemie Windows Holographic).

Jeśli szukasz określonego ustawienia, pamiętaj, że [profil ograniczeń urządzenia z systemem Windows Holographic for Business](device-restrictions-windows-holographic.md) zawiera wiele wbudowanych ustawień. Dzięki temu być może nie trzeba będzie wprowadzać wartości niestandardowych.

W tym artykule pokazano, jak utworzyć profil niestandardowy dla urządzeń z systemem Windows Holographic for Business. Zawiera on także listę zalecanych ustawień identyfikatora OMA-URI.

## <a name="create-the-profile"></a>Tworzenie profilu

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
2. Wybierz pozycję **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Podaj następujące ustawienia:

    - **Nazwa**: Wprowadź nazwę profilu, na przykład `hololens custom profile`.
    - **Opis**: Wprowadź opis profilu.
    - **Platforma**: Wybierz **System Windows 10 lub nowszy**.
    - **Typ profilu**: Wybierz **Niestandardowy**.

4. W obszarze **Niestandardowe ustawienia OMA-URI** wybierz pozycję **Dodaj**. Podaj następujące ustawienia:

    - **Nazwa**: Wprowadź unikatową nazwę dla ustawienia OMA-URI, aby ułatwić jego identyfikację na liście ustawień.
    - **Opis**: Wprowadź opis ułatwiający identyfikację ustawienia oraz zawierający inne ważne szczegóły.
    - **OMA-URI** (rozróżniana jest wielkość liter): Wprowadź identyfikator OMA-URI, którego chcesz używać jako ustawienia.
    - **Typ danych**: Wybierz typ danych używany w przypadku tego ustawienia identyfikatora OMA-URI. Dostępne opcje:

        - String
        - Ciąg (plik XML)
        - Data i godzina
        - Integer
        - Liczba zmiennoprzecinkowa
        - Boolean
        - Base64 (plik)

    - **Wartość**: Wprowadź wartość danych, którą chcesz skojarzyć z wprowadzonym identyfikatorem OMA-URI. Wartość zależy od wybranego typu danych. Jeśli na przykład wybrano opcję **Data i godzina**, wybierz wartość za pomocą selektora daty.

    Po dodaniu ustawień możesz wybrać pozycję **Eksportuj**. Wybranie pozycji **Eksportuj** spowoduje utworzenie listy wszystkich dodanych wartości w pliku wartości rozdzielanych przecinkami (CSV).

5. Wybierz przycisk **OK**, aby zapisać zmiany. W razie potrzeby kontynuuj dodawanie ustawień.
6. Po zakończeniu wybierz pozycję **OK** > **Utwórz**, aby utworzyć profil usługi Intune. Po utworzeniu profil będzie widoczny na liście **Konfiguracja urządzenia — profile**.

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

W tabeli [CSPs supported in Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens) (Dostawcy usługi konfiguracji obsługiwani w systemie Windows Holographic) znajduje się pełna lista wszystkich dostawców usługi konfiguracji (CSP) obsługiwanych w systemie Windows Holographic. Nie wszystkie ustawienia są zgodne ze wszystkimi wersjami systemu Windows Holographic. Tabela [CSPs supported in Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens) (Dostawcy usługi konfiguracji obsługiwani w systemie Windows Holographic) zawiera listę obsługiwanych wersji dla każdego dostawcy usług konfiguracji.

Ponadto usługa Intune nie obsługuje wszystkich ustawień wymienionych w tabeli [CSPs supported in Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens) (Dostawcy usługi konfiguracji obsługiwani w systemie Windows Holographic). Aby dowiedzieć się, czy usługa Intune obsługuje dane ustawienie, otwórz artykuł dotyczący tego ustawienia. Na stronie każdego ustawienia znajdują się informacje dotyczące obsługiwanych operacji. Aby ustawienie mogło być używane z usługą Intune, musi obsługiwać operacje **Dodaj** lub **Zastąp**.

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje jeszcze żadnych czynności. Teraz należy [przypisać profil](device-profile-assign.md).

Zobacz, jak utworzyć profil niestandardowy na [urządzeniach z systemem Windows 10](custom-settings-windows-10.md).