---
title: Aplikacje dla systemu iOS z zasadami ochrony aplikacji
description: W tym temacie opisano, czego można oczekiwać, gdy aplikacja dla systemu iOS jest zarządzana przy użyciu zasad ochrony aplikacji.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 11/18/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: b57e6525-b57c-4cb4-a84c-9f70ba1e8e19
ms.reviewer: andcerat
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 165ce160339647e396b9cfc3a8374f21c77665f8
ms.sourcegitcommit: f9dc50642efa8656054ef67f9335b9b46b655f93
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/02/2020
ms.locfileid: "75606625"
---
# <a name="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies"></a>Czego można oczekiwać, gdy aplikacja dla systemu iOS jest zarządzana przy użyciu zasad ochrony aplikacji

Zasady ochrony aplikacji usługi Intune mają zastosowanie do aplikacji, które są używane w miejscu pracy lub nauki. Oznacza to, że gdy pracownicy i uczniowie korzystają z aplikacji w kontekście osobistym, mogą nie zauważyć żadnych różnic w środowisku pracy. W kontekście służbowym mogą jednak otrzymywać monity o podjęcie decyzji dotyczących kont, zaktualizowanie ich ustawień lub skontaktowanie się z Tobą w celu uzyskania pomocy. Skorzystaj z tego artykułu, aby dowiedzieć się, co może się zdarzyć, gdy użytkownicy podejmą próbę uzyskania dostępu do aplikacji chronionych przez usługę Intune i ich używania.  

## <a name="access-apps"></a>Dostęp do aplikacji

Jeśli urządzenie **nie jest zarejestrowane w usłudze Intune**, użytkownik zostanie poproszony o ponowne uruchomienie aplikacji przy jej pierwszym użyciu. Aby do aplikacji można było zastosować zasady ochrony aplikacji, należy ponownie uruchomić urządzenie.

<!--- The following screenshot from the Skype app illustrates this restart request: --->

<!---  ![Screenshot of the iOS device showing PIN prompt](./media/end-user-mam-apps-ios/iOS_AppPINPrompt.png) --->

Na urządzeniach, które są **zarejestrowane do celów zarządzania w usłudze Intune**, użytkownik zobaczy komunikat, że jego aplikacja jest teraz zarządzana.

## <a name="use-apps-with-multi-identity-support"></a>Korzystanie z aplikacji z obsługą wielu tożsamości

Aplikacje z obsługą wielu tożsamości umożliwiają używanie różnych kont służbowych i osobistych do uzyskiwania dostępu do tych samych aplikacji. Zasady ochrony aplikacji, takie jak wprowadzanie numeru PIN urządzenia, są aktywowane, gdy użytkownicy uzyskują dostęp do tych aplikacji w kontekście służbowym.   

Monity o podanie numeru PIN mogą być wyświetlane dla użytkowników w różny sposób w zależności od sposobu skonfigurowania zasad.  Można na przykład skonfigurować zasady tak, aby:       
* Program Microsoft Outlook pokazywał użytkownikowi monit o podanie numeru PIN podczas uruchamiania aplikacji. 
* Usługa OneDrive pokazywała użytkownikowi monit o podanie numeru PIN, gdy będzie on logować się do konta służbowego.  
* Programy Microsoft Word, PowerPoint i Excel pokazywały użytkownikowi monit o podanie numeru PIN, gdy będzie on uzyskiwać dostęp do dokumentów przechowywanych w firmowej lokalizacji usługi OneDrive dla Firm.  

- Dowiedz się więcej o aplikacjach, które obsługują [ochronę aplikacji i wiele tożsamości](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) za pomocą usługi Intune.  

## <a name="manage-user-accounts-on-the-device"></a>Zarządzanie kontami użytkowników na urządzeniu  

Zasady ochrony aplikacji usługi Intune ograniczają użytkowników do jednego zarządzanego konta służbowego na aplikację. Zasady ochrony aplikacji nie ograniczają liczby niezarządzanych kont, które użytkownik może dodać.   

- Jeśli użytkownik podejmuje próbę dodania drugiego konta zarządzanego, jest proszony o wybranie konta zarządzanego, które ma być używane. Jeśli użytkownik doda drugie konto, pierwsze konto zostanie usunięte.
- Jeśli zasady ochrony zostaną dodane do innego konta użytkownika, użytkownik zostanie poproszony o wybranie konta zarządzanego do użycia. Drugie konto zostanie usunięte. 

Niektórzy użytkownicy nie będą mieli opcji przełączania się między kontami zarządzanymi ani ich wybierania. Opcja ta nie jest dostępna na urządzeniach, które są:
* Zarządzane przez usługę Intune  
* Zarządzane przez rozwiązania innych firm do zarządzania mobilnością w przedsiębiorstwie i skonfigurowane przy użyciu ustawienia IntuneMAMUPN 

Przykładowy scenariusz poniżej opisuje sposób obsługi wielu kont użytkowników:  

Użytkownik A pracuje dla dwóch firm — **Firmy X** i **Firmy Y**. Użytkownik A ma konto służbowe dla każdej firmy, a obaj użytkownicy wdrażają zasady ochrony aplikacji za pomocą usługi Intune. **Firma X** wdraża zasady ochrony aplikacji **przed** **Firmą Y**. Konto skojarzone z **Firmą X** pobiera zasady ochrony aplikacji jako pierwsze. Jeśli chcesz, aby konto użytkownika skojarzone z Firmą Y było zarządzane zgodnie z zasadami ochrony aplikacji, musisz usunąć konto użytkownika skojarzone z Firmą X i dodać konto użytkownika skojarzone z Firmą Y.  

## <a name="next-steps"></a>Następne kroki

[Czego można oczekiwać, gdy aplikacja systemu Android jest zarządzana przy użyciu zasad ochrony aplikacji](end-user-mam-apps-android.md)
