---
title: "Korzystanie z resetowania do ustawień fabrycznych lub usuwania danych firmy na urządzeniach przy użyciu usługi Intune"
titlesuffix: Azure portal
description: "Dowiedz się, jak usunąć dane firmy z urządzenia lub zresetować urządzenie do ustawień fabrycznych."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4fdb787e-084f-4507-9c63-c96b13bfcdf9
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 54def958cb82709f55b3c5f75d85f3b530e3d70b
ms.sourcegitcommit: 229f9bf89efeac3eb3d28dff01e9a77ddbf618eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/05/2018
---
# <a name="remove-devices-by-using-factory-reset-or-remove-company-data"></a>Usuwanie urządzeń za pomocą resetowania do ustawień fabrycznych lub usuwania danych firmy

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Z usługi Intune możesz usunąć urządzenia, które nie są już potrzebne, mają inne zastosowanie lub zostały zagubione. Możesz to zrobić przy użyciu polecenia **usunięcia danych firmy** lub **zresetowania do ustawień fabrycznych**. Użytkownicy mogą też wydać z aplikacji Portal firmy usługi Intune polecenie do urządzeń będących własnością prywatną i zarejestrowanych w usłudze Intune.

> [!NOTE]
> Zanim usuniesz użytkownika z usługi Azure Active Directory, wydaj polecenie **zresetowania do ustawień fabrycznych** lub **usunięcia danych firmy** wszystkim urządzeniom skojarzonym z tym użytkownikiem. Jeśli usuniesz użytkowników z zarządzanymi urządzeniami z usługi Azure Active Directory, usługa Intune nie może już wydawać poleceń resetowania do ustawień fabrycznych lub usuwania danych firmy do tych urządzeń.

## <a name="factory-reset"></a>Resetowanie do ustawień fabrycznych

**Resetowanie do ustawień fabrycznych** przywraca ustawienia fabryczne urządzenia, usuwając wszystkie dane i ustawienia dotyczące firmy oraz użytkownika. Urządzenie jest usuwane z zarządzania przez usługę Intune. Resetowanie do ustawień fabrycznych jest przydatne w przypadku resetowania urządzenia przed przekazaniem go nowemu użytkownikowi albo w przypadku utraty lub kradzieży urządzenia. Należy rozważnie korzystać z funkcji resetowania do ustawień fabrycznych. Nie będzie można odzyskać danych na urządzeniu.

### <a name="to-factory-reset-a-device"></a>Aby zresetować urządzenie do ustawień fabrycznych

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Urządzenia i grupy** wybierz pozycję **Wszystkie urządzenia**.
4. Wybierz nazwę urządzenia, które chcesz zresetować do ustawień fabrycznych.
5. W bloku, w którym wyświetlona jest nazwa urządzenia, wybierz pozycję **Resetowanie do ustawień fabrycznych**.
6. W systemie Windows 10 w wersji 1709 lub nowszej istnieje dodatkowa opcja „Zachowaj stan rejestracji i konto użytkownika”. 
    
    |Zachowywanie w przypadku resetowania do ustawień fabrycznych|Niezachowane|
    | -------------|------------|
    |Konta użytkowników skojarzone z urządzeniem|Pliki użytkownika|
    |Stan komputera \(dołączenie do domeny, dołączenie do usługi Azure Active Directory)| Aplikacje zainstalowane przez użytkownika \(aplikacje ze Sklepu i aplikacje Win32)|
    |Rejestracja w usłudze zarządzania urządzeniami przenośnymi|Ustawienia urządzenia inne niż domyślne|
    |Aplikacje zainstalowane przez producenta OEM \(aplikacje ze Sklepu i aplikacje Win32)||
    |Profil użytkownika||
    |Dane użytkownika przechowywane poza profilem użytkownika||
    |Informacje o logowaniu automatycznym użytkownika|| 
    
         
7. Kliknij przycisk **Tak**, aby potwierdzić resetowanie do ustawień fabrycznych.

Jeśli urządzenie zostało włączone i połączone, propagowanie polecenia resetowania do ustawień fabrycznych do wszystkich typów urządzeń trwa mniej niż 15 minut.

