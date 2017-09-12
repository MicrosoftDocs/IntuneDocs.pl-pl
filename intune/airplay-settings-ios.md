---
title: "Ustawienia funkcji AirPlay dla urządzeń z systemem iOS w usłudze Intune"
titlesuffix: Azure portal
description: "Dowiedz się, jak używać usługi Intune w celu umożliwienia automatycznego łączenia urządzeń z systemem iOS z urządzeniami zgodnymi z funkcją AirPlay."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 03ecd2de215ff5b825dc8240d0b4f1bb77891d46
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/09/2017
---
# <a name="intune-airplay-settings-for-ios-devices"></a>Ustawienia funkcji AirPlay dla urządzeń z systemem iOS w usłudze Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Omawiane ustawienia pozwalają połączyć zarządzane urządzenia z systemem iOS z urządzeniami zgodnymi z funkcją AirPlay (takimi jak Apple TV) w ramach sieci.
Daje to następujące możliwości:

- **Skonfiguruj listę urządzeń i haseł** — ta funkcja pozwala użytkownikom automatycznie łączyć się urządzeniami zgodnymi z funkcją AirPlay znajdującymi się w ich zasięgu. Podaj nazwy urządzeń zgodnych z funkcją AirPlay oraz ich hasła, aby użytkownicy nie musieli podawać tych danych, łącząc się z nimi.
- **Konfigurowanie dozwolonych miejsc docelowych** — skonfiguruj listę urządzeń AirPlay (według identyfikatora urządzenia). Użytkownicy końcowi mogą wyświetlić tylko te urządzenia, które znajdują się na liście; tylko z nimi mogą się także połączyć (dotyczy wyłącznie urządzeń nadzorowanych).

## <a name="get-started"></a>Wprowadzenie

1. W bloku **Funkcje urządzenia** wybierz pozycję **AirPlay**.
2. W bloku **AirPlay** wybierz co najmniej jedną z następujących czynności:

## <a name="configure-a-device-and-password-list"></a>Konfigurowanie listy urządzeń i haseł

1. W bloku **Hasła** wypełnij pola **Nazwa urządzenia** i **Hasło** urządzenia AirPlay, na przykład **Contoso Apple TV**.
2. Po wprowadzeniu szczegółowych danych urządzenia kliknij przycisk **Dodaj**. Urządzenie pojawi się na liście **Nazwa urządzenia**.
3. Kontynuuj dodawanie urządzeń. Gdy skończysz, wybierz przycisk **OK**.


## <a name="configure-allowed-destinations"></a>Konfigurowanie dozwolonych miejsc docelowych

1. W bloku **Dozwolone miejsca docelowe (tylko nadzorowane)** wypełnij pole **Identyfikator urządzenia** odnoszące się do urządzenia AirPlay, na przykład 52:46:CD:51:83:4C.
2. Po wprowadzeniu identyfikatora urządzenia kliknij przycisk **Dodaj**. Identyfikator pojawi się na liście **Identyfikator urządzenia**.
3. Kontynuuj dodawanie urządzeń. Gdy skończysz, wybierz przycisk **OK**.

Możesz również zaimportować urządzenia i hasła oraz dozwolone miejsca docelowe z pliku wartości rozdzielonych przecinkami (csv).


## <a name="next-steps"></a>Następne kroki

Teraz można przypisać profil urządzenia do wybranych grup. Aby uzyskać szczegółowe informacje, zobacz [Przypisywanie profilów urządzeń](device-profile-assign.md).

