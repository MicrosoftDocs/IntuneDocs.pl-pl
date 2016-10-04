---
title: "Rozwiązywanie problemów z wdrażaniem aplikacji | Microsoft Intune"
description: "W tym temacie przedstawiono informacje pomagające w rozwiązywaniu problemów z wdrażaniem aplikacji w usłudze Microsoft Intune."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 09/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 28ac298e-fb73-4c1c-b3fd-8336639e05e6
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 30d42bc4ee38a45895320eebd665fe8f5a0cb4ee
ms.openlocfilehash: 0db3e6a39bd0d30231c339cb4501ce25059e4657


---

# Rozwiązywanie problemów z wdrażaniem aplikacji w usłudze Microsoft Intune
Jeśli masz problemy z wdrażaniem aplikacji i zarządzaniem nimi za pomocą usługi Intune, zacznij tutaj. Ten temat zawiera omówienie i rozwiązania niektórych typowych problemów, które mogą wystąpić.

## Typowe kody błędów wdrażania aplikacji

|Kod błędu|Możliwy problem|Sugerowane rozwiązanie|
|--------------|--------------------|------------------------|
|0x80073CFF<br /><br />0x80CF201C (błąd klienta)|Aby zainstalować tę aplikację, wymagany jest system z obsługą ładowania bezpośredniego.|Upewnij się, że pakiet aplikacji jest podpisany przy użyciu zaufanego podpisu i zainstalowany na urządzeniu przyłączonym do domeny, które ma włączone zasady AllowAllTrustedApps, lub na urządzeniu, które ma licencję ładowania bezpośredniego systemu Windows z włączonymi zasadami AllowAllTrustedApps (stosowane podczas rejestrowania urządzenia z systemem Windows RT).|
|0x80073CF0|Nie można otworzyć pakietu.|Możliwe przyczyny:<br /><br />— pakiet nie został podpisany.<br />— nazwa wydawcy jest niezgodna z podmiotem certyfikatu podpisywania.<br /><br />Sprawdź dziennik zdarzeń AppxPackagingOM, aby uzyskać więcej informacji.|
|0x80073CF3|Niepowodzenie aktualizacji, błąd weryfikacji zależności lub konflikt pakietu|Możliwe przyczyny:<br /><br />— przychodzący pakiet powoduje konflikt z zainstalowanym pakietem.<br />— określona zależność pakietu nie została odnaleziona.<br />— pakiet nie obsługuje poprawnej architektury procesora.<br /><br />Sprawdź dziennik zdarzeń AppXDeployment-Server, aby uzyskać więcej informacji.|
|0x80073CFB|Dany pakiet jest już zainstalowany i jego ponowna instalacja jest zablokowana|Ten błąd może pojawić się w przypadku instalowania pakietu, który nie jest identyczny z pakietem już zainstalowanym. Upewnij się , że podpis cyfrowy jest również częścią pakietu. Jeśli pakiet został ponownie skompilowany lub ponownie podpisany, nie jest już bitowo identyczny z wcześniej zainstalowanym pakietem. Dostępne są następujące dwie opcje naprawienia tego błędu:<br /><br />— zwiększenie numeru wersji aplikacji, a następnie ponowne skompilowanie i ponowne podpisanie pakietu.<br />— usunięcie starego pakietu dla każdego użytkownika w systemie przed zainstalowaniem nowego pakietu.|
|0x87D1041C|Instalacja aplikacji zakończyła się pomyślnie, ale nie wykryto aplikacji.|— Aplikacja została pomyślnie wdrożona przez usługę Intune, a następnie odinstalowana (na przykład przez użytkownika końcowego). Poinstruuj użytkownika, aby ponownie zainstalował aplikację z portalu firmy. Wymagane aplikacje zostaną automatycznie zainstalowane ponownie po następnym zaewidencjonowaniu urządzenia.|

## Rozwiązywanie problemów z aplikacjami ze Sklepu Windows

Informacje zawarte w temacie [Tworzenie pakietów, wdrażanie i zapytania aplikacji ze Sklepu Windows](https://msdn.microsoft.com/library/windows/desktop/hh973484.aspx) pomagają w rozwiązywaniu typowych problemów, które mogą wystąpić podczas instalowania aplikacji ze Sklepu Windows za pomocą usługi Intune lub w inny sposób.

## Rozwiązywanie problemów z wdrażaniem aplikacji na komputerach zarządzanych przez klienta oprogramowania usługi Intune
Aby ułatwić rozwiązywanie problemów z wdrażaniem aplikacji na komputerach zarządzanych przez klienta oprogramowania usługi Intune, warto zajrzeć do następujących dwóch plików dziennika:
- Plik w folderze %ProgramFiles%\Microsoft\OnlineManagement\Logs
- Plik %ProgramFiles%\Microsoft\OnlineManagement\Updates\ReportingEvents.log

Ponadto, jeśli trzeba utworzyć zgłoszenie do pomocy technicznej dotyczące usługi Intune, warto także wysłać te dzienniki do firmy Microsoft.


### Następne kroki
Jeśli te informacje dotyczące rozwiązywania problemów nie pomogły, skontaktuj się z pomocą techniczną firmy Microsoft zgodnie z opisem w temacie [Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](how-to-get-support-for-microsoft-intune.md).



<!--HONumber=Sep16_HO4-->