## <a name="remove-company-data"></a>Usuwanie danych firmy

Polecenie **usunięcia danych firmy** powoduje usunięcie danych zarządzanych aplikacji (jeśli ma to zastosowanie), ustawień i profilów poczty e-mail, które zostały przypisane przy użyciu usługi Intune. Usunięcie danych firmy nie powoduje usunięcia osobistych danych użytkownika z urządzenia. Urządzenie jest usuwane z zarządzania przez usługę Intune. W poniższych tabelach opisano usuwane dane oraz wpływ usunięcia danych firmy na dane pozostające na urządzeniu.

### <a name="ios"></a>iOS

|Typ danych|iOS|
|-------------|-------|
|Aplikacje firmowe i skojarzone dane zainstalowane za pomocą usługi Intune|Aplikacje zostaną odinstalowane. Dane aplikacji firmowych zostaną usunięte.<br /><br />Dane aplikacji firmy Microsoft korzystających z zarządzania aplikacjami mobilnymi zostaną usunięte. Aplikacja nie zostanie usunięta.|
|Ustawienia|Konfiguracje, które były ustawione przez zasady usługi Intune, przestaną być wymuszane, a użytkownicy będą mogli zmieniać ustawienia.|
|Ustawienia profili sieci Wi-Fi i sieci VPN|Usuwane.|
|Ustawienia profili certyfikatów|Certyfikaty zostaną usunięte i odwołane.|
|Agent zarządzania|Profil zarządzania jest usuwany.|
|Poczta e-mail|Profile poczty e-mail aprowizowane za pośrednictwem usługi Intune i poczta e-mail zapisana w pamięci podręcznej na urządzeniu zostaną usunięte.|
|Outlook|Wiadomości e-mail odebrane w aplikacji Microsoft Outlook dla systemu iOS zostaną usunięte.|
|Odłączanie usługi Azure Active Directory (AD)|Rekord usługi Azure AD zostanie usunięty.|
|Kontakty | Kontakty synchronizowane bezpośrednio z aplikacji do natywnej książki adresowej są usuwane.  Nie można usunąć wszystkich kontaktów zsynchronizowanych z natywnej książki adresowej do innego źródła zewnętrznego. <br /> <br />Aktualnie obsługiwana jest tylko aplikacja Outlook.

### <a name="android"></a>Android

