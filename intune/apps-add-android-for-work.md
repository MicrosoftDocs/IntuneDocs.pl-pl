---
title: Przypisywanie aplikacji do urządzeń z programem Android for Work
titlesuffix: Microsoft Intune
description: Dowiedz się, jak synchronizować aplikacje ze sklepu Google Play dla firm i przypisywać je do urządzeń z programem Android for Work.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1742c33642667a9e7b8ca2f780094345959cd86c
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2018
---
# <a name="assign-apps-to-android-for-work-devices-with-intune"></a>Przypisywanie aplikacji do urządzeń z programem Android for Work za pomocą usługi Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Android for Work to program dla urządzeń z systemem Android. Wszystkie aplikacje instalowane na urządzeniach z programem Android for Work pochodzą ze sklepu Google Play for Work. Przypisywanie aplikacji do urządzeń z programem Android for Work przebiega inaczej niż przypisywanie aplikacji do urządzeń ze standardową wersją systemu Android. Proces obejmuje zalogowanie się do sklepu, wyszukanie odpowiednich aplikacji, a następnie ich zatwierdzenie. Następnie aplikacja zostaje wyświetlona w węźle **Licencjonowane aplikacje** w witrynie Azure Portal i można zarządzać przypisaniem aplikacji w taki sam sposób, jak w przypadku wszystkich innych.

Ponadto możesz przypisywać utworzone samodzielnie aplikacje biznesowe w następujący sposób:
- Utwórz w ramach programu Google Developer konto, które pozwala publikować aplikacje w prywatnym obszarze w sklepie Google Play.
- Zsynchronizuj aplikacje z usługą Intune.

## <a name="before-you-start"></a>Przed rozpoczęciem

Upewnij się, że w obciążeniu **Rejestrowanie urządzenia** w witrynie Azure Portal usługa Intune i program Android for Work zostały skonfigurowane do współpracy.

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a>Synchronizowanie aplikacji ze sklepu Google Play for Work

