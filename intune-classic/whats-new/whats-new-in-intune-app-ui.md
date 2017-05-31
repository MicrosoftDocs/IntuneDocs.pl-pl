---
title: "Aktualizacje interfejsu użytkownika dla aplikacji użytkownika końcowego usługi Intune | Microsoft Docs"
description: "Dowiedz się więcej na temat zmian interfejsu użytkownika dla aplikacji, które działają na urządzeniach użytkownika końcowego z usługą Intune."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b782e382-8deb-48a7-a437-d7c5a17163f1
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 629a091c1016186700a95bf76b9feed9ef0adb79
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---
# <a name="ui-updates-for-intune-end-user-apps"></a>Aktualizacje interfejsu użytkownika dla aplikacji użytkownika końcowego usługi Intune
Dowiedz się, jakie aktualizacje wprowadziliśmy w interfejsie użytkownika dla aplikacji, które użytkownicy końcowi zobaczą w tej wersji usługi Microsoft Intune. Może to ułatwić komunikację z użytkownikami oraz aktualizowanie wszystkich dokumentów niestandardowych, które utworzono w celu obsługi wdrożenia. Może to także ułatwić zrozumienie, jak lepiej rozwiązywać problemy, z jakimi borykają się użytkownicy, gdy dzwonią do działu pomocy technicznej przy użyciu aplikacji Portal firmy.

## <a name="coming-soon-in-the-ui"></a>Wkrótce w interfejsie użytkownika
Są to plany dotyczące metod ulepszania środowiska użytkownika przez aktualizację interfejsu użytkownika.

> [!Note]
> Należy pamiętać, że poniższe obrazy mogą być wersjami wstępnymi i zapowiadany produkt może różnić się od prezentowanych wersji.

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Ulepszone środowisko logowania w aplikacjach Portalu firmy dla wszystkich platform <!--User Story 1132123-->

Informujemy o zmianie, która zostanie wprowadzona w ciągu następnych kilku miesięcy i ułatwi logowanie w aplikacjach Portal firmy w usłudze Intune dla systemów Android, iOS i Windows. Nowe środowisko użytkownika zostanie udostępnione automatycznie na wszystkich platformach aplikacji Portal firmy, gdy zmiana ta zostanie wprowadzona w usłudze Azure AD. Ponadto użytkownicy mogą teraz logować się do Portalu firmy za pomocą innego urządzenia, korzystając z wygenerowanego kodu jednorazowego. Ta opcja jest szczególnie przydatna w sytuacji, gdy niezbędne jest zalogowanie się bez użycia poświadczeń.  

Poniżej przedstawiono poprzednie środowisko logowania, nowe środowisko logowania z poświadczeniami oraz nowe środowisko logowania za pomocą innego urządzenia.

__Poprzednie środowisko logowania__

![Strona logowania do Portalu firmy z ikoną osoby przed graficzną reprezentacją witryny sieci Web. Poniżej znajduje się przycisk „Zaloguj”. Link u dołu pozwala uzyskać dostęp do informacji dotyczących polityki prywatności firmy Microsoft oraz sposobu korzystania przez nią z plików cookie.](./media/cp_ios_aad_signin_before_1704_001.png)

![Po wybraniu przycisku Zaloguj użytkownik wprowadza swoje poświadczenia na stronie z monitem o podanie adresu e-mail i hasła, na której znajdują się także informacje dotyczące rozwiązywania problemów z hasłem.](./media/cp_ios_aad_signin_before_1704_002.png)

![Po wpisaniu hasła przez użytkownika w aplikacji Portal firmy następuje logowanie, którego postęp jest widoczny na pasku ładowania.](./media/cp_ios_aad_signin_before_1704_003.png)

__Nowe środowisko logowania__

![Strona logowania do Portalu firmy z ikoną osoby przed graficzną reprezentacją witryny sieci Web. Poniżej znajduje się przycisk „Zaloguj”. Link u dołu pozwala uzyskać dostęp do informacji dotyczących polityki prywatności firmy Microsoft oraz sposobu korzystania przez nią z plików cookie.](./media/cp_ios_aad_signin_after_1704_001.png)

![Na jednym ekranie użytkownik otrzymuje zwykle monit o podanie samego adresu e-mail, a nie adresu e-mail i hasła.](./media/cp_ios_aad_signin_after_1704_002.png)

![Monit o podanie hasła wyświetla się po zaakceptowaniu podanego adresu e-mail.](./media/cp_ios_aad_signin_after_1704_003.png)

![Po przeprowadzeniu procesu uwierzytelniania w aplikacji Portal firmy następuje logowanie, którego postęp sygnalizuje pasek ładowania.](./media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

__Nowe środowisko logowania dostępne podczas logowania za pomocą innego urządzenia__

![Strona logowania do Portalu firmy z ikoną osoby przed graficzną reprezentacją witryny sieci Web. Poniżej znajduje się przycisk „Zaloguj”. Link u dołu pozwala uzyskać dostęp do informacji dotyczących polityki prywatności firmy Microsoft oraz sposobu korzystania przez nią z plików cookie.](./media/cp_ios_aad_signin_from_another_device_after_1704_001.png)

Wybierz link __Zaloguj się za pomocą innego urządzenia__.

![Zgodnie z instrukcjami po uzyskaniu unikatowego kodu dostępu należy na komputerze służbowym przejść na stronę aka.ms/devicelogin, a następnie zalogować się, korzystając z kodu.](./media/cp_ios_aad_signin_from_another_device_after_1704_003.png)

Uruchom przeglądarkę i przejdź na stronę [https://aka.ms/devicelogin](https://aka.ms/devicelogin).

![Zrzut ekranu przedstawiający przeglądarkę użytkownika na komputerze służbowym zamiast aplikacji Portal firmy. Na stronie „Logowanie do urządzenia” zostanie wyświetlony monit o podanie kodu odebranego w aplikacji Portal firmy.](./media/cp_ios_aad_signin_from_another_device_after_1704_004.png)

Wprowadź kod z aplikacji Portal firmy. Po wybraniu pozycji __Kontynuuj__ będzie możliwe uwierzytelnienie przy użyciu dowolnej metody obsługiwanej przez firmę, np. z użyciem karty inteligentnej.

![Użytkownik wprowadził w odpowiednim polu swój unikatowy kod, a w witrynie „Logowanie do urządzenia” został wyświetlony monit o potwierdzenie, że aplikacja Portal firmy usługi Intune jest właściwą aplikacją, która ma otrzymać autoryzację do logowania.](./media/cp_ios_aad_signin_from_another_device_after_1704_005.png)

![Strona potwierdzenia stwierdzająca, że użytkownik zalogował się do aplikacji Portal firmy na urządzeniu i że można już zamknąć tę stronę.](./media/cp_ios_aad_signin_from_another_device_after_1704_006.png)

W aplikacji Portal firmy rozpocznie się logowanie.

![Po przeprowadzeniu procesu uwierzytelniania w aplikacji Portal firmy następuje logowanie, którego postęp sygnalizuje pasek ładowania.](./media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

## <a name="april-2017"></a>Kwiecień 2017

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431--"></a>Nowe ikony przeglądarki Managed Browser i aplikacji Portal firmy <!--918433, 918431-->

Przeglądarka Managed Browser otrzymuje zaktualizowane ikony aplikacji dla systemów Android i iOS. Nowa ikona będzie zawierać zaktualizowany identyfikator Intune, dzięki czemu będzie bardziej spójna z innymi aplikacjami w rozwiązaniu Enterprise Mobility + Security (EM+S).

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune-classic/whats-new/media/cp_manbro_before_042017.png" alt="The previous version of the Managed Browser app icon." width=200 height=366 align=center>
          </td>
          <td>
             <img src="/intune-classic/whats-new/media/cp_manbro_after_042017.png" alt="The updated version of the Managed Browser app icon." width=200 height=366 align=center>
           </td>
      </tr>
   </table>
</body>
</html>

Portal firmy również otrzymuje zaktualizowane ikony aplikacji dla systemów Android, iOS i Windows, aby poprawić spójność z innymi aplikacjami w rozwiązaniu EM+S. Ikony te będą stopniowo wydawane na różnych platformach od kwietnia do końca maja.

### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Wskaźnik postępu logowania w aplikacji Portal firmy dla systemu Android <!--953374-->

Aktualizacja aplikacji Portal firmy dla systemu Android pokazuje wskaźnik postępu logowania, gdy użytkownik uruchomi lub wznowi działanie aplikacji. Wskaźnik przechodzi przez nowe stany, od „Trwa łączenie...” przez „Trwa logowanie...” do „Trwa sprawdzanie wymagań dotyczących bezpieczeństwa...”, zanim zezwoli użytkownikowi na dostęp do aplikacji.

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune-classic/whats-new/media/cp_android_connecting_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Connecting' underneath it." width=200 height=366 align=center>
          </td>
          <td>
             <img src="/intune-classic/whats-new/media/cp_android_signing_in_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Signing in' underneath it." width=200 height=366 align=center>
           </td>
           <td>
              <img src="/intune-classic/whats-new/media/cp_android_checking_security_reqs_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Checking for security requirements' underneath it." width=200 height=366 align=center>
           </td>
      </tr>
   </table>
</body>
</html>

### <a name="improved-app-install-status-for-the-windows-10-company-portal-app---676495--"></a>Ulepszono stan instalacji aplikacji Portal firmy dla systemu Windows 10 <!--676495-->
Aplikacja Portal firmy dla systemu Windows 10 oferuje teraz pasek postępu instalacji na stronie szczegółów aplikacji. Ta funkcja jest obsługiwana w przypadku nowoczesnych aplikacji na urządzeniach z Rocznicową aktualizacją systemu Windows 10 oraz jego nowszymi wersjami.

__Przed__
  ![Obraz poprzedniej wersji ekranu ładowania, na którym był wyświetlany stan „Trwa instalowanie”.](./media/cp_win10_install_status_before_1704.png)

__Po__
  ![Obraz zaktualizowanej wersji ekranu ładowania, na którym jest teraz wyświetlany pasek postępu instalacji.](./media/cp_win10_install_status_after_1704.png)

## <a name="february-2017"></a>Luty 2017

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622-announced-1702--"></a>Nowe środowisko użytkownika aplikacji Portal firmy dla systemu Android <!--621622, announced 1702-->
Od marca aplikacja Portal firmy dla systemu Android będzie zgodna z [zaleceniami dotyczącymi projektowania materiałów](https://material.io/guidelines/material-design/introduction.html) w celu zapewnienia bardziej nowoczesnego wyglądu i działania. Udoskonalone środowisko użytkownika końcowego obejmuje między innymi następujące elementy:

* __Kolory__: nagłówkom kart można nadać kolory z palety kolorów niestandardowych.

![Po lewej stronie: obraz aplikacji Portal firmy dla systemu Android przed aktualizacją. Po prawej stronie: obraz aplikacji Portal firmy dla systemu Android po aktualizacji. Oba obrazy przedstawiają kartę Urządzenia jako kartę wybraną spośród trzech dostępnych kart (Aplikacje, Urządzenia i Kontakt z działem IT).](./media/CP_Android_DevicesTab_BeforeAfter.png)

* __Interfejs__: przyciski __Polecane aplikacje__ i __Wszystkie aplikacje__ na karcie __Aplikacje__ zostały zaktualizowane. Przycisk __Wyszukaj__ jest teraz przestawnym przyciskiem akcji.

![Po lewej stronie: obraz aplikacji Portal firmy dla systemu Android przed aktualizacją. Po prawej stronie: obraz aplikacji Portal firmy dla systemu Android po aktualizacji. Oba obrazy przedstawiają kartę Aplikacje jako kartę wybraną spośród trzech dostępnych kart (Aplikacje, Urządzenia i Kontakt z działem IT).](./media/CP_Android_AppsTab_BeforeAfter.png)

* __Nawigacja__: na karcie Wszystkie aplikacje jest dostępny widok z kartami __Polecane__, __Wszystkie__ i __Kategorie__ w celu zapewnienia łatwiejszej nawigacji. Karta __Kontakt z działem IT__ została ulepszona w celu zapewnienia lepszej czytelności.

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune-classic/whats-new/media/cp_android_contactit_after.png" alt="The Company Portal app for Android displaying an updated version of the Contact IT tab. The tab shows available contact information for IT, including phone number, email address, IT website, and IT contact information." width=200 height=366 align=center>
          </td>
      </tr>
   </table>
</body>
</html>

## <a name="january-2017"></a>Styczeń 2017

### <a name="modernizing-the-company-portal-website---753980-announced-1701--"></a>Modernizowanie witryny sieci Web Portal firmy <!--753980, announced 1701-->
Od lutego witryna sieci Web Portal firmy będzie obsługiwać aplikacje przeznaczone dla użytkowników, którzy nie mają zarządzanych urządzeń. Witryna internetowa zostanie zmieniona tak, aby wyglądała jak witryny innych produktów i usług firmy Microsoft, przy użyciu nowego schematu kontrastujących kolorów, ilustracji dynamicznych i menu typu „hamburger”. ![Mały obraz menu typu „hamburger” dodanego w lewym górnym rogu witryny internetowej Portal firmy,](./media/CP_hamburger_menu.png) które będzie zawierać szczegółowe dane kontaktowe działu pomocy technicznej i informacje o istniejących urządzeniach zarządzanych. Układ strony docelowej zostanie zmieniony tak, aby wyróżnić aplikacje dostępne dla użytkowników, a aplikacje polecane i ostatnio zaktualizowane zostaną oznaczone symbolem karuzeli.

![Z lewej strony: obraz przedstawiający bieżącą wersję witryny sieci Web Portal firmy z poprzednią wersją widoków Aplikacje, Moje urządzenia oraz Polecane i Kategorie. Z prawej strony: obraz przedstawiający zaktualizowaną wersję witryny sieci Web Portal firmy z odświeżoną karuzelą aplikacji, listą niedawno opublikowanych aplikacji i zaktualizowanym widokiem Kategorie.](./media/CP_Website_BeforeAfter_Feb2016.png)


### <a name="see-also"></a>Zobacz także
* [Blog usługi Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plan platformy w chmurze](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Co nowego w wersji zapoznawczej na platformie Azure](https://docs.microsoft.com/intune/whats-new)
* [Archiwum nowości](whats-new-archive.md)

