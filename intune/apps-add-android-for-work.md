---
title: "Przypisywanie aplikacji do urządzeń z programem Android for Work | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: w tym temacie opisano sposób synchronizowania, a następnie przypisywania aplikacji ze sklepu Google Play for Work do urządzeń z programem Android for Work."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 49e86ab665d9022739c0330092734ba897ea3b02
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---

# <a name="how-to-assign-apps-to-android-for-work-devices-with-intune"></a>Jak przypisywać aplikacje do urządzeń z programem Android for Work za pomocą usługi Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Przypisywanie aplikacji do urządzeń z programem Android for Work przebiega inaczej niż przypisywanie aplikacji do urządzeń ze standardową wersją systemu Android. Wszystkie aplikacje, które instalujesz dla programu Android for Work, pochodzą ze sklepu Google Play for Work. Proces obejmuje zalogowanie się do sklepu, wyszukanie odpowiednich aplikacji, a następnie ich zatwierdzenie.
Następnie aplikacja jest widoczna w węźle **Licencjonowane aplikacje** w portalu usługi Intune. Z poziomu tej witryny możesz zarządzać przypisywaniem aplikacji w taki sam sposób, jak przypisywaniem dowolnych innych aplikacji.

Ponadto możesz przypisywać własne aplikacje biznesowe, jeśli zostały one utworzone. W tym celu musisz utworzyć konto w ramach programu Google Developer, które pozwala publikować aplikacje w prywatnym obszarze w sklepie Google Play, a następnie synchronizować je za pomocą usługi Intune.

## <a name="before-you-start"></a>Przed rozpoczęciem

Upewnij się, że w obciążeniu **Rejestrowanie urządzenia** w portalu usługi Intune usługa Intune i program Android for Work zostały skonfigurowane pod kątem do współpracy.

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a>Synchronizowanie aplikacji ze sklepu Google Play for Work


