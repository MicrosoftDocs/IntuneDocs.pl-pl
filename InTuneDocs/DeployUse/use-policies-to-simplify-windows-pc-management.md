---
title: "Korzystanie z zasad w celu uproszczenia zarządzania komputerami z systemem Windows | Microsoft Intune"
description: "W artykule opisano zasady zarządzania komputerami z systemem Windows i ustawienia dla programu Microsoft Intune Center."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 10/04/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f0afda7e-f4c3-4bcd-b4bf-4304103cf73e
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f34810d4f2f556522d993bf6e8e120c30a03e24c
ms.openlocfilehash: 1c6800ea3fde39603478437de6da7200ecae5afb


---

# <a name="use-policies-to-simplify-windows-pc-management"></a>Korzystanie z zasad w celu uproszczenia zarządzania komputerami z systemem Windows

Komputery z systemem Windows z uruchomionym klientem oprogramowania usługi Intune może być zarządzany za pomocą zasad **Zarządzanie komputerem** usługi Intune. Użyj zasad **Zarządzanie komputerem** usługi Intune, aby skonfigurować ustawienia w programie Microsoft Intune Center umożliwiające kontrolowanie aktualizacji dla komputerów i konfigurowanie Zapory systemu Windows dla komputerów.

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



<!--HONumber=Nov16_HO4-->


