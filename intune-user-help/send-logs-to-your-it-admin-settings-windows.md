---
title: Wysyłanie dzienników z urządzeń z systemem Windows 10 do działu pomocy technicznej Twojej firmy | Dokumentacja firmy Microsoft
description: Rejestrowanie urządzenia z systemem Windows 10 (w wersji 1511) w usłudze Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 01/09/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 038747fb-5b52-47c4-a2b6-f9218da4cfe1
searchScope:
- User help
ROBOTS: ''
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3f8d1ff89f948715890eb9a31535e90b8787a856
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 03/14/2019
ms.locfileid: "55849864"
---
# <a name="send-logs-to-your-company-support-from-the-settings-app-for-windows-10"></a>Wysyłanie dzienników z aplikacji Ustawienia w systemie Windows 10 do działu pomocy technicznej Twojej firmy

Użyj aplikacji Ustawienia, aby rozwiązać problemy z aplikacją Portal firmy dla systemu Windows 10. Jeśli napotkasz problem podczas korzystania z aplikacji na urządzeniu z systemem Windows 10, możesz wysłać wiadomość e-mail do zespołu pomocy technicznej w celu uzyskania pomocy. Zdarzenia i błędy występujące w aplikacji Portal firmy są zapisywane na urządzeniu w specjalnym dokumencie o nazwie _dziennik diagnostyczny_. Mogą one zawierać dodatkowe informacje szczegółowe o błędzie, a po wyeksportowaniu są przydatne dla zespołów pomocy technicznej.

1. Aby otworzyć aplikację **Ustawienia**, przejdź do menu **Start** i wybierz pozycję **Ustawienia**. Możesz również wyszukać ciąg *ustawienia* na pasku wyszukiwania.
2. Przejdź kolejno do pozycji **Konta** > **Uzyskaj dostęp do miejsca pracy lub nauki**.
3. Wybierz pozycję **Eksportuj pliki dziennika zarządzania**.

   ![Zostanie wyświetlony ekran „Uzyskaj dostęp do miejsca pracy lub nauki” zawierający opcję Eksportuj pod nagłówkiem „Powiązane ustawienia”.](./media/w10-export-logs.png)

4. Dzienniki zostaną zapisane w lokalizacji **C:\Użytkownicy\Publiczne\Dokumenty publiczne\MDMDiagnostics**. Zostaną utworzone dwa pliki: jednym z nich będzie plik samego dziennika, a drugim będzie specjalny dokument, który umożliwi administratorowi przeglądanie dzienników w różnych programach (np. Microsoft Excel). Dołącz oba te pliki do wiadomości e-mail i wyślij ją administratorowi. Jeśli wykonasz te czynności więcej niż raz, po prostu wybierz pliki z dnia utworzenia dzienników. 

Być może trzeba będzie również wysłać [dzienniki z aplikacji Portal firmy](send-logs-to-your-it-admin-cp-windows.md), które jeszcze bardziej ułatwią działowi pomocy technicznej Twojej firmy rozwiązanie wszelkich napotkanych problemów. 

Nadal potrzebujesz pomocy? Skontaktuj się z pomocą techniczną Twojej firmy. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).
