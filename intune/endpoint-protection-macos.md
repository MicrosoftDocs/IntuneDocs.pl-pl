---
title: Dodawanie programu Endpoint Protection w systemie macOS w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Na urządzeniach z systemem macOS użyj programu Gatekeeper, aby określić, gdzie można instalować aplikacje (z uwzględnieniem sklepu Mac App Store). Ponadto włącz lub skonfiguruj zaporę, aby zezwolić na wybrane aplikacje, zablokować wybrane aplikacje, użyć trybu ukrywania, a nawet zablokować wybrane typy połączeń przychodzących przy użyciu usługi Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/25/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1fe22291c808c498f9c099498b97e131ea531334
ms.sourcegitcommit: 2bce5e43956b6a5244a518caa618f97f93b4f727
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 07/24/2019
ms.locfileid: "68467415"
---
# <a name="macos-endpoint-protection-settings-in-intune"></a>Ustawienia programu Endpoint Protection w usłudze Intune dla systemu MacOS  

W tym artykule opisano ustawienia programu Endpoint Protection, które można skonfigurować dla urządzeń z systemem macOS. Te ustawienia można skonfigurować przy użyciu profilu konfiguracji urządzenia macOS dla programu [Endpoint Protection](endpoint-protection-configure.md) w usłudze Intune.  

## <a name="gatekeeper"></a>Program Gatekeeper  

- **Zezwalaj na aplikacje pobrane z tych lokalizacji**  
  Ogranicz liczbę aplikacji, które można uruchomić na urządzeniu, w zależności od tego, skąd zostały pobrane aplikacje. Celem jest ochrona urządzeń przed złośliwym oprogramowaniem oraz zezwalanie na aplikacje tylko z zaufanych źródeł.  

  - **Nieskonfigurowany**  
  - **Mac App Store**  
  - **Mac App Store i zidentyfikowani deweloperzy**  
  - **Dowolne miejsce**  

  **Domyślnie**: Nie skonfigurowano  

- **Użytkownik może zastąpić strażnika**  
  Zapobiega zastępowaniu ustawień programu Gatekeeper przez użytkowników, a także uniemożliwia użytkownikom stosowanie kombinacji Control + kliknięcie w celu instalacji aplikacji. Po włączeniu ustawienia użytkownicy mogą użyć kombinacji Control + kliknięcie na dowolnej aplikacji i zainstalować ją.  
 
  - **Nie skonfigurowano** — użytkownicy mogą sterować kliknięciem w celu zainstalowania aplikacji.  
  - **Blokuj** — uniemożliwia użytkownikom korzystanie z funkcji kontroli — kliknij, aby zainstalować aplikacje.  

  **Domyślnie**: Nie skonfigurowano  

## <a name="firewall"></a>Zapora  

Użyj zapory, aby blokować połączenia według poszczególnych aplikacji, a nie według portów. Użycie ustawień dla poszczególnych aplikacji umożliwia łatwiejsze uzyskanie korzyści z ochrony za pomocą zapory. Ponadto takie rozwiązanie pomaga zapobiegać przejmowaniu przez niepożądane aplikacje portów sieciowych, które są otwarte dla aplikacji dozwolonych.  

**Ogólne**
- **Zapora**  
  Włącz zaporę, aby skonfigurować obsługę połączeń przychodzących w danym środowisku.  
  - **Nieskonfigurowany**  
  - **Włączenie**  

  **Domyślnie**: Nie skonfigurowano  

- **Połączenia przychodzące**  
  Blokuj wszystkie połączenia przychodzące poza połączeniami wymaganymi dla podstawowych usług internetowych, np. DHCP, Bonjour i IPSec. Ta funkcja blokuje również wszystkie usługi udostępniania, takie jak Udostępnianie plików czy Udostępnianie ekranu. Jeśli używasz usług udostępniania, zachowaj to ustawienie jako *Nieskonfigurowane*.  
  - **Nieskonfigurowany**  
  - **Zablokuj**  

  **Domyślnie**: Nie skonfigurowano  

**Zezwalanie lub blokowanie połączeń przychodzących dla określonych aplikacji.**  

  - **Aplikacje dozwolone**  
    Wybierz aplikacje, które są jawnie dozwolone do odbierania połączeń przychodzących.  

  - **Aplikacje zablokowane**  
    Wybierz aplikacje, które powinny blokować połączenia przychodzące.  

  - **Tryb niewidzialności**  
    Aby zapobiegać odpowiadaniu przez komputer na żądania sondowania, włącz tryb niewidzialności. Urządzenie nadal odpowiada na przychodzące żądania w przypadku autoryzowanych aplikacji. Nieoczekiwane żądania, takie jak ICMP (ping), są ignorowane.  
    - **Nieskonfigurowany**  
    - **Włączenie**  

    **Domyślnie**: Nie skonfigurowano  

## <a name="filevault"></a>FileVault  
Aby uzyskać więcej informacji na temat ustawień Apple FileVault, zobacz [FDEFileVault](https://developer.apple.com/documentation/devicemanagement/fdefilevault) w zawartości dla deweloperów firmy Apple. 

- **FileVault**  
  Pełne szyfrowanie dysków można *włączyć* przy użyciu XTS-AES 128 z FileVault na urządzeniach z systemem macOS 10,13 lub nowszym.  
  - **Nieskonfigurowany**  
  - **Włączenie**  

  **Domyślnie**: Nie skonfigurowano  

  - **Typ klucza odzyskiwania**  
    Klucze *osobiste* odzyskiwania kluczy są tworzone dla urządzeń. Skonfiguruj następujące ustawienia dla klucza osobistego.  

    - **Lokalizacja osobistego klucza odzyskiwania** — Określ krótki komunikat dla użytkownika, który wyjaśnia, jak i gdzie można pobrać osobisty klucz odzyskiwania. Ten tekst zostanie wstawiony do komunikatu, który użytkownik widzi na ekranie logowania, gdy zostanie wyświetlony monit o wprowadzenie osobistego klucza odzyskiwania w przypadku zapomnienia hasła.  
      
    - **Obrót osobistego klucza odzyskiwania** — określ częstotliwość rotacji osobistego klucza odzyskiwania dla urządzenia. Można wybrać wartość domyślną **nieskonfigurowane** lub wartości z przenoszącą od **1** do **12** miesięcy.  

  - **Wyłącz monit o wylogowaniu**  
    Uniemożliwiaj użytkownikowi monitowanie o włączenie FileVault podczas wylogowywania się.  Po wybraniu opcji wyłączone monit o wylogowanie jest wyłączony, a zamiast tego użytkownik zostanie poproszony o zalogowanie się.  
    - **Nieskonfigurowany**  
    - **Wyłącz**  

    **Domyślnie**: Nie skonfigurowano  

  - **Liczba dozwolonych przypadków obejścia**  
  Ustaw, ile razy użytkownik może zignorować komunikaty o włączeniu FileVault przed FileVault będzie wymagane, aby użytkownik mógł się zalogować.  

    - **Nie skonfigurowano** — szyfrowanie na urządzeniu jest wymagane przed dodaniem kolejnego logowania.  
    - **1** do **10** — zezwala użytkownikowi na ignorowanie monitu od 1 do 10 razy przed wymaganiem szyfrowania na urządzeniu.  
    - **Bez limitu, zawsze Monituj** — użytkownik jest monitowany o włączenie FileVault, ale szyfrowanie nigdy nie jest wymagane.  
 
    **Domyślnie**: Nie skonfigurowano  


