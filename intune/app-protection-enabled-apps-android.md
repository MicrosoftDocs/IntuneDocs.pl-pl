---
title: Aplikacje dla systemu Android z zasadami ochrony aplikacji
titlesuffix: Microsoft Intune
description: Dowiedz się, czego oczekiwać od aplikacji systemu Android zawierającej zasady ochrony.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 12/07/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a6816285-8e43-4dc8-bca0-e80ec5ef01e6
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 16cef0b3e72c2e7815aada1c45c0e312b84931ab
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2018
ms.locfileid: "31833021"
---
# <a name="what-to-expect-when-your-android-app-is-managed-by-app-protection-policies"></a>Czego można oczekiwać, gdy aplikacja dla systemu Android jest zarządzana przy użyciu zasad ochrony aplikacji 

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Dowiedz się, czego oczekiwać od aplikacji systemu Android zawierających zasady ochrony. Zasady ochrony aplikacji są stosowane wyłącznie podczas korzystania z aplikacji w kontekście służbowym. Na przykład w przypadku uzyskiwania dostępu do aplikacji przy użyciu konta służbowego lub w przypadku uzyskiwania dostępu do plików przechowywanych w firmowej lokalizacji w usłudze OneDrive.
##  <a name="accessing-apps"></a>Uzyskiwanie dostępu do aplikacji

Aplikacja Portal firmy jest wymagana dla wszystkich aplikacji na urządzeniach z systemem Android, które mają zasady ochrony aplikacji.

Zainstaluj aplikację Portal firmy na wszystkich urządzeniach, które nie zostały zarejestrowane w usłudze Intune. Użytkownicy nie muszą logować się do aplikacji Portal firmy, aby korzystać z aplikacji z zasadami ochrony aplikacji.
Aplikacja Portal firmy umożliwia udostępnianie danych w bezpiecznej lokalizacji. Dlatego to wymaganie obowiązuje nawet w przypadku urządzeń niezarejestrowanych.


##  <a name="using-apps-with-multi-identity-support"></a>Korzystanie z aplikacji z obsługą wielu tożsamości

Zasady ochrony aplikacji mają zastosowanie tylko wtedy, gdy użytkownik próbuje uzyskać dostęp do danych służbowych.  Jeśli użytkownik uzyska dostęp do aplikacji w ramach użytku osobistego, można będzie zaobserwować inne zachowania.

Niektóre aplikacje obsługują wiele tożsamości. W takim przypadku usługa Intune stosuje tylko zasady ochrony aplikacji, gdy użytkownik uzyskuje dostęp do danych służbowych.  Na przykład może zostać wyświetlony monit o podanie kodu PIN.  W **aplikacji Outlook** monit jest wyświetlany tylko wtedy, gdy użytkownik uruchamia aplikację. W **aplikacji OneDrive** monit jest wyświetlany, gdy użytkownik wpisuje konto służbowe.  W programach Microsoft **Word**, **PowerPoint** i **Excel** monit jest wyświetlany, gdy użytkownik uzyskuje dostęp do firmowych dokumentów w usłudze OneDrive.
##  <a name="managing-user-accounts-on-the-device"></a>Zarządzanie kontami użytkowników na urządzeniu

Usługa Intune obsługuje wdrażanie zasad ochrony aplikacji na koncie jednego użytkownika dla każdego urządzenia.

* W zależności od używanej aplikacji drugi użytkownik może być blokowany na urządzeniu. Jednak we wszystkich przypadkach zasady dotyczą tylko pierwszego użytkownika, który pobierze zasady ochrony aplikacji.

  * Programy **Microsoft Word**, **Excel** i **PowerPoint** nie będą blokować dostępu do dodatkowego konta użytkownika. Zasady ochrony aplikacji nie będą mieć jednak wpływu na konto użytkownika.

  * W przypadku **aplikacji OneDrive i Outlook** możesz używać tylko jednego konta służbowego.  Dodawanie większej liczby kont służbowych w tych aplikacjach jest zablokowane.  Jednak możesz usunąć użytkownika z urządzenia, a następnie dodać innego użytkownika do urządzenia.


