---
title: "Przypisywanie aplikacji do urządzeń z programem Android for Work"
titlesuffix: Microsoft Intune
description: "Dowiedz się, jak synchronizować aplikacje ze sklepu Google Play for Work Store i przypisywać je do urządzeń z programem Android for Work."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e3b5a742fb480cf9c4c77106b849eebb95ad2439
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-assign-apps-to-android-for-work-devices-with-intune"></a>Jak przypisywać aplikacje do urządzeń z programem Android for Work za pomocą usługi Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Android for Work to program dla urządzeń z systemem Android. Wszystkie aplikacje instalowane na urządzeniach z programem Android for Work pochodzą ze sklepu Google Play for Work. Przypisywanie aplikacji do urządzeń z programem Android for Work przebiega inaczej niż przypisywanie aplikacji do urządzeń ze standardową wersją systemu Android. Proces obejmuje zalogowanie się do sklepu, wyszukanie odpowiednich aplikacji, a następnie ich zatwierdzenie. Następnie aplikacja pojawia się w węźle **Licencjonowane aplikacje** w witrynie Azure Portal. Z poziomu tej witryny możesz zarządzać przypisywaniem aplikacji w taki sam sposób, jak przypisywaniem dowolnych innych aplikacji.

Ponadto możesz przypisywać własne aplikacje biznesowe, jeśli zostały one utworzone, w następujący sposób:
- Utwórz w ramach programu Google Developer konto, które pozwala publikować aplikacje w prywatnym obszarze w sklepie Google Play.
- Zsynchronizuj aplikacje z usługą Intune.

## <a name="before-you-start"></a>Przed rozpoczęciem

Upewnij się, że w obciążeniu **Rejestrowanie urządzenia** w witrynie Azure Portal usługa Intune i program Android for Work zostały skonfigurowane do współpracy.

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a>Synchronizowanie aplikacji ze sklepu Google Play for Work

1. Przejdź do [sklepu Google Play for Work](https://play.google.com/work). Zaloguj się za pomocą tego samego konta, którego użyto do skonfigurowania połączenia między usługą Intune i programem Android for Work.
2. Wyszukaj w sklepie i wybierz aplikację, którą chcesz przypisać za pomocą usługi Intune.
3. Wybierz pozycję **Zatwierdź** na stronie przedstawiającej aplikację. W poniższych przykładach wybrana została aplikacja Microsoft Excel.</br>

    ![Przykład — zatwierdzanie aplikacji w sklepie Google Play for Work](media/approve.png)</br>
    
  Zostanie otwarte okno aplikacji z monitem o nadanie uprawnień dla aplikacji do wykonywania poszczególnych operacji. 

4. Wybierz pozycję **Zatwierdź**, aby zaakceptować uprawnienia aplikacji i kontynuować.</br>

    ![Przykład — zatwierdzanie uprawnień aplikacji](media/approve-app-permissions.png)

5. Wybierz sposób obsługi nowych żądań uprawnień aplikacji. Następnie wybierz opcję **Zapisz**, aby zapisać sposób obsługi nowych żądań uprawnień aplikacji.</br>

    ![Przykład — zapisywanie nowych żądań uprawnień aplikacji](media/approve-app-settings.png)</br>

    Aplikacja została zatwierdzona i jest widoczna w konsoli administratora IT. Teraz możesz [zsynchronizować aplikację Android for Work z usługą Intune](apps-add-android-for-work.md#sync-an-android-for-work-app-with-intune). 

## <a name="sync-an-android-for-work-app-with-intune"></a>Synchronizowanie aplikacji Android for Work z usługą Intune

Jeśli aplikacja ze sklepu została zatwierdzona, ale nie jest widoczna w węźle **Licencjonowane aplikacje** w obciążeniu **Aplikacje mobilne**, wymuś natychmiastową synchronizację w następujący sposób:

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie + zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Aplikacje mobilne**.
4. W obciążeniu **Aplikacje mobilne** wybierz pozycję **Android for Work** w sekcji **Konfiguracja**.
5. W okienku Android for Work wybierz pozycję **Synchronizuj**. Strona zaktualizuje godzinę i stan ostatniej synchronizacji.
6. W obciążeniu **Aplikacje mobilne** wybierz pozycję **Aplikacje**, aby wyświetlić nowo dostępne aplikacje Android for Work.

Gdy aplikacja zostanie wyświetlona w węźle **Licencje aplikacji** w obciążeniu **Aplikacje mobilne**, możesz [przypisać ją w taki sam sposób, jak dowolną inną aplikację](/intune-azure/manage-apps/deploy-apps). Aplikacje można przypisywać tylko do grup użytkowników.

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

## <a name="working-with-a-line-of-business-app-from-the-google-play-for-work-store"></a>Praca z aplikacją biznesową ze sklepu Google Play for Work

1. Przejdź do konsoli dewelopera w sklepie Google Play — [play.google.com/apps/publish](https://play.google.com/apps/publish).
2. Zaloguj się za pomocą tego samego konta, którego użyto do skonfigurowania połączenia między usługą Intune i programem Android for Work. Jeśli logujesz się po raz pierwszy, musisz się zarejestrować i zapłacić opłatę, aby zostać członkiem programu Google Developer.
3. W konsoli wybierz pozycję **Dodaj nową aplikację**.
4. Informacje o aplikacji możesz przekazać i udostępnić w ten sam sposób, jak w przypadku publikowania dowolnych aplikacji w sklepie Google Play. Musisz jednak wybrać ustawienie **Udostępnij tę aplikację tylko dla mojej organizacji (<*nazwa organizacji*>)**:</br>

    ![Opcja udostępniania aplikacji tylko dla danej organizacji](media/restrict.png)</br>

Ta czynność zagwarantuje, że aplikacja będzie dostępna tylko dla Twojej organizacji i nie będzie dostępna w publicznym sklepie Google Play.
Aby uzyskać więcej informacji o tym, jak przekazywać i publikować aplikacje systemu Android, zobacz [Konsola dewelopera Google — pomoc](https://support.google.com/googleplay/android-developer/answer/113469).
5. Po opublikowaniu aplikacji przejdź do [sklepu Google Play for Work](https://play.google.com/work). Zaloguj się za pomocą tego samego konta, którego użyto do skonfigurowania połączenia między usługą Intune i programem Android for Work.
6. W węźle **Aplikacje** w sklepie sprawdź, czy widać opublikowaną aplikację. Ta aplikacja została automatycznie zatwierdzona do synchronizacji z usługą Intune.

## <a name="next-steps"></a>Następne kroki

- [Jak przypisać aplikacje do grup](apps-deploy.md)