1. Przejdź do [sklepu Google Play for Work](https://play.google.com/work). Zaloguj się za pomocą tego samego konta, którego użyto do skonfigurowania połączenia między usługą Intune i programem Android for Work.
2. Wyszukaj w sklepie aplikację, którą chcesz przypisać za pomocą usługi Intune.
3. Na stronie wybranej aplikacji wybierz pozycję **Zatwierdź**. W tym przykładzie wybrano aplikację Microsoft Excel.<br>
  ![Przykładowe zatwierdzanie aplikacji](media/approve.png)
4. Zostanie otwarte okno aplikacji z monitem o nadanie uprawnień dla aplikacji do wykonywania poszczególnych operacji. Musisz wybrać pozycję **Zatwierdź**, aby kontynuować.<br>
  ![Przykładowe zatwierdzanie uprawnień aplikacji](media/approve-app-permissions.png)
5. Po chwili zostanie wyświetlony komunikat z potwierdzeniem, że aplikacja została zatwierdzona i jest dostępna w Twojej konsoli administratora IT.

## <a name="publish-then-synchronize-a-line-of-business-app-from-the-google-play-for-work-store"></a>Publikowanie, a następnie synchronizowanie aplikacji biznesowej ze sklepu Google Play for Work

1. Przejdź do konsoli dewelopera w sklepie Google Play — [play.google.com/apps/publish](https://play.google.com/apps/publish).
2. Zaloguj się za pomocą tego samego konta, którego użyto do skonfigurowania połączenia między usługą Intune i programem Android for Work. Jeśli logujesz się po raz pierwszy, musisz się zarejestrować i zapłacić opłatę, aby zostać członkiem programu Google Developer.
3. W konsoli wybierz pozycję **Dodaj nową aplikację**.
4. Informacje o aplikacji możesz przekazać i udostępnić w ten sam sposób, jak w przypadku publikowania dowolnych aplikacji w sklepie Google Play. Musisz jednak wybrać ustawienie **Udostępnij tę aplikację tylko dla mojej organizacji (<*nazwa organizacji*>)**, jak pokazano poniżej.<br>
  ![Opcja udostępniania aplikacji tylko dla danej organizacji](media/restrict.png)<br>
Zagwarantuje to, że aplikacja będzie dostępna tylko dla Twojej organizacji i nie będzie dostępna w publicznym sklepie Google Play.
Aby uzyskać więcej informacji o tym, jak przekazywać i publikować aplikacje systemu Android, zobacz [Konsola dewelopera Google — pomoc](https://support.google.com/googleplay/android-developer/answer/113469).
5. Po opublikowaniu aplikacji przejdź do [sklepu Google Play for Work](https://play.google.com/work). Zaloguj się za pomocą tego samego konta, którego użyto do skonfigurowania połączenia między usługą Intune i programem Android for Work.
6. W węźle **Aplikacje** w sklepie sprawdź, czy widać opublikowaną aplikację. Uwaga: aplikacja ta została automatycznie zatwierdzona w celu jej synchronizowania za pomocą usługi Intune.

## <a name="assign-an-android-for-work-app"></a>Przypisywanie aplikacji Android for Work

Jeśli aplikacja ze sklepu została zatwierdzona, ale nie jest jeszcze widoczna w węźle **Licencjonowane aplikacje** w obciążeniu **Aplikacje mobilne**, możesz wymusić natychmiastową synchronizację w następujący sposób:

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz pozycję **Aplikacje mobilne**.
4. W obciążeniu **Aplikacje mobilne** wybierz kolejno opcje **Instalator** > **Android for Work**.
5. W bloku Android for Work wybierz pozycję **Synchronizuj teraz**.
6. Na tej stronie jest również wyświetlana godzina i stan ostatniej synchronizacji.

Gdy aplikacja zostanie wyświetlona w węźle **Licencjonowane aplikacje** w obciążeniu **Aplikacje mobilne**, możesz [przypisać ją w taki sam sposób, jak dowolną inną aplikację](/intune-azure/manage-apps/deploy-apps). Aplikacje można przypisywać tylko do grup użytkowników.

Po przypisaniu aplikacja zostanie zainstalowana na docelowych urządzeniach. Użytkownik urządzenia nie będzie monitowany o zatwierdzenie instalacji.

## <a name="manage-app-permissions"></a>Zarządzanie uprawnieniami aplikacji
Program Android for Work wymaga zatwierdzenia aplikacji w zarządzanej konsoli internetowej Google Play przed ich zsynchronizowaniem z usługą Intune i przypisaniem do użytkowników.  Jako że usługa Android for Work umożliwia automatyczne i dyskretne wypychanie tych aplikacji na urządzenia użytkowników, należy zaakceptować uprawnienia aplikacji dla wszystkich użytkowników.  Podczas instalacji użytkownicy końcowi nie będą widzieć żadnych uprawnień aplikacji, dlatego należy przeczytać i sprawdzić te uprawnienia.

Jeśli deweloper aplikacji publikuje nową wersję aplikacji ze zaktualizowanymi uprawnieniami, uprawnienia te nie są automatycznie akceptowane, nawet jeśli poprzednie uprawnienia zostały zatwierdzone. Jeśli na urządzeniu istnieje stara wersja aplikacji, można nadal z niej korzystać, ale aplikacja nie zostanie uaktualniona do czasu zatwierdzenia nowych uprawnień. Na urządzeniach, na których aplikacja nie jest jeszcze zainstalowana, nie można jej zainstalować do czasu zatwierdzenia nowych uprawnień.

### <a name="how-to-update-app-permissions"></a>Aktualizowanie uprawnień aplikacji

Należy okresowo odwiedzać zarządzaną konsolę Google Play w celu upewnienia się, czy aplikacja nie wymaga nowych uprawnień. Jeśli po przypisaniu aplikacji okaże się, że nie jest ona zainstalowana na urządzeniach, sprawdź, czy aplikacja nie wymaga nowych uprawnień. W tym celu wykonaj następujące czynności:

1. Odwiedź witrynę http://play.google.com/work
2. Zaloguj się przy użyciu konta Google używanego do publikowania i zatwierdzania aplikacji.
3. Przejdź do karty **Aktualizacje**, aby zobaczyć, czy którakolwiek aplikacja wymaga aktualizacji.  Wszystkie wyświetlone aplikacje wymagają nowych uprawnień i nie zostaną przypisane do czasu ich zastosowania.  

