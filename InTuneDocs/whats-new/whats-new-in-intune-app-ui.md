---
title: "Aktualizacje interfejsu użytkownika dla aplikacji użytkownika końcowego usługi Intune | Microsoft Docs"
description: "Dowiedz się więcej na temat zmian interfejsu użytkownika dla aplikacji, które działają na urządzeniach użytkownika końcowego z usługą Intune."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b782e382-8deb-48a7-a437-d7c5a17163f1
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 0a39abc7f19f4c2c8074de66a9cd5df9cef78ed5
ms.openlocfilehash: 81761af5ab5aebe6abb44ff43a7df5a337d38fc7
ms.lasthandoff: 04/13/2017


---
# <a name="ui-updates-for-intune-end-user-apps"></a>Aktualizacje interfejsu użytkownika dla aplikacji użytkownika końcowego usługi Intune
Dowiedz się, jakie aktualizacje wprowadziliśmy w interfejsie użytkownika dla aplikacji, które użytkownicy końcowi zobaczą w tej wersji usługi Microsoft Intune. Może to ułatwić komunikację z użytkownikami oraz aktualizowanie wszystkich dokumentów niestandardowych, które utworzono w celu obsługi wdrożenia. Może to także ułatwić zrozumienie, jak lepiej rozwiązywać problemy, z jakimi borykają się użytkownicy, gdy dzwonią do działu pomocy technicznej przy użyciu aplikacji Portal firmy.

> [!Note]
> Należy pamiętać, że poniższe obrazy są podglądy i zapowiadany produkt może się różnić od prezentowanych wersji.

## <a name="whats-coming-in-intune-app-ui"></a>Elementy interfejsu użytkownika aplikacji usługi Intune dostępne wkrótce

### <a name="april-2017"></a>Kwiecień 2017

#### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431--"></a>Nowe ikony przeglądarki Managed Browser i aplikacji Portal firmy <!--918433, 918431-->

Przeglądarka Managed Browser otrzymuje zaktualizowane ikony aplikacji dla systemów Android i iOS. Nowa ikona będzie zawierać zaktualizowany identyfikator Intune, dzięki czemu będzie bardziej spójna z innymi aplikacjami w rozwiązaniu Enterprise Mobility + Security (EM+S).

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_manbro_before_042017.png" alt="The previous version of the Managed Browser app icon." width=200 height=366 align=center>
          </td>
          <td>
             <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_manbro_after_042017.png" alt="The updated version of the Managed Browser app icon." width=200 height=366 align=center>
           </td>
      </tr>
   </table>
</body>
</html>

Portal firmy również otrzymuje zaktualizowane ikony aplikacji dla systemów Android, iOS i Windows, aby poprawić spójność z innymi aplikacjami w rozwiązaniu EM+S. Ikony te będą stopniowo wydawane na różnych platformach od kwietnia do końca maja.

#### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Wskaźnik postępu logowania w aplikacji Portal firmy dla systemu Android <!--953374-->

Aktualizacja aplikacji Portal firmy dla systemu Android pokazuje wskaźnik postępu logowania, gdy użytkownik uruchomi lub wznowi działanie aplikacji. Wskaźnik przechodzi przez nowe stany, od „Trwa łączenie...” przez „Trwa logowanie...” do „Trwa sprawdzanie wymagań dotyczących bezpieczeństwa...”, zanim zezwoli użytkownikowi na dostęp do aplikacji.

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_android_signing_in_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Connecting' underneath it." width=200 height=366 align=center>
          </td>
          <td>
             <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_android_checking_security_reqs_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Signing in' underneath it." width=200 height=366 align=center>
           </td>
           <td>
              <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_android_connecting_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Checking for security requirements' underneath it." width=200 height=366 align=center>
           </td>
      </tr>
   </table>
</body>
</html>

## <a name="whats-been-announced-for-ui-updates-for-end-user-apps"></a>Ogłoszone aktualizacje interfejsu użytkownika aplikacji użytkownika końcowego

### <a name="february-2017"></a>Luty 2017

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
            <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_android_contactit_after.png" alt="The Company Portal app for Android displaying an updated version of the Contact IT tab. The tab shows available contact information for IT, including phone number, email address, IT website, and IT contact information." width=200 height=366 align=center>
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
* [Plan platformy w chmurze](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Co nowego w wersji zapoznawczej na platformie Azure](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [Archiwum nowości](whats-new-archive.md)

