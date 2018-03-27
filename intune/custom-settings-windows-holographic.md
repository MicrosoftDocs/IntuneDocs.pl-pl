---
title: Ustawienia niestandardowe urządzeń z systemem Windows Holographic for Business w usłudze Microsoft Intune
titlesuffix: ''
description: Informacje dotyczące ustawień, których można używać w niestandardowym profilu systemu Holographic for Business.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.article: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d5cdba24c10b90756d9a2b9f08fd7d4dcd727303
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/22/2018
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-windows-holographic-for-business"></a>Niestandardowe ustawienia urządzenia w usłudze Microsoft Intune dla urządzeń z systemem Windows Holographic for Business

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

 Profil **niestandardowy** usługi Microsoft Intune dla systemu Windows Holographic for Business umożliwia wdrożenie ustawień OMA-URI (Open Mobile Alliance Uniform Resource Identifier), których można użyć do sterowania funkcjami na urządzeniach. System Windows Holographic for Business udostępnia wiele ustawień dostawców usługi konfiguracji (CSP). Aby zapoznać się z omówieniem dostawcy usługi konfiguracji, zobacz [Introduction to configuration service providers (CSPs) for IT pros](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers) (Wprowadzenie do dostawców usługi konfiguracji dla specjalistów IT). Aby uzyskać informacje o konkretnym dostawcy usługi konfiguracji obsługiwanym w systemie Windows Holographic, zobacz [CSPs supported in Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens) (Dostawcy usługi konfiguracji obsługiwani w systemie Windows Holographic).

Jeśli szukasz konkretnego ustawienia, pamiętaj, że [profil ograniczeń urządzenia z systemem Windows Holographic for Business](device-restrictions-windows-holographic.md) zawiera wiele wbudowanych ustawień i nie wymaga określenia wartości niestandardowych.

1. Aby rozpocząć pracę, postępuj zgodnie z instrukcjami w artykule [How to configure custom device settings in Microsoft Intune](custom-settings-configure.md) (Jak skonfigurować niestandardowe ustawienia urządzenia w usłudze Microsoft Intune).
2. W obszarze **Tworzenie profilu** wybierz pozycję **Ustawienia**, aby dodać co najmniej jedno ustawienie OMA-URI.
3. W obszarze **Ustawienia niestandardowe OMA-URI** kliknij przycisk **Dodaj**, aby dodać nową wartość. Możesz również kliknąć przycisk **Eksportuj**, aby utworzyć listę wszystkich wartości skonfigurowanych w pliku wartości rozdzielanych przecinkami (.csv).
4. Dla każdego ustawienia OMA-URI, które chcesz dodać, wprowadź następujące informacje:
    - **Nazwa ustawienia** — Wprowadź unikatową nazwę dla ustawienia OMA-URI, aby ułatwić jego identyfikację na liście ustawień.
    - **Opis** — Opcjonalnie wprowadź opis ustawienia.
    - **Typ danych** — Wybierz spośród opcji:
        - **Ciąg**
        - **Ciąg (XML)**
        - **Data i godzina**
        - **Liczba całkowita**
        - **Liczba zmiennoprzecinkowa**
        - **Wartość logiczna**
    - **OMA-URI (z uwzględnieniem wielkości liter)** — Określ identyfikator OMA-URI, dla którego chcesz podać ustawienie.
    - **Wartość** — Określ wartość, która będzie kojarzona z określonym wcześniej identyfikatorem OMA-URI.
1. Gdy skończysz, w obszarze **Tworzenie profilu** kliknij pozycję **Utwórz**.
Profil zostanie utworzony i wyświetlony na liście profilów.

## <a name="recommended-custom-settings"></a>Zalecane ustawienia niestandardowe

Następujące ustawienia są przydatne w przypadku urządzeń z systemem Windows Holographic for Business:


