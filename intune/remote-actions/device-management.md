---
title: Zarządzanie urządzeniami za pomocą usługi Microsoft Intune — Azure | Microsoft Docs
description: Przeglądaj urządzenia zarządzane w usłudze Microsoft Intune, a także eksportuj listę urządzeń do formatu CSV, wyświetlaj urządzenia dołączone do usługi Azure Active Directory, sprawdzaj dziennik zmian akcji urządzenia, używaj łącznika usługi TeamViewer do umożliwiania zdalnego rozwiązywania problemów z urządzeniami z systemem Android przez administratorów IT oraz wyświetlaj wszystkie akcje, które można uruchomić na urządzeniach.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/19/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: cd1d99e0c3853a7bf607dd2f64046c503068566d
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71728627"
---
# <a name="what-is-microsoft-intune-device-management"></a>Co to jest zarządzanie urządzeniami w usłudze Microsoft Intune?

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Jako administrator IT musisz się upewnić, że zarządzane urządzenia udostępniają zasoby, których użytkownicy potrzebują do wykonania swojej pracy, a jednocześnie chronić te dane przed ryzykiem.

Obciążenie **Urządzenia** zapewnia wgląd w urządzenia zarządzane i umożliwia wykonywanie zadań zdalnych na tych urządzeniach.

## <a name="get-to-your-devices"></a>Przechodzenie do urządzeń

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Wybierz pozycję **Urządzenia**. Ten widok zapewnia szczegółowe informacje o poszczególnych urządzeniach oraz czynnościach, które można wobec nich wykonać, w tym:

   - **Omówienie** — wyświetla wizualną migawkę zarejestrowanych urządzeń oraz pokazuje, ile urządzeń korzysta z różnych platform, w tym systemu Android, iOS i innych.
   - **Wszystkie urządzenia** — wyświetla listę zarejestrowanych urządzeń, którymi zarządzasz.

     Funkcja **Eksportuj** umożliwia utworzenie pliku CSV z listą wszystkich urządzeń w przyrostach co 10 000 (Internet Explorer) lub 30 000 (Microsoft Edge, Chrome).

     Wybierz dowolne urządzenie, aby [wyświetlić dodatkowe szczegóły o tym urządzeniu](device-inventory.md), w tym szczegóły dotyczące sprzętu, zainstalowanych aplikacji, stanu zasad zgodności i innych informacji.

   - **Urządzenia w usłudze Azure AD** — wyświetla listę urządzeń zarejestrowanych w usłudze Azure Active Directory (Azure AD) lub dołączonych do tej usługi. Dowiedz się więcej o [zarządzaniu urządzeniami w usłudze Azure AD](https://docs.microsoft.com/azure/active-directory/device-management-introduction).
   - **Akcje urządzenia** — zawiera historię zdalnych akcji wykonywanych na różnych urządzeniach obejmującą informacje o każdej akcji, jej stanie, osobie inicjującej i czasie.

     ![Zrzut ekranu przedstawiający monitorowanie akcji urządzenia](./media/device-management/monitor-device-actions.png)

   - **Dzienniki inspekcji** — stanowią rekord działań, które generują zmiany w usłudze Intune. [Dzienniki inspekcji](../fundamentals/monitor-audit-logs.md) zawierają więcej szczegółowych informacji.
   - **Łącznik usługi TeamViewer** — usługa umożliwia użytkownikom urządzeń z systemem Android zarządzanych przez usługę Intune uzyskiwanie pomocy zdalnej od administratora IT. Dowiedz się więcej o programie [TeamViewer](teamviewer-support.md).
   - **Pomoc i obsługa techniczna** — zapewnia skrót do wskazówek związanych z rozwiązywaniem problemów, żądania pomocy technicznej oraz sprawdzania stanu usługi Intune.

## <a name="available-device-actions"></a>Dostępne akcje urządzenia
Dostępne akcje zależą od platformy urządzenia i jego konfiguracji.

- [Wyświetl spis urządzeń](device-inventory.md)
- Uruchom akcje zdalne urządzenia:
  - [Wycofaj](devices-wipe.md#retire)
  - [Czyszczenie danych](devices-wipe.md#wipe)
  - [Zdalne blokowanie](device-remote-lock.md)
  - [Zresetuj kod dostępu](device-passcode-reset.md)
  - [Obchodzenie blokady aktywacji](device-activation-lock-bypass.md) (tylko system iOS)
  - [Zaczynanie od początku](device-fresh-start.md) (tylko system Windows)
  - [Tryb zgubienia](device-lost-mode.md) (tylko system iOS)
  - [Lokalizowanie urządzenia](device-locate.md) (tylko system iOS)
  - [Ponowne uruchamianie](device-restart.md) (tylko system Windows)
  - [Resetowanie numeru PIN w systemie Windows 10](device-windows-pin-reset.md)
  - [Zdalne sterowanie dla systemu Android](teamviewer-support.md)
  - [Synchronizowanie urządzenia](device-sync.md)
  - [Wysyłanie powiadomień niestandardowych](custom-notifications.md#send-a-custom-notification-to-a-single-device) (Android, iOS)

## <a name="next-steps"></a>Następne kroki

- W obszarze **Wszystkie urządzenia** wybierz urządzenie, aby wyświetlić więcej szczegółów o tym konkretnym urządzeniu.
- Wybierz pozycję **Akcje urządzenia**, aby zobaczyć stan akcji podjętych na zarządzanych urządzeniach.
