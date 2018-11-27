---
title: Tworzenie powiadomień aplikacji dla urządzeń z systemem iOS — Microsoft Intune — Azure | Microsoft Docs
description: Dodawaj lub twórz powiadomienia aplikacji dla systemu iOS w usłudze Microsoft Intune. Wybierz, które aplikacje mają wysyłać powiadomienia, skonfiguruj ustawienia powiadomień na ekranie blokady, włącz dźwięk, wybierz typ alertu i dodaj znaczek.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: bda26d1d-2a3b-4669-adf8-a5aa7f994916
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 2bf4919fecbba8ad4c0f3b8535adf8b97a35342e
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52182197"
---
# <a name="configure-app-notifications-settings-on-ios-devices-in-intune"></a>Konfigurowanie ustawień powiadomień aplikacji na urządzeniach z systemem iOS w usłudze Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Skonfiguruj sposób, w jaki aplikacje na urządzeniu z systemem iOS wysyłają powiadomienia. Te ustawienia obsługują nadzorowane urządzenia z systemem iOS w wersji 9.3 i nowszych.

## <a name="add-the-app-notification"></a>Dodawanie powiadomienia aplikacji

1. Zaloguj się do witryny [Azure Portal](https://portal.azure.com).
2. W profilu systemu iOS lub macOS wybierz pozycję **Funkcje urządzenia**. Obszar [Funkcje urządzenia z systemem iOS lub macOS](device-features-configure.md) zawiera listę czynności, które należy wykonać, aby utworzyć profil.
3. Wybierz pozycję **Powiadomienia w aplikacji (tylko nadzorowane)**, a następnie pozycję **Dodaj**: ![Dodaj powiadomienie w aplikacji w profilu systemu iOS lub macOS w usłudze Intune](./media/ios-macos-app-notifications.png).
4. Wprowadź następujące właściwości:

   - **Identyfikator pakietu aplikacji** — wprowadź **identyfikator pakietu aplikacji**, którą chcesz skonfigurować. Aby uzyskać pomoc, zobacz **Identyfikatory pakietu dla wbudowanych aplikacji systemu iOS** w tym temacie.
   - **Nazwa aplikacji** — wprowadź nazwę aplikacji, którą chcesz skonfigurować. Ta nazwa nie jest wyświetlana na urządzeniu i ma na celu ułatwienie identyfikacji aplikacji na liście.
   - **Wydawca** — wprowadź wydawcę aplikacji, którą chcesz skonfigurować. Ta nazwa wydawcy nie jest wyświetlana na urządzeniu i ma na celu ułatwienie identyfikacji aplikacji na liście.
   - **Powiadomienia** — włącz lub wyłącz powiadomienia wysyłane z aplikacji do urządzenia. Jeśli to ustawienie zostanie wyłączone, zostaną wyłączone także następujące ustawienia.
     - **Pokaż w centrum powiadomień** — włączenie tego ustawienia powoduje zezwolenie aplikacji na wyświetlanie powiadomień w centrum powiadomień na urządzeniu.
     - **Pokaż na ekranie blokady** — włączenie tego ustawienia powoduje, że powiadomienia z aplikacji będą wyświetlane na ekranie blokady urządzenia.
     - **Typ alertu** — wybierz typ powiadomienia, które będzie wyświetlane po odblokowaniu urządzenia:
       - **Brak** — nie zostanie wyświetlone żadne powiadomienie.
       - **Transparent** — zostanie na krótko wyświetlony transparent z powiadomieniem.
       - **Modalne** — zostanie wyświetlone powiadomienie, które użytkownik będzie musiał ręcznie zamknąć przed kontynuowaniem korzystania z urządzenia.
     - **Znaczek na ikonie aplikacji** — włącz to ustawienie, aby dodać na ikonie aplikacji znaczek, który będzie sygnalizować powiadomienie wysłane z aplikacji.
     - **Dźwięki** — po włączeniu tego ustawienia w przypadku dostarczania powiadomienia zostanie odtworzony dźwięk.

5. Kontynuuj konfigurowanie dla kolejnych aplikacji, zgodnie z potrzebami. Po zakończeniu dodawania aplikacji wybierz przycisk **OK**.
6. Wybierz pozycję **Utwórz**, aby zapisać profil.

## <a name="bundle-id-reference-for-built-in-ios-apps"></a>Identyfikatory pakietu dla wbudowanych aplikacji systemu iOS

Następująca lista zawiera identyfikatory pakietu typowych wbudowanych aplikacji systemu iOS. Aby wyszukać identyfikatory pakietu innych aplikacji, najlepiej skontaktuj się z dostawcą oprogramowania.

|||
|-|-|
|Nazwa aplikacji|Identyfikator pakietu|
|App Store|com.apple.AppStore|
|Kalkulator|com.apple.calculator|
|Kalendarz|com.apple.mobilecal|
|Aparat fotograficzny|com.apple.camera|
|Zegar|com.apple.mobiletimer|
|Kompas|com.apple.compass|
|Kontakty|com.apple.MobileAddressBook|
|FaceTime|com.apple.facetime|
|Moi znajomi|com.apple.mobileme.fmf1|
|Znajdź mój iPhone|com.apple.mobileme.fmip1|
|Centrum gier|com.apple.gamecenter|
|GarageBand|com.apple.mobilegarageband|
|Kondycja|com.apple.Health|
|iBooks|com.apple.iBooks|
|iTunes Store|com.apple.MobileStore|
|iTunes U|com.apple.itunesu|
|Keynote|com.apple.Keynote|
|Mail|com.apple.mobilemail|
|Mapy|com.apple.Maps|
|Komunikaty|com.apple.MobileSMS|
|Muzyka|com.apple.Music|
|News|com.apple.news|
|Uwagi|com.apple.mobilenotes|
|Liczby|com.apple.Numbers|
|Pages|com.apple.Pages|
|Photo Booth|com.apple.Photo-Booth|
|Zdjęcia|com.apple.mobileslideshow|
|Podcasty|com.apple.podcasts|
|Przypomnienia|com.apple.reminders|
|Safari|com.apple.mobilesafari|
|Ustawienia|com.apple.Preferences|
|Giełda|com.apple.stocks|
|Porady|com.apple.tips|
|Filmy|com.apple.videos|
|Dyktafon|com.apple.VoiceMemos|
|Wallet|com.apple.Passbook|
|Zegarek|com.apple.Bridge|
|Pogoda|com.apple.weather|

## <a name="next-steps"></a>Następne kroki

Przypisz profil urządzenia do wybranych grup. Aby poznać czynności, które należy wykonać, zobacz [Przypisywanie profilów urządzeń](device-profile-assign.md).