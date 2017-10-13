---
title: "Wysyłanie dzienników z urządzeń z systemem Windows 10 do działu pomocy technicznej Twojej firmy | Dokumentacja firmy Microsoft"
description: "Rejestrowanie urządzenia z systemem Windows 10 (w wersji 1511) w usłudze Intune"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 05/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 038747fb-5b52-47c4-a2b6-f9218da4cfe1
searchScope: User help
ROBOTS: 
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 1e84bd13a58359f281ebfca3901d643dfc012d90
ms.sourcegitcommit: db7a7bbead3a3fa78c4d643607f709a2909eb608
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/28/2017
---
# <a name="send-logs-to-your-company-support-from-the-settings-app-for-windows-10"></a>Wysyłanie dzienników z aplikacji Ustawienia w systemie Windows 10 do działu pomocy technicznej Twojej firmy

Jeśli podczas korzystania z urządzenia z systemem Windows 10 zarządzanym przez firmę wystąpi błąd, możesz pomóc działowi pomocy technicznej Twojej firmy rozwiązać problem, wysyłając informacje pocztą e-mail. Te informacje są przechowywane na urządzeniu w specjalnym dokumencie nazywanym _dziennikiem diagnostycznym_.

1.  Otwórz aplikację **Ustawienia** systemu Windows, przechodząc do **menu Start** i wybierając przycisk **Ustawienia**. Możesz również wyszukać „ustawienia” na pasku wyszukiwania.
2.  Przejdź kolejno do pozycji **Konta** > **Uzyskaj dostęp do miejsca pracy lub nauki**.
3.  Wybierz pozycję „Eksportuj pliki dziennika zarządzania”.

  ![Zostanie wyświetlony ekran „Uzyskaj dostęp do miejsca pracy lub nauki” zawierający opcję Eksportuj pod nagłówkiem „Powiązane ustawienia”.](./media/w10-export-logs.png)

4. Dzienniki zostaną zapisane w lokalizacji **C:\Użytkownicy\Publiczne\Dokumenty publiczne\MDMDiagnostics**. Zostaną utworzone dwa pliki: jednym z nich będzie plik samego dziennika, a drugim będzie specjalny dokument, który umożliwi administratorowi przeglądanie dzienników w różnych programach (np. Microsoft Excel). Dołącz oba te pliki do wiadomości e-mail i wyślij ją administratorowi. Jeśli wykonasz te czynności więcej niż raz, po prostu wybierz pliki z dnia utworzenia dzienników. 

Być może trzeba będzie również wysłać [dzienniki z aplikacji Portal firmy](send-logs-to-your-it-admin-cp-windows.md), które jeszcze bardziej ułatwią działowi pomocy technicznej Twojej firmy rozwiązanie wszelkich napotkanych problemów. 

Nadal potrzebujesz pomocy? Skontaktuj się z pomocą techniczną Twojej firmy. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://portal.manage.microsoft.com).
