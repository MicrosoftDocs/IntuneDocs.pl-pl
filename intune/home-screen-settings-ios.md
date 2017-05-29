---
title: "Ustawienia układu ekranu głównego dla urządzeń z systemem iOS w usłudze Intune"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: informacje o ustawieniach pozwalających dostosować ekran główny i obszar Docka w urządzeniach z systemem iOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6aba4491-afb9-43cd-9ccc-14e6a2a5a3b1
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 7743573ab893b7d54c11e183133fa02368c00779
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---

# <a name="intune-home-screen-layout-settings-for-ios-devices"></a>Ustawienia układu ekranu głównego dla urządzeń z systemem iOS w usłudze Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Te ustawienia umożliwiają konfigurację układu aplikacji, folderów i wycinków witryn w obszarze Docka i na ekranie głównym wszystkich urządzeń z systemem iOS, do których zostaną przypisane zasady.

Urządzenia iOS, do których zostanie przypisany profil, muszą działać w trybie nadzorowanym i muszą mieć zainstalowany system iOS w wersji 9.3 lub nowszej.

1. W bloku **Funkcje urządzenia** wybierz pozycję **Układ ekranu głównego (tylko tryb nadzorowany)**.
2. W bloku **Układ ekranu głównego (tylko tryb nadzorowany)** wybierz odpowiednio pozycję **Dock** lub **Strony**, w zależności od tego, dla jakiego obszaru chcesz skonfigurować układ.

## <a name="add-items-to-the-dock"></a>Dodawanie elementów do obszaru Docka

W bloku **Dock** możesz dodać do 6 elementów lub folderów, które zostaną dodane do obszaru Docka u dołu ekranu w systemie iOS. Wiele urządzeń obsługuje jednak mniejszą liczbę elementów, na przykład w telefonach iPhone obsługiwane są maksymalnie 4 elementy. W takim przypadku na urządzeniu wyświetlane będą tylko pierwsze cztery elementy, które zostały skonfigurowane.

1. Wybierz pozycję **Dodaj**, aby dodać element do obszaru Docka.
2. W bloku **Dodaj wiersz** określ element, który chcesz dodać, wybierając pozycję **Aplikacja** lub **Folder**.
3. Korzystając z informacji zawartych w sekcjach **Jak dodać aplikację do listy** i **Jak dodać folder do listy** w tym temacie, skonfiguruj aplikacje i foldery, które mają być widoczne w obszarze Docka.
4. Kontynuuj dodawanie elementów. Gdy skończysz, klikaj przycisk **OK** w kolejnych blokach, aż powrócisz do bloku **Utwórz profil**. Wybierz pozycję **Utwórz**.

>[!TIP]
> Możesz przeciągać i upuszczać elementy w obszarze list ekranu głównego i stron, aby zmieniać ich kolejność. 

### <a name="example"></a>Przykład

W tym przykładzie skonfigurowano układ Docka w taki sposób, aby były w nim wyświetlane wyłącznie aplikacje Safari, Mail i Giełda. Na poniższej ilustracji zostały przedstawione właściwości aplikacji Mail:

![Przykładowe ustawienia Docka w systemie iOS](http://i.imgur.com/FfFiUcP.png)

Po przypisaniu zasad do telefonu iPhone wygląd Docka tego urządzenia będzie zbliżony do przedstawionego poniżej:

![Przykładowy układ Docka telefonu iPhone z systemem iOS](http://i.imgur.com/bAgCe8F.png)

## <a name="add-home-screen-pages"></a>Dodawanie stron ekranu głównego

Możesz dodawać strony, które mają być wyświetlane na ekranie głównym, oraz aplikacje, które będą widoczne na każdej ze stron. Aplikacje dodawane do strony są rozmieszczane od lewej do prawej — w kolejności, w której są wymienione na liście. Jeśli dodanych zostanie więcej aplikacji, niż mieści się na stronie, aplikacje zostaną przeniesione na następną stronę.


1. W bloku **Strony** wybierz pozycję **Dodaj**.
2. W bloku **Dodaj wiersz** wypełnij pole **Nazwa strony**. Jest to nazwa, do której można się odwołać w portalu usługi Intune i która *nie jest wyświetlana* na urządzeniu z systemem iOS.
3. W bloku **Dodaj** określ, jaki element chcesz dodać na stronie, wybierając pozycję **Aplikacja** lub **Folder**.
4. Korzystając z informacji zawartych w sekcjach **Jak dodać aplikację do listy** i **Jak dodać folder do listy** w tym temacie, skonfiguruj aplikacje i foldery, które mają być widoczne na stronie.

### <a name="example"></a>Przykład

W tym przykładzie skonfigurowano nową stronę o nazwie **Contoso**. Na stronie znajdują się tylko aplikacje Moi znajomi i Ustawienia. Na poniższej ilustracji zostały przedstawione właściwości aplikacji Ustawienia:

![Przykład ustawień ekranu głównego w systemie iOS](http://i.imgur.com/Jc2OxyX.png)

Po przypisaniu zasad do telefonu iPhone wygląd strony w urządzeniu będzie zbliżony do przedstawionego poniżej:

![Urządzenie z systemem iOS ze zmodyfikowanym ekranem głównym](http://i.imgur.com/Bd37PHa.png)

## <a name="how-to-add-an-app-to-the-list"></a>Jak dodać aplikację do listy

1. Wypełnij pole **Nazwa aplikacji**. Jest to nazwa, do której można się odwołać w portalu usługi Intune i która *nie jest wyświetlana* na urządzeniu z systemem iOS.
2. Wprowadź **Identyfikator pakietu aplikacji** dla aplikacji, którą chcesz wyświetlić. Aby uzyskać pomoc, zobacz **Identyfikatory pakietu dla wbudowanych aplikacji systemu iOS** w dalszej części tego tematu.
3. Kliknij przycisk **OK** i dodawaj kolejne elementy. W obszarze Docka można ich dodać maksymalnie **6**, a na stronie urządzenia — maksymalnie **60**.
4. Po zakończeniu kliknij przycisk **OK**.

## <a name="how-to-add-a-folder-to-the-list"></a>Jak dodać folder do listy

Aplikacje dodawane do strony w folderze są rozmieszczane od lewej do prawej — w kolejności, w której są wymienione na liście. Jeśli dodanych zostanie więcej aplikacji, niż mieści się na stronie, aplikacje zostaną przeniesione na następną stronę.

1. Wypełnij pole **Nazwa folderu**. Tę nazwę zobaczą użytkownicy na swoich urządzeniach.
2. Wybierz pozycję **Dodaj**, aby utworzyć stronę w folderze. Możesz dodać maksymalnie 20 stron.
3. W bloku **Dodaj wiersz** wpisz nazwę strony. Jest to nazwa, do której można się odwołać w portalu usługi Intune i która *nie jest wyświetlana* na urządzeniu z systemem iOS.
3. Wypełnij pole **Nazwa aplikacji**. Jest to nazwa, do której można się odwołać w portalu usługi Intune i która *nie jest wyświetlana* na urządzeniu z systemem iOS.
2. Wprowadź **Identyfikator pakietu aplikacji** dla aplikacji, którą chcesz wyświetlić. Aby uzyskać pomoc, zobacz temat **Jak dodać aplikację do listy**.
3. Wybierz pozycję **Dodaj**. Możesz dodać maksymalnie 60 elementów.
4. Po zakończeniu kliknij przycisk **OK**.


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


