---
title: Instalowanie aplikacji usługi Office 365 na urządzeniach przy użyciu usługi Microsoft Intune
titlesuffix: ''
description: Dowiedz się, jak przy użyciu usługi Microsoft Intune można ułatwić instalowanie aplikacji usługi Office 365 na urządzeniach z systemem Windows 10.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/11/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3292671a-5f5a-429e-90f7-b20019787d22
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7d3db1449ec583678924fadb0db930146c3cd848
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/02/2019
ms.locfileid: "57229755"
---
# <a name="assign-office-365-apps-to-windows-10-devices-with-microsoft-intune"></a>Przypisywanie aplikacji usługi Office 365 do urządzeń z systemem Windows 10 przy użyciu usługi Microsoft Intune

Ten typ aplikacji ułatwia przypisywanie aplikacji usługi Office 365 do zarządzanych przez Ciebie urządzeń z systemem Windows 10. Możesz także zainstalować aplikacje dla klienta klasycznego usługi Microsoft Project Online i programu Microsoft Visio Pro dla usługi Office 365, jeśli masz ich licencje. Wybrane aplikacje są wyświetlane jako pojedynczy wpis na liście aplikacji w konsoli usługi Intune.

> [!NOTE]
> Aplikacje usługi Office 365 ProPlus wdrożone za pośrednictwem usługi Microsoft Intune należy aktywować za pomocą licencji usługi Office 365 ProPlus. Obecnie usługa Intune nie obsługuje wersji Office 365 Business.

## <a name="before-you-start"></a>Przed rozpoczęciem

> [!IMPORTANT]
> Jeśli na urządzeniu użytkownika końcowego znajdują się aplikacje msi pakietu Office, musisz użyć funkcji **Usuń pliki MSI**, aby je bezpiecznie odinstalować. W przeciwnym razie nie będzie można zainstalować aplikacji usługi Office 365 dostarczonych przez usługę Intune.

