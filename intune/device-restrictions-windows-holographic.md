---
title: "Ustawienia ograniczeń urządzeń z systemem Windows Holographic for Business w usłudze Microsoft Intune"
titleSuffix: 
description: "Informacje na temat ustawień usługi Intune służących do kontrolowania ustawień i funkcji na urządzeniach z systemem Windows Holographic for Business."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 3/6/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9acce571330a754de85b65caf8ec71912fd36a69
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/17/2018
---
# <a name="microsoft-intune-windows-holographic-for-business-device-restriction-settings"></a>Ustawienia ograniczeń urządzeń z systemem Windows Holographic for Business w usłudze Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

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

-   **Przeglądarka Microsoft Edge** — umożliwia korzystanie z przeglądarki Edge na urządzeniu.
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

## <a name="reporting-and-telemetry"></a>Raportowanie i telemetria

- **Udostępnij dane użycia** — wybierz poziom przesyłania danych diagnostycznych.