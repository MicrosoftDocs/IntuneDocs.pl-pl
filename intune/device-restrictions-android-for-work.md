---
title: "Ustawienia ograniczeń urządzenia z programem Android for Work w usłudze Intune"
titlesuffix: Azure portal
description: "Informacje na temat ustawień usługi Intune służących do kontrolowania ustawień i funkcji urządzeń z programem Android for Work."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1830720b-16cb-4f2f-a71a-62967f882563
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: beb8368aa2db33df84bb64985177b47beebc80ac
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/12/2017
---
# <a name="android-for-work-device-restriction-settings-in-microsoft-intune"></a>Ustawienia ograniczeń urządzenia z programem Android for Work w usłudze Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="work-profile-settings"></a>Ustawienia profilu służbowego
-   **Kopiuj i wklejaj między profilem służbowym a osobistym** — steruje kopiowaniem i wklejaniem między aplikacjami służbowymi i prywatnymi. Wybierz pozycję **Blokuj**, aby włączyć blokowanie. Wybierz pozycję **Nieskonfigurowane**, aby wyłączyć blokowanie.
- **Udostępnianie danych między profilami służbowym i osobistym** — użyj tego ustawienia, aby określić, czy aplikacje w profilu służbowym mogą udostępniać dane aplikacjom w profilu osobistym. To ustawienie określa akcje udostępniania w ramach aplikacji (na przykład opcję **Udostępnij…** w aplikacji Chrome) i nie ma zastosowania do zachowania schowka w zakresie kopiowania/wklejania. W odróżnieniu od [ustawień zasad ochrony aplikacji](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) ustawienia ograniczeń urządzenia są zarządzane w portalu usługi Intune i używają partycji profilu służbowego programu Android for Work do izolowania zarządzanych aplikacji. Wybierz spośród opcji:
    - **Domyślne ograniczenia udostępniania** — to ustawienie określa domyślne zachowanie urządzenia w zakresie udostępniania, które różni się w zależności od wersji zainstalowanego systemu Android. Udostępnianie danych z profilu osobistego w profilu służbowym jest domyślnie dozwolone. Udostępnianie danych z profilu służbowego w profilu osobistym jest domyślnie zablokowane. To ustawienie zapobiega udostępnianiu danych z profilu służbowego w profilu osobistym. Google nie umożliwia blokowania udostępniania z profilu osobistego w profilu służbowym na urządzeniach z systemem w wersji 6.0 lub nowszej.   
    - **Aplikacje w profilu służbowym mogą obsługiwać żądania udostępnienia z profilu osobistego** — ta opcja pozwala włączyć wbudowaną funkcję systemu Android pozwalającą na udostępnianie danych z profilu osobistego w profilu służbowym. Gdy ta opcja jest włączona, żądanie udostępnienia z aplikacji w profilu osobistym umożliwi udostępnianie danych aplikacjom w profilu służbowym. Jest to domyślne ustawienie w przypadku urządzeń z systemem Android w wersji wcześniejszej niż 6.0.
    - **Zezwalaj na udostępnianie przez granice** — umożliwia udostępnianie przez granicę profilu służbowego w obu kierunkach. Po wybraniu tego ustawienia aplikacje w profilu służbowym mogą udostępniać dane niewskazanym aplikacjom w profilu osobistym. Tego ustawienia należy używać ostrożnie, ponieważ pozwala ono zarządzanym aplikacjom z profilu służbowego udostępniać dane aplikacjom w niezarządzanym obszarze urządzenia.

