---
title: "Zarządzanie urządzeniami za pomocą programu Exchange ActiveSync | Microsoft Intune"
description: "Niezarejestrowanymi urządzeniami przenośnymi, których użytkownicy nie zarejestrowali w programie Exchange ActiveSync (EAS), możesz bezpośrednio zarządzać, używając programu Exchange Connector."
keywords: 
author: nathbarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 14f5cf53-6764-4e22-a18b-fa750b3acd41
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e9cbf5858cc4e860b540f421b6d463b8e7a429cf
ms.openlocfilehash: f545c7db4c29690a72c5a84dfcab6f179cbe72a2


---

# Zarządzanie urządzeniami przenośnymi za pomocą programu Exchange ActiveSync i usługi Microsoft Intune
Aby usługa Microsoft Intune mogła bezpośrednio zarządzać urządzeniami przenośnymi, użytkownicy muszą zarejestrować urządzenia w usłudze Intune. Dla urządzeń przenośnych, których użytkownicy nie zarejestrowali, możesz włączyć zarządzanie za pomocą programu Exchange ActiveSync (EAS), używając programu Exchange Connector. Urządzenia mogą być zarządzane za pomocą lokalnych serwerów programu Exchange, jak i hostowanego w chmurze programu Exchange w ramach usługi Microsoft Office 365.

## Reguły dostępu do programu Exchange dla urządzeń przenośnych ##

Program Exchange wymaga zestawu reguł, które definiują, co się dzieje, gdy urządzenia przenośne podejmują próby połączenia z programem EAS. Te reguły są zarządzane w konsoli administracyjnej usługi Intune.

[Reguły dostępu do programu Exchange dla urządzeń przenośnych](exchange-access-rules-for-mobile-devices.md)

## Instalowanie programu Exchange Connector
Program Exchange Connector umożliwia zarządzanie wdrożeniem programu Exchange w konsoli usługi Intune. Należy najpierw zainstalować i skonfigurować odpowiedni program Exchange z usługą Intune. Wybierz odpowiednią opcję na podstawie tego, czy serwer Exchange działa lokalnie lub jest hostowany jako usługa w chmurze:

-   [Instalowanie łącznika usługi Intune dla lokalnego programu Exchange](intune-on-premises-exchange-connector.md)
-   [Konfigurowanie łącznika Intune Service to Service dla hostowanego programu Exchange](intune-service-to-service-exchange-connector.md)

## Zastosowanie zasad dla urządzeń przenośnych zarządzanych przez program Exchange
Ustawienia zasad można stosować za pomocą konsoli usługi Intune. Aby uzyskać informacje na ten temat, zobacz [Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md). Listę ustawień zasad programu Exchange ActiveSync i funkcji obsługiwanych przez konkretne urządzenia przenośne zawiera [tabela porównawcza klientów programu Exchange ActiveSync](http://go.microsoft.com/fwlink/?LinkId=247270).

> [!NOTE]
> Po połączeniu usługi Intune ze środowiskiem programu Microsoft Exchange zasady programu EAS dotyczące wszystkich użytkowników zarządzanych za pomocą usługi Intune zostaną ustawione na bieżące zasady domyślne na serwerze Microsoft Exchange, chyba że w ramach usługi Intune są zdefiniowane bardziej szczegółowe zasady.

## Czyszczenie danych firmy z urządzeń przenośnych
Na koniec można [wyczyścić dane firmowe z urządzeń przenośnych zarządzanych przez program EAS](wipe-for-exchange-managed-mobile-devices.md), jeśli te urządzenia nie są już używane lub w przypadku utraty albo kradzieży urządzenia.



<!--HONumber=Jul16_HO4-->


