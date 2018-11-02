---
title: Korzystanie z aplikacji zarządzanych na urządzeniu z systemem Android | Microsoft Docs
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ed10a62c-b026-4ad3-ac41-641933522df2
searchScope:
- User help
ROBOTS: ''
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 60df25542e69422e15a2a57473a3fbfa2cc413a5
ms.sourcegitcommit: 604b29c480b24270b5debc3e5f3141c8149ee6ed
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2018
ms.locfileid: "49959506"
---
# <a name="use-managed-apps-on-your-android-device"></a>Korzystanie z aplikacji zarządzanych na urządzeniu z systemem Android
Aplikacje zarządzane są konfigurowane tak, aby spełniały wymagania organizacji dotyczące bezpieczeństwa oraz chroniły dane służbowe. Te aplikacje są udostępniane w urządzeniu z możliwością automatycznego instalowania lub używania. 

Zanim otrzymasz i zainstalujesz aplikację zarządzaną, organizacja skonfiguruje jej uprawnienia. Mogą one ograniczać funkcjonalność aplikacji lub interakcje użytkowników, aby chronić danych aplikację przed udostępnianiem lub używaniem przez nieautoryzowane osoby. Organizacja może na przykład zablokować kopiowanie i wklejanie w aplikacji. Może także ograniczyć zapisywanie danych w lokalnym magazynie urządzenia.

Aby zmaksymalizować ochronę danych, organizacja może skonfigurować kilka aplikacji zarządzanych do współpracy. Przykład:
1. Łączysz się z siecią organizacji w aplikacji Managed Browser, takiej jak program Microsoft Edge.
2. Klikasz link, aby otworzyć plik prezentacji współpracownika.
3. Odpowiednia aplikacja zarządzana, taka jak program Microsoft PowerPoint, otwiera plik.

Organizacje mogą wymagać używania aplikacji zarządzanej do wykonania określonego zadania, takiego jak otwieranie pliku służbowego lub uzyskiwanie dostępu do linku internetowego. Jeśli nie masz aplikacji, kontynuowanie zadania może okazać się niemożliwe. Niektóre aplikacje zarządzane są udostępniane do zainstalowania, ale nie są wymagane.

## <a name="how-do-i-know-im-using-a-managed-app"></a>Jak mogę sprawdzić, czy używam aplikacji zarządzanej?
Gdy po raz pierwszy uzyskujesz dostęp do danych służbowych w aplikacji zarządzanej, jest wyświetlany komunikat podobny do poniższego przykładowego zrzutu ekranu. Komunikat zawiera monit o ponowne uruchomienie aplikacji przed kontynuowaniem.

![Zrzut ekranu przedstawiający komunikat wyświetlany, gdy użytkownik otwiera aplikację zarządzaną w urządzeniu. Komunikat to: „Twoja organizacja nie chroni teraz danych w tej aplikacji. Aby kontynuować, musisz ponownie uruchomić aplikację”. Pod komunikatem znajduje się przycisk OK.](./media/managed-apps-message.png)

## <a name="commonly-managed-apps"></a>Popularne aplikacje zarządzane  
Oto przykładowe często wymagane lub dostępne aplikacje zarządzane w miejscach pracy i nauki:

-   Microsoft Edge

-   Microsoft Outlook

-   Microsoft Word, Excel i PowerPoint

## <a name="how-do-i-get-managed-apps"></a>Jak uzyskać aplikacje zarządzane?
Najpierw należy zainstalować aplikację Portal firmy, a w razie potrzeby objąć urządzenie zarządzaniem. Następnie należy skorzystać z jednego z trzech sposobów uzyskania aplikacji zarządzanych.
* Organizacja automatycznie instaluje aplikacje w urządzeniu w momencie rejestracji. Aby uzyskać informacje na temat rejestracji, zobacz [Rejestrowanie urządzenia w usłudze Intune](enroll-your-device-in-Intune-android.md).
* Organizacja udostępnia aplikacje zarządzane przeznaczone dla Ciebie w aplikacji Portal firmy. Przejdź do witryny internetowej lub aplikacji Portal firmy, aby wyszukiwać, przeglądać i instalować te aplikacje. 
* Instalujesz aplikację ze sklepu Google Play, a następnie logujesz się do niej przy użyciu konta służbowego.  

## <a name="what-can-my-company-support-manage-in-an-app"></a>Czym dział pomocy technicznej mojej firmy może zarządzać w aplikacji?
Poniższa lista zawiera opis ustawień, którymi dział pomocy technicznej w firmie może zarządzać w aplikacji. Te ustawienia mają wpływ na sposób wyświetlania danych służbowych w urządzeniu, uzyskiwania do nich dostępu oraz używania ich w inny sposób:

* Dostęp do określonych witryn sieci Web  

* Dostęp do wewnętrznych witryn internetowych firmy przy użyciu programu Edge i serwera proxy usługi Azure Active Directory  

* Minimalna wersja aplikacji, wersja systemu operacyjnego

* Możliwość udostępniania i przenoszenia danych między aplikacjami  

* Sposób i lokalizacja zapisywania plików  

* Funkcja kopiowania i wklejania  

* Wymagania dotyczące uzyskiwania dostępu za pomocą numeru PIN  

* Sposób logowania przy użyciu poświadczeń firmowych  

* Możliwość tworzenia kopii zapasowej danych w chmurze  

* Możliwość tworzenia zrzutów ekranu  

* Wymagania dotyczące szyfrowania danych  

Aby uzyskać więcej informacji o aplikacjach zarządzanych na Twoim urządzeniu, skontaktuj się z działem pomocy technicznej Twojej firmy. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).
