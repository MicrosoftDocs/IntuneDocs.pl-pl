---
title: "Ustawienia powiadomień aplikacji dla urządzeń z systemem iOS w usłudze Intune"
titlesuffix: Azure portal
description: "Informacje na temat ustawień służących do kontrolowania powiadomień z aplikacji na urządzeniach z systemem iOS."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bda26d1d-2a3b-4669-adf8-a5aa7f994916
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 91e4b6197c7606a70862ad5fb12b10b5e0f3ed81
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/25/2018
---
# <a name="intune-app-notifications-settings-for-ios-devices"></a>Ustawienia powiadomień aplikacji dla urządzeń z systemem iOS w usłudze Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Umożliwia skonfigurowanie sposobu, w jaki aplikacje zainstalowane na urządzeniu wysyłają powiadomienia. Te ustawienia obsługują nadzorowane urządzenia z systemem iOS w wersji 9.3 i nowszych.

## <a name="configure-settings"></a>Konfigurowanie ustawień

1. W bloku Funkcje urządzenia wybierz pozycję **Powiadomienia w aplikacji (tylko nadzorowane)**.
2. W bloku **Powiadomienia aplikacji** wybierz pozycję **Dodaj**, a następnie skonfiguruj następujące wartości:
    - **Identyfikator pakietu aplikacji** — wprowadź **identyfikator pakietu aplikacji**, którą chcesz skonfigurować. Aby uzyskać pomoc, zobacz **Identyfikatory pakietu dla wbudowanych aplikacji systemu iOS** w dalszej części tego tematu.
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
3. Kontynuuj konfigurowanie dla kolejnych aplikacji, zgodnie z potrzebami. Gdy skończysz, wybierz przycisk **OK**.
4. Wybieraj przycisk **OK**, aż powrócisz do bloku **Utwórz profil**, a następnie wybierz pozycję **Utwórz**. 


## <a name="bundle-id-reference-for-built-in-ios-apps"></a>Identyfikatory pakietu dla wbudowanych aplikacji systemu iOS

Ta lista zawiera identyfikatory pakietu typowych wbudowanych aplikacji systemu iOS. Aby wyszukać identyfikatory pakietu innych aplikacji, skontaktuj się z dostawcą oprogramowania. 

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

Teraz można przypisać profil urządzenia do wybranych grup. Aby uzyskać szczegółowe informacje, zobacz [Przypisywanie profilów urządzeń](device-profile-assign.md).
