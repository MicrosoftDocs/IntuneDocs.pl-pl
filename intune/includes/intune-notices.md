---
ms.openlocfilehash: dc86f2c22410236368753acd4dd3b66698037241
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57736855"
---

Te powiadomienia zawierają ważne informacje, które mogą ułatwić przygotowanie nadchodzących zmianach w usłudze Intune i funkcji. 

### <a name="change-in-enrollment-workflow-with-intune-company-portal-on-corporate-ios-devices-authenticating-with-setup-assistant----1927359---"></a>Zmiany w przepływie pracy rejestracji z portalu firmy usługi Intune na urządzeniach firmowych z systemem iOS z uwierzytelniania przy użyciu Asystenta ustawień <!-- 1927359 -->
Ma ona nadchodzące zmiany w przepływie pracy na potrzeby rejestracji urządzeń z systemem iOS za pomocą jednego metod firmy Apple urządzeń firmowych rejestracji — programu Apple Configurator, kierownika firmy Apple, Apple School Manager lub Apple Device Enrollment Program (DEP), gdy za pomocą Instalatora Asystenta ustawień dla uwierzytelniania. Ta zmiana dotyczy tylko urządzeń przenośnych zarejestrowanych za pomocą koligacji użytkownika.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Po wprowadzeniu tej zmiany w ~~marcu~~ kwietniu profile rejestracji w usłudze Intune w witrynie Azure Portal zostaną zaktualizowane, tak aby określić sposób uwierzytelniania urządzeń oraz wskazać, czy otrzymują aplikację Portal firmy. Będzie ulepszony przepływ pracy, aby zarejestrować urządzenia z systemem iOS za pomocą metod wymienionych powyżej. Uwaga:

- Podczas rejestrowania nowych urządzeń i uwierzytelniania przy użyciu Asystenta ustawień, można wybrać, czy automatycznie wdrożyć aplikację portalu firmy. Użytkownicy końcowi zobaczą już na ekranie "Identyfikacji urządzenia" i "Potwierdź urządzenia" ekranu w procesie rejestracji.  
- Na urządzeniach, które już zarejestrowane za pośrednictwem Asystenta ustawień za pomocą jednej z metod rejestracji urządzeń firmowych firmy Apple należy podjąć odpowiednie działania, jeśli chcesz włączyć dostęp warunkowy. Musisz skonfigurować zasady konfiguracji aplikacji za pomocą określonego xml do wypychania aplikacji Portal firmy do tych urządzeń. W tym celu rosną wpis w blogu w linku dodatkowe informacje. Jeśli zdecydujesz się wypychanie aplikacji Portal firmy w taki sposób, użytkownicy końcowi zobaczą już na ekranie "Identyfikacji urządzenia" i "Potwierdź urządzenia" ekranu w usłudze flow rejestracji 
- Po tej zmiany jest wdrażana, jeśli nie zostały wdrożone portalu firmy przy użyciu profilu konfiguracji aplikacji wymienionych powyżej i jeśli pobieranie użytkowników końcowych w aplikacji Portal firmy z aplikacji są przechowywane, będzie mógł się zalogować, ale zostanie wyświetlony komunikat o błędzie. Nie będą mogli korzystać z aplikacji dla dostępu warunkowego. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?
Jeśli planujesz użycie zmodyfikowanego przepływu pracy, należy zaktualizować swoje wskazówki użytkowników końcowych w celu wskazania, że:

- Użytkownicy końcowi będą widzieli już dwa ekrany, które podano powyżej w procedurę rejestracji. 
- One musisz zalogować się do portalu firmy, gdy aplikacja jest wdrożona automatycznie, a nie pobierać je ze sklepu z aplikacjami. 

Można teraz utworzyć zasady konfiguracji aplikacji, jeśli to konieczne, w ramach przygotowania do tej zmiany. Ten nowy przepływ pracy można zaobserwować zobaczysz profile rejestracji zaktualizowane w konsoli. Firma Microsoft będzie również informują o wdrożenia za pośrednictwem Centrum wiadomości. Po tym należy podjąć działania, dzięki czemu użytkownicy końcowi mogą rejestrować za pomocą programu DEP przy użyciu Asystenta ustawień i aplikacji Portal firmy można użyć dla dostępu warunkowego.

Zobacz nasz blog pomocy technicznej, napisz linku dodatkowe informacje, aby uzyskać więcej informacji na temat tej zmiany.

#### <a name="additional-information"></a>Dodatkowe informacje 
[https://aka.ms/enrollment_setup_assistant](https://aka.ms/enrollment_setup_assistant)


### <a name="company-portal-changes-for-ios-122-enrollment-in-intune"></a>Zmiany portalu firmy dla systemu iOS 12.2 rejestracji w usłudze Intune
W komunikacie MC172534 poinformowaliśmy, że firma Apple ogłosiła pewne zmiany związane z rejestrowaniem urządzeń z systemem iOS w usługach zarządzania urządzeniami mobilnymi (MDM). Zmiana prawdopodobnie będzie widoczna w wersji dla systemu iOS w marca 2019 r, a także wszystkie wersje systemu iOS w przyszłości. Wprowadzamy niektórych aktualizacji w portalu firmy w celu odzwierciedlenia zmian firmy Apple. 
 
#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Jeśli użytkownicy końcowi uaktualnić swoje urządzenia z systemem iOS 12.2 i wyższych, należy wiedzieć, że istnieje modyfikacji przepływu pracy i ich należy wykonać dodatkowe kroki w celu ukończenia procesu rejestrowania w usłudze Intune. Marcowa aktualizacja usługi Intune w tym miejscu po ich będzie działania —  

- Rozpoczęcie procesu rejestracji w aplikacji Portal firmy, aby pobrać profil zarządzania
- Wybierz pozycję Ustawienia > Ogólne > Profile i zwróć uwagę na powiadomienie czerwony wskaźnika
- Wybierz prawidłowy profil i klikanie do instalacji
- Wróć do portalu firmy w celu ukończenia procesu rejestrowania

Kliknij informacje dodatkowe szczegółowe informacje na temat procedurę rejestracji.

Nie powinny mieć wpływ na chyba że są one wyrejestrowane i wymagają nowej rejestracji urządzenia, które zostały już zarejestrowane i przeprowadź uaktualnienie do systemu iOS 12.2 lub nowszym. Środowisko rejestracji na urządzeniach z systemem iOS 12.1 lub wcześniejszym nie zmieni się w tej nowej wersji firmy Apple. Nie będzie mieć wpływ na urządzenia zarejestrowane za pośrednictwem jednego lub metod rejestracji w firmie Apple (Device Enrollment Program, Apple School Manager lub kierownika firmy Apple).

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Co zrobić, aby przygotować się do tej zmiany?
Zaplanuj uaktualnienie dokumentacji i wskazówek dla użytkowników końcowych. Możesz również poinformować o tych zmianach dział pomocy technicznej. Będziemy informować Cię informować za pośrednictwem naszej co to jest nowa strona, gdy ta zmiana przechodzi na żywo. 

Jeśli chcesz korzystać z zalet wprowadzamy zmiany aplikacji Portal firmy, poproś użytkowników końcowych, aby zaktualizować urządzenie do nowej wersji systemu iOS, po usług Marcowa aktualizacja usługi Intune, kiedy wersja aplikacji 3.9.0 aplikacji Portal firmy. jest zwalniana.

Kliknij przycisk dodatkowe informacje dla wpisu w blogu pomocy technicznej ze zrzutami ekranu (wersja zapoznawcza), zmian w aplikacji Portal firmy.

Informacje dodatkowe [https://aka.ms/CP_changes_iOS12](https://aka.ms/CP_changes_iOS12)

### <a name="plan-for-change-workflow-changes-for-ios-12-enrollment-in-intune"></a>Planowanie zmian: przepływ pracy zmienia dla systemu iOS 12 rejestracji w usłudze Intune
Firma Apple ogłosiła pewne zmiany związane z rejestrowaniem urządzeń z systemem iOS w usługach zarządzania urządzeniami mobilnymi (MDM). Zmiana nastąpi prawdopodobnie w wersji systemu iOS z wiosny 2019 r i będzie obowiązywać we wszystkich przyszłych wersjach systemu iOS.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Jeśli użytkownicy końcowi uaktualnią swoje urządzenia do tej nowej wersji systemu iOS 12 na wiosnę, należy wiedzieć o zmodyfikowanym przepływie pracy i dodatkowych krokach, które będą musieli wykonać w celu ukończenia procesu rejestrowania w usłudze Intune. Kiedy Apple wprowadza te zmiany, użytkownicy końcowi będą mieć do:

- Rozpoczęcie procesu rejestracji w aplikacji Portal firmy, aby pobrać profil zarządzania
- Wybierz pozycję Ustawienia > Ogólne > Profile
- Wybierz prawidłowy profil i klikanie do instalacji
- Wróć do portalu firmy w celu ukończenia procesu rejestrowania 

Uaktualnienie do nowej wersji systemu iOS urządzeń, które są już zarejestrowane, nie będzie mieć na nie wpływu, chyba że zostaną wyrejestrowane i będą wymagać nowej rejestracji.

Środowisko rejestracji na urządzeniach z systemem iOS 12.1 lub wcześniejszym nie zmieni się w tej nowej wersji firmy Apple.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Co zrobić, aby przygotować się do tej zmiany?
Zaplanuj uaktualnienie dokumentacji i wskazówek dla użytkowników końcowych. Możesz również poinformować o tych zmianach dział pomocy technicznej. Poinformujemy Cię o wprowadzeniu tej zmiany w życie za pomocą Centrum wiadomości i strony Co nowego.

#### <a name="additional-information"></a>Dodatkowe informacje
[Obsługa zrzutów ekranu i wideo procedurę rejestracji oczekiwany wpis w blogu](https://aka.ms/iOS_enrollment_changes).

### <a name="plan-for-change-user-experience-update-to-intune-company-portal-app-for-ios"></a>Planowanie zmian: aktualizacja środowiska użytkownika aplikacji Portal firmy usługi Intune dla systemu iOS
Z radością informujemy, że w usłudze Intune wkrótce zostanie udostępniona znacząca aktualizacja środowiska obsługi użytkownika aplikacji Portal firmy dla systemu iOS. Aktualizacja będzie zawierała wizualne zmiany strony głównej, na której zostaną dodane zaawansowane filtry i szybszy dostęp do aplikacji i książek.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Ta aktualizacja środowiska użytkownika nie zmieni bieżącej funkcjonalności aplikacji Portal firmy dla systemu iOS, będzie natomiast zawierać następujące elementy:
- Strona główna o wyglądzie i działaniu natywnym dla systemu iOS 
- Funkcje filtrowania list zawartości i wyszukiwania z uwzględnieniem możliwości filtrowania według typu zawartości (aplikacje lub książki elektroniczne) oraz dostępności (zarządzanie urządzeniem wymagane lub dostępne bez rejestracji)
- Możliwość wyszukiwania książek elektronicznych
- Historia wyszukiwania dla aplikacji i książek elektronicznych

Jeśli bierzesz udział w programie Apple TestFlight, otrzymasz powiadomienie o wstępnej wersji zaktualizowanej aplikacji Portal firmy usługi Intune dla systemu iOS, gdy będzie dostępna. Jeśli nie bierzesz udziału w programie Apple TestFlight, nie jest za późno, aby się zarejestrować. Rejestracja umożliwi korzystanie ze zaktualizowanej aplikacji Portal firmy, zanim będzie ona dostępna dla Twoich użytkowników końcowych. Będzie można również przekazywać opinie z zespołem usługi Intune.  

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Co zrobić, aby przygotować się do tej zmiany?
Nie trzeba podejmować żadnych działań, te zmiany zostaną wprowadzone w nadchodzącym wydaniu aplikacji Portal firmy dla systemu iOS. 

#### <a name="additional-information"></a>Dodatkowe informacje
[https://aka.ms/cp_update_iOS](https://aka.ms/cp_update_iOS)


### <a name="reminder-removal-of-existing-exchange-online-to-intune-connectors----3105122---"></a>Przypomnienie: Usunięcie istniejącej usługi Exchange Online do usługi Intune łączników <!-- 3105122 -->
W MC165575 możemy udostępnić, aby firma Microsoft może usuwać Exchange Online funkcję łącznika usługi Intune "Service to Service" w nadchodzącej aktualizacji. Wraz z aktualizacją lutego do usługi Intune firma Microsoft będzie wyłączyć przycisk aby skonfigurować nowe łączniki. Planujemy usunąć wszystkie istniejące usługi Exchange Online do łączników usługi Intune w marca 2019 r.
 
#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Otrzymujesz tę wiadomość, ponieważ nasze rekordy wskazują, że używasz funkcji łącznika typu „usługa z usługą” w danym środowisku. Łącznik typu „usługa z usługą” obsługuje zarządzanie urządzeniami programu Exchange Active Sync Only w usłudze Intune dla usługi Exchange Online i nie obsługuje infrastruktury lokalnej. Ten łącznik — ze względu na sposób wyświetlania w konsoli — wydaje się być niezbędny w przypadku dostępu warunkowego, gdy w rzeczywistości nie jest potrzebny dla takiego dostępu. Może używano tego łącznika do zrozumienia użycia usługi Exchange Online przed zastosowaniem dostępu warunkowego. Te informacje są podawane przez Centrum administracyjnym usługi Microsoft 365. W tym miejscu znajdziesz udostępnia raporty użycia dla usługi Exchange Online w tym aplikacja typu używanych na potrzeby od 7 do 180 dni. Aby uzyskać więcej informacji, zobacz [Office 365 raportów w Centrum administracyjne — użycie aplikacji poczty E-mail](https://docs.microsoft.com/office365/admin/activity-reports/email-apps-usage?view=o365-worldwide).  
 
Jeśli używasz tego łącznika w swoim środowisku, nie będziesz mieć możliwości monitorowania ani czyszczenia urządzeń programu Exchange Active Sync Only w usłudze Intune po wyłączeniu łączników w lutym. Nie przewidujemy, aby ta zmiana miała wpływ na użytkowników końcowych.
 
#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Co zrobić, aby przygotować się do tej zmiany?
Jeśli masz skonfigurowany łącznik typu „usługa z usługą” i masz urządzenia programu Exchange Active Sync Only, przełącz się do innych metod zarządzania urządzeniami. Do wyboru są następujące opcje:

- Zarejestrowanie urządzeń w rozwiązaniu do zarządzania urządzeniami przenośnymi (MDM) 
- Używanie zasad rozwiązania Intune App Protection do zarządzania urządzeniami 
- Używanie kontrolek programu Exchange zgodnie z opisem w [tej](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/clients-and-mobile-in-exchange-online) dokumentacji 

#### <a name="additional-information"></a>Dodatkowe informacje  
https://docs.microsoft.com/intune/exchange-service-connector-configure




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