|Typ danych|Android|Android Samsung Knox Standard|
|-------------|-----------|------------------------|
|Linki sieci Web|Usuwane.|Usuwane.|
|Aplikacje niezarządzane ze sklepu Google Play|Aplikacje i dane pozostają zainstalowane.|Aplikacje i dane pozostają zainstalowane.|
|Niezarządzane aplikacje biznesowe|Aplikacje i dane pozostają zainstalowane.|Aplikacje zostaną odinstalowane i w rezultacie dane lokalne aplikacji zostaną usunięte. Żadne dane poza aplikacją (np. na karcie SD) nie zostaną usunięte.|
|Aplikacje zarządzane ze sklepu Google Play|Dane aplikacji zostaną usunięte. Aplikacja nie zostanie usunięta. Dane chronione przez szyfrowanie MAM poza aplikacją (np. karta SD) pozostaną zaszyfrowane i nie będzie można ich używać, ale nie zostaną usunięte.|Dane aplikacji zostaną usunięte. Aplikacja nie zostanie usunięta. Dane chronione przez szyfrowanie MAM poza aplikacją (np. karta SD) pozostaną zaszyfrowane, ale nie zostaną usunięte.|
|Zarządzane aplikacje biznesowe|Dane aplikacji zostaną usunięte. Aplikacja nie zostanie usunięta. Dane chronione przez szyfrowanie MAM poza aplikacją (np. karta SD) pozostaną zaszyfrowane i nie będzie można ich używać, ale nie zostaną usunięte.|Dane aplikacji zostaną usunięte. Aplikacja nie zostanie usunięta. Dane chronione przez szyfrowanie MAM poza aplikacją (np. karta SD) pozostaną zaszyfrowane i nie będzie można ich używać, ale nie zostaną usunięte.|
|Ustawienia|Konfiguracje, które były ustawione przez zasady usługi Intune, przestaną być wymuszane, a użytkownicy będą mogli zmieniać ustawienia.|Konfiguracje, które były ustawione przez zasady usługi Intune, przestaną być wymuszane, a użytkownicy będą mogli zmieniać ustawienia.|
|Ustawienia profili sieci Wi-Fi i sieci VPN|Usuwane.|Usuwane.|
|Ustawienia profili certyfikatów|Certyfikaty zostaną odwołane, ale nie zostaną usunięte.|Certyfikaty zostaną usunięte i odwołane.|
|Agent zarządzania|Uprawnienie administratora urządzenia jest odwoływane.|Uprawnienie administratora urządzenia jest odwoływane.|
|Poczta e-mail|Nie dotyczy (profile poczty e-mail nie są obsługiwane przez urządzenia z systemem Android)|Profile poczty e-mail aprowizowane za pośrednictwem usługi Intune i poczta e-mail zapisana w pamięci podręcznej na urządzeniu zostaną usunięte.|
|Outlook|Poczta e-mail odebrana przez aplikację Microsoft Outlook dla systemu Android zostanie usunięta, ale tylko w przypadku, gdy program Outlook jest chroniony przy użyciu zasad zarządzania aplikacjami mobilnymi. W przeciwnym razie program Outlook nie zostanie wyczyszczony podczas wyrejestrowania.|Poczta e-mail odebrana przez aplikację Microsoft Outlook dla systemu Android zostanie usunięta, ale tylko w przypadku, gdy program Outlook jest chroniony przy użyciu zasad zarządzania aplikacjami mobilnymi. W przeciwnym razie program Outlook nie zostanie wyczyszczony podczas wyrejestrowania.|
|Odłączanie usługi Azure Active Directory (AD)|Rekord usługi Azure AD zostanie usunięty.|Rekord usługi Azure AD zostanie usunięty.|
|Kontakty | Kontakty synchronizowane bezpośrednio z aplikacji do natywnej książki adresowej są usuwane.  Nie można usunąć wszystkich kontaktów zsynchronizowanych z natywnej książki adresowej do innego źródła zewnętrznego. <br /> <br />Aktualnie obsługiwana jest tylko aplikacja Outlook.|Kontakty synchronizowane bezpośrednio z aplikacji do natywnej książki adresowej są usuwane.  Nie można usunąć wszystkich kontaktów zsynchronizowanych z natywnej książki adresowej do innego źródła zewnętrznego. <br /> <br />Aktualnie obsługiwana jest tylko aplikacja Outlook.

### <a name="android-for-work"></a>Program Android for Work

Usunięcie danych firmy z urządzenia z programem Android for Work spowoduje usunięcie wszystkich danych, aplikacji i ustawień z profilu służbowego na tym urządzeniu. Powoduje to wycofanie urządzenia z zarządzania za pomocą usługi Intune. Resetowanie do ustawień fabrycznych nie jest obsługiwane w przypadku programu Android for Work.

### <a name="windows"></a>Windows

