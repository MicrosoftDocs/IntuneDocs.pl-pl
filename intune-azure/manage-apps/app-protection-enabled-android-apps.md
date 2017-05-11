---
title: Aplikacje dla systemu Android z zasadami ochrony aplikacji
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: w tym temacie opisano, czego można oczekiwać, gdy aplikacja dla systemu Android jest zarządzana przy użyciu zasad ochrony aplikacji."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a6816285-8e43-4dc8-bca0-e80ec5ef01e6
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 896a7143bc0b7ec80f69482681f4ed17d79661d4
ms.contentlocale: pl-pl
ms.lasthandoff: 02/18/2017


---

# <a name="what-to-expect-when-your-android-app-is-managed-by-app-protection-policies"></a>Czego można oczekiwać, gdy aplikacja dla systemu Android jest zarządzana przy użyciu zasad ochrony aplikacji 
[!INCLUDE[azure_preview](../includes/azure_preview.md)] W tym temacie opisano środowisko użytkownika aplikacji z zasadami ochrony aplikacji. Zasady ochrony aplikacji są stosowane tylko wtedy, gdy aplikacje są używane służbowo, czyli na przykład podczas korzystania z aplikacji przy użyciu konta służbowego lub uzyskiwania dostępu do plików przechowywanych w lokalizacji służbowej w usłudze OneDrive.
##  <a name="accessing-apps"></a>Uzyskiwanie dostępu do aplikacji

Aplikacja Portal firmy jest wymagana dla wszystkich aplikacji skojarzonych z zasadami ochrony aplikacji na urządzeniach z systemem Android.

W przypadku urządzeń, które nie zostały zarejestrowane w usłudze Intune, aplikacja Portal firmy musi zostać zainstalowana na urządzeniu. Użytkownik nie musi jednak jej uruchamiać ani logować się w niej, aby korzystać z aplikacji zarządzanych przy użyciu zasad ochrony aplikacji.
Aplikacja Portal firmy umożliwia usłudze Intune udostępnianie danych w bezpiecznej lokalizacji, przez co jest wymagana, nawet jeśli urządzenie nie jest zarejestrowane w usłudze Intune.


##  <a name="using-apps-with-multi-identity-support"></a>Korzystanie z aplikacji z obsługą wielu tożsamości

Zasady ochrony aplikacji są stosowane tylko podczas służbowego używania aplikacji, więc w zależności od trybu działania (służbowego lub osobistego) aplikacja może zachowywać się różnie.

W przypadku aplikacji, które obsługują wiele tożsamości, usługa Intune stosuje zasady ochrony aplikacji tylko, jeśli użytkownik korzysta z aplikacji służbowo.  Na przykład podczas uzyskiwania dostępu do danych służbowych użytkownik zobaczy monit o podanie kodu PIN.  W przypadku **aplikacji Outlook** użytkownik końcowy musi podać kod PIN podczas uruchamiania aplikacji. W przypadku **aplikacji OneDrive** trzeba to zrobić po wybraniu konta służbowego.  W przypadku aplikacji Microsoft **Word**, **PowerPoint* i* *Excel** kod PIN trzeba podać w celu uzyskania dostępu do dokumentów przechowywanych w lokalizacji firmowej w usłudze OneDrive dla Firm.
##  <a name="managing-user-accounts-on-the-device"></a>Zarządzanie kontami użytkowników na urządzeniu

Usługa Intune obsługuje wdrażanie zasad ochrony aplikacji na koncie tylko jednego użytkownika dla każdego urządzenia.

* W zależności od używanej aplikacji drugi użytkownik może być blokowany na urządzeniu. Jednak we wszystkich przypadkach zasady dotyczą tylko pierwszego użytkownika, który pobierze zasady ochrony aplikacji.

  * Programy **Microsoft Word**, **Excel** i **PowerPoint** nie blokują drugiego konta użytkownika, ale zasady ochrony aplikacji nie są stosowane do tego konta.

  * W przypadku **aplikacji OneDrive i Outlook** możesz używać tylko jednego konta służbowego.  Dodawanie większej liczby kont służbowych w tych aplikacjach jest zablokowane.  Możesz natomiast usunąć użytkownika na urządzeniu i dodać innego użytkownika.


