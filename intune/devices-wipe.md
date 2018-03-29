---
title: Usuwanie danych firmowych z urządzeń przy użyciu usługi Microsoft Intune — Azure | Microsoft Docs
description: Usuń dane firmowe z urządzenia lub wykonaj reset do ustawień fabrycznych w przypadku urządzeń z systemem Android, Android for Work, iOS, macOS lub Windows, korzystając z usługi Microsoft Intune. Ponadto możesz usunąć urządzenie z usługi Azure Active Directory.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4fdb787e-084f-4507-9c63-c96b13bfcdf9
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e4581b59de68c2877b122887fa1ffe86eaa2b92c
ms.sourcegitcommit: 390a4be5aa36007c36fb6a5abcfe8d20bc862a4b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/22/2018
---
# <a name="remove-devices-by-using-factory-reset-or-remove-company-data"></a>Usuwanie urządzeń za pomocą resetowania do ustawień fabrycznych lub usuwania danych firmy

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Z usługi Intune możesz usunąć urządzenia, które nie są już potrzebne, mają inne zastosowanie lub zostały zagubione. Możesz to zrobić przy użyciu akcji **Usuń dane firmowe** lub **Resetowanie do ustawień fabrycznych**. Użytkownicy mogą też w aplikacji Portal firmy usługi Intune wydać polecenie zdalne do urządzeń będących własnością prywatną i zarejestrowanych w usłudze Intune.

> [!NOTE]
> Zanim usuniesz użytkownika z usługi Azure Active Directory, użyj akcji **Resetowanie do ustawień fabrycznych** lub **Usuń dane firmowe** na wszystkich urządzeniach skojarzonych z tym użytkownikiem. Jeśli usuniesz użytkowników mających zarządzane urządzenia z usługi Azure AD, usługa Intune nie będzie już mogła wydawać tym urządzeniom poleceń resetowania do ustawień fabrycznych ani usuwania danych firmowych.

## <a name="factory-reset"></a>Resetowanie do ustawień fabrycznych

Akcja **Resetowanie do ustawień fabrycznych** przywraca domyślne ustawienia fabryczne na urządzeniu. Reset do ustawień fabrycznych spowoduje usunięcie wszystkich ustawień i danych firmowych oraz użytkownika. Urządzenie jest usuwane z zarządzania przez usługę Intune. Reset do ustawień fabrycznych jest przydatny w przypadku resetowania urządzenia przed przekazaniem go nowemu użytkownikowi albo w przypadku utraty lub kradzieży urządzenia. Rozważnie korzystaj z funkcji **Resetowanie do ustawień fabrycznych**. Nie będzie można odzyskać danych na urządzeniu.

### <a name="factory-reset-a-device"></a>Resetowanie urządzenia do ustawień fabrycznych

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz opcję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz pozycję **Urządzenia** > **Wszystkie urządzenia**.
4. Wybierz nazwę urządzenia, które chcesz zresetować do ustawień fabrycznych.
5. W okienku wyświetlającym nazwę urządzenia wybierz pozycję **Resetowanie do ustawień fabrycznych**.
6. W systemie Windows 10 w wersji 1709 lub nowszej możesz też użyć opcji **Zachowaj stan rejestracji i konto użytkownika**. 
    
    |Zachowywane podczas resetowania do ustawień fabrycznych|Niezachowane|
    | -------------|------------|
    |Konta użytkowników skojarzone z urządzeniem|Pliki użytkownika|
    |Stan maszyny \(przyłączenie do domeny, dołączenie do usługi Azure AD)| Aplikacje zainstalowane przez użytkownika \(aplikacje ze Sklepu i aplikacje Win32)|
    |Rejestracja zarządzania urządzeniami przenośnymi|Ustawienia urządzenia inne niż domyślne|
    |Aplikacje zainstalowane przez producenta OEM \(aplikacje ze Sklepu i aplikacje Win32)||
    |Profil użytkownika||
    |Dane użytkownika przechowywane poza jego profilem||
    |Informacje o logowaniu automatycznym użytkownika|| 
    
         
7. Wybierz przycisk **Tak**, aby potwierdzić reset do ustawień fabrycznych.

Jeśli urządzenie jest włączone i połączone, propagowanie akcji **Resetowanie do ustawień fabrycznych** do wszystkich typów urządzeń potrwa mniej niż 15 minut.

## <a name="remove-company-data"></a>Usuwanie danych firmy

Akcja **Usuń dane firmowe** powoduje usunięcie zarządzanych danych aplikacji (jeśli dotyczy), ustawień i profilów poczty e-mail, które zostały przypisane przy użyciu usługi Intune. Akcja **Usuń dane firmowe** nie powoduje usunięcia osobistych danych użytkownika z urządzenia. Urządzenie jest usuwane z zarządzania przez usługę Intune. 

W poniższych tabelach opisano usuwane dane oraz wpływ akcji **Usuń dane firmowe** na dane pozostające na urządzeniu po usunięciu danych firmowych.

### <a name="ios"></a>iOS

|Typ danych|iOS|
|-------------|-------|
|Aplikacje firmowe i skojarzone dane zainstalowane za pomocą usługi Intune|Aplikacje zostaną odinstalowane. Dane aplikacji firmowych zostaną usunięte.<br /><br />Dane aplikacji firmy Microsoft korzystających z zarządzania aplikacjami mobilnymi zostaną usunięte. Aplikacja nie zostanie usunięta.|
|Ustawienia|Konfiguracje, które były ustawione przez zasady usługi Intune, nie są już wymuszane. Użytkownicy mogą zmieniać ustawienia.|
|Ustawienia profili sieci Wi-Fi i sieci VPN|Usuwane.|
|Ustawienia profili certyfikatów|Certyfikaty zostaną usunięte i odwołane.|
|Agent zarządzania|Profil zarządzania jest usuwany.|
|Poczta e-mail|Profile poczty e-mail aprowizowane za pośrednictwem usługi Intune są usuwane. Poczta e-mail zapisana w pamięci podręcznej na urządzeniu jest usuwana.|
|Outlook|Wiadomości e-mail odebrane w aplikacji Microsoft Outlook dla systemu iOS są usuwane.|
|Odłączenie usługi Azure AD|Rekord usługi Azure AD jest usuwany.|
|Kontakty |Kontakty synchronizowane bezpośrednio z aplikacji do natywnej książki adresowej są usuwane. Nie można usunąć wszystkich kontaktów zsynchronizowanych z natywnej książki adresowej do innego źródła zewnętrznego. <br /> <br />Aktualnie obsługiwana jest tylko aplikacja Outlook.

### <a name="android"></a>Android

|Typ danych|Android|Android Samsung Knox Standard|
|-------------|-----------|------------------------|
|Linki sieci Web|Usuwane.|Usuwane.|
|Aplikacje niezarządzane ze sklepu Google Play|Aplikacje i dane pozostają zainstalowane.|Aplikacje i dane pozostają zainstalowane.|
|Niezarządzane aplikacje biznesowe|Aplikacje i dane pozostają zainstalowane.|Aplikacje są odinstalowywane, a lokalne dane aplikacji są usuwane. Żadne dane poza aplikacją (np. na karcie SD) nie są usuwane.|
|Aplikacje zarządzane ze sklepu Google Play|Dane aplikacji zostaną usunięte. Aplikacja nie jest usuwana. Dane chronione przez szyfrowanie funkcji zarządzania aplikacjami mobilnymi (MAM, Mobile Application Management) poza aplikacją (np. karta SD) pozostają zaszyfrowane i nie można ich używać, ale nie są usuwane.|Dane aplikacji zostaną usunięte. Aplikacja nie jest usuwana. Dane chronione przez szyfrowanie MAM poza aplikacją (np. karta SD) pozostają zaszyfrowane, ale nie są usuwane.|
|Zarządzane aplikacje biznesowe|Dane aplikacji zostaną usunięte. Aplikacja nie jest usuwana. Dane chronione przez szyfrowanie MAM poza aplikacją (np. karta SD) pozostają zaszyfrowane i nie można ich używać, ale nie są usuwane.|Dane aplikacji zostaną usunięte. Aplikacja nie jest usuwana. Dane chronione przez szyfrowanie MAM poza aplikacją (np. karta SD) pozostają zaszyfrowane i nie można ich używać, ale nie są usuwane.|
|Ustawienia|Konfiguracje, które były ustawione przez zasady usługi Intune, nie są już wymuszane. Użytkownicy mogą zmieniać ustawienia.|Konfiguracje, które były ustawione przez zasady usługi Intune, nie są już wymuszane. Użytkownicy mogą zmieniać ustawienia.|
|Ustawienia profili sieci Wi-Fi i sieci VPN|Usuwane.|Usuwane.|
|Ustawienia profili certyfikatów|Certyfikaty są odwoływane, ale nie są usuwane.|Certyfikaty zostaną usunięte i odwołane.|
|Agent zarządzania|Uprawnienie administratora urządzenia jest odwoływane.|Uprawnienie administratora urządzenia jest odwoływane.|
|Poczta e-mail|Nie dotyczy (profile poczty e-mail nie są obsługiwane przez urządzenia z systemem Android)|Profile poczty e-mail aprowizowane za pośrednictwem usługi Intune są usuwane. Poczta e-mail zapisana w pamięci podręcznej na urządzeniu jest usuwana.|
|Outlook|Poczta e-mail odebrana przez aplikację Outlook dla systemu Android jest usuwana, ale tylko w przypadku, gdy program Outlook jest chroniony przy użyciu zasad zarządzania aplikacjami mobilnymi. W przeciwnym razie program Outlook nie jest czyszczony podczas wyrejestrowywania urządzenia.|Poczta e-mail odebrana przez aplikację Outlook dla systemu Android jest usuwana, ale tylko w przypadku, gdy program Outlook jest chroniony przy użyciu zasad zarządzania aplikacjami mobilnymi. W przeciwnym razie program Outlook nie jest czyszczony podczas wyrejestrowywania urządzenia.|
|Odłączenie usługi Azure AD|Rekord usługi Azure AD jest usuwany.|Rekord usługi Azure AD jest usuwany.|
|Kontakty |Kontakty synchronizowane bezpośrednio z aplikacji do natywnej książki adresowej są usuwane. Nie można usunąć wszystkich kontaktów zsynchronizowanych z natywnej książki adresowej do innego źródła zewnętrznego. <br /> <br />Aktualnie obsługiwana jest tylko aplikacja Outlook.|Kontakty synchronizowane bezpośrednio z aplikacji do natywnej książki adresowej są usuwane. Nie można usunąć wszystkich kontaktów zsynchronizowanych z natywnej książki adresowej do innego źródła zewnętrznego. <br /> <br />Aktualnie obsługiwana jest tylko aplikacja Outlook.

### <a name="android-for-work"></a>Program Android for Work

Usunięcie danych firmy z urządzenia z programem Android for Work spowoduje usunięcie wszystkich danych, aplikacji i ustawień z profilu służbowego na tym urządzeniu. Urządzenie jest wycofywane z zarządzania za pomocą usługi Intune. Resetowanie do ustawień fabrycznych nie jest obsługiwane w przypadku programu Android for Work.


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

