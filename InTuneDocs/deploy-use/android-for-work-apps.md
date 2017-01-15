---
title: "Wdrażanie aplikacji na urządzeniach z programem Android for Work | Microsoft Docs"
description: "W tym temacie opisano sposób synchronizowania, a następnie wdrażania aplikacji ze sklepu Google Play for Work na urządzeniach z programem Android for Work."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/6/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd0bbd90-d3fe-4efc-83fd-d1f3f86800d4
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: c3a46f9a8e66a1d7de8878105f5752b17a3857b7


---

# <a name="how-to-deploy-apps-to-android-for-work-devices-with-intune"></a>Jak wdrażać aplikacje na urządzeniach z programem Android for Work za pomocą usługi Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

Wdrażanie aplikacji na urządzeniach z programem Android for Work przebiega inaczej niż wdrażanie aplikacji na urządzaniach ze standardową wersją systemu Android. Wszystkie aplikacje, które instalujesz dla programu Android for Work, pochodzą ze sklepu Google Play for Work. Proces obejmuje zalogowanie się do sklepu, wyszukanie odpowiednich aplikacji, a następnie ich zatwierdzenie.
Następnie aplikacja jest wyświetlana w węźle **Aplikacje kupione w ramach zakupów zbiorczych** w konsoli usługi Intune. Z poziomu tej konsoli możesz zarządzać wdrażaniem aplikacji w ten sam sposób, w jaki wdrażasz dowolne inne aplikacje.
Ponadto możesz wdrażać swoje własne aplikacje biznesowe, jeśli zostały one przez Ciebie utworzone. W tym celu musisz utworzyć konto w ramach programu Google Developer, które pozwala publikować aplikacje w prywatnym obszarze w sklepie Google Play, a następnie synchronizować je za pomocą usługi Intune.

## <a name="before-you-start"></a>Przed rozpoczęciem

1. Na karcie **Administrator** w konsoli usługi Intune upewnij się, że skonfigurowano usługę Intune i program Android for Work do współdziałania.

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a>Synchronizowanie aplikacji ze sklepu Google Play for Work


1. Przejdź do [sklepu Google Play for Work](https://play.google.com/work). Zaloguj się za pomocą tego samego konta, którego użyto do skonfigurowania połączenia między usługą Intune i programem Android for Work.
2. Wyszukaj w sklepie aplikację, którą chcesz wdrożyć za pomocą usługi Intune.
3. Na stronie wybranej aplikacji wybierz pozycję **Zatwierdź**. W tym przykładzie wybrano aplikację Microsoft Excel.<br>
  ![Przykładowe zatwierdzanie aplikacji](/intune/deploy-use/media/approve.png)
4. Zostanie otwarte okno aplikacji z monitem o nadanie uprawnień dla aplikacji do wykonywania poszczególnych operacji. Musisz wybrać pozycję **Zatwierdź**, aby kontynuować.<br>
  ![Przykładowe zatwierdzanie uprawnień aplikacji](/intune/deploy-use/media/approve-app-permissions.png)
5. Po chwili zostanie wyświetlony komunikat z potwierdzeniem, że aplikacja została zatwierdzona i jest dostępna w Twojej konsoli administratora IT.

## <a name="publish-then-synchronize-a-line-of-business-app-from-the-google-play-for-work-store"></a>Publikowanie, a następnie synchronizowanie aplikacji biznesowej ze sklepu Google Play for Work

1. Przejdź do konsoli dewelopera w sklepie Google Play — [play.google.com/apps/publish](https://play.google.com/apps/publish).
2. Zaloguj się za pomocą tego samego konta, którego użyto do skonfigurowania połączenia między usługą Intune i programem Android for Work. Jeśli logujesz się po raz pierwszy, musisz się zarejestrować i zapłacić opłatę, aby zostać członkiem programu Google Developer.
3. W konsoli wybierz pozycję **Dodaj nową aplikację**.
4. Informacje o aplikacji możesz przekazać i udostępnić w ten sam sposób, jak w przypadku publikowania dowolnych aplikacji w sklepie Google Play. Musisz jednak wybrać ustawienie **Udostępnij tę aplikację tylko dla mojej organizacji (<*nazwa organizacji*>)**, jak pokazano poniżej.<br>
  ![Opcja udostępniania aplikacji tylko dla danej organizacji](/intune/deploy-use/media/restrict.png)<br>
Zagwarantuje to, że aplikacja będzie dostępna tylko dla Twojej organizacji i nie będzie dostępna w publicznym sklepie Google Play.
Aby uzyskać więcej informacji o tym, jak przekazywać i publikować aplikacje systemu Android, zobacz [Konsola dewelopera Google — pomoc](https://support.google.com/googleplay/android-developer/answer/113469).
5. Po opublikowaniu aplikacji przejdź do [sklepu Google Play for Work](https://play.google.com/work). Zaloguj się za pomocą tego samego konta, którego użyto do skonfigurowania połączenia między usługą Intune i programem Android for Work.
6. W węźle **Aplikacje** w sklepie sprawdź, czy widać opublikowaną aplikację. Uwaga: aplikacja ta została automatycznie zatwierdzona w celu jej synchronizowania za pomocą usługi Intune.

## <a name="deploy-an-android-for-work-app"></a>Wdrażanie aplikacji programu Android for Work

Zwykle usługa Intune będzie przeprowadzać synchronizację ze sklepem Google Play for Work dwa razy dziennie. Jeśli zatwierdzono aplikację ze sklepu, ale jeszcze nie widać tej aplikacji w węźle **Aplikacje kupione w ramach zakupów zbiorczych** w obszarze roboczym **Aplikacje**, możesz wymusić natychmiastową synchronizację w poniższy sposób:

1. W [konsoli administratora usługi Intune](https://manage.microsoft.com) wybierz pozycję **Administracja** > **Zarządzanie urządzeniami przenośnymi** > **Android for Work**.
2. Na stronie **Konfiguracja zarządzania urządzeniami przenośnymi obsługującymi program Android for Work** wybierz pozycję **Synchronizuj teraz**.
3. Na tej stronie jest również wyświetlana godzina i stan ostatniej synchronizacji.

Gdy aplikacja zostanie wyświetlona w węźle **Aplikacje kupione w ramach zakupów zbiorczych** w obszarze roboczym **Aplikacje**, możesz [wdrożyć ją dokładnie tak samo, jak dowolną inną aplikację](deploy-apps-in-microsoft-intune.md). Aplikację można wdrażać tylko do grup użytkowników. Obecnie możesz wybrać tylko akcje **Wymagana** i **Odinstaluj**. Od października 2016 zaczniemy dodawać akcję wdrażania **Dostępna** w nowych dzierżawach.

Po wdrożeniu aplikacja zostanie zainstalowana na urządzeniach docelowych. Użytkownik urządzenia nie będzie monitowany o zatwierdzenie.



<!--HONumber=Dec16_HO2-->