|Nazwa ustawienia|Identyfikator URI OMA|Typ danych  |
|---------|---------|---------|
|[AllowFastReconnect](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-allowfastreconnect)|./Vendor/MSFT/Policy/Config/Authentication/AllowFastReconnect|Integer<br>0 — niedozwolone<br>1 — dozwolone (ustawienie domyślne)|
|[AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)|./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Integer<br>0 — niedozwolone<br>1 — dozwolone (ustawienie domyślne)|
|[AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)|./Vendor/MSFT/Policy/Config/Update/AllowUpdateService|Integer<br>0 — usługa aktualizacji nie jest dozwolona <br>1 — usługa aktualizacji jest dozwolona (ustawienie domyślne)|
|[UpdateServiceURL](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)|./Vendor/MSFT/Policy/Config/Update/UpdateServiceUrl|String<br>Adres URL — urządzenie sprawdza dostępność aktualizacji na serwerze WSUS pod określonym adresem URL.<br>Nieskonfigurowane — urządzenie sprawdza dostępność aktualizacji w witrynie Microsoft Update.|
|[RequireUpdatesApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)|./Vendor/MSFT/Policy/Config/Update/RequireUpdateApproval|Integer<br>0 — nieskonfigurowane. Urządzenie instaluje wszystkie odpowiednie aktualizacje.<br>1 — urządzenie instaluje tylko aktualizacje, które zarówno można zastosować, jak i znajdują się na liście zatwierdzonych aktualizacji. Ustaw te zasady na wartość 1, jeśli dział IT chce kontrolować wdrożenia aktualizacji na urządzeniach, np. wtedy, gdy przed wdrożeniem jest wymagane testowanie.|
|[ApprovedUpdates](https://docs.microsoft.com/windows/client-management/mdm/update-csp)|./Vendor/MSFT/Update/ApprovedUpdates<br><br>**Ważne**<br>Musisz przeczytać i zaakceptować zaktualizowane Umowy licencyjne użytkownika oprogramowania (EULA) w imieniu swoich użytkowników końcowych. Niewykonanie tej czynności jest naruszeniem zobowiązań prawnych lub umownych.|Węzeł zatwierdzania aktualizacji i akceptacji Umowy licencyjnej użytkownika oprogramowania (EULA) w imieniu użytkownika końcowego.|
[ApplicationLaunchRestrictions](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp)|./Vendor/MSFT/AppLocker/ApplicationLaunchRestrictions/*Grouping*/*ApplicationType*/Policy<br><br>**Ważne**<br>W artykule dostawcy usług kryptograficznych funkcji AppLocker są używane przykłady XML. Aby skonfigurować ustawienia przy użyciu profilów niestandardowych w usłudze Intune, należy użyć zwykłego kodu XML.|String<br>Aby uzyskać więcej informacji, zobacz artykuł o [dostawcy usług kryptograficznych funkcji AppLocker](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp).

## <a name="how-to-find-the-policies-you-can-configure"></a>Jak znaleźć zasady, które można skonfigurować

W tabeli [CSPs supported in Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens) (Dostawcy usługi konfiguracji obsługiwani w systemie Windows Holographic) znajduje się pełna lista wszystkich dostawców usługi konfiguracji (CSP) obsługiwanych w systemie Windows Holographic. Nie wszystkie ustawienia są zgodne ze wszystkimi wersjami systemu Windows Holographic. Tabela w artykule poświęconym systemowi Windows zawiera informacje o wersjach obsługiwanych w przypadku poszczególnych dostawców usług konfiguracji.

Ponadto usługa Intune nie obsługuje wszystkich ustawień wymienionych w artykule. Aby dowiedzieć się, czy usługa Intune obsługuje dane ustawienie, otwórz artykuł dotyczący tego ustawienia. Na stronie każdego ustawienia znajdują się informacje dotyczące obsługiwanych operacji. Aby ustawienie mogło być używane z usługą Intune, musi obsługiwać operacje **Dodaj** lub **Zastąp**.
