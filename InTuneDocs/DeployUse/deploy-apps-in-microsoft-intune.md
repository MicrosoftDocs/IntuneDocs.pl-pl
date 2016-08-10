---
title: "Wdrażanie aplikacji | Microsoft Intune"
description: "Informacje przedstawione w tym temacie ułatwiają wdrażanie aplikacji przy użyciu usługi Microsoft Intune."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b42019e-73da-4538-a496-212f11d5bf9b
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0c6f795031ec23ffe6f332b3510eea43d5fbdbcd
ms.openlocfilehash: 4c9f5b111fbd95f9e1c928cfaaa0c7ebf61dad2a

---
# Wdrażanie aplikacji w usłudze Microsoft Intune

Informacje przedstawione w tym temacie ułatwiają wdrażanie aplikacji przy użyciu usługi Microsoft Intune.


## Wdrażanie aplikacji
Poniżej przedstawiono procedurę wdrażania aplikacji w wybranych grupach urządzeń lub użytkowników.

### Aby wdrożyć aplikację

1. W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) kliknij pozycję **Aplikacje** &gt; **Aplikacje**, aby wyświetlić listę aplikacji, którymi zarządzasz.

2.  Wybierz aplikację, którą chcesz wdrożyć, a następnie kliknij pozycję **Zarządzaj wdrożeniem**.

3.  W oknie dialogowym *&lt;nazwa aplikacji&gt;* na stronie **Wybieranie grup** wybierz grupy użytkowników lub urządzeń, w których chcesz wdrożyć aplikację.

4.  Na stronie **Akcja wdrażania** skonfiguruj następujące ustawienia:

    - **Zatwierdzenie** — wybierz odpowiednie ustawienie wdrożenia:
        - **Wymagane** (instalacja obowiązkowa)
        - **Dostępne** (instalacja przeprowadzana na żądanie przez użytkownika w Portalu firmy)
        - **Nie dotyczy** (aplikacja nie jest zainstalowana lub wyświetlana w Portalu firmy)
        - **Odinstaluj** (aplikacja zostanie odinstalowana z urządzeń docelowych)
    - **Termin** — w przypadku wymaganych instalacji wybierz termin wdrożenia aplikacji. Możesz wybrać jedną ze wstępnie zdefiniowanych wartości lub wybrać pozycję **Niestandardowy**, aby skonfigurować własny termin.

5. Jeśli wdrażaną aplikację można skonfigurować przy użyciu zasad zarządzania aplikacjami mobilnymi, zostanie wyświetlona strona **Zarządzanie aplikacjami mobilnymi**. Na tej stronie możesz wybrać zasady zarządzania aplikacjami mobilnymi, które chcesz skojarzyć z tą aplikacją.

    [Sprawdź, które aplikacje firmy Microsoft są zgodne z zasadami zarządzania aplikacjami mobilnymi.](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx)

6. Jeśli wdrażana aplikacja jest zgodna z profilami sieci VPN w usłudze Intune, zostanie wyświetlona strona **Profil sieci VPN**. Na tej stronie możesz skojarzyć aplikacje systemu iOS z wdrożonym profilem sieci VPN. Połączenie sieci VPN jest automatycznie otwierane po uruchomieniu aplikacji. Aby udostępnić profil sieci VPN, musi on mieć włączone ustawienie profilu **Na aplikację sieci VPN**.
 Aby uzyskać informacje dotyczące sposobu konfigurowania profilów sieci VPN, w tym informacje na temat sposobu kojarzenia profilów z aplikacjami, zobacz [Połączenia VPN w usłudze Microsoft Intune](vpn-connections-in-microsoft-intune.md).

## Przykład

W tym przykładzie aplikacja została wdrożona na urządzeniu z systemem iOS przy użyciu ustawienia **Dostępne**.
Aplikacja jest wyświetlana na urządzeniach użytkowników w portalu firmy i użytkownicy mogą ją stamtąd zainstalować.

Na przykład na tym zrzucie ekranu pokazano aplikację Bing dla systemu iOS wdrożoną za pomocą typu instalacji **Link zewnętrzny** z ikoną niestandardową. Opcja **Wyświetlaj jako polecaną aplikację i wyróżnij w Portalu firmy** została wybrana.  
![iOS — aplikacja dostępna](./media/available-install-on-iOS.png)

Jeśli aplikacja została wdrożona na urządzeniu z systemem iOS przy użyciu ustawienia **Wymagane**, użytkownik otrzyma powiadomienie o tym, że aplikacja jest gotowa do zainstalowania. Na przykład na tym zrzucie ekranu pokazano aplikację Foldery robocze dla systemu iOS wdrożoną za pomocą typu instalacji **Zarządzana aplikacja systemu iOS ze sklepu App Store**.
![iOS — aplikacja wymagana](./media/iOS-Required-install.PNG)

## Następne kroki

Po wdrożeniu aplikacji możesz monitorować jej postęp. Aby uzyskać więcej informacji, zobacz [Monitorowanie aplikacji w usłudze Microsoft Intune](monitor-apps-in-microsoft-intune.md).



<!--HONumber=Jul16_HO5-->


