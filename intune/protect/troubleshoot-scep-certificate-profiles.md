---
title: Rozwiązywanie problemów dotyczących używania profilów certyfikatów protokołu SCEP do aprowizowania certyfikatów za pomocą usługi Microsoft Intune | Microsoft Docs
description: Rozwiązywanie problemów dotyczących używania protokołu SCEP na urządzeniach w celu żądania certyfikatów do użycia z usługą Intune, w tym do komunikacji z urządzeń do usługi rejestrowania urządzeń sieciowych, z usługi rejestrowania urządzeń sieciowych do urzędów certyfikacji oraz z łącznika certyfikatów usługi Intune do usługi Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/30/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4496a5bbc6d5ee5134dc4e6a795494710ea6865d
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77515224"
---
# <a name="overview-for-troubleshooting-scep-certificate-profiles-with-microsoft-intune"></a>Omówienie rozwiązywania problemów z profilami certyfikatów SCEP w usłudze Microsoft Intune

W usłudze Intune rozwiązywanie problemów dotyczących używania profilów certyfikatów w usłudze prostego protokołu rejestrowania certyfikatów (SCEP) może być trudne. Ten artykuł zawiera omówienie, które może pomóc w rozwiązywaniu problemów przez:

- Objaśnienie architektury i przepływu komunikacji w procesie protokołu SCEP
- Pomaga to w zawężaniu możliwego obszaru wystąpienia problemu w tym przepływie komunikacji
- Identyfikowanie plików dziennika kluczy przywoływanych w kolejnych artykułach dotyczących rozwiązywania problemów z profilami certyfikatów

Informacje zawarte w tym artykule i innych powiązanych artykułach na temat rozwiązywania problemów z certyfikatami SCEP dotyczą korzystania z profilów certyfikatów SCEP na urządzeniach z systemami Android, iOS/iPad i Windows. Podobne informacje dotyczące systemu macOS są w tej chwili niedostępne.

Aby rozwiązać problemy z usługą rejestracji urządzeń sieciowych (NDES), zobacz następujące artykuły w witrynie support.microsoft.com:

