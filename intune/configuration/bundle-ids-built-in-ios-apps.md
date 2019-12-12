---
title: Identyfikatory pakietów systemu iOS dla aplikacji wbudowanych w usłudze Microsoft Intune — Azure | Microsoft Docs
titleSuffix: ''
description: Zobacz listę identyfikatorów pakietów dla wbudowanych aplikacji dla systemu iOS. Te identyfikatory pakietów umożliwiają jawne zezwalanie na używanie aplikacji w zasadach i profilach konfiguracji urządzeń w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/25/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: ''
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b7e2bd869f898bbe7f894cfd9e9c767c8b42e9c4
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "74465636"
---
# <a name="bundle-ids-for-built-in-ios-apps-you-can-use-in-intune"></a>Identyfikatory pakietów dla wbudowanych aplikacji dla systemu iOS, których można używać w usłudze Intune

Podczas konfigurowania funkcji na urządzeniach z systemem iOS można również dodawać wbudowane aplikacje. W tym artykule wymieniono identyfikatory pakietów niektórych typowych wbudowanych aplikacji dla systemu iOS. Aby wyszukać identyfikatory pakietu innych aplikacji, skontaktuj się z dostawcą oprogramowania. Zobacz listę [identyfikatorów pakietów dla systemu iOS](https://support.apple.com/guide/mdm/ios-bundle-ids-mdm90f60c1ce/web) (otwiera witrynę firmy Apple).

## <a name="bundle-ids"></a>Identyfikatory pakietów

| Identyfikator pakietu                   | Nazwa aplikacji     | Wydawca |
|-----------------------------|--------------|-----------|
| com. Apple. Store             | App Store    | Apple     |
| com.apple.calculator        | Kalkulator   | Apple     |
| com.apple.mobilecal         | Kalendarz     | Apple     |
| com.apple.camera            | Aparat fotograficzny       | Apple     |
| com.apple.mobiletimer       | Zegar        | Apple     |
| com. Apple. clips             | Film        | Apple     |
| com.apple.compass           | Kompas      | Apple     |
| com.apple.MobileAddressBook | Kontakty     | Apple     |
| com.apple.facetime          | FaceTime     | Apple     |
| com.apple.DocumentsApp      | Pliki        | Apple     |
| com.apple.mobileme.fmf1     | Moi znajomi | Apple     |
| com.apple.mobileme.fmip1    | Znajdź mój iPhone  | Apple     |
| com.apple.gamecenter        | Centrum gier  | Apple     |
| com.apple.mobilegarageband  | GarageBand   | Apple     |
| com.apple.Health            | Kondycja       | Apple     |
| com.apple.Home              | Domowy         | Apple     |
| com.apple.iBooks            | iBooks       | Apple     |
| com.apple.iMovie            | iMovie       | Apple     |
| com.apple.itunesconnect.mobile | iTunes Connect | Apple |
| com.apple.MobileStore       | iTunes Store | Apple     |
| com.apple.itunesu           | iTunes U     | Apple     |
| com.apple.Keynote           | Keynote      | Apple     |
| com.apple.mobilemail        | Mail         | Apple     |
| com.apple.Maps              | Mapy         | Apple     |
| com. Apple. Measure           | Miara      | Apple     |
| com.apple.MobileSMS         | Komunikaty     | Apple     |
| com.apple.Music             | Muzyka        | Apple     |
| com.apple.news              | News         | Apple     |
| com.apple.mobilenotes       | Uwagi        | Apple     |
| com.apple.Numbers           | Liczby      | Apple     |
| com.apple.Pages             | Pages        | Apple     |
| com.apple.mobilephone       | Telefon        | Apple     |
| com.apple.Photo-Booth       | Photo Booth  | Apple     |
| com.apple.mobileslideshow   | Zdjęcia       | Apple     |
| com.apple.podcasts          | Podcasty     | Apple     |
| com.apple.reminders         | Przypomnienia    | Apple     |
| com.apple.mobilesafari      | Safari       | Apple     |
| com.apple.Preferences       | Ustawienia     | Apple     |
| com. Apple. shortcuts         | Skróty    | Apple     |
| com.apple.SiriViewService   | Siri         | Apple     |
| com.apple.stocks            | Giełda       | Apple     |
| com.apple.tips              | Porady         | Apple     |
| com.apple.tv                | TV           | Apple     |
| com.apple.videos            | Filmy       | Apple     |
| com.apple.VoiceMemos        | Dyktafon   | Apple     |
| com.apple.Passbook          | Wallet       | Apple     |
| com.apple.Bridge            | Zegarek        | Apple     |
| com.apple.weather           | Pogoda      | Apple     |      

## <a name="next-steps"></a>Następne kroki

Te identyfikatory pakietów umożliwiają konfigurowanie [funkcji urządzeń](ios-device-features-settings.md) oraz [ograniczanie niektórych ustawień lub zezwalanie na ich używanie ](device-restrictions-ios.md) na urządzeniach z systemem iOS.
