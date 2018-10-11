---
title: Ustawienia kiosku systemu Android w usłudze Microsoft Intune — platforma Azure | Microsoft Docs
description: Skonfiguruj urządzenia kiosku rozwiązania Android enterprise.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 9/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f49e0bc496f176434577d42d3a372fc4e8bc22d3
ms.sourcegitcommit: 7063072c94e43aefc6be0072780622a1da8485d5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46119107"
---
# <a name="android-enterprise-kiosk-settings-in-intune"></a>Ustawienia kiosku rozwiązania Android enterprise w usłudze Intune

Profile kiosku systemu Android obsługują następujące ustawienia konfiguracji. Podczas tworzenia profilu te ustawienia są wyświetlane po wybraniu pozycji **Typ profilu** > **Tylko właściciel urządzenia** > **Ograniczenia dotyczące urządzeń**. Aby wyświetlić te ustawienia, wybierz pozycję **Właściwości** z profilu ograniczeń dotyczących urządzeń z rozwiązaniem Android enterprise, a następnie wybierz pozycję **Konfiguruj**.

## <a name="general-settings"></a>Ustawienia ogólne

- **Przechwytywanie ekranu**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom przechwytywanie ekranu urządzenia.
- **Aparat fotograficzny**: wybierz pozycję **Blokuj**, aby wyłączyć aparat fotograficzny urządzenia.
- **Domyślne zasady uprawnień**: to ustawienie określa domyślne zasady uprawnień dla żądań uprawnień w środowisku uruchomieniowym. Dopuszczalne wartości to:
    - **Ustawienie domyślne urządzenia**: użyte zostaną ustawienia domyślne urządzenia.
    - **Monituj**: użytkownik jest monitowany o zatwierdzenie uprawnień.
    - **Automatycznie udzielaj**: uprawnienia są automatycznie udzielane.
    - **Automatycznie odmawiaj**: uprawnienia są automatycznie odrzucane.
- **Zmiany głośności**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom zmienianie głośności urządzenia.
- **Wyczyść**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom wyczyszczenie urządzenia.
- **Bezpieczny rozruch**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom ponowne uruchamianie urządzenia w trybie awaryjnym.
- **Pasek stanu**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom dostęp do paska stanu, w tym powiadomień i szybkich ustawień.
- **Zmiany ustawień sieci Wi-Fi**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom zmienianie konfiguracji sieci Wi-Fi utworzonych przez właściciela urządzenia. Użytkownicy mogą tworzyć własne konfiguracje sieci Wi-Fi.
- **Konfiguracja punktu dostępu sieci Wi-Fi**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom tworzenie i edytowanie jakichkolwiek konfiguracji sieci Wi-Fi.
- **Funkcje debugowania**: wybierz pozycję **Zezwalaj**, aby umożliwić użytkownikom korzystanie z funkcji debugowania.
- **Dostosowanie mikrofonu**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom dostosowywanie głośności i wyciszanie mikrofonu.
- **Adresy e-mail na potrzeby ochrony funkcji czyszczenia**: wybierz pozycję **Adresy e-mail konta Google**, aby określić adresy e-mail (oddzielane średnikami), za pomocą których można odblokować urządzenie po przeprowadzeniu czyszczenia. Jeśli adres e-mail nie zostanie określony, każda osoba może odblokować urządzenie po przeprowadzeniu czyszczenia.
- **Wyjście bezpieczeństwa sieci**: wybierz pozycję **Włącz**, aby włączyć funkcję wyjścia bezpieczeństwa sieci. Jeśli podczas rozruchu nie można nawiązać połączenia sieciowego, funkcja wyjścia bezpieczeństwa wyświetla użytkownikowi monit o nawiązanie tymczasowego połączenia z siecią w celu odświeżenia zasad urządzenia. Po zastosowaniu zasad sieć tymczasowa zostanie zapomniana, a urządzenie będzie kontynuować rozruch. Umożliwia to nawiązanie połączenia z siecią, gdy w ramach ostatnich zasad nie istnieje odpowiednia sieć, a urządzenie jest uruchamiane w aplikacji w trybie blokady zadania lub użytkownik nie może uzyskać dostępu do ustawień urządzenia.
- **Zezwalaj na instalację z nieznanych źródeł**: wybierz pozycję **Zezwalaj**, aby umożliwić użytkownikom przeprowadzanie instalacji z nieznanych źródeł.
- **Aktualizacja systemu**: wybierz opcję, aby określić sposób obsługi aktualizacji bezprzewodowych przez urządzenie:
    - **Ustawienie domyślne urządzenia**: użyte zostaną ustawienia domyślne urządzenia.
    - **Automatyczne**: aktualizacje są automatycznie instalowane bez interakcji z użytkownikiem. Ustawienie tych zasad powoduje natychmiastowe instalowanie wszystkich oczekujących aktualizacji.
    - **Odłożone**: instalowanie aktualizacji jest odkładane o 30 dni. Po upływie tych 30 dni system Android monituje użytkownika o zainstalowanie aktualizacji. Producenci urządzeń i operatorzy mogą uniemożliwiać (wykluczać) odkładanie ważnych aktualizacji zabezpieczeń. Aktualizacja podlegająca takiemu wykluczeniu powoduje wyświetlenie użytkownikowi powiadomienia systemowego na urządzeniu. 
    - **Okno obsługi**: aktualizacje są instalowane automatycznie w ramach codziennego okna obsługi skonfigurowanego w usłudze Intune. Próba zainstalowania jest podejmowana codziennie przez 30 dni i może zakończyć się niepowodzeniem ze względu na brak miejsca lub niski poziom baterii. Po upływie 30 dni system Android monituje użytkownika o zainstalowanie. To okno jest też używane do instalowania aktualizacji aplikacji ze sklepu Play. Ta opcja jest zalecana w przypadku urządzeń dedykowanych, takich jak kioski, ponieważ umożliwia aktualizowanie aplikacji na pierwszym planie kiosków z pojedynczymi aplikacjami. 