1. Przejdź do [sklepu Google Play for Work](https://play.google.com/work). Zaloguj się za pomocą tego samego konta, którego użyto do skonfigurowania połączenia między usługą Intune i programem Android for Work.
2. Wyszukaj w sklepie i wybierz aplikację, którą chcesz przypisać za pomocą usługi Intune.
3. Na stronie z wyświetloną aplikacją wybierz pozycję **Zatwierdź**.  
    W poniższym przykładzie wybrano aplikację Microsoft Excel.

    ![Przycisk Zatwierdź w sklepie Google Play dla firm](media/approve.png)
    
   Zostanie otwarte okno aplikacji z monitem o nadanie uprawnień dla aplikacji do wykonywania poszczególnych operacji. 

4. Wybierz pozycję **Zatwierdź**, aby zaakceptować uprawnienia aplikacji i kontynuować.

    ![Przycisk Zatwierdź na potrzeby uprawnień aplikacji](media/approve-app-permissions.png)

5. Wybierz opcję obsługi nowych żądań dotyczących uprawnień aplikacji, a następnie wybierz pozycję **Zapisz**.

    ![Opcje obsługi nowych żądań dotyczących uprawnień aplikacji](media/approve-app-settings.png)

    Aplikacja została zatwierdzona i jest wyświetlana w konsoli administratora IT. Następnie możesz [zsynchronizować aplikację Android for Work z usługą Intune](apps-add-android-for-work.md#sync-an-android-for-work-app-with-intune). 

## <a name="sync-an-android-for-work-app-with-intune"></a>Synchronizowanie aplikacji Android for Work z usługą Intune

Jeśli aplikacja ze sklepu została zatwierdzona, ale nie jest widoczna w węźle **Licencjonowane aplikacje** w obciążeniu **Aplikacje mobilne**, wymuś natychmiastową synchronizację w następujący sposób:

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Aplikacje mobilne**.
4. W okienku obciążenia **Aplikacje mobilne** w obszarze **Instalacja** wybierz pozycję **Android for Work**.
5. W okienku **Android for Work** wybierz pozycję **Synchronizuj**.  
    Strona aktualizuje godzinę i stan ostatniej synchronizacji.
6. W okienku obciążenia **Aplikacje mobilne** wybierz pozycję **Aplikacje**.  
    Zostanie wyświetlona nowo udostępniona aplikacja Android for Work.

Gdy aplikacja zostanie wyświetlona w węźle **Licencje aplikacji** w okienku obciążenia **Aplikacje mobilne**, możesz [przypisać ją w taki sam sposób, jak dowolną inną aplikację](/intune-azure/manage-apps/deploy-apps). Aplikacje można przypisywać tylko do grup użytkowników.

Po przypisaniu aplikacja jest instalowana na urządzeniach docelowych. Użytkownik urządzenia nie będzie monitowany o zatwierdzenie instalacji.

## <a name="manage-android-for-work-app-permissions"></a>Zarządzanie uprawnieniami aplikacji Android for Work
Program Android for Work wymaga zatwierdzenia aplikacji w zarządzanej konsoli internetowej Google Play przed ich zsynchronizowaniem z usługą Intune i przypisaniem do użytkowników. Ponieważ program Android for Work umożliwia automatyczne i dyskretne wypychanie aplikacji na urządzenia użytkowników, należy zaakceptować uprawnienia aplikacji w imieniu wszystkich użytkowników. Podczas instalacji użytkownicy nie widzą żadnych uprawnień aplikacji, dlatego należy przeczytać i zrozumieć uprawnienia.

Jeśli deweloper aplikacji publikuje nową wersję aplikacji ze zaktualizowanymi uprawnieniami, uprawnienia nie są automatycznie akceptowane, nawet jeśli poprzednie uprawnienia zostały zatwierdzone. Użytkownicy urządzeń z poprzednią wersją aplikacji nadal mogą z niej korzystać. Aplikacja nie zostanie jednak uaktualniona do momentu zatwierdzenia nowych uprawnień. Na urządzeniach, na których aplikacja nie jest jeszcze zainstalowana, nie można jej zainstalować do czasu zatwierdzenia nowych uprawnień.

### <a name="update-app-permissions"></a>Aktualizowanie uprawnień aplikacji

Należy okresowo odwiedzać zarządzaną konsolę Google Play w celu upewnienia się, czy aplikacja nie wymaga nowych uprawnień. Sklep Google Play można skonfigurować tak, aby w sytuacji, gdy dla zatwierdzonej aplikacji wymagane będą nowe uprawnienia, była wysyłana wiadomość e-mail na określone adresy. Jeśli po przypisaniu aplikacji okaże się, że nie zainstalowano jej na urządzeniach, sprawdź, czy aplikacja nie wymaga nowych uprawnień, wykonując następujące czynności:

1. Przejdź do sklepu [Google Play](http://play.google.com/work).
2. Zaloguj się przy użyciu konta Google używanego do publikowania i zatwierdzania aplikacji.
3. Wybierz kartę **Aktualizacje** i sprawdź, czy którekolwiek aplikacje wymagają aktualizacji.  
    Wszystkie wyświetlone aplikacje wymagają nowych uprawnień i nie zostaną przypisane do czasu ich zastosowania.

Można także skonfigurować sklep Google Play w taki sposób, aby automatycznie ponownie zatwierdzał uprawnienia poszczególnych aplikacji. 

## <a name="working-with-a-line-of-business-app-from-the-google-play-for-work-store"></a>Praca z aplikacją biznesową ze sklepu Google Play for Work

1. Zaloguj się do [konsoli programisty Google Play](https://play.google.com/apps/publish) za pomocą tego samego konta, którego użyto do skonfigurowania połączenia między usługą Intune i programem Android for Work.  
    Jeśli logujesz się po raz pierwszy, musisz się zarejestrować i zapłacić opłatę, aby zostać członkiem programu Google Developer.
2. W konsoli wybierz pozycję **Dodaj nową aplikację**.
3. Informacje o aplikacji możesz przekazać i udostępnić w ten sam sposób, jak w przypadku publikowania dowolnych aplikacji w sklepie Google Play. Musisz jednak wybrać pozycję **Udostępnij tę aplikację tylko dla mojej organizacji (<*nazwa organizacji*>)**.

    ![Udostępnianie aplikacji tylko dla danej organizacji](media/restrict.png)

    Ta czynność zagwarantuje, że aplikacja będzie dostępna tylko dla Twojej organizacji i nie będzie dostępna w publicznym sklepie Google Play.

    Aby uzyskać więcej informacji na temat przekazywania i publikowania aplikacji systemu Android, zobacz [Konsola programisty Google — pomoc](https://support.google.com/googleplay/android-developer/answer/113469).
4. Po opublikowaniu aplikacji zaloguj się do [sklepu Google Play dla firm](https://play.google.com/work) za pomocą tego samego konta, którego użyto do skonfigurowania połączenia między usługą Intune i programem Android for Work.
5. W węźle **Aplikacje** w sklepie sprawdź, czy opublikowana aplikacja jest widoczna.  
    Ta aplikacja została automatycznie zatwierdzona do synchronizacji z usługą Intune.

## <a name="next-steps"></a>Następne kroki

- [Przypisywanie aplikacji do grup](apps-deploy.md) 

