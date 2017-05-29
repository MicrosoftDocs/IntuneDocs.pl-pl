---
title: "Korzystanie z zasad w celu uproszczenia zarządzania komputerami z systemem Windows | Microsoft Docs"
description: "W artykule opisano zasady zarządzania komputerami z systemem Windows i ustawienia dla programu Microsoft Intune Center."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f0afda7e-f4c3-4bcd-b4bf-4304103cf73e
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: a2b956f8c999ec5489152a63a9af6e24da8ec536
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---

# <a name="use-policies-to-simplify-windows-pc-management"></a>Korzystanie z zasad w celu uproszczenia zarządzania komputerami z systemem Windows

Do zarządzania komputerami z systemem Windows jako komputerami osobistymi, uruchamiając na nich oprogramowanie klienckie usługi Intune, możesz używać tylko zasad **Zarządzanie komputerem** w konsoli administracyjnej usługi Intune. Wszystkie inne zasady wymienione w konsoli administracyjnej są przeznaczone tylko dla urządzeń przenośnych. Za pomocą zasad **Zarządzanie komputerem** możesz konfigurować ustawienia w programie Microsoft Intune Center, kontrolować aktualizacje dla komputerów osobistych i konfigurować Zaporę systemu Windows dla komputerów osobistych.

![Szablon zasad dla komputerów z systemem Windows](../media/pc_policy_template.png)

### <a name="manage-the-microsoft-intune-center"></a>Zarządzanie programem Microsoft Intune Center
Użytkownicy widzą klienta oprogramowania usługi Intune jako **Microsoft Intune Center**. Program Microsoft Intune Center umożliwia użytkownikom:

-   Pobieranie aplikacji z Portalu firmy.

-   Wyszukiwanie aktualizacji.

-   Zarządzanie programem Endpoint Protection usługi Microsoft Intune.

-  Wysyłanie żądań pomocy zdalnej.

Program Microsoft Intune Center jest instalowany na wszystkich zarządzanych komputerach. W zasadach usługi Intune można skonfigurować następujące ustawienia (są one widoczne dla użytkowników programu Microsoft Intune Center):

|Ustawienie zasad|Szczegóły|
|------------------|--------------------|
|**Nazwa**|Nazwa administratora, który zarządza komputerem.<br />Maksymalna długość: 40 znaków|
|**Numer telefonu**|Numer telefonu administratora, który zarządza komputerem.<br />Maksymalna długość: 20 znaków|
|**Adres e-mail**|Adres e-mail administratora, który zarządza komputerem.<br />Maksymalna długość: 40 znaków|
|**Nazwa witryny sieci Web**|Nazwa witryny sieci Web pomocy technicznej dla użytkowników.<br />>Maksymalna długość: 40 znaków|
|**Adres URL witryny sieci Web**|Adres URL witryny sieci Web pomocy technicznej.<br />Maksymalna długość: 150 znaków|
|**Uwagi**|Uwaga widoczna dla użytkowników.<br />Maksymalna długość: 120 znaków|

Zobacz następujące zasoby, aby uzyskać informacje o zasadach i ustawieniach, które można skonfigurować dla komputerów z systemem Windows:

- [Zapewnianie aktualności oprogramowania na komputerach z systemem Windows za pomocą aktualizacji w usłudze Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) — Te zasady wykonują wyszukiwanie i pobieranie aktualizacji oprogramowania od firmy Microsoft i innych firm dla komputerów zarządzanych. Aktualizacje te nie obejmują uaktualnień systemu operacyjnego (tzn. uaktualniania systemu Windows 7 do wersji Windows 10 i uaktualnień z jednej wersji systemu Windows 10 do nowszej wersji).

- [Zabezpieczanie komputerów z systemem Windows przy użyciu programu Endpoint Protection dla usługi Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md) — Te ustawienia obejmują harmonogramy skanowania i działań, jakie należy podjąć w razie wykrycia złośliwego oprogramowania.

- [Ochrona komputerów z systemem Windows przy użyciu zasad Zapory systemu Windows w usłudze Microsoft Intune](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) — Te zasady upraszczają administrację ustawień zapory systemu Windows na komputerach zarządzanych.


### <a name="see-also"></a>Zobacz także

[Typowe zadania związane z zarządzaniem komputerem z systemem Windows za pomocą klienta oprogramowania usługi Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)

