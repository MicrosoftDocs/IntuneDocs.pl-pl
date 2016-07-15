---
title: "Rejestrowanie firmowych urządzeń z systemem iOS w usłudze Microsoft Intune | Microsoft Intune"
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2d3ca4ab-f20c-4d56-9413-f8ef19cf0722
ROBOTS: noindex,nofollow
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 779127bfd39145010f0d9b6609286aaf4dedfdc8
ms.openlocfilehash: 48359b44bec9ac3e1c9510debc01d2cf8abf6d2b


---

# Rejestrowanie firmowych urządzeń z systemem iOS w usłudze Microsoft Intune
Usługa Microsoft Intune obsługuje rejestrowanie firmowych urządzeń z systemem iOS w ramach programu Device Enrollment Program (DEP) firmy Apple lub przy użyciu programu [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) działającego na komputerze Mac.

Firmowe urządzenia z systemem iOS można zarejestrować na trzy sposoby:

-   **Rejestracja przy użyciu asystenta ustawień** — resetuje urządzenie do ustawień fabrycznych i przygotowuje je do konfiguracji przez nowego użytkownika urządzenia. Ta metoda wymaga od administratora podłączenia do komputera Mac z programem Apple Configurator urządzenia z systemem iOS za pośrednictwem portu USB w celu wstępnego skonfigurowania rejestracji. Następnie urządzenia są dostarczane do użytkowników, którzy uruchamiają proces Asystenta ustawień, konfigurują urządzenie za pomocą służbowych poświadczeń użytkownika i kończą proces rejestracji. [Rejestracja urządzeń z systemem iOS przy użyciu narzędzia Apple Configurator i Asystenta ustawień](ios-setup-assistant-enrollment-in-microsoft-intune.md)

-   **Rejestracja bezpośrednia** — tworzy plik zgodny z programem Apple Configurator do użytku podczas przygotowywania urządzenia. Zarejestrowane urządzenie nie jest resetowane do ustawień fabrycznych, ale nie ma określonej przynależności do użytkownika. Ta metoda wymaga od administratora podłączenia do komputera Mac z programem Apple Configurator urządzenia z systemem iOS za pośrednictwem portu USB w celu zarejestrowania urządzenia. [Rejestrowanie urządzeń z systemem iOS przy użyciu bezpośredniej rejestracji w programie Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md)

-   **Device Enrollment Program (DEP)** — wdraża profil rejestracji bez udziału użytkownika w urządzeniach zakupionych w programie Device Enrollment Program firmy Apple. Gdy użytkownik uruchomi Asystenta ustawień na urządzeniu, urządzenie zostanie zarejestrowane w usłudze Intune.  Urządzenia zarejestrowane w programie DEP nie mogą zostać wyrejestrowane przez użytkowników. [Rejestrowanie urządzeń z systemem iOS biorących udział w programie Device Enrollment Program](ios-device-enrollment-program-in-microsoft-intune.md)




### Zobacz także
[Przygotowanie do rejestracji urządzeń w usłudze Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Jun16_HO4-->


