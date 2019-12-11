---
title: Zasady ochrony aplikacji na potrzeby rozszerzeń
titleSuffix: Microsoft Intune
description: W tym temacie opisano ustawienia zasad ochrony aplikacji (APP) dla rozszerzeń.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: demerson
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1a94f3d175fe5c036c5e90635a66467263b23122
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72499121"
---
# <a name="protecting-application-extensions"></a>Ochrona rozszerzeń aplikacji

W tym artykule opisano zasady ochrony aplikacji dla rozszerzeń w usłudze Microsoft Intune.

## <a name="add-ins-for-outlook-app"></a>Dodatki dla aplikacji Outlook

Dodatki programu Outlook pozwalają zintegrować popularne aplikacje z klientem poczty e-mail. Dodatki dla programu Outlook w środowiskach Windows, Mac i Outlook dla systemu Android i iOS są dostępne w Internecie. Zestaw Intune APP SDK i zasady ochrony aplikacji usługi Intune nie obejmują obsługi dodatków zarządzania dla programu Outlook, ale istnieją inne sposoby, aby ograniczyć ich użycie. Ponieważ dodatki są zarządzane przez program Microsoft Exchange, użytkownicy otrzymają możliwość udostępniania danych i wiadomości między programem Outlook i niezarządzanymi aplikacjami zgodnymi z dodatkiem, chyba że dodatki zostaną wyłączone dla użytkownika przez program Exchange.

Jeśli nie chcesz, aby użytkownicy końcowi mogli uzyskiwać dostęp do dodatków programu Outlook i je instalować (dotyczy wszystkich klientów programu Outlook), upewnij się, że w obszarze ról w centrum administracyjnym programu Exchange wprowadzono następujące zmiany:

- Aby uniemożliwić użytkownikom instalowanie dodatków ze Sklepu Office, usuń dla nich rolę Moja witryna Marketplace.
- Aby uniemożliwić użytkownikom ładowanie bezpośrednie dodatków, usuń dla nich rolę Moje aplikacje niestandardowe.
- Aby uniemożliwić użytkownikom instalowanie wszystkich dodatków, usuń dla nich zarówno rolę Moje aplikacje niestandardowe, jak i rolę Moja witryna Marketplace.

Instrukcje te dotyczą usług Office 365, Exchange 2016 i Exchange 2013 w środowiskach programu Outlook w sieci Web, w systemach Windows i Mac oraz w urządzeniach przenośnych.

