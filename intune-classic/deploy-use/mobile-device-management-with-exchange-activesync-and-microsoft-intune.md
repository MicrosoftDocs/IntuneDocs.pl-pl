---
title: Zarządzanie urządzeniami za pomocą programu Exchange ActiveSync
description: Zarządzanie urządzeniami przenośnymi za pomocą programu Exchange ActiveSync (EAS) przy użyciu programu Exchange Connector
keywords: ''
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 14f5cf53-6764-4e22-a18b-fa750b3acd41
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f5e9bd3dd2026096c323858fc7faa915895ed55d
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="exchange-activesync-mobile-device-management-with-microsoft-intune"></a>Zarządzanie urządzeniami przenośnymi za pomocą programu Exchange ActiveSync i usługi Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Aby usługa Microsoft Intune mogła bezpośrednio zarządzać urządzeniami przenośnymi, urządzenia muszą być [zarejestrowane w usłudze Intune](prerequisites-for-enrollment.md). Administratorzy mogą również włączyć bardziej ograniczone rozwiązanie do zarządzania, umożliwiające zarządzanie urządzeniami za pomocą programu Exchange ActiveSync (EAS) przy użyciu programu Exchange Connector. Urządzenia mogą być zarządzane za pomocą lokalnych serwerów programu Exchange lub usługi Exchange Online w ramach usługi Office 365. Usługa Intune obsługuje tylko jedno połączenie programu Exchange Connector dowolnego typu na subskrypcję.

## <a name="exchange-access-rules-for-mobile-devices"></a>Reguły dostępu do programu Exchange dla urządzeń przenośnych ##

Program Exchange wymaga zestawu reguł, które definiują, co się dzieje, gdy urządzenia przenośne podejmują próby połączenia z programem EAS. Te reguły są zarządzane w konsoli administracyjnej usługi Intune.

[Reguły dostępu do programu Exchange dla urządzeń przenośnych](exchange-access-rules-for-mobile-devices.md)

## <a name="install-the-exchange-connector"></a>Instalowanie programu Exchange Connector
Program Exchange Connector umożliwia zarządzanie wdrożeniem programu Exchange w konsoli usługi Intune. Należy najpierw zainstalować i skonfigurować odpowiedni program Exchange z usługą Intune. Wybierz odpowiednią opcję na podstawie tego, czy serwer Exchange działa lokalnie, czy jest hostowany jako usługa w chmurze:

-   [Konfigurowanie usługi Intune dla usługi Exchange Online lub nowych wersji środowiska usługi Exchange Online w wersji dedykowanej](intune-service-to-service-exchange-connector.md)
-   [Instalowanie łącznika usługi Intune dla lokalnych serwerów programu Exchange i starszych wersji środowiska usługi Exchange Online w wersji dedykowanej](intune-on-premises-exchange-connector.md)


## <a name="apply-policy-for-exchange-managed-mobile-devices"></a>Zastosowanie zasad dla urządzeń przenośnych zarządzanych przez program Exchange
Za pomocą konsoli usługi Intune można zarządzać [ustawieniami zasad programu EAS](exchange-activesync-policy-settings-in-microsoft-intune.md) i [ograniczyć dostęp do zasobów firmy](restrict-access-to-email-and-o365-services-with-microsoft-intune.md). Listę ustawień zasad programu Exchange ActiveSync i funkcji obsługiwanych przez konkretne urządzenia przenośne zawiera [tabela porównawcza klientów programu Exchange ActiveSync](http://go.microsoft.com/fwlink/?LinkId=247270).

> [!NOTE]
> Po połączeniu usługi Intune ze środowiskiem programu Microsoft Exchange zasady programu EAS dotyczące wszystkich użytkowników zarządzanych za pomocą usługi Intune zostaną ustawione na bieżące zasady domyślne na serwerze Microsoft Exchange, chyba że w ramach usługi Intune są zdefiniowane bardziej szczegółowe zasady.

## <a name="wipe-company-data-from-mobile-devices"></a>Czyszczenie danych firmy z urządzeń przenośnych
Na koniec można [wyczyścić dane firmowe z urządzeń przenośnych zarządzanych przez program EAS](wipe-for-exchange-managed-mobile-devices.md), jeśli te urządzenia nie są już używane lub w przypadku utraty albo kradzieży urządzenia.
