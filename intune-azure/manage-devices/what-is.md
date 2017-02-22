---
title: "Zarządzanie urządzeniami w usłudze Intune | Wersja zapoznawcza usługi Intune Azure | Dokumentacja firmy Microsoft"
description: "Wersja zapoznawcza usługi Intune Azure: dowiedz się, jak wyświetlać urządzenia zarządzane za pomocą usługi Intune i wykonywać na nich różne operacje."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/06/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 040c4e18d87110ab7380a64540d08127574a7c46
ms.openlocfilehash: 5a967cc1be387f83f95591186f786db61d3debcd


---

# <a name="what-is-device-management"></a>Co to jest zarządzanie urządzeniami? 


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Obciążenie **Urządzenia i grupy** zapewnia wgląd w urządzenia zarządzane i umożliwia wykonywanie zadań zdalnych na tych urządzeniach. Aby uzyskać dostęp do obciążenia:

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Urządzenia i grupy**.

    ![Obciążenie Urządzenia i grupy](./media/devices-and-groups-workload.png)

Wybierz jedną z następujących opcji:

- **Przegląd** Pobranie informacji o zarejestrowanych urządzeniach i systemach operacyjnych działających na każdym z nich.
- **Zarządzanie** — opcja **Wszystkie urządzenia** umożliwia wyświetlenie listy wszystkich zarządzanych urządzeń.
    Wybierz jedno z urządzeń na liście, aby otworzyć blok <*nazwa urządzenia*> **Przegląd**, w którym można wybrać jedną z opcji:
    - **Przegląd** — zobacz ogólne informacje dotyczące urządzenia, w tym informacje o jego nazwie, właścicielu, czy jest to urządzenie BYOD, kiedy ostatnio zostało zewidencjonowane itd. Ponadto można wykonać następujące akcje zdalne na urządzeniu (nie wszystkie akcje są obsługiwane przez wszystkie platformy urządzeń):
        - **Usuń dane firmy** — usuwa tylko dane firmy zarządzane przez usługę Intune. Nie usuwa z urządzenia danych osobistych. Urządzenie nie będzie już zarządzane przez usługę Intune i nie będzie mogło uzyskać dostępu do zasobów firmy (nieobsługiwane w przypadku urządzeń z systemem Windows, które są połączone z usługą Azure Active Directory).
        - **Resetowanie do ustawień fabrycznych** — przywraca na urządzeniu ustawienia domyślne. Urządzenie nie będzie już zarządzane przez usługę Intune i zarówno dane firmy, jak i dane osobiste są usuwane. Nie można cofnąć tej akcji.
        - **Zdalne blokowanie** — blokuje urządzenie. W celu odblokowania urządzenia jego właściciel musi użyć swojego kodu dostępu. Można zdalnie zablokować tylko urządzenie, które ma ustawiony numer PIN lub hasło.
        - **Resetowanie kodu dostępu** — generuje nowy kod dostępu urządzenia, które będzie wyświetlane w bloku <*nazwa urządzenia*> **przegląd**.
        - **Zastosuj obejście blokady aktywacji** — powoduje usunięcie blokady aktywacji z urządzenia z systemem iOS bez identyfikatora Apple ID i hasła użytkownika. Po zastosowaniu obejścia blokady aktywacji urządzenie ponownie przejdzie w stan blokady aktywacji, gdy zostanie uruchomiona aplikacja Znajdź mój iPhone. Stosuj obejście blokady aktywacji tylko w sytuacji, gdy masz fizyczny dostęp do urządzenia.
        - **Tryb utraty** — w przypadku kradzieży urządzenia można włączyć tryb utraty. Dzięki niemu można określić komunikat i numer telefonu do wyświetlenia na ekranie blokady urządzenia.
        - **Uruchom ponownie** — powoduje ponowne uruchomienie urządzenia. Właściciel urządzenia nie jest automatycznie powiadamiany o ponownym uruchomieniu, dlatego ta akcja może doprowadzić do utraty wykonanej pracy.
        ![Przegląd urządzenia](http://i.imgur.com/4Rx4VXm.png)
        
    - **Sprzęt** — wyświetlenie szczegółowych informacji dotyczących urządzenia, w tym ilości wolnego miejsca, modelu i producenta oraz innych danych.
    ![Spis sprzętu zarządzanego urządzenia](./media/hardware-inventory.png)
    - **Wykryte aplikacje** — wyświetla listę wszystkich aplikacji, które zostały odnalezione na urządzeniu przez usługę Intune.
    ![Węzeł Wykryte aplikacje](./media/detected-applications.png)
- **Monitoruj** Wybranie opcji **Akcje urządzenia** umożliwia wyświetlenie listy akcji urządzenia, które mogły zostać wykonane na urządzeniach zarządzanych, oraz bieżącego stanu tych akcji.
![Monitoruj akcje urządzenia](./media/monitor-device-actions.png)



<!--HONumber=Feb17_HO1-->


