---
title: Rozwiązywanie problemów z łącznikiem certyfikatów usługi Microsoft Intune i identyfikatory zdarzeń | Microsoft Docs
description: Rozwiązywanie problemów z łącznikiem certyfikatów usługi Microsoft Intune poprzez przeglądanie identyfikatorów i opisów zdarzeń oraz przeglądanie kodów diagnostycznych usługi łącznika usługi Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 05/01/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 682d51269798dff181a3bd8384268da862118a70
ms.sourcegitcommit: 1494ff4b33c13a87f20e0f3315da79a3567db96e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/20/2019
ms.locfileid: "71167760"
---
# <a name="intune-certificate-connector-events-and-diagnostic-codes"></a>Zdarzenia łącznika certyfikatów usługi Intune i kody diagnostyczne

Począwszy od wersji 6.1806.x.x, usługa łącznika Intune rejestruje zdarzenia w **Podglądzie zdarzeń** (**Dzienniki aplikacji i usług** > **Łącznik usługi Microsoft Intune**). Użyj tych zdarzeń, aby w łatwiejszy sposób rozwiązywać potencjalne problemy związane z konfiguracją łącznika usługi Intune. Te zdarzenia rejestrują powodzenia i niepowodzenia operacji, a także zawierają kody diagnostyczne wraz z komunikatami, które ułatwiają administratorowi IT rozwiązywanie problemów.