- Na urządzeniach, na których wdrażasz te aplikacje, musi być zainstalowana aktualizacja Windows 10 Creators Update lub jej nowsza wersja.
- Usługa Intune obsługuje dodawanie aplikacji pakietu Office tylko z pakietu usługi Office 365.
- Jeśli jakiekolwiek aplikacje pakietu Office są otwarte, gdy usługa Intune instaluje pakiet aplikacji, instalacja może zakończyć się niepowodzeniem, a użytkownicy mogą utracić dane z niezapisanych plików.
- Ta metoda instalacji nie jest obsługiwana na urządzeniach z systemem Windows 10 S, Windows Home, Windows Team, Windows Holographic lub Windows Holographic for Business.
- Usługa Intune nie obsługuje instalowania aplikacji komputerowych usługi Office 365 ze sklepu Microsoft Store (znanych jako aplikacje pakietu Office Centennial) na urządzeniach, na których już wdrożono aplikacje usługi Office 365 przy użyciu usługi Intune. Jeśli zainstalujesz tę konfigurację, może dojść do utraty lub uszkodzenia danych.
- Wielokrotne wymagane lub dostępne przypisania aplikacji nie są dodawane. Nowsze przypisanie aplikacji spowoduje zastąpienie zainstalowanych wcześniej przypisań aplikacji. Jeśli na przykład pierwszy zestaw aplikacji pakietu Office zawiera program Word, a późniejszy go nie zawiera, program Word zostanie odinstalowany. Ten warunek nie dotyczy aplikacji Visio ani Project.
- **Wersja pakietu Office**: wybierz, czy chcesz przypisać 32-bitową, czy 64-bitową wersję pakietu Office. Wersję 32-bitową można zainstalować na urządzeniach 32-bitowych i 64-bitowych, ale wersję 64-bitową można zainstalować tylko na urządzeniach 64-bitowych.
- **Usuń plik MSI z urządzeń użytkownika końcowego** — wybierz, czy chcesz usunąć wcześniej istniejące aplikacje MSI pakietu Office z urządzeń użytkownika końcowego. Instalacja nie powiedzie się, jeśli na urządzeniach użytkownika końcowego są wcześniej istniejące aplikacje MSI. Aplikacje do odinstalowania nie są ograniczone tylko do aplikacji wybranych do instalacji w okienku **Konfigurowanie pakietu aplikacji**, ponieważ zostaną usunięte wszystkie aplikacje pakietu Office (MSI) na urządzeniu użytkownika końcowego. Aby uzyskać więcej informacji, zobacz [Remove existing MSI versions of Office when upgrading to Office 365 ProPlus (Usuwanie istniejących wersji MSI pakietu Office podczas uaktualniania do usługi Office 365 ProPlus)](https://docs.microsoft.com/deployoffice/upgrade-from-msi-version). Podczas ponownego instalowania pakietu Office na maszynach użytkowników końcowych przez usługę Intune użytkownicy końcowi automatycznie uzyskają te same pakiety językowe, które mieli z poprzednimi instalacjami MSI pakietu Office.

## <a name="get-started"></a>Wprowadzenie

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Aplikacje klienckie**.
4. W okienku obciążenia **Aplikacje klienckie** w obszarze **Zarządzanie** wybierz pozycję **Aplikacje**.
5. Wybierz pozycję **Dodaj**.
6. W okienku **Dodawanie aplikacji** na liście **Typ aplikacji** w obszarze **Pakiet Office 365** wybierz pozycję **Windows 10**.

Możesz teraz skonfigurować pakiet aplikacji.

## <a name="configure-the-app-suite"></a>Konfigurowanie pakietu aplikacji

Wybierz aplikacje pakietu Office, które chcesz przypisać do urządzeń.

1. W okienku **Dodawanie aplikacji** wybierz pozycję **Konfiguruj pakiet aplikacji**.
2. W okienku **Konfigurowanie pakietu aplikacji** wybierz standardowe aplikacje pakietu Office, które chcesz przypisać do urządzeń.  
    Ponadto możesz zainstalować aplikacje dla klienta klasycznego usługi Microsoft Project Online i programu Microsoft Visio Pro dla usługi Office 365, jeśli masz ich licencje.
3. Wybierz przycisk **OK**.

## <a name="configure-app-information"></a>Konfigurowanie informacji o aplikacji

W tym kroku podajesz informacje o pakiecie aplikacji. Te informacje pomagają zidentyfikować pakiet aplikacji w usłudze Intune i ułatwiają użytkownikom wyszukiwanie tego pakietu w portalu firmy.

1. W okienku **Dodawanie aplikacji** wybierz pozycję **Informacje o pakiecie aplikacji**.
2. W okienku **Informacje o pakiecie aplikacji** wykonaj następujące czynności:
    - **Nazwa pakietu**: wprowadź nazwę pakietu aplikacji wyświetlaną w portalu firmy. Upewnij się, że wszystkie używane nazwy pakietów są unikatowe. Jeśli dana nazwa pakietu aplikacji występuje dwa razy, użytkownicy portalu firmy będą widzieć tylko jedną z aplikacji o tej nazwie.
    - **Opis pakietu**: wprowadź opis pakietu aplikacji. Możesz na przykład podać listę aplikacji wybranych do uwzględnienia.
    - **Wydawca**: w roli wydawcy występuje firma Microsoft.
    - **Kategoria**: opcjonalnie wybierz co najmniej jedną wbudowaną lub utworzoną przez siebie kategorię aplikacji. To ustawienie ułatwi użytkownikom znajdowanie pakietu aplikacji podczas przeglądania portalu firmy.
    - **Wyświetl jako polecaną aplikację w Portalu firmy**: wybierz tę opcję, aby wyświetlić pakiet aplikacji w dobrze widocznym miejscu na stronie głównej portalu firmy podczas przeglądania aplikacji przez użytkowników.
    - **Adres URL informacji**: Opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o tej aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Adres URL zasad ochrony prywatności**: Opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje dotyczące zasad ochrony prywatności w tej aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Deweloper**: w roli dewelopera występuje firma Microsoft.
    - **Właściciel**: w roli właściciela występuje firma Microsoft.
    - **Uwagi**: wprowadź wszelkie uwagi, które chcesz skojarzyć z tą aplikacją.
    - **Logo**: logo usługi Office 365 jest wyświetlane razem z nazwą aplikacji podczas przeglądania portalu firmy.
3. Wybierz przycisk **OK**.

## <a name="configure-app-settings"></a>Konfigurowanie ustawień aplikacji

W tym kroku skonfigurujesz opcje instalacji pakietu aplikacji. Ustawienia są stosowane do wszystkich aplikacji dodawanych do pakietu.

1. W okienku **Dodawanie aplikacji** wybierz pozycję **Ustawienia pakietu aplikacji**.
2. W okienku **Ustawienia pakietu aplikacji** wykonaj następujące czynności:
    - **Wersja pakietu Office**: wybierz, czy chcesz przypisać 32-bitową, czy 64-bitową wersję pakietu Office. Wersję 32-bitową można zainstalować na urządzeniach 32-bitowych i 64-bitowych, ale wersję 64-bitową można zainstalować tylko na urządzeniach 64-bitowych.
    - **Kanał aktualizacji**: wybierz sposób aktualizacji pakietu Office na urządzeniach. Aby uzyskać informacje dotyczące różnych kanałów aktualizacji, zobacz [Omówienie kanałów aktualizacji usługi Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus). Wybierz spośród opcji:
        - **Raz na miesiąc**
        - **Raz na miesiąc (docelowy)**
        - **Półroczny**
        - **Półroczny (docelowy)**

        Po wybraniu kanału możesz opcjonalnie wybrać pozycję **Określona**, aby zainstalować określoną wersję pakietu Office dla wybranego kanału na urządzeniach użytkownika końcowego. Następnie wybierz **określoną wersję** pakietu Office do użycia.
        
        Dostępne wersje będą się zmieniać z upływem czasu. Dlatego podczas tworzenia nowego wdrożenia mogą być dostępne nowsze wersje, a pewne starsze wersje mogą być niedostępne. Bieżące wdrożenia będą nadal wdrażane przy użyciu starszej wersji, lecz lista dla kanału będzie stale aktualizowana.
        
        Dla urządzeń, które zaktualizowały swoje przypięte wersje (lub zaktualizowały jakiekolwiek inne właściwości) i są wdrożone jako dostępne, stan raportowania będzie widoczny jako zainstalowany, jeśli poprzednia wersja była zainstalowana, zanim nastąpiło zaewidencjonowanie urządzenia. Gdy nastąpi ewidencjonowanie urządzenia, stan zostanie tymczasowo zmieniony na Nieznany, jednak nie zostanie on wyświetlony dla użytkownika. Gdy użytkownik zainicjuje instalację nowszej dostępnej wersji, zobaczy zmianę stanu na Zainstalowane.
        
        Aby uzyskać więcej informacji, zobacz [Overview of update channels for Office 365 ProPlus (Omówienie kanałów aktualizacji usługi Office 365 ProPlus)](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus).

    - **Usuń plik MSI z urządzeń użytkownika końcowego** — wybierz, czy chcesz usunąć wcześniej istniejące aplikacje MSI pakietu Office z urządzeń użytkownika końcowego. Instalacja nie powiedzie się, jeśli na urządzeniach użytkownika końcowego są wcześniej istniejące aplikacje MSI. Aplikacje do odinstalowania nie są ograniczone tylko do aplikacji wybranych do instalacji w okienku **Konfigurowanie pakietu aplikacji**, ponieważ zostaną usunięte wszystkie aplikacje pakietu Office (MSI) na urządzeniu użytkownika końcowego. Aby uzyskać więcej informacji, zobacz [Remove existing MSI versions of Office when upgrading to Office 365 ProPlus (Usuwanie istniejących wersji MSI pakietu Office podczas uaktualniania do usługi Office 365 ProPlus)](https://docs.microsoft.com/deployoffice/upgrade-from-msi-version). Podczas ponownego instalowania pakietu Office na maszynach użytkowników końcowych przez usługę Intune użytkownicy końcowi automatycznie uzyskają te same pakiety językowe, które mieli z poprzednimi instalacjami MSI pakietu Office. 
    - **Automatycznie akceptuj licencję użytkownika aplikacji**: wybierz tę opcję, jeśli użytkownicy końcowi nie muszą akceptować umowy licencyjnej. Usługa Intune zaakceptuje umowę automatycznie.
    - **Użyj aktywacji na komputerze udostępnionym**: wybierz tę opcję, jeśli wielu użytkowników współużytkuje komputer. Aby uzyskać więcej informacji, zobacz [omówienie aktywacji na komputerze udostępnionym dla usługi Office 365](https://docs.microsoft.com/DeployOffice/overview-of-shared-computer-activation-for-office-365-proplus).
    - **Języki**: pakiet Office jest automatycznie instalowany we wszystkich obsługiwanych językach, które zostały zainstalowane w systemie Windows na urządzeniu użytkownika końcowego. Wybierz tę opcję, jeśli chcesz zainstalować dodatkowe języki z pakietem aplikacji. <p></p>
    Dla aplikacji pakietu Office 365 Pro Plus zarządzanych przez usługę Intune możesz wdrożyć dodatkowe języki. Lista dostępnych języków uwzględnia **Typ** pakietu językowego (podstawowy, częściowy i weryfikujący). W witrynie Azure Portal wybierz pozycję **Microsoft Intune** > **Aplikacje klienckie** > **Aplikacje** > **Dodaj**. Na liście **Typ aplikacji** w bloku **Dodaj aplikację** wybierz pozycję **Windows 10** w obszarze **Pakiet Office 365**. Wybierz pozycję **Języki** w bloku **Ustawienia pakietu aplikacji**. Aby uzyskać więcej informacji, zobacz artykuł [Overview of deploying languages in Office 365 ProPlus](https://docs.microsoft.com/deployoffice/overview-of-deploying-languages-in-office-365-proplus) (Omówienie wdrażania języków w usłudze Office 365 ProPlus).

## <a name="finish-up"></a>Zakończenie

Po zakończeniu w okienku **Dodawanie aplikacji** wybierz pozycję **Dodaj**. Utworzona aplikacja jest wyświetlana na liście aplikacji.

## <a name="errors-during-installation-of-the-app-suite"></a>Błędy podczas instalacji pakietu aplikacji

W poniższej tabeli przedstawiono listę kodów typowych błędów, które mogą wystąpić, oraz ich znaczenie.

### <a name="status-for-office-csp"></a>Stan dostawcy CSP pakietu Office

| Stan | Etap | Opis |
|--------------------------------------------------|--------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1460 (ERROR_TIMEOUT) | Pliki do pobrania | Nie można pobrać Narzędzia wdrażania pakietu Office |
| 13 (ERROR_INVALID_DATA) | - | Nie można zweryfikować podpisu pobranego Narzędzia wdrażania pakietu Office |
| Kod błędu z zasad CertVerifyCertificateChainPolicy | - | Nie można sprawdzić certyfikatów pobranego Narzędzia wdrażania pakietu Office |
| 997 | PWT | Instalowanie |
| 0 | Po instalacji | Instalacja zakończona pomyślnie |
| 1603 (ERROR_INSTALL_FAILURE) | - | Nie można sprawdzić wymagań wstępnych, takich jak: SxS (nastąpiła próba instalacji po zainstalowaniu instalatora MSI 2016), niezgodność wersji, inne |
| 0x8000ffff (E_UNEXPECTED) | - | Podjęto próbę odinstalowania w sytuacji, gdy na maszynie nie ma modułu Szybka instalacja pakietu Office |
| 17002 | - | Nie można ukończyć scenariusza (instalacja). Możliwe przyczyny: instalacja anulowana przez użytkownika, instalacja anulowana przez inną instalację, brak miejsca na dysku podczas instalacji, nieznany identyfikator języka |
| 17004 | - | Nieznane jednostki SKU |


### <a name="office-deployment-tool-error-codes"></a>Kody błędów Narzędzia wdrażania pakietu Office

| Scenariusz | Kod powrotu | Interfejs użytkownika | Uwaga |
|------------------------------------------------------------------------------------------------------------------|---------------------------------------|----------------------------------------------------|------------------------------------|
| Podjęto działania związane z odinstalowywaniem w sytuacji, gdy nie ma aktywnego modułu Szybka instalacja | -2147418113, 0x8000ffff lub 2147549183 | Kod błędu: 30088-1008 Kod błędu: 30125-1011 (404) | Narzędzie wdrażania pakietu Office |
| Instalacja, gdy zainstalowano wersję instalatora MSI | 1603 | - | Narzędzie wdrażania pakietu Office |
| Instalacja anulowana przez użytkownika lub inną instalację | 17002 | - | Szybka instalacja |
| Próba zainstalowania wersji 64-bitowej na urządzeniu z zainstalowaną wersją 32-bitową | 1603 | - | Kod zwrotny Narzędzia wdrażania pakietu Office |
| Próba zainstalowania nieznanej jednostki SKU (to nie jest rzeczywisty przypadek użycia dostawcy CSP pakietu Office, ponieważ należy przekazywać tylko prawidłowe jednostki SKU) | 17004 | - | Szybka instalacja |
| Brak miejsca | 17002 | - | Szybka instalacja |
| Nie można uruchomić modułu Szybka instalacja (nieoczekiwana sytuacja) | 17000 | - | Szybka instalacja |
| Moduł Szybka instalacja nie mógł umieścić scenariusza w kolejce (nieoczekiwana sytuacja) | 17001 | - | Szybka instalacja |

## <a name="next-steps"></a>Następne kroki

- Aby przypisać aplikacje do wybranych grup, [Przypisywanie aplikacji do grup](/intune-azure/manage-apps/deploy-apps).
