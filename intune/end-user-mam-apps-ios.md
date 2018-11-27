---
title: Aplikacje dla systemu iOS z zasadami ochrony aplikacji
description: W tym temacie opisano, czego można oczekiwać, gdy aplikacja dla systemu iOS jest zarządzana przy użyciu zasad ochrony aplikacji.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 02/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: b57e6525-b57c-4cb4-a84c-9f70ba1e8e19
ms.reviewer: andcerat
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: bc4ceb6fe8c96a80310ceb58e13850c65b676d0c
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52182385"
---
# <a name="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies"></a>Czego można oczekiwać, gdy aplikacja dla systemu iOS jest zarządzana przy użyciu zasad ochrony aplikacji

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

 W tym temacie opisano środowisko użytkownika aplikacji objętych zasadami ochrony aplikacji. Zasady ochrony aplikacji są stosowane tylko wtedy, gdy aplikacje są używane do celów służbowych, czyli na przykład podczas korzystania z aplikacji przy użyciu konta służbowego lub uzyskiwania dostępu do plików przechowywanych w lokalizacji firmowej w usłudze OneDrive dla Firm.

##  <a name="access-apps"></a>Dostęp do aplikacji

Jeśli urządzenie **nie jest zarejestrowane w usłudze Intune**, użytkownik zostanie poproszony o ponowne uruchomienie aplikacji przy jej pierwszym użyciu. Aby do aplikacji można było zastosować zasady ochrony aplikacji, należy ponownie uruchomić urządzenie.

<!--- The following screenshot from the Skype app illustrates this restart request: --->


<!---  ![Screenshot of the iOS device showing PIN prompt](../media/appmanagement/iOS_AppPINPrompt.png) --->

Na urządzeniach, które są **zarejestrowane do celów zarządzania w usłudze Intune**, użytkownik zobaczy komunikat, że jego aplikacja jest teraz zarządzana.

##  <a name="use-apps-with-multi-identity-support"></a>Korzystanie z aplikacji z obsługą wielu tożsamości

Aplikacje, które obsługują wiele tożsamości, umożliwiają uzyskiwanie dostępu do tych samych aplikacji przy użyciu różnych kont (służbowych i osobistych), podczas gdy zasady ochrony aplikacji są stosowane tylko wtedy, gdy aplikacje są używane w kontekście służbowym.  

Na przykład podczas uzyskiwania dostępu do danych służbowych użytkownik zobaczy monit o podanie numeru PIN. W przypadku **aplikacji Outlook** użytkownik musi podać numer PIN podczas uruchamiania aplikacji. Korzystając z **aplikacji OneDrive**, użytkownik jest monitowany o numer PIN przy podawaniu konta służbowego.  W przypadku aplikacji Microsoft **Word**, **PowerPoint** i **Excel** numer PIN trzeba podać w celu uzyskania dostępu do dokumentów przechowywanych w lokalizacji firmowej w usłudze OneDrive dla Firm.

- Dowiedz się więcej o aplikacjach, które obsługują [ochronę aplikacji i wiele tożsamości](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) za pomocą usługi Intune.

Zasady ochrony aplikacji są stosowane tylko w kontekście służbowym. W związku z tym aplikacja może zachowywać się inaczej w zależności od tego, czy jest używana w kontekście służbowym czy osobistym.

##  <a name="manage-user-accounts-on-the-device"></a>Zarządzanie kontami użytkowników na urządzeniu

Aplikacje z obsługą wielu tożsamości umożliwiają użytkownikom dodawanie wielu kont.  Aplikacja usługi Intune obsługuje tylko jedno konto zarządzane.  Aplikacja usługi Intune nie ogranicza liczby kont niezarządzanych.

Jeśli w aplikacji istnieje konto zarządzane:
*   Jeśli użytkownik podejmuje próbę dodania drugiego konta zarządzanego, jest proszony o wybranie konta zarządzanego, które ma być używane.  Drugie konto zostanie usunięte.
*   Jeśli administrator IT dodaje zasady do drugiego istniejącego konta, użytkownik jest proszony o wybranie konta zarządzanego do użycia.  Drugie konto zostanie usunięte.

Zapoznaj się z przykładowym scenariuszem poniżej, aby lepiej zrozumieć zasady obsługi wielu kont użytkowników.

Użytkownik A pracuje dla dwóch firm — **Firmy X** i **Firmy Y**. Użytkownik A ma konto służbowe dla każdej firmy, a obaj użytkownicy wdrażają zasady ochrony aplikacji za pomocą usługi Intune. **Firma X** wdraża zasady ochrony aplikacji **przed** **Firmą Y**. Konto skojarzone z **Firmą X** pobiera zasady ochrony aplikacji jako pierwsze. Jeśli chcesz, aby konto użytkownika skojarzone z Firmą Y było zarządzane zgodnie z zasadami ochrony aplikacji, musisz usunąć konto użytkownika skojarzone z Firmą X i dodać konto użytkownika skojarzone z Firmą Y.

### <a name="add-a-second-account"></a>Dodawanie drugiego konta

Jeśli korzystasz z urządzenia z systemem iOS, podczas próby dodania drugiego konta służbowego na tym urządzeniu może zostać wyświetlony komunikat o blokadzie. Konta zostaną wyświetlone, umożliwiając wybranie konta do usunięcia.

## <a name="next-steps"></a>Następne kroki
[Czego można oczekiwać, gdy aplikacja systemu Android jest zarządzana przy użyciu zasad ochrony aplikacji](end-user-mam-apps-android.md)