> [!TIP]  
> Aby rozwiązać problemy i zweryfikować instalację łącznika usługi Intune, zobacz [Przykłady skryptów urzędu certyfikacji](https://aka.ms/intuneconnectorverificationscript).

## <a name="event-ids-and-descriptions"></a>Identyfikatory i opisy zdarzeń

| Identyfikator zdarzenia      | Nazwa zdarzenia    | Opis zdarzenia | Powiązane kody diagnostyczne |
| ------------- | ------------- | -------------     | -------------            |
| 10010 | StartedConnectorService  | Usługa łącznika została uruchomiona | 0x00000000, 0x0FFFFFFF |
| 10020 | StoppedConnectorService  | Usługa łącznika została zatrzymana | 0x00000000, 0x0FFFFFFF |
| 10100 | CertificateRenewal_Success  | Pomyślnie odnowiono certyfikat rejestracji łącznika | 0x00000000, 0x0FFFFFFF |
| 10102 | CertificateRenewal_Failure  | Odnowienie certyfikatu rejestracji łącznika nie powiodło się. Ponownie zainstaluj łącznik. | 0x00000000, 0x00000405, 0x0FFFFFFF |
| 10302 | RetrieveCertificate_Error  | Nie można pobrać certyfikatu rejestracji łącznika z rejestru. Przejrzyj szczegóły zdarzenia dla odcisku palca certyfikatu powiązanego z tym zdarzeniem. | 0x00000000, 0x00000404, 0x0FFFFFFF |
| 10301 | RetrieveCertificate_Warning  | Sprawdź informacje diagnostyczne w szczegółach zdarzenia. | 0x00000000, 0x00000403, 0x0FFFFFFF |
| 20100 | PkcsCertIssue_Success  | Pomyślnie wystawiono certyfikat PKCS. Przejrzyj szczegóły zdarzeń dla następujących elementów powiązanych z tym zdarzeniem: identyfikator urządzenia, identyfikator użytkownika, nazwa urzędu certyfikacji, nazwa szablonu certyfikatu i odcisk palca certyfikatu. | 0x00000000, 0x0FFFFFFF |
| 20102 | PkcsCertIssue_Failure  | Nie można wystawić certyfikatu PKCS. Przejrzyj szczegóły zdarzeń dla następujących elementów powiązanych z tym zdarzeniem: identyfikator urządzenia, identyfikator użytkownika, nazwa urzędu certyfikacji, nazwa szablonu certyfikatu i odcisk palca certyfikatu. | 0x00000000, 0x00000400, 0x00000401, 0x0FFFFFFF |
| 20200 | RevokeCert_Success  | Pomyślnie odwołano certyfikat. Przejrzyj szczegóły zdarzeń dla następujących elementów powiązanych z tym zdarzeniem: identyfikator urządzenia, identyfikator użytkownika, nazwa urzędu certyfikacji i numer seryjny certyfikatu. | 0x00000000, 0x0FFFFFFF |
| 20202 | RevokeCert_Failure | Nie można odwołać certyfikatu. Przejrzyj szczegóły zdarzeń dla następujących elementów powiązanych z tym zdarzeniem: identyfikator urządzenia, identyfikator użytkownika, nazwa urzędu certyfikacji i numer seryjny certyfikatu. Aby uzyskać dodatkowe informacje, zobacz Dzienniki SVC usługi NDES.   | 0x00000000, 0x00000402, 0x0FFFFFFF |
| 20300 | Upload_Success | Pomyślnie przekazano żądanie certyfikatu lub dane dotyczące odwołania. Przejrzyj szczegóły zdarzenia, aby uzyskać informacje o przekazaniu. | 0x00000000, 0x0FFFFFFF |
| 20302 | Upload_Failure | Nie można przekazać żądania certyfikatu lub danych dotyczących odwołania. Przejrzyj stan przekazania w szczegółach zdarzenia, aby określić punkt awarii.| 0x00000000, 0x0FFFFFFF |
| 20400 | Download_Success | Pomyślnie pobrano żądanie podpisania certyfikatu, pobrania certyfikatu klienta lub odwołania certyfikatu. Aby uzyskać informacje o pobieraniu, przejrzyj szczegóły zdarzenia.  | 0x00000000, 0x0FFFFFFF |
| 20402 | Download_Failure | Nie można pobrać żądania podpisania certyfikatu, pobrać certyfikatu klienta lub odwołać certyfikatu. Aby uzyskać informacje o pobieraniu, przejrzyj szczegóły zdarzenia. | 0x00000000, 0x0FFFFFFF |
| 20500 | CRPVerifyMetric_Success  | Zweryfikowanie wezwania klienta przez punkt rejestracji certyfikatu powiodło się | 0x00000000, 0x0FFFFFFF |
| 20501 | CRPVerifyMetric_Warning  | Punkt rejestracji certyfikatu został ukończony, ale żądanie zostało odrzucone. Aby uzyskać więcej informacji, wyświetl kod diagnostyczny i komunikat. | 0x00000000, 0x00000411, 0x0FFFFFFF |
| 20502 | CRPVerifyMetric_Failure  | Zweryfikowanie wezwania klienta przez punkt rejestracji certyfikatu nie powiodło się. Aby uzyskać więcej informacji, wyświetl kod diagnostyczny i komunikat. Wyświetl szczegóły komunikatu zdarzeń dla identyfikatora urządzenia odpowiadającego wezwaniu. | 0x00000000, 0x00000408, 0x00000409, 0x00000410, 0x0FFFFFFF |
| 20600 | CRPNotifyMetric_Success  | Punkt rejestracji certyfikatu pomyślnie ukończył proces powiadamiania i wysłał certyfikat na urządzenie klienckie. | 0x00000000, 0x0FFFFFFF |
| 20602 | CRPNotifyMetric_Failure  | Ukończenie procesu powiadamiania przez punkt rejestracji certyfikatu nie powiodło się. Aby uzyskać informacji dotyczące żądania, zobacz szczegóły komunikatu o zdarzeniu. Sprawdź połączenie między serwerem usługi NDES i urzędem certyfikacji. | 0x00000000, 0x0FFFFFFF |

## <a name="diagnostic-codes"></a>Kody diagnostyczne

| Kod diagnostyczny | Nazwa diagnostyki | Komunikatu diagnostyczny |
| -------------   | -------------   | -------------      |
| 0x00000000 | Powodzenie  | Powodzenie |
| 0x00000400 | PKCS_Issue_CA_Unavailable  | Urząd certyfikacji jest nieprawidłowy lub nieosiągalny. Sprawdź, czy urząd certyfikacji jest dostępny i Twój serwer może się z nim komunikować. |
| 0x00000401 | Symantec_ClientAuthCertNotFound  | Nie odnaleziono certyfikatu autoryzacji klienta firmy Symantec w lokalnym magazynie certyfikatów. Aby uzyskać więcej informacji, zapoznaj się z artykułem [Instalacja certyfikatu autoryzacji firmy Symantec](certificates-digicert-configure.md#install-the-digicert-ra-certificate).  |
| 0x00000402 | RevokeCert_AccessDenied  | Określone konto nie ma uprawnień do odwołania certyfikatu z urzędu certyfikacji. Zobacz pole Nazwa urzędu certyfikacji w szczegółach komunikatu o zdarzeniu, aby określić urząd certyfikacji.  |
| 0x00000403 | CertThumbprint_NotFound  | Nie można odnaleźć certyfikatu zgodnego z danymi wejściowymi. Zarejestruj łącznik certyfikatów i spróbuj ponownie. |
| 0x00000404 | Certificate_NotFound  | Nie można odnaleźć certyfikatu zgodnego z podanymi danymi wejściowymi. Ponownie zarejestruj łącznik certyfikatów i spróbuj ponownie. |
| 0x00000405 | Certificate_Expired  | Certyfikat wygasł. Ponownie zarejestruj łącznik certyfikatów, aby odnowić certyfikat, a następnie spróbuj ponownie. |
| 0x00000408 | CRPSCEPCert_NotFound  | Nie można odnaleźć certyfikatu szyfrowania CRP. Sprawdź, czy prawidłowo skonfigurowano usługę NDES i łącznik usługi Intune. |
| 0x00000409 | CRPSCEPSigningCert_NotFound  | Nie można pobrać certyfikatu podpisywania. Sprawdź, czy usługa łącznika Intune jest poprawnie skonfigurowana i uruchomiona. Sprawdź również, czy zdarzenia pobierania certyfikatów zakończyły się pomyślnie. |
| 0x00000410 | CRPSCEPDeserialize_Failed  | Nie można zdeserializować żądania wezwania SCEP. Sprawdź, czy prawidłowo skonfigurowano usługę NDES i łącznik usługi Intune. |
| 0x00000411 | CRPSCEPChallenge_Expired  | Wezwanie odrzucone z powodu wygasłego testu certyfikatu. Urządzenie klienckie może ponowić próbę po uzyskaniu nowego wezwania z serwera zarządzania. |
| 0x0FFFFFFFF | Unknown_Error  | Nie można wykonać żądania, ponieważ wystąpił błąd po stronie serwera. Spróbuj ponownie. |


## <a name="next-steps"></a>Następne kroki
Dodatkową pomoc można uzyskać w przewodniku [Troubleshooting SCEP certificate profile deployment in Microsoft Intune](https://support.microsoft.com/help/4457481/troubleshooting-scep-certificate-profile-deployment-in-intune) (Rozwiązywanie problemów z wdrażaniem profilu certyfikatu SCEP w usłudze Microsoft Intune).
