---
title: Rozwiązywanie problemów z aktualizacjami oprogramowania w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Rozwiązywanie problemów z aktualizacjami oprogramowania w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/29/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: d17b70f4-17b4-4d89-88fd-70fa4f34fbea
ROBOTS: ''
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8ad8d904f72df169eea136c625a2f44d645cafbc
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72509758"
---
# <a name="troubleshoot-software-updates-in-microsoft-intune"></a>Rozwiązywanie problemów z aktualizacjami oprogramowania w usłudze Microsoft Intune

Rozwiązywanie problemów z aktualizacjami oprogramowania w usłudze Microsoft Intune. Aby wyświetlić listę kodów i opisów błędów, przejdź do artykułu [Kody błędów agenta aktualizacji oprogramowania wraz z opisami w usłudze Microsoft Intune](../protect/software-update-agent-error-codes.md).

## <a name="windows-7-devices-with-many-superseded-updates-stop-reporting-to-intune"></a>Urządzenia z systemem Windows 7, na których wiele aktualizacji zostało zastąpionych, przestają zgłaszać się w usłudze Intune

Na klientach usługi Microsoft Intune może występować co najmniej jeden z następujących objawów:

- Urządzenia nagle przestają zgłaszać się w usłudze Intune.  
- Na urządzeniach dochodzi do wysokiego wykorzystania procesora CPU.
- Aplikacje instalowane za pośrednictwem usługi Intune instalują się powolnie.
- W programie Microsoft Intune Center wyświetla się następujący błąd: `An error occurred while updating your computer. Error found: Code 0x800705b4`.
- W obszarze Konsola administracyjna usługi Intune > Grupy > Wszystkie urządzenia > Stan wyświetla się następujący błąd: `One or more agents that are installed on this computer have errors. The information for this computer may not be accurate or up-to-date.`

Ten problem może wystąpić, jeśli zastąpione aktualizacje (czyli aktualizacje, które zostały zastąpione przez inne aktualizacje) nie były odrzucane od dłuższego czasu. Podczas niektórych procesów (np. instalowania aplikacji) system Windows sprawdza kolejno wszystkie zastąpione aktualizacje, aby aktualizacje i ich zdarzenia następujące były prawidłowo mapowane. Jeśli lista zastąpionych aktualizacji zbytnio się rozrośnie, zadanie sprawdzania może powodować wysokie wykorzystanie procesora CPU w wyniku obciążenia związanego z przetwarzaniem i wymaganego czasu. Ten problem dotyczy głównie urządzeń z systemem Windows 7 ze względu na dużą liczbę dostępnych dla niego zastąpionych aktualizacji. W nowszych systemach operacyjnych liczba zastąpionych aktualizacji nie jest tak duża, więc ten problem może w nich nie występować.

**Rozwiązanie**

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz pozycję **Aktualizacje oprogramowania**.
3. Odrzuć wszystkie zastąpione aktualizacje systemu Windows 7 lub aplikacji (np. pakietu Microsoft Office) zainstalowanych na komputerach, których dotyczy problem.
4. Uruchom ponownie klientów, których dotyczy problem.

Jeśli używasz systemu Windows 7, upewnij się, że zainstalowana jest następująca aktualizacja: [3050265 Klient usługi Windows Update dla systemu Windows 7: czerwiec 2015 r.](https://support.microsoft.com/kb/3050265)

## <a name="next-steps"></a>Następne kroki

Uzyskaj [pomoc techniczną od firmy Microsoft](get-support.md) lub skorzystaj z [forum społeczności](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).