---
title: Najczęstsze komunikaty dotyczące ochrony punktu końcowego w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Poznaj najczęstsze komunikaty, które mogą wyświetlać się podczas korzystania z ochrony punktu końcowego i usługi Microsoft Defender w usłudze Microsoft Intune, a także sposoby rozwiązywania typowych problemów.
keywords: ''
author: Brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/13/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: e31df2d2-bb1b-491b-9a71-04e0b18829c1
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 819586a923f5c0f3a81a6d59c4a3895898182f6b
ms.sourcegitcommit: 78cebd3571fed72a3a99e9d33770ef3d932ae8ca
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2019
ms.locfileid: "74059157"
---
# <a name="endpoint-protection-issues-and-possible-solutions-in-microsoft-intune"></a>Problemy dotyczące ochrony punktu końcowego w usłudze Microsoft Intune i ich możliwe rozwiązania

Ten artykuł zawiera opisy możliwych przyczyn problemów oraz potencjalne rozwiązania niektórych błędów i ostrzeżeń. Podane tu informacje ułatwią rozwiązywanie problemów związanych z korzystaniem z ochrony punktu końcowego.

## <a name="microsoft-defender-error-codes"></a>Kody błędów programu Microsoft Defender

Zapoznaj się z dziennikami zdarzeń i kodami błędów, aby [rozwiązać problemy z Programem antywirusowym Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus).

## <a name="common-intune-errors-and-possible-resolutions"></a>Typowe błędy usługi Intune i możliwe rozwiązania

### <a name="endpoint-protection-engine-unavailable"></a>Aparat programu Endpoint Protection jest niedostępny

**Możliwa przyczyna**: aparat programu Endpoint Protection usługi Intune został uszkodzony lub usunięty.

**Możliwe rozwiązania**:

- Jeśli ochrona punktu końcowego jest uszkodzona lub nie można jej zaktualizować, należy zaktualizować lub ponownie zainstalować program.
- Wymuś natychmiastową aktualizację. W programie klienckim ochrony punktu końcowego (np. na pasku zadań) kliknij opcję **Aktualizuj**.
- W obszarze Panel sterowania > Programy kliknij pozycję **Agent programu Microsoft Intune Endpoint Protection**. Odinstaluj aplikację.
- Podczas następnej synchronizacji aktualizacji Menedżer usługi Microsoft Online Management Update wykryje brakujący program i zainstaluje go ponownie o zaplanowanej godzinie instalacji.

### <a name="features-are-disabled"></a>Funkcje są wyłączone

Może pojawiać się komunikat, że niektóre funkcje są wyłączone. Przyczyną może być to, że administrator wyłączył ochronę punktu końcowego w usłudze Intune lub usługę Microsoft Defender przy użyciu profilu konfiguracji. Na urządzeniu mógł je też wyłączyć użytkownik końcowy. Komunikaty, które mogą się wyswietlać:

`Endpoint Protection disabled`  
`Real-time protection disabled`  
`Download scanning disabled`  
`File and program activity monitoring disabled`  
`Behavior monitoring disabled`  
`Script scanning disabled`  
`Network Inspection System disabled`  

**Możliwe rozwiązania**: włącz te funkcje. Więcej informacji zawierają te artykuły:

- [Dodawanie ustawień ochrony punktu końcowego](../protect/endpoint-protection-configure.md)
- [Program antywirusowy Microsoft Defender](../configuration/device-restrictions-windows-10.md#microsoft-defender-antivirus)
- [Użytkownicy końcowi: włączanie ochrony w czasie rzeczywistym w celu uzyskiwania dostępu do zasobów firmy](/intune-user-help/turn-on-defender-windows)

### <a name="malware-definitions-out-of-date"></a>Definicje złośliwego oprogramowania są nieaktualne

Ten stan jest wyświetlany, gdy definicje złośliwego oprogramowania na urządzeniu są nieaktualne (pochodzą sprzed co najmniej 14 dni). Komunikat może wyświetlać się na przykład wtedy, gdy urządzenie utraci połączenie z Internetem lub gdy definicje złośliwego oprogramowania są nieaktualne.

**Możliwe rozwiązania**: jeśli definicje złośliwego oprogramowania są nieaktualne, zaktualizuj je, korzystając z [Programu antywirusowego Microsoft Defender](../configuration/device-restrictions-windows-10.md#microsoft-defender-antivirus).

### <a name="full-scan-overdue-or-quick-scan-overdue"></a>Zaległe skanowanie — pełne lub szybkie

Pełne lub szybkie skanowanie nie zostało wykonane od 14 dni. Ten błąd może wystąpić, jeśli urządzenie zostanie ponownie uruchomione podczas pełnego skanowania.

**Możliwe rozwiązania**: jeśli skanowanie jest zaległe, możesz uruchomić jednorazowe skanowanie lub zaplanować skanowanie cykliczne. Zobacz [Microsoft Defender Antivirus](../configuration/device-restrictions-windows-10.md#microsoft-defender-antivirus).

### <a name="another-endpoint-protection-application-running"></a>Uruchomiona jest inna aplikacja ochrony punktu końcowego

Uruchomiona jest inna aplikacja ochrony punktu końcowego, a komputer jest w dobrej kondycji.

**Możliwe rozwiązania**: jeśli jest zainstalowana inna aplikacja ochrony punktu końcowego i usługa Intune ją wykryje, urządzenie może zacząć działać niestabilnie.

## <a name="next-steps"></a>Następne kroki

Uzyskaj [pomoc techniczną od firmy Microsoft](get-support.md) lub skorzystaj z [forum społeczności](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).
