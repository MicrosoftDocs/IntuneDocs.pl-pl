---
title: Ograniczenia urządzeń dotyczące systemu Windows Holographic for Business w usłudze Microsoft Intune na platformie Azure | Microsoft Docs
description: Przeczytaj informacje i skonfiguruj ustawienia ograniczeń urządzeń w usłudze Microsoft Intune dla systemu Windows Holographic for Business, w tym wyrejestrowanie, geolokalizację, hasła, instalowanie aplikacji ze sklepu z aplikacjami, pliki cookie i menu podręczne w programie Edge, usługę Windows Defender, wyszukiwanie, chmurę i magazyn, łączność Bluetooth, czas systemowy i dane użycia na platformie Azure.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9d7f54ce0e288025a4a7f0f45bf5b10de5323021
ms.sourcegitcommit: e8e8164586508f94704a09c2e27950fe6ff184c3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2018
ms.locfileid: "39321758"
---
# <a name="device-restriction-settings-for-windows-holographic-for-business-in-intune"></a>Ustawienia ograniczeń urządzeń dla systemu Windows Holographic for Business w usłudze Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Następujące ustawienia ograniczeń urządzenia są obsługiwane na urządzeniach z systemem Windows Holographic for Business, takich jak Microsoft Hololens.

## <a name="general"></a>Ogólne

- **Ręczne wyrejestrowanie**— umożliwia użytkownikowi ręczne usunięcie konta firmowego z urządzenia.
- **Cortana** — włącza lub wyłącza asystenta głosowego Cortana.
- **Geolokalizacja** — określa, czy urządzenie może używać informacji z usług lokalizacyjnych.

## <a name="password"></a>Hasło
-   **Hasło** — wymaga od użytkownika końcowego wprowadzenia hasła w celu uzyskania dostępu do urządzenia.
    -   **Wymagaj hasła przy powrocie urządzenia ze stanu bezczynności** — określa, że użytkownik musi wprowadzić hasło, aby odblokować urządzenie.

## <a name="app-store"></a>App Store

-   **Automatycznie aktualizuj aplikacje ze sklepu** — umożliwia automatyczne aktualizowanie zainstalowanych aplikacji pochodzących ze Sklepu Microsoft.
-   **Instalacja aplikacji zaufanej** — umożliwia ładowanie bezpośrednie aplikacji podpisanych za pomocą zaufanego certyfikatu.
-   **Odblokowanie trybu deweloperskiego** — umożliwia korzystanie z ustawień trybu deweloperskiego systemu Windows, np. z ustawienia umożliwiającego użytkownikowi końcowemu modyfikację aplikacji ładowanych bezpośrednio.

## <a name="edge-browser"></a>Przeglądarka Microsoft Edge

-   **Pliki cookie** — umożliwia przeglądarce na urządzeniu zapisywanie plików cookie z Internetu.
-   **Wyskakujące okienka** — umożliwia blokowanie wyskakujących okienek w przeglądarce (tylko system Windows 10 Desktop).
-   **Sugestie wyszukiwania** — umożliwia sugerowanie witryn przez wyszukiwarkę podczas wpisywania wyszukiwanych fraz.
-   **Menedżer haseł** — włącza lub wyłącza funkcję menedżera haseł w przeglądarce Microsoft Edge.
- **Wysyłaj nagłówki Nie śledź** — umożliwia skonfigurowanie przeglądarki Microsoft Edge do wysyłania nagłówków „Nie śledź” do witryn sieci Web odwiedzanych przez użytkowników.

## <a name="windows-defender-smart-screen"></a>Windows Defender SmartScreen

- **Filtr SmartScreen dla przeglądarki Microsoft Edge** — włącz filtr SmartScreen dla przeglądarki Edge używany podczas uzyskiwania dostępu do witryn i pobierania plików.

## <a name="search"></a>Wyszukaj
- **Lokalizacja wyszukiwania** — określ, czy podczas wyszukiwania mogą być używane informacje o lokalizacji.

