---
title: "Pełne lub selektywne czyszczenie na urządzeniach za pomocą usługi Intune"
titleSuffix: Intune on Azure
description: "Informacje na temat przeprowadzania selektywnego czyszczenia danych firmy na urządzeniu lub pełnego czyszczenia z przywróceniem ustawień fabrycznych urządzenia."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4fdb787e-084f-4507-9c63-c96b13bfcdf9
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2063612ee11d2bc7915ebe4bb28c67854a2599c3
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2017
---
# <a name="use-full-or-selective-wipe"></a>Korzystanie z czyszczenia pełnego lub selektywnego

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Z urządzeń zarządzanych przez usługę Intune, które nie są już potrzebne, mają inne zastosowanie lub zostały zagubione, można wyczyścić aplikacje i dane. Usługa Intune umożliwia selektywne i pełne czyszczenie danych. Użytkownicy mogą także wydać z aplikacji Portal firmy usługi Intune polecenie zdalnego wyczyszczenia urządzeń będących własnością prywatną i zarejestrowanych w usłudze Intune.

  > [!NOTE]
  > Ten temat dotyczy tylko czyszczenia danych z urządzeń zarządzanych w ramach zarządzania urządzeniami przenośnymi przez usługę Intune. Można również użyć [witryny Azure Portal](https://portal.azure.com) do [wyczyszczenia danych firmowych z aplikacji](https://docs.microsoft.com/intune-classic/deploy-use/wipe-managed-company-app-data-with-microsoft-intune). Możesz również [wycofać komputery zarządzane przy użyciu oprogramowania klienckiego usługi Intune](https://docs.microsoft.com/intune-classic/deploy-use/retire-a-windows-pc-with-microsoft-intune).

## <a name="full-wipe"></a>Pełne czyszczenie danych

**Pełne czyszczenie danych** przywraca ustawienia fabryczne urządzenia przez usunięcie wszystkich danych i ustawień dotyczących firmy oraz użytkownika. Urządzenie jest usuwane z usługi Intune. Pełne czyszczenie danych jest przydatne w przypadku resetowania urządzenia przed przekazaniem go nowemu użytkownikowi albo w przypadku utraty lub kradzieży urządzenia.  **Należy rozważnie korzystać z funkcji pełnego czyszczenia danych. Nie będzie można odzyskać danych na urządzeniu**.


> [!Warning]
> Urządzenia z systemem Windows 10 RTM (wcześniejszym niż Windows 10 w wersji 1511) mające mniej niż 4 GB pamięci RAM mogą stać się niedostępne, jeśli zostaną wyczyszczone. Urządzenie z systemem Windows 10, które przestało odpowiadać, można uruchomić z napędu USB.


**Aby przeprowadzić pełne czyszczenie (przywrócenie stanu fabrycznego) urządzenia**:

1.  W bloku **Urządzenia i grupy** wybierz pozycję **Wszystkie urządzenia**.

2.  Wybierz nazwę urządzenia, które chcesz wyczyścić.

3.  W bloku, w którym wyświetlona jest nazwa urządzenia, wybierz pozycję **Przywracanie stanu fabrycznego**, a następnie wybierz pozycję **Tak**, aby potwierdzić czyszczenie.

Jeśli urządzenie jest włączone i połączone, propagowanie polecenia czyszczenia do wszystkich typów urządzeń trwa mniej niż 15 minut.

### <a name="to-delete-devices-in-the-azure-active-directory-portal"></a>Aby usunąć urządzenia w portalu usługi Azure Active Directory

1.  Przejdź do witryny [http://aka.ms/accessaad](http://aka.ms/accessaad) lub wybierz pozycję **Administrator** &gt; **Azure AD** w witrynie [https://portal.office.com](https://portal.office.com).

2.  Zaloguj się za pomocą identyfikatora organizacji, korzystając z linku w lewej części strony.

3.  Utwórz subskrypcję platformy Azure, jeśli jej nie masz. Jeśli masz płatne konto, ta operacja nie powinna wymagać uiszczenia płatności ani podania danych karty kredytowej (wybierz link do subskrypcji **Zarejestruj bezpłatny katalog Azure Active Directory**).

4.  Wybierz pozycję **Active Directory**, a następnie wybierz organizację.

5.  Wybierz kartę **Użytkownicy** .

6.  Wybierz użytkownika, którego urządzenia chcesz usunąć.

7.  Wybierz pozycję **Urządzenia**.

8.  Usuń urządzenia zgodnie z potrzebami, na przykład takie, które nie są już w użyciu lub zawierają niedokładne definicje.


## <a name="selective-wipe"></a>Selektywne czyszczenie danych

**Selektywne czyszczenie danych** powoduje usunięcie z urządzenia danych firmowych, włącznie z danymi zarządzania aplikacjami mobilnymi (MAM, Mobile App Management; jeśli ma to zastosowanie), ustawieniami i profilami poczty e-mail. Selektywne czyszczenie danych nie powoduje usunięcia osobistych danych użytkownika z urządzenia. Urządzenie jest usuwane z usługi Intune. W poniższych tabelach opisano usuwane dane oraz wpływ selektywnego czyszczenia na dane pozostające na urządzeniu. (Tabele są uporządkowane według platform).

**iOS**

|Typ danych|iOS|
|-------------|-------|
|Aplikacje firmowe i skojarzone dane zainstalowane za pomocą usługi Intune|Aplikacje zostaną odinstalowane. Dane aplikacji firmowych zostaną usunięte.<br /><br />Dane aplikacji firmy Microsoft korzystających z zarządzania aplikacjami mobilnymi zostaną usunięte. Aplikacja nie zostanie usunięta.|
|Ustawienia|Konfiguracje, które były ustawione przez zasady usługi Intune, przestaną być wymuszane, a użytkownicy będą mogli zmieniać ustawienia.|
|Ustawienia profili sieci Wi-Fi i sieci VPN|Usuwane.|
|Ustawienia profili certyfikatów|Certyfikaty zostaną usunięte i odwołane.|
|Agent zarządzania|Profil zarządzania jest usuwany.|
|Poczta e-mail|Profile poczty e-mail aprowizowane za pośrednictwem usługi Intune i poczta e-mail zapisana w pamięci podręcznej na urządzeniu zostaną usunięte. Jeśli aplikacja Microsoft Exchange jest zainstalowana lokalnie, profile poczty e-mail i buforowane wiadomości e-mail nie są usuwane.|
|Outlook|Wiadomości e-mail odebrane w aplikacji Microsoft Outlook dla systemu iOS zostaną usunięte.</br>Wyjątek: Jeśli aplikacja Exchange jest zainstalowana lokalnie, wiadomości e-mail nie zostaną usunięte.|
|Odłączanie usługi Azure Active Directory (AAD)|Rekord usługi AAD zostanie usunięty.|
|Kontakty | Kontakty synchronizowane bezpośrednio z aplikacji do natywnej książki adresowej są usuwane.  Nie można wyczyścić wszystkich kontaktów zsynchronizowanych z natywnej książki adresowej do innego źródła zewnętrznego. <br /> <br />Aktualnie obsługiwana jest tylko aplikacja Outlook.

**Android**

|Typ danych|Android|Android Samsung KNOX Standard|
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
|Outlook|Poczta e-mail odebrana w aplikacji Microsoft Outlook dla systemu Android zostanie usunięta.</br>Wyjątek: Jeśli aplikacja Exchange jest zainstalowana lokalnie, wiadomości e-mail nie zostaną usunięte.|Poczta e-mail odebrana w aplikacji Microsoft Outlook dla systemu Android zostanie usunięta.</br>Wyjątek: Jeśli aplikacja Exchange jest zainstalowana lokalnie, wiadomości e-mail nie zostaną usunięte.|
|Odłączanie usługi Azure Active Directory (AAD)|Rekord usługi AAD zostanie usunięty.|Rekord usługi AAD zostanie usunięty.|
|Kontakty | Kontakty synchronizowane bezpośrednio z aplikacji do natywnej książki adresowej są usuwane.  Nie można wyczyścić wszystkich kontaktów zsynchronizowanych z natywnej książki adresowej do innego źródła zewnętrznego. <br /> <br />Aktualnie obsługiwana jest tylko aplikacja Outlook.|Kontakty synchronizowane bezpośrednio z aplikacji do natywnej książki adresowej są usuwane.  Nie można wyczyścić wszystkich kontaktów zsynchronizowanych z natywnej książki adresowej do innego źródła zewnętrznego. <br /> <br />Aktualnie obsługiwana jest tylko aplikacja Outlook.

**Android for Work**

Wykonywanie czyszczenia selektywnego na urządzeniu z programem Android for Work powoduje usunięcie wszystkich danych, aplikacji i ustawień z profilu służbowego na tym urządzeniu. Powoduje to wycofanie urządzenia z zarządzania za pomocą usługi Intune. Pełne czyszczenie danych nie jest obsługiwane w przypadku programu Android for Work.

**Windows**

|Typ danych|Windows 8.1 (MDM) i Windows RT 8.1|Windows RT|Windows Phone 8 i Windows Phone 8.1|Windows 10|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Aplikacje firmowe i skojarzone dane zainstalowane za pomocą usługi Intune|Klucz plików chronionych przez system szyfrowania plików zostanie odwołany i użytkownik nie będzie mógł otwierać plików.|Nie spowoduje usunięcia aplikacji firmowych.|Aplikacje zainstalowane pierwotnie za pośrednictwem portalu firmy zostaną odinstalowane. Dane aplikacji firmowych zostaną usunięte.|Aplikacje są dezinstalowane, a klucze ładowania bezpośredniego są usuwane.|
|Ustawienia|Konfiguracje, które były ustawione przez zasady usługi Intune, przestaną być wymuszane, a użytkownicy będą mogli zmieniać ustawienia.|Konfiguracje, które były ustawione przez zasady usługi Intune, przestaną być wymuszane, a użytkownicy będą mogli zmieniać ustawienia.|Konfiguracje, które były ustawione przez zasady usługi Intune, przestaną być wymuszane, a użytkownicy będą mogli zmieniać ustawienia.|Konfiguracje, które były ustawione przez zasady usługi Intune, przestaną być wymuszane, a użytkownicy będą mogli zmieniać ustawienia.|
|Ustawienia profili sieci Wi-Fi i sieci VPN|Usuwane.|Usuwane.|Nieobsługiwane.|Usuwane.|
|Ustawienia profili certyfikatów|Certyfikaty zostaną usunięte i odwołane.|Certyfikaty zostaną usunięte i odwołane.|Nieobsługiwane.|Certyfikaty zostaną usunięte i odwołane.|
|Poczta e-mail|Usuwa wiadomości e-mail z obsługą systemu szyfrowania plików, w tym wiadomości e-mail i załączniki z aplikacji Poczta dla systemu Windows.|Nieobsługiwane.|Profile poczty e-mail aprowizowane za pośrednictwem usługi Intune i poczta e-mail zapisana w pamięci podręcznej na urządzeniu zostaną usunięte.|Usuwa wiadomości e-mail z obsługą systemu szyfrowania plików, w tym wiadomości e-mail i załączniki z aplikacji Poczta dla systemu Windows. Usuwa konta poczty zaaprowizowane przez usługę Intune.</br>**Wyjątek**: Jeśli aplikacja Microsoft Exchange jest zainstalowana lokalnie, konta e-mail nie zostaną usunięte.|
|Odłączanie usługi Azure Active Directory (AAD)|Nie.|Nie.|Rekord usługi AAD zostanie usunięty.|Nie dotyczy. System Windows 10 nie obsługuje selektywnego czyszczenia danych na urządzeniach przyłączonych do usługi Azure Active Directory.|

**Aby przeprowadzić selektywne czyszczenie danych**:

1.  W bloku **Urządzenia i grupy** wybierz pozycję **Wszystkie urządzenia**.

2.  Wybierz nazwę urządzenia, które chcesz wyczyścić.

3.  W bloku, w którym wyświetlona jest nazwa urządzenia, wybierz pozycję **Usuń dane firmowe**, a następnie wybierz pozycję **Tak**, aby potwierdzić czyszczenie.

Jeśli urządzenie jest włączone i połączone, propagowanie polecenia czyszczenia do wszystkich typów urządzeń trwa mniej niż 15 minut.
