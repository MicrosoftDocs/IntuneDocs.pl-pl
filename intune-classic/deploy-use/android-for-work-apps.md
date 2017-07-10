---
title: "Wdrażanie aplikacji na urządzeniach z programem Android for Work"
description: "W tym temacie opisano sposób synchronizowania, a następnie wdrażania aplikacji ze sklepu Google Play for Work na urządzeniach z programem Android for Work."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd0bbd90-d3fe-4efc-83fd-d1f3f86800d4
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: adc4a343e610a1a75f8a5bc51a1894f6fcf998bb
ms.sourcegitcommit: c9b3a95bf529b6cb2a2bdacbc49127dfa0c233e5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/05/2017
---
# <a name="how-to-deploy-apps-to-android-for-work-devices-with-intune"></a>Jak wdrażać aplikacje na urządzeniach z programem Android for Work za pomocą usługi Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Wdrażanie aplikacji na urządzeniach z programem Android for Work przebiega inaczej niż wdrażanie aplikacji na urządzaniach ze standardową wersją systemu Android. Wszystkie aplikacje, które instalujesz dla programu Android for Work, pochodzą ze sklepu Google Play for Work. Proces obejmuje zalogowanie się do sklepu, wyszukanie odpowiednich aplikacji, a następnie ich zatwierdzenie.
Następnie aplikacja jest wyświetlana w węźle **Aplikacje kupione w ramach zakupów zbiorczych** w konsoli usługi Intune. Z poziomu tej konsoli możesz zarządzać wdrażaniem aplikacji w ten sam sposób, w jaki wdrażasz dowolne inne aplikacje.

Ponadto możesz wdrażać swoje własne aplikacje biznesowe, jeśli zostały one przez Ciebie utworzone. W tym celu:
- Utwórz konto w ramach programu Google Developer, które pozwala publikować aplikacje w prywatnym obszarze w sklepie Google Play.
- Zsynchronizuj aplikacje z usługą Intune.

## <a name="before-you-start"></a>Przed rozpoczęciem

Na karcie **Administrator** w konsoli usługi Intune upewnij się, że skonfigurowano usługę Intune i program Android for Work do współdziałania.

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a>Synchronizowanie aplikacji ze sklepu Google Play for Work


