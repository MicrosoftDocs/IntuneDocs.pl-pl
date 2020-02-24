---
title: Wycofywanie lub czyszczenie urządzeń przy użyciu usługi Microsoft Intune — Azure | Microsoft Docs
description: Wycofaj lub wyczyść urządzenie z systemem Android, profilem służbowym systemu Windows, systemem iOS/iPadOS lub macOS albo urządzeń z systemem Windows, korzystając z usługi Microsoft Intune. Ponadto możesz usunąć urządzenie z usługi Azure Active Directory.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/08/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4fdb787e-084f-4507-9c63-c96b13bfcdf9
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 62ba66469dfff004c3cd6a60284ec7466e8b9f00
ms.sourcegitcommit: 51591b862d97904291af7aa53a6eb341b11a761e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2020
ms.locfileid: "77415513"
---
# <a name="remove-devices-by-using-wipe-retire-or-manually-unenrolling-the-device"></a>Usuwanie urządzeń przy użyciu czyszczenia, wycofywania lub ręcznego wyrejestrowywania urządzenia

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Za pomocą akcji **Wycofaj** lub **Wyczyść** możesz usunąć z usługi Intune urządzenia, które nie są już potrzebne, mają inne zastosowanie lub zostały zagubione. Użytkownicy mogą też w aplikacji Portal firmy usługi Intune wydać polecenie zdalne do urządzeń zarejestrowanych w usłudze Intune.

> [!NOTE]
> Zanim usuniesz użytkownika z usługi Azure Active Directory, użyj akcji **Wyczyść** lub **Wycofaj** na wszystkich urządzeniach skojarzonych z tym użytkownikiem. Jeśli usuniesz użytkowników mających zarządzane urządzenia z usługi Azure AD, usługa Intune nie będzie już mogła wydawać tym urządzeniom poleceń wyczyszczenia lub wycofania.

## <a name="wipe"></a>Czyszczenie danych

Akcja **Wyczyść** przywraca domyślne ustawienia fabryczne na urządzeniu. Jeśli pole wyboru **Zachowaj stan rejestracji i konto użytkownika** zostało zaznaczone, dane użytkownika są zachowywane. W przeciwnym razie wszystkie dane, aplikacje i ustawienia zostaną usunięte.

|Akcja Wyczyść|**Zachowaj stan rejestracji i konto użytkownika**|Usunięto z zarządzania przez usługę Intune|Opis|
|:-------------:|:------------:|:------------:|------------|
|**Czyszczenie danych**| Nie zaznaczono | Tak | Czyści wszystkie konta użytkowników, dane, zasady zarządzania urządzeniami przenośnymi i ustawienia. Resetuje system operacyjny do domyślnego stanu i ustawień.|
|**Czyszczenie danych**| Zaznaczono | Nie | Czyści wszystkie zasady zarządzania urządzeniami przenośnymi. Zachowuje konta i dane użytkowników. Przywraca domyślne ustawienia użytkownika. Resetuje system operacyjny do domyślnego stanu i ustawień.|


> [!NOTE]
> Akcja czyszczenia nie jest dostępna dla urządzeń z systemem iOS/iPadOS zarejestrowanych w ramach rejestracji użytkownika.

Opcja **Zachowaj stan rejestracji i konto użytkownika** jest dostępna tylko w wersji 1709 systemu Windows 10 lub nowszej.

Opcja **Wykonaj chronione czyszczenie** zapewnia, że nie można obejść akcji czyszczenia przez wyłączenie urządzenia. Funkcja chronionego czyszczenia będzie ponawiać próby zresetowania urządzenia do momentu pomyślnego przeprowadzenia czyszczenia. W przypadku niektórych konfiguracji ta akcja może pozostawić urządzenie w stanie, który uniemożliwia jego ponowne uruchomienie.

Zasady zarządzania urządzeniami przenośnymi zostaną zastosowane przy następnym połączeniu urządzenia z usługą Intune.

Czyszczenie jest przydatne w przypadku resetowania urządzenia przed przekazaniem go nowemu użytkownikowi albo w przypadku utraty lub kradzieży urządzenia. Należy rozważnie korzystać z funkcji **Wyczyść**. Nie będzie można odzyskać danych na urządzeniu.

### <a name="wiping-a-device"></a>Czyszczenie urządzenia

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Wybierz pozycję **Urządzenia** > **Wszystkie urządzenia**.
4. Wybierz nazwę urządzenia, które chcesz wyczyścić.
5. W okienku wyświetlającym nazwę urządzenia wybierz pozycję **Wyczyść**.
6. W systemie Windows 10 w wersji 1709 lub nowszej możesz też użyć opcji **Wyczyść urządzenie, lecz zachowaj stan rejestracji i skojarzone konto użytkownika**. 
    
    |Zachowywane podczas czyszczenia |Niezachowane|
    | -------------|------------|
    |Konta użytkowników skojarzone z urządzeniem|Pliki użytkownika|
    |Stan maszyny \(przyłączenie do domeny, dołączenie do usługi Azure AD)| Aplikacje zainstalowane przez użytkownika \(aplikacje ze Sklepu i aplikacje Win32)|
    |Rejestracja zarządzania urządzeniami przenośnymi|Ustawienia urządzenia inne niż domyślne|
    |Aplikacje zainstalowane przez producenta OEM \(aplikacje ze Sklepu i aplikacje Win32)||
    |Profil użytkownika||
    |Dane użytkownika przechowywane poza jego profilem||
    |Informacje o logowaniu automatycznym użytkownika|| 
    
         
7. Aby potwierdzić czyszczenie, wybierz opcję **Tak**.

Jeśli urządzenie jest włączone i połączone, propagowanie akcji **Wyczyść** do wszystkich typów urządzeń potrwa mniej niż 15 minut.

## <a name="retire"></a>Wycofaj

