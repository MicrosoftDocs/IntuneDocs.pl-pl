---
title: "Zapewnianie lepszej ochrony danych dzięki zdalnemu czyszczeniu danych"
description: "Usługa Intune udostępnia funkcje czyszczenia selektywnego i pełnego umożliwiające usunięcie poufnych danych firmy oraz dostępu do wielu zasobów firmy."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8519e411-3d48-44eb-9b41-3e4fd6a93112
ms.reviewer: lancecra
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9d03f3936d608b9d526724eccbbdadbe030b53b8
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2017
---
# <a name="help-protect-your-data-with-full-or-selective-wipe-using-microsoft-intune"></a>Zapewnianie lepszej ochrony danych dzięki pełnemu lub selektywnemu czyszczeniu przy użyciu usługi Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Z urządzeń zarządzanych przez usługę Intune, które nie są już potrzebne, mają inne zastosowanie lub zostały zagubione, można wyczyścić aplikacje i dane. Usługa Intune umożliwia selektywne i pełne czyszczenie danych. Użytkownicy mogą także wydać z aplikacji Portal firmy usługi Intune polecenie zdalnego wyczyszczenia urządzeń będących własnością prywatną i zarejestrowanych w usłudze Intune.

  > [!NOTE]
  > Ten temat dotyczy tylko czyszczenia danych z urządzeń zarządzanych w ramach zarządzania urządzeniami przenośnymi przez usługę Intune. Można również użyć [witryny Azure Portal](https://portal.azure.com) do [wyczyszczenia danych firmowych z aplikacji](wipe-managed-company-app-data-with-microsoft-intune.md). Możesz również [wycofać komputery zarządzane przy użyciu oprogramowania klienckiego usługi Intune](retire-a-windows-pc-with-microsoft-intune.md).

## <a name="full-wipe"></a>Pełne czyszczenie danych

**Pełne czyszczenie danych** przywraca ustawienia fabryczne urządzenia przez usunięcie wszystkich danych i ustawień dotyczących firmy oraz użytkownika. Urządzenie jest usuwane z usługi Intune. Pełne czyszczenie danych jest przydatne w przypadku resetowania urządzenia przed przekazaniem go nowemu użytkownikowi albo w przypadku utraty lub kradzieży urządzenia.  **Należy rozważnie korzystać z funkcji pełnego czyszczenia danych. Nie będzie można odzyskać danych na urządzeniu**.


> [!Warning]
> Urządzenia z systemem Windows 10 RTM (wcześniejszym niż Windows 10 w wersji 1511) mające mniej niż 4 GB pamięci RAM mogą stać się niedostępne, jeśli zostaną wyczyszczone. Urządzenie z systemem Windows 10, które przestało odpowiadać, można uruchomić z napędu USB.

### <a name="remotely-wipe-a-device-from-the-intune-administrator-console"></a>Zdalne czyszczenie urządzenia z poziomu konsoli administratora usługi Intune

1.  Wybierz urządzenia do wyczyszczenia. Można je znaleźć według użytkownika lub według urządzenia.

    -   **Według użytkownika:**

        1.  W [konsoli administratora usługi Intune](https://manage.microsoft.com/) wybierz pozycje **Grupy** &gt; **Wszyscy użytkownicy**.

        2.  Wybierz nazwę użytkownika, którego urządzenie przenośne ma zostać wyczyszczone. Wybierz pozycję **Wyświetl właściwości**.

        3.  Na stronie **Właściwości** użytkownika wybierz pozycję **Urządzenia**, a następnie wybierz nazwę urządzenia przenośnego, które chcesz wyczyścić. Użyj kombinacji klawisza Ctrl i kliknięcia, aby wybrać wiele urządzeń.

    -   **Według urządzenia:**

        1.  W [konsoli administratora usługi Intune](https://manage.microsoft.com/) wybierz pozycję **Grupy** &gt; **Wszystkie urządzenia przenośne**.

         ![Rozpoczynanie operacji wycofania lub czyszczenia](../media/dev-sa-wipe.png)

        2.  Wybierz pozycję **Urządzenia**, a następnie wybierz nazwę urządzenia przenośnego, które chcesz wyczyścić. Użyj kombinacji klawisza Ctrl i kliknięcia, aby wybrać wiele urządzeń.

2.  Wybierz pozycję **Wycofaj/wyczyść**.

3.  Zostanie wyświetlony komunikat potwierdzenia z pytaniem, czy chcesz wycofać urządzenie.

    -   Aby przeprowadzić **selektywne czyszczenie danych**, które powoduje usunięcie tylko aplikacji i danych firmy, wybierz pozycję **Tak**.

    -   Aby przeprowadzić **pełne czyszczenie danych**, które powoduje usunięcie wszystkich aplikacji i danych, a następnie przywraca domyślne ustawienia fabryczne urządzenia, wybierz pozycję **Wyczyść urządzenie przed jego wycofaniem**. Ta akcja ma zastosowanie do wszystkich platform z wyjątkiem systemu Windows 8.1. **Nie można odzyskać danych usuniętych przez pełne czyszczenie danych**.

Jeśli urządzenie jest włączone i połączone, propagowanie polecenia czyszczenia do wszystkich typów urządzeń trwa mniej niż 15 minut.

#### <a name="to-delete-devices-in-the-azure-active-directory-portal"></a>Aby usunąć urządzenia w portalu usługi Azure Active Directory

1.  Przejdź do witryny [http://aka.ms/accessaad](http://aka.ms/accessaad) lub wybierz pozycję **Administrator** &gt; **Azure AD** w witrynie [https://portal.office.com](https://portal.office.com).

2.  Zaloguj się za pomocą Identyfikatora organizacji, korzystając z linku w lewej części strony.

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
|Poczta e-mail|n/d Zobacz element programu Outlook.|Profile poczty e-mail aprowizowane za pośrednictwem usługi Intune i poczta e-mail zapisana w pamięci podręcznej na urządzeniu zostaną usunięte.|
|Outlook|Poczta e-mail odebrana przez aplikację Microsoft Outlook dla systemu Android zostanie usunięta, ale tylko w przypadku, gdy program Outlook jest chroniony przy użyciu zasad zarządzania aplikacjami mobilnymi. W przeciwnym razie program Outlook nie zostanie wyczyszczony podczas wyrejestrowania.</br>Wyjątek: Jeśli aplikacja Exchange jest zainstalowana lokalnie, wiadomości e-mail nie zostaną usunięte.|Poczta e-mail odebrana przez aplikację Microsoft Outlook dla systemu Android zostanie usunięta, ale tylko w przypadku, gdy program Outlook jest chroniony przy użyciu zasad zarządzania aplikacjami mobilnymi. W przeciwnym razie program Outlook nie zostanie wyczyszczony podczas wyrejestrowania.</br>Wyjątek: Jeśli aplikacja Exchange jest zainstalowana lokalnie, wiadomości e-mail nie zostaną usunięte.|
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

## <a name="wipe-encryption-file-system-efs-enabled-content"></a>Czyszczenie zawartości z obsługą systemu szyfrowania plików (EFS)
Selektywne czyszczenie zawartości z obsługą systemu szyfrowania plików jest obsługiwane w systemach Windows 8.1 i Windows RT 8.1. W przypadku selektywnego czyszczenia zawartości z obsługą systemu szyfrowania plików obowiązują następujące reguły:

-   Selektywne czyszczenie zawartości dotyczy tylko aplikacji i danych chronionych przez system szyfrowania plików, który używa tej samej domeny internetowej co konto usługi Intune. Aby uzyskać więcej informacji, zobacz [Selektywne czyszczenie danych w systemie Windows w celu zarządzania danymi urządzenia](http://technet.microsoft.com/library/dn486874.aspx).

-   Wprowadzenie zmian w domenie skojarzonej z systemem szyfrowania plików może zająć do 48 godzin. Dopiero po upływie tego czasu można selektywnie wyczyścić aplikacje i dane, które używają nowej domeny.

-   Każda domena zarejestrowana w usłudze Intune zostanie wyczyszczona.

Selektywne czyszczenie zawartości z obsługą systemu szyfrowania plików jest obecnie obsługiwane w przypadku następujących danych i aplikacji:

-   Aplikacja poczty dla systemu Windows

-   Foldery robocze

-   Pliki i foldery zaszyfrowane w systemie szyfrowania plików. Aby uzyskać więcej informacji, zobacz [Najlepsze rozwiązania dotyczące systemu szyfrowania plików](http://support.microsoft.com/kb/223316).

-   Jeśli organizacja ma swoją tożsamość w usłudze Active Directory, należy użyć narzędzia do synchronizacji katalogów (DirSync), aby zsynchronizować informacje z usługą AAD w celu zapewnienia prawidłowego działania selektywnego czyszczenia danych z obsługą systemu szyfrowania plików.  Aby uzyskać więcej informacji dotyczących narzędzia DirSync, zobacz [Scenariusz synchronizacji katalogów](http://technet.microsoft.com/library/dn441212.aspx) w dokumentacji usługi Azure Active Directory.

## <a name="monitor-retire-wipe-and-delete-actions"></a>Monitorowanie akcji wycofywania, czyszczenia i usuwania
Aby wyświetlić raport urządzeń, które zostały wycofane, wyczyszczone lub usunięte:

1.  W [konsoli administratora usługi Intune](https://manage.microsoft.com/) wybierz pozycję **Raporty** &gt; **Raporty dotyczące historii urządzeń**.

2.  Podaj datę początkową i końcową raportu, a następnie wybierz pozycję **Wyświetl raport**.

Ten raport przedstawia również, kto wykonał daną akcję.

### <a name="see-also"></a>Zobacz też
[Wycofywanie urządzeń](retire-devices-from-microsoft-intune-management.md)

[Selektywne czyszczenie danych w systemie Windows w celu zarządzania danymi urządzenia](http://technet.microsoft.com/library/dn486874.aspx)
