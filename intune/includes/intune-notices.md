---
title: dołączanie pliku
description: dołączanie pliku
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: 073115d33f9a4f22fe3706ef15860c2a8d8a68ee
ms.sourcegitcommit: 69aaf89140f82f344404e75a69dc59d8a1585b10
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 03/30/2019
ms.locfileid: "58675497"
---
Te powiadomienia zawierają ważne informacje, które mogą ułatwić przygotowanie nadchodzących zmianach w usłudze Intune i funkcji. 

### <a name="change-in-enrollment-workflow-with-intune-company-portal-on-corporate-ios-devices-authenticating-with-setup-assistant----1927359---"></a>Zmiany w przepływie pracy rejestracji z portalu firmy usługi Intune na urządzeniach firmowych z systemem iOS z uwierzytelniania przy użyciu Asystenta ustawień <!-- 1927359 -->
Ma ona nadchodzące zmiany w przepływie pracy na potrzeby rejestracji urządzeń z systemem iOS za pomocą jednego metod firmy Apple urządzeń firmowych rejestracji — programu Apple Configurator, kierownika firmy Apple, Apple School Manager lub Apple Device Enrollment Program (DEP), gdy za pomocą Instalatora Asystenta ustawień dla uwierzytelniania. Ta zmiana dotyczy tylko urządzeń przenośnych zarejestrowanych za pomocą koligacji użytkownika.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Po wprowadzeniu tej zmiany w ~~marcu~~ kwietniu profile rejestracji w usłudze Intune w witrynie Azure Portal zostaną zaktualizowane, tak aby określić sposób uwierzytelniania urządzeń oraz wskazać, czy otrzymują aplikację Portal firmy. Będzie ulepszony przepływ pracy, aby zarejestrować urządzenia z systemem iOS za pomocą metod wymienionych powyżej. 

- Podczas rejestrowania nowych urządzeń i uwierzytelniania przy użyciu Asystenta ustawień, można wybrać, czy automatycznie wdrożyć aplikację portalu firmy. Użytkownicy końcowi zobaczą już na ekranie "Identyfikacji urządzenia" i "Potwierdź urządzenia" ekranu w procesie rejestracji.  
- Na urządzeniach, które już zarejestrowane za pośrednictwem Asystenta ustawień za pomocą jednej z metod rejestracji urządzeń firmowych firmy Apple należy podjąć odpowiednie działania, jeśli chcesz włączyć dostęp warunkowy. Musisz skonfigurować zasady konfiguracji aplikacji za pomocą określonego xml do wypychania aplikacji Portal firmy do tych urządzeń. W tym celu rosną wpis w blogu w linku dodatkowe informacje. Jeśli zdecydujesz się wypychanie aplikacji Portal firmy w taki sposób, użytkownicy końcowi zobaczą już na ekranie "Identyfikacji urządzenia" i "Potwierdź urządzenia" ekranu w usłudze flow rejestracji 
- Po tej zmiany jest wdrażana, jeśli nie zostały wdrożone portalu firmy przy użyciu profilu konfiguracji aplikacji wymienionych powyżej i jeśli pobieranie użytkowników końcowych w aplikacji Portal firmy z aplikacji są przechowywane, mógł się zalogować, ale zostanie wyświetlony komunikat o błędzie. Nie będą mogli korzystać z aplikacji dla dostępu warunkowego. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?
Jeśli planujesz użycie zmodyfikowanego przepływu pracy, należy zaktualizować swoje wskazówki użytkowników końcowych w celu wskazania, że:

- Użytkownicy końcowi będą widzieli już dwa ekrany, które podano powyżej w procedurę rejestracji. 
- One musisz zalogować się do portalu firmy, gdy aplikacja jest wdrożona automatycznie, a nie pobierać je ze sklepu z aplikacjami. 

Można teraz utworzyć zasady konfiguracji aplikacji, jeśli to konieczne, w ramach przygotowania do tej zmiany. Ten nowy przepływ pracy można zaobserwować zobaczysz profile rejestracji zaktualizowane w konsoli. Firma Microsoft będzie również informują o wdrożenia za pośrednictwem Centrum wiadomości. Po tym należy podjąć działania, dzięki czemu użytkownicy końcowi mogą rejestrować za pomocą programu DEP przy użyciu Asystenta ustawień i aplikacji Portal firmy można użyć dla dostępu warunkowego.

Zobacz nasz blog pomocy technicznej, napisz linku dodatkowe informacje, aby uzyskać więcej informacji na temat tej zmiany.

