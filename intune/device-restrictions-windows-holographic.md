---
title: Ustawienia urządzeń z systemem Windows Holographic for Business — Microsoft Intune — Azure | Microsoft Docs
description: Przeczytaj informacje i skonfiguruj ustawienia ograniczeń urządzeń w usłudze Microsoft Intune dla systemu Windows Holographic for Business, w tym wyrejestrowanie, geolokalizację, hasła, instalowanie aplikacji ze sklepu z aplikacjami, pliki cookie i menu podręczne w programie Microsoft Edge, usługę Windows Defender, wyszukiwanie, chmurę i magazyn, łączność Bluetooth, czas systemowy oraz dane użycia na platformie Azure.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: cdac4623c6c5c9e7258897e1536856e6b24492ea
ms.sourcegitcommit: fff179f59bd542677cbd4bf3bacc24bb880e2cb6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/07/2018
ms.locfileid: "53032014"
---
# <a name="windows-holographic-for-business-device-settings-to-allow-or-restrict-features-using-intune"></a>Ustawienia urządzeń z systemem Windows Holographic for Business w celu zezwolenia na funkcje lub ich ograniczenia przy użyciu usługi Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

W tym artykule wymieniono i opisano różne ustawienia, które można kontrolować na urządzeniach z systemem Windows Holographic for Business, takich jak Microsoft Hololens. Użyj tych ustawień w ramach swojego rozwiązania do zarządzania urządzeniami mobilnymi (MDM), aby zezwolić na działanie funkcji lub je wyłączyć, kontrolować zabezpieczenia i nie tylko.

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji urządzenia](device-restrictions-configure.md).

## <a name="general"></a>Ogólne

- **Ręczne wyrejestrowanie**: Umożliwia użytkownikowi ręczne usunięcie z urządzenia konta w miejscu pracy.
- **Cortana**: Włącza lub wyłącza asystenta głosowego Cortana.
- **Geolokalizacja**: Określa, czy urządzenie może używać informacji z usług lokalizacyjnych.

## <a name="password"></a>Hasło

- **Hasło**: Wymaga od użytkownika końcowego wprowadzenia hasła w celu uzyskania dostępu do urządzenia.
- **Wymagaj hasła po przywróceniu urządzenia ze stanu bezczynności**: Określa, że użytkownik musi wprowadzić hasło, aby odblokować urządzenie.

## <a name="app-store"></a>App Store

- **Automatycznie aktualizuj aplikacje ze sklepu**: Umożliwia automatyczne aktualizowanie zainstalowanych aplikacji pochodzących ze sklepu Microsoft Store.
- **Instalacja aplikacji zaufanej**: Umożliwia ładowanie bezpośrednie aplikacji podpisanych za pomocą zaufanego certyfikatu.
- **Odblokowanie trybu deweloperskiego**: Umożliwia korzystanie z ustawień trybu deweloperskiego systemu Windows, na przykład zezwolenie użytkownikowi końcowemu na modyfikację aplikacji ładowanych bezpośrednio.

## <a name="microsoft-edge-browser"></a>Przeglądarka Microsoft Edge

- **Pliki cookie**: Umożliwia przeglądarce na urządzeniu zapisywanie plików cookie z Internetu.
- **Wyskakujące okienka**: Umożliwia blokowanie wyskakujących okienek w przeglądarce (tylko system Windows 10 Desktop).
- **Sugestie wyszukiwania**: Umożliwia wyszukiwarce sugerowanie witryn podczas wpisywania fraz do wyszukania.
- **Menedżer haseł**: Włącza lub wyłącza funkcję menedżera haseł w przeglądarce Microsoft Edge.
- **Wysyłaj nagłówki Nie śledź**: Konfiguruje przeglądarkę Microsoft Edge, aby wysyłała nagłówki „Nie śledź” do witryn internetowych odwiedzanych przez użytkowników.

## <a name="windows-defender-smart-screen"></a>Windows Defender SmartScreen

- **SmartScreen dla Microsoft Edge**: Włącz filtr SmartScreen dla przeglądarki Microsoft Edge używany podczas uzyskiwania dostępu do witryn i pobierania plików.

## <a name="search"></a>Wyszukaj