1. Przejdź do [sklepu Google Play for Work](https://play.google.com/work). Zaloguj się za pomocą tego samego konta, którego użyto do skonfigurowania połączenia między usługą Intune i programem Android for Work.
2. Wyszukaj w sklepie aplikację, którą chcesz wdrożyć za pomocą usługi Intune.
3. Na stronie wybranej aplikacji wybierz pozycję **Zatwierdź**. W tym przykładzie wybrano aplikację Microsoft Excel.<br>
  ![Przykładowe zatwierdzanie aplikacji](media/approve.png)
4. Zostanie otwarte okno aplikacji z monitem o nadanie uprawnień dla aplikacji do wykonywania poszczególnych operacji. Wybierz pozycję **Zatwierdź**, aby kontynuować.<br>
  ![Przykładowe zatwierdzanie uprawnień aplikacji](media/approve-app-permissions.png)
5. Aplikacja została zatwierdzona i jest widoczna w konsoli administratora IT.

## <a name="publish-then-synchronize-a-line-of-business-app-from-the-google-play-for-work-store"></a>Publikowanie, a następnie synchronizowanie aplikacji biznesowej ze sklepu Google Play for Work

1. Przejdź do konsoli dewelopera w sklepie Google Play — [play.google.com/apps/publish](https://play.google.com/apps/publish).
2. Zaloguj się za pomocą tego samego konta, którego użyto do skonfigurowania połączenia między usługą Intune i programem Android for Work. Jeśli logujesz się po raz pierwszy, musisz się zarejestrować i zapłacić opłatę, aby zostać członkiem programu Google Developer.
3. W konsoli wybierz pozycję **Dodaj nową aplikację**.
4. Informacje o aplikacji możesz przekazać i udostępnić w ten sam sposób, jak w przypadku publikowania dowolnych aplikacji w sklepie Google Play. Musisz jednak wybrać ustawienie **Udostępnij tę aplikację tylko dla mojej organizacji (<*nazwa organizacji*>)**:<br>
  ![Opcja udostępniania aplikacji tylko dla danej organizacji](media/restrict.png)<br>
Ta czynność zagwarantuje, że aplikacja będzie dostępna tylko dla Twojej organizacji i nie będzie dostępna w publicznym sklepie Google Play.
Aby uzyskać więcej informacji o tym, jak przekazywać i publikować aplikacje systemu Android, zobacz [Konsola dewelopera Google — pomoc](https://support.google.com/googleplay/android-developer/answer/113469).
5. Po opublikowaniu aplikacji przejdź do [sklepu Google Play for Work](https://play.google.com/work). Zaloguj się za pomocą tego samego konta, którego użyto do skonfigurowania połączenia między usługą Intune i programem Android for Work.
6. W węźle **Aplikacje** w sklepie sprawdź, czy widać opublikowaną aplikację. Aplikacja zostanie automatycznie zatwierdzona do synchronizacji z usługą Intune.

## <a name="deploy-an-android-for-work-app"></a>Wdrażanie aplikacji programu Android for Work

Jeśli zatwierdzono aplikację ze sklepu, ale jeszcze nie widać tej aplikacji w węźle **Aplikacje kupione w ramach zakupów zbiorczych** w obszarze roboczym **Aplikacje**, możesz wymusić natychmiastową synchronizację w następujący sposób:

1. W [konsoli administratora usługi Intune](https://manage.microsoft.com) wybierz pozycję **Administracja** > **Zarządzanie urządzeniami przenośnymi** > **Android for Work**.
2. Na stronie **Konfiguracja zarządzania urządzeniami przenośnymi obsługującymi program Android for Work** wybierz pozycję **Synchronizuj teraz**.
3. Na tej stronie jest również wyświetlana godzina i stan ostatniej synchronizacji.

Gdy aplikacja zostanie wyświetlona w węźle **Aplikacje kupione w ramach zakupów zbiorczych** w obszarze roboczym **Aplikacje**, możesz [wdrożyć ją dokładnie tak samo, jak dowolną inną aplikację](deploy-apps-in-microsoft-intune.md). Aplikację można wdrażać tylko do grup użytkowników. Obecnie możesz wybrać tylko akcje **Wymagana** i **Odinstaluj**.

Wdrożenie aplikacji ze stanem **Dostępna** pozwala zastosować nowe funkcje grupowania i kierowania. Użytkownicy nowo aprowizowanych kont usługi Intune mogą korzystać z tej funkcji po jej udostępnieniu. Istniejący klienci usługi Intune mogą używać tej funkcji po zmigrowaniu ich dzierżawy do portalu usługi Intune Azure. Istniejący klienci mogą utworzyć konto w wersji próbnej usługi Intune w celu zaplanowania działań związanych z tą funkcją i testowania jej do czasu migracji ich dzierżawy.

Po wdrożeniu aplikacja zostanie zainstalowana na urządzeniach docelowych. Użytkownik urządzenia nie będzie monitowany o zatwierdzenie.

## <a name="manage-app-permissions"></a>Zarządzanie uprawnieniami aplikacji
Usługa Android for Work wymaga zatwierdzenia aplikacji w zarządzanej konsoli internetowej Google Play przed ich zsynchronizowaniem z usługą Intune i wdrożeniem na urządzeniach użytkowników.  Jako że usługa Android for Work umożliwia automatyczne i dyskretne wypychanie tych aplikacji na urządzenia użytkowników, należy zaakceptować uprawnienia aplikacji dla wszystkich użytkowników.  Podczas instalacji użytkownicy końcowi nie widzą żadnych uprawnień aplikacji, dlatego należy przeczytać i sprawdzić te uprawnienia.

Jeśli deweloper aplikacji publikuje nową wersję aplikacji ze zaktualizowanymi uprawnieniami, uprawnienia te nie są automatycznie akceptowane, nawet jeśli poprzednie uprawnienia zostały zatwierdzone. Jeśli na urządzeniu istnieje stara wersja aplikacji, można nadal z niej korzystać, ale aplikacja nie zostanie uaktualniona do czasu zatwierdzenia nowych uprawnień. Na urządzeniach, na których aplikacja nie jest jeszcze zainstalowana, nie można jej zainstalować do czasu zatwierdzenia nowych uprawnień.

### <a name="how-to-update-app-permissions"></a>Aktualizowanie uprawnień aplikacji

Należy okresowo odwiedzać zarządzaną konsolę Google Play w celu upewnienia się, czy aplikacja nie wymaga nowych uprawnień. Sklep Google Play można skonfigurować tak, aby w sytuacji, gdy dla zatwierdzonej aplikacji wymagane będą nowe uprawnienia, była wysyłana wiadomość e-mail na określone adresy. Jeśli po przypisaniu aplikacji okaże się, że nie jest ona zainstalowana na urządzeniach, sprawdź, czy aplikacja nie wymaga nowych uprawnień. W tym celu wykonaj następujące czynności:

1. Odwiedź witrynę http://play.google.com/work
2. Zaloguj się przy użyciu konta Google używanego do publikowania i zatwierdzania aplikacji.
3. Przejdź do karty **Aktualizacje**, aby zobaczyć, czy którakolwiek aplikacja wymaga aktualizacji.  Wszystkie wyświetlone aplikacje wymagają nowych uprawnień i nie zostaną przypisane do czasu ich zastosowania.  

Można także skonfigurować sklep Google Play w taki sposób, aby automatycznie ponownie zatwierdzał uprawnienia poszczególnych aplikacji. 
