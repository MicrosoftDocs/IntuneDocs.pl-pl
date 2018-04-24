---
title: Ograniczenia urządzeń korzystających z programu Android for Work w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Na urządzeniach z programem Android for Work możesz ograniczyć część ustawień, w tym kopiowanie i wklejanie, pokazywanie powiadomień, uprawnienia aplikacji, udostępnianie danych, długość hasła, błędy logowania, używanie odcisku palca do odblokowywania, ponowne używanie haseł oraz włączanie udostępniania kontaktów służbowych za pomocą technologii Bluetooth.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 11ce7fa7fa4d48d9cc292b7b6565b6b4f2be2dc4
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="work-device-restriction-settings-in-intune"></a>Ustawienia ograniczeń urządzenia służbowego w usłudze Intune

W tym artykule opisano ustawienia ograniczeń urządzenia, które można skonfigurować w usłudze Microsoft Intune dla urządzeń z programem Android for Work.

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="work-profile-settings"></a>Ustawienia profilu służbowego

### <a name="general-settings"></a>Ustawienia ogólne

- **Kopiuj i wklejaj między profilem służbowym a osobistym**: steruje kopiowaniem i wklejaniem między aplikacjami służbowymi i osobistymi. Wybierz pozycję **Blokuj**, aby włączyć blokowanie. Wybierz pozycję **Nieskonfigurowane**, aby wyłączyć blokowanie.
- **Udostępnianie danych między profilami służbowym i osobistym**: określ, czy aplikacje w profilu służbowym mogą udostępniać dane aplikacjom w profilu osobistym. To ustawienie określa akcje udostępniania w ramach aplikacji (na przykład opcję **Udostępnij…** w aplikacji Chrome) i nie ma zastosowania do zachowania schowka w zakresie kopiowania/wklejania. W odróżnieniu od [ustawień zasad ochrony aplikacji](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) ustawieniami ograniczeń urządzenia zarządza się w portalu usługi Intune i używa partycji profilu służbowego programu Android for Work do izolowania zarządzanych aplikacji. Wybierz spośród opcji:
  - **Domyślne ograniczenia udostępniania**: domyślne zachowanie urządzenia w zakresie udostępniania, które różni się w zależności od wersji systemu Android. Udostępnianie danych z profilu osobistego w profilu służbowym jest domyślnie dozwolone. Udostępnianie danych z profilu służbowego w profilu osobistym jest domyślnie zablokowane. To ustawienie zapobiega udostępnianiu danych z profilu służbowego w profilu osobistym. Google nie umożliwia blokowania udostępniania z profilu osobistego w profilu służbowym na urządzeniach z systemem w wersji 6.0 lub nowszej.
  - **Aplikacje w profilu służbowym mogą obsługiwać żądania udostępnienia z profilu osobistego**: umożliwia włączenie wbudowanej funkcji systemu Android pozwalającej na udostępnianie danych z profilu osobistego w profilu służbowym. Gdy ta opcja jest włączona, żądanie udostępnienia z aplikacji w profilu osobistym umożliwi udostępnianie danych aplikacjom w profilu służbowym. Jest to domyślne ustawienie w przypadku urządzeń z systemem Android w wersji wcześniejszej niż 6.0.
  - **Zezwalaj na udostępnianie przez granice**: umożliwia udostępnianie przez granicę profilu służbowego w obu kierunkach. Po wybraniu tego ustawienia aplikacje w profilu służbowym mogą udostępniać dane niewskazanym aplikacjom w profilu osobistym. Tego ustawienia należy używać ostrożnie, ponieważ pozwala ono zarządzanym aplikacjom z profilu służbowego na udostępnianie danych aplikacjom w niezarządzanym obszarze urządzenia.

- **Powiadomienia profilu służbowego przy zablokowanym urządzeniu**: pozwala określić, czy aplikacje z profilu służbowego mogą wyświetlać dane w powiadomieniach, gdy urządzenie jest zablokowane.
- **Domyślne uprawnienia aplikacji**: powoduje ustawienie domyślnych zasad uprawnień dla wszystkich aplikacji w profilu służbowym. Począwszy od systemu Android 6, użytkownik jest monitowany o udzielenie określonych uprawnień wymaganych przez aplikacje, gdy aplikacja jest uruchamiana. To ustawienie zasad pozwala określić, czy użytkownicy są monitowani o nadanie uprawnień wszystkim aplikacjom w profilu służbowym. Można na przykład przypisać aplikację do profilu służbowego, który wymaga dostępu do lokalizacji. Standardowo aplikacja monituje użytkownika o zatwierdzenie lub odrzucenie dostępu aplikacji do lokalizacji. Te zasady pozwalają zdecydować, czy wszystkie uprawnienia powinny być przyznawane automatycznie bez wyświetlania monitu, czy ma być automatycznie wybierana opcja odmowy dostępu bez wyświetlania monitu, czy też decyzja ma zostać pozostawiona użytkownikowi końcowemu. Wybierz spośród opcji:
  - **Ustawienie domyślne urządzenia**
  - **Monit**
  - **Automatyczne udzielaj**
  - **Automatyczne odmawiaj**

    Stan nadania uprawnień można dodatkowo zdefiniować dla określonych aplikacji, używając zasad konfiguracji aplikacji dla poszczególnych aplikacji (w obszarze **Aplikacje mobilne** > **Zasady konfiguracji aplikacji**).

- **Dodawanie i usuwanie kont**

   Uniemożliwia użytkownikom końcowym ręczne dodawanie i usuwanie kont w profilu służbowym.

   Na przykład w przypadku wdrożenia aplikacji Gmail w profilu programu Android for Work można uniemożliwić użytkownikom końcowym dodawanie i usuwanie kont w tym profilu służbowym.

- **Udostępnianie kontaktów za pośrednictwem połączenia Bluetooth**: umożliwia dostęp do kontaktów służbowych z innego urządzenia, takiego jak samochód, sparowanego za pomocą połączenia Bluetooth. Domyślnie to ustawienie nie jest skonfigurowane i kontakty służbowe nie są wyświetlane. Wybierz pozycję **Włącz**, aby zezwolić na udostępnianie i wyświetlić kontakty z profilu służbowego. To ustawienie dotyczy urządzeń z systemem Android w wersji 6.0 i nowszych oraz profilem służbowym.

### <a name="work-profile-password"></a>Hasło profilu służbowego

- **Wymagaj hasła profilu służbowego**: ma zastosowanie do systemu Android 7.0 lub nowszego z włączonym profilem służbowym. Zdefiniuj zasady kodu dostępu, które będą mieć zastosowanie wyłącznie do aplikacji w profilu służbowym. Domyślnie użytkownik końcowy może używać dwóch różnych kodów PIN lub wybrać opcję połączenia zdefiniowanych kodów PIN w celu uzyskania kodu PIN o większej sile.
- **Minimalna długość hasła**: określ minimalną liczbę znaków, które musi zawierać hasło użytkownika (**4**-**16**)
- **Maksymalna liczba minut braku aktywności przed zablokowaniem profilu służbowego**: określ, po jakim czasie następuje zablokowanie profilu służbowego. Użytkownik musi następnie wprowadzić swoje poświadczenia, aby odzyskać dostęp.
- **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia**: określ, ile razy może zostać podane nieprawidłowe hasło, zanim profil służbowy zostanie wyczyszczony z urządzenia.
- **Wygaśnięcie hasła (dni)**: określ liczbę dni, po których użytkownik końcowy musi zmienić hasło (**1**-**255**).
- **Wymagany typ hasła**: wybierz typ hasła, które musi zostać ustawione na urządzeniu. Wybierz spośród opcji:
  - **Ustawienie domyślne urządzenia**
  - **Zabezpieczenia biometryczne na niskim poziomie**
  - **Wymagane**
  - **Co najmniej numeryczne**
  - **Złożona wartość liczbowa**: powtarzające się lub kolejne cyfry, np. „1111” lub „1234”, są niedozwolone
  - **Co najmniej alfabetyczne**
  - **Co najmniej alfanumeryczne**
  - **Co najmniej alfanumeryczne z symbolami**
