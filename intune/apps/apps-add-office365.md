---
title: Dodawanie aplikacji usługi Office 365 do urządzeń z systemem Windows 10 przy użyciu usługi Microsoft Intune
titleSuffix: ''
description: Dowiedz się, jak przy użyciu usługi Microsoft Intune możesz zainstalować aplikacje usługi Office 365 na urządzeniach z systemem Windows 10.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/23/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3292671a-5f5a-429e-90f7-b20019787d22
ms.reviewer: craigma
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, seoapril2019
ms.collection: M365-identity-device-management
ms.openlocfilehash: 86d02ae1277ff2fd6dfce9bf206628f5dc1c2a84
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2020
ms.locfileid: "76755334"
---
# <a name="add-office-365-apps-to-windows-10-devices-with-microsoft-intune"></a>Dodawanie aplikacji usługi Office 365 do urządzeń z systemem Windows 10 za pomocą usługi Microsoft Intune

Aby móc przypisywać, monitorować, konfigurować lub zabezpieczać aplikacje, trzeba je najpierw dodać do usługi Intune. Jednym z dostępnych [typów aplikacji](apps-add.md#app-types-in-microsoft-intune) są aplikacje usługi Office 365 dla urządzeń z systemem Windows 10. Po wybraniu tego typu aplikacji w usłudze Intune możesz przypisać i zainstalować aplikacji usługi Office 365 na zarządzanych urządzeniach z systemem Windows 10. Możesz także przypisać i zainstalować aplikacje dla klienta klasycznego usługi Microsoft Project Online i programu Microsoft Visio Online Plan 2, jeśli masz ich licencje. Dostępne aplikacje usługi Office 365 są wyświetlane jako pojedynczy wpis na liście aplikacji w konsoli usługi Intune na platformie Azure.

> [!NOTE]
> Aplikacje usługi Office 365 ProPlus wdrożone za pośrednictwem usługi Microsoft Intune należy aktywować za pomocą licencji usługi Office 365 ProPlus. Obecnie usługa Intune nie obsługuje wersji Office 365 Business.

## <a name="before-you-start"></a>Przed rozpoczęciem

> [!IMPORTANT]
> Jeśli na urządzeniu użytkownika końcowego znajdują się aplikacje msi pakietu Office, musisz użyć funkcji **Usuń pliki MSI**, aby je bezpiecznie odinstalować. W przeciwnym razie nie będzie można zainstalować aplikacji usługi Office 365 dostarczonych przez usługę Intune.

- Na urządzeniach, na których wdrażasz te aplikacje, musi być zainstalowana aktualizacja Windows 10 Creators Update lub jej nowsza wersja.
- Usługa Intune obsługuje dodawanie aplikacji pakietu Office tylko z pakietu usługi Office 365.
- Jeśli jakiekolwiek aplikacje pakietu Office są otwarte, gdy usługa Intune instaluje pakiet aplikacji, instalacja może zakończyć się niepowodzeniem, a użytkownicy mogą utracić dane z niezapisanych plików.
- Ta metoda instalacji nie jest obsługiwana na urządzeniach z systemem Windows Home, Windows Team, Windows Holographic lub Windows Holographic for Business.
- Usługa Intune nie obsługuje instalowania aplikacji komputerowych usługi Office 365 ze sklepu Microsoft Store (znanych jako aplikacje pakietu Office Centennial) na urządzeniach, na których już wdrożono aplikacje usługi Office 365 przy użyciu usługi Intune. Jeśli zainstalujesz tę konfigurację, może dojść do utraty lub uszkodzenia danych.
- Wielokrotne wymagane lub dostępne przypisania aplikacji nie są dodawane. Nowsze przypisanie aplikacji spowoduje zastąpienie zainstalowanych wcześniej przypisań aplikacji. Jeśli na przykład pierwszy zestaw aplikacji pakietu Office zawiera program Word, a późniejszy go nie zawiera, program Word zostanie odinstalowany. Ten warunek nie dotyczy aplikacji Visio ani Project.
- Wielokrotne wdrożenia usługi Office 365 nie są obecnie obsługiwane. Na urządzenie można dostarczyć tylko jedno wdrożenie.
- **Wersja pakietu Office**: wybierz, czy chcesz przypisać 32-bitową, czy 64-bitową wersję pakietu Office. Wersję 32-bitową można zainstalować na urządzeniach 32-bitowych i 64-bitowych, ale wersję 64-bitową można zainstalować tylko na urządzeniach 64-bitowych.
- **Usuń plik MSI z urządzeń użytkownika końcowego** — wybierz, czy chcesz usunąć wcześniej istniejące aplikacje MSI pakietu Office z urządzeń użytkownika końcowego. Instalacja nie powiedzie się, jeśli na urządzeniach użytkownika końcowego są wcześniej istniejące aplikacje MSI. Aplikacje do odinstalowania nie są ograniczone tylko do aplikacji wybranych do instalacji w okienku **Konfigurowanie pakietu aplikacji**, ponieważ zostaną usunięte wszystkie aplikacje pakietu Office (MSI) na urządzeniu użytkownika końcowego. Aby uzyskać więcej informacji, zobacz [Remove existing MSI versions of Office when upgrading to Office 365 ProPlus (Usuwanie istniejących wersji MSI pakietu Office podczas uaktualniania do usługi Office 365 ProPlus)](https://docs.microsoft.com/deployoffice/upgrade-from-msi-version). Podczas ponownego instalowania pakietu Office na maszynach użytkowników końcowych przez usługę Intune użytkownicy końcowi automatycznie uzyskają te same pakiety językowe, które mieli z poprzednimi instalacjami MSI pakietu Office.

## <a name="select-the-office-365-suite-app-type"></a>Wybieranie typu aplikacji pakietu Office 365

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Aplikacje** > **Wszystkie aplikacje** > **Dodaj**.
3. Wybierz pozycję **Windows 10** w sekcji **Pakiet Office 365** okienka **Wybierz typ aplikacji**.
4. Kliknij pozycję **Wybierz**. Zostaną wyświetlone kroki **dodawania pakietu Office 365**.


## <a name="step-1---app-suite-information"></a>Krok 1. Informacje o pakiecie aplikacji

W tym kroku podajesz informacje o pakiecie aplikacji. Te informacje pomagają zidentyfikować pakiet aplikacji w usłudze Intune i ułatwiają użytkownikom wyszukiwanie tego pakietu w portalu firmy.

1. Na stronie **informacji o pakiecie aplikacji** możesz potwierdzić lub zmodyfikować wartości domyślne:
    - **Nazwa pakietu**: wprowadź nazwę pakietu aplikacji wyświetlaną w portalu firmy. Upewnij się, że wszystkie używane nazwy pakietów są unikatowe. Jeśli dana nazwa pakietu aplikacji występuje dwa razy, użytkownicy portalu firmy będą widzieć tylko jedną z aplikacji o tej nazwie.
    - **Opis pakietu**: wprowadź opis pakietu aplikacji. Możesz na przykład podać listę aplikacji wybranych do uwzględnienia.
    - **Wydawca**: w roli wydawcy występuje firma Microsoft.
    - **Kategoria**: opcjonalnie wybierz co najmniej jedną wbudowaną lub utworzoną przez siebie kategorię aplikacji. To ustawienie ułatwi użytkownikom znajdowanie pakietu aplikacji podczas przeglądania portalu firmy.
    - **Pokaż jako polecaną aplikację w Portalu firmy**: wybierz tę opcję, aby wyświetlić pakiet aplikacji w dobrze widocznym miejscu na stronie głównej portalu firmy podczas przeglądania aplikacji przez użytkowników.
    - **Adres URL informacji**: Opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o tej aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Adres URL zasad ochrony prywatności**: Opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje dotyczące zasad ochrony prywatności w tej aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Deweloper**: w roli dewelopera występuje firma Microsoft.
    - **Właściciel**: w roli właściciela występuje firma Microsoft.
    - **Uwagi**: wprowadź wszelkie uwagi, które chcesz skojarzyć z tą aplikacją.
    - **Logo**: logo usługi Office 365 jest wyświetlane razem z nazwą aplikacji podczas przeglądania portalu firmy.
2. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Konfigurowanie pakietu aplikacji**.

## <a name="step-2---option-1-configure-app-suite-using-the-configuration-designer"></a>Krok 2. (**Opcja 1**) Konfigurowanie pakietu aplikacji za pomocą projektanta konfiguracji 

Wybierając pozycję **Format ustawień konfiguracji**, możesz wybrać metodę konfigurowania ustawień aplikacji. Do wyboru są następujące opcje formatu ustawień:
- Projektant konfiguracji
- Wprowadzanie danych XML

Po wybraniu opcji **Projektant konfiguracji** okienko **Dodawanie aplikacji** zmieni się i będzie można w nim wybrać trzy dodatkowe opcje ustawień:
- Konfigurowanie pakietu aplikacji
- Informacje o pakiecie aplikacji
- Właściwości

<img alt="Add Office 365 - Configuration designer" src="./media/apps-add-office365/apps-add-office365-02.png" width="700">

1. Na stronie **Pakiet aplikacji konfiguracji** wybierz pozycję **Projektant konfiguracji**.
   - **Wybierz aplikacje pakietu Office**: z listy rozwijanej wybierz standardowe aplikacje pakietu Office, które chcesz przypisać do urządzeń.
   - **Wybierz inne aplikacje pakietu Office (wymagana licencja)** : z listy rozwijanej wybierz dodatkowe aplikacje pakietu Office, które chcesz przypisać do urządzeń i dla których masz licencje. Obejmują one aplikacje licencjonowane, takie jak Microsoft Project Online Desktop Client i Microsoft Visio Online Plan 2.
   - **Architektura**: wybierz, czy chcesz przypisać **32-bitową**, czy **64-bitową** wersję pakietu Office. Wersję 32-bitową można zainstalować na urządzeniach 32-bitowych i 64-bitowych, ale wersję 64-bitową można zainstalować tylko na urządzeniach 64-bitowych.
    - **Kanał aktualizacji**: wybierz sposób aktualizacji pakietu Office na urządzeniach. Aby uzyskać informacje dotyczące różnych kanałów aktualizacji, zobacz [Omówienie kanałów aktualizacji usługi Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus). Wybierz spośród opcji:
        - **Raz na miesiąc**
        - **Raz na miesiąc (docelowy)**
        - **Półroczny**
        - **Półroczny (docelowy)**

        Po wybraniu kanału możesz wybrać następujące opcje:
        - **Usuń inne wersje**: Wybierz pozycję **Tak**, aby usunąć inne wersje pakietu Office (MSI) z urządzeń użytkownika. Wybierz tę opcję, jeśli chcesz usunąć wcześniej istniejące aplikacje MSI pakietu Office z urządzeń użytkownika końcowego. Instalacja nie powiedzie się, jeśli na urządzeniach użytkownika końcowego są wcześniej istniejące aplikacje MSI. Aplikacje do odinstalowania nie są ograniczone tylko do aplikacji wybranych do instalacji w okienku **Konfigurowanie pakietu aplikacji**, ponieważ zostaną usunięte wszystkie aplikacje pakietu Office (MSI) na urządzeniu użytkownika końcowego. Aby uzyskać więcej informacji, zobacz [Remove existing MSI versions of Office when upgrading to Office 365 ProPlus (Usuwanie istniejących wersji MSI pakietu Office podczas uaktualniania do usługi Office 365 ProPlus)](https://docs.microsoft.com/deployoffice/upgrade-from-msi-version). Podczas ponownego instalowania pakietu Office na maszynach użytkowników końcowych przez usługę Intune użytkownicy końcowi automatycznie uzyskają te same pakiety językowe, które mieli z poprzednimi instalacjami MSI pakietu Office. 
        - **Wybierz wersję do zainstalowania**: wybierz wersję pakietu Office, która powinna zostać zainstalowana.
        - **Określona wersja**: Jeśli wybrano pozycję **Określona** jako **wersję do zainstalowania** w powyższym ustawieniu, można wybrać opcję instalacji określonej wersji pakietu Office dla wybranego kanału na urządzeniach użytkowników końcowych. 
            
            Dostępne wersje będą się zmieniać z upływem czasu. Dlatego podczas tworzenia nowego wdrożenia mogą być dostępne nowsze wersje, a pewne starsze wersje mogą być niedostępne. Bieżące wdrożenia będą nadal wdrażane przy użyciu starszej wersji, lecz lista dla kanału będzie stale aktualizowana.
            
            Dla urządzeń, które zaktualizowały swoje przypięte wersje (lub zaktualizowały jakiekolwiek inne właściwości) i są wdrożone jako dostępne, stan raportowania będzie widoczny jako zainstalowany, jeśli poprzednia wersja była zainstalowana, zanim nastąpiło zaewidencjonowanie urządzenia. Gdy nastąpi ewidencjonowanie urządzenia, stan zostanie tymczasowo zmieniony na Nieznany, jednak nie zostanie on wyświetlony dla użytkownika. Gdy użytkownik zainicjuje instalację nowszej dostępnej wersji, zobaczy zmianę stanu na Zainstalowane.
            
            Aby uzyskać więcej informacji, zobacz [Overview of update channels for Office 365 ProPlus (Omówienie kanałów aktualizacji usługi Office 365 ProPlus)](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus).
    - **Użyj aktywacji na komputerze udostępnionym**: wybierz tę opcję, jeśli wielu użytkowników współużytkuje komputer. Aby uzyskać więcej informacji, zobacz [omówienie aktywacji na komputerze udostępnionym dla usługi Office 365](https://docs.microsoft.com/DeployOffice/overview-of-shared-computer-activation-for-office-365-proplus).
    - **Automatycznie akceptuj licencję użytkownika aplikacji**: wybierz tę opcję, jeśli użytkownicy końcowi nie muszą akceptować umowy licencyjnej. Usługa Intune zaakceptuje umowę automatycznie.
    - **Języki**: pakiet Office jest automatycznie instalowany we wszystkich obsługiwanych językach, które zostały zainstalowane w systemie Windows na urządzeniu użytkownika końcowego. Wybierz tę opcję, jeśli chcesz zainstalować dodatkowe języki z pakietem aplikacji. <p></p>
        Dla aplikacji pakietu Office 365 Pro Plus zarządzanych przez usługę Intune możesz wdrożyć dodatkowe języki. Lista dostępnych języków uwzględnia **Typ** pakietu językowego (podstawowy, częściowy i weryfikujący). W witrynie Azure Portal wybierz kolejno pozycje **Microsoft Intune** > **Aplikacje** > **Wszystkie aplikacje** > **Dodaj**. Na liście **Typ aplikacji** w okienku **Dodaj aplikację** wybierz pozycję **Windows 10** w obszarze **Pakiet Office 365**. Wybierz pozycję **Języki** w okienku **Ustawienia pakietu aplikacji**. Aby uzyskać więcej informacji, zobacz artykuł [Overview of deploying languages in Office 365 ProPlus](https://docs.microsoft.com/deployoffice/overview-of-deploying-languages-in-office-365-proplus) (Omówienie wdrażania języków w usłudze Office 365 ProPlus).
2. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Tagi zakresu**.

## <a name="step-2---option-2-configure-app-suite-using-xml-data"></a>Krok 2. (**Opcja 2**) Konfigurowanie pakietu aplikacji przy użyciu danych XML 

W przypadku wybrania opcji **Wprowadź dane XML** w polu listy rozwijanej **format ustawienia** na stronie **Konfigurowanie pakietu aplikacji** możesz skonfigurować pakiet aplikacji Office przy użyciu niestandardowego pliku konfiguracji.

![Dodawanie projektanta konfiguracji usługi Office 365](./media/apps-add-office365/apps-add-office365-01.png)

1. Dodano plik XML konfiguracji.
2. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Tagi zakresu**.

Aby uzyskać więcej informacji na temat wprowadzania danych XML, zobacz artykuł [Configuration options for the Office Deployment Tool](https://docs.microsoft.com/DeployOffice/configuration-options-for-the-office-2016-deployment-tool) (Opcje konfiguracji narzędzia wdrażania pakietu Office).

## <a name="step-3---select-scope-tags-optional"></a>Krok 3. Wybieranie tagów zakresu (opcjonalnie)
Za pomocą tagów zakresu można określić, kto będzie mógł wyświetlać informacje o aplikacji klienckiej w usłudze Intune. Więcej informacji o tagach zakresu zawiera artykuł [Używanie kontroli dostępu opartej na rolach i tagów zakresu w rozproszonej infrastrukturze informatycznej](../fundamentals/scope-tags.md).

1. Kliknij pozycję **Wybierz tagi zakresu**, aby opcjonalnie dodać tagi zakresu dla pakietu aplikacji. 
2. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Przypisania**.

## <a name="step-4---assignments"></a>Krok 4. Przypisania

1. Wybierz przypisania grupy **Wymagane**, **Dostępne dla zarejestrowanych urządzeń** lub **Odinstaluj** dla pakietu aplikacji. Aby uzyskać więcej informacji, zobacz temat [Dodawanie grup w celu organizowania użytkowników i urządzeń](~/fundamentals/groups-add.md) i [Przypisywanie aplikacji do grup przy użyciu usługi Microsoft Intune](apps-deploy.md).
2. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Recenzja i tworzenie**. 

## <a name="step-5---review--create"></a>Krok 5. Przegląd + tworzenie

1. Przejrzyj wartości i ustawienia wprowadzone dla pakietu aplikacji.
2. Gdy skończysz, kliknij pozycję **Utwórz**, aby dodać aplikację do usługi Intune.

    Zostanie wyświetlony blok **Omówienie** dotyczący utworzonego pakietu aplikacji systemu Windows 10 dla usługi Office 365.

## <a name="deployment-details"></a>Szczegóły wdrożenia

Po przypisaniu zasad wdrażania z usługi Intune do maszyn docelowych za pośrednictwem [dostawcy usługi konfiguracji pakietu Office (CSP)](https://docs.microsoft.com/windows/client-management/mdm/office-csp) urządzenie końcowe automatycznie pobierze pakiet instalacyjny z lokalizacji *officecdn.microsoft.com*. W katalogu *Program Files* zostaną wyświetlone dwa katalogi:

![Pakiety instalacji pakietu Office w katalogu Program Files](./media/apps-add-office365/office-folder.png)

W katalogu *Microsoft Office* zostanie utworzony nowy folder, w którym są przechowywane pliki instalacyjne:

![Nowo utworzony folder w katalogu Microsoft Office](./media/apps-add-office365/created-folder.png)

W katalogu *Microsoft Office 15* są przechowywane pliki modułu uruchamiania instalacji typu Szybka instalacja. Instalacja rozpocznie się automatycznie, jeśli wymagany jest typ przypisania:

![Pliki uruchamiania instalacji typu Szybka instalacja](./media/apps-add-office365/clicktorun-files.png)

Instalacja zostanie przeprowadzona w trybie dyskretnym, jeśli przypisanie pakietu O365 zostanie skonfigurowane zgodnie z wymaganiami. Pobrane pliki instalacyjne zostaną usunięte po pomyślnym zakończeniu instalacji. Jeśli przypisanie zostanie skonfigurowane jako **Dostępne**, aplikacje pakietu Office pojawią się w aplikacji Portal firmy, aby użytkownicy końcowi mogli ręcznie wyzwolić instalację.

## <a name="troubleshooting"></a>Rozwiązywanie problemów
Usługa Intune używa [narzędzia wdrażania pakietu Office](https://docs.microsoft.com/DeployOffice/overview-of-the-office-2016-deployment-tool) do pobrania i wdrożenia usługi Office 365 ProPlus do komputerów klienckich przy użyciu [sieci CDN usługi Office 365](https://docs.microsoft.com/office365/enterprise/content-delivery-networks). Skorzystaj z najlepszych rozwiązań opisanych w temacie [Managing Office 365 endpoints](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints) (Zarządzanie punktami końcowymi usługi Office 365), aby upewnić się, że konfiguracja sieci umożliwia klientom bezpośredni dostęp do sieci CDN zamiast kierowania ruchu CDN za pośrednictwem centralnych serwerów proxy, co pozwoli uniknąć niepotrzebnego opóźnienia.

Jeśli wystąpią problemy podczas instalacji lub w czasie wykonywania, uruchom program [Asystent odzyskiwania i pomocy technicznej firmy Microsoft dla usługi Office 365 ](https://diagnostics.office.com) na urządzeniu docelowym.

### <a name="additional-troubleshooting-details"></a>Dodatkowe informacje dotyczące rozwiązywania problemów

Jeśli nie możesz zainstalować aplikacji usługi O365 na urządzeniu, musisz określić, czy problem dotyczy usługi Intune, czy systemu operacyjnego lub pakietu Office. Jeśli w katalogu *Program Files* urządzenia widoczne są foldery *Microsoft Office* i *Microsoft Office 15*, można potwierdzić, że usługa Intune pomyślnie zainicjowała wdrożenie. Jeśli te dwa foldery nie są widoczne w katalogu *Program Files*, należy potwierdzić następujące przypadki:

- Urządzenie zostało prawidłowo zarejestrowane w usłudze Microsoft Intune. 
- Na urządzeniu istnieje aktywne połączenie sieciowe. Jeśli urządzenie jest w trybie samolotowym, jest wyłączone lub znajduje się w lokalizacji bez zasięgu usług, zasady nie zostaną zastosowane, dopóki nie zostanie nawiązane połączenie sieciowe.
- Spełniono wymagania sieciowe dotyczące zarówno usługi Intune, jak i usługi Office 365, a powiązane zakresy adresów IP są dostępne zgodnie z następującymi artykułami:

  - [Przepustowość i wymagania dotyczące konfiguracji sieci usługi Intune](https://docs.microsoft.com/intune/network-bandwidth-use)
  - [Adresy URL i zakresy adresów IP usługi Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)

- Pakiet aplikacji usługi O365 został przypisany do odpowiednich grup. 

Ponadto należy monitorować rozmiar katalogu *C:\Program Files\Microsoft Office\Updates\Download*. Pakiet instalacyjny pobrany z chmury usługi Intune zostanie zapisany w tej lokalizacji. Jeśli rozmiar tego katalogu nie zwiększa się lub zwiększa się bardzo powoli, zaleca się ponowne sprawdzenie łączności sieciowej i przepustowości.

Jeśli okaże się, że usługa Intune i infrastruktura sieciowa działają zgodnie z oczekiwaniami, należy przeanalizować problem z perspektywy systemu operacyjnego. Należy rozważyć następujące kwestie:

- Na urządzeniu docelowym musi działać system Windows 10 Creators Update lub nowszy.
- Podczas wdrażania aplikacji przez usługę Intune nie mogą być otwarte żadne istniejące aplikacje pakietu Office.
- Istniejące wersje MSI pakietu Office zostały prawidłowo usunięte z urządzenia. Usługa Intune korzysta z funkcji Szybka instalacja pakietu Office, która nie jest zgodna z pakietem Office MSI. To zachowanie zostało opisane w następującym dokumencie:<br>
  [Pakiet Office zainstalowany za pomocą funkcji Szybka instalacja i Instalatora Windows na tym samym komputerze nie jest obsługiwany](https://support.office.com/article/office-installed-with-click-to-run-and-windows-installer-on-same-computer-isn-t-supported-30775ef4-fa77-4f47-98fb-c5826a6926cd)
- Zalogowany użytkownik musi mieć uprawnienia do instalowania aplikacji na urządzeniu.
- Upewnij się, że nie ma żadnych problemów, na podstawie dziennika Podgląd zdarzeń systemu Windows **Dzienniki systemu Windows** -> **Aplikacje**.
- Przechwyć pełne dzienniki instalacji pakietu Office podczas instalacji. W tym celu wykonaj następujące czynności:<br>
    1. Aktywuj pełne rejestrowanie dla instalacji pakietu Office na komputerach docelowych. W tym celu uruchom następujące polecenie, aby zmodyfikować rejestr:<br>
        `reg add HKLM\SOFTWARE\Microsoft\ClickToRun\OverRide /v LogLevel /t REG_DWORD /d 3`<br>
    2. Ponownie wdróż pakiet usługi Office 365 na urządzeniach docelowych.<br>
    3. Odczekaj około 15–20 minut, a następnie przejdź do folderu **% temp%** i folderu **%windir%\temp**, posortuj według **Data modyfikacji** i wybierz pliki *{nazwa komputera}-{sygnatura czasowa}.log*, które są modyfikowane zgodnie z czasem odtwarzania.<br>
    4. Uruchom następujące polecenie, aby wyłączyć pełny dziennik:<br>
        `reg delete HKLM\SOFTWARE\Microsoft\ClickToRun\OverRide /v LogLevel /f`<br>
        Pełne dzienniki mogą dostarczyć dalszych szczegółowych informacji o procesie instalacji.

## <a name="errors-during-installation-of-the-app-suite"></a>Błędy podczas instalacji pakietu aplikacji

Informacje na temat wyświetlania pełnych dzienników instalacji zawiera artykuł [How to enable Office 365 ProPlus ULS logging](/office/troubleshoot/diagnostic-logs/how-to-enable-office-365-proplus-uls-logging) (Jak włączyć rejestrowanie zdarzeń usługi Office 365 ProPlus w usłudze ULS).

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

- Aby przypisać pakiet aplikacji do dodatkowych grup, zobacz temat [Przypisywanie aplikacji do grup](/intune-azure/manage-apps/deploy-apps).