#### <a name="additional-information"></a>Dodatkowe informacje 
[https://aka.ms/enrollment_setup_assistant](https://aka.ms/enrollment_setup_assistant)

### <a name="plan-for-change-user-experience-update-to-intune-company-portal-app-for-ios"></a>Planowanie zmian: aktualizacja środowiska użytkownika aplikacji Portal firmy usługi Intune dla systemu iOS
Z radością informujemy, że w usłudze Intune wkrótce zostanie udostępniona znacząca aktualizacja środowiska obsługi użytkownika aplikacji Portal firmy dla systemu iOS. Aktualizacja będzie zawierała wizualne zmiany strony głównej, na której zostaną dodane zaawansowane filtry i szybszy dostęp do aplikacji i książek.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Ta aktualizacja środowiska użytkownika nie zmieni bieżącej funkcjonalności aplikacji Portal firmy dla systemu iOS, będzie natomiast zawierać następujące elementy:
- Strona główna o wyglądzie i działaniu natywnym dla systemu iOS 
- Funkcje filtrowania list zawartości i wyszukiwania z uwzględnieniem możliwości filtrowania według typu zawartości (aplikacje lub książki elektroniczne) oraz dostępności (zarządzanie urządzeniem wymagane lub dostępne bez rejestracji)
- Możliwość wyszukiwania książek elektronicznych
- Historia wyszukiwania dla aplikacji i książek elektronicznych

Jeśli bierzesz udział w programie Apple TestFlight, otrzymasz powiadomienie o wstępnej wersji zaktualizowanej aplikacji Portal firmy usługi Intune dla systemu iOS, gdy będzie dostępna. Jeśli nie bierzesz udziału w programie Apple TestFlight, nie jest za późno, aby się zarejestrować. Rejestracja umożliwi korzystanie ze zaktualizowanej aplikacji Portal firmy, zanim będzie ona dostępna dla Twoich użytkowników końcowych. Możesz również przekazywać opinie z zespołem usługi Intune.  

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Co zrobić, aby przygotować się do tej zmiany?
Nie trzeba podejmować żadnych działań, te zmiany zostaną wprowadzone w nadchodzącym wydaniu aplikacji Portal firmy dla systemu iOS. 

#### <a name="additional-information"></a>Dodatkowe informacje
[https://aka.ms/cp_update_iOS](https://aka.ms/cp_update_iOS)

### <a name="check-your-delay-visibility-of-software-updates-setting-in-intune"></a>Sprawdź ustawienia "Opóźnienie widoczność aktualizacji oprogramowania" w usłudze Intune 

Firma Microsoft jest udostępniane w MC171466, który możemy zostały poruszania się kilka ustawień w konsoli. Za pomocą Marcowa aktualizacja usługi Intune całkowicie usuniemy ustawienie "Aktualizacje opóźnienie widoczność oprogramowania" w bloku zasad aktualizacji systemu iOS. Nie spowoduje to zmianę sposobu zastosowania Twoje zaplanowane aktualizacje oprogramowania, ale może wpływać na czas opóźnienia widoczność aktualizacji dla użytkowników końcowych. Może być konieczne podejmij działanie przed końcem marca, jeśli używasz tego ustawienia. 

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Po aktualizacji usługa Intune lutego zauważysz, że ustawienie jest wyświetlane w profilów ograniczeń dotyczących urządzeń w konsoli, a w systemie iOS aktualizacji zasad w bloku aktualizacji oprogramowania. Po wyświetleniu tej zmiany zostaną uwzględnione w konsoli Oto, co trzeba zrobić.

- Dla istniejącej zasady aktualizacji systemu iOS: w przypadku niestandardowych skonfigurować tego ustawienia, aby coś innego niż domyślny 30 dni i chcesz istniejącej konfiguracji dla ustawień widoczności opóźnienia kontynuować stosowanie po zakończeniu marca, musisz utworzyć nowy Profil ograniczeń urządzenia z systemem iOS. W tym miejscu ustawienie widoczności opóźnienie musisz mieć takie same wartości jak istniejące zasady aktualizacji systemu iOS i przeznaczone do tych samych grup. Po Marcowa aktualizacja usługi nie będzie już można edytować wartości dla tego ustawienia w istniejących zasad aktualizacji systemu iOS, ponieważ już nie będą widoczne w tym bloku. Zamiast tego zostanie skonfigurowane ustawienie w nowych profilów.
  Jeśli wartość przez liczbę dni można opóźnić widoczność nie jest zgodny w obu lokalizacjach, w przypadku wartości niestandardowe skonfigurowane ustawienie widoczności opóźnienia, ustawienie nie będzie działać, i użytkownicy końcowi będą widzieli aktualizacji na swoich urządzeniach, jak jest ona dostępna. Może to mieć znaczenie minimalne dla większości klientów, ponieważ inne ustawienia w bloku zasad aktualizacji oprogramowania zawsze miały pierwszeństwo za pośrednictwem tego ustawienia w konsoli.
- Aby uzyskać nowe zasady aktualizacji systemu iOS: Jeśli spróbujesz utworzyć nowe zasady w bloku aktualizacji oprogramowania po aktualizacji usługa Intune lutego, zostanie wyświetlony, to ustawienie, wygaszone out. Zobaczysz notatki w konsoli, przekierowywanie do bloku konfiguracji urządzenia, jeśli chcesz opóźnienie widoczność aktualizacji.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Co zrobić, aby przygotować się do tej zmiany?
Nie trzeba podjąć działania, jeśli nie używaj tego ustawienia, lub nie powinien być opóźnienie widoczność aktualizacji oprogramowania dla użytkowników końcowych.

W razie potrzeby opóźnienia widoczność aktualizacje rozpocząć konfigurowanie ustawienia w nowych profilów w bloku konfiguracji urządzenia w ramach ograniczenia dotyczące urządzeń > Ogólne. Jeśli masz to niestandardowe ustawienie skonfigurowane w systemie iOS istniejące zasady aktualizacji, utworzyć nowy profil ograniczeń urządzenia równoważne z taką samą wartość "dni" opóźnienia widoczność aktualizacji dla użytkowników, po lutym przed marca przedaktualizacyjnych i wprowadza. 

Możesz zaktualizować swoje wskazówki specjalistów IT i poinformuj techniczną.

Zobacz nasz blog pomocy technicznej, Opublikuj informacje dodatkowe, aby uzyskać szczegółowe informacje dotyczące sposobu konfigurowania tego ustawienia.

#### <a name="additional-information"></a>Dodatkowe informacje 
[https://aka.ms/Delay_visibility_setting_iOS](https://aka.ms/Delay_visibility_setting_iOS)

### <a name="plan-for-change-upcoming-fix-for-windows-10-email-profiles-in-intune---3904031--"></a>Planowanie zmian: planowanej poprawce dla profilów poczty e-mail w systemie Windows 10 w usłudze Intune <!--3904031-->
Aktualizujemy sposób, w jaki usługa Intune zapisuje wiadomość e-mail, które profile dla systemu Windows 10 w kwietniu aktualizacji do usługi Intune, aby naprawić błąd również, aby upewnić się, że Twoje profile poczty e-mail w dalszym ciągu działać w przyszłych wersjach systemu Windows 10. Brak akcji, którą należy wykonać po wdrożeniu tej poprawki.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Ta zmiana wpływa na, jeśli używasz profilów poczty e-mail systemu Windows 10 za pomocą
- Natywnego klienta poczty E-mail na komputerach stacjonarnych z systemem Windows 10 lub
- Klient poczty e-mail programu Outlook na Windows 10 Mobile

Ma to wpływ na obu autonomicznego i hybrydowego zarządzania urządzeniami przenośnymi (MDM) klientów usługi Intune.

Po aktualizacji kwietnia wprowadza, należy ponownie utworzyć te profile w konsoli usługi Intune (w konsoli administracyjnej programu Configuration Manager, jeśli korzystasz z hybrydowego zarządzania urządzeniami Przenośnymi).

Jeśli nie podejmiesz działania, Oto zobaczysz dla profilów utworzonych przed aktualizacją z kwietnia:

- Istniejące profile poczty e-mail będą widoczne w stan błędu w konsoli usługi Intune lub konsoli administracyjnej programu Configuration Manager, ale użytkownicy końcowi będą nadal mieć dostęp do poczty e-mail. Jednak po kolejnych aktualizacji Windows można zaobserwować te profile nie będzie działać. Użytkownicy końcowi na urządzeniach docelowych i związanych z tych profilów utraci dostęp do poczty e-mail.
- Zmiany wprowadzone do tych profilów po kwietnia nie zostaną odzwierciedlone w docelowe urządzenia.
- Selektywne czyszczenie danych nie będzie działać do usuwania tych profilów, nawet po zakończeniu poprawki jest udostępniona w kwietniu.

Jeśli podejmować działania i ponownie utworzyć profile poczty e-mail, użytkownicy końcowi będą musi przechodzić przez kroki podobne do tych po wdrożeniu profilu poczty e-mail po raz pierwszy. Wiadomości e-mail będzie zablokowany, synchronizowanie do momentu zaakceptowania aktualizację, która dotyczy nowy profil.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?
Należy podjąć działania, tylko wtedy, gdy poprawka jest wdrażana wraz z aktualizacją z kwietnia. Firma Microsoft będzie skontaktować się z Tobą za pośrednictwem Centrum wiadomości po tej zmianie przechodzi na żywo, aby można było zacząć ponownie utworzyć profilów w usłudze Intune.

Jeśli używasz profilów poczty e-mail w systemie Windows 10 w usłudze Intune, należy wykonać następujące czynności:

1. Przechwytywanie istniejących ustawień profilu w systemie Windows 10
2. Cofanie przypisania i/lub usuń istniejące profile
3. Tworzenie nowych profilów przy użyciu ustawień przechwycony i przypisać profile nowy do tych samych grup

Może być konieczne, Powiadom użytkowników końcowych i pozwól techniczną wiedzieć o tej zmianie. Zajrzyj do pomocy technicznej wpis w blogu informacje dodatkowe szczegóły błędu i instrukcje dotyczące ponownego tworzenia tych profilów.

#### <a name="additional-information"></a>Dodatkowe informacje
https://aka.ms/Win10EmailProfiles

