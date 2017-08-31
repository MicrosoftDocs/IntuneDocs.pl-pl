---
title: "Aktualizacje interfejsu użytkownika dla aplikacji użytkownika końcowego usługi Intune"
description: "Dowiedz się więcej na temat zmian interfejsu użytkownika dla aplikacji, które działają na urządzeniach użytkownika końcowego z usługą Intune."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 08/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b782e382-8deb-48a7-a437-d7c5a17163f1
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6db9bc7a3bafd61d03513ea1b6e1f0246faaab57
ms.sourcegitcommit: 4dc5bed94cc965a54eacac2d87fb2d49c9300c3a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/25/2017
---
# <a name="ui-updates-for-intune-end-user-apps"></a>Aktualizacje interfejsu użytkownika dla aplikacji użytkownika końcowego usługi Intune
Dowiedz się, jakie aktualizacje wprowadziliśmy w interfejsie użytkownika dla aplikacji, które użytkownicy końcowi zobaczą w tej wersji usługi Microsoft Intune. Może to ułatwić komunikację z użytkownikami oraz aktualizowanie wszystkich dokumentów niestandardowych, które utworzono w celu obsługi wdrożenia. Może to także ułatwić zrozumienie, jak lepiej rozwiązywać problemy, z jakimi borykają się użytkownicy, gdy dzwonią do działu pomocy technicznej przy użyciu aplikacji Portal firmy.

## <a name="week-of-august-21-2017"></a>Tydzień od 21 sierpnia 2017 r.

### <a name="intune-mobile-application-management-mam-dialog-boxes-will-have-a-modern-interface----1199015---"></a>Okna dialogowe zarządzania aplikacjami mobilnymi w usłudze Intune (MAM) będą miały nowoczesny interfejs <!-- 1199015 -->

Okna dialogowe zarządzania aplikacjami mobilnymi w usłudze Intune (MAM) zostaną zaktualizowane do nowoczesnego wyglądu. Okna dialogowe będą działać w taki sam sposób jak w poprzednim stylu.

**Poprzednie środowisko**

![stary interfejs](media\NewUI_Old_AttachFileHandler.jpg)

**Nowoczesne środowisko**

![nowoczesny interfejs](media\NewUI_Modern_AttachFileHandler.jpg)


## <a name="week-of-august-14-2017"></a>Tydzień od 14 sierpnia 2017 r.

### <a name="updates-to-the-device-details-page-on-the-company-portal-app-for-windows-10----1287448---"></a>Aktualizacje na stronie „Szczegóły urządzeń” w aplikacji Portal firmy dla systemu Windows 10 <!---1287448--->

W aplikacji Portal firmy dla systemu Windows 10 przeniesiono tag __Kategoria__ spod tytułu do właściwości na stronie __Szczegóły urządzenia__.

![Ekran „Szczegóły urządzenia” aplikacji Portal firmy dla systemu Windows 10, na którym pole „Kategorie” jest teraz wyświetlane jako właściwość, a nie bezpośrednio pod tytułem ekranu.](./media/cp_win10_category_tag_move_after_1708.png)

## <a name="week-of-july-31-2017"></a>Tydzień od 31 lipca 2017 r.

### <a name="apps-details-pages-will-display-new-information-for-android-devices---1287476--"></a>Na stronie szczegółów aplikacji będą wyświetlane nowe informacje dla urządzeń z systemem Android <!--1287476-->

Na stronie szczegółów aplikacji w aplikacji Portal firmy dla systemu Android będą teraz wyświetlane kategorie aplikacji zdefiniowane przez administratora IT dla danej aplikacji.

![Nowa strona szczegółów aplikacji](./media/cp_android_appdetails_after_1708.png)

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

## <a name="week-of-june-12-2017"></a>Tydzień od 12 czerwca 2017 r.

### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies---1305217--"></a>Aplikacja Portal firmy dla systemu Android ma teraz nowe środowisko użytkownika końcowego dla zasad ochrony aplikacji <!--1305217-->
Na podstawie opinii klientów zmodyfikowaliśmy aplikację Portal firmy dla systemu Android w celu wyświetlania przycisku **Dostęp do zawartości firmowej**. Ma to na celu zapobieganie niepotrzebnemu przechodzeniu przez użytkowników końcowych przez proces rejestracji, gdy potrzebują tylko dostępu do aplikacji obsługujących zasady ochrony aplikacji, czyli funkcję zarządzania aplikacjami mobilnymi usługi Intune.

Użytkownik naciśnie przycisk **Dostęp do zawartości firmowej**, zamiast rozpoczynać rejestrowanie urządzenia.

![Obraz aplikacji Portal firmy dla systemu Android z wyświetlonym w środku przyciskiem „Dostęp do zawartości firmowej” podpisanym dużym tekstem zamiast opcji natychmiastowej rejestracji jak w standardowym przypadku](./media/and_access_company_content_after_1706.png)

Użytkownik jest następnie przekierowywany do witryny internetowej Portal firmy w celu autoryzowania aplikacji do użytku na urządzeniu, gdzie witryna internetowa Portal firmy zweryfikuje jego poświadczenia.

![Obraz witryny internetowej Portal firmy z potwierdzeniem zalogowania się.](./media/and_iwp_sign_in_auth_page_after_1706.png)

Urządzenie można nadal rejestrować do pełnego zarządzania, naciskając menu **akcja**.

![Obraz aplikacji Portal firmy dla systemu Android z otwartym menu w prawym górnym rogu ekranu z opcją zarejestrowania urządzenia.](./media/and_sign_in_menu_after_app_protection_policy_enrolled_after_1706.png)

### <a name="improvements-to-app-syncing-with-windows-10-creators-update---676505--"></a>Ulepszenia synchronizacji aplikacji w wersji Aktualizacja systemu Windows 10 dla twórców <!--676505-->

Aplikacja Portal firmy dla systemu Windows 10 będzie teraz automatycznie inicjować synchronizację żądań instalacji aplikacji dla urządzeń z systemem w wersji Aktualizacja systemu Windows 10 dla twórców (wersja 1703). Pozwoli to ograniczyć problem związany z zatrzymywaniem się instalacji aplikacji w stanie „Oczekiwanie na synchronizację”. Ponadto użytkownicy będą mogli ręcznie zainicjować synchronizację z poziomu aplikacji.

![Obraz aplikacji Portal firmy dla systemu Windows 10: trwa oczekiwanie na pobranie aplikacji Microsoft Word ze sklepu z aplikacjami Portalu firmy.](./media/w10_download_pending_after_1706.png)

![Obraz aplikacji Portal firmy dla systemu Windows 10: stan nowej synchronizacji automatycznej z komunikatem o stanie wskazującym, że urządzenie jest synchronizowane i próbuje pobrać aplikację.](./media/w10_download_pending_syncing_after_1706.png)

### <a name="new-guided-experience-for-windows-10-company-portal----1058938---"></a>Nowe środowisko z przewodnikiem dla Portalu firmy systemu Windows 10 <!---1058938--->
Aplikacja Portal firmy dla systemu Windows 10 będzie zawierać wskazówki przewodnika usługi Intune dla urządzeń, które nie zostały zidentyfikowane ani zarejestrowane. Nowe środowisko obejmuje instrukcje krok po kroku, które prowadzą użytkownika przez proces rejestracji w usłudze Azure Active Directory (wymaganej dla funkcji dostępu warunkowego) oraz rejestracji MDM (wymaganej dla funkcji zarządzania urządzeniami). Przewodnik obsługi będzie dostępny na stronie głównej Portalu firmy. Użytkownicy mogą nadal używać aplikacji, jeśli nie ukończą rejestracji, ale może wystąpić ograniczenie funkcjonalności.

Ta aktualizacja jest widoczna tylko na urządzeniach z Rocznicową aktualizacją systemu Windows 10 (kompilacją 1607) i nowszymi wersjami.

![Obraz strony docelowej aplikacji Portal firmy dla systemu Windows 10 z komunikatem o stanie w środku na liście „urządzenia”, który informuje użytkownika, że używanego przez niego urządzenia nie skonfigurowano jeszcze do użytku firmowego i że użytkownik powinien wybrać ten komunikat, aby rozpocząć konfigurowanie.](./media/win10_guided_enroll_select_setup_after_1706.png)

![Obraz strony konfiguracji aplikacji Portal firmy dla systemu Windows 10 z ostrzeżeniem dla użytkownika, że musi on dodać do tego urządzenia konto firmowe, aby móc zarejestrować urządzenie w celu objęcia go zarządzaniem.](./media/win10_guided_enroll_we_help_setup_after_1706.png)

![Obraz strony aplikacji Portal firmy dla systemu Windows 10 służącej do dodawania konta firmowego do danego urządzenia z informacją dla użytkownika, że musi on przejść do aplikacji Ustawienia i wybrać pozycję Połącz, aby sfinalizować rejestrację. Gdy to zrobi, na ekranie pojawi się informacja, że należy powrócić do aplikacji Portal firmy, aby sfinalizować rejestrację.](./media/win10_guided_enroll_leaving_for_iwp_after_1706.png)

![Obraz strony aplikacji Portal firmy dla systemu Windows 10 służącej do rejestrowania w systemie zarządzania z komunikatem o stanie wskazującym ukończenie operacji: urządzenie jest zarejestrowane i użytkownik powinien nacisnąć przycisk Dalej, aby kontynuować.](./media/win10_guided_enroll_youre_now_enrolled_after_1706.png)

![Obraz ekranu ukończenia operacji aplikacji Portal firmy dla systemu Windows 10 z informacją, że wszystko jest gotowe i że urządzenie jest zarejestrowane przy użyciu konta firmowego, które poprawnie do niego dodano.](./media/win10_guided_enroll_youre_all_set_after_1706.png)

### <a name="new-menu-action-to-easily-remove-company-portal---1164569--"></a>Nowa akcja menu do łatwego usuwania Portalu firmy <!--1164569-->
W odpowiedzi na opinie użytkowników w aplikacji Portal firmy dla systemu Android została dodana nowa akcja menu do inicjowania usunięcia Portalu firmy z urządzenia. Powoduje ona usunięcie urządzenia z zarządzania w usłudze Intune, dzięki czemu użytkownik może samodzielnie usunąć aplikację z urządzenia.

![Obraz aplikacji Portal firmy dla systemu Android z otwartym menu akcji w prawym górnym rogu. Nowa opcja „usuń portal firmy” jest dostępna jako trzecia opcja poniżej opcji „mój profil” i „ustawienia”, powyżej pozycji „warunki i postanowienia”, „pomoc i opinie” oraz „informacje”.](./media/android_remove_cp_menu_action_after_1705.png)

![Obraz okna dialogowego potwierdzenia, które jest dostępne po wybraniu w menu akcji nowej opcji „usuń portal firmy”. Okno dialogowe informuje użytkownika, że „po usunięciu portalu firmy urządzenie przestanie być zarządzane przez administratora IT, a dostęp do firmowych danych, aplikacji i poczty e-mail może zostać utracony”. Następnie użytkownik jest proszony o potwierdzenie za pomocą przycisku „Tak”, że chce usunąć aplikację Portal firmy.](./media/android_remove_cp_menu_confirmation_after_1705.png)

## <a name="week-of-june-5-2017"></a>Tydzień od 5 czerwca 2017 r.

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios---1230777--"></a>Ulepszenia kafelków aplikacji w aplikacji Portal firmy dla systemu iOS <!--1230777-->
Zaktualizowaliśmy wygląd kafelków aplikacji na stronie głównej, aby odpowiadał on kolorowi ustawionemu dla Portalu firmy.

**Przed**

![Obraz aplikacji Portal firmy dla systemu iOS przed aktualizacją, na którym przedstawiono wstępnie ustawione obrazy dla pozycji „Wszystkie aplikacje”, „Polecane aplikacje” i „Kategorie”.](./media/cp_ios_homepage_before_1705.png)

**Po**

![Obraz aplikacji Portal firmy dla systemu iOS po aktualizacji, który przedstawia możliwość wybrania kolorów zgodnie z potrzebami organizacji.](./media/cp_ios_homepage_after_1705.png)

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>Selektor konta już dostępny w aplikacji Portal firmy dla systemu iOS
Jeśli użytkownicy używają konta służbowego w celu logowania się do innych aplikacji firmy Microsoft na swoich urządzeniach z systemem iOS, podczas pierwszego logowania się do Portalu firmy mogą zobaczyć nowy selektor konta.

![Obraz selektora konta przedstawiający użytkownika testowego (Robin Swanson), który wybiera między dwoma adresami e-mail. Pod dwoma adresami znajduje się przycisk, który umożliwia użytkownikowi zalogowanie się przy użyciu innego konta.](./media/cp_ios_multi-account-selector-after-1705.png)

## <a name="april-2017"></a>Kwiecień 2017

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431--"></a>Nowe ikony przeglądarki Managed Browser i aplikacji Portal firmy <!--918433, 918431-->

Przeglądarka Managed Browser otrzymuje zaktualizowane ikony aplikacji dla systemów Android i iOS. Nowa ikona będzie zawierać zaktualizowany identyfikator Intune, dzięki czemu będzie bardziej spójna z innymi aplikacjami w rozwiązaniu Enterprise Mobility + Security (EM+S).

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune/media/cp_manbro_before_042017.png" alt="The previous version of the Managed Browser app icon." width=200 height=366 align=center>
          </td>
          <td>
             <img src="/intune/media/cp_manbro_after_042017.png" alt="The updated version of the Managed Browser app icon." width=200 height=366 align=center>
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
            <img src="/intune/media/cp_android_connecting_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Connecting' underneath it." width=200 height=366 align=center>
          </td>
          <td>
             <img src="/intune/media/cp_android_signing_in_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Signing in' underneath it." width=200 height=366 align=center>
           </td>
           <td>
              <img src="/intune/media/cp_android_checking_security_reqs_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Checking for security requirements' underneath it." width=200 height=366 align=center>
           </td>
      </tr>
   </table>
