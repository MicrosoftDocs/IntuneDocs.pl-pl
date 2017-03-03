---
title: Ustawienia zasad ochrony aplikacji dla systemu iOS
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: w tym temacie opisano ustawienia zasad ochrony aplikacji dla urządzeń z systemem iOS."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0f8b08f2-504c-4b38-bea2-b8a4ef0526b8
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: a391f9e16faf315c5fb88191f3de3f8f2f3d5178
ms.lasthandoff: 02/18/2017


---

#  <a name="ios-app-protection-policy-settings"></a>Ustawienia zasad ochrony aplikacji dla systemu iOS
[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Opisane w tym temacie ustawienia zasad można [skonfigurować](app-protection-policies.md) dla zasad ochrony aplikacji w bloku **Ustawienia** w witrynie Azure Portal.

Istnieją dwie kategorie ustawień zasad: relokacja danych i dostęp. W tym temacie termin ***aplikacje zarządzane przez zasady*** dotyczy aplikacji konfigurowanych przy użyciu zasad ochrony aplikacji.

##  <a name="data-relocation-settings"></a>Ustawienia relokacji danych

| Ustawienie | Sposób użycia | Wartości domyślne |
|------|------|------|
| **Nie zezwalaj na kopie zapasowe programu iTunes i usługi iCloud** | Wybierz opcję **Tak**, aby uniemożliwić tej aplikacji tworzenie kopii zapasowych danych służbowych w programie iTunes i usłudze iCloud. Wybierz opcję **Nie**, aby zezwolić tej aplikacji na tworzenie kopii zapasowych danych służbowych w programie iTunes i usłudze iCloud.| Tak |
| **Zezwalaj aplikacji na przesyłanie danych do innych aplikacji** | Określ, które aplikacje mogą odbierać dane z tej aplikacji: <ul><li> **Aplikacje zarządzane przez zasady**: zezwalaj na przesyłanie danych tylko do innych aplikacji zarządzanych przez zasady.</li> <li>**Wszystkie aplikacje**: zezwalaj na przesyłanie danych do wszystkich aplikacji. </li> <li>**Brak**: nie zezwalaj na przesyłanie danych do żadnych aplikacji, w tym również innych aplikacji zarządzanych przez zasady.</li></ul> Ponadto jeśli ta opcja zostanie ustawiona na wartość **Aplikacje zarządzane przez zasady** lub **Brak**, zostanie zablokowana funkcja systemu iOS 9, która umożliwia narzędziu Spotlight Search wyszukiwanie danych w ramach aplikacji. <br><br> Istnieją pewne aplikacje i usługi, w przypadku których usługa Intune może zezwolić na przesyłanie danych do tych aplikacji i usług. Sekcja [Wyjątki w transferze danych](#Data-transfer-exemptions) zawiera pełną listę aplikacji i usług. | Wszystkie aplikacje |
| **Zezwalaj aplikacji na odbieranie danych z innych aplikacji** | Określ, jakie aplikacje mogą przesyłać dane do tej aplikacji: <ul><li>**Aplikacje zarządzane przez zasady**: zezwalaj na przesyłanie danych tylko z innych aplikacji zarządzanych przez zasady.</li><li>**Wszystkie aplikacje**: zezwalaj na przesyłanie danych z wszystkich aplikacji.</li><li>**Brak**: nie zezwalaj na przesyłanie danych z żadnych aplikacji, w tym również innych aplikacji zarządzanych przez zasady. </li></ul> <p>  Istnieją pewne aplikacje i usługi, w przypadku których usługa Intune może zezwolić na przesyłanie danych z tych aplikacji i usług. Sekcja [Wyjątki w transferze danych](#Data-transfer-exemptions) zawiera pełną listę aplikacji i usług. | Wszystkie aplikacje |
| **Nie zezwalaj na używanie polecenia „Zapisz jako”** | Wybierz opcję **Tak**, aby wyłączyć używanie opcji Zapisz jako w tej aplikacji. Wybierz opcję **Nie**, jeśli chcesz zezwolić na używanie polecenia Zapisz jako. | Nie |
| **Ogranicz wycinanie, kopiowanie i wklejanie w innych aplikacjach** | Określ, kiedy można używać akcji wycinania, kopiowania i wklejania w tej aplikacji. Wybierz spośród opcji: <ul><li>**Zablokowane**: nie zezwalaj na akcje wycinania, kopiowania i wklejania między tą aplikacją i dowolną inną aplikacją.</li><li>**Aplikacje zarządzane przez zasady**: zezwalaj na akcje wycinania, kopiowania i wklejania między tą aplikacją i innymi aplikacjami zarządzanymi przez zasady.</li><li>**Aplikacje zarządzane przez zasady z funkcją wklejania**: zezwalaj na wycinanie i kopiowanie między tą aplikacją i innymi aplikacjami zarządzanymi przez zasady. Zezwalaj na wklejanie w tej aplikacji danych z dowolnych aplikacji.</li><li>**Dowolna aplikacja**: brak ograniczeń wycinania, kopiowania i wklejania do i z tej aplikacji. | Dowolna aplikacja |
|**Ogranicz zawartość sieci Web do wyświetlenia w programie Managed Browser** | Wybierz opcję **Tak**, aby wymusić otwieranie linków sieci Web w danej aplikacji za pomocą aplikacji Managed Browser. <br><br> W przypadku urządzeń, które nie zostały zarejestrowane w usłudze Intune, linki sieci Web w aplikacjach zarządzanych przez zasady będą otwierane tylko w aplikacji Managed Browser. <br><br> Jeśli używasz usługi Intune do zarządzania swoimi urządzeniami, zobacz [Zarządzanie dostępem do Internetu za pomocą zasad programu Managed Browser w usłudze Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/manage-internet-access-using-managed-browser-policies). | Nie |
| **Szyfruj dane aplikacji** | W przypadku aplikacji zarządzanych przez zasady dane są szyfrowane, gdy nie są używane, za pomocą szyfrowania na poziomie urządzenia obsługiwanego przez system iOS. Jeśli jest wymagany numer PIN, dane są szyfrowane zgodnie z ustawieniami zasad ochrony aplikacji. <br><br> Przejdź do oficjalnej dokumentacji firmy Apple dostępnej [tutaj](https://support.apple.com/HT202739), aby sprawdzić, które moduły szyfrowania systemu iOS mają certyfikat FIPS 140-2 lub oczekują na uzyskanie certyfikatu FIPS 140-2. <br><br> Określ, kiedy dane służbowe w tej aplikacji są szyfrowane. Wybierz spośród opcji: <ul><li>**Gdy urządzenie jest zablokowane**: wszystkie dane aplikacji skojarzonych z tymi zasadami są szyfrowane, gdy urządzenie jest zablokowane.</li><li>**Gdy urządzenie jest zablokowane i istnieją otwarte pliki**: wszystkie dane aplikacji skojarzonych z tymi zasadami są szyfrowane, gdy urządzenie jest zablokowane, z wyjątkiem danych w plikach obecnie otwartych w aplikacji.</li><li>**Po ponownym uruchomieniu urządzenia:** wszystkie dane aplikacji skojarzonych z tymi zasadami są szyfrowane po ponownym uruchomieniu urządzenia, do momentu odblokowania urządzenia po raz pierwszy.</li><li>**Użyj ustawień urządzenia:** dane aplikacji są szyfrowane na podstawie ustawień domyślnych urządzenia. Po włączeniu tego ustawienia użytkownik musi skonfigurować i stosować numer PIN, aby uzyskać dostęp do urządzenia.  Jeśli nie skonfigurowano numeru PIN, aplikacje nie będą otwierane, a użytkownik otrzyma monit o ustawienie numeru PIN z następującym komunikatem: „Twoja organizacja wymaga włączenia numeru PIN urządzenia w celu uzyskania dostępu do tej aplikacji”. </li></ul> | Gdy urządzenie jest zablokowane |
| **Wyłącz synchronizację kontaktów** | Wybierz opcję **Tak**, aby uniemożliwić aplikacji zapisywanie danych w natywnej aplikacji Kontakty na urządzeniu. Jeśli wybierzesz opcję **Nie**, aplikacja będzie mogła zapisywać dane w natywnej aplikacji Kontakty na urządzeniu. <br><br>Gdy jest wykonywane selektywne czyszczenie danych w celu usunięcia danych służbowych z aplikacji, kontakty zsynchronizowane bezpośrednio z aplikacji do natywnej aplikacji Kontakty są usuwane. Nie można wyczyścić wszystkich kontaktów zsynchronizowanych z natywnej książki adresowej do innego źródła zewnętrznego. Obecnie dotyczy to tylko aplikacji Microsoft Outlook. | Nie |
| **Wyłącz drukowanie** | Wybierz opcję **Tak**, aby uniemożliwić aplikacji drukowanie danych służbowych. | Nie |


> [!NOTE]
> Żadne z ustawień relokacji danych nie steruje funkcją „Otwórz za pomocą” zarządzaną przez firmę Apple na urządzeniach z systemem iOS. Aby korzystać z funkcji „Otwórz za pomocą” zarządzanej przez firmę Apple, zobacz [Zarządzanie przesyłaniem danych między aplikacjami systemu iOS za pomocą usługi Microsoft Intune](manage-data-transfer-between-ios-apps-with-microsoft-intune.md).

## <a name="data-transfer-exemptions"></a>Wyjątki w transferze danych

Istnieją pewne aplikacje i usługi platform, w przypadku których w pewnych scenariuszach zasady ochrony aplikacji usługi Intune mogą zezwolić na przesyłanie danych z tych aplikacji i usług oraz do nich. Ta lista może ulec zmianom i odzwierciedla usługi oraz aplikacje uważane za przydatne w kwestii bezpieczeństwa wydajności.

| Nazwy aplikacji/usług | Opis |
| ---- | --- |
|tel; telprompt | Natywna aplikacja telefoniczna |
| skype | Skype |
| app-settings | Ustawienia urządzenia |
| itms; itmss; itms-apps; itms-appss; itms-services | App Store |
| calshow | Kalendarz natywny |


## <a name="access-settings"></a>Ustawienia dostępu

| Ustawienie | Sposób użycia | Wartości domyślne |
|------|------|------|
| **Wymagaj numeru PIN w celu udzielenia dostępu** | Wybierz opcję **Tak**, aby wymagać numeru PIN do korzystania z tej aplikacji. Użytkownik zostanie poproszony o skonfigurowanie tego numeru PIN przy pierwszym uruchomieniu aplikacji w kontekście służbowym. Wartość domyślna: **Tak**.<br><br> Skonfiguruj następujące ustawienia dotyczące siły numeru PIN: <ul><li>**Liczba prób przed zresetowaniem numeru PIN**: określ liczbę prób wprowadzenia numeru PIN, po której użytkownik musi go zresetować. Wartość domyślna: **5**.</li><li> **Zezwalaj na prosty numer PIN**: wybierz opcję **Tak**, aby zezwolić użytkownikom na stosowanie prostych sekwencji numeru PIN, takich jak 1234 lub 1111. Wybierz opcję **Nie**, aby uniemożliwić im stosowanie prostych sekwencji. Wartość domyślna: **Tak**. </li><li> **Długość numeru PIN**: określ minimalną liczbę cyfr w sekwencji numeru PIN. Wartość domyślna: **4**. </li><li> **Zezwalaj na odcisk palca zamiast numeru PIN (iOS 8.0 i nowsze)**: Wybierz opcję **Tak**, aby zezwolić użytkownikowi na dostęp do aplikacji za pomocą funkcji [Touch ID](https://support.apple.com/en-us/HT201371) zamiast numeru PIN. Wartość domyślna: **Tak**.</li></ul> Na urządzeniach z systemem iOS możesz zezwolić użytkownikowi na potwierdzanie tożsamości za pomocą funkcji [Touch ID](https://support.apple.com/en-us/HT201371) zamiast numeru PIN. Gdy użytkownik spróbuje skorzystać z tej aplikacji za pomocą konta służbowego, otrzyma monit o potwierdzenie tożsamości odciskiem palca, a nie numerem PIN. </li></ul>| Wymagaj numeru PIN: tak <br><br> Liczba prób przed zresetowaniem numeru PIN: 5 <br><br> Zezwalaj na prosty numer PIN: tak <br><br> Długość numeru PIN: 4 <br><br> Zezwalaj na odcisk palca: tak |
| **Wymagaj poświadczeń firmowych w celu udzielenia dostępu** | Wybierz opcję **Tak**, aby wymagać od użytkownika logowania się za pomocą konta służbowego zamiast numeru PIN w celu uzyskania dostępu do aplikacji. Wybranie opcji **Tak** przesłania wymagania dotyczące numeru PIN lub funkcji Touch ID.  | Nie |
| **Blokuj uruchamianie aplikacji zarządzanych na urządzeniach, na których zdjęto zabezpieczenia systemu lub uzyskano dostęp do konta root** |  Wybierz opcję **Tak**, aby uniemożliwić tej aplikacji działanie na urządzeniach, na których zdjęto zabezpieczenia systemu lub uzyskano dostęp do konta root. Użytkownik nadal będzie mógł wykonywać zadania osobiste za pomocą tej aplikacji, ale będzie musiał korzystać z innego urządzenia w celu uzyskania dostępu do danych służbowych w tej aplikacji. | Tak |
| **Ponownie sprawdź wymagania dostępu po (w minutach)** | Skonfiguruj następujące ustawienia: <ul><li>**Limit czasu:** określ czas (w minutach) przed ponownym sprawdzeniem wymagań dostępu do aplikacji. Wartość domyślna: **30** minut.</li><li>**Okres karencji w trybie offline:** jeśli urządzenie znajduje się w trybie offline, określ czas (w minutach) przed ponownym sprawdzeniem wymagań dostępu do aplikacji. Wartość domyślna: **720** minut (12 godzin).</li></ul>| Limit czasu: 30 <br><br> W trybie offline: 720 |
| **Interwał offline przed wyczyszczeniem danych aplikacji (w dniach)** | Dane służbowe w tej aplikacji mogą zostać wyczyszczone, jeśli urządzenie było w trybie offline dłużej niż przez określony czas. Określ liczbę dni, przez które urządzenie może pozostawać w trybie offline przed usunięciem z niego danych służbowych. <br><br> | 90 dni |

##  <a name="add-ins-for-outlook-app"></a>Dodatki dla aplikacji Outlook

Zespół ds. programu Outlook udostępnił ostatnio dodatki dla programu Outlook dla systemu iOS, które umożliwiają integrację popularnych aplikacji z klientem poczty e-mail. Dodatki dla programu Outlook w środowiskach Windows, Mac i Outlook dla systemu iOS są dostępne w sieci Web. Ponieważ dodatki są zarządzane przez program Microsoft Exchange, użytkownicy otrzymają możliwość udostępniania danych i wiadomości między programem Outlook i niezarządzanymi aplikacjami zgodnymi z dodatkiem, chyba że dodatki zostaną wyłączone dla użytkownika przez program Exchange.

Jeśli nie chcesz, aby użytkownicy końcowi mogli uzyskiwać dostęp do dodatków programu Outlook i je instalować (dotyczy wszystkich klientów programu Outlook), upewnij się, że w obszarze ról w centrum administracyjnym programu Exchange wprowadzono następujące zmiany:

- Aby uniemożliwić użytkownikom instalowanie dodatków ze Sklepu Office, usuń dla nich rolę Moja witryna Marketplace.
- Aby uniemożliwić użytkownikom ładowanie bezpośrednie dodatków, usuń dla nich rolę Moje aplikacje niestandardowe.
- Aby uniemożliwić użytkownikom instalowanie wszystkich dodatków, usuń dla nich zarówno rolę Moje aplikacje niestandardowe, jak i rolę Moja witryna Marketplace.

Instrukcje te dotyczą usług Office 365, Exchange 2016 i Exchange 2013 w środowiskach programu Outlook w sieci Web, w systemach Windows i Mac oraz w urządzeniach przenośnych.

- Dowiedz się więcej o [dodatkach programu Outlook](https://technet.microsoft.com/library/jj943753(v=exchg.150).aspx).
- Dowiedz się więcej na temat tego, [jak określić, którzy administratorzy i użytkownicy mogą instalować dodatki dla aplikacji Outlook i zarządzać nimi](https://technet.microsoft.com/library/jj943754(v=exchg.150).aspx).