* Przed wdrożeniem zasad ochrony aplikacji urządzenie może mieć wiele istniejących kont użytkowników. W takim przypadku pierwsze konto, na którym są wdrażane zasady ochrony aplikacji, będzie zarządzane przez zasady ochrony aplikacji usługi Intune.


Przeczytaj poniższy przykładowy scenariusz, aby dowiedzieć się, jak usługa Intune obsługuje wiele kont użytkowników.

Użytkownik A pracuje dla dwóch firm: **Firmy X** i **Firmy Y**. Użytkownik A ma konto służbowe dla każdej firmy, a obaj użytkownicy wdrażają zasady ochrony aplikacji za pomocą usługi Intune. **Firma X** wdraża zasady ochrony aplikacji **przed** **Firmą Y**. Zasady ochrony aplikacji zostaną zastosowane na koncie skojarzonym z **Firmą X**, ale nie na koncie skojarzonym z Firmą Y. Aby konto użytkownika skojarzone z Firmą Y było zarządzane przez zasady ochrony aplikacji, użytkownik A musi usunąć konto użytkownika skojarzone z Firmą X.
### <a name="adding-a-second-account"></a>Dodawanie drugiego konta
####  <a name="android"></a>Android
Może pojawić się monit o usunięcie istniejącego konta i dodanie nowego.  Aby usunąć istniejące konto, przejdź do pozycji **Ustawienia &gt;Ogólne &gt; Menedżer aplikacji &gt;Portal firmy. Następnie wybierz pozycję „Wyczyść dane”.**

![Zrzut ekranu komunikatu o błędzie i instrukcjami dotyczącymi usunięcia konta](./media/android-switch-user.png)

##  <a name="viewing-media-files-with-the-azure-information-protection-app-previously-known-as-rights-management-sharing-app"></a>Wyświetlanie plików multimedialnych przy użyciu aplikacji Azure Information Protection (znaną wcześniej jako aplikacja Rights Management sharing)
Aby wyświetlać firmowe pliki audio i wideo, pliki PDF i pliki obrazów na urządzeniach z systemem Android, użyj [aplikacji Azure Information Protection](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer).

Pobierz tę aplikację ze sklepu Google Play.  

Obsługiwane są następujące typy plików:

* **Audio:** AAC LC, HE-AACv1 (AAC+), HE-AACv2 (rozszerzone AAC+), AAC ELD (rozszerzone AAC o małym opóźnieniu), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Ogg Vorbis, PCM/WAVE.
* **Wideo:** H.263, H.264 AVC, MPEG-4 SP, VP8.
* **Obraz:** jpg, pjpg, png, ppng, bmp, pbmp, gif, pgif, jpeg, pjpeg.
* **Dokumenty:** PDF, PPDF

------------

|                                                                                 <strong>pfile</strong>                                                                                 |                                                                      <strong>tekst</strong>                                                                      |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Pfile to ogólny format „otoki” chronionych plików. Hermetyzuje on zaszyfrowaną zawartość i licencje usługi Azure Information Protection. Może służyć do ochrony pliku dowolnego typu. | Pliki tekstowe, w tym XML, CSV itp., można otworzyć w celu wyświetlania w aplikacji nawet wtedy, gdy są chronione. Typy plików: txt, ptxt, csv, pcsv, log, plog, xml, pxml. |

---------------
## <a name="next-steps"></a>Następne kroki
[Czego można oczekiwać, gdy aplikacja dla systemu iOS jest zarządzana przy użyciu zasad ochrony aplikacji](app-protection-enabled-apps-ios.md)

### <a name="see-also"></a>Zobacz też
[Tworzenie i wdrażanie zasad ochrony aplikacji przy użyciu usługi Microsoft Intune](app-protection-policies.md)
