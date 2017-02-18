---
title: Aplikacje dla systemu Android z zasadami MAM | Microsoft Docs
description: "W tym temacie opisano to, czego można oczekiwać, gdy aplikacja jest zarządzana przy użyciu zasad zarządzania aplikacjami mobilnymi."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 10/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 53c8e2ad-f627-425b-9adc-39ca69dbb460
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: aeacfddb3ed42938dd9443e2734222c977436430


---

# <a name="what-to-expect-when-your-android-app-is-managed-by-mam-policies"></a>Oczekiwany przebieg zarządzania aplikacją systemu Android przez zasady zarządzania aplikacjami mobilnymi

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

W tym temacie opisano środowisko użytkownika aplikacji z zasadami zarządzania aplikacjami mobilnymi (MAM). Zasady MAM są stosowane tylko wtedy, gdy aplikacje są używane do celów służbowych, czyli na przykład podczas korzystania z aplikacji przy użyciu konta służbowego lub uzyskiwania dostępu do plików przechowywanych w lokalizacji firmowej w usłudze OneDrive.
##  <a name="access-apps"></a>Dostęp do aplikacji

Aplikacja Portal firmy jest wymagana dla wszystkich aplikacji skojarzonych z zasadami MAM na urządzeniach z systemem Android.

Na urządzeniach, które nie zostały zarejestrowane w usłudze Intune, musi być zainstalowana aplikacja Portal firmy. Użytkownik nie musi jednak jej uruchamiać ani się w niej logować, aby korzystać z aplikacji zarządzanych przy użyciu zasad MAM.

Aplikacja Portal firmy zapewnia usłudze Intune możliwość współużytkowania danych w bezpiecznej lokalizacji. W związku z tym Aplikacja Portal firmy jest wymagana dla wszystkich aplikacji skojarzonych z zasadami MAM, nawet jeśli urządzenie nie jest zarejestrowane w usłudze Intune.


##  <a name="use-apps-with-multi-identity-support"></a>Korzystanie z aplikacji z obsługą wielu tożsamości

Zasady MAM są stosowane tylko w kontekście służbowym. W związku z tym aplikacja może zachowywać się inaczej w zależności od tego, czy jest używana w kontekście służbowym czy osobistym.

Na przykład podczas uzyskiwania dostępu do danych służbowych użytkownik zobaczy monit o podanie numeru PIN. W przypadku **aplikacji Outlook** użytkownik musi podać numer PIN podczas uruchamiania aplikacji. Korzystając z **aplikacji OneDrive**, użytkownik jest monitowany o numer PIN przy podawaniu konta służbowego. W przypadku aplikacji Microsoft **Word**, **PowerPoint** i **Excel** kod PIN trzeba podać w celu uzyskania dostępu do dokumentów przechowywanych w lokalizacji firmowej w usłudze OneDrive dla Firm.

##  <a name="manage-user-accounts-on-the-device"></a>Zarządzanie kontami użytkowników na urządzeniu

Usługa Intune obsługuje wdrażanie zasad MAM tylko na jednym koncie użytkownika dla każdego urządzenia.

* W zależności od używanej aplikacji drugi użytkownik może być blokowany na urządzeniu. Jednak we wszystkich przypadkach zasady dotyczą tylko pierwszego użytkownika, który pobierze zasady MAM.

  * Programy **Microsoft Word**, **Excel** i **PowerPoint** nie blokują drugiego konta użytkownika, ale zasady MAM nie są stosowane do tego konta.

  * W przypadku aplikacji **OneDrive** i **Outlook** można używać tylko jednego konta służbowego.  Nie możesz dodawać wielu kont służbowych dla tych aplikacji.  Możesz natomiast usunąć użytkownika na urządzeniu i dodać innego użytkownika.


* Jeśli urządzenie ma wiele istniejących kont użytkowników przed wdrożeniem zasad MAM, pierwsze konto, na którym wdrożono zasady MAM, jest zarządzane według zasad MAM usługi Intune.


Zapoznaj się z przykładowym scenariuszem poniżej, aby lepiej zrozumieć zasady obsługi wielu kont użytkowników.

Użytkownik A pracuje dla dwóch firm — **Firmy X** i **Firmy Y**. Użytkownik A ma konto służbowe dla każdej firmy, a obaj użytkownicy wdrażają zasady MAM za pomocą usługi Intune. **Firma X** wdraża zasady zarządzania aplikacjami mobilnymi **przed** **Firmą Y**. Zasady MAM zostaną zastosowane na koncie skojarzonym z **Firmą X**, ale nie na koncie skojarzonym z Firmą Y. Jeśli chcesz, aby konto użytkownika skojarzone z Firmą Y było zarządzane według zasad MAM, musisz usunąć konto użytkownika skojarzone z Firmą X.
### <a name="add-a-second-account"></a>Dodawanie drugiego konta
####  <a name="android"></a>Android
Jeśli korzystasz z urządzenia z systemem Android, może zostać wyświetlony komunikat o blokadzie zawierający instrukcje usunięcia istniejącego konta i dodania nowego.  Aby usunąć istniejące konto, przejdź do pozycji **Ustawienia &gt;Ogólne &gt; Menedżer aplikacji &gt;Portal firmy**. Następnie wybierz pozycję **Wyczyść dane**.

![Zrzut ekranu komunikatu o błędzie i instrukcjami dotyczącymi usunięcia konta](../media/AppManagement/Android_SwitchUser.png)

##  <a name="view-media-files-with-the-azure-information-protection-app"></a>Wyświetlanie plików multimedialnych przy użyciu aplikacji Azure Information Protection
Aby wyświetlać firmowe pliki audio i wideo, pliki PDF i pliki obrazów na urządzeniach z systemem Android, użyj [aplikacji Azure Information Protection](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer) (wcześniej znanej jako aplikacja do tworzenia i przetwarzania dokumentów chronionych usługami Rights Management).

Pobierz tę aplikację ze sklepu Google Play.  

Obsługiwane są następujące typy plików:

* **Audio:** AAC LC, HE-AACv1 (AAC+), HE-AACv2 (rozszerzone AAC+), AAC ELD (rozszerzone AAC o małym opóźnieniu), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Ogg Vorbis, PCM/WAVE
* **Wideo:** H.263, H.264 AVC, MPEG-4 SP, VP8
* **Obraz:** jpg, pjpg, png, ppng, bmp, pbmp, gif, pgif, jpeg, pjpeg
* **Dokumenty:** PDF, PPDF


|**pfile**|**tekst**|
|----|----|
|Pfile jest ogólnym formatem „otoki” dla plików chronionych, który hermetyzuje zaszyfrowaną zawartość i licencje usługi Azure Information Protection. Może służyć do ochrony pliku dowolnego typu.|Pliki tekstowe, m.in. w formatach XML i CSV, można otworzyć w celu wyświetlenia w aplikacji nawet wtedy, gdy są chronione. Typy plików: txt, ptxt, csv, pcsv, log, plog, xml, pxml.|

## <a name="next-steps"></a>Następne kroki
[Oczekiwany przebieg zarządzania aplikacją systemu iOS przez zasady zarządzania aplikacjami mobilnymi](user-experience-for-mam-enabled-ios-apps-with-microsoft-intune.md)

### <a name="see-also"></a>Zobacz także
[Tworzenie i wdrażanie zasad zarządzania aplikacjami mobilnymi przy użyciu usługi Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


