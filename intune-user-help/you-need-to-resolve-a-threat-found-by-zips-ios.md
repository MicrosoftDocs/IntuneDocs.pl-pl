---
title: Rozwiązywanie problemów związanych z zagrożeniami wykrytymi przez aplikację Zimperium zIPS w systemie iOS | Microsoft Docs
description: Dowiedz się, jak usuwać zagrożenia wykryte na urządzeniu z systemem iOS.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: eaccd9c0-cd46-48e2-8675-4c022c74f672
searchScope:
- User help
ROBOTS: ''
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: ffc9750d6189e0d9ba3cc4cd8c28ffee6032acbc
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72500687"
---
# <a name="resolve-a-threat-found-by-zimperium-zips"></a>Rozwiązywanie problemu zagrożenia wykrytego przez aplikację Zimperium zIPS

Aplikacja Zimperium zIPS to mobilna usługa ochrony przed zagrożeniami, która identyfikuje potencjalne zagrożenia na urządzeniach z systemem iOS. Zagrożenia te są zgłaszane do aplikacji Portal firmy i pojawiają się tam jako nierozwiązane, niezgodne problemy. Jeśli urządzenie zostanie zidentyfikowane jako niezgodne, wykonywanie następujących czynności może być niemożliwe:

* Łączenie z firmową pocztą e-mail
* Łączenie firmową siecią Wi-Fi
* Łączenie z usługą SharePoint Online
* Synchronizowanie plików firmowych z usługą OneDrive
* Uzyskiwanie dostępu do aplikacji firmowych

W tym artykule opisano sposób rozpoznawania alertów zagrożeń aplikacji Zimperium zIPS oraz działania, które należy podjąć, aby je rozwiązać. 

## <a name="troubleshoot-virus-or-security-threat"></a>Rozwiązywanie problemów związanych z zagrożeniem ze strony wirusa lub zagrożeniem dla bezpieczeństwa  
W przypadku wykrycia zagrożenia wirusowego lub zagrożenia dla bezpieczeństwa aplikacja Zimperium zIPS wymusi ograniczenia zgodnie z zasadami dostępu organizacji. Zasady dostępu w firmie mogą uniemożliwiać dostęp do firmowej sieci, aplikacji i poczty e-mail z urządzenia.  

Aplikacja Zimperium zIPS wyświetli monit o podjęcie działania w celu odzyskania utraconego dostępu. Wybierz zagrożenie i wykonaj instrukcje w aplikacji, aby rozwiązać problem.

Ponieważ aplikacja jest zintegrowana z firmowym dostawcą zarządzania urządzeniami przenośnymi, zobaczysz również ostrzeżenie o ograniczonym dostępie w aplikacji Portal firmy. Ostrzeżenie zawiera instrukcję o otworzeniu aplikacji Zimperium zIPS w celu rozwiązania zagrożenia wirusowego lub bezpieczeństwa.  

  ![Zrzut ekranu przedstawiający stronę urządzenia w witrynie Portal firmy z ostrzeżeniem aplikacji Zimperium zIPS.](./media/CP-lookout-virus-banner-1808.png)  
  
## <a name="troubleshoot-an-app-threat"></a>Rozwiązywanie problemów z zagrożeniem ze strony aplikacji

Jeśli zainstalujesz aplikację, która zostanie uznana za zagrożenie dla urządzenia, otrzymasz powiadomienie w aplikacji Zimperium zIPS. Jeśli ta aplikacja pozostaje na urządzeniu, nie będzie można uzyskać dostępu do zasobów firmy.  

Aby rozwiązać problem, wybierz aplikację z listy zagrożeń w aplikacji Zimperium zIPS. Następnie wykonaj instrukcje wyświetlane na ekranie, aby usunąć i odinstalować aplikację.  

Nadal potrzebujesz pomocy? Skontaktuj się z działem pomocy technicznej Twojej firmy. Odpowiednie informacje kontaktowe możesz znaleźć w [witrynie aplikacji Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).   