|Typ danych|Windows 8.1 (MDM) i Windows RT 8.1|Windows RT|Windows Phone 8 i Windows Phone 8.1|Windows 10|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Aplikacje firmowe i skojarzone dane zainstalowane za pomocą usługi Intune|Klucz plików chronionych przez system szyfrowania plików zostanie odwołany i użytkownik nie będzie mógł otwierać plików.|Nie spowoduje usunięcia aplikacji firmowych.|Aplikacje zainstalowane pierwotnie za pośrednictwem portalu firmy zostaną odinstalowane. Dane aplikacji firmowych zostaną usunięte.|Aplikacje są dezinstalowane, a klucze ładowania bezpośredniego są usuwane.<br>W przypadku systemu Windows 10 w wersji 1703 (aktualizacja dla twórców) i nowszych aplikacje usługi Office 365 ProPlus nie są usuwane.|
|Ustawienia|Konfiguracje, które były ustawione przez zasady usługi Intune, przestaną być wymuszane, a użytkownicy będą mogli zmieniać ustawienia.|Konfiguracje, które były ustawione przez zasady usługi Intune, przestaną być wymuszane, a użytkownicy będą mogli zmieniać ustawienia.|Konfiguracje, które były ustawione przez zasady usługi Intune, przestaną być wymuszane, a użytkownicy będą mogli zmieniać ustawienia.|Konfiguracje, które były ustawione przez zasady usługi Intune, przestaną być wymuszane, a użytkownicy będą mogli zmieniać ustawienia.|
|Ustawienia profili sieci Wi-Fi i sieci VPN|Usuwane.|Usuwane.|Nieobsługiwane.|Usuwane.|
|Ustawienia profili certyfikatów|Certyfikaty zostaną usunięte i odwołane.|Certyfikaty zostaną usunięte i odwołane.|Nieobsługiwane.|Certyfikaty zostaną usunięte i odwołane.|
|Poczta e-mail|Usuwa wiadomości e-mail z obsługą systemu szyfrowania plików, w tym wiadomości e-mail i załączniki z aplikacji Poczta dla systemu Windows.|Nieobsługiwane.|Profile poczty e-mail aprowizowane za pośrednictwem usługi Intune i poczta e-mail zapisana w pamięci podręcznej na urządzeniu zostaną usunięte.|Usuwa wiadomości e-mail z obsługą systemu szyfrowania plików, w tym wiadomości e-mail i załączniki z aplikacji Poczta dla systemu Windows. Usuwa konta poczty zaaprowizowane przez usługę Intune.|
|Odłączanie usługi Azure Active Directory (AD)|Nie.|Nie.|Rekord usługi Azure AD zostanie usunięty.|Nie dotyczy. System Windows 10 nie obsługuje usuwania danych firmy na urządzeniach przyłączonych do usługi Azure Active Directory.|

### <a name="to-remove-company-data"></a>Aby usunąć dane firmy

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Urządzenia i grupy** wybierz pozycję **Wszystkie urządzenia**.
4. Wybierz nazwę urządzenia, z którego chcesz usunąć dane firmy.
5. W bloku, w którym wyświetlona jest nazwa urządzenia, wybierz pozycję **Usuń dane firmowe**, a następnie wybierz pozycję **Tak**, aby potwierdzić.

Jeśli urządzenie jest włączone i połączone, propagowanie polecenia usuwania danych do wszystkich typów urządzeń trwa mniej niż 15 minut.

## <a name="delete-devices-from-the-azure-active-directory-portal"></a>Usuwanie urządzeń z portalu usługi Azure Active Directory

Z powodu problemów z komunikacją lub braku urządzeń może być konieczne usunięcie urządzeń z usługi Azure Active Directory (AD). Polecenie usunięcia nie powoduje usunięcia urządzenia z zarządzania, ale polecenia **Usuń** możesz użyć do usuwania rekordów urządzeń z witryny Azure Portal, gdy wiesz, że są one niedostępne i najprawdopodobniej nie będą się ponownie komunikować z platformą Azure.

1.  Zaloguj się do [usługi Azure Active Directory w portalu platformy Azure](http://aka.ms/accessaad) przy użyciu poświadczeń administratora. Możesz też zarejestrować się w [portalu usługi Office 365](https://portal.office.com), a następnie wybrać kolejno pozycje **Administrator** &gt; **Azure AD** przy użyciu linku w lewej części strony.
3.  Utwórz subskrypcję platformy Azure, jeśli jej nie masz. Jeśli masz płatne konto, ta operacja nie powinna wymagać uiszczenia płatności ani podania danych karty kredytowej (wybierz link do subskrypcji **Zarejestruj bezpłatny katalog Azure Active Directory**).
4.  Wybierz pozycję **Active Directory**, a następnie wybierz organizację.
5.  Wybierz kartę **Użytkownicy** .
6.  Wybierz użytkownika, którego urządzenia chcesz usunąć.
7.  Wybierz pozycję **Urządzenia**.
8.  Usuń urządzenia zgodnie z potrzebami, na przykład takie, które nie są już w użyciu lub zawierają niedokładne definicje.