- [Verify NDES configuration on-premises for SCEP certificates in Intune](https://support.microsoft.com/help/4490130/ndes-configuration-on-premises-for-scep-certificates-in-intune) (Weryfikowanie konfiguracji usługi NDES w środowisku lokalnym na potrzeby certyfikatów protokołu SCEP w usłudze Intune)
- [Troubleshooting NDES configuration for use with Microsoft Intune certificate profiles]( https://support.microsoft.com/help/4459540/troubleshoot-ndes-configuration-for-use-with-intune) (Rozwiązywanie problemów z konfiguracją usługi NDES do użycia z profilami certyfikatów usługi Microsoft Intune)

Przed kontynuowaniem upewnij się, że spełniono [wymagania wstępne dotyczące używania profilów certyfikatów protokołu SCEP](certificates-scep-configure.md#prerequisites-for-using-scep-for-certificates), w tym wdrażania certyfikatu głównego za pośrednictwem zaufanego profilu certyfikatu.

## <a name="scep-communication-flow-overview"></a>Omówienie przepływu komunikacji protokołu SCEP

Na poniższej ilustracji przedstawiono podstawowe omówienie procesu komunikacji protokołu SCEP w usłudze Intune.

![Przepływ profilu certyfikatu protokołu SCEP](../protect/media/troubleshoot-scep-certificate-profiles/scep-certificate-profile-flow.png)

1. [Wdrożenie profilu certyfikatu protokołu SCEP](troubleshoot-scep-certificate-profile-deployment.md). Usługa Intune generuje ciąg żądania, który wymaga określonego użytkownika, celu certyfikatu i typu certyfikatu.

2. [Komunikacja urządzenia z serwerem usługi NDES](troubleshoot-scep-certificate-device-to-ndes.md). Urządzenie używa identyfikatora URI usługi NDES z profilu, aby skontaktować się z serwerem usługi NDES w celu przedstawienia żądania.

3. [Komunikacja usługi NDES z modułem zasad](troubleshoot-scep-certificate-ndes-policy-module.md). Usługa NDES przekazuje żądanie do modułu zasad łącznika certyfikatów usługi Intune na serwerze, który weryfikuje żądanie.

4. [Usługa NDES do urzędu certyfikacji](troubleshoot-scep-certificate-ndes-policy-module.md). Usługa NDES przekazuje prawidłowe żądania w celu wystawienia certyfikatu do urzędu certyfikacji.

5. [Dostarczenie certyfikatu do urządzenia](troubleshoot-scep-certificate-delivery.md). Certyfikat jest dostarczany do urządzenia.

6. [Zgłoszenie wdrożenia do usługi Intune](troubleshoot-scep-certificate-reporting.md). Łącznik certyfikatów usługi Intune zgłasza zdarzenie wystawiania certyfikatu do usługi Intune.

## <a name="log-files"></a>Pliki dziennika

Aby zidentyfikować problemy z komunikacją i przepływem pracy aprowizowania certyfikatów, przejrzyj pliki dziennika z infrastruktury serwera i urządzeń. Dalsze sekcje dotyczące rozwiązywania problemów z profilami certyfikatów protokołu SCEP odnoszą się do plików dziennika wspomnianych w tej sekcji.

- [Dzienniki infrastruktury i serwera](#logs-for-on-premises-infrastructure)

Dzienniki urządzeń zależą od platformy urządzenia:  

- [iOS i iPadOS](#logs-for-ios-and-ipados-devices)
- [Android](#logs-for-android-devices)
- [Windows](#logs-for-windows-devices)

### <a name="logs-for-on-premises-infrastructure"></a>Dzienniki dotyczące infrastruktury lokalnej
  
Infrastruktura lokalna, która obsługuje użycie profilów certyfikatów protokołu SCEP na potrzeby wdrożeń certyfikatów, obejmuje łącznik certyfikatów usługi Microsoft Intune, usługę NDES działającą w systemie Windows Server i urząd certyfikacji.

Pliki dziennika dla tych ról obejmują Podgląd zdarzeń systemu Windows, konsole certyfikatów i różne pliki dzienników specyficzne dla łącznika certyfikatów usługi Intune, usługi NDES lub innych ról i operacji, które są częścią infrastruktury lokalnej.

Poniższa lista zawiera dzienniki lub konsole, do których odwołują się kolejne artykuły dotyczące rozwiązywania problemów z protokołem SCEP. 

- **NDESConnector_date_time.svclog**:

  Ten dziennik przedstawia komunikację z łącznika certyfikatów usługi Microsoft Intune do usługi Intune w chmurze. Aby wyświetlić ten plik dziennika, możesz użyć [narzędzia do przeglądania danych śledzenia usług](https://docs.microsoft.com/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe).

  Powiązany klucz rejestru: *HKLM\SW\Microsoft\MicrosoftIntune\NDESConnector\ConnectionStatus*

  Lokalizacja: Na serwerze, który hostuje usługę NDES, w folderze *%program_files%\Microsoft intune\ndesconnectorsvc\logs\logs*

- **CertificateRegistrationPoint_date_time.svclog**:

  Ten dziennik przedstawia moduł zasad usługi NDES, który otrzymuje i weryfikuje żądania certyfikatów. Aby wyświetlić ten plik dziennika, możesz użyć [narzędzia do przeglądania danych śledzenia usług](https://docs.microsoft.com/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe).

  Lokalizacja: Na serwerze, który hostuje usługę NDES, w folderze *%program_files%\Microsoft intune\ndesconnectorsvc\logs\logs*

- **NDESPlugin.log**:

  Ten dziennik przedstawia przekazywanie żądań certyfikatów do punktu rejestracji certyfikatu oraz weryfikację tych żądań.

  Lokalizacja: Na serwerze, który hostuje usługę NDES, w folderze *%program_files%\Microsoft Intune\NDESPolicyModule\logs*

- **Dzienniki usług IIS**:

  Dzienniki usług IIS przedstawiają żądania certyfikatów z urządzeń przenośnych, w których jest wprowadzana usługa NDES.

  Lokalizacja: Na serwerze, który hostuje usługę NDES, w folderze *c:\inetpub\logs\LogFiles\W3SVC1*

- **Dziennik aplikacji systemu Windows**:

  Ten dziennik jest przydatny podczas badania problemów z usługami IIS, takich jak pula aplikacji protokołu SCEP.

  Lokalizacja: Na serwerze, który hostuje usługę NDES: Uruchom plik **eventvwr.msc**, aby otworzyć Podgląd zdarzeń systemu Windows




### <a name="logs-for-android-devices"></a>Dzienniki dotyczące urządzeń z systemem Android

W przypadku urządzeń z systemem Android użyj pliku dziennika aplikacji **Portal firmy dla systemu Android** o nazwie **OMADM.log**. Przed zebraniem i przejrzeniem dzienników upewnij się, że włączono [pełne rejestrowanie](/intune-user-help/use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android), a następnie odtwórz problem.

Aby zebrać plik OMADM.logs z urządzenia, zobacz temat [Przekazywanie i przesyłanie dzienników pocztą e-mail przy użyciu kabla USB](/intune-user-help/send-logs-to-your-it-admin-using-cable-android).

Możesz również [przekazywać dzienniki i wysyłać je pocztą e-mail](/intune-user-help/send-logs-to-your-it-admin-by-email-android#upload-and-email-logs-from-microsoft-intune-app) w celu obsługi.

### <a name="logs-for-ios-and-ipados-devices"></a>Dzienniki dotyczące urządzeń z systemem iOS i iPadOS

W przypadku urządzeń z systemem iOS/iPadOS należy użyć dzienników debugowania i **Xcode**, które są uruchamiane na komputerze Mac:

1. Podłącz urządzenie z systemem iOS/iPadOS do komputera Mac, a następnie przejdź do pozycji **Aplikacje** > **Narzędzia**, aby otworzyć aplikację Konsola. 

2. W obszarze **akcji** wybierz opcje **uwzględniania komunikatów informacyjnych** i **uwzględniania komunikatów debugowania**.

   ![Wybieranie opcji dzienników](../protect/media/troubleshoot-scep-certificate-profiles/message-options.png)

3. Odtwórz problem, a następnie zapisz dzienniki w pliku tekstowym:
   1. Wybierz pozycję **Edytuj** > **Zaznacz wszystko**, aby zaznaczyć wszystkie komunikaty na bieżącym ekranie, a następnie wybierz pozycję **Edytuj** > **Kopiuj**, aby skopiować komunikaty do schowka. 
   2. Otwórz aplikację TextEdit, wklej skopiowane dzienniki do nowego pliku tekstowego, a następnie zapisz plik.


Dziennik Portalu firmy dla urządzeń z systemem iOS i iPadOS nie zawiera informacji o profilach certyfikatów protokołu SCEP.

### <a name="logs-for-windows-devices"></a>Dzienniki dotyczące urządzeń z systemem Windows

W przypadku urządzeń z systemem Windows należy używać dzienników zdarzeń systemu Windows do diagnozowania problemów z rejestracją lub zarządzaniem urządzeniami, jeśli zarządzanie urządzeniami odbywa się za pomocą usługi Intune.

Na urządzeniu otwórz obszar **Podgląd zdarzeń** > **Dzienniki aplikacji i usług** > **Microsoft** > **Windows** > **DeviceManagement-Enterprise-Diagnostics-Provider**

![Dzienniki zdarzeń systemu Windows](../protect/media/troubleshoot-scep-certificate-profiles/windows-event-log.png)

## <a name="next-steps"></a>Następne kroki

Przejrzyj [wdrożenie profilów certyfikatów protokołu SCEP](troubleshoot-scep-certificate-profile-deployment.md) 