* Jeśli urządzenie ma wiele istniejących kont użytkowników przed wdrożeniem zasad ochrony aplikacji, pierwsze konto, na którym wdrożono zasady ochrony aplikacji, jest zarządzane przez zasady ochrony aplikacji usługi Intune.


Zapoznaj się z przykładowym scenariuszem poniżej, aby lepiej zrozumieć zasady traktowania wielu kont użytkowników.

Użytkownik A pracuje dla dwóch firm — **Firmy X** i **Firmy Y**. Użytkownik A ma konto służbowe dla każdej firmy, a obaj użytkownicy wdrażają zasady ochrony aplikacji za pomocą usługi Intune. **Firma X** wdraża zasady ochrony aplikacji **przed** **Firmą Y**. Zasady ochrony aplikacji zostaną zastosowane na koncie skojarzonym z **Firmą X**, ale nie na koncie skojarzonym z Firmą Y. Jeśli chcesz, aby konto użytkownika skojarzone z Firmą Y było zarządzane przez zasady ochrony aplikacji, musisz usunąć konto użytkownika skojarzone z Firmą X.
### <a name="adding-a-second-account"></a>Dodawanie drugiego konta
####  <a name="android"></a>Android
Jeśli korzystasz z urządzenia z systemem Android, może zostać wyświetlony komunikat o blokadzie z instrukcjami usunięcia istniejącego konta i dodania nowego.  Aby usunąć istniejące konto, przejdź do pozycji **Ustawienia &gt; Ogólne &gt; Menedżer aplikacji &gt; Portal firmy, a następnie wybierz pozycję „Wyczyść dane”**.

![Zrzut ekranu komunikatu o błędzie i instrukcjami dotyczącymi usunięcia konta](../media/android-switch-user.png)

##  <a name="viewing-media-files-with-the-azure-information-protection-app-previously-known-as-rights-management-sharing-app"></a>Wyświetlanie plików multimedialnych przy użyciu aplikacji Azure Information Protection (znaną wcześniej jako aplikacja Rights Management sharing)
Aby wyświetlać firmowe pliki audio i wideo, pliki PDF i pliki obrazów na urządzeniach z systemem Android, użyj [aplikacji Azure Information Protection](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer).

Pobierz tę aplikację ze sklepu Google Play.  

Obsługiwane są następujące typy plików:

* **Audio:** AAC LC, HE-AACv1 (AAC+), HE-AACv2 (rozszerzone AAC+), AAC ELD (rozszerzone AAC o małym opóźnieniu), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Ogg Vorbis, PCM/WAVE.
* **Wideo:** H.263, H.264 AVC, MPEG-4 SP, VP8.
* **Obraz:** jpg, pjpg, png, ppng, bmp, pbmp, gif, pgif, jpeg, pjpeg.
* **Dokumenty:** PDF, PPDF

------------
|**pfile**|**tekst**|
|----|----|
|Pfile jest ogólnym formatem „otoki” dla plików chronionych, który hermetyzuje zaszyfrowaną zawartość i licencje usługi Azure Information Protection oraz może służyć do ochrony dowolnego typu pliku.|Pliki tekstowe, w tym XML, CSV itp., można otworzyć w celu wyświetlania w aplikacji nawet wtedy, gdy są chronione. Typy plików: txt, ptxt, csv, pcsv, log, plog, xml, pxml.|
---------------
## <a name="next-steps"></a>Następne kroki
[Czego można oczekiwać, gdy aplikacja dla systemu iOS jest zarządzana przy użyciu zasad ochrony aplikacji](app-protection-enabled-ios-apps.md)

### <a name="see-also"></a>Zobacz także
[Tworzenie i wdrażanie zasad ochrony aplikacji przy użyciu usługi Microsoft Intune](app-protection-policies.md)