## <a name="kiosk-settings"></a>Ustawienia kiosku

- **Tryb kiosku**: określa, czy na urządzeniu można uruchamiać tylko jedną aplikację, czy wiele aplikacji. Aby uzyskać więcej informacji, zobacz [Ustawienia kiosku dla urządzeń z systemem Android](android-kiosk-settings.md).
    - **Kiosk z pojedynczą aplikacją**: użytkownicy mogą uzyskiwać dostęp tylko do jednej aplikacji.
    - **Kiosk z wieloma aplikacjami**: użytkownicy mogą uzyskiwać dostęp do ograniczonego zestawu aplikacji.

## <a name="device-password-settings"></a>Ustawienia haseł urządzeń

- **Blokada klawiatury**: wybierz pozycję **Wyłącz**, aby uniemożliwić użytkownikom używanie funkcji blokady klawiatury na urządzeniu.
- **Wymagany typ hasła**: określ typ hasła wymagany dla urządzenia.
- **Minimalna długość hasła**: określ minimalną długość hasła wymaganą dla urządzenia.
- **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia**: określ liczbę dopuszczalnych nieudanych logowań przed wyczyszczeniem urządzenia.

## <a name="power-settings"></a>Ustawienia zasilania

- **Czas do zablokowania ekranu**: ustaw okres bezczynności przed zablokowaniem urządzenia.
- **Włączony ekran, gdy urządzenie jest podłączone**: wybierz źródła zasilania. Jeśli urządzenie będzie podłączone do jednego z nich, ekran urządzenia będzie włączony.

## <a name="users-and-accounts-settings"></a>Ustawienia użytkowników i kont

- **Dodawanie nowych użytkowników**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom dodawanie nowych użytkowników.
- **Usuwanie użytkowników**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom usuwanie użytkowników.
- **Zmiany dotyczące konta**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom modyfikowanie kont.

## <a name="next-steps"></a>Następne kroki
[Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).



