---
title: Akcje i opcje usługi Intune obsługiwane przez rejestrację użytkowników firmy Apple
titleSuffix: Microsoft Intune
description: Zapoznaj się z akcjami i opcjami usługi Intune obsługiwanymi przez rejestrację użytkowników firmy Apple
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/2/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 96c802e76aab673aa6a9108dc0a14f553c26b96b
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72505404"
---
# <a name="intune-actions-and-options-supported-with-apple-user-enrollment"></a>Akcje i opcje usługi Intune obsługiwane przez rejestrację użytkowników firmy Apple

Rejestracja użytkownika obsługuje podzestaw opcji zarządzania urządzeniami. Jeśli wstępnie istniejący profil konfiguracji zostanie zastosowany do urządzenia z rejestracją użytkowników, na tym urządzeniu będą stosowane tylko ustawienia obsługiwane przez rejestrację użytkowników.

## <a name="password-settings"></a>Ustawienia hasła

W przypadku skonfigurowania dowolnego ustawienia hasła na urządzeniach z rejestracją użytkowników ustawienia w obszarze **Proste hasła** są automatycznie ustawiane na wartość **Blokuj** i jest wymuszany 6-cyfrowy numer PIN.

Można na przykład skonfigurować ustawienie **Wygaśnięcie hasła** i wypchnąć te zasady do urządzeń zarejestrowanych przez użytkownika. Na urządzeniach występują następujące zdarzenia:
- Ustawienie **Wygaśnięcie hasła** jest ignorowane.
- Proste hasła, takie jak `1111` lub `1234`, nie są dozwolone.
- 6-cyfrowy numer PIN jest wymuszany.

## <a name="administrator-remote-device-actions-and-options"></a>Zdalne akcje i opcje administratora dotyczące urządzenia
Administratorzy mogą wykonywać następujące akcje i używać następujących opcji na urządzeniach z rejestracją użytkowników:
- Wycofaj
- Usuwanie
- Zdalne blokowanie
- Synchronizuj

Żadne inne akcje nie są obsługiwane.

## <a name="end-user-actions"></a>Akcje użytkownika końcowego
Na urządzeniach z rejestracją użytkowników użytkownicy końcowi mogą wykonywać następujące akcje z poziomu aplikacji i witryny internetowej Portal firmy:
- Zmienianie nazwy. Ta akcja dotyczy tylko nazwy użytkownika w Portalu firmy. Nie będzie ona powodować całkowitej zmiany nazwy urządzenia poza tym kontekstem.
- Usuń
- Zdalne blokowanie
- Sprawdzanie stanu

## <a name="other-supported-options"></a>Inne obsługiwane opcje

Następujące opcje są obsługiwane w usłudze Intune dla urządzeń zarejestrowanych przy użyciu funkcji rejestracji użytkowników firmy Apple:
- Sieć VPN dla aplikacji. Z tej opcji obsługi są wykluczone domeny przeglądarki Safari, ponieważ rejestracja użytkowników nie obsługuje konfigurowania ustawień tej przeglądarki.
- Sieć Wi-Fi 
- Usuwanie aplikacji firmowych po wyrejestrowaniu
- Wdrażanie aplikacji za pomocą planu zakupów zbiorczych (VPP) dla użytkowników z licencjami
- Wykrywanie zdjęcia zabezpieczeń systemu

Obsługiwane są następujące ograniczenia:
- Wyświetlanie dokumentów firmowych w aplikacjach niezarządzanych
- Wyświetlanie dokumentów innych niż firmowe w aplikacjach firmowych
- Zezwalanie aplikacjom niezarządzanym na odczytywanie z kont kontaktów zarządzanych
- Usługa AirDrop jako niezarządzane miejsce docelowe
- Wymagana zaszyfrowania kopia zapasowa
- Synchronizacja aplikacji zarządzanych z chmurą
- Dostęp do centrum sterowania po zablokowaniu urządzenia
- Dostęp do centrum powiadomień po zablokowaniu urządzenia
- Widok Dzisiaj, gdy urządzenie jest zablokowane
- Blokowanie zrzutów ekranu
- Blokowanie tworzenia kopii zapasowych książek przedsiębiorstwa
- Blokowanie synchronizacji metadanych książek przedsiębiorstwa
- Wymagaj zaszyfrowanej kopii zapasowej
- Wymaganie wykrywania nadgarstka w zegarku
- Blokowanie programu Siri
- Blokowanie programu Siri po zablokowaniu urządzenia
- Ostrzeżenia o oszustwach w przeglądarce Safari
- Blokowanie przesyłania diagnostyki do firmy Apple


## <a name="options-not-supported"></a>Opcje nieobsługiwane
Następujące opcje nie są obsługiwane na urządzeniach zarejestrowanych przy użyciu funkcji rejestracji użytkowników. Jeśli potrzebujesz tych opcji, zapoznaj się z tematem dotyczącym rejestracji urządzeń należących do użytkownika lub automatycznej rejestracji urządzeń firmowych.
- Zbieranie danych spisu aplikacji dla aplikacji poza zarządzanym woluminem APFS.
- Zbieranie danych spisu certyfikatów i profilów aprowizacji poza zarządzanym woluminem APFS.
- Zbieranie identyfikatorów UDID i innych trwałych identyfikatorów urządzeń.
- Rejestracja użytkowników obsługuje unikatowy identyfikator rejestracji dla każdego zarejestrowanego urządzenia, ale ten identyfikator nie jest utrwalany po wyrejestrowaniu.
- Następujące funkcje usługi Intune nie są obsługiwane z powodu tego ograniczenia:
- Profile użytkowników protokołu SCEP z nazwą podmiotu w formacie numeru seryjnego.
- Sieć VPN na poziomie urządzenia.
- Wdrożenie aplikacji programu VPP licencjonowanej w urządzeniu.
- Kontrola MDM aplikacji poza zarządzanym woluminem APFS.
- Zasady ochrony aplikacji nadal będą stosowane do tych aplikacji. Nie będzie można jednak przejąć zarządzania ani wdrożyć zarządzanej wersji tych aplikacji, chyba że użytkownik usunie je z urządzenia.
- Akcje, konfiguracje, ustawienia i polecenia wymagające nadzoru. 

## <a name="next-steps"></a>Następne kroki

[Konfigurowanie rejestracji użytkowników w systemach iOS oraz iPadOS](ios-user-enrollment.md)