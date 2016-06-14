---
# required metadata

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

## Kwiecień 2016
Wszystkie te funkcje są również obsługiwane dla klientów hybrydowych (program Configuration Manager zintegrowany z usługą Intune).
### Zarządzanie aplikacjami
- **Zgodność użytkownika funkcji zarządzania aplikacjami mobilnymi.**
Teraz można wyświetlić [stan](monitor-mobile-app-management-policies-with-Microsoft-Intune.md) zasad zarządzania aplikacjami dla dowolnego użytkownika w dzierżawie usługi Azure Active Directory (AAD). Obejmuje to następujące działania:
   - Urządzenia
   - Aplikacje na urządzeniu

   Wartości stanu:

   **Zaewidencjonowano**: wskazuje, że zasady zostały wdrożone dla użytkownika, aplikacja była stosowana w kontekście pracy i pomyślnie odebrała zasady.

    **Nie zaewidencjonowano**: wskazuje, że zasady zostały wdrożone dla użytkownika, ale aplikacja nie była stosowana w kontekście pracy od tego momentu.


- **Kontrolki zarządzania aplikacjami mobilnymi zapobiegające synchronizacji kontaktów programu Outlook (Android).**
Dostępne jest nowe ustawienie do [zarządzania aplikacjami mobilnymi](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) bez rejestracji urządzeń. To ustawienie umożliwia zapobieganie synchronizacji przez aplikację kontaktów z natywną książką adresową na urządzeniach z systemem Android. Po włączeniu tego ustawienia wybrane aplikacje nie będą w stanie zapisywać kontaktów w natywnej książce adresowej. Po wyłączeniu tego ustawienia wybrane aplikacje będą w stanie zapisywać kontakty w natywnej książce adresowej. Po [zdalnym wyczyszczeniu urządzenia lub aplikacji](wipe-managed-company-app-data-with-Microsoft-Intune.md) zostaną usunięte wszystkie kontakty zapisane wcześniej w natywnej książce adresowej. To nowe ustawienie jest obsługiwane początkowo przez aplikację Outlook na urządzeniach z systemem Android.

### Zarządzanie urządzeniami
- **Identyfikacja numeru telefonu dla urządzeń należących do firmy.** Telefony skategoryzowane jako firmowe są teraz identyfikowane przez pełny numer telefonu na przykład przy uruchomieniu raportu inwentaryzacyjnego urządzenia przenośnego. Numery telefonów BYOD są nadal maskowane symbolami **** i wyświetlane są tylko 4 ostatnie cyfry.


### Aktualizacje Portalu firmy
**Aplikacja Portal firmy dla systemu Android**
Użytkownicy, którzy nie zarejestrowali urządzeń w usłudze Intune i którzy nie mają zainstalowanych poprawnych certyfikatów, nie będą w stanie zalogować się do aplikacji Portal firmy systemu Android i zobaczą komunikat „Nie możesz się zalogować ze względu na brak wymaganego certyfikatu na urządzeniu”. Komunikat zawiera link „Rozwiązanie problemu”, którego naciśnięcie powoduje wyświetlenie instrukcji instalacji certyfikatu. Aby zobaczyć kroki, które użytkownicy końcowi powinni wykonać w celu rozwiązania problemu, zobacz [Brak wymaganego certyfikatu urządzenia](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_cert_missing).

**Aplikacja Portal firmy dla systemu iOS**
Dodano obsługę akcji „pociągnij, aby odświeżyć”, umożliwiającej odświeżenie zawartości ekranu głównego, w tym aplikacji, urządzeń i danych kontaktowych działu IT. Akcja „pociągnij, aby odświeżyć” nie sprawdza informacji dotyczących zgodności i zasad. Można to zrobić, wybierając kafelek bieżącego urządzenia i naciskając przycisk **Synchronizuj**.

**Aplikacja Portal firmy w systemie Windows 10 Mobile i Windows Phone 8.1**
Podczas instalacji aplikacji biznesowych przez użytkowników końcowych wyświetlane jest teraz usprawnione środowisko instalacyjne aplikacji. Jeśli instalacja aplikacji trwa zbyt długo, użytkownicy mogą synchronizować swoje urządzenia ręcznie, co wymusza wznowienie procesu synchronizacji. Aby przejrzeć instrukcje dla użytkowników końcowych, zobacz [Ręczne synchronizowanie urządzenia w celu przyspieszenia instalacji aplikacji](https://technet.microsoft.com/library/mt427782.aspx#BKMK_win10m_wp81_sync_manually).

**Witryna sieci Web Portal firmy**
Gdy użytkownicy systemów Windows 10 Mobile i Windows Phone 8.1 instalują aplikacje biznesowe, wyświetlane są następujące nowe stany zapewniające więcej informacji na temat stanu instalacji:

* **Oczekiwanie na synchronizację urządzenia** — użytkownik nacisnął pozycję „Instaluj” i urządzenie próbuje przeprowadzić synchronizację z infrastrukturą usługi Intune. Synchronizacja jest wymagana w celu ukończenia instalacji. Komunikat „Oczekiwanie na synchronizację urządzenia” to również link, który użytkownicy mogą nacisnąć w celu wyświetlenia [instrukcji](https://technet.microsoft.com/library/mt590895.aspx#BKMK_iwp_sync_manually) ręcznej synchronizacji urządzenia z usługą Intune, jeśli proces synchronizacji trwa długo lub zablokował się.
* **Pobieranie** — trwa przetwarzanie żądania pobierania użytkownika; urządzenie pobiera i instaluje aplikację.

Przed dodaniem tych stanów użytkownicy nie mieli wystarczających informacji na temat sytuacji w przypadku długich instalacji, ponieważ wyświetlany był tylko stan „Instalowanie”, który mógł pozostawać na ekranie godzinami. Dodanie nowych stanów oznacza, że zamiast kontaktować się z działem pomocy technicznej, użytkownicy mogą nacisnąć link „Oczekiwanie na synchronizację urządzenia” i wykonać instrukcje, aby wymusić wznowienie procesu synchronizacji.

### Wkrótce

**Zmiany dotyczące kont menedżerów rejestracji urządzeń.** Aby zwiększyć wydajność i skalę, usługa Intune nie pokazuje już wszystkich urządzeń menedżerów rejestracji urządzeń (DEM) w okienku Moje urządzenia aplikacji Portal firmy. Wyświetlane jest tylko urządzenie lokalne, na którym uruchomiono aplikację, jeśli zostało zarejestrowane przez aplikację Portal firmy. Użytkownik menedżera rejestracji urządzeń może wykonywać działania na urządzeniu lokalnym, ale zdalne zarządzanie innymi zarejestrowanymi urządzeniami można przeprowadzać tylko z konsoli administracyjnej usługi Intune.  Dodatkowo usługa Intune wycofuje korzystanie z kont menedżera rejestracji urządzeń z programem Device Enrollment Program firmy Apple i narzędziem Apple Configurator. Obie te metody rejestracji obsługują już rejestrację bez użytkowników dla udostępnionych urządzeń z systemem iOS.  Kont menedżera rejestracji urządzeń należy używać tylko w przypadku braku dostępności rejestracji bez użytkowników dla urządzeń udostępnionych.

Śledź na bieżąco rozwój usługi Intune, korzystając z [mapy platformy usług w chmurze](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).


## Poprzednie wersje usługi Intune
Aby zobaczyć funkcje wprowadzone w usłudze Intune w ostatnich sześciu miesiącach, zobacz artykuł [Poprzednie wersje usługi Intune](previous-intune-releases.md).



### Zobacz także
* [Blog usługi Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)


<!--HONumber=May16_HO1-->