## <a name="cloud-and-storage"></a>Chmura i magazyn
-   **Konto Microsoft** — umożliwia użytkownikowi skojarzenie konta Microsoft z urządzeniem.

## <a name="cellular-and-connectivity"></a>Sieć komórkowa i łączność

-   **Bluetooth** — określa, czy użytkownik może włączyć i skonfigurować na urządzeniu połączenie Bluetooth.
-   **Odnajdowanie Bluetooth** — umożliwia wykrycie urządzenia przez inne urządzenia obsługujące technologię Bluetooth.
-   **Rozgłaszanie Bluetooth** — umożliwia odbieranie reklam przez urządzenie za pośrednictwem połączenia Bluetooth.

## <a name="control-panel-and-settings"></a>Panel sterowania i Ustawienia

- **Modyfikowanie czasu systemowego** — uniemożliwia użytkownikowi końcowemu zmianę daty i godziny na urządzeniu.

## <a name="kiosk---obsolete"></a>Kiosk — przestarzałe

Te ustawienia są przeznaczone tylko do odczytu i nie można ich zmienić. Aby skonfigurować tryb kiosku, zobacz [Ustawienia kiosku](kiosk-settings.md#windows-holographic-for-business).

Na kiosku jest zazwyczaj uruchamiana konkretna aplikacja. Użytkownicy nie mogą uzyskać na urządzeniu dostępu do funkcjonalności lub funkcji spoza aplikacji kiosku.

- **Tryb kiosku** — wskazuje typ trybu kiosku obsługiwany przez zasady. Dostępne opcje:

  - **Nieskonfigurowane** (domyślne) — zasady nie umożliwiają trybu kiosku. 
  - **Kiosk z pojedynczą aplikacją** — profil umożliwia uruchamianie tylko jednej aplikacji na urządzeniu. Gdy użytkownik zaloguje się, jest uruchamiana konkretna aplikacja. Ten tryb uniemożliwia także użytkownikowi otwieranie nowych aplikacji oraz zmianę uruchomionej aplikacji.
  - **Kiosk z wieloma aplikacjami** — profil umożliwia uruchamianie wielu aplikacji na urządzeniu. Tylko dodane aplikacje są dostępne dla użytkownika. Korzyści z kiosku z wieloma aplikacjami (czyli urządzenia o stałym przeznaczeniu) polegają na udostępnieniu użytkownikom łatwego do poznania środowiska, w którym są dostępne tylko potrzebne im aplikacje. Aplikacje, których użytkownicy nie potrzebują, są ukryte. 
  
    Dodając aplikacje do środowiska kiosku z wieloma aplikacjami, dodajesz również plik układu menu Start. Temat [Start menu layout file (Plik układu menu Start)](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-file-for-intune) zawiera przykładowy kod XML, którego można użyć w usłudze Intune. 

#### <a name="single-app-kiosks"></a>Kioski z pojedynczą aplikacją
Podaj następujące ustawienia:

- **Konto użytkownika** — podaj lokalne (na urządzeniu) konto użytkownika lub dane logowanie konta usługi Azure AD skojarzonego z aplikacją kiosku. W przypadku kont przyłączonych do domeny usługi Azure AD podaj konto w formacie `domain\username@tenant.org`. 

    W przypadku kiosków w miejscach publicznych z włączonym automatycznym logowaniem należy użyć typu użytkownika z najniższymi uprawnieniami (na przykład lokalnego standardowego konta użytkownika). Aby skonfigurować konto usługi Azure Active Directory (AD) pod kątem trybu kiosku, użyj formatu `AzureAD\user@contoso.com`.

- **Identyfikator modelu użytkownika aplikacji (AUMID) aplikacji** — podaj identyfikator modelu użytkownika aplikacji (AUMID) dla aplikacji kiosku. Aby dowiedzieć się więcej, zobacz [Znajdowanie identyfikatora modelu użytkownika aplikacji zainstalowanej aplikacji](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

## <a name="reporting-and-telemetry"></a>Raportowanie i telemetria

- **Udostępnij dane użycia** — wybierz poziom przesyłania danych diagnostycznych.
