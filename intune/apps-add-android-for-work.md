---
title: "Przypisywanie aplikacji do urządzeń z programem Android for Work"
titlesuffix: Azure portal
description: "W tym temacie opisano sposób synchronizowania, a następnie przypisywania aplikacji ze sklepu Google Play for Work na urządzeniach z programem Android for Work."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 06/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f873fa6324bab56ce8233a8a550e2d13fe2fb054
ms.sourcegitcommit: 9fabf1a8db53842f7b00762374de5b137158ee25
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-assign-apps-to-android-for-work-devices-with-intune"></a>Jak przypisywać aplikacje do urządzeń z programem Android for Work za pomocą usługi Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Przypisywanie aplikacji do urządzeń z programem Android for Work przebiega inaczej niż przypisywanie aplikacji do urządzeń ze standardową wersją systemu Android. Wszystkie aplikacje, które instalujesz dla programu Android for Work, pochodzą ze sklepu Google Play for Work. Proces obejmuje zalogowanie się do sklepu, wyszukanie odpowiednich aplikacji, a następnie ich zatwierdzenie.
Następnie aplikacja pojawia się w węźle **Licencjonowane aplikacje** w witrynie Azure Portal. Z poziomu tej witryny możesz zarządzać przypisywaniem aplikacji w taki sam sposób, jak przypisywaniem dowolnych innych aplikacji.

Ponadto możesz przypisywać własne aplikacje biznesowe, jeśli zostały one utworzone, w następujący sposób:
- Utwórz w ramach programu Google Developer konto, które pozwala publikować aplikacje w prywatnym obszarze w sklepie Google Play.
- Zsynchronizuj aplikacje z usługą Intune.

## <a name="before-you-start"></a>Przed rozpoczęciem

Upewnij się, że w obciążeniu **Rejestrowanie urządzenia** w witrynie Azure Portal usługa Intune i program Android for Work zostały skonfigurowane do współpracy.

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a>Synchronizowanie aplikacji ze sklepu Google Play for Work

1. Przejdź do [sklepu Google Play for Work](https://play.google.com/work). Zaloguj się za pomocą tego samego konta, którego użyto do skonfigurowania połączenia między usługą Intune i programem Android for Work.
2. Wyszukaj w sklepie aplikację, którą chcesz przypisać za pomocą usługi Intune.
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
6. W węźle **Aplikacje** w sklepie sprawdź, czy widać opublikowaną aplikację. Ta aplikacja została automatycznie zatwierdzona do synchronizacji z usługą Intune.

## <a name="assign-an-android-for-work-app"></a>Przypisywanie aplikacji Android for Work

Jeśli aplikacja ze sklepu została zatwierdzona, ale nie jest widoczna w węźle **Licencjonowane aplikacje** w obciążeniu **Aplikacje mobilne**, wymuś natychmiastową synchronizację w następujący sposób:

1. Zaloguj się do portalu Azure Portal.
2. W bloku **Intune** wybierz pozycję **Aplikacje mobilne**.
3. W obciążeniu **Aplikacje mobilne** wybierz kolejno opcje **Instalator** > **Android for Work**.
4. W bloku Android for Work wybierz pozycję **Synchronizuj teraz**.
5. Na tej stronie jest również wyświetlana godzina i stan ostatniej synchronizacji.

Gdy aplikacja zostanie wyświetlona w węźle **Licencjonowane aplikacje** w obciążeniu **Aplikacje mobilne**, możesz [przypisać ją w taki sam sposób, jak dowolną inną aplikację](/intune-azure/manage-apps/deploy-apps). Aplikacje można przypisywać tylko do grup użytkowników.

Po przypisaniu aplikacja zostanie zainstalowana na docelowych urządzeniach. Użytkownik urządzenia nie będzie monitowany o zatwierdzenie instalacji.

## <a name="manage-android-for-work-app-permissions"></a>Zarządzanie uprawnieniami aplikacji Android for Work
Program Android for Work wymaga zatwierdzenia aplikacji w zarządzanej konsoli internetowej Google Play przed ich zsynchronizowaniem z usługą Intune i przypisaniem do użytkowników.  Jako że usługa Android for Work umożliwia automatyczne i dyskretne wypychanie tych aplikacji na urządzenia użytkowników, należy zaakceptować uprawnienia aplikacji dla wszystkich użytkowników.  Podczas instalacji użytkownicy końcowi nie widzą żadnych uprawnień aplikacji, dlatego należy przeczytać i sprawdzić te uprawnienia.

Jeśli deweloper aplikacji publikuje nową wersję aplikacji ze zaktualizowanymi uprawnieniami, uprawnienia te nie są automatycznie akceptowane, nawet jeśli poprzednie uprawnienia zostały zatwierdzone. Użytkownicy urządzeń ze starszą wersją aplikacji nadal mogą z niej korzystać. Aplikacja nie zostanie jednak uaktualniona do momentu zatwierdzenia nowych uprawnień. Na urządzeniach, na których aplikacja nie jest jeszcze zainstalowana, nie można jej zainstalować do czasu zatwierdzenia nowych uprawnień.

### <a name="how-to-update-app-permissions"></a>Aktualizowanie uprawnień aplikacji

Należy okresowo odwiedzać zarządzaną konsolę Google Play w celu upewnienia się, czy aplikacja nie wymaga nowych uprawnień. Sklep Google Play można skonfigurować tak, aby w sytuacji, gdy dla zatwierdzonej aplikacji wymagane będą nowe uprawnienia, była wysyłana wiadomość e-mail na określone adresy. Jeśli po przypisaniu aplikacji okaże się, że nie jest ona zainstalowana na urządzeniach, sprawdź, czy aplikacja nie wymaga nowych uprawnień. W tym celu wykonaj następujące czynności:

1. Odwiedź witrynę http://play.google.com/work
2. Zaloguj się przy użyciu konta Google używanego do publikowania i zatwierdzania aplikacji.
3. Przejdź do karty **Aktualizacje**, aby zobaczyć, czy którakolwiek aplikacja wymaga aktualizacji.  Wszystkie wyświetlone aplikacje wymagają nowych uprawnień i nie zostaną przypisane do czasu ich zastosowania.  

Można także skonfigurować sklep Google Play w taki sposób, aby automatycznie ponownie zatwierdzał uprawnienia poszczególnych aplikacji. 



