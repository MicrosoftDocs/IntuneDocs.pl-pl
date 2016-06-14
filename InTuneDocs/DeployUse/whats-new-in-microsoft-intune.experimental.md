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

## Maj 2016 r.


Wszystkie opisane funkcje — z wyjątkiem integracji z oprogramowaniem TeamViewer — są obsługiwane również we wdrożeniach hybrydowych (program Configuration Manager z usługą Intune). Aby uzyskać więcej informacji na temat nowych funkcji hybrydowych, odwiedź stronę [Nowości dla funkcji hybrydowych](https://technet.microsoft.com/en-us/library/mt718155.aspx).

### Dokumentacja

Zapraszamy do wersji zapoznawczej witryny [docs.microsoft.com](https://docs.microsoft.com/en-us/intune).
Jest to zupełnie nowa, nowoczesna platforma zawartości zaprojektowana z myślą o tym, aby ułatwić naszym klientom zrozumienie usługi Intune oraz korzystanie z niej.
Aby przeczytać o wszystkich nowych funkcjach, zobacz temat [Introducing docs.microsoft.com](https://docs.microsoft.com/teamblog/introducing-docs-microsoft-com/) (Wprowadzenie do witryny docs.microsoft.com)

### Kondycja usługi Intune
Informacje o kondycji usługi Intune zostały przeniesione do lokalizacji centralnej z innymi usługami firmy Microsoft. Teraz znajdziesz te informacje w [portalu zarządzania usługą Office 365](https://portal.office.com/Admin/Default.aspx) w obszarze **Kondycja usługi**.
Aby uzyskać więcej informacji, zobacz [ten wpis w blogu](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).


### Zarządzanie aplikacjami

- **Zestaw SDK zarządzania aplikacjami mobilnymi: obsługa konfiguracji długości numeru PIN.** Możliwe będzie określenie długości numeru PIN dla aplikacji zarządzania aplikacjami mobilnymi, podobnie jak numeru PIN urządzenia. Użytkownicy końcowi będą musieli zachować zgodność z ustawionymi ograniczeniami. Wyświetlany będzie nieco zmodyfikowany ekran numeru PIN, umożliwiający wprowadzanie dłuższych numerów. Aby uzyskać szczegółowe informacje, zobacz [Ustawienia zasad zarządzania aplikacjami mobilnymi dla systemu Android](/intune/deploy-use/android-mam-policy-settings) i [Ustawienia zasad zarządzania aplikacjami mobilnymi dla systemu iOS](/intune/deploy-use/ios-mam-policy-settings).

- **Skype dla firm dla systemów iOS i Android.** Aplikację Skype dla firm można teraz wskazać jako objętą [zarządzaniem aplikacjami mobilnymi i to bez konieczności stosowania zasad rejestracji](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune). Gdy użytkownicy zalogują się, zostaną zastosowane zasady zarządzania aplikacjami mobilnymi.

- **Nowe aplikacje dostępne do zarządzania z zastosowaniem zasad zarządzania aplikacjami mobilnymi.** Aplikacje Microsoft Word, Excel i PowerPoint dla systemu Android teraz mogą być skojarzone z zasadami zarządzania aplikacjami mobilnymi na urządzeniach, które nie są zarejestrowane w usłudze Intune. Pełna lista obsługiwanych aplikacji jest dostępna w galerii aplikacji mobilnych usługi Microsoft Intune na stronie [partnerów aplikacji usługi Microsoft Intune](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx).

### Zarządzanie urządzeniami

- **Sesje pomocy zdalnej dla komputerów z systemem Windows.** Integracja oprogramowania TeamViewer dla komputerów z systemem Windows zarządzanych przez oprogramowanie klienckie usługi Intune umożliwi ustanawianie sesji pomocy zdalnej z komputerami z systemem Windows w celu wsparcia działu pomocy technicznej. Obsługiwane są komputery z systemami Windows 7, 8, 8.1 i Windows 10.
Aby uzyskać więcej informacji, zobacz [Typowe zadania związane z zarządzaniem komputerem z systemem Windows za pomocą klienta komputerowego usługi Microsoft Intune](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#respond-to-a-remote-assistance-request).

### Aktualizacje Portalu firmy

#### Aplikacja Portal firmy dla systemu Android

- **Wyskakujące powiadomienia dla użytkownika końcowego**: użytkownicy końcowi będą teraz otrzymywać wyskakujące powiadomienia z aplikacji Portal firmy dla systemu Android, gdy będą rejestrować w niej urządzenia lub usuwać je z niej.

- **Zmiany w kontach menedżerów rejestracji urządzeń w aplikacji Portal firmy dla systemu Android.** W celu poprawy wydajności i skalowania usługa Intune nie pokazuje już wszystkich urządzeń menedżerów rejestracji urządzeń (DEM) w okienku Moje urządzenia aplikacji Portal firmy dla systemu Android. Wyświetlane jest tylko urządzenie lokalne, na którym uruchomiono aplikację, jeśli zostało zarejestrowane przez aplikację Portal firmy. Użytkownik menedżera rejestracji urządzeń może wykonywać działania na urządzeniu lokalnym, ale zdalne zarządzanie innymi zarejestrowanymi urządzeniami można przeprowadzać tylko z konsoli administracyjnej usługi Intune.
-
#### Witryna sieci Web Portal firmy

**Witryna sieci Web Portal firmy: baner identyfikacji urządzenia będzie zapewniać więcej informacji użytkownikom końcowym.** Użytkownicy mogą teraz łatwiej identyfikować urządzenie, które wybrali, gdy korzystają z witryny sieci Web Portal firmy. W przypadku wybrania niewłaściwego urządzenia użytkownik będzie mógł wybrać poprawne urządzenie, naciskając link **Dotknij tutaj** na banerze na stronie głównej.


## Wkrótce

- **Dołączanie interfejsu użytkownika Centrum wiadomości**. W ramach migracji usługi Intune do [portalu zarządzania usługą Office 365](https://portal.office.com/) rozpoczniemy korzystanie z Centrum wiadomości portalu w celu informowania o nowych funkcjach i przesyłania innych powiadomień. Ponadto po zainstalowaniu towarzyszącej aplikacji mobilnej Office 365 Admin możesz otrzymywać powiadomienia na telefonie komórkowym oraz z łatwością przekazywać wszelkie komunikaty użytkownikom i aliasom dystrybucyjnym.
Od majowej wersji rozpoczniemy korzystanie z Centrum wiadomości do powiadamiania o ukończeniu aktualizacji wraz z informacjami o nowych i ulepszonych funkcjach usługi Intune. Sprawdź Centrum wiadomości, logując się do [portalu zarządzania usługi Office 365](https://portal.office.com/) i wybierając opcję CENTRUM WIADOMOŚCI w lewym okienku nawigacyjnym.

- **Zmiany dotyczące kont menedżerów rejestracji urządzeń**. W celu poprawy wydajności i skalowania usługa Intune nie pokazuje już **wszystkich** urządzeń menedżerów rejestracji urządzeń (DEM) w okienku **Moje urządzenia** aplikacji Portal firmy dla systemu iOS. Wyświetlane jest tylko urządzenie lokalne, na którym uruchomiono aplikację, jeśli zostało zarejestrowane przez aplikację Portal firmy. Użytkownik menedżera rejestracji urządzeń może wykonywać działania na urządzeniu lokalnym, ale zdalne zarządzanie innymi zarejestrowanymi urządzeniami można przeprowadzać tylko z konsoli administracyjnej usługi Intune. Dodatkowo usługa Intune wycofuje korzystanie z kont menedżera rejestracji urządzeń z programem Device Enrollment Program firmy Apple i narzędziem Apple Configurator. Obie te metody rejestracji obsługują już rejestrację bez użytkowników dla współużytkowanych urządzeń z systemem iOS. Kont menedżera rejestracji urządzeń należy używać tylko w przypadku braku dostępności rejestracji bez użytkowników dla urządzeń udostępnionych.

### Plan chmury
Śledź na bieżąco rozwój usługi Intune, korzystając z [mapy platformy usług w chmurze](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).

### Wycofanie usług
- **Aplikacje Intune Viewer.** Wraz z wydaniem nowej aplikacji RMS sharing usuwamy następujące aplikacje Intune Viewer, począwszy od sierpnia 2016 roku:
    - Intune AV Viewer
    - Intune PDF Viewer
    - Intune Image Viewer dla systemu Android z witryny Google Play

  Zamiast korzystać z aplikacji Intune Viewer, zalecamy używanie nowej aplikacji Rights Management (RMS sharing) dla systemu Android, która pozwala na wdrożenie jednej aplikacji zamiast trzech osobnych aplikacji w celu bezpiecznego przeglądania plików firmy na urządzeniach. Dowiedz się więcej na temat aplikacji RMS sharing (za pomocą linku do dokumentacji).

- **Usunięcie możliwości określania własnych grup docelowych dla reguł powiadomień.**
Reguły powiadomień usługi Intune definiują osoby, do których będą wysyłane alerty e-mail z usługi Intune. Obecnie można konfigurować reguły powiadomień w celu wysyłania wiadomości e-mail do wszystkich użytkowników urządzeń należących do utworzonej grupy urządzeń usługi Intune. Począwszy od 1 czerwca 2016 roku wskazywanie grup utworzonych przez użytkownika jako docelowych nie będzie obsługiwane.

    Aktualnie w celu skierowania reguły powiadomień do grupy utworzonej z konsoli administracyjnej usługi Microsoft Intune należy wykonać następujące czynności:

    W obszarze roboczym **Administrator** kliknij pozycje **Reguły powiadomień** > **Utwórz nową regułę**

    W drugim kroku Kreatora tworzenia reguł powiadomień wybierz grupy urządzeń, których dotyczyć będzie dana reguła. Krok „Wybierz grupy urządzeń” jest wycofywany z konsoli usługi Intune.

    Wstępny plan dla tej zmiany jest następujący:
    - W czerwcu 2016 roku nowi dzierżawcy nie zobaczą kroku drugiego Kreatora tworzenia reguł powiadomień. Nie dotyczy to jednak istniejących dzierżaw.
    - W okolicach sierpnia 2016 roku dla niektórych istniejących dzierżaw nie będzie już widoczny krok „Wybierz grupy urządzeń” w kreatorze.
    - W okolicach października 2016 roku oczekujemy, że krok „Wybierz grupy urządzeń” w kreatorze przestanie być widoczny dla wszystkich dzierżaw.


- **Zmiany w zakresie obsługi aplikacji Portal firmy dla systemu iOS**. W najbliższych miesiącach zostanie przeprowadzona aktualizacja aplikacji Portal firmy usługi Microsoft Intune dla systemu iOS, która będzie obsługiwać tylko urządzenia z systemem iOS 8.0 lub nowszym. Użytkownicy nie będą mogli rejestrować nowych urządzeń z systemem starszym niż iOS 8.0. Zarejestrowane urządzenia z wersjami systemu starszymi niż iOS 8.0 nadal będą zarządzane i przez ograniczony czas będzie można nadal korzystać z aplikacji Portal firmy. Jednak w celu uzyskania dostępu do najnowszych wersji aplikacji Portal firmy urządzenia muszą mieć system iOS 8.0 lub nowszy. Firma Microsoft zachęca do powiadamiania użytkowników, aby aktualizowali systemy na swoich urządzeniach do wersji iOS 8.0 lub nowszej, dzięki czemu będą mogli w pełni korzystać z nowych funkcji usługi Intune.



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


<!--HONumber=Jun16_HO1-->


