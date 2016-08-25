---
title: "Wybieranie metody zarządzania urządzeniami | Microsoft Intune"
description: "Poznaj różne sposoby rejestrowania urządzeń i zarządzania nimi."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 770aad50-fd7a-4cf1-a793-f95fe47fc3f8
ms.reviewer: angrobe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c329bd08aaf72ae2acaa03dcb12c911d84b46b4e
ms.openlocfilehash: cfd9df3814d0d306a254a5566155a91ce5d0ca16


---

# Wybieranie metody zarządzania urządzeniami
Usługa Intune umożliwia zarządzanie różnymi urządzeniami po *zarejestrowaniu* ich w usłudze. Użytkownicy mogą następnie korzystać z *portalu firmy*, aby wykonywać szereg operacji, takich jak rejestrowanie swoich urządzeń, przeglądanie i instalowanie aplikacji, upewnianie się, że urządzenie jest zgodne z zasadami firmy, oraz kontaktowanie się z pomocą techniczną IT.

## Metody zarządzania urządzeniami przenośnymi
Usługa Intune umożliwia zarządzanie następującymi platformami urządzeń:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

> [!NOTE]
> Jeśli urządzenia z wersją systemu iOS starszą niż obsługiwana wersja zostały już zarejestrowane wcześniej, pozostaną one zarejestrowane. Sprawdź dokumentację, aby potwierdzić, że funkcja obsługuje daną wersję systemu iOS.

Usługa Intune umożliwia zarządzanie urządzeniami użytkowników, co jest określane jako model „Przynieś własne urządzenie” (BYOD, Bring Your Own Device). Pozwala ona również na zarządzanie urządzeniami należącymi do firmy, w tym scenariuszami, w których firmy przedstawiają użytkownikom listę urządzeń do wyboru. Ta strategia jest znana jako „Wybierz własne urządzenie” (CYOD, Choose Your Own Device).

### Rejestrowanie urządzeń do zarządzania
W przypadku systemów operacyjnych dla urządzeń przenośnych, takich jak iOS, Android i Windows Phone, zawsze musisz zarejestrować urządzenia. Sposób rejestrowania urządzeń zależy od potrzeb organizacji:

|Typ rejestracji|„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)|„Wybierz własne urządzenie” (CYOD, Choose Your Own Device)|Urządzenie udostępnione z kontem menedżera|Urządzenie udostępnione bez konta użytkownika|
|-------------------|--------|--------|--------------------------------------|----------------------------------------|
|**Opis**|Osobiste urządzenie zarejestrowane przy użyciu usługi Microsoft Intune|Urządzenie dla jednego użytkownika należące do firmy|Urządzenie należące do firmy, które jest zarządzane przy użyciu konta menedżera udostępnionego dla wielu użytkowników|Urządzenie bez użytkownika należące do firmy, z którego korzysta wielu użytkowników.|
|**Użytkownik urządzenia**|Właściciel|Przypisany użytkownik|Bez konta określonego użytkownika|Bez określonego użytkownika|
|**Użytkownik rejestrujący**|Właściciel|Administrator|Menedżer urządzeń|Dowolny użytkownik|
|**Użytkownik wyrejestrowujący**|Właściciel lub administrator|Platforma |Administrator lub użytkownik|Administrator lub użytkownik|
|**Użytkownik z uprawnieniami do resetowania**|Właściciel lub administrator|Administrator|Administrator|Administrator|

Aby uzyskać dodatkowe wskazówki, zobacz informacje dotyczące [rejestrowania urządzeń przenośnych](/intune/get-started/choose-how-to-enroll-devices1).

> [!NOTE]
> Aby uzyskać pełną listę możliwości dostępnych po zarejestrowaniu urządzeń, zobacz [Możliwości zarządzania urządzeniami przenośnymi](mobile-device-management-capabilities-in-microsoft-intune.md).

## Metody zarządzania komputerami z systemem Windows
Usługa Intune umożliwia zarządzanie komputerami z systemem Windows Vista i nowszymi wersjami systemu Windows za pomocą klienta komputerowego usługi Intune. Jednak w przypadku komputerów z systemem Windows możesz wybrać między ich zarejestrowaniem a zainstalowaniem oprogramowania klienckiego usługi Intune, które zawiera kilka funkcji niedostępnych w przypadku rejestrowania urządzeń. W większości przypadków będziesz rejestrować urządzenie z systemem Windows za pomocą usługi Intune, co zapewnia szerszy zestaw możliwości niż w przypadku klienta komputerowego.

Rozważ użycie klienta komputerowego usługi Intune, gdy chcesz:

- użyć dowolnej z funkcji dostępnych w kliencie komputerowym usługi Microsoft Intune do zarządzania komputerami z systemem Windows;
- zarządzać komputerem z systemem operacyjnym Windows, który nie jest obsługiwany w przypadku rejestracji.

> [!NOTE]
> Aby uzyskać pełną listę możliwości dostępnych po zainstalowaniu klienta komputerowego usługi Intune na komputerach z obsługiwanym systemem Windows, zobacz [Możliwości zarządzania komputerami z systemem Windows](windows-pc-management-capabilities-in-microsoft-intune.md).

## Zarządzanie przy użyciu programu Exchange ActiveSync
Urządzeniami możesz również zarządzać za pomocą programu Exchange ActiveSync. Wymaga to zainstalowania łącznika On-Premises Connector albo użycia wbudowanego łącznika Service to Service Connector w celu nawiązania połączenia z programem Exchange Server.

Aby dowiedzieć się więcej o wymaganiach dotyczących sprzętu i oprogramowania w przypadku instalowania łącznika On-Premises Connector, zobacz [Wymagania dotyczące łącznika On-Premises Connector](/intune/deploy-use/intune-on-premises-exchange-connector#requirements-for-the-on-premises-connector).

Aby dowiedzieć się więcej o używaniu łącznika On-Premises Connector lub łącznika Service to Service Connector z programem Exchange, zobacz [Zarządzanie urządzeniami przenośnymi za pomocą programu Exchange ActiveSync i usługi Microsoft Intune](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune).



## Następne kroki
Teraz już znasz niektóre możliwości dostępne po zarejestrowaniu urządzeń w usłudze [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. Następnie musisz [zarejestrować urządzenia](/intune/deploy-use/enroll-devices-in-microsoft-intune). Po zarejestrowaniu urządzeń możesz korzystać ze wszystkich możliwości, które zostały przedstawione w tym temacie. <!--lindavr: There's a logical flaw in our "get to know/get started" content. You can take the path in this topic or you can take the path in the What to know before your get started topic. And they don't cover the same ground. -->



<!--HONumber=Aug16_HO3-->


