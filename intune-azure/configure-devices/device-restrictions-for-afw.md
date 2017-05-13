---
title: "Ustawienia ograniczeń urządzenia z programem Android for Work w usłudze Intune | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: informacje na temat ustawień usługi Intune służących do kontrolowania ustawień i funkcjonalności na urządzeniach z programem Android for Work."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1830720b-16cb-4f2f-a71a-62967f882563
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: f9e8a5deb17ebb77d480213567e5ccf6550e3493
ms.openlocfilehash: be6303f2db508c2aca9ba9a40fcd43278f83c045
ms.contentlocale: pl-pl
ms.lasthandoff: 05/03/2017


---

# <a name="android-for-work-device-restriction-settings-in-microsoft-intune"></a>Ustawienia ograniczeń urządzenia z programem Android for Work w usłudze Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="work-profile-settings"></a>Ustawienia profilu służbowego
-     **Udostępnianie danych między profilami służbowym i osobistym** — użyj tego ustawienia, aby określić, czy aplikacje w profilu służbowym mogą udostępniać dane aplikacjom w profilu osobistym. Wybierz spośród opcji:
    - **Domyślne ograniczenia udostępniania** — domyślne zachowanie urządzenia w zakresie udostępniania, które różni się w zależności od wersji zainstalowanego systemu Android. Udostępnianie danych z profilu osobistego w profilu służbowym jest domyślnie dozwolone. Udostępnianie danych z profilu służbowego w profilu osobistym jest domyślnie zablokowane. Taka konfiguracja zapobiega wyciekowi danych z profilu służbowego do profilu osobistego. Google nie umożliwia blokowania danych przesyłanych z profilu osobistego na profil służbowy na urządzeniach z systemem w wersji wcześniejszej niż 6.0.  
    - **Aplikacje w profilu służbowym mogą obsługiwać żądania udostępnienia z profilu osobistego** — ta opcja pozwala włączyć wbudowaną funkcję systemu Android pozwalającą na udostępnianie danych z profilu osobistego w profilu służbowym. Gdy ta opcja jest włączona, żądanie udostępnienia przesłane z aplikacji w profilu osobistym umożliwi udostępnianie danych aplikacjom w profilu służbowym. Jest to domyślne zachowanie w przypadku urządzeń z systemem Android w wersji wcześniejszej niż 6.0.
    - **Aplikacje w profilu osobistym mogą obsługiwać żądania udostępnienia z profilu służbowego** — umożliwia udostępnianie danych między obydwoma profilami w obu kierunkach. Po wybraniu tego ustawienia aplikacje w profilu służbowym mogą udostępniać dane niezarządzanym aplikacjom w profilu osobistym.  Tego ustawienia należy używać ostrożnie, jako że umożliwia ono przesyłanie zarządzanych danych z profilu służbowego do niezarządzanych lokalizacji w urządzeniu.


-     **Powiadomienia profilu służbowego przy zablokowanym urządzeniu** — pozwala określić, czy aplikacje z profilu służbowego mogą wyświetlać powiadomienia na ekranie, gdy urządzenie jest zablokowane.
-     **Domyślne uprawnienia aplikacji** — powoduje ustawienie domyślnych zasad uprawnień dla wszystkich aplikacji w profilu służbowym. Począwszy od systemu Android w wersji 6 użytkownik końcowy otrzymuje monity dotyczące określonych uprawnień wymaganych przez aplikacje podczas ich działania. To ustawienie zasad pozwala określić, czy i jak użytkownicy są monitowani o nadanie uprawnień aplikacjom w profilu służbowym.
Można na przykład wypchnąć do profilu służbowego aplikację, która wymaga dostępu do lokalizacji. W przypadku zastosowania standardowej konfiguracji w aplikacji zostałoby wyświetlone wyskakujące okno dialogowe z pytaniem, czy użytkownik chce udzielić aplikacji dostępu do lokalizacji. Użytkownik mógłby zezwolić na dostęp lub wybrać opcję odmowy dostępu. Ta zasada pozwala zdecydować, czy wszystkie uprawnienia powinny być przyznawane automatycznie bez wyświetlania monitu, czy ma być automatycznie wybierana opcja odmowy dostępu bez wyświetlania monitu, czy też decyzja ma zostać pozostawiona użytkownikowi końcowemu. Wybierz spośród opcji:
    -     **Ustawienie domyślne urządzenia**
    -     **Monit**
    -     **Automatyczne udzielaj**
    -     **Automatyczne odmawiaj**

