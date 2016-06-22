---
# required metadata

title: Wkrótce | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 06/10/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: mamoriss
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Wkrótce w usłudze Microsoft Intune
Te informacje są przekazywane pod rygorem umowy NDA w bardzo ograniczonym zakresie i mogą ulec zmianie. Niektóre funkcje wymienione w tym miejscu mogą nie być wdrożone na czas i zostać opóźnione do przyszłych wersji. Inne funkcje są testowane w wersji pilotażowej, aby zapewnić przygotowanie ich do użytku przez klientów. W przypadku pytań lub wątpliwości skontaktuj się ze swoim partnerem ds. usługi Intune/PM.

Ta strona jest okresowo aktualizowana. Odwiedź ją ponownie, aby sprawdzić informacje na temat nadchodzących aktualizacji.

Dla usługi Intune opracowywane są następujące zmiany. Wszystkie te funkcje będą również obsługiwane dla hybrydowych wdrożeń klientów (program Configuration Manager z usługą Intune). Aby uzyskać więcej informacji na temat nowych funkcji hybrydowych, odwiedź stronę [Co nowego w funkcjach hybrydowych](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).


## Zarządzanie aplikacjami
- **Ulepszone funkcje konfiguracji zasad dotyczących danych przedsiębiorstwa w systemie Windows 10.** Wprowadzono ulepszenia funkcji konfiguracji zasad ochrony danych przedsiębiorstwa w systemie Windows 10 dotyczące tworzenia reguł aplikacji, określania definicji granic sieci i innych ustawień ochrony danych przedsiębiorstwa.
<!---TFS 1303011--->

- **Dostęp warunkowy dla przeglądarki.** Będzie możliwe ustawienie zasad dostępu warunkowego dla usług Exchange Online i SharePoint Online, co umożliwi dostęp do nich tylko przez zarządzane i zgodne urządzenia z systemem iOS lub Android. Użytkownicy końcowi, którzy podejmą próbę zalogowania się do witryn usługi Outlook Web Access (OWA) lub usługi SharePoint przy użyciu urządzeń z systemami iOS i Android, zostaną poproszeni o zarejestrowanie swoich urządzeń w usłudze Intune oraz rozwiązanie wszelkich problemów z niezgodnością przed ukończeniem logowania.
<!---TFS 1175844--->

- **Usługa Dynamics CRM Online obsługuje dostęp warunkowy.** Klienci będą mogli określać zasady dostępu warunkowego dla usługi Dynamics CRM Online, co umożliwi dostęp do niej tylko przez zarządzane i zgodne urządzenia z systemem iOS lub Android. Użytkownicy końcowi, którzy podejmą próbę zalogowania się do aplikacji mobilnej Dynamics CRM w systemie iOS lub Android, zostaną poproszeni o rejestrację w usłudze Intune oraz rozwiązanie wszelkich problemów z niezgodnością przed ukończeniem logowania.
<!---TFS1295358--->

### Obsługa platformy Xamarin
Zestaw SDK aplikacji usługi Microsoft Intune będzie obsługiwać aplikacje platformy Xamarin w następujących scenariuszach:

- Tworzenie nowych aplikacji oraz modyfikowanie kodu istniejących aplikacji biznesowych przy użyciu zestawu SDK usługi Intune. Wtyczka będzie dostępna na [stronie usługi Microsoft Intune w serwisie Github](https://github.com/msintuneappsdk).
- Dodanie obsługi zarządzania aplikacjami mobilnymi do istniejących aplikacji biznesowych przy użyciu narzędzia opakowującego aplikacje usługi Intune

Aby łatwiej wybrać metodę do zastosowania, zobacz [Wybieranie sposobu przygotowania aplikacji do zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune).
<!--- TFS 1061478 & TFS 1152340--->

## Zarządzanie urządzeniami
- **Ustawienie zasad programu Windows Defender umożliwiające ochronę przed potencjalnie niechcianymi aplikacjami.** W programie Windows Defender dodano nowe ustawienie o nazwie **Wykrywanie potencjalnie niechcianych aplikacji** do ogólnych zasad konfiguracji systemu Windows 10 Desktop i Mobile. Przy użyciu tego ustawienia możesz chronić zarejestrowane komputery stacjonarne z systemem Windows przed uruchamianiem oprogramowania sklasyfikowanego przez program Windows Defender jako potencjalnie niechciane. Można chronić komputery przed uruchamianiem tych aplikacji lub używać trybu inspekcji, aby zgłaszać zdarzenia instalowania potencjalnie niechcianych aplikacji.
<!---TFS 1244478--->

## Dostęp warunkowy
**Zasady kontroli dostępu do sieci dla usługi Intune w produkcie Cisco ISE.**  Klienci korzystający z platformy Cisco Identity Service Engine (ISE) 2.1 i usługi Microsoft Intune mogą ustawić zasady kontroli dostępu do sieci w produkcie ISE.

W przypadku korzystania z tych zasad urządzenia, które łączą się z siecią przy użyciu sieci WiFi lub VPN, muszą spełniać następujące warunki przed udzieleniem im dostępu:

* być zarządzane przez usługę Intune,
* być zgodne z wdrożonymi zasadami zgodności usługi Intune.

Użytkownicy końcowi niezgodnych urządzeń będą otrzymywali monit o zarejestrowanie się i skorygowanie wszystkich problemów ze zgodnością w celu uzyskania dostępu.
<!---TFS 1299144--->

## Portal firmy
**Zmiany w kontach menedżerów rejestracji urządzeń w aplikacji Portal firmy dla systemu iOS.** Aby zwiększyć wydajność i skalę, usługa Intune nie pokazuje już wszystkich urządzeń menedżerów rejestracji urządzeń (DEM) w okienku Moje urządzenia aplikacji Portal firmy dla systemu iOS. Wyświetlane będzie tylko urządzenie lokalne, na którym uruchomiono aplikację, o ile zostało zarejestrowane przez aplikację Portal firmy. Użytkownik menedżera rejestracji urządzeń może wykonywać działania na urządzeniu lokalnym, ale zdalne zarządzanie innymi zarejestrowanymi urządzeniami można będzie wykonywać tylko z konsoli administracyjnej usługi Intune.  Dodatkowo w usłudze Intune wycofano używanie kont menedżera rejestracji urządzeń z programem Device Enrollment Program firmy Apple i narzędziem Apple Configurator. Obie te metody rejestracji obsługują już rejestrację bez użytkowników dla współużytkowanych urządzeń z systemem iOS. Kont menedżera rejestracji urządzeń należy używać tylko w przypadku braku dostępności rejestracji bez użytkowników dla współużytkowanych urządzeń.
<!---TFS 1233681--->

## Wycofywanie usług
**Aplikacje Portal firmy dla systemów Windows 8 i Windows Phone 8 będą wycofywane od września 2016 roku.** Począwszy od września 2016 roku w usłudze Microsoft Intune zakończy się obsługa aplikacji Portal firmy Microsoft Intune dla platform Windows Phone 8 i Windows 8. Zaktualizuj urządzenia do systemów Windows 8.1 i Windows Phone 8.1 oraz skorzystaj z odpowiedniej aplikacji Portal firmy dla systemu Windows 8.1 lub Windows Phone 8.1, aby kontynuować dystrybucję aplikacji na tych urządzeniach.
<!---TFS 1255391--->

**Usunięcie określania grup niestandardowych jako obiektów docelowych reguł powiadomień.**
Reguły powiadomień usługi Intune definiują, do kogo będą wysyłane alerty e-mail z usługi Intune. Obecnie można konfigurować reguły powiadomień w celu wysyłania wiadomości e-mail do wszystkich użytkowników urządzeń należących do utworzonej grupy urządzeń usługi Intune. Około 1 czerwca 2016 roku określanie grup utworzonych przez użytkownika jako docelowych przestanie być obsługiwane.

Wstępny plan dla tej zmiany jest następujący:
- W sierpniu 2016 roku nowi dzierżawcy nie będą widzieć drugiego kroku Kreatora tworzenia reguł powiadomień. Nie dotyczy to jednak istniejących dzierżawców.
- W okolicach września 2016 roku niektórzy istniejący dzierżawcy nie będą widzieć kroku „Wybierz grupy urządzeń” w kreatorze.
- Przewidujemy, że krok „Wybierz grupy urządzeń” w kreatorze przestanie być widoczny dla wszystkich dzierżawców w okolicach listopada 2016 roku.
<!---   TFS 1278864--->

**Zmiany w obsłudze aplikacji Portal firmy dla systemu iOS.**
W lipcu wszyscy użytkownicy aplikacji Portal firmy usługi Microsoft Intune dla systemu iOS będą musieli używać jej najnowszej wersji. Nowi użytkownicy będą mogli pobrać tylko najnowszą wersję, a bieżący użytkownicy będą musieli przeprowadzić aktualizację do najnowszej wersji. Najnowsza wersja aplikacji wymaga systemu iOS 8.0 lub nowszego, dlatego urządzenia ze starszymi wersjami systemu iOS nie będą mogły korzystać z portalu firmy ani rejestrować się do czasu ich zaktualizowania do systemu iOS 8.0 lub nowszego oraz zaktualizowania aplikacji Portal firmy do najnowszej wersji. Zarejestrowane urządzenia z wersjami systemu iOS poniżej 8.0 będą nadal zarządzane i wyświetlane w konsoli administracyjnej usługi Intune.  

**Aplikacje Intune Viewer.** Wraz z wydaniem nowej aplikacji RMS sharing zostaną usunięte następujące aplikacje Intune Viewer, począwszy od sierpnia 2016 roku:
- Intune AV Viewer
- Intune PDF Viewer
- Intune Image Viewer dla systemu Android ze sklepu Google Play

Zalecamy, aby zamiast korzystania z aplikacji Intune Viewer używać nowej aplikacji do zarządzania prawami (RMS sharing) dla systemu Android, co pozwala na wdrożenie jednej aplikacji zamiast trzech osobnych aplikacji w celu bezpiecznego przeglądania plików firmy na urządzeniach z systemem Android. Dowiedz się więcej na temat aplikacji RMS sharing (za pomocą linku do dokumentacji).


### Zobacz także
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new-in-microsoft-intune.md).


<!--HONumber=Jun16_HO3-->