- **Zapobiegaj ponownemu użyciu starych haseł**: wprowadź liczbę nowych haseł, których należy użyć, zanim będzie możliwe ponowne użycie starego hasła (**1**-**24**).
- **Odblokowywanie za pomocą odcisku palca**: uniemożliwia użytkownikowi końcowemu użycie skanera linii papilarnych w celu odblokowania urządzenia
- **Blokada Smart Lock i inni agenci zaufania**: umożliwia sterowanie funkcją Smart Lock na zgodnych urządzeniach. Ta funkcja telefonu, czasami znana jako funkcja agentów zaufania, umożliwia wyłączenie lub obejście hasła profilu służbowego, jeśli urządzenie jest w zaufanej lokalizacji. Na przykład gdy urządzenie jest połączone z konkretnym urządzeniem Bluetooth lub znajduje się w pobliżu tagu NFC. Za pomocą tego ustawienia można uniemożliwić użytkownikom konfigurowanie funkcji Smart Lock.

## <a name="device-password"></a>Hasło urządzenia

- **Minimalna długość hasła**: określ minimalną liczbę znaków, które musi zawierać hasło użytkownika (**4**-**14**)
- **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu**: określ, po jakim czasie braku aktywności następuje automatyczne zablokowanie urządzenia
- **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia**: określ, ile razy może zostać podane nieprawidłowe hasło, zanim zostaną wyczyszczone wszystkie dane z urządzenia
- **Wygaśnięcie hasła (dni)**: określ liczbę dni, po których użytkownik końcowy musi zmienić hasło (**1**-**255**)
- **Wymagany typ hasła**: wybierz typ hasła, które musi zostać ustawione na urządzeniu. Wybierz spośród opcji:
  - **Ustawienie domyślne urządzenia**
  - **Zabezpieczenia biometryczne na niskim poziomie**
  - **Wymagane**
  - **Co najmniej numeryczne**
  - **Złożona wartość liczbowa**: powtarzające się lub kolejne cyfry, np. „1111” lub „1234”, są niedozwolone
  - **Co najmniej alfabetyczne**
  - **Co najmniej alfanumeryczne**
  - **Co najmniej alfanumeryczne z symbolami**
- **Zapobiegaj ponownemu użyciu starych haseł**: wprowadź liczbę nowych haseł, których należy użyć, zanim będzie możliwe ponowne użycie starego hasła (**1**-**24**).
- **Odblokowywanie za pomocą odcisku palca**: uniemożliwia użytkownikowi końcowemu użycie skanera linii papilarnych w celu odblokowania urządzenia
- **Blokada Smart Lock i inni agenci zaufania**: umożliwia sterowanie funkcją Smart Lock na zgodnych urządzeniach. Ta funkcja telefonu, czasami znana jako funkcja agentów zaufania, umożliwia wyłączenie lub obejście hasła ekranu blokady urządzenia, jeśli urządzenie jest w zaufanej lokalizacji. Na przykład gdy urządzenie jest połączone z konkretnym urządzeniem Bluetooth lub znajduje się w pobliżu tagu NFC. Za pomocą tego ustawienia można uniemożliwić użytkownikom konfigurowanie funkcji Smart Lock.

## <a name="system-security"></a>Zabezpieczenia systemu

- **Skanowanie aplikacji pod kątem zagrożeń**: wymuszaj włączenie ustawienia **Weryfikuj aplikacje** w profilach służbowych i osobistych.

   > [!Note]
   > To ustawienie działa tylko w przypadku urządzeń z systemem Android O lub nowszym.

## <a name="next-step"></a>Następny krok

Aby zapisać profil i przypisać go do użytkowników i urządzeń, zobacz [Konfigurowanie ustawień ograniczeń urządzenia](device-restrictions-configure.md).