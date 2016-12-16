---
title: Poprzednie wersje | Microsoft Intune
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/05/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4dab832da4490c3df045d2c627b231028c92b25
ms.openlocfilehash: 3de5e57589a24600301e54a3b60eecb5321ff838


---

# <a name="previous-intune-releases"></a>Poprzednie wersje usługi Intune

Ta strona stanowi listę ogłoszeń opublikowanych w artykule [Co nowego w usłudze Microsoft Intune](whats-new-in-microsoft-intune.md).

[!INCLUDE[wit_nextref](../includes/whats-new-last-six-months.md)]

## <a name="may-2016"></a>Maj 2016
Wszystkie te funkcje są również obsługiwane dla wdrożeń hybrydowych (program Configuration Manager z usługą Intune). Aby uzyskać więcej informacji na temat nowych funkcji hybrydowych, odwiedź stronę [Co nowego w funkcjach hybrydowych](https://technet.microsoft.com/en-us/library/mt718155.aspx).

### <a name="documentation"></a>Dokumentacja
Zapraszamy do skorzystania z wersji zapoznawczej witryny [docs.microsoft.com](https://docs.microsoft.com/en-us/intune)!
Jest to zupełnie nowa, nowoczesna platforma zawartości zaprojektowana z myślą o tym, aby ułatwić naszym klientom zrozumienie usługi Intune oraz korzystanie z niej.
Aby przeczytać o wszystkich nowych funkcjach, zobacz [Wprowadzenie do witryny docs.microsoft.com](https://docs.microsoft.com/teamblog/introducing-docs-microsoft-com/)

### <a name="intune-service-health"></a>Kondycja usługi Intune
Informacje o kondycji usługi Intune zostały przeniesione do centralnej lokalizacji z innymi usługami firmy Microsoft. Teraz znajdziesz te informacje w [portalu zarządzania usługą Office 365](https://portal.office.com/Admin/Default.aspx) w obszarze **Kondycja usługi**.
Aby uzyskać więcej informacji, zobacz [ten wpis w blogu](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).

### <a name="app-management"></a>Zarządzanie aplikacjami
- **Zestaw SDK zarządzania aplikacjami mobilnymi: obsługa konfiguracji długości numeru PIN.** Będzie możliwe określenie długości numeru PIN dla aplikacji w ramach zarządzania aplikacjami mobilnymi, podobnie jak w przypadku numeru PIN urządzenia. Użytkownicy końcowi będą musieli zachować zgodność z określonymi nowymi ograniczeniami. Będzie wyświetlany nieco zmodyfikowany ekran numeru PIN, umożliwiający wprowadzanie dłuższych numerów. Aby uzyskać szczegółowe informacje, zobacz [Ustawienia zasad zarządzania aplikacjami mobilnymi dla systemu Android](/intune/deploy-use/android-mam-policy-settings) i [Ustawienia zasad zarządzania aplikacjami mobilnymi dla systemu iOS](/intune/deploy-use/ios-mam-policy-settings).

- **Aplikacja Skype dla firm dla systemów iOS i Android.** Aplikację Skype dla firm można teraz wskazać jako objętą [zarządzaniem aplikacjami mobilnymi bez stosowania zasad rejestracji](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune). Gdy użytkownicy zalogują się, zostaną zastosowane zasady zarządzania aplikacjami mobilnymi.

- **Nowe aplikacje dostępne do zarządzania przy użyciu zasad zarządzania aplikacjami mobilnymi.** Aplikacje Microsoft Word, Excel i PowerPoint dla systemu Android teraz mogą być skojarzone z zasadami zarządzania aplikacjami mobilnymi na urządzeniach, które nie są zarejestrowane w usłudze Intune. Pełna lista obsługiwanych aplikacji jest dostępna w galerii aplikacji mobilnych usługi Microsoft Intune na stronie [partnerów aplikacji usługi Microsoft Intune](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx).


### <a name="company-portal-updates"></a>Aktualizacje Portalu firmy

#### <a name="android-company-portal-app"></a>Aplikacja Portal firmy dla systemu Android
- **Wyskakujące powiadomienia dla użytkownika końcowego**: użytkownicy końcowi będą teraz otrzymywać wyskakujące powiadomienia z aplikacji Portal firmy dla systemu Android, gdy będą rejestrować lub usuwać swoje urządzenia w Portalu firmy.

- **Zmiany w kontach menedżerów rejestracji urządzeń w aplikacji Portal firmy dla systemu Android.** W celu poprawy wydajności i skalowania usługa Intune nie pokazuje już wszystkich urządzeń menedżerów rejestracji urządzeń (DEM) w okienku Moje urządzenia w aplikacji Portal firmy dla systemu Android. Wyświetlane jest tylko urządzenie lokalne, na którym uruchomiono aplikację, o ile zostało zarejestrowane przez aplikację Portal firmy. Użytkownik menedżera rejestracji urządzeń może wykonywać działania na urządzeniu lokalnym, ale zdalne zarządzanie innymi zarejestrowanymi urządzeniami można przeprowadzać tylko z konsoli administracyjnej usługi Intune.

#### <a name="company-portal-website"></a>Witryna sieci Web Portal firmy
- **Witryna sieci Web Portal firmy: transparent identyfikacji urządzenia będzie zapewniać więcej informacji użytkownikom końcowym.** Użytkownicy końcowi mogą teraz łatwiej identyfikować urządzenie, które wybrali, gdy korzystają z witryny sieci Web Portal firmy. W przypadku wybrania niewłaściwego urządzenia użytkownik będzie mógł wybrać poprawne urządzenie, naciskając link **Naciśnij tutaj** na transparencie na stronie głównej.

### <a name="service-deprecation"></a>Wycofywanie usług
- **Aplikacje Intune Viewer.** Wraz z wydaniem nowej aplikacji RMS sharing zostaną usunięte następujące aplikacje Intune Viewer, począwszy od sierpnia 2016 roku:
    - Intune AV Viewer
    - Intune PDF Viewer
    - Intune Image Viewer dla systemu Android ze sklepu Google Play

  Zalecamy, aby zamiast korzystania z aplikacji Intune Viewer używać nowej aplikacji do zarządzania prawami (RMS sharing) dla systemu Android, co pozwala na wdrożenie jednej aplikacji zamiast trzech osobnych aplikacji w celu bezpiecznego przeglądania plików firmy na urządzeniach z systemem Android. Dowiedz się więcej na temat aplikacji RMS sharing (za pomocą linku do dokumentacji).

- **Usunięcie określania grup niestandardowych jako obiektów docelowych reguł powiadomień.**
Reguły powiadomień usługi Intune definiują, do kogo będą wysyłane alerty e-mail z usługi Intune. Obecnie można konfigurować reguły powiadomień w celu wysyłania wiadomości e-mail do wszystkich użytkowników urządzeń należących do utworzonej grupy urządzeń usługi Intune. Około 1 czerwca 2016 roku określanie grup utworzonych przez użytkownika jako docelowych przestanie być obsługiwane.

    Obecnie w celu skierowania reguły powiadomień do grupy utworzonej z konsoli administracyjnej usługi Microsoft Intune można wykonać następujące czynności:

    W obszarze roboczym **Administracja** kliknij pozycję **Reguły powiadomień** > **Utwórz nową regułę**.

    W drugim kroku Kreatora tworzenia reguł powiadomień wybierz grupy urządzeń, których będzie dotyczyć dana reguła. Ten krok („Wybierz grupy urządzeń”) jest usuwany z konsoli usługi Intune.

    Wstępny plan dla tej zmiany jest następujący:
    - W czerwcu 2016 roku nowi dzierżawcy nie będą widzieć drugiego kroku Kreatora tworzenia reguł powiadomień. Nie dotyczy to jednak istniejących dzierżawców.
    - W okolicach sierpnia 2016 roku niektórzy istniejący dzierżawcy nie będą widzieć kroku „Wybierz grupy urządzeń” w kreatorze.
    - Przewidujemy, że krok „Wybierz grupy urządzeń” w kreatorze przestanie być widoczny dla wszystkich dzierżawców w okolicach października 2016 roku.


- **Zmiany w obsłudze aplikacji Portal firmy dla systemu iOS**. W najbliższych miesiącach odbędzie się aktualizacja aplikacji Portal firmy usługi Microsoft Intune dla systemu iOS, która obejmie tylko urządzenia z systemem iOS 8.0 lub nowszym. Użytkownicy nie będą mogli rejestrować nowych urządzeń z wersjami starszymi niż iOS 8.0. Zarejestrowane urządzenia z wersjami starszymi niż iOS 8.0 nadal będą zarządzane i przez ograniczony czas będzie można nadal korzystać z aplikacji Portal firmy. Jednak w celu uzyskania dostępu do najnowszych wersji aplikacji Portal firmy urządzenia muszą mieć system iOS 8.0 lub późniejszą wersję. Zalecamy powiadomienie użytkowników, aby przeprowadzili aktualizację do wersji iOS 8.0 lub nowszej w celu pełnego korzystania z nowych funkcji usługi Intune.  


## <a name="april-2016"></a>Kwiecień 2016
Wszystkie te funkcje są również obsługiwane dla klientów hybrydowych (program Configuration Manager zintegrowany z usługą Intune).

### <a name="app-management"></a>Zarządzanie aplikacjami
- **Zgodność użytkownika funkcji zarządzania aplikacjami mobilnymi.**
Teraz można wyświetlić [stan](/intune/deploy-use/monitor-mobile-app-management-policies-with-Microsoft-Intune) zasad zarządzania aplikacjami dla dowolnego użytkownika w dzierżawie usługi Azure Active Directory (AAD). Obejmuje to następujące działania:
   - Urządzenia
   - Aplikacje na urządzeniu

   Wartości stanu:

   **Zaewidencjonowano**: wskazuje, że zasady zostały wdrożone dla użytkownika, aplikacja była stosowana w kontekście pracy i pomyślnie odebrała zasady.

    **Nie zaewidencjonowano**: wskazuje, że zasady zostały wdrożone dla użytkownika, ale aplikacja nie była stosowana w kontekście pracy od tego momentu.


- **Kontrolki zarządzania aplikacjami mobilnymi zapobiegające synchronizacji kontaktów programu Outlook (Android).**
Dostępne jest nowe ustawienie do [zarządzania aplikacjami mobilnymi](/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) bez rejestracji urządzeń. To ustawienie umożliwia zapobieganie synchronizacji przez aplikację kontaktów z natywną książką adresową na urządzeniach z systemem Android. Po włączeniu tego ustawienia wybrane aplikacje nie będą w stanie zapisywać kontaktów w natywnej książce adresowej. Po wyłączeniu tego ustawienia wybrane aplikacje będą w stanie zapisywać kontakty w natywnej książce adresowej. Po [zdalnym wyczyszczeniu urządzenia lub aplikacji](/intune/deploy-use/wipe-managed-company-app-data-with-Microsoft-Intune) zostaną usunięte wszystkie kontakty zapisane wcześniej w natywnej książce adresowej. To nowe ustawienie jest obsługiwane początkowo przez aplikację Outlook na urządzeniach z systemem Android.

### <a name="device-management"></a>Zarządzanie urządzeniami
- **Identyfikacja numeru telefonu dla urządzeń należących do firmy.** Telefony skategoryzowane jako firmowe są teraz identyfikowane przez pełny numer telefonu na przykład przy uruchomieniu raportu inwentaryzacyjnego urządzenia przenośnego. Numery telefonów BYOD są nadal maskowane symbolami **** i wyświetlane są tylko 4 ostatnie cyfry.


### <a name="company-portal-updates"></a>Aktualizacje Portalu firmy
**Aplikacja Portal firmy dla systemu Android** Użytkownicy, którzy nie zarejestrowali urządzeń w usłudze Intune i którzy nie mają zainstalowanych poprawnych certyfikatów, nie będą w stanie zalogować się do aplikacji Portal firmy systemu Android i zobaczą komunikat „Nie możesz się zalogować, ponieważ urządzenie nie ma wymaganego certyfikatu”. Komunikat zawiera link „Rozwiązanie problemu”, którego naciśnięcie powoduje wyświetlenie instrukcji instalacji certyfikatu. Aby zobaczyć kroki, które użytkownicy końcowi powinni wykonać w celu rozwiązania problemu, zobacz [Brak wymaganego certyfikatu urządzenia](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_cert_missing).

**Aplikacja Portal firmy dla systemu iOS** Dodano obsługę akcji „pociągnij, aby odświeżyć”, umożliwiającej odświeżenie zawartości ekranu głównego, w tym aplikacji, urządzeń i danych kontaktowych działu IT. Akcja „pociągnij, aby odświeżyć” nie sprawdza informacji dotyczących zgodności i zasad. Można to zrobić, wybierając kafelek bieżącego urządzenia i naciskając przycisk **Synchronizuj**.

**Aplikacja Portal firmy w systemie Windows 10 Mobile i Windows Phone 8.1** Podczas instalacji aplikacji biznesowych przez użytkowników końcowych wyświetlane jest teraz usprawnione środowisko instalacyjne aplikacji. Jeśli instalacja aplikacji trwa długo, użytkownicy mogą synchronizować swoje urządzenia ręcznie, co wymusza wznowienie procesu synchronizacji. Aby przejrzeć instrukcje dla użytkowników końcowych, zobacz [Ręczne synchronizowanie urządzenia w celu przyspieszenia instalacji aplikacji](https://technet.microsoft.com/library/mt427782.aspx#BKMK_win10m_wp81_sync_manually).

**Witryna sieci Web Portal firmy** Gdy użytkownicy systemów Windows 10 Mobile i Windows Phone 8.1 instalują aplikacje biznesowe, wyświetlane są następujące nowe stany zapewniające więcej informacji na temat stanu instalacji:

* **Oczekiwanie na synchronizację urządzenia** — użytkownik nacisnął pozycję „Instaluj” i urządzenie próbuje przeprowadzić synchronizację z infrastrukturą usługi Intune. Synchronizacja jest wymagana w celu ukończenia instalacji. Komunikat „Oczekiwanie na synchronizację urządzenia” to również link, który użytkownicy mogą nacisnąć w celu wyświetlenia [instrukcji](https://technet.microsoft.com/library/mt590895.aspx#BKMK_iwp_sync_manually) ręcznej synchronizacji urządzenia z usługą Intune, jeśli proces synchronizacji trwa długo lub zablokował się.
* **Pobieranie** — trwa przetwarzanie żądania pobierania użytkownika; urządzenie pobiera i instaluje aplikację.

Przed dodaniem tych stanów użytkownicy nie mieli wystarczających informacji na temat sytuacji w przypadku długich instalacji, ponieważ wyświetlany był tylko stan „Instalowanie”, który mógł pozostawać na ekranie godzinami. Dodanie nowych stanów oznacza, że zamiast kontaktować się z działem pomocy technicznej, użytkownicy mogą nacisnąć link „Oczekiwanie na synchronizację urządzenia” i wykonać instrukcje, aby wymusić wznowienie procesu synchronizacji.

>[!div class="step-by-step"]

>[&larr; **Co nowego w usłudze Intune**](whats-new-in-microsoft-intune.md)    



<!--HONumber=Dec16_HO1-->