Akcja **Wycofaj** powoduje usunięcie zarządzanych danych aplikacji (jeśli dotyczy), ustawień i profilów poczty e-mail, które zostały przypisane przy użyciu usługi Intune. Urządzenie jest usuwane z zarządzania przez usługę Intune. Stanie się tak, gdy urządzenie zostanie zameldowane kolejny raz i otrzyma zdalną akcję **Wycofaj**. Urządzenie nadal jest widoczne w usłudze Intune do czasu zaewidencjonowania urządzenia. Jeśli chcesz natychmiast usunąć nieaktywne urządzenia, użyj akcji [Usuń](devices-wipe.md#delete-devices-from-the-intune-portal).

Akcja **Wycofaj** nie powoduje usunięcia osobistych danych użytkownika z urządzenia.  

W poniższych tabelach opisano usuwane dane oraz wpływ akcji **Wycofaj** na dane pozostające na urządzeniu po usunięciu danych firmowych.

### <a name="ios"></a>iOS

|Typ danych|iOS|
|-------------|-------|
|Aplikacje firmowe i skojarzone dane zainstalowane za pomocą usługi Intune|**Aplikacje zainstalowane za pomocą aplikacji Portal firmy:** W przypadku aplikacji przypiętych do profilu zarządzania usuwane są wszystkie aplikacje i dane aplikacji. Te aplikacje obejmują aplikacje oryginalnie zainstalowane ze sklepu App Store i później zarządzane jako aplikacje firmowe, chyba że aplikacja nie została skonfigurowana do odinstalowania po usunięciu urządzenia. <br /><br /> **Aplikacje firmy Microsoft używające funkcji zarządzania aplikacjami mobilnymi i zainstalowane ze sklepu App Store:** W przypadku aplikacji, które nie są zarządzane za pomocą aplikacji Portal firmy, usuwane są dane aplikacji firmowych, które są chronione za pomocą szyfrowania zarządzania aplikacjami mobilnymi (MAM) w lokalnym magazynie aplikacji. Dane chronione przez szyfrowanie MAM poza aplikacją pozostają zaszyfrowane i nie można ich używać, ale nie są usuwane. Dane aplikacji osobistych i aplikacje nie są usuwane.|
|Ustawienia|Konfiguracje, które były ustawione przez zasady usługi Intune, nie są już wymuszane. Użytkownicy mogą zmieniać ustawienia.|
|Ustawienia profili sieci Wi-Fi i sieci VPN|Usuwane.|
|Ustawienia profili certyfikatów|Certyfikaty zostaną usunięte i odwołane.|
|Agent zarządzania|Profil zarządzania jest usuwany.|
|Poczta e-mail|Profile poczty e-mail aprowizowane za pośrednictwem usługi Intune są usuwane. Poczta e-mail zapisana w pamięci podręcznej na urządzeniu jest usuwana.|
|Odłączenie usługi Azure AD|Rekord usługi Azure AD jest usuwany.|

### <a name="android"></a>Android

|Typ danych|Android|Android Samsung Knox Standard|
|-------------|-----------|------------------------|
|Linki sieci Web|Usuwane.|Usuwane.|
|Aplikacje niezarządzane ze sklepu Google Play|Aplikacje i dane pozostają zainstalowane. <br /> <br />Usuwane są dane aplikacji firmowych, które są chronione za pomocą szyfrowania zarządzania aplikacjami mobilnymi (MAM) w lokalnym magazynie aplikacji. Dane chronione przez szyfrowanie MAM poza aplikacją pozostają zaszyfrowane i nie można ich używać, ale nie są usuwane. |Aplikacje i dane pozostają zainstalowane. <br /> <br />Usuwane są dane aplikacji firmowych, które są chronione za pomocą szyfrowania zarządzania aplikacjami mobilnymi (MAM) w lokalnym magazynie aplikacji. Dane chronione przez szyfrowanie MAM poza aplikacją pozostają zaszyfrowane i nie można ich używać, ale nie są usuwane.|
|Niezarządzane aplikacje biznesowe|Aplikacje i dane pozostają zainstalowane.|Aplikacje są odinstalowywane, a lokalne dane aplikacji są usuwane. Żadne dane poza aplikacją (np. na karcie SD) nie są usuwane.|
|Aplikacje zarządzane ze sklepu Google Play|Dane aplikacji zostaną usunięte. Aplikacja nie jest usuwana. Dane chronione przez szyfrowanie funkcji zarządzania aplikacjami MAM poza aplikacją (np. karta SD) pozostają zaszyfrowane i nie można ich używać, ale nie są usuwane.|Dane aplikacji zostaną usunięte. Aplikacja nie jest usuwana. Dane chronione przez szyfrowanie MAM poza aplikacją (np. karta SD) pozostają zaszyfrowane, ale nie są usuwane.|
|Zarządzane aplikacje biznesowe|Dane aplikacji zostaną usunięte. Aplikacja nie jest usuwana. Dane chronione przez szyfrowanie MAM poza aplikacją (np. karta SD) pozostają zaszyfrowane i nie można ich używać, ale nie są usuwane.|Dane aplikacji zostaną usunięte. Aplikacja nie jest usuwana. Dane chronione przez szyfrowanie MAM poza aplikacją (np. karta SD) pozostają zaszyfrowane i nie można ich używać, ale nie są usuwane.|
|Ustawienia|Konfiguracje, które były ustawione przez zasady usługi Intune, nie są już wymuszane. Użytkownicy mogą zmieniać ustawienia.|Konfiguracje, które były ustawione przez zasady usługi Intune, nie są już wymuszane. Użytkownicy mogą zmieniać ustawienia.|
|Ustawienia profili sieci Wi-Fi i sieci VPN|Usuwane.|Usuwane.|
|Ustawienia profili certyfikatów|Certyfikaty są odwoływane, ale nie są usuwane.|Certyfikaty zostaną usunięte i odwołane.|
|Agent zarządzania|Uprawnienie administratora urządzenia jest odwoływane.|Uprawnienie administratora urządzenia jest odwoływane.|
|Poczta e-mail|Nie dotyczy (profile poczty e-mail nie są obsługiwane przez urządzenia z systemem Android)|Profile poczty e-mail aprowizowane za pośrednictwem usługi Intune są usuwane. Poczta e-mail zapisana w pamięci podręcznej na urządzeniu jest usuwana.|
|Odłączenie usługi Azure AD|Rekord usługi Azure AD jest usuwany.|Rekord usługi Azure AD jest usuwany.|

### <a name="android-work-profile"></a>Profil służbowy systemu Android

Usunięcie danych firmy z urządzenia z profilem służbowym systemu Android spowoduje usunięcie wszystkich danych, aplikacji i ustawień z profilu służbowego na tym urządzeniu. Urządzenie jest wycofywane z zarządzania za pomocą usługi Intune. Czyszczenie nie jest obsługiwane w przypadku profilów służbowych systemu Android.

### <a name="android-enterprise-kiosk-devices"></a>Urządzenia kiosku w rozwiązaniu Android enterprise

Urządzenia kiosku możesz tylko wyczyścić. Nie możesz wycofywać urządzeń kiosku z systemem Android.


### <a name="macos"></a>macOS

|Typ danych|macOS|
|-------------|-------|
|Ustawienia|Konfiguracje, które były ustawione przez zasady usługi Intune, nie są już wymuszane. Użytkownicy mogą zmieniać ustawienia.|
|Ustawienia profili sieci Wi-Fi i sieci VPN|Usuwane.|
|Ustawienia profili certyfikatów|Certyfikaty wdrożone za pomocą oprogramowania MDM są usuwane i odwoływane.|
|Agent zarządzania|Profil zarządzania jest usuwany.|
|Outlook|W przypadku włączenia dostępu warunkowego urządzenie nie będzie odbierać nowych wiadomości e-mail.|
|Odłączenie usługi Azure AD|Rekord usługi Azure AD jest usuwany.|

### <a name="windows"></a>Windows

|Typ danych|Windows 8.1 (MDM) i Windows RT 8.1|Windows RT|Windows Phone 8.1 i Windows Phone 8|Windows 10|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Aplikacje firmowe i skojarzone dane zainstalowane za pomocą usługi Intune|Klucze dla plików chronionych przez system szyfrowania plików są odwoływane. Użytkownik nie może otworzyć plików.|Aplikacje firmowe nie są usuwane.|Aplikacje zainstalowane pierwotnie za pośrednictwem portalu firmy są odinstalowywane. Dane aplikacji firmowych zostaną usunięte.|Aplikacje zostaną odinstalowane. Klucze ładowania bezpośredniego są usuwane.<br>W przypadku systemu Windows 10 w wersji 1703 (aktualizacja dla twórców) lub nowszej aplikacje usługi Office 365 ProPlus nie są usuwane. Aplikacje Win32 zainstalowane za pomocą rozszerzenia do zarządzania usługi Intune nie zostaną odinstalowane na wyrejestrowanych urządzeniach. Administratorzy mogą korzystać z wykluczania przypisania, aby nie oferować aplikacji Win32 na urządzeniach BYOD.|
|Ustawienia|Konfiguracje, które były ustawione przez zasady usługi Intune, nie są już wymuszane. Użytkownicy mogą zmieniać ustawienia.|Konfiguracje, które były ustawione przez zasady usługi Intune, nie są już wymuszane. Użytkownicy mogą zmieniać ustawienia.|Konfiguracje, które były ustawione przez zasady usługi Intune, nie są już wymuszane. Użytkownicy mogą zmieniać ustawienia.|Konfiguracje, które były ustawione przez zasady usługi Intune, nie są już wymuszane. Użytkownicy mogą zmieniać ustawienia.|
|Ustawienia profili sieci Wi-Fi i sieci VPN|Usuwane.|Usuwane.|Nieobsługiwane.|Usuwane.|
|Ustawienia profili certyfikatów|Certyfikaty zostaną usunięte i odwołane.|Certyfikaty zostaną usunięte i odwołane.|Nieobsługiwane.|Certyfikaty zostaną usunięte i odwołane.|
|Poczta e-mail|Usuwa pocztę e-mail obsługującą system szyfrowania plików. Dotyczy to także wiadomości e-mail i załączników w aplikacji Poczta dla systemu Windows.|Nieobsługiwane.|Profile poczty e-mail aprowizowane za pośrednictwem usługi Intune są usuwane. Poczta e-mail zapisana w pamięci podręcznej na urządzeniu jest usuwana.|Usuwa pocztę e-mail obsługującą system szyfrowania plików. Dotyczy to także wiadomości e-mail i załączników w aplikacji Poczta dla systemu Windows. Usuwa konta poczty zaaprowizowane przez usługę Intune.|
|Odłączenie usługi Azure AD|Nie.|Nie.|Rekord usługi Azure AD jest usuwany.|Rekord usługi Azure AD jest usuwany.|

> [!NOTE]
> W przypadku urządzeń z systemem Windows 10 przyłączonych do usługi Azure AD podczas początkowej instalacji (OOBE) polecenie wycofania spowoduje usunięcie wszystkich kont usługi Azure AD z urządzenia. Wykonaj kroki opisane w temacie [Uruchamianie komputera w trybie awaryjnym](https://support.microsoft.com/en-us/help/12376/windows-10-start-your-pc-in-safe-mode), aby zalogować się jako administrator lokalny i odzyskać dostęp do lokalnych danych użytkownika. 

### <a name="retire"></a>Wycofaj

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. W okienku **Urządzenia** wybierz pozycję **Wszystkie urządzenia**.
3. Wybierz nazwę urządzenia, które chcesz wycofać.
4. W okienku wyświetlającym nazwę urządzenia wybierz pozycję **Wycofaj**. Wybierz pozycję **Tak**, aby potwierdzić.

Jeśli urządzenie jest włączone i połączone, propagowanie akcji **Wycofaj** do wszystkich typów urządzeń potrwa mniej niż 15 minut.

## <a name="delete-devices-from-the-intune-portal"></a>Usuwanie urządzeń z portalu usługi Intune

Jeśli chcesz usunąć urządzenia z portalu usługi Intune, możesz usunąć je z okienka określonego urządzenia. Przy następnym zaewidencjonowaniu urządzenia zostaną z niego usunięte wszystkie dane firmy.

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz kolejno pozycje **Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenia do usunięcia > **Usuń**.

### <a name="automatically-delete-devices-with-cleanup-rules"></a>Automatyczne usuwanie urządzeń przy użyciu reguł oczyszczania
Usługę Intune można skonfigurować tak, aby automatycznie usuwała urządzenia, które wyglądają na nieaktywne lub nieaktualne albo które nie odpowiadają. Te reguły oczyszczania stale monitorują spis urządzeń, aby zapewnić aktualność rekordów urządzeń. Urządzenia usunięte w ten sposób są usuwane z obszaru zarządzania usługi Intune.
1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz kolejno pozycje **Urządzenia** > **Reguły czyszczenia urządzeń** > **Tak**.
3. W polu **Usuń urządzenia, które nie zostały zaewidencjonowane przez następującą liczbę dni** wprowadź liczbę z zakresu od 30 do 270.
4. Wybierz polecenie **Zapisz**.



## <a name="delete-devices-from-the-azure-active-directory-portal"></a>Usuwanie urządzeń z portalu usługi Azure Active Directory

Usunięcie urządzeń z usługi Azure AD może być konieczne z powodu problemów z komunikacją lub braku urządzeń. Za pomocą akcji **Usuń** możesz usunąć rekordy urządzeń z witryny Azure Portal, gdy wiesz, że urządzenia są niedostępne i najprawdopodobniej nie będą się ponownie komunikować z platformą Azure. Akcja **Usuń** nie usuwa urządzenia z zarządzania.

1. Zaloguj się do [usługi Azure Active Directory w witrynie Azure Portal](https://aka.ms/accessaad) przy użyciu poświadczeń administratora. Możesz również zalogować się do [centrum administracyjnego platformy Microsoft 365](https://admin.microsoft.com). Z menu wybierz pozycję **Centra administracyjne** > **Azure AD**.
2. Utwórz subskrypcję platformy Azure, jeśli jej nie masz. Jeśli masz płatne konto, ta operacja nie powinna wymagać uiszczenia płatności ani podania danych karty kredytowej (wybierz link do subskrypcji **Zarejestruj bezpłatny katalog Azure Active Directory**).
3. Wybierz pozycję **Azure Active Directory**, a następnie wybierz organizację.
4. Wybierz kartę **Użytkownicy** .
5. Wybierz użytkownika skojarzonego z urządzeniem, które chcesz usunąć.
6. Wybierz pozycję **Urządzenia**.
7. Usuń urządzenia zgodnie z potrzebami. Na przykład możesz usunąć urządzenia, które nie są już używane lub zawierają niedokładne definicje.

## <a name="retire-an-apple-dep-device-from-intune"></a>Wycofywanie urządzenia Apple DEP z usługi Intune

Jeśli chcesz całkowicie usunąć urządzenie Apple DEP z zarządzania przez usługę Intune, wykonaj następujące kroki:

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Urządzenia** > **Wszystkie urządzenia**, a następnie wybierz urządzenie i opcję **Wycofaj**.
![Zrzut ekranu przedstawiający opcję Wycofaj](./media/devices-wipe/retire.png)
3. Odwiedź witrynę [deploy.apple.com](http://deploy.apple.com) i wyszukaj urządzenie według jego numeru seryjnego.
4. W menu **Assigned to (Przypisane do)** wybierz pozycję **Unassigned (Nieprzypisane)** .

5. Wybierz przycisk **Reassign (Przypisz ponownie)** .

    ![Zrzut ekranu przedstawiający ponowne przypisanie urządzenia Apple](./media/devices-wipe/apple-reassign.png)

## <a name="fresh-start"></a>Rozpoczęcie od nowa

Dotyczy urządzeń z systemem Windows 10. Przeczytaj więcej na temat funkcji [Rozpoczęcie od nowa](device-fresh-start.md).

## <a name="next-steps"></a>Następne kroki

Jeśli chcesz ponownie zarejestrować usunięte urządzenie, zobacz [Opcje rejestracji](../enrollment/enrollment-options.md).