-   **Powiadomienia profilu służbowego przy zablokowanym urządzeniu** — pozwala określić, czy aplikacje z profilu służbowego mogą wyświetlać dane w powiadomieniach, gdy urządzenie jest zablokowane.
-   **Domyślne uprawnienia aplikacji** — powoduje ustawienie domyślnych zasad uprawnień dla wszystkich aplikacji w profilu służbowym. Począwszy od systemu Android 6, użytkownik jest monitowany o udzielenie określonych uprawnień wymaganych przez aplikacje, gdy aplikacja jest uruchamiana. To ustawienie zasad pozwala określić, czy użytkownicy są monitowani o nadanie uprawnień wszystkim aplikacjom w profilu służbowym. Można na przykład przypisać aplikację do profilu służbowego, który wymaga dostępu do lokalizacji. Standardowo aplikacja monituje użytkownika o zatwierdzenie lub odrzucenie dostępu aplikacji do lokalizacji. Te zasady pozwalają zdecydować, czy wszystkie uprawnienia powinny być przyznawane automatycznie bez wyświetlania monitu, czy ma być automatycznie wybierana opcja odmowy dostępu bez wyświetlania monitu, czy też decyzja ma zostać pozostawiona użytkownikowi końcowemu. Wybierz spośród opcji:
    -   **Ustawienie domyślne urządzenia**
    -   **Monit**
    -   **Automatyczne udzielaj**
    -   **Automatyczne odmawiaj**

    Stan nadania uprawnień można dodatkowo zdefiniować dla określonych aplikacji, definiując zasady konfiguracji aplikacji dla poszczególnych aplikacji (w obszarze **Aplikacje mobilne** > **Zasady konfiguracji aplikacji**).

### <a name="work-profile-password"></a>Hasło profilu służbowego
- **Wymagaj hasła profilu służbowego** — (Android 7.0 i nowsze wersje z włączonym profilem służbowym) definiuje zasady kodu dostępu mające zastosowanie tylko do aplikacji w profilu służbowym. Domyślnie użytkownik końcowy może użyć dwóch różnych kodów PIN lub wybrać opcję połączenia ich w celu uzyskania kodu PIN o większej sile.
- **Minimalna długość hasła** — określ minimalną liczbę znaków, które musi zawierać hasło użytkownika (**4**-**16**).
- **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu** — określ, po jakim czasie następuje zablokowanie profilu służbowego. Użytkownik musi następnie wprowadzić swoje poświadczenia, aby odzyskać dostęp.
- **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia** — określ, ile razy może zostać podane nieprawidłowe hasło, zanim profil służbowy zostanie wyczyszczony z urządzenia.
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
- **Blokada Smart Lock i inni agenci zaufania** — umożliwia sterowanie funkcją Smart Lock na zgodnych urządzeniach. Ta funkcja telefonu, czasami znana jako funkcja agentów zaufania, umożliwia wyłączenie lub obejście hasła profilu, jeśli urządzenie jest w zaufanej lokalizacji (np. gdy zostało podłączone do określonego urządzenia Bluetooth lub znajduje się w pobliżu tagu NFC). Możesz użyć tego ustawienia, aby uniemożliwić użytkownikom konfigurowanie funkcji blokady inteligentnej.

## <a name="device-password"></a>Hasło urządzenia

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
- **Blokada Smart Lock i inni agenci zaufania** — umożliwia sterowanie funkcją Smart Lock na zgodnych urządzeniach. Ta funkcja telefonu, czasami znana jako funkcja agentów zaufania, umożliwia wyłączenie lub obejście hasła ekranu blokady urządzenia, jeśli urządzenie jest w zaufanej lokalizacji (np. gdy zostało podłączone do określonego urządzenia Bluetooth lub znajduje się w pobliżu tagu NFC). Możesz użyć tego ustawienia, aby uniemożliwić użytkownikom konfigurowanie funkcji blokady inteligentnej.

## <a name="system-security"></a>Zabezpieczenia systemu

 - **Skanowanie aplikacji pod kątem zagrożeń** — wymuszaj włączenie ustawienia **Weryfikuj aplikacje** w profilach służbowych i osobistych.

   > [!Note]  
   > To ustawienie będzie działać tylko w przypadku urządzeń z systemem Android O lub nowszym. 

## <a name="next-steps"></a>Następne kroki

Skorzystaj z informacji w temacie [Jak skonfigurować ustawienia ograniczeń urządzeń](device-restrictions-configure.md), aby zapisać i przypisać profil do użytkowników i urządzeń.
