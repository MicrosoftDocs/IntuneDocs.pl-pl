---
title: Przypisywanie zarządzanych aplikacji ze sklepu Google Play do urządzeń z systemem Android Enterprise
titlesuffix: Microsoft Intune
description: Dowiedz się, jak synchronizować aplikacje z zarządzanego sklepu Google Play i przypisywać je do urządzeń z systemem Android Enterprise.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/25/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: a2f339c9ecf79f3c2e4e87eccd9a5f3b80046aa0
ms.sourcegitcommit: 17f58d35a6bdff3e179662f3731fc74d39144470
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/28/2019
ms.locfileid: "55105208"
---
# <a name="add-managed-google-play-apps-to-android-enterprise-devices-with-intune"></a>Dodawanie zarządzanych aplikacji ze sklepu Google Play do urządzeń z systemem Android Enterprise z usługą Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Rozwiązanie Android Enterprise to program obejmujący urządzenia z profilem służbowym systemu Android, urządzenia dedykowane, urządzenia kiosku oraz urządzenia w pełni zarządzane. W przypadku urządzeń z profilem służbowym systemu Android rozwiązanie Android enterprise to zestaw funkcji i usług, które oddzielają osobiste aplikacje i dane od służbowych aplikacji i danych. Rozwiązanie Android enterprise udostępnia dodatkowe opcje zarządzania i ochrony prywatności, które ułatwiają użytkownikom korzystanie z urządzeń z systemem Android w celach służbowych. Usługa Intune ułatwia wdrażanie aplikacji i ustawień na urządzeniach z profilem służbowym systemu Android, co zapewnia oddzielenie informacji osobistych od służbowych. Wszystkie aplikacje, które instalujesz na urządzeniach z profilem służbowym systemu Android, pochodzą z zarządzanego sklepu Google Play. Przypisywanie aplikacji do urządzeń z profilem służbowym systemu Android przebiega inaczej niż przypisywanie aplikacji do standardowych urządzeń z systemem Android. Proces obejmuje zalogowanie się do sklepu, wyszukanie odpowiednich aplikacji, a następnie ich zatwierdzenie. Następnie aplikacja zostaje wyświetlona w węźle **Licencjonowane aplikacje** w witrynie Azure Portal i można zarządzać przypisaniem aplikacji w taki sam sposób, jak w przypadku wszystkich innych.

Ponadto możesz przypisywać utworzone samodzielnie aplikacje biznesowe w następujący sposób:
- Utwórz w ramach programu Google Developer konto, które pozwala publikować aplikacje w prywatnym obszarze w sklepie Google Play.
- Zsynchronizuj aplikacje z usługą Intune.

## <a name="before-you-start"></a>Przed rozpoczęciem

Upewnij się, że w obciążeniu **Rejestrowanie urządzenia** w witrynie Azure Portal usługa Intune i profile służbowe systemu Android zostały skonfigurowane do współpracy. Aby uzyskać więcej informacji, zobacz [Rejestrowanie urządzeń z systemem Android](android-work-profile-enroll.md).

>[!NOTE]
>Jeśli pracujesz, korzystając z usługi Microsoft Intune, firma Microsoft zaleca używanie przeglądarki Microsoft Edge lub Google Chrome.