## <a name="password"></a>Hasło

- **Minimalna długość hasła** — określ minimalną liczbę znaków, które musi zawierać hasło użytkownika (**4**-**14**)
- **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu** — określ, po jakim czasie braku aktywności następuje automatyczne zablokowanie urządzenia.
- **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia** — określ, ile razy może zostać podane nieprawidłowe hasło, zanim zostaną wyczyszczone wszystkie dane z urządzenia.
- **Wygaśnięcie hasła (dni)** — określ liczbę dni, po których użytkownik końcowy musi zmienić hasło (**1**-**255**).
- **Wymagany typ hasła** — wybierz typ hasła, które musi zostać ustawione na urządzeniu. Wybierz spośród opcji:
    - **Ustawienie domyślne urządzenia**
    - **Zabezpieczenia biometryczne na niskim poziomie**
    - **Wymagane**
    - **Co najmniej numeryczne**
    - **Złożona wartość liczbowa** — (powtarzające się lub kolejne cyfry, np. „1111” lub „1234”, są niedozwolone)
    - **Co najmniej alfabetyczne**
    - **Co najmniej alfanumeryczne**
    - **Co najmniej alfanumeryczne z symbolami**
- **Zapobiegaj ponownemu użyciu starych haseł** — wprowadź liczbę nowych haseł, których należy użyć, zanim będzie możliwe ponowne użycie starego hasła (**1**-**24**).
- **Odblokowywanie za pomocą odcisku palca** — uniemożliwia użytkownikowi końcowemu użycie skanera linii papilarnych w celu odblokowania urządzenia.
- **Blokada Smart Lock i inni agenci zaufania** — umożliwia sterowanie funkcją Smart Lock na zgodnych urządzeniach. Ta funkcja telefonu, czasami znana jako funkcja agentów zaufania, umożliwia wyłączenie lub obejście hasła ekranu blokady urządzenia, jeśli urządzenie jest w zaufanej lokalizacji (np. gdy zostało podłączone do danego urządzenia Bluetooth lub znajduje się w pobliżu tagu NFC). Tego ustawienia można użyć, aby uniemożliwić użytkownikom skonfigurowanie funkcji Smart Lock.

## <a name="custom-policy-settings"></a>Ustawienia zasad niestandardowych
**Niestandardowe zasady konfiguracji programu Android for Work** w usłudze Microsoft Intune umożliwiają przypisanie ustawień OMA-URI, których można użyć do sterowania funkcjami na urządzeniach z programem Android for Work. Są to ustawienia standardowe używane przez wielu producentów urządzeń przenośnych do sterowania funkcjami urządzeń.

Ta funkcja ma umożliwić przypisanie ustawień systemu Android, których nie można skonfigurować przy użyciu zasad usługi Intune.
Obecnie usługa Intune obsługuje tylko ograniczoną liczbę zasad niestandardowych systemu Android. Zobacz przykłady w tym temacie, aby dowiedzieć się, które zasady możesz skonfigurować.

### <a name="general-settings"></a>Ustawienia ogólne

|Nazwa ustawienia|Szczegóły|
    |----------------|--------------------|
    |**Nazwa** |Wprowadź unikatową nazwę niestandardowych zasad systemu Android, która pomoże je zidentyfikować w konsoli usługi Intune.|
    |**Opis** |Podaj opis zawierający omówienie zasad niestandardowych systemu Android oraz inne istotne informacje ułatwiające ich wyszukanie.|

### <a name="oma-uri-settings"></a>Ustawienia OMA-URI

  |Nazwa ustawienia|Szczegóły|
  |--------|--------------------|
  |**Nazwa** |Wprowadź unikatową nazwę dla ustawienia OMA-URI, aby ułatwić jego identyfikację na liście ustawień.|
  |**Opis** |Podaj opis, który zawiera omówienie ustawienia oraz inne istotne informacje, które ułatwią jego wyszukanie.|
    |**OMA-URI (z uwzględnieniem wielkości liter)** |Określ identyfikator OMA-URI, dla którego chcesz podać ustawienie.|
  |**Typ danych** |Wybierz typ danych, zgodnie z którym określisz to ustawienie OMA-URI. Wybierz jedną z opcji: **Ciąg, Ciąg (XML), Data i godzina, Liczba całkowita, Liczba zmiennoprzecinkowa** lub **Wartość logiczna**.|
  |**Wartość** |Określ wartość, która będzie kojarzona z określonym wcześniej identyfikatorem OMA-URI.|

