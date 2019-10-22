---
title: Rozwiązywanie problemów z programem Exchange Connector
titleSuffix: Microsoft Intune
description: Rozwiązywanie problemów związanych z lokalnym łącznikiem Exchange Connector usługi Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/02/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: a7e3c742-295b-40bb-9afa-17f243062500
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 962e66a9fdf6d8abcf6855f645775026ee4db850
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72508842"
---
# <a name="troubleshoot-the-intune-exchange-connector"></a>Rozwiązywanie problemów z programem Intune Exchange Connector

W tym artykule opisano, jak rozwiązywać problemy związane z programem Intune Exchange Connector.

## <a name="before-you-start"></a>Przed rozpoczęciem

Przed rozpoczęciem rozwiązywania problemów z programem Exchange Connector w usłudze Intune Zbierz podstawowe informacje, aby pracować na solidnej platformie. Takie podejście może pomóc w lepszym zrozumieniu istoty problemu i ich szybszego rozwiązywania.

- Sprawdź, czy proces spełnia wymagania instalacyjne. Zobacz [Konfigurowanie lokalnego programu Intune Exchange Connector](exchange-connector-install.md).
- Sprawdź, czy Twoje konto ma uprawnienia administratora programu Exchange i usługi Intune.
- Zwróć uwagę na pełny i dokładny tekst komunikatu o błędzie, szczegóły i lokalizację, w której zostanie wyświetlony komunikat.
- Określ, kiedy problem został uruchomiony: 
  - Czy po raz pierwszy konfigurujesz łącznik? 
  - Czy łącznik działał prawidłowo, a następnie niepowodzenie?
  - Jeśli działały, jakie zmiany wystąpiły w środowisku usługi Intune, środowisku programu Exchange lub na komputerze, na którym jest uruchamiane oprogramowanie łącznika?
- Co to jest urząd MDM? Jeśli jest System Center Configuration Manager, której wersji Configuration Manager użyć?
- Jakiej wersji programu Exchange używasz?

### <a name="use-powershell-to-get-more-data-on-exchange-connector-issues"></a>Uzyskiwanie dodatkowych danych dotyczących problemów z programem Exchange Connector za pomocą programu PowerShell

- Aby uzyskać listę wszystkich urządzeń przenośnych dla skrzynki pocztowej, użyj `Get-ActiveSyncDeviceStatistics -mailbox mbx`
- Aby uzyskać listę adresów SMTP dla skrzynki pocztowej, użyj `Get-Mailbox -Identity user | select emailaddresses | fl`
- Aby uzyskać szczegółowe informacje dotyczące stanu dostępu do urządzenia, użyj polecenia `Get-CASMailbox <upn> | fl`

## <a name="review-the-connector-configuration"></a>Przegląd konfiguracji łącznika

Zapoznaj się z [wymaganiami dotyczącymi lokalnego programu Exchange Connector](exchange-connector-install.md#intune-exchange-connector-requirements) , aby upewnić się, że środowisko i łącznik są prawidłowo skonfigurowane. 

### <a name="general-considerations-for-the-connector"></a>Ogólne zagadnienia dotyczące łącznika

- Upewnij się, że Zapora i serwery proxy umożliwiają komunikację między serwerem obsługującym łącznik usługi Intune Exchange i usługą Intune.

- Komputer obsługujący łącznik usługi Intune Exchange oraz serwer dostępu klienta programu Exchange (CAS) powinien być przyłączony do domeny i znajdować się w tej samej sieci LAN. Upewnij się, że do konta używanego przez łącznik usługi Intune Exchange są dodawane wymagane uprawnienia.

- Konto powiadomień służy do pobierania ustawień *wykrywania automatycznego* . Aby uzyskać więcej informacji na temat Autodisover w programie Exchange, zobacz [Usługa wykrywania automatycznego w programie Exchange Server](https://docs.microsoft.com/exchange/architecture/client-access/autodiscover?view=exchserver-2016).

- Program Intune Exchange Connector wysyła żądanie do adresu URL EWS przy użyciu poświadczeń konta powiadomień do wysyłania wiadomości e-mail z powiadomieniami razem *z linkiem wprowadzenie (* do rejestracji w usłudze Intune). Użycie *linku wprowadzenie do* rejestracji jest wymaganiem dla urządzeń z systemem Android. W przeciwnym razie te urządzenia będą blokowane przez dostęp warunkowy.

### <a name="common-issues-for-connector-configurations"></a>Typowe problemy dotyczące konfiguracji łącznika

- **Uprawnienia konta**: w oknie dialogowym Microsoft Intune Exchange Connector upewnij się, że określono konto użytkownika, które ma odpowiednie uprawnienia do wykonywania [wymaganych poleceń cmdlet programu Exchange w środowisku Windows PowerShell](exchange-connector-install.md#exchange-cmdlet-requirements).
- **Wiadomości e-mail z powiadomieniami**: Włącz powiadomienia i określ konto powiadomień.
- **Synchronizacja serwera dostępu klienta**: podczas konfigurowania programu Exchange Connector należy określić urzędy certyfikacji o najniższym opóźnieniu sieci na serwerze hostującym łącznik programu Exchange. Opóźnienie komunikacji między serwerem CAS i programem Exchange Connector może spowodować opóźnienia odnajdywania urządzeń, zwłaszcza w przypadku korzystania z usługi Exchange Online w warstwie Dedykowana.
- **Harmonogram synchronizacji**: uzyskanie dostępu przez użytkownika z nowo zarejestrowanym urządzeniem może zostać opóźnione do momentu, aż program Exchange Connector zsynchronizuje się z serwerem CAS programu Exchange. Pełna synchronizacja jest wykonywana raz dziennie, a synchronizacja różnicowa (szybka) jest wykonywana kilka razy dziennie. Aby zminimalizować opóźnienie, możesz [ręcznie wymusić szybką synchronizację lub pełną synchronizację](exchange-connector-install.md#manually-force-a-quick-sync-or-full-sync).

## <a name="next-steps"></a>Następne kroki
Poniższe artykuły mogą pomóc w rozwiązywaniu typowych problemów i określonych błędów:

- [Rozwiązywanie typowych problemów z programem Intune Exchange Connector](troubleshoot-exchange-connector-common-problems.md).
- [Rozwiązywanie typowych błędów dla programu Intune Exchange Connector](troubleshoot-exchange-connector-common-errors.md).

Wyszukaj pomoc techniczną lub społeczność usługi Intune:

- Zobacz [Uzyskaj pomoc techniczną](../fundamentals/get-support.md) , aby korzystać z konsoli usługi Intune, aby pomóc w rozwiązywaniu problemu lub otworzyć przypadek pomocy technicznej w firmie Microsoft. 
- Opublikuj swój problem na [forach Microsoft Intune](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod).  