|Typ danych|Windows 8.1 (MDM) i Windows RT 8.1|Windows RT|Windows Phone 8.1 i Windows Phone 8|Windows 10|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Aplikacje firmowe i skojarzone dane zainstalowane za pomocą usługi Intune|Klucze dla plików chronionych przez system szyfrowania plików są odwoływane. Użytkownik nie może otworzyć plików.|Aplikacje firmowe nie są usuwane.|Aplikacje zainstalowane pierwotnie za pośrednictwem portalu firmy są odinstalowywane. Dane aplikacji firmowych zostaną usunięte.|Aplikacje zostaną odinstalowane. Klucze ładowania bezpośredniego są usuwane.<br>W przypadku systemu Windows 10 w wersji 1703 (aktualizacja dla twórców) lub nowszej aplikacje usługi Office 365 ProPlus nie są usuwane.|
|Ustawienia|Konfiguracje, które były ustawione przez zasady usługi Intune, nie są już wymuszane. Użytkownicy mogą zmieniać ustawienia.|Konfiguracje, które były ustawione przez zasady usługi Intune, nie są już wymuszane. Użytkownicy mogą zmieniać ustawienia.|Konfiguracje, które były ustawione przez zasady usługi Intune, nie są już wymuszane. Użytkownicy mogą zmieniać ustawienia.|Konfiguracje, które były ustawione przez zasady usługi Intune, nie są już wymuszane. Użytkownicy mogą zmieniać ustawienia.|
|Ustawienia profili sieci Wi-Fi i sieci VPN|Usuwane.|Usuwane.|Nieobsługiwane.|Usuwane.|
|Ustawienia profili certyfikatów|Certyfikaty zostaną usunięte i odwołane.|Certyfikaty zostaną usunięte i odwołane.|Nieobsługiwane.|Certyfikaty zostaną usunięte i odwołane.|
|Poczta e-mail|Usuwa pocztę e-mail obsługującą system szyfrowania plików. Dotyczy to także wiadomości e-mail i załączników w aplikacji Poczta dla systemu Windows.|Nieobsługiwane.|Profile poczty e-mail aprowizowane za pośrednictwem usługi Intune są usuwane. Poczta e-mail zapisana w pamięci podręcznej na urządzeniu jest usuwana.|Usuwa pocztę e-mail obsługującą system szyfrowania plików. Dotyczy to także wiadomości e-mail i załączników w aplikacji Poczta dla systemu Windows. Usuwa konta poczty zaaprowizowane przez usługę Intune.|
|Odłączenie usługi Azure AD|Nie.|Nie.|Rekord usługi Azure AD jest usuwany.|Nie dotyczy. W systemie Windows 10 nie można usunąć danych firmowych w przypadku urządzeń przyłączonych do usługi Azure AD.|

### <a name="remove-company-data"></a>Usuwanie danych firmy

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Urządzenia** wybierz pozycję **Wszystkie urządzenia**.
4. Wybierz nazwę urządzenia, z którego chcesz usunąć dane firmowe.
5. W okienku wyświetlającym nazwę urządzenia wybierz pozycję **Usuń dane firmowe**. Wybierz pozycję **Tak**, aby potwierdzić.

Jeśli urządzenie jest włączone i połączone, propagowanie akcji **Usuń dane firmowe** do wszystkich typów urządzeń potrwa mniej niż 15 minut.

## <a name="delete-devices-from-the-azure-active-directory-portal"></a>Usuwanie urządzeń z portalu usługi Azure Active Directory

Usunięcie urządzeń z usługi Azure AD może być konieczne z powodu problemów z komunikacją lub braku urządzeń. Za pomocą akcji **Usuń** możesz usunąć rekordy urządzeń z witryny Azure Portal, gdy wiesz, że urządzenia są niedostępne i najprawdopodobniej nie będą się ponownie komunikować z platformą Azure. Akcja **Usuń** nie usuwa urządzenia z zarządzania.

1.  Zaloguj się do [usługi Azure Active Directory w witrynie Azure Portal](http://aka.ms/accessaad) przy użyciu poświadczeń administratora. Możesz też zalogować się do [portalu usługi Office 365](https://portal.office.com). Z menu wybierz pozycję **Centra administracyjne** > **Azure AD**.
2.  Utwórz subskrypcję platformy Azure, jeśli jej nie masz. Jeśli masz płatne konto, ta operacja nie powinna wymagać uiszczenia płatności ani podania danych karty kredytowej (wybierz link do subskrypcji **Zarejestruj bezpłatny katalog Azure Active Directory**).
3.  Wybierz pozycję **Azure Active Directory**, a następnie wybierz organizację.
4.  Wybierz kartę **Użytkownicy** .
5. Wybierz użytkownika skojarzonego z urządzeniem, które chcesz usunąć.
6.  Wybierz pozycję **Urządzenia**.
7.  Usuń urządzenia zgodnie z potrzebami. Na przykład możesz usunąć urządzenia, które nie są już używane lub zawierają niedokładne definicje.