</body>
</html>

### <a name="improved-app-install-status-for-the-windows-10-company-portal-app---676495--"></a>Ulepszono stan instalacji aplikacji Portal firmy dla systemu Windows 10 <!--676495-->
Aplikacja Portal firmy dla systemu Windows 10 oferuje teraz pasek postępu instalacji na stronie szczegółów aplikacji. Ta funkcja jest obsługiwana w przypadku nowoczesnych aplikacji na urządzeniach z Rocznicową aktualizacją systemu Windows 10 oraz jego nowszymi wersjami.

__Przed__ ![Obraz poprzedniej wersji ekranu ładowania, na którym był wyświetlany stan „Trwa instalowanie”.](./media/cp_win10_install_status_before_1704.png)

__Po__ ![Obraz zaktualizowanej wersji ekranu ładowania, na którym jest teraz wyświetlany pasek postępu instalacji.](./media/cp_win10_install_status_after_1704.png)

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
            <img src="/intune/media/cp_android_contactit_after.png" alt="The Company Portal app for Android displaying an updated version of the Contact IT tab. The tab shows available contact information for IT, including phone number, email address, IT website, and IT contact information." width=200 height=366 align=center>
          </td>
      </tr>
   </table>
</body>
</html>

## <a name="january-2017"></a>Styczeń 2017

### <a name="modernizing-the-company-portal-website---753980-announced-1701--"></a>Modernizowanie witryny sieci Web Portal firmy <!--753980, announced 1701-->
Od lutego witryna sieci Web Portal firmy będzie obsługiwać aplikacje przeznaczone dla użytkowników, którzy nie mają zarządzanych urządzeń. Witryna internetowa zostanie zmieniona tak, aby wyglądała jak witryny innych produktów i usług firmy Microsoft, przy użyciu nowego schematu kontrastujących kolorów, ilustracji dynamicznych i menu typu „hamburger”. ![Mały obraz menu typu „hamburger” dodanego w lewym górnym rogu witryny internetowej Portal firmy,](./media/CP_hamburger_menu.png) które będzie zawierać szczegółowe dane kontaktowe działu pomocy technicznej i informacje o istniejących urządzeniach zarządzanych. Układ strony docelowej zostanie zmieniony tak, aby wyróżnić aplikacje dostępne dla użytkowników, a aplikacje polecane i ostatnio zaktualizowane zostaną oznaczone symbolem karuzeli.

![Z lewej strony: obraz przedstawiający bieżącą wersję witryny sieci Web Portal firmy z poprzednią wersją widoków Aplikacje, Moje urządzenia oraz Polecane i Kategorie. Z prawej strony: obraz przedstawiający zaktualizowaną wersję witryny sieci Web Portal firmy z odświeżoną karuzelą aplikacji, listą niedawno opublikowanych aplikacji i zaktualizowanym widokiem Kategorie.](./media/CP_Website_BeforeAfter_Feb2016.png)

## <a name="coming-soon-in-the-ui"></a>Wkrótce w interfejsie użytkownika
Są to plany dotyczące metod ulepszania środowiska użytkownika przez aktualizację interfejsu użytkownika.

> [!Note]
> Należy pamiętać, że poniższe obrazy mogą być wersjami wstępnymi i zapowiadany produkt może różnić się od prezentowanych wersji.

### <a name="ui-updates-to-the-company-portal-website---1313244-part-2--"></a>Aktualizacje interfejsu użytkownika witryny internetowej Portal firmy <!--1313244 part 2-->

__Aktualizacje sekcji Polecane aplikacje__ — do witryny dodaliśmy dedykowaną stronę, na której użytkownicy mogą przeglądać aplikacje wybrane do polecania. Dostosowaliśmy również interfejs użytkownika w sekcji Polecane na stronie głównej.

![Kolorowe kafelki przedstawiające aplikacje. Są to duże kolorowe kwadraty znajdujące się poniżej każdej aplikacji, których kolor jest określany na podstawie podstawowego koloru logo aplikacji. Sekcja „Polecane aplikacje” jest wyświetlana w górnej części aplikacji Portal firmy.](./media/cp_win10_colorful_tiles_after_1708.png)

### <a name="see-also"></a>Zobacz także
* [Blog usługi Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plan platformy w chmurze](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Co nowego w usłudze Intune](https://docs.microsoft.com/intune/whats-new)
