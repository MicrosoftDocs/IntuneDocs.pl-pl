---
title: Rozwiązywanie problemów z programem Endpoint Protection w usłudze Intune — Azure — | Microsoft Docs
description: Rozwiąż problem, używając programu Microsoft Intune Endpoint Protection.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e31df2d2-bb1b-491b-9a71-04e0b18829c1
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1de1722aa635367dac4b586e1333aed163156a83
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55836680"
---
# <a name="troubleshoot-endpoint-protection-in-intune"></a>Rozwiązywanie problemów z programem Endpoint Protection w usłudze Intune

Skorzystaj z informacji, aby rozwiązać problemy występujące podczas korzystania z programu Endpoint Protection. Możesz również [zapoznać się z dziennikami zdarzeń i kodami błędów, aby rozwiązywać problemy z programem antywirusowym Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus).

Jeśli te informacje nie pomogą w rozwiązaniu problemu, możesz również [uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](get-support.md).

### <a name="error-messages"></a>Komunikaty o błędach
W tej sekcji opisano możliwe przyczyny i potencjalne rozwiązania poniższych błędów i ostrzeżeń.

|Pozycja w okienku stanu|Możliwe przyczyny|Potencjalne rozwiązania|
|---------------|--------------------|-----------------------|
|**Aparat programu Endpoint Protection jest niedostępny**|Aparat programu Endpoint Protection w usłudze Intune uległ uszkodzeniu lub został usunięty.|Jeśli aparat programu Endpoint Protection w usłudze Intune jest uszkodzony, możesz spróbować zaktualizować lub ponownie zainstalować oprogramowanie.<br /><br />Aby wymusić natychmiastową aktualizację, wybierz pozycję **Aktualizuj** w oprogramowaniu klienckim programu Endpoint Protection (które można znaleźć na pasku zadań na zarządzanych komputerach).<br /><br />Jeśli nie można zaktualizować aparatu programu Endpoint Protection, trzeba ponownie zainstalować ten aparat.<br /><br />Na liście zainstalowanych programów w Panelu sterowania na zarządzanym komputerze odszukaj pozycję **Agent programu Endpoint Protection usługi Microsoft Intune**, a następnie odinstaluj tę aplikację.<br /><br />Podczas następnej synchronizacji aktualizacji Menedżer usługi Microsoft Online Management Update wykryje brakujący program i zainstaluje go ponownie o zaplanowanej godzinie instalacji.|
|**Program Endpoint Protection jest wyłączony**|Program Endpoint Protection w usłudze Intune został wyłączony przez administratora przy użyciu profilu konfiguracji lub przez użytkownika na zarządzanym komputerze.|Włącz program Endpoint Protection. Zobacz [Dodawanie ustawień programu Endpoint Protection](endpoint-protection-configure.md) w usłudze Intune lub [Włączanie usługi Windows Defender w celu uzyskiwania dostępu do zasobów firmy](/intune-user-help/turn-on-defender-windows).|
|**Ochrona w czasie rzeczywistym jest wyłączona**|Ochrona w czasie rzeczywistym została wyłączona przez administratora (przy użyciu profilu) lub przez użytkownika na zarządzanym komputerze.|Włącz program Endpoint Protection. Zobacz [Program antywirusowy Windows Defender](device-restrictions-windows-10.md#windows-defender-antivirus) w usłudze Intune lub [Włączanie usługi Windows Defender w celu uzyskiwania dostępu do zasobów firmy](/intune-user-help/turn-on-defender-windows). |
|**Skanowanie pobierania jest wyłączone**|Skanowanie pobierania zostało wyłączone przez administratora przy użyciu profilu lub przez użytkownika na zarządzanym komputerze.|Włącz skanowanie. Zobacz [Program antywirusowy Windows Defender](device-restrictions-windows-10.md#windows-defender-antivirus) w usłudze Intune lub [Włączanie usługi Windows Defender w celu uzyskiwania dostępu do zasobów firmy](/intune-user-help/turn-on-defender-windows). |
|**Monitorowanie działania plików i programów jest wyłączone**|Monitorowanie działania plików i programów zostało wyłączone przez administratora przy użyciu profilu lub przez użytkownika na zarządzanym komputerze.|Włącz działanie plików i programów. Zobacz [Program antywirusowy Windows Defender](device-restrictions-windows-10.md#windows-defender-antivirus) w usłudze Intune lub [Włączanie usługi Windows Defender w celu uzyskiwania dostępu do zasobów firmy](/intune-user-help/turn-on-defender-windows). |
|**Monitorowanie zachowania jest wyłączone**|Monitorowanie zachowania zostało wyłączone przez administratora przy użyciu profilu lub przez użytkownika na zarządzanym komputerze.|Włącz monitorowanie zachowania. Zobacz [Program antywirusowy Windows Defender](device-restrictions-windows-10.md#windows-defender-antivirus) w usłudze Intune lub [Włączanie usługi Windows Defender w celu uzyskiwania dostępu do zasobów firmy](/intune-user-help/turn-on-defender-windows). |
|**Skanowanie skryptu jest wyłączone**|Skanowanie skryptów zostało wyłączone przez administratora przy użyciu profilu lub przez użytkownika na zarządzanym komputerze.|Włącz skanowanie skryptów. Zobacz [Program antywirusowy Windows Defender](device-restrictions-windows-10.md#windows-defender-antivirus) w usłudze Intune lub [Włączanie usługi Windows Defender w celu uzyskiwania dostępu do zasobów firmy](/intune-user-help/turn-on-defender-windows). |
|**System inspekcji sieci jest wyłączony**|System Network Inspection System został wyłączony przez administratora przy użyciu profilu lub przez użytkownika na zarządzanym komputerze.|Włącz system Network Inspection System. Zobacz [Program antywirusowy Windows Defender](device-restrictions-windows-10.md#windows-defender-antivirus) w usłudze Intune lub [Włączanie usługi Windows Defender w celu uzyskiwania dostępu do zasobów firmy](/intune-user-help/turn-on-defender-windows). |
|**Definicje złośliwego oprogramowania są nieaktualne**|Komputer mógł być odłączony od Internetu przez dłuższy czas i jego definicje złośliwego oprogramowania mogły jeszcze nie zostać zaktualizowane. Ten stan jest wyświetlany, gdy definicje złośliwego oprogramowania na komputerze są nieaktualne (pochodzą sprzed co najmniej 14 dni).|Jeśli definicje złośliwego oprogramowania są nieaktualne, możesz je zaktualizować, korzystając [programu antywirusowego Windows Defender](device-restrictions-windows-10.md#windows-defender-antivirus).|
|**Zaległe pełne skanowanie**|Nie wykonano pełnego skanowania w ciągu ostatnich 14 dni. Może to być spowodowane ponownym uruchomieniem komputera podczas pełnego skanowania.|Jeśli pełne skanowanie jest zaległe, możesz uruchomić jednorazowe pełne skanowanie lub zaplanować cykliczne pełne skanowanie. Zobacz [Program antywirusowy Windows Defender](device-restrictions-windows-10.md#windows-defender-antivirus). |
|**Zaległe szybkie skanowanie**|Nie wykonano szybkiego skanowania w ciągu ostatnich 14 dni. Może to być spowodowane ponownym uruchomieniem komputera podczas szybkiego skanowania.|Jeśli szybkie skanowanie jest zaległe, możesz uruchomić jednorazowe szybkie skanowanie lub zaplanować cykliczne szybkie skanowanie. Zobacz [Program antywirusowy Windows Defender](device-restrictions-windows-10.md#windows-defender-antivirus).|
|**Uruchomiona jest inna aplikacja ochrony punktu końcowego**|Uruchomiona jest inna aplikacja ochrony punktu końcowego, a komputer jest w dobrej kondycji.|Domyślnie, jeśli jest zainstalowana inna aplikacja Endpoint Protection i usługa Intune wykryje tę aplikację, urządzenie może stać się niestabilne.|

### <a name="next-steps"></a>Następne kroki
Jeśli te informacje nie pomogą w rozwiązaniu problemu, możesz również [uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](get-support.md).
