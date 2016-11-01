---
title: Aplikacje dla systemu Android z zasadami MAM | Microsoft Intune
description: "W tym temacie opisano to, czego można oczekiwać, gdy aplikacja jest zarządzana przy użyciu zasad zarządzania aplikacjami mobilnymi."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 53c8e2ad-f627-425b-9adc-39ca69dbb460
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 389daf0ed39fa2cd4b2e5d6e52cbd6809a568c9e
ms.openlocfilehash: 546b909737b4ea34bd747880fe8ed2d366c6b18a


---

# Oczekiwany przebieg zarządzania aplikacją systemu Android przez zasady zarządzania aplikacjami mobilnymi
W tym temacie opisano środowisko użytkownika aplikacji z zasadami MAM. Zasady zarządzania aplikacjami mobilnymi (MAM, mobile application management) są stosowane tylko wtedy, gdy aplikacje są używane służbowo, czyli na przykład podczas korzystania z aplikacji przy użyciu konta służbowego lub uzyskiwania dostępu do plików przechowywanych w lokalizacji służbowej w usłudze OneDrive.
##  Uzyskiwanie dostępu do aplikacji

Aplikacja Portal firmy jest wymagana dla wszystkich aplikacji skojarzonych z zasadami MAM na urządzeniach z systemem Android.

W przypadku urządzeń, które nie zostały zarejestrowane w usłudze Intune, aplikacja Portal firmy musi zostać zainstalowana na urządzeniu. Użytkownik nie musi jednak jej uruchamiać ani logować się w niej, aby korzystać z aplikacji zarządzanych przy użyciu zasad MAM.
Aplikacja Portal firmy umożliwia usłudze Intune udostępnianie danych w bezpiecznej lokalizacji, przez co jest wymagana, nawet jeśli urządzenie nie jest zarejestrowane w usłudze Intune.


##  Korzystanie z aplikacji z obsługą wielu tożsamości

Zasady MAM są stosowane tylko podczas służbowego używania aplikacji, więc w zależności od trybu działania (służbowego lub osobistego) aplikacja może zachowywać się różnie.

W przypadku aplikacji, które obsługują wiele tożsamości, usługa Intune stosuje zasady MAM tylko, jeśli użytkownik korzysta z aplikacji służbowo.  Na przykład podczas uzyskiwania dostępu do danych służbowych użytkownik zobaczy monit o podanie kodu PIN.  W przypadku **aplikacji Outlook** użytkownik końcowy musi podać kod PIN podczas uruchamiania aplikacji. W przypadku **aplikacji OneDrive** trzeba to zrobić po wybraniu konta służbowego.  W przypadku aplikacji Microsoft **Word**, **PowerPoint* i **Excel** kod PIN trzeba podać w celu uzyskania dostępu do dokumentów przechowywanych w lokalizacji firmowej w usłudze OneDrive dla Firm.
##  Zarządzanie kontami użytkowników na urządzeniu

Usługa Intune obsługuje wdrażanie zasad MAM na koncie tylko jednego użytkownika dla każdego urządzenia.

* W zależności od używanej aplikacji drugi użytkownik może być blokowany na urządzeniu. Jednak we wszystkich przypadkach zasady dotyczą tylko pierwszego użytkownika, który pobierze zasady MAM.

  * Programy **Microsoft Word**, **Excel** i **PowerPoint** nie blokują drugiego konta użytkownika, ale zasady MAM nie są stosowane do tego konta.

  * W przypadku **aplikacji OneDrive i Outlook** możesz używać tylko jednego konta służbowego.  Dodawanie większej liczby kont służbowych w tych aplikacjach jest zablokowane.  Możesz natomiast usunąć użytkownika na urządzeniu i dodać innego użytkownika.


* Jeśli urządzenie ma wiele istniejących kont użytkowników przed wdrożeniem zasad MAM, pierwsze konto, na którym wdrożono zasady MAM, jest zarządzane przez zasady MAM usługi Intune.


Zapoznaj się z przykładowym scenariuszem poniżej, aby lepiej zrozumieć zasady traktowania wielu kont użytkowników.

Użytkownik A pracuje dla dwóch firm — **Firmy X** i **Firmy Y**. Użytkownik A ma konto służbowe dla każdej firmy, a obaj użytkownicy wdrażają zasady MAM za pomocą usługi Intune. **Firma X** wdraża zasady zarządzania aplikacjami mobilnymi **przed** **Firmą Y**. Zasady MAM zostaną zastosowane na koncie skojarzonym z **Firmą X**, ale nie na koncie skojarzonym z Firmą Y. Jeśli chcesz, aby konto użytkownika skojarzone z Firmą Y było zarządzane przez zasady MAM, musisz usunąć konto użytkownika skojarzone z Firmą X.
### Dodawanie drugiego konta
####  Android
Jeśli korzystasz z urządzenia z systemem Android, może zostać wyświetlony komunikat o blokadzie z instrukcjami usunięcia istniejącego konta i dodania nowego.  Aby usunąć istniejące konto, przejdź do pozycji **Ustawienia &gt; Ogólne &gt; Menedżer aplikacji &gt; Portal firmy, a następnie wybierz pozycję „Wyczyść dane”**.

![Zrzut ekranu komunikatu o błędzie i instrukcjami dotyczącymi usunięcia konta](../media/AppManagement/Android_SwitchUser.png)

##  Wyświetlanie plików multimedialnych przy użyciu aplikacji Azure Information Protection (znaną wcześniej jako aplikacja Rights Management sharing)
Aby wyświetlać firmowe pliki audio i wideo, pliki PDF i pliki obrazów na urządzeniach z systemem Android, użyj [aplikacji Azure Information Protection](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer).

Pobierz tę aplikację ze sklepu Google Play.  

Obsługiwane są następujące typy plików:

* **Audio:** AAC LC, HE-AACv1 (AAC+), HE-AACv2 (rozszerzone AAC+), AAC ELD (rozszerzone AAC o małym opóźnieniu), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Ogg Vorbis, PCM/WAVE.
* **Wideo:** H.263, H.264 AVC, MPEG-4 SP, VP8.
* **Obraz:** jpg, pjpg, png, ppng, bmp, pbmp, gif, pgif, jpeg, pjpeg.
* **Dokumenty:** PDF, PPDF

------------
|**pfile**|**text**|
|----|----|
|Pfile jest ogólnym formatem „otoki” dla plików chronionych, który hermetyzuje zaszyfrowaną zawartość i licencje usługi Azure Information Protection oraz może służyć do ochrony dowolnego typu pliku.|Pliki tekstowe, w tym XML, CSV itp., można otworzyć w celu wyświetlania w aplikacji nawet wtedy, gdy są chronione. Typy plików: txt, ptxt, csv, pcsv, log, plog, xml, pxml.|
---------------
## Następne kroki
[Oczekiwany przebieg zarządzania aplikacją systemu iOS przez zasady zarządzania aplikacjami mobilnymi](user-experience-for-mam-enabled-ios-apps-with-microsoft-intune.md)

### Zobacz także
[Tworzenie i wdrażanie zasad zarządzania aplikacjami mobilnymi przy użyciu usługi Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO3-->


