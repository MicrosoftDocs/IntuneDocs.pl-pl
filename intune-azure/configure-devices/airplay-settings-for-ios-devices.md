---
title: "Ustawienia funkcji AirPlay dla urządzeń z systemem iOS w usłudze Intune"
titleSuffix: Intune Azure preview
description: "Dowiedz się, jak używać usługi Intune w celu umożliwienia automatycznego łączenia urządzeń z systemem iOS z urządzeniami zgodnymi z funkcją AirPlay."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: f1f7aa6a0b441b51f20d104c4353a1542a9e01ad
ms.lasthandoff: 04/19/2017


---

# <a name="intune-airplay-settings-for-ios-devices"></a>Ustawienia funkcji AirPlay dla urządzeń z systemem iOS w usłudze Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Omawiane ustawienia pozwalają połączyć zarządzane urządzenia z systemem iOS z urządzeniami zgodnymi z funkcją AirPlay (takimi jak Apple TV) w ramach sieci.
Daje to następujące możliwości:

- **Konfigurowanie listy urządzeń i haseł** — dostarcz urządzeniom nazwy i hasła urządzeń AirPlay, aby umożliwić im automatyczne nawiązywanie połączenia, gdy znajdą się w zasięgu. Jeśli podasz hasło, użytkownicy końcowi nie będą musieli podawać go, chcąc nawiązać połączenie.
- **Konfigurowanie dozwolonych miejsc docelowych** — skonfiguruj listę urządzeń AirPlay (według identyfikatora urządzenia). Użytkownicy końcowi będą mieć możliwość wyświetlenia tylko tych urządzeń, które znajdują się na liście; tylko z nimi będą się mogli także połączyć (dotyczy wyłącznie urządzeń nadzorowanych).

## <a name="get-started"></a>Wprowadzenie

1. W bloku **Funkcje urządzenia** wybierz pozycję **AirPlay**.
2. W bloku **AirPlay** wybierz co najmniej jedną z następujących czynności:

## <a name="configure-a-device-and-password-list"></a>Konfigurowanie listy urządzeń i haseł

1. W bloku **Hasła** wypełnij pola **Nazwa urządzenia** i **Hasło** urządzenia Airplay, na przykład **Contoso Apple TV**.
2. Po wprowadzeniu szczegółowych danych urządzenia kliknij przycisk **Dodaj**. Urządzenie pojawi się na liście **Nazwa urządzenia**.
3. Kontynuuj dodawanie urządzeń. Gdy skończysz, wybierz przycisk **OK**.


## <a name="configure-allowed-destinations"></a>Konfigurowanie dozwolonych miejsc docelowych

1. W bloku **Dozwolone miejsca docelowe (tylko nadzorowane)* wypełnij pole **Identyfikator urządzenia** odnoszące się do urządzenia AirPlay, na przykład 52:46:CD:51:83:4C.
2. Po wprowadzeniu identyfikatora urządzenia kliknij przycisk **Dodaj**. Identyfikator pojawi się na liście **Identyfikator urządzenia**.
3. Kontynuuj dodawanie urządzeń. Gdy skończysz, wybierz przycisk **OK**.

Możesz również zaimportować urządzenia i hasła oraz dozwolone miejsca docelowe z pliku wartości rozdzielonych przecinkami (csv).



