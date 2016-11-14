---
title: "Pojawia się monit o zainstalowanie aplikacji Lookout for Work na urządzeniu z systemem iOS | Microsoft Intune"
description: 
keywords: 
author: barlan
ms.author: barlan
manager: angrobe
ms.date: 10/17/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7adab655-8317-4512-ba7d-beeaa25bbf6c
ROBOTS: NOINDEX,NOFOLLOW
translationtype: Human Translation
ms.sourcegitcommit: 2edbb8a70458290e69626d85f734d38243a2002a
ms.openlocfilehash: 03eee971fe74b73983111549338b13bf4068a85c


---

# Pojawia się monit o zainstalowanie aplikacji Lookout for Work na urządzeniu z systemem iOS

Administrator IT wymaga, aby przed uzyskaniem dostępu do swoich dokumentów zainstalować aplikację Lookout for Work, która pomaga chronić urządzenie, wyszukując potencjalne zagrożenia bezpieczeństwa. W zależności od sposobu skonfigurowania aplikacji Lookout for Work przez administratora IT na urządzeniu mogą pojawiać się różne monity.

**Co należy zrobić:**

1.  Jeśli zobaczysz następujący monit, naciśnij pozycję **Zainstaluj**, aby umożliwić instalację aplikacji Lookout for Work na urządzeniu.

    ![Naciśnij pozycję Zainstaluj, aby zainstalować aplikację Lookout for Work](./media/ios-lfw-install-app-request.png)

2. Jeśli zobaczysz następujący komunikat, naciśnij pozycję **Ustawienia**, włącz opcję **Usługi lokalizacji**, a następnie naciśnij przycisk **Kontynuuj**.

    ![Naciśnij pozycję Ustawienia, a następnie opcję Usługi lokalizacji](./media/ios-lfw-allow-location-services.png)

3. Sprawdź uprawnienia, których wymaga aplikacja Lookout for Work, i naciśnij przycisk **Kontynuuj**.

    ![Masz teraz połączenie z aplikacją Lookout for Work](./media/ios-lfw-permissions-lookout-needs.png)

4. W monicie proszącym o zezwolenie aplikacji Lookout for Work na wysyłanie powiadomień naciśnij pozycję **Zezwalaj**.

    ![Naciśnij pozycję Ustawienia, a następnie opcję Usługi lokalizacji](./media/ios-lfw-allow-notifications.png)

    
Aplikacja Lookout for Work kończy instalację. Zobaczysz poniższy ekran, jeśli na urządzeniu nie zostaną znalezione zagrożenia bezpieczeństwa.

![Aplikacja Lookout for Work nie znalazła żadnych zagrożeń bezpieczeństwa](./media/ios-lfw-no-threats-found.png)

Jeśli aplikacja Lookout for Work znajdzie zagrożenie bezpieczeństwa urządzenia, zostaną wyświetlone instrukcje rozwiązania problemu.

**Jeśli instalacja nie działa**

Czasami instalacja może zakończyć się niepowodzeniem w związku z problemami technicznymi wykraczającymi poza Twoją kontrolę. Jeśli tak się stanie, skontaktuj się z administratorem IT. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](http://portal.manage.microsoft.com).




<!--HONumber=Oct16_HO3-->


