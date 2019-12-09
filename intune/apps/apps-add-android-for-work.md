---
title: Przypisywanie zarządzanych aplikacji ze sklepu Google Play do urządzeń z systemem Android Enterprise
titleSuffix: Microsoft Intune
description: Dowiedz się, jak synchronizować aplikacje z zarządzanego sklepu Google Play i przypisywać je do urządzeń z systemem Android Enterprise.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0e57aa0546950a12cdb2d4a2e3c8ed721bfc24b8
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/27/2019
ms.locfileid: "74564154"
---
# <a name="add-managed-google-play-apps-to-android-enterprise-devices-with-intune"></a>Dodawanie zarządzanych aplikacji ze sklepu Google Play do urządzeń z systemem Android Enterprise z usługą Intune

Zarządzany sklep Google Play to sklep firmy Google z aplikacjami klasy korporacyjnej oraz jedyne źródło aplikacji do urządzeń z systemem Android Enterprise. W usłudze Intune można organizować wdrażanie aplikacji za pomocą zarządzanego sklepu Google Play w przypadku dowolnego scenariusza systemu Android Enterprise (w tym profilu służbowego, dedykowanych oraz w pełni zarządzanych rejestracji). Sposób dodawania aplikacji z zarządzanego sklepu Google Play do usługi Intune różni się od sposobu dodawania aplikacji do systemu Android nieprzeznaczonego dla firm. Aplikacje ze sklepu, biznesowe oraz sieciowe, są zatwierdzane w sklepie Google Play lub do niego dodawane, a następnie synchronizowane z usługą Intune, aby pojawiły się na liście aplikacji klienckich. Gdy aplikacje pojawią się na liście aplikacji klienckich, można zarządzać ich przypisaniami z zarządzanego sklepu Google Play, tak jak w przypadku każdej innej aplikacji.

Aby ułatwić Ci konfigurowanie i używanie funkcji zarządzania systemem Android Enterprise, po połączeniu dzierżawy usługi Intune z zarządzanym sklepem Google Play usługa Intune automatycznie doda do konsoli administracyjnej cztery popularne aplikacje powiązane z systemem Android Enterprise. Są to:

- **[Microsoft Intune](https://play.google.com/store/apps/details?id=com.microsoft.intune)**  — używana w scenariuszach w pełni zarządzanych za pomocą Android Enterprise. Ta aplikacja jest automatycznie instalowana na w pełni zarządzanych urządzeniach podczas procesu ich rejestracji.
- **[Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)** — pomaga zalogować się do kont w przypadku używania weryfikacji dwuskładnikowej. Ta aplikacja jest automatycznie instalowana na w pełni zarządzanych urządzeniach podczas procesu ich rejestracji.
- **[Intune — Portal firmy](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)**  — używana w przypadku scenariuszy obejmujących zasady ochrony aplikacji i profil służbowy Android Enterprise.
- **[Zarządzany ekran główny](https://play.google.com/store/apps/details?id=com.microsoft.launcher.enterprise)** — aplikacja używana w scenariuszach z użyciem systemu Android Enterprise dla urządzeń dedykowanych w trybie kiosku z wieloma aplikacjami. Administratorzy IT powinni utworzyć przypisanie w celu zainstalowania tej aplikacji na dedykowanych urządzeniach, które będą używane w kioskach z wieloma aplikacjami.

>[!NOTE]
>Gdy użytkownik końcowy zarejestruje swoje w pełni zarządzane urządzenie z systemem Android Enterprise, nastąpi automatyczna instalacja aplikacji Intune — Portal firmy, a jej ikona pojawi się na ekranie. Jeśli użytkownik końcowy podejmie próbę uruchomienia aplikacji Intune — Portal firmy, zostanie przekierowany do aplikacji Microsoft Intune, a ikona aplikacji Portal firmy zostanie ukryta.

## <a name="before-you-start"></a>Przed rozpoczęciem
- Upewnij się, że dzierżawa usługi Intune ma połączenie z zarządzanym sklepem Google Play.  Aby uzyskać więcej informacji, zobacz [Łączenie konta usługi Intune z kontem zarządzanego sklepu Google Play](../enrollment/connect-intune-android-enterprise.md).
- Jeśli zamierzasz zarejestrować urządzenia z profilem służbowym, upewnij się, że profile służbowe usługi Intune i systemu Android skonfigurowano tak, aby współpracowały ze sobą w ramach obciążenia **Rejestrowanie urządzeń** portalu Azure. Aby uzyskać więcej informacji, zobacz [Rejestrowanie urządzeń z systemem Android](../enrollment/android-work-profile-enroll.md).

>[!NOTE]
>Jeśli pracujesz, korzystając z usługi Microsoft Intune, firma Microsoft zaleca używanie przeglądarki Microsoft Edge lub Google Chrome.

## <a name="managed-google-play-app-types"></a>Typy aplikacji w zarządzanym sklepie Google Play
W zarządzanym sklepie Google Play są dostępne trzy typy aplikacji:

- **Aplikacja zarządzanego sklepu Google Play** — aplikacje publiczne, które są ogólnie dostępne w sklepie Play. Tymi aplikacjami możesz zarządzać w usłudze Intune. Wystarczy, że wyszukasz te, którymi chcesz zarządzać, zatwierdzisz je, a następnie zsynchronizujesz z usługą Intune.
- **Aplikacja prywatna z zarządzanego sklepu Google Play** — są to aplikacje biznesowe publikowane w zarządzanym sklepie Google Play przez administratorów usługi Intune.  Te aplikacje są prywatne i dostępne tylko dla dzierżawy usługi Intune. W ten sposób można zarządzać aplikacjami biznesowymi oraz wdrażać je za pomocą zarządzanego sklepu Google Play i systemu Android Enterprise.
- **Link sieci Web zarządzanego sklepu Google Play** — są to linki sieci Web z ikonami zdefiniowanymi przez administratora IT, które można wdrożyć na urządzeniach z systemem Android Enterprise. Są one wyświetlane na liście aplikacji urządzenia, podobnie jak zwykłe aplikacje.

## <a name="managed-google-play-store-apps"></a>Aplikacje zarządzanego sklepu Google Play
Istnieją dwie metody przeglądania i zatwierdzania aplikacji zarządzanego sklepu Google Play przy użyciu usługi Intune:

1. Bezpośrednio w konsoli usługi Intune — przeglądaj i zatwierdzaj aplikacje ze sklepu w widoku w ramach usługi Intune. Możesz pracować bezpośrednio w konsoli usługi Intune, nie musisz ponownie uwierzytelniać swojej tożsamości za pomocą innego konta.
1. W zarządzanej konsoli Google Play — możesz opcjonalnie otworzyć zarządzaną konsolę Google Play i tam zatwierdzić aplikacje. Aby uzyskać więcej informacji, zobacz [Synchronizowanie aplikacji z zarządzanego sklepu Google Play z usługą Intune](apps-add-android-for-work.md#sync-a-managed-google-play-app-with-intune).  Wymaga to oddzielnego logowania przy użyciu konta używanego do łączenia dzierżawy usługi Intune z zarządzanym sklepem Google Play.


### <a name="add-a-managed-google-play-store-app-directly-in-the-intune-console"></a>Dodawanie aplikacji zarządzanego sklepu Google Play bezpośrednio w konsoli usługi Intune

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz kolejno pozycje **Aplikacje** > **Wszystkie aplikacje** > **Dodaj**.
3. W polu listy rozwijanej **Typ aplikacji** wybierz pozycję **Zarządzany sklep Google Play**.
4. Wybierz pozycję **Zarządzany sklep Google Play — otwórz**, aby otworzyć wykaz zawartości zarządzanego sklepu Google Play.
5. Wybierz pozycję **Szukaj w sklepie Play** w katalogu Google Play.
6. Użyj pola wyszukiwania, aby wyszukać aplikacje, którymi chcesz zarządzać.
7. Kliknij pozycję **Zatwierdź**, aby zatwierdzić aplikację w zarządzanym sklepie Google Play, a następnie kliknij pozycję **Zatwierdź**, aby zaakceptować uprawnienia aplikacji.
8. Wybierz pozycję **Utrzymuj zatwierdzenie, gdy aplikacja żąda nowych uprawnień** w oknie Ustawienia zatwierdzania, a następnie kliknij przycisk **Zapisz**. Jeśli nie wybierzesz tej opcji, będzie trzeba ręcznie zatwierdzać wszystkie nowe uprawnienia, gdy deweloper aplikacji opublikuje aktualizację. Spowoduje to zatrzymanie instalacji i aktualizacji do momentu zatwierdzenia uprawnień. Z tego powodu zalecamy wybranie opcji automatycznego zatwierdzania nowych uprawnień. 
9. Kliknij przycisk **OK**, aby uwzględnić zatwierdzone aplikacje.
10. Kliknij pozycję **Synchronizuj** w okienku **dodawania aplikacji**, aby przeprowadzić synchronizację z usługą zarządzanego sklepu Google Play.

### <a name="add-a-managed-google-play-store-app-in-the-managed-google-play-console-alternative"></a>Dodawanie aplikacji z zarządzanego sklepu Google Play za pośrednictwem konsoli zarządzanego sklepu Google Play (metoda alternatywna)
Jeśli wolisz zsynchronizować aplikację z zarządzanego sklepu Google Play, zamiast dodawać ją bezpośrednio za pomocą usługi Intune, wykonaj poniższe kroki.

> [!IMPORTANT]
> Informacje podane poniżej przedstawiają alternatywną metodę dodawania aplikacji z zarządzanego sklepu Google Play za pomocą usługi Intune zgodnie z powyższym opisem.

1. Przejdź do [zarządzanego sklepu Google Play](https://play.google.com/work). Zaloguj się za pomocą tego samego konta, którego użyto do skonfigurowania połączenia między usługą Intune a systemem Android Enterprise.
2. Wyszukaj w sklepie i wybierz aplikację, którą chcesz przypisać za pomocą usługi Intune.
3. Na stronie z wyświetloną aplikacją wybierz pozycję **Zatwierdź**.  
    W poniższym przykładzie wybrano aplikację Microsoft Excel.

    ![Przycisk Zatwierdź w zarządzanym sklepie Google Play](./media/apps-add-android-for-work/approve.png)

   Zostanie otwarte okno aplikacji z monitem o nadanie uprawnień dla aplikacji do wykonywania poszczególnych operacji.

4. Wybierz pozycję **Zatwierdź**, aby zaakceptować uprawnienia aplikacji i kontynuować.

    ![Przycisk Zatwierdź na potrzeby uprawnień aplikacji](./media/apps-add-android-for-work/approve-app-permissions.png)

5. Wybierz opcję obsługi nowych żądań dotyczących uprawnień aplikacji, a następnie wybierz pozycję **Zapisz**.

    ![Opcje obsługi nowych żądań dotyczących uprawnień aplikacji](./media/apps-add-android-for-work/approve-app-settings.png)

    Aplikacja została zatwierdzona i jest wyświetlana w konsoli administratora IT. Następnie możesz [zsynchronizować aplikację profilu służbowego systemu Android z usługą Intune](apps-add-android-for-work.md#sync-a-managed-google-play-app-with-intune).

## <a name="managed-google-play-private-lob-apps"></a>Prywatne aplikacje biznesowe z zarządzanego sklepu Google Play

Istnieją dwa sposoby dodawania aplikacji biznesowych do zarządzanego sklepu Google Play:

1. Bezpośrednio w konsoli usługi Intune — można dodawać aplikacje biznesowe, przesyłając wyłącznie APK oraz nazwy aplikacji bezpośrednio w usłudze Intune. Ta metoda nie wymaga posiadania konta programisty Google ani wnoszenia opłaty za rejestrację jako programista Google.  Ta metoda jest prostsza, składa się z mniejszej liczby kroków oraz sprawia, że aplikacje LOB są udostępniane do zarządzania w ciągu zaledwie 10 minut.
1. W konsoli programisty Google Play — jeśli masz konto programisty Google lub chcesz skonfigurować zaawansowane funkcje dystrybucji, które są dostępne wyłącznie w konsoli programisty Google Play (na przykład dodawanie dodatkowych zrzutów ekranu z aplikacji), możesz użyć [konsoli programisty Google Play](https://play.google.com/apps/publish). 

### <a name="managed-google-play-private-lob-app-publishing-directly-in-the-intune-console"></a>Publikowanie aplikacji prywatnych (LOB) z zarządzanego sklepu Google Play bezpośrednio w konsoli usługi Intune

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz kolejno pozycje **Aplikacje** > **Wszystkie aplikacje** > **Dodaj**.
3. W polu listy rozwijanej **Typ aplikacji** wybierz pozycję **Zarządzany sklep Google Play**.
4. Wybierz pozycję **Zarządzany sklep Google Play — otwórz**, aby otworzyć wykaz zawartości zarządzanego sklepu Google Play.
5. Wybierz pozycję **Aplikacje prywatne** w katalogu Google Play.
6. Kliknij przycisk **„+”** , aby dodać nową aplikację.
7. Prześlij nazwę aplikacji i pakiet APK.
8. Kliknij przycisk **Utwórz**.
9. Po zakończeniu dodawania aplikacji zamknij okienko Zarządzany sklep Google Play
10. Kliknij pozycję **Synchronizuj** w okienku **dodawania aplikacji**, aby przeprowadzić synchronizację z usługą zarządzanego sklepu Google Play. Może minąć kilka minut, zanim aplikacje prywatne będą dostępne do synchronizacji. Jeśli aplikacja nie pojawi się podczas pierwszej synchronizacji, odczekaj kilka minut i zainicjuj nową synchronizację.

Więcej informacji na temat aplikacji prywatnych z zarządzanego sklepu Google Play, łącznie z często zadawanymi pytaniami, znajduje się w artykule pomocy technicznej firmy Google: https://support.google.com/googleplay/work/answer/9146439

>[!NOTE]
>Prywatne aplikacje dodane przy użyciu tej metody nigdy nie mogą być udostępniane publicznie. Tej opcji publikowania używaj tylko wtedy, gdy masz pewność, że aplikacja pozostanie prywatna i dostępna tylko dla organizacji.
  

### <a name="managed-google-play-private-lob-app-publishing-using-the-google-developer-console"></a>Publikowanie aplikacji prywatnych (LOB) z zarządzanego sklepu Google Play za pomocą konsoli programisty Google

1. Zaloguj się do [konsoli programisty Google Play](https://play.google.com/apps/publish) za pomocą tego samego konta, którego użyto do skonfigurowania połączenia między usługą Intune a systemem Android Enterprise.  
    Jeśli logujesz się po raz pierwszy, musisz się zarejestrować i zapłacić opłatę, aby zostać członkiem programu Google Developer.
2. W konsoli wybierz pozycję **Dodaj nową aplikację**.
3. Informacje o aplikacji możesz przekazać i udostępnić w ten sam sposób, jak w przypadku publikowania dowolnych aplikacji w sklepie Google Play. Musisz jednak wybrać pozycję **Udostępnij tę aplikację tylko dla mojej organizacji (<*nazwa organizacji*>)** .

    ![Udostępnianie aplikacji tylko dla danej organizacji](./media/apps-add-android-for-work/restrict.png)

    Ta operacja sprawia, że aplikacja będzie dostępna tylko dla Twojej organizacji. Nie będzie ona dostępna w publicznym sklepie Google Play.

    Aby uzyskać więcej informacji na temat przekazywania i publikowania aplikacji systemu Android, zobacz [Konsola programisty Google — pomoc](https://support.google.com/googleplay/android-developer/answer/113469).
4. Po opublikowaniu aplikacji zaloguj się do [zarządzanego sklepu Google Play](https://play.google.com/work) za pomocą tego samego konta, którego użyto do skonfigurowania połączenia między usługą Intune a systemem Android Enterprise.
5. W węźle **Aplikacje** w sklepie sprawdź, czy opublikowana aplikacja jest widoczna.  
    Ta aplikacja została automatycznie zatwierdzona do synchronizacji z usługą Intune.

## <a name="managed-google-play-web-links"></a>Linki sieci Web z zarządzanego sklepu Google Play

Linki sieci Web z zarządzanego sklepu Google Play można instalować i zarządzać nimi tak, jak innym aplikacjami w systemie Android. Po zainstalowaniu na urządzeniu pojawią się na liście aplikacji użytkownika wraz z innymi zainstalowanymi aplikacjami. Ich naciśnięcie spowoduje uruchomienie przeglądarki urządzenia.

Linki sieci Web będą otwierane przy użyciu przeglądarki Microsoft Edge lub dowolnej innej wdrożonej przeglądarki. Pamiętaj o wdrożeniu na urządzeniach co najmniej jednej aplikacji przeglądarki, aby można było poprawnie otwierać na nich linki sieci Web. Jednak wszystkie opcje menu **Wyświetlanie** dostępne dla linków sieci Web (pełny ekran, autonomiczny i minimalny interfejs użytkownika) będą działały wyłącznie w przeglądarce Chrome. 

> [!IMPORTANT]
> W momencie publikowania tego dokumentu istnieje znana usterka Google, która uniemożliwia otwieranie linków sieci Web na urządzeniach z przeglądarkami innymi niż Chrome. Firma Google zobowiązała się ją naprawić.  Ta informacja zostanie usunięta, jeśli firma Microsoft otrzyma od firmy Google potwierdzenie wydania poprawki.

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz kolejno pozycje **Aplikacje** > **Wszystkie aplikacje** > **Dodaj**.
3. W polu listy rozwijanej **Typ aplikacji** wybierz pozycję **Zarządzany sklep Google Play**.
4. Wybierz pozycję **Zarządzany sklep Google Play — otwórz**, aby otworzyć wykaz zawartości zarządzanego sklepu Google Play.
5. Wybierz pozycję **Aplikacje internetowe** w katalogu Google Play.
6. Kliknij przycisk **„+”** , aby dodać nową aplikację.
7. Wprowadź wymagane informacje, a następnie kliknij opcję **Utwórz**.
8. Po zakończeniu dodawania aplikacji zamknij okienko Zarządzany sklep Google Play
9. Kliknij pozycję **Synchronizuj** w okienku **dodawania aplikacji**, aby przeprowadzić synchronizację z usługą zarządzanego sklepu Google Play. Może minąć kilka minut, zanim aplikacje prywatne będą dostępne do synchronizacji. Jeśli aplikacja nie pojawi się podczas pierwszej synchronizacji, odczekaj kilka minut i zainicjuj nową synchronizację.

## <a name="sync-a-managed-google-play-app-with-intune"></a>Synchronizowanie aplikacji z zarządzanego sklepu Google Play z usługą Intune

Jeśli aplikacja ze sklepu została zatwierdzona, ale nie jest widoczna w obciążeniu **Aplikacje**, wymuś natychmiastową synchronizację w następujący sposób:

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Wybierz kolejno pozycje **Aplikacje** > **Administracja dzierżawą** > **Łączniki i tokeny** > **Zarządzany sklep Google Play**.
5. W okienku **Zarządzany sklep Google Play** wybierz pozycję **Odśwież**.  
    Strona aktualizuje godzinę i stan ostatniej synchronizacji.
6. W centrum administracyjnym programu Microsoft Endpoint Manager wybierz kolejno pozycje **Aplikacje** > **Wszystkie aplikacje**.  
    Zostanie wyświetlona nowo udostępniona aplikacja z zarządzanego sklepu Google Play.

## <a name="assigning-a-managed-google-play-app-to-android-enterprise-work-profile-devices"></a>Przypisywanie aplikacji z zarządzanego sklepu Google Play do urządzeń z profilem służbowym systemu Android Enterprise

Gdy aplikacja zostanie wyświetlona w węźle **Licencje aplikacji** w okienku obciążenia **Aplikacje**, możesz [ją przypisać w taki sam sposób, jak dowolną inną aplikację](/intune-azure/manage-apps/deploy-apps), przypisując aplikację do grup użytkowników.

Po przypisaniu aplikacja zostanie zainstalowana (lub udostępniona do zainstalowania) na wybranych urządzeniach użytkowników. Użytkownik urządzenia nie będzie monitowany o zatwierdzenie instalacji. Aby uzyskać więcej informacji na temat urządzeń z profilem służbowym systemu Android Enterprise, zobacz [Konfigurowanie rejestracji urządzeń z profilem służbowym systemu Android Enterprise](../enrollment/android-work-profile-enroll.md). 

> [!NOTE] 
> Użytkownik końcowy będzie widział w zarządzanym sklepie Google Play wyłącznie przypisane aplikacje. Jest to więc kluczowy krok, jaki musi wykonać administrator podczas konfigurowania aplikacji za pomocą zarządzanego sklepu Google Play.

## <a name="assigning-a-managed-google-play-app-to-android-enterprise-fully-managed-devices"></a>Przypisywanie aplikacji z zarządzanego sklepu Google Play do w pełni zarządzanych urządzeń z systemem Android Enterprise

[W pełni zarządzane urządzenia z systemem Android Enterprise](../enrollment/android-fully-managed-enroll.md) to urządzenia należące do firmy skojarzone z jednym użytkownikiem i wykorzystywane wyłącznie do pracy, a nie do celów osobistych. Użytkownicy korzystający z w pełni zarządzanych urządzeń mogą na nich pobierać dostępne aplikacje firmowe za pomocą aplikacji zarządzanego sklepu Google Play.

Domyślnie w pełni zarządzane urządzenie z systemem Android Enterprise nie zezwala pracownikom na instalowanie jakichkolwiek aplikacji, które nie są zatwierdzone przez organizację. Ponadto zasady określają, że pracownicy nie mogą usuwać żadnych zainstalowanych aplikacji. Jeśli chcesz dać użytkownikom dostęp do pełnego sklepu Google Play ze wszystkimi aplikacjami, a nie tylko do zatwierdzonych aplikacji w zarządzanym sklepie Google Play, wybierz w ustawieniu **Zezwalaj na dostęp do wszystkich aplikacji w sklepie Google Play** opcję **Zezwalaj**. Dzięki temu ustawieniu użytkownik będzie miał za pośrednictwem swojego konta firmowego dostęp do wszystkich aplikacji w sklepie Google Play. Opcje kupowania aplikacji będą jednak ograniczone. Ograniczenie zakupów można usunąć, dając użytkownikom możliwość dodawania do urządzenia nowych kont. Dzięki temu użytkownicy końcowi będą mogli kupować aplikacje ze sklepu Google Play przy użyciu swoich kont osobistych, a także dokonywać zakupów w aplikacjach. Aby uzyskać więcej informacji, zobacz [Ustawienia urządzeń z systemem Android Enterprise w celu zezwolenia na funkcje lub ich ograniczenia przy użyciu usługi Intune](../configuration/device-restrictions-android-for-work.md). 

> [!NOTE]
> W procesie dołączania aplikacje Microsoft Intune i Microsoft Authenticator zostaną zainstalowane jako wymagane na wszystkich w pełni zarządzanych urządzeniach. Automatyczna instalacja tych aplikacji zapewnia obsługę dostępu warunkowego. Ponadto użytkownicy aplikacji Microsoft Intune mogą przeglądać i rozwiązywać problemy ze zgodnością. 

## <a name="manage-android-enterprise-app-permissions"></a>Zarządzanie uprawnieniami aplikacji w systemie Android Enterprise
System Android Enterprise wymaga zatwierdzenia aplikacji w konsoli internetowej zarządzanego sklepu Google Play przed ich zsynchronizowaniem z usługą Intune i przypisaniem do użytkowników. Ponieważ system Android Enterprise umożliwia automatyczne i dyskretne wypychanie aplikacji na urządzenia użytkowników, należy zaakceptować uprawnienia aplikacji w imieniu wszystkich użytkowników. Podczas instalacji użytkownicy nie widzą żadnych uprawnień aplikacji, dlatego istotne jest, aby zrozumieć sposób działania uprawnień.

Jeśli deweloper aplikacji zaktualizuje uprawnienia wraz z nową wersją aplikacji, uprawnienia nie zostaną automatycznie zaakceptowane, nawet jeśli poprzednie uprawnienia zostały zatwierdzone. Użytkownicy urządzeń z poprzednią wersją aplikacji nadal mogą z niej korzystać. Aplikacja nie zostanie jednak uaktualniona do momentu zatwierdzenia nowych uprawnień. Na urządzeniach, na których aplikacja nie jest jeszcze zainstalowana, nie można jej zainstalować do czasu zatwierdzenia nowych uprawnień. 

### <a name="update-app-permissions"></a>Aktualizowanie uprawnień aplikacji

Należy okresowo odwiedzać zarządzaną konsolę Google Play w celu upewnienia się, czy aplikacja nie wymaga nowych uprawnień. Sklep Google Play można skonfigurować tak, aby w sytuacji, gdy dla zatwierdzonej aplikacji wymagane będą nowe uprawnienia, była wysyłana wiadomość e-mail na określone adresy. Jeśli po przypisaniu aplikacji okaże się, że nie zainstalowano jej na urządzeniach, sprawdź, czy aplikacja nie wymaga nowych uprawnień, wykonując następujące kroki:

1. Przejdź do sklepu [Google Play](https://play.google.com/work).
2. Zaloguj się przy użyciu konta Google używanego do publikowania i zatwierdzania aplikacji.
3. Wybierz kartę **Aktualizacje** i sprawdź, czy którekolwiek aplikacje wymagają aktualizacji.  
    Wszystkie wyświetlone aplikacje wymagają nowych uprawnień i nie zostaną przypisane do czasu ich zastosowania.

Można także skonfigurować sklep Google Play w taki sposób, aby automatycznie ponownie zatwierdzał uprawnienia poszczególnych aplikacji.

## <a name="additional-managed-google-play-app-reporting-for-android-enterprise-work-profile-devices"></a>Dodatkowe raportowanie aplikacji z zarządzanego sklepu Google Play dla urządzeń z profilem służbowym rozwiązania Android Enterprise

W przypadku aplikacji zarządzanych ze sklepu Google Play wdrożonych na urządzeniach z profilem służbowym systemu Android Enterprise można wyświetlić stan i numer wersji aplikacji zainstalowanej na urządzeniu za pomocą usługi Intune. 

## <a name="delete-managed-google-play-apps"></a>Usuwanie aplikacji z zarządzanego sklepu Google Play
W razie potrzeby możesz usuwać aplikacje z zarządzanego sklepu Google Play z poziomu usługi Microsoft Intune. Aby usunąć aplikację z zarządzanego sklepu Google Play, otwórz usługę Microsoft Intune w witrynie Azure Portal i wybierz kolejno pozycje **Aplikacje** > **Wszystkie aplikacje**. Na liście aplikacji wybierz wielokropek (...) po prawej stronie aplikacji z zarządzanego sklepu Google Play, a następnie wybierz pozycję **Usuń** z wyświetlonej listy. Po usunięciu aplikacji zarządzanej ze sklepu Google Play z listy aplikacji ta aplikacja zarządzana stanie się automatycznie aplikacją niezatwierdzoną.

## <a name="android-enterprise-system-apps"></a>Aplikacje systemu Android Enterprise

Aplikację systemu Android Enterprise można włączyć na [dedykowanych urządzeniach z systemem Android Enterprise](../enrollment/android-kiosk-enroll.md) lub [w pełni zarządzanych urządzeniach](../enrollment/android-fully-managed-enroll.md). Aby uzyskać więcej informacji na temat dodawania aplikacji systemu Android Enterprise, patrz [Dodawanie aplikacji systemu Android Enterprise do usługi Microsoft Intune](apps-ae-system.md).

## <a name="next-steps"></a>Następne kroki

- [Przypisywanie aplikacji do grup](apps-deploy.md)