- **Lokalizacja wyszukiwania** — określ, czy podczas wyszukiwania mogą być używane informacje o lokalizacji.

## <a name="cloud-and-storage"></a>Chmura i magazyn

- **Konto Microsoft**: Zezwala użytkownikowi na skojarzenie konta Microsoft z urządzeniem.

## <a name="cellular-and-connectivity"></a>Sieć komórkowa i łączność

- **Bluetooth**: Określa, czy użytkownik może włączyć i skonfigurować na urządzeniu połączenie Bluetooth.
- **Odnajdowanie Bluetooth**: Umożliwia wykrycie urządzenia przez inne urządzenia obsługujące technologię Bluetooth.
- **Reklamy Bluetooth**: Umożliwia urządzeniu odbieranie reklam przez połączenie Bluetooth.

## <a name="control-panel-and-settings"></a>Panel sterowania i Ustawienia

- **Modyfikowanie czasu systemowego**: Uniemożliwia użytkownikowi końcowemu zmianę daty i godziny na urządzeniu.

## <a name="kiosk---obsolete"></a>Kiosk — przestarzałe

Te ustawienia są przeznaczone tylko do odczytu i nie można ich zmienić. Aby skonfigurować tryb kiosku, zobacz [Ustawienia kiosku](kiosk-settings.md#windows-holographic-for-business).

Na kiosku jest zazwyczaj uruchamiana konkretna aplikacja. Użytkownicy nie mogą uzyskać na urządzeniu dostępu do funkcjonalności lub funkcji spoza aplikacji kiosku.

- **Tryb kiosku**: Wskazuje typ trybu kiosku obsługiwanego przez zasady. Dostępne opcje:

  - **Nieskonfigurowane** (wartość domyślna): Zasady nie umożliwiają korzystania z trybu kiosku. 
  - **Kiosk z pojedynczą aplikacją**: Profil umożliwia uruchamianie tylko jednej aplikacji na urządzeniu. Gdy użytkownik zaloguje się, jest uruchamiana konkretna aplikacja. Ten tryb uniemożliwia także użytkownikowi otwieranie nowych aplikacji oraz zmianę uruchomionej aplikacji.
  - **Kiosk z wieloma aplikacjami**: Profil umożliwia uruchamianie wielu aplikacji na urządzeniu. Tylko dodane aplikacje są dostępne dla użytkownika. Korzyści z kiosku z wieloma aplikacjami (czyli urządzenia o stałym przeznaczeniu) polegają na udostępnieniu użytkownikom łatwego do poznania środowiska, w którym są dostępne tylko potrzebne im aplikacje. Aplikacje, których użytkownicy nie potrzebują, są ukryte. 
  
    Dodając aplikacje do środowiska kiosku z wieloma aplikacjami, dodajesz również plik układu menu Start. Temat [Start menu layout file (Plik układu menu Start)](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-file-for-intune) zawiera przykładowy kod XML, którego można użyć w usłudze Intune. 

#### <a name="single-app-kiosks"></a>Kioski z pojedynczą aplikacją

Podaj następujące ustawienia:

- **Konto użytkownika**: Podaj lokalne (na urządzeniu) konto użytkownika lub dane logowanie konta usługi Azure AD skojarzonego z aplikacją kiosku. W przypadku kont przyłączonych do domeny usługi Azure AD podaj konto w formacie `domain\username@tenant.org`. 

    W przypadku kiosków w miejscach publicznych z włączonym automatycznym logowaniem należy użyć typu użytkownika z najniższymi uprawnieniami (na przykład lokalnego standardowego konta użytkownika). Aby skonfigurować konto usługi Azure Active Directory (AD) pod kątem trybu kiosku, użyj formatu `AzureAD\user@contoso.com`.

- **Identyfikator modelu użytkownika aplikacji (AUMID) aplikacji**: Wprowadź identyfikator AUMID aplikacji kiosku. Aby dowiedzieć się więcej, zobacz [Znajdowanie identyfikatora modelu użytkownika aplikacji zainstalowanej aplikacji](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

## <a name="reporting-and-telemetry"></a>Raportowanie i telemetria

- **Udostępnij dane użycia**: Wybierz poziom przesyłania danych diagnostycznych.
