---
title: "Rozwiązywanie problemów z wdrażaniem aplikacji | Microsoft Docs"
description: "W tym temacie przedstawiono informacje pomagające w rozwiązywaniu problemów z wdrażaniem aplikacji w usłudze Microsoft Intune."
keywords: 
author: robstackmsft
ms.author: robstack
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
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 239371198cbbc01b1345c72b3f887055acd44462


---

# <a name="troubleshoot-app-deployment-problems-in-microsoft-intune"></a>Rozwiązywanie problemów z wdrażaniem aplikacji w usłudze Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Jeśli masz problemy z wdrażaniem aplikacji i zarządzaniem nimi za pomocą usługi Intune, zacznij tutaj. Ten temat zawiera omówienie i rozwiązania niektórych typowych problemów, które mogą wystąpić.

## <a name="common-app-deployment-error-codes"></a>Typowe kody błędów wdrażania aplikacji

|Kod błędu|Możliwy problem|Sugerowane rozwiązanie|
|--------------|--------------------|------------------------|
|0x80073CFF<br /><br />0x80CF201C (błąd klienta)|Aby zainstalować tę aplikację, wymagany jest system z obsługą ładowania bezpośredniego.|Upewnij się, że pakiet aplikacji został podpisany przy użyciu zaufanego podpisu i zainstalowany na urządzeniu przyłączonym do domeny, które ma włączone zasady AllowAllTrustedApps, lub na urządzeniu, które ma licencję ładowania bezpośredniego systemu Windows z włączonymi zasadami AllowAllTrustedApps.|
|0x80073CF0|Nie można otworzyć pakietu.|Możliwe przyczyny:<br /><br />— pakiet nie został podpisany.<br />— nazwa wydawcy jest niezgodna z podmiotem certyfikatu podpisywania.<br /><br />Sprawdź dziennik zdarzeń AppxPackagingOM, aby uzyskać więcej informacji.|
|0x80073CF3|Niepowodzenie aktualizacji, błąd weryfikacji zależności lub konflikt pakietu|Możliwe przyczyny:<br /><br />— przychodzący pakiet powoduje konflikt z zainstalowanym pakietem.<br />— określona zależność pakietu nie została odnaleziona.<br />— pakiet nie obsługuje poprawnej architektury procesora.<br /><br />Sprawdź dziennik zdarzeń AppXDeployment-Server, aby uzyskać więcej informacji.|
|0x80073CFB|Dany pakiet jest już zainstalowany i jego ponowna instalacja jest zablokowana|Ten błąd może pojawić się w przypadku instalowania pakietu, który nie jest identyczny z pakietem już zainstalowanym. Upewnij się , że podpis cyfrowy jest również częścią pakietu. Jeśli pakiet został ponownie skompilowany lub ponownie podpisany, nie jest już bitowo identyczny z wcześniej zainstalowanym pakietem. Dostępne są następujące dwie opcje naprawienia tego błędu:<br /><br />— zwiększenie numeru wersji aplikacji, a następnie ponowne skompilowanie i ponowne podpisanie pakietu.<br />— usunięcie starego pakietu dla każdego użytkownika w systemie przed zainstalowaniem nowego pakietu.|
|0x87D1041C|Instalacja aplikacji zakończyła się pomyślnie, ale nie wykryto aplikacji.|— Aplikacja została pomyślnie wdrożona przez usługę Intune, a następnie odinstalowana (na przykład przez użytkownika końcowego). Poinstruuj użytkownika, aby ponownie zainstalował aplikację z portalu firmy. Wymagane aplikacje zostaną automatycznie zainstalowane ponownie po następnym zaewidencjonowaniu urządzenia.|

## <a name="troubleshooting-apps-from-the-windows-store"></a>Rozwiązywanie problemów z aplikacjami ze Sklepu Windows

Informacje zawarte w temacie [Tworzenie pakietów, wdrażanie i zapytania aplikacji ze Sklepu Windows](https://msdn.microsoft.com/library/windows/desktop/hh973484.aspx) pomagają w rozwiązywaniu typowych problemów, które mogą wystąpić podczas instalowania aplikacji ze Sklepu Windows za pomocą usługi Intune lub w inny sposób.

## <a name="troubleshooting-app-deployment-to-pcs-managed-by-the-intune-software-client"></a>Rozwiązywanie problemów z wdrażaniem aplikacji na komputerach zarządzanych przez klienta oprogramowania usługi Intune
Aby ułatwić rozwiązywanie problemów z wdrażaniem aplikacji na komputerach zarządzanych przez klienta oprogramowania usługi Intune, warto zajrzeć do następujących dwóch plików dziennika:
- Plik w folderze %ProgramFiles%\Microsoft\OnlineManagement\Logs
- Plik %ProgramFiles%\Microsoft\OnlineManagement\Updates\ReportingEvents.log

Ponadto, jeśli trzeba utworzyć zgłoszenie do pomocy technicznej dotyczące usługi Intune, warto także wysłać te dzienniki do firmy Microsoft.


### <a name="next-steps"></a>Następne kroki
Jeśli te informacje dotyczące rozwiązywania problemów nie pomogły, skontaktuj się z pomocą techniczną firmy Microsoft zgodnie z opisem w temacie [Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](how-to-get-support-for-microsoft-intune.md).



<!--HONumber=Dec16_HO2-->


