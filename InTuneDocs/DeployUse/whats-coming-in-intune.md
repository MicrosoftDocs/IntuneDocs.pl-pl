---
title: "Wkrótce | Microsoft Intune"
description: 
keywords: 
author: Lindavr
manager: jeffgilb
ms.date: 07/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 35ee5d0c8898c95898c0527a623cf13c454387f2
ms.openlocfilehash: 831cec6cd0e02a94c1a3f67d4adf5a5dcbb01449


---

# Wkrótce w usłudze Microsoft Intune — lipiec
Te informacje są przekazywane pod rygorem umowy NDA w bardzo ograniczonym zakresie i mogą ulec zmianie. Niektóre funkcje wymienione w tym miejscu mogą nie być wdrożone na czas i zostać opóźnione do przyszłych wersji. Inne funkcje są testowane w wersji pilotażowej, aby zapewnić przygotowanie ich do użytku przez klientów. W przypadku pytań lub wątpliwości skontaktuj się ze swoim partnerem ds. usługi Intune/PM.

Ta strona jest okresowo aktualizowana. Odwiedź ją ponownie, aby sprawdzić informacje na temat nadchodzących aktualizacji.

Dla usługi Intune opracowywane są następujące zmiany. Wszystkie te funkcje będą również w przyszłości obsługiwane dla hybrydowych wdrożeń klientów (program Configuration Manager z usługą Intune). Aby uzyskać więcej informacji na temat nowych funkcji hybrydowych, odwiedź stronę [Co nowego w funkcjach hybrydowych](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).


## Zarządzanie aplikacjami
### Poprawa aktualizowania profilu aprowizacji aplikacji
Biznesowe aplikacje mobilne systemu Apple iOS są tworzone za pomocą dołączonego profilu aprowizacji, a ich kod jest podpisywany przy użyciu certyfikatu. Gdy aplikacja jest uruchamiana na urządzeniu z systemem iOS, system iOS potwierdza integralność aplikacji systemu iOS i wymusza zasady zdefiniowane przez profil aprowizacji.

Certyfikat podpisywania przedsiębiorstwa używany do podpisywania aplikacji jest zwykle ważny przez 3 lata. Profil aprowizacji wygasa jednak po 1 roku. Dzięki tej aktualizacji usługa Intune udostępnia narzędzia umożliwiające aktywne wdrażanie nowych zasad profilu aprowizacji na urządzeniach, na których znajdują się aplikacje bliskie wygaśnięcia, ale certyfikat jest nadal ważny.
<!--- TFS 1280247--->

### Obsługa platformy Xamarin
Zestaw SDK aplikacji usługi Microsoft Intune będzie obsługiwać aplikacje platformy Xamarin w następujących scenariuszach:

- Tworzenie nowych aplikacji oraz modyfikowanie kodu istniejących aplikacji biznesowych przy użyciu zestawu SDK usługi Intune. Wtyczka będzie dostępna na [stronie usługi Microsoft Intune w serwisie Github](https://github.com/msintuneappsdk).
- Dodanie obsługi zarządzania aplikacjami mobilnymi do istniejących aplikacji biznesowych przy użyciu narzędzia opakowującego aplikacje usługi Intune

Aby łatwiej wybrać metodę do zastosowania, zobacz [Wybieranie sposobu przygotowania aplikacji do zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune).

<!--- TFS 1061478 & TFS 1152340--->

## Zarządzanie urządzeniami
### Zwiększenie limitów rejestracji urządzeń
Usługa Intune zwiększy maksymalny limit rejestracji konfigurowalnych urządzeń z 5 na 15 urządzeń dla każdego użytkownika.
<!---TFS 1289896 --->

## Zarządzanie grupami
### Przejście grup usługi Intune do grup usługi Azure Active Directory rozpocznie się w sierpniu 2016
Usługa Intune wprowadza nową funkcjonalność zarządzania grupami, która używa grup zabezpieczeń usługi Azure Active Directory (AAD) jako grupy użytkowników i urządzeń w usłudze Intune. Te grupy będą używane do zarządzania grupami, wdrażania zasad i wdrażania profilów **po wprowadzeniu nowego portalu administracyjnego usługi Intune używającej platformy Azure**.

Nowe środowisko zlikwiduje konieczność duplikowania grup między usługami, **pozwoli na dostęp do nowych funkcji grup usługi Azure Active Directory Premium (AADP)** i zapewni możliwość rozszerzenia przy użyciu programów PowerShell i Graph. Ujednolici to również środowisko administrowania grupami w zarządzaniu mobilnością w przedsiębiorstwie.

W celu umożliwienia przejścia do grup zabezpieczeń środowisko **bieżącej konsoli administracyjnej** zostanie zmodyfikowane. **Te zmiany i sposób korzystania z grup zabezpieczeń usługi AAD zostaną zarejestrowane w dokumentacji usługi Intune**.

Nowi klienci usługi Intune zobaczą **zmiany grup zabezpieczeń przed bieżącymi dzierżawcami**.

Oprócz zmian w zarządzaniu grupami **zostaną wycofane następujące funkcje**:
- Wykluczanie członków lub grup podczas tworzenia nowej grupy
- Zarządzanie grupami w roli administratora usługi
- Niestandardowe alerty bazujące na grupach dla reguł powiadomień
- Przestawianie z grupami w raportach


## Portal firmy

### Dodanie obszaru „Powiadomienia” do Portalu firmy dla systemu Android
W sierpniu udostępnimy aktualizację Portalu firmy dla systemu Android, która wprowadzi nową ikonę **Powiadomienia** na stronie głównej. Naciśnięcie tej ikony spowoduje przejście na stronę **Powiadomienia**, która przedstawia użytkownikowi końcowemu wszystkie elementy, które wymagają uwagi w aplikacji Portal firmy, takie jak brak zgodności urządzeń, aktualizacja rejestracji i aktywacja rejestracji. Jeśli używasz również aplikacji Portal firmy dla systemu iOS, powiadomienia masz już widoczne. Wraz z wprowadzeniem strony **Powiadomienia** nie będzie widoczna strona **Konfigurowanie dostępu do zasobów firmy** po uruchomieniu lub wznowieniu pracy w Portalu firmy dla systemu Android, jeśli urządzenie zostało już zarejestrowane. Wiemy, że wiele osób utworzyło wskazówki dla użytkowników końcowych i doceniają wcześniejsze powiadomienie, gdy wskazówki lub zrzuty ekranu mogą wymagać aktualizacji. Prosimy więc o takie zaktualizowanie dokumentacji, aby odzwierciedlała ona nadchodzące zmiany w środowisku. Zaktualizowano zrzuty ekranu można znaleźć tutaj: https://aka.ms/androidcpupdate  

### Pomaganie użytkownikom w rozwiązaniu problemów z rejestracją, gdy działanie narzędzia Workplace Join kończy się niepowodzeniem
Jeśli korzystasz z dostępu warunkowego, kroki rejestracji dla systemów Windows 8.1, Windows 10 Desktop i Windows 10 Mobile zostały uproszczone w witrynie internetowej Portalu firmy dla użytkowników końcowych, którzy napotkali błąd narzędzia Workplace Join (WPJ). Wcześniej, gdy użytkownik końcowy próbował zarejestrować urządzenie i użyć narzędzia WPJ, po czym rejestracja kończyła się pomyślnie, ale działanie narzędzia WPJ kończyło się niepowodzeniem, zarejestrowane urządzenie nie było wyświetlane na liście urządzeń do zidentyfikowania przez użytkowników, co było mylące. Użytkownicy zobaczą teraz osobne kroki „Rejestrowanie urządzeń” i „Workplace Join”, co ułatwi sprawdzenie stanu urządzenia i ukończenie procesu po niepowodzeniu narzędzia WPJ. Oddzielne kroki powinny również uprościć proces rozwiązywania problemów dla administratorów IT.

### Zmiany w kontach menedżerów rejestracji urządzeń w aplikacji Portal firmy dla systemu iOS
Aby zwiększyć wydajność i skalę, usługa Intune nie pokazuje już wszystkich urządzeń menedżerów rejestracji urządzeń (DEM) w okienku Moje urządzenia aplikacji Portal firmy dla systemu iOS. Wyświetlane będzie tylko urządzenie lokalne, na którym uruchomiono aplikację, o ile zostało zarejestrowane przez aplikację Portal firmy. Użytkownik menedżera rejestracji urządzeń może wykonywać działania na urządzeniu lokalnym, ale zdalne zarządzanie innymi zarejestrowanymi urządzeniami można będzie wykonywać tylko z konsoli administracyjnej usługi Intune.  Dodatkowo w usłudze Intune wycofano używanie kont menedżera rejestracji urządzeń z programem Device Enrollment Program firmy Apple i narzędziem Apple Configurator. Obie te metody rejestracji obsługują już rejestrację bez użytkowników dla współużytkowanych urządzeń z systemem iOS. Kont menedżera rejestracji urządzeń należy używać tylko w przypadku braku dostępności rejestracji bez użytkowników dla współużytkowanych urządzeń.
<!---TFS 1233681--->
### Ograniczenie instalacji aplikacji ładowanych bezpośrednio do zarejestrowanych urządzeń z systemem Android
Na urządzeniach z systemem Android nie można już instalować aplikacji za pośrednictwem witryny internetowej Portalu firmy, chyba że zostały zarejestrowane w usłudze Intune przy użyciu aplikacji Portal firmy usługi Intune dla systemu Android. 
<!---TFS 1299082--->

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



<!--HONumber=Jul16_HO3-->


