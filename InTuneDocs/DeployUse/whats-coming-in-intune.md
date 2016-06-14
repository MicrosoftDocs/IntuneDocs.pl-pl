---
# required metadata

title: Wkrótce | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 05/03/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Wkrótce w usłudze Microsoft Intune
Te informacje są przekazywane pod rygorem umowy NDA w bardzo ograniczonym zakresie i mogą ulec zmianie. Niektóre funkcje wymienione w tym miejscu mogą nie być gotowe w dniu odcięcia i zostać opóźnione do przyszłych wersji. Inne funkcje są testowane w trybie pilotażowym, co zapewnia przygotowanie ich do użytku przez klientów. Skontaktuj się ze swoim partnerem ds. Intune/PM w przypadku jakichkolwiek pytań lub wątpliwości.

Ta strona jest okresowo aktualizowana. Odwiedź ją ponownie, aby sprawdzić informacje na temat nadchodzących aktualizacji.

Dla usługi Intune opracowywane są następujące zmiany. Wszystkie te funkcje będą również obsługiwane dla hybrydowych wdrożeń klientów (program Configuration Manager z usługą Intune). Aby uzyskać więcej informacji na temat nowych funkcji hybrydowych, odwiedź stronę [Nowości dla funkcji hybrydowych](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

## Dołączanie do Centrum wiadomości
W ramach migracji usługi Intune do [portalu zarządzania usługą Office 365](https://portal.office.com/) rozpoczniemy korzystanie z Centrum wiadomości portalu w celu informowania o nowych funkcjach i przesyłania innych powiadomień.  Ponadto po zainstalowaniu towarzyszącej aplikacji mobilnej Office 365 Admin możesz otrzymywać powiadomienia na telefonie komórkowym oraz z łatwością przekazywać wszelkie komunikaty użytkownikom i aliasom dystrybucyjnym.<br>  
Od majowej wersji rozpoczniemy korzystanie z Centrum wiadomości do powiadamiania o ukończeniu aktualizacji wraz z informacjami o nowych i ulepszonych funkcjach usługi Intune.  Sprawdź Centrum wiadomości, logując się do [portalu zarządzania usługi Office 365](https://portal.office.com/) i wybierając opcję **CENTRUM WIADOMOŚCI** w lewym okienku nawigacyjnym.
<!---TFS 1242782--->


## Zarządzanie aplikacjami
- **Dostęp warunkowy dla przeglądarki.** Możliwe będzie ustawienie zasad dostępu warunkowego dla usług Exchange Online i SharePoint Online, co umożliwi dostęp do nich tylko przez zarządzane i zgodne urządzenia z systemem iOS lub Android. Użytkownicy końcowi, którzy podejmą próbę zalogowania się do witryny usługi Outlook Web Access (OWA) lub usługi SharePoint przy użyciu urządzeń z systemem iOS i Android, zostaną poproszeni o zarejestrowanie swoich urządzeń w usłudze Intune, jak również naprawienie wszelkich problemów z niezgodnością przed zakończeniem logowania.
<!---TFS 1175844--->

- **Zestaw SDK zarządzania aplikacjami mobilnymi: obsługa konfiguracji długości numeru PIN.** Możliwe będzie określenie długości numeru PIN dla aplikacji zarządzania aplikacjami mobilnymi, podobnie jak numeru PIN urządzenia. Użytkownicy końcowi będą musieli zachować zgodność z określonymi ograniczeniami. Wyświetlany będzie nieco zmodyfikowany ekran numeru PIN, umożliwiający wprowadzanie dłuższych numerów.
<!--- TFS 1104753--->

- **Kontrolki zarządzania aplikacjami mobilnymi zapobiegające synchronizacji kontaktów programu Outlook (iOS).** Dostępne jest nowe ustawienie do zarządzania aplikacjami mobilnymi bez rejestracji urządzeń. To ustawienie umożliwia administratorowi usługi Intune zapobieganie synchronizacji przez aplikacje kontaktów z natywną książką adresową na urządzeniach z systemem iOS. Po włączeniu tego ustawienia aplikacja nie będzie w stanie zapisywać kontaktów w natywnej książce adresowej. Po wyłączeniu tego ustawienia aplikacja będzie w stanie zapisywać kontakty w natywnej książce adresowej. Po selektywnym wyczyszczeniu urządzenia przez administratora usługi Intune zostaną usunięte wszystkie kontakty zapisane wcześniej w natywnej książce adresowej. To nowe ustawienie jest teraz obsługiwane przez aplikację Outlook na urządzeniach z systemem iOS.
<!---TFS item 1276166--->

- **Skype dla firm dla systemu Android.** Administratorzy usługi Intune mogą teraz kierować aplikacją Skype dla firm przy użyciu zarządzania aplikacjami mobilnymi bez zasad rejestracji.  Po zalogowaniu użytkowników stosowane są zasady zarządzania aplikacjami mobilnymi.
<!--- TFS item 1248444 --->

- **Skype dla firm dla systemu iOS.** Administratorzy usługi Intune mogą teraz kierować aplikacją Skype dla firm przy użyciu zarządzania aplikacjami mobilnymi bez zasad rejestracji.  Po zalogowaniu użytkowników stosowane są zasady zarządzania aplikacjami mobilnymi.
<!--- TFS item 1248443 --->

### Obsługa platformy Xamarin
Zestaw SDK aplikacji usługi Microsoft Intune obsługuje teraz aplikacje platformy Xamarin w następujących scenariuszach:

- Tworzenie nowych aplikacji oraz modyfikowanie kodu istniejącej gamy aplikacji biznesowych przy użyciu zestawu SDK usługi Intune. Dodatek jest dostępny na stronie [Microsoft Intune Github](https://github.com/msintuneappsdk).
- Rozszerzenie obsługi zarządzania aplikacjami mobilnymi na istniejącą gamę aplikacji biznesowych przy użyciu narzędzia opakowującego aplikacje usługi Intune

Aby ułatwić sobie wybór metody, zapoznaj się z artykułem [Wybieranie sposobu przygotowania aplikacji do zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune).
<!--- TFS 1061478 & TFS 1152340--->


## Zarządzanie urządzeniami
- **Sesje Pomocy zdalnej dla komputerów z systemem Windows.** Integracja aplikacji TeamViewer z komputerami z systemem Windows zarządzanymi przez agenta umożliwia tworzenie sesji pomocy zdalnej dla komputerów z systemem Windows zarządzanych przez agenta, co zapewnia pomoc dla działów pomocy technicznej użytkowników końcowych. Dotyczy to systemów Windows 7, 8, 8.1 i Windows 10.
<!--- TFS 1284856--->


<!--- TFS item 1274326 --->

## Kontrola dostępu
* **Usługa Skype dla firm Online obsługuje dostęp warunkowy.** Administratorzy usługi Intune będą w stanie określać zasady dostępu warunkowego dla usługi Skype dla firm Online, co umożliwia dostęp do niej tylko przez zarządzane i zgodne urządzenia z systemem iOS lub Android. Użytkownicy końcowi, którzy podejmą próbę zalogowania się do aplikacji mobilnej Skype dla firm w systemie iOS lub Android, zostaną poproszeni o rejestrację w usłudze Intune oraz rozwiązanie wszystkich problemów z niezgodnością przed zakończeniem logowania.
<!---TFS item 1254499--->

## Portal firmy
* **Baner identyfikacji urządzenia będzie zapewniać więcej informacji użytkownikom końcowym.** Ułatwi użytkownikom identyfikację wybranych urządzeń przy korzystaniu z witryny sieci Web Portalu firmy. W przypadku wybrania niewłaściwego urządzenia użytkownik będzie mógł wybrać poprawne urządzenie, naciskając link „Dotknij tutaj” na banerze na stronie głównej.
<!--- TFS 1231157--->

* **Pakiety aplikacji systemu Windows dostępne bezpośrednio z Portalu firmy**: użytkownicy komputerów z systemami Windows 8, Windows 8.1 i Windows RT mogą teraz instalować pakiety aplikacji systemu Windows (z rozszerzeniem appx) bezpośrednio z witryny Portalu firmy. Poprzednio to administratorzy usługi Intune musieli wdrażać aplikacje lub też użytkownicy musieli instalować aplikację Portal firmy na urządzeniach w celu instalacji aplikacji.
<!--- TFS item 1082481 --->

* **Użytkownicy mogą zdalnie zablokować urządzenie z Portalu firmy** Do witryny sieci Web Portalu firmy dodano nową opcję blokady zdalnej, która umożliwia użytkownikom zdalne blokowanie urządzenia z portalu w przypadku jego utraty lub kradzieży. Poniższa tabela zawiera platformy obsługiwane przez funkcję blokady zdalnej usługi Intune oraz usługi Intune z programem Configuration Manager.
<!--- TFS item 1195661 --->

|Platforma  |Szczegóły dotyczące obsługi|
|---------|---------|
|iOS | Obsługiwane|
|Android | Obsługiwane|
|Windows Phone 8,1 | Obsługiwane|
|Windows 10 Mobile | Obsługiwane tylko wtedy, gdy na telefonie ustawiono kod dostępu|
|Komputer (Windows 8.0 i starsze) | Nieobsługiwane|
|Komputer (Windows 8.1) | Nieobsługiwane|
|Windows Phone 8.0 | Nieobsługiwane|
|Windows 10 Desktop | Nieobsługiwane|

## Wycofanie usług
* **Określanie grup niestandardowych do usuwania reguł powiadomień.** Od początku czerwca 2016 r. nie będzie już możliwe wykorzystanie Kreatora tworzenia reguł powiadomień do określania reguł powiadomień dla grup utworzonych przez użytkowników.

    Obecnie w celu wyboru grupy utworzonej przez użytkowników w konsoli administracyjnej usługi Microsoft Intune należy wybrać opcję **Administrator** > **Reguły powiadomień** > **Utwórz nową regułę**. W drugim kroku Kreatora tworzenia reguł powiadomień należy wybrać grupy urządzeń, których dotyczyć będzie dana reguła. Ten krok, **Wybierz grupy urządzeń**, jest wycofywany z konsoli usługi Intune.

    Krok **Wybierz grupy urządzeń** nie będzie obsługiwany począwszy od wersji usługi Intune z czerwca 2016 r. Opcja ta będzie jednak dalej widoczna do sierpnia 2016 r. Po sierpniu zaczniemy migrację dzierżaw do nowego środowiska pracy, co potrwa dwa miesiące. Do października 2016 r. wszyscy istniejący klienci powinni zostać przeniesieni do nowego środowiska. Po przejściu do nowego środowiska nie będzie już wyświetlana opcja określenia reguł powiadomień dla konkretnej grupy.
<!---   TFS 1278864--->







### Zobacz także
Aby dowiedzieć się więcej o najnowszych zmianach, zapoznaj się z artykułem [Co nowego w usłudze Microsoft Intune](whats-new-in-microsoft-intune.md).


<!--HONumber=May16_HO1-->


