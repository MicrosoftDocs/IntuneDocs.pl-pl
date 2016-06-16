---
# required metadata

experiment_id: lindavr-abtest-20160527
title: Co nowego | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Co nowego w usłudze Microsoft Intune
## Czerwiec 2016

### Aktualizacje Portalu firmy

#### Aplikacja Portal firmy dla systemu iOS

- Podczas instalacji aplikacji biznesowych przez użytkowników końcowych wyświetlane jest teraz usprawnione środowisko instalacyjne aplikacji. Jeśli instalacja aplikacji trwa długo, użytkownicy mogą synchronizować swoje urządzenia ręcznie, co wymusza wznowienie procesu synchronizacji. Aby przejrzeć instrukcje dla użytkowników końcowych, zobacz [Ręczne synchronizowanie urządzenia z systemem iOS](/Intune/EndUser/sync-your-device-manually-ios.md).

- Aplikacja Portal firmy usługi Microsoft Intune dla systemu iOS została zaktualizowana do obsługi systemu iOS w wersji 8.0 i nowszych. Ta aktualizacja oznacza, że użytkownicy końcowi mogą instalować aplikację Portal firmy i rejestrować w usłudze Intune nowe urządzenia tylko wtedy, gdy urządzenie ma zainstalowany system iOS w wersji 8.0 lub nowszej. Użytkownicy, którzy mają wcześniej zarejestrowane urządzenia z nieobsługiwaną wersją systemu iOS, mogą nadal używać aplikacji Portal firmy, która znajduje się na urządzeniu.

## Maj 2016