- Dowiedz się więcej o [dodatkach programu Outlook](https://technet.microsoft.com/library/jj943753(v=exchg.150).aspx).
- Dowiedz się więcej na temat tego, [jak określić, którzy administratorzy i użytkownicy mogą instalować dodatki dla aplikacji Outlook i zarządzać nimi](https://technet.microsoft.com/library/jj943754(v=exchg.150).aspx).

## <a name="linkedin-account-connections-for-microsoft-apps"></a>Połączenia konta usługi LinkedIn dla aplikacji firmy Microsoft

Połączenia konta LinkedIn umożliwiają użytkownikom wyświetlanie publicznych informacji o profilu LinkedIn za pomocą niektórych aplikacji firmy Microsoft. Domyślnie użytkownicy mogą postanowić połączyć swoje konta usługi LinkedIn i służbowe konta Microsoft, aby wyświetlić dodatkowe informacje o profilu LinkedIn. 

> [!NOTE]
> Integracja usługi LinkedIn jest obecnie niedostępna dla klientów z instytucji rządowych Stanów Zjednoczonych i dla organizacji ze skrzynkami pocztowymi usługi Exchange Online hostowanymi w Australii, Kanadzie, Chinach, Francji, Niemczech, Indiach, Korei Południowej, Wielkiej Brytanii, Japonii i Republice Południowej Afryki.

Zestaw SDK usługi Intune i zasady ochrony aplikacji usługi Intune nie obejmują obsługi zarządzania połączeniami konta usługi LinkedIn, ale istnieją inne sposoby, aby nimi zarządzać. Możesz wyłączyć połączenia konta usługi LinkedIn dla całej organizacji lub możesz włączyć połączenia konta usługi LinkedIn dla wybranych grup użytkowników w organizacji. Te ustawienia wpływają na połączenia usługi LinkedIn w aplikacjach usługi Office 365 na wszystkich platformach (internetowych, mobilnych i na pulpicie). Można:

- Włączyć lub wyłączyć połączenia konta usługi LinkedIn dla Twojej dzierżawy w witrynie Azure Portal. 
- Włączyć lub wyłączyć połączenia konta LinkedIn w przypadku aplikacji pakietu Office 2016 Twojej organizacji za pomocą zasad grupy.

Jeśli integracja usługi LinkedIn jest włączona dla Twojej dzierżawy, gdy użytkownicy w Twojej organizacji łączą swoje konto usługi LinkedIn i służbowe konta Microsoft, mają dwie opcje: 

- Mogą oni przyznać uprawnienia do udostępniania danych między obydwoma kontami. Oznacza to, że dają oni uprawnienie swojemu kontu usługi LinkedIn do udostępniania danych swojemu kontu służbowemu Microsoft oraz swojemu kontu służbowemu Microsoft do udostępnienia danych swojemu kontu usługi LinkedIn. Dane, które są udostępniane usłudze LinkedIn, opuszczają usługi online. 
- Mogą oni udzielić uprawnienia do udostępniania danych tylko z konta usługi LinkedIn swojemu kontu służbowemu Microsoft

Jeśli użytkownik wyraża zgodę na udostępnianie danych między kontami, jak w dodatkach pakietu Office, integracja usługi LinkedIn używa istniejących interfejsów API programu Microsoft Graph. Integracja LinkedIn korzysta tylko z podzbioru interfejsów API dostępnych dla dodatków pakietu Office i obsługuje różne wykluczenia.


|Uprawnienia programu Microsoft Graph  |Opis  |
|---------|---------|
|Uprawnienia do odczytu dla [osób](https://developer.microsoft.com/graph/docs/concepts/permissions_reference#people-permissions)     |Zezwala aplikacji na odczytywanie uporządkowanej listy osób odpowiednich dla zalogowanego użytkownika. Lista może zawierać kontakty lokalne, kontakty z sieci społecznościowych lub katalog Twojej organizacji i osoby, z którymi kontaktowano się ostatnio (np. za pomocą poczty e-mail i programu Skype).         |
|Uprawnienia do odczytu dla [kalendarzy](https://developer.microsoft.com/graph/docs/concepts/permissions_reference#calendars-permissions)     |Zezwala aplikacji na odczytywanie wydarzeń w kalendarzach użytkownika. Zawiera spotkania w kalendarzach zalogowanego użytkownika, ich godziny, lokalizacje i uczestników.         |
|Uprawnienia do odczytu dla [profilu użytkownika](https://developer.microsoft.com/graph/docs/concepts/permissions_reference#user-permissions)     |Zezwala użytkownikom na logowanie się do aplikacji oraz zezwala aplikacji na odczytywanie profilu zalogowanych użytkowników. Umożliwia również aplikacji odczytywanie podstawowych informacji o firmie dla zalogowanych użytkowników.         |
|Subscriptions     |Ten zakres nie jest dostępny i nie jest jeszcze używany. Obejmuje on subskrypcje udostępniane przez organizację użytkownika aplikacjom i usługom firmy Microsoft, takim jak usługa Office 365.         |
|Szczegółowe informacje     |Ten zakres nie jest dostępny i nie jest jeszcze używany. Obejmuje on zainteresowania skojarzone z kontem zalogowanego użytkownika na podstawie używania przez niego usług firmy Microsoft.         |

### <a name="learn-more"></a>Dowiedz się więcej

- Dowiedz się więcej o [informacjach i funkcjach usługi LinkedIn w aplikacjach firmy Microsoft](https://go.microsoft.com/fwlink/?linkid=850740).
- Więcej informacji na temat wersji połączeń konta usługi LinkedIn znajdziesz na [stronie harmonogramu działania dla usługi Office 365](https://products.office.com/en-US/business/office-365-roadmap?filters=%26freeformsearch=linkedin#abc). 
- Dowiedz się więcej o [Konfigurowaniu połączeń konta usługi LinkedIn](https://docs.microsoft.com/azure/active-directory/linkedin-integration).
- Aby uzyskać więcej informacji o danych, które są współużytkowane przez konta usługi LinkedIn i konta służbowe Microsoft użytkowników, zobacz [LinkedIn in Microsoft applications at your work or school (Usługa LinkedIn w aplikacjach firmy Microsoft w miejscu pracy lub nauki)](https://www.linkedin.com/help/linkedin/answer/84077).