## <a name="managed-google-play-app-type"></a>Typ aplikacji zarządzanej ze sklepu Google Play 
Dzięki zastosowaniu typów aplikacji **zarządzanych ze sklepu Google Play** będzie można wybiórczo dodawać [aplikacje zarządzane ze sklepu Google Play](https://play.google.com/work/search?q=microsoft&c=apps) do usługi Intune. Administratorzy usługi Intune mogą przeglądać, wyszukiwać, zatwierdzać, synchronizować i przypisywać zatwierdzone aplikacje zarządzane ze sklepu Google Play z poziomu usługi Intune.  Nie jest już konieczne przechodzenie do zarządzanej konsoli Google Play i dokonywanie ponownego uwierzytelniania. 

> [!NOTE]
> Jeśli chcesz zsynchronizować aplikację zarządzaną ze sklepu Google Play z usługą Intune, zobacz sekcję [Synchronizowanie aplikacji z zarządzanego sklepu Google Play przy użyciu usługi Intune](apps-add-android-for-work.md#synchronize-a-managed-google-play-app-with-intune-alternative)

## <a name="add-a-managed-google-play-app-using-intune"></a>Dodawanie aplikacji zarządzanej ze sklepu Google Play przy użyciu usługi Intune

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi** > **Intune**.  
    Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Aplikacje klienckie** > **Aplikacje**.
5. W okienku **Aplikacje** wybierz pozycję **Dodaj**.
6. W polu listy rozwijanej **Typ aplikacji** wybierz pozycję **Zarządzany sklep Google Play**.
7. Wybierz pozycję **Zarządzany sklep Google Play — zatwierdzanie aplikacji**, aby wyszukiwać zatwierdzonych aplikacji zarządzane ze sklepu Google Play.
8. Kliknij każdą aplikację, którą chcesz uwzględnić. Następnie:
9. Kliknij pozycję **Zatwierdź**, aby zatwierdzić aplikację zarządzaną ze sklepu Google Play, a następnie kliknij pozycję **Zatwierdź**, aby zaakceptować uprawnienia aplikacji. 
10. Kliknij przycisk **OK**, aby uwzględnić aplikacje.
11. Kliknij przycisk **Dodaj** w okienku **dodawania aplikacji**, aby przeprowadzić synchronizację z usługą zarządzanego sklepu Google Play.

## <a name="synchronize-a-managed-google-play-app-with-intune-alternative"></a>Synchronizowanie aplikacji z zarządzanego sklepu Google Play przy użyciu usługi Intune (alternatywa)
Jeśli wolisz zsynchronizować aplikację z zarządzanego sklepu Google Play, zamiast dodawać ją bezpośrednio za pomocą usługi Intune, wykonaj poniższe kroki.

> [!IMPORTANT]
> Informacje podane poniżej przedstawiają alternatywną metodę dodawania aplikacji z zarządzanego sklepu Google Play za pomocą usługi Intune zgodnie z powyższym opisem.

### <a name="synchronize-an-app-from-the-managed-google-play-store"></a>Synchronizowanie aplikacji z zarządzanego sklepu Google Play

1. Przejdź do [zarządzanego sklepu Google Play](https://play.google.com/work). Zaloguj się za pomocą tego samego konta, którego użyto do skonfigurowania połączenia między usługą Intune i rozwiązaniem Android enterprise.
2. Wyszukaj w sklepie i wybierz aplikację, którą chcesz przypisać za pomocą usługi Intune.
3. Na stronie z wyświetloną aplikacją wybierz pozycję **Zatwierdź**.  
    W poniższym przykładzie wybrano aplikację Microsoft Excel.

    ![Przycisk Zatwierdź w zarządzanym sklepie Google Play](media/approve.png)
    
   Zostanie otwarte okno aplikacji z monitem o nadanie uprawnień dla aplikacji do wykonywania poszczególnych operacji. 

4. Wybierz pozycję **Zatwierdź**, aby zaakceptować uprawnienia aplikacji i kontynuować.

    ![Przycisk Zatwierdź na potrzeby uprawnień aplikacji](media/approve-app-permissions.png)

5. Wybierz opcję obsługi nowych żądań dotyczących uprawnień aplikacji, a następnie wybierz pozycję **Zapisz**.

    ![Opcje obsługi nowych żądań dotyczących uprawnień aplikacji](media/approve-app-settings.png)

    Aplikacja została zatwierdzona i jest wyświetlana w konsoli administratora IT. Następnie możesz [zsynchronizować aplikację profilu służbowego systemu Android z usługą Intune](apps-add-android-for-work.md#sync-a-managed-google-play-app-with-intune). 

### <a name="sync-a-managed-google-play-app-with-intune"></a>Synchronizowanie aplikacji z zarządzanego sklepu Google Play z usługą Intune

Jeśli aplikacja ze sklepu została zatwierdzona, ale nie jest widoczna w węźle **Licencjonowane aplikacje** w obciążeniu **Aplikacje klienckie**, wymuś natychmiastową synchronizację w następujący sposób:

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Aplikacje klienckie**.
4. W okienku obciążenia **Aplikacje klienckie** w obszarze **Instalacja** wybierz pozycję **Zarządzany sklep Google Play**.
5. W okienku **Zarządzany sklep Google Play** wybierz pozycję **Odśwież**.  
    Strona aktualizuje godzinę i stan ostatniej synchronizacji.
6. W okienku obciążenia **Aplikacje klienckie** wybierz pozycję **Aplikacje**.  
    Zostanie wyświetlona nowo udostępniona aplikacja z zarządzanego sklepu Google Play.

## <a name="assigning-the-managed-google-play-app"></a>Przypisywanie aplikacji z zarządzanego sklepu Google Play

Gdy aplikacja zostanie wyświetlona w węźle **Licencje aplikacji** w okienku obciążenia **Aplikacje klienckie**, możesz [przypisać ją w taki sam sposób, jak dowolną inną aplikację](/intune-azure/manage-apps/deploy-apps), przypisując aplikację do grup użytkowników.

Po przypisaniu aplikacja jest instalowana na urządzeniach docelowych. Użytkownik urządzenia nie będzie monitowany o zatwierdzenie instalacji.

## <a name="manage-android-enterprise-app-permissions"></a>Zarządzanie uprawnieniami aplikacji w rozwiązaniu Android enterprise
Rozwiązanie Android enterprise wymaga zatwierdzenia aplikacji w konsoli internetowej zarządzanego sklepu Google Play przed ich zsynchronizowaniem z usługą Intune i przypisaniem do użytkowników. Ponieważ rozwiązanie Android enterprise umożliwia automatyczne i dyskretne wypychanie aplikacji na urządzenia użytkowników, należy zaakceptować uprawnienia aplikacji w imieniu wszystkich użytkowników. Podczas instalacji użytkownicy nie widzą żadnych uprawnień aplikacji, dlatego istotne jest, aby zrozumieć sposób działania uprawnień.

Jeśli deweloper aplikacji zaktualizuje uprawnienia wraz z nową wersją aplikacji, uprawnienia nie zostaną automatycznie zaakceptowane, nawet jeśli poprzednie uprawnienia zostały zatwierdzone. Użytkownicy urządzeń z poprzednią wersją aplikacji nadal mogą z niej korzystać. Aplikacja nie zostanie jednak uaktualniona do momentu zatwierdzenia nowych uprawnień. Na urządzeniach, na których aplikacja nie jest jeszcze zainstalowana, nie można jej zainstalować do czasu zatwierdzenia nowych uprawnień.

### <a name="update-app-permissions"></a>Aktualizowanie uprawnień aplikacji

Należy okresowo odwiedzać zarządzaną konsolę Google Play w celu upewnienia się, czy aplikacja nie wymaga nowych uprawnień. Sklep Google Play można skonfigurować tak, aby w sytuacji, gdy dla zatwierdzonej aplikacji wymagane będą nowe uprawnienia, była wysyłana wiadomość e-mail na określone adresy. Jeśli po przypisaniu aplikacji okaże się, że nie zainstalowano jej na urządzeniach, sprawdź, czy aplikacja nie wymaga nowych uprawnień, wykonując następujące kroki:

1. Przejdź do sklepu [Google Play](https://play.google.com/work).
2. Zaloguj się przy użyciu konta Google używanego do publikowania i zatwierdzania aplikacji.
3. Wybierz kartę **Aktualizacje** i sprawdź, czy którekolwiek aplikacje wymagają aktualizacji.  
    Wszystkie wyświetlone aplikacje wymagają nowych uprawnień i nie zostaną przypisane do czasu ich zastosowania.

Można także skonfigurować sklep Google Play w taki sposób, aby automatycznie ponownie zatwierdzał uprawnienia poszczególnych aplikacji. 

## <a name="working-with-a-line-of-business-app-from-the-managed-google-play-store"></a>Praca z aplikacją biznesową z zarządzanego sklepu Google Play

1. Zaloguj się do [konsoli programisty Google Play](https://play.google.com/apps/publish) za pomocą tego samego konta, którego użyto do skonfigurowania połączenia między usługą Intune i rozwiązaniem Android enterprise.  
    Jeśli logujesz się po raz pierwszy, musisz się zarejestrować i zapłacić opłatę, aby zostać członkiem programu Google Developer.
2. W konsoli wybierz pozycję **Dodaj nową aplikację**.
3. Informacje o aplikacji możesz przekazać i udostępnić w ten sam sposób, jak w przypadku publikowania dowolnych aplikacji w sklepie Google Play. Musisz jednak wybrać pozycję **Udostępnij tę aplikację tylko dla mojej organizacji (<*nazwa organizacji*>)**.

    ![Udostępnianie aplikacji tylko dla danej organizacji](media/restrict.png)

    Ta operacja sprawia, że aplikacja będzie dostępna tylko dla Twojej organizacji. Nie będzie ona dostępna w publicznym sklepie Google Play.

    Aby uzyskać więcej informacji na temat przekazywania i publikowania aplikacji systemu Android, zobacz [Konsola programisty Google — pomoc](https://support.google.com/googleplay/android-developer/answer/113469).
4. Po opublikowaniu aplikacji zaloguj się do [zarządzanego sklepu Google Play](https://play.google.com/work) za pomocą tego samego konta, którego użyto do skonfigurowania połączenia między usługą Intune i rozwiązaniem Android enterprise.
5. W węźle **Aplikacje** w sklepie sprawdź, czy opublikowana aplikacja jest widoczna.  
    Ta aplikacja została automatycznie zatwierdzona do synchronizacji z usługą Intune.

## <a name="delete-managed-google-play-apps"></a>Usuwanie aplikacji z zarządzanego sklepu Google Play 
W razie potrzeby możesz usuwać aplikacje z zarządzanego sklepu Google Play z poziomu usługi Microsoft Intune. Aby usunąć aplikację z zarządzanego sklepu Google Play, otwórz usługę Microsoft Intune w witrynie Azure Portal i wybierz kolejno pozycje **Aplikacje klienckie** > **Aplikacje**. Na liście aplikacji wybierz wielokropek (...) po prawej stronie aplikacji z zarządzanego sklepu Google Play, a następnie wybierz pozycję **Usuń** z wyświetlonej listy. Po usunięciu aplikacji zarządzanej ze sklepu Google Play z listy aplikacji ta aplikacja zarządzana stanie się automatycznie aplikacją niezatwierdzoną.

## <a name="next-steps"></a>Następne kroki

- [Przypisywanie aplikacji do grup](apps-deploy.md) 