Wszystkie te funkcje są również obsługiwane dla wdrożeń hybrydowych (program Configuration Manager z usługą Intune). Aby uzyskać więcej informacji na temat nowych funkcji hybrydowych, odwiedź stronę [Co nowego w funkcjach hybrydowych](https://technet.microsoft.com/en-us/library/mt718155.aspx).

### Dokumentacja

Zapraszamy do skorzystania z wersji zapoznawczej witryny [docs.microsoft.com](https://docs.microsoft.com/en-us/intune)!
Jest to zupełnie nowa, nowoczesna platforma zawartości zaprojektowana z myślą o tym, aby ułatwić naszym klientom zrozumienie usługi Intune oraz korzystanie z niej.
Aby przeczytać o wszystkich nowych funkcjach, zobacz [Wprowadzenie do witryny docs.microsoft.com](https://docs.microsoft.com/teamblog/introducing-docs-microsoft-com/)

### Kondycja usługi Intune
Informacje o kondycji usługi Intune zostały przeniesione do centralnej lokalizacji z innymi usługami firmy Microsoft. Teraz znajdziesz te informacje w [portalu zarządzania usługą Office 365](https://portal.office.com/Admin/Default.aspx) w obszarze **Kondycja usługi**.
Aby uzyskać więcej informacji, zobacz [ten wpis w blogu](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).


### Zarządzanie aplikacjami

- **Zestaw SDK zarządzania aplikacjami mobilnymi: obsługa konfiguracji długości numeru PIN.** Będzie możliwe określenie długości numeru PIN dla aplikacji w ramach zarządzania aplikacjami mobilnymi, podobnie jak w przypadku numeru PIN urządzenia. Użytkownicy końcowi będą musieli zachować zgodność z określonymi nowymi ograniczeniami. Będzie wyświetlany nieco zmodyfikowany ekran numeru PIN, umożliwiający wprowadzanie dłuższych numerów. Aby uzyskać szczegółowe informacje, zobacz [Ustawienia zasad zarządzania aplikacjami mobilnymi dla systemu Android](/intune/deploy-use/android-mam-policy-settings) i [Ustawienia zasad zarządzania aplikacjami mobilnymi dla systemu iOS](/intune/deploy-use/ios-mam-policy-settings).

- **Aplikacja Skype dla firm dla systemów iOS i Android.** Aplikację Skype dla firm można teraz wskazać jako objętą [zarządzaniem aplikacjami mobilnymi bez stosowania zasad rejestracji](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune). Gdy użytkownicy zalogują się, zostaną zastosowane zasady zarządzania aplikacjami mobilnymi.

- **Nowe aplikacje dostępne do zarządzania przy użyciu zasad zarządzania aplikacjami mobilnymi.** Aplikacje Microsoft Word, Excel i PowerPoint dla systemu Android teraz mogą być skojarzone z zasadami zarządzania aplikacjami mobilnymi na urządzeniach, które nie są zarejestrowane w usłudze Intune. Pełna lista obsługiwanych aplikacji jest dostępna w galerii aplikacji mobilnych usługi Microsoft Intune na stronie [partnerów aplikacji usługi Microsoft Intune](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx).



### Aktualizacje Portalu firmy

#### Aplikacja Portal firmy dla systemu Android

- **Wyskakujące powiadomienia dla użytkownika końcowego**: użytkownicy końcowi będą teraz otrzymywać wyskakujące powiadomienia z aplikacji Portal firmy dla systemu Android, gdy będą rejestrować lub usuwać swoje urządzenia w Portalu firmy.

- **Zmiany w kontach menedżerów rejestracji urządzeń w aplikacji Portal firmy dla systemu Android.** W celu poprawy wydajności i skalowania usługa Intune nie pokazuje już wszystkich urządzeń menedżerów rejestracji urządzeń (DEM) w okienku Moje urządzenia w aplikacji Portal firmy dla systemu Android. Wyświetlane jest tylko urządzenie lokalne, na którym uruchomiono aplikację, o ile zostało zarejestrowane przez aplikację Portal firmy. Użytkownik menedżera rejestracji urządzeń może wykonywać działania na urządzeniu lokalnym, ale zdalne zarządzanie innymi zarejestrowanymi urządzeniami można przeprowadzać tylko z konsoli administracyjnej usługi Intune.
-
#### Witryna sieci Web Portal firmy

**Witryna sieci Web Portal firmy: transparent identyfikacji urządzenia będzie zapewniać więcej informacji użytkownikom końcowym.** Użytkownicy końcowi mogą teraz łatwiej identyfikować urządzenie, które wybrali, gdy korzystają z witryny sieci Web Portal firmy. W przypadku wybrania niewłaściwego urządzenia użytkownik będzie mógł wybrać poprawne urządzenie, naciskając link **Naciśnij tutaj** na transparencie na stronie głównej.


## Wkrótce

- **Dołączanie w interfejsie użytkownika Centrum wiadomości**. W ramach migracji usługi Intune do [portalu zarządzania usługą Office 365](https://portal.office.com/) rozpoczniemy korzystanie z Centrum wiadomości portalu w celu informowania o nowych funkcjach i przesyłania innych powiadomień. Ponadto po zainstalowaniu towarzyszącej administracyjnej aplikacji mobilnej usługi Office 365 możesz otrzymywać powiadomienia na telefonie komórkowym oraz łatwo przekazywać wszelkie komunikaty użytkownikom i aliasom dystrybucyjnym.
Od majowej wersji zaczniemy używać Centrum wiadomości w celu powiadamiania o ukończeniu aktualizacji oraz dołączymy informacje o nowych i ulepszonych funkcjach usługi Intune. Sprawdź Centrum wiadomości już dzisiaj, logując się do [portalu zarządzania usługi Office 365](https://portal.office.com/) i wybierając opcję CENTRUM WIADOMOŚCI w lewym okienku nawigacji.

- **Zmiany dotyczące kont menedżerów rejestracji urządzeń**. W celu poprawy wydajności i skalowania usługa Intune nie pokazuje już **wszystkich** urządzeń menedżerów rejestracji urządzeń (DEM) w okienku **Moje urządzenia** aplikacji Portal firmy dla systemu iOS. Wyświetlane jest tylko urządzenie lokalne, na którym uruchomiono aplikację, o ile zostało zarejestrowane przez aplikację Portal firmy. Użytkownik menedżera rejestracji urządzeń może wykonywać działania na urządzeniu lokalnym, ale zdalne zarządzanie innymi zarejestrowanymi urządzeniami można przeprowadzać tylko z konsoli administracyjnej usługi Intune. Dodatkowo w usłudze Intune wycofano używanie kont menedżera rejestracji urządzeń z programem Device Enrollment Program firmy Apple i narzędziem Apple Configurator. Obie te metody rejestracji obsługują już rejestrację bez użytkowników dla współużytkowanych urządzeń z systemem iOS. Kont menedżera rejestracji urządzeń należy używać tylko w przypadku braku dostępności rejestracji bez użytkowników dla współużytkowanych urządzeń.

### Plan chmury
Śledź na bieżąco rozwój usługi Intune, korzystając z [planu platformy w chmurze](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).

### Wycofywanie usług
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



## Poprzednie wersje usługi Intune
Aby zobaczyć funkcje wprowadzone w usłudze Intune w ostatnich sześciu miesiącach, zobacz artykuł [Poprzednie wersje usługi Intune](previous-intune-releases.md).
> [!div class="op_single_selector"]
- [Kwiecień 2016](previous-intune-releases.md)
- [Marzec 2016](previous-intune-releases.md)
- [Luty 2016](previous-intune-releases.md)
- [Styczeń 2016](previous-intune-releases.md)
- [Grudzień 2015](previous-intune-releases.md)
- [Listopad 2015](previous-intune-releases.md)




### Zobacz także
* [Blog usługi Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plan platformy w chmurze](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)


<!--HONumber=Jun16_HO2-->


