---
title: Aplikacje dla systemu Android z zasadami ochrony aplikacji
description: W tym temacie opisano, czego można oczekiwać, gdy aplikacja jest zarządzana przy użyciu zasad ochrony aplikacji.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 02/15/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 53c8e2ad-f627-425b-9adc-39ca69dbb460
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: a7aa439fcf60173cac71f0fc71ebac481660c785
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514697"
---
# <a name="what-to-expect-when-your-android-app-is-managed-by-app-protection-policies"></a>Czego można oczekiwać, gdy aplikacja dla systemu Android jest zarządzana przy użyciu zasad ochrony aplikacji

W tym artykule opisano środowisko użytkownika aplikacji z zasadami ochrony aplikacji. Zasady ochrony aplikacji są stosowane tylko wtedy, gdy aplikacje są używane do celów służbowych, czyli na przykład podczas korzystania z aplikacji przy użyciu konta służbowego lub uzyskiwania dostępu do plików przechowywanych w lokalizacji usługi OneDrive dla Firm.

## <a name="access-apps"></a>Dostęp do aplikacji

Aplikacja Portal firmy jest wymagana dla wszystkich aplikacji skojarzonych z zasadami ochrony aplikacji na urządzeniach z systemem Android.

Na urządzeniach, które nie zostały zarejestrowane w usłudze Intune, musi być zainstalowana aplikacja Portal firmy. Użytkownik nie musi jednak jej uruchamiać ani się w niej logować, aby korzystać z aplikacji zarządzanych przy użyciu zasad ochrony aplikacji.

Aplikacja Portal firmy zapewnia usłudze Intune możliwość współużytkowania danych w bezpiecznej lokalizacji. W związku z tym aplikacja Portal firmy jest wymagana dla wszystkich aplikacji skojarzonych z zasadami ochrony aplikacji, nawet jeśli urządzenie nie jest zarejestrowane w usłudze Intune.

## <a name="use-apps-with-multi-identity-support"></a>Korzystanie z aplikacji z obsługą wielu tożsamości

Zasady ochrony aplikacji są stosowane tylko w kontekście służbowym. W związku z tym aplikacja może zachowywać się inaczej w zależności od tego, czy jest używana w kontekście służbowym czy osobistym.

Na przykład podczas uzyskiwania dostępu do danych służbowych użytkownik zobaczy monit o podanie numeru PIN. W przypadku **aplikacji Outlook** użytkownik musi podać numer PIN podczas uruchamiania aplikacji. Korzystając z **aplikacji OneDrive**, użytkownik jest monitowany o numer PIN przy podawaniu konta służbowego. W przypadku aplikacji Microsoft **Word**, **PowerPoint** i **Excel** kod PIN trzeba podać w celu uzyskania dostępu do dokumentów przechowywanych w lokalizacji firmowej w usłudze OneDrive dla Firm.

## <a name="manage-user-accounts-on-the-device"></a>Zarządzanie kontami użytkowników na urządzeniu

Aplikacje z obsługą wielu tożsamości umożliwiają użytkownikom dodawanie wielu kont.  Aplikacja usługi Intune obsługuje tylko jedno konto zarządzane.  Aplikacja usługi Intune nie ogranicza liczby kont niezarządzanych.

Jeśli w aplikacji istnieje konto zarządzane:

* Jeśli użytkownik podejmuje próbę dodania drugiego konta zarządzanego, jest proszony o wybranie konta zarządzanego, które ma być używane.  Drugie konto zostanie usunięte.
* Jeśli administrator IT dodaje zasady do drugiego istniejącego konta, użytkownik jest proszony o wybranie konta zarządzanego do użycia.  Drugie konto zostanie usunięte.

Zapoznaj się z przykładowym scenariuszem poniżej, aby lepiej zrozumieć zasady obsługi wielu kont użytkowników.

Użytkownik A pracuje dla dwóch firm — **Firmy X** i **Firmy Y**. Użytkownik A ma konto służbowe dla każdej firmy, a obaj użytkownicy wdrażają zasady ochrony aplikacji za pomocą usługi Intune. **Firma X** wdraża zasady ochrony aplikacji **przed** **Firmą Y**. Zasady ochrony aplikacji zostaną zastosowane na koncie skojarzonym z **Firmą X**, ale nie na koncie skojarzonym z Firmą Y. Jeśli chcesz, aby konto użytkownika skojarzone z Firmą Y było zarządzane zgodnie z zasadami ochrony aplikacji, musisz usunąć konto użytkownika skojarzone z Firmą X i dodać konto skojarzone z Firmą Y.

### <a name="add-a-second-account"></a>Dodawanie drugiego konta

#### <a name="android"></a>Android

Jeśli korzystasz z urządzenia z systemem Android, może zostać wyświetlony komunikat o blokadzie zawierający instrukcje usunięcia istniejącego konta i dodania nowego.  Aby usunąć istniejące konto, przejdź do pozycji **Ustawienia &gt;Ogólne &gt; Menedżer aplikacji &gt;Portal firmy**. Następnie wybierz pozycję **Wyczyść dane**.

![Zrzut ekranu komunikatu o błędzie i instrukcjami dotyczącymi usunięcia konta](./media/end-user-mam-apps-android/Android_SwitchUser.png)

## <a name="view-media-files-with-the-azure-information-protection-app"></a>Wyświetlanie plików multimedialnych przy użyciu aplikacji Azure Information Protection

Aby wyświetlać firmowe pliki audio i wideo, pliki PDF i pliki obrazów na urządzeniach z systemem Android, użyj [aplikacji Azure Information Protection](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer) (wcześniej znanej jako aplikacja do tworzenia i przetwarzania dokumentów chronionych usługami Rights Management).

Pobierz tę aplikację ze sklepu Google Play.  

Obsługiwane są następujące typy plików:

* **Audio:** AAC LC, HE-AACv1 (AAC+), HE-AACv2 (rozszerzone AAC+), AAC ELD (rozszerzone AAC o małym opóźnieniu), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Ogg Vorbis, PCM/WAVE
* **Wideo:** H.263, H.264 AVC, MPEG-4 SP, VP8
* **Obraz:** jpg, pjpg, png, ppng, bmp, pbmp, gif, pgif, jpeg, pjpeg
* **Dokumenty:** PDF, PPDF

|**pfile**|
|----|
|Pfile jest ogólnym formatem „otoki” dla plików chronionych, który hermetyzuje zaszyfrowaną zawartość i licencje usługi Azure Information Protection. Może służyć do ochrony pliku dowolnego typu.|

## <a name="next-steps"></a>Następne kroki
[Czego można oczekiwać, gdy aplikacja systemu iOS/iPadOS jest zarządzana przy użyciu zasad ochrony aplikacji](end-user-mam-apps-ios.md)
