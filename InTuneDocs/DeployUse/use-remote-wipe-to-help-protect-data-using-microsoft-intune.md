---
title: "Zapewnianie lepszej ochrony danych dzięki zdalnemu czyszczeniu danych | Microsoft Intune"
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8519e411-3d48-44eb-9b41-3e4fd6a93112
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 06f144693fe4e535b2ed423c95f5431e391f316f
ms.openlocfilehash: 077f35afc5084b0381fd330236e45d62e1242484


---

# Zapewnianie lepszej ochrony danych dzięki pełnemu lub selektywnemu czyszczeniu przy użyciu usługi Microsoft Intune
Podobnie jak w przypadku urządzeń, na pewnym etapie jest wymagane lub konieczne [wycofanie aplikacji](retire-apps-using-microsoft-intune.md), które zostały wdrożone na komputerach i urządzeniach przenośnych, ale są już niepotrzebne. Może być również konieczne usunięcie danych firmy z urządzenia. Usługa Intune umożliwia selektywne i pełne czyszczenie danych. Ponieważ urządzenia przenośne mogą zawierać poufne dane firmy i umożliwiają dostęp do wielu zasobów firmy, w przypadku utraty lub kradzieży urządzenia można wydać z usługi Intune polecenie zdalnego wyczyszczenia urządzenia. Ponadto użytkownicy mogą wydać z usługi Intune polecenie zdalnego wyczyszczenia urządzenia dla urządzeń będących własnością prywatną i zarejestrowanych w usłudze Intune.

  > [!NOTE]
  > Ten temat dotyczy tylko czyszczenia danych z urządzeń zarządzanych przez usługę Intune. Można również użyć [portalu Azure w wersji zapoznawczej](https://portal.azure.com) do [czyszczenia danych firmy z aplikacji](wipe-managed-company-app-data-with-microsoft-intune.md).

## Pełne czyszczenie danych


**Pełne czyszczenie danych** przywraca ustawienia fabryczne urządzenia przez usunięcie wszystkich danych i ustawień dotyczących firmy oraz użytkownika. Urządzenie jest usuwane z usługi Intune. Pełne czyszczenie danych jest przydatne w przypadku resetowania urządzenia przed przekazaniem go nowemu użytkownikowi albo w przypadku utraty lub kradzieży urządzenia.  **Należy rozważnie korzystać z funkcji pełnego czyszczenia danych. Nie będzie można odzyskać danych na urządzeniu**.

> [!Warning]
> Urządzenia z systemem Windows 10 RTM (tj. wcześniejszym niż Windows 10 w wersji 1511) z mniej niż 4 GB pamięci RAM mogą stać się niedostępne, jeśli zostaną wyczyszczone. Urządzenie z systemem Windows 10, które przestało odpowiadać, można uruchomić z napędu USB lub użyć podobnego obejścia.

## Selektywne czyszczenie danych

**Selektywne czyszczenie danych** powoduje usunięcie z urządzenia danych firmy, włącznie z danymi zarządzania aplikacjami mobilnymi (jeśli ma to zastosowanie), ustawieniami i profilami poczty e-mail. Selektywne czyszczenie danych nie powoduje usunięcia osobistych danych użytkownika z urządzenia. Urządzenie jest usuwane z usługi Intune. W poniższych tabelach opisano (według platform) usuwane dane oraz wpływ selektywnego czyszczenia na dane pozostające na urządzeniu.

**iOS**

|Typ danych|iOS|
|-------------|-------|
|Aplikacje firmowe i skojarzone dane zainstalowane za pomocą usługi Intune.|Aplikacje zostaną odinstalowane. Dane aplikacji firmowych zostaną usunięte.<br /><br />Dane aplikacji firmy Microsoft korzystających z zarządzania aplikacjami mobilnymi zostaną usunięte. Aplikacja nie zostanie usunięta.|
|Ustawienia|Konfiguracje, które zostały określone przez zasady usługi Intune, przestaną być wymuszane, a użytkownicy będą mogli zmieniać ustawienia.|
|Ustawienia profili sieci Wi-Fi i sieci VPN|Zostaną usunięte|
|Ustawienia profili certyfikatów|Certyfikaty zostaną usunięte i odwołane.|
|Agent zarządzania|Profil zarządzania jest usuwany.|
|Poczta e-mail|Profile poczty e-mail obsługiwane za pośrednictwem usługi Intune i poczta e-mail zapisana w pamięci podręcznej na urządzeniu zostaną usunięte.|
|Odłączanie usługi Azure Active Directory (AAD)|Rekord usługi AAD zostanie usunięty|
|Kontakty | Kontakty synchronizowane bezpośrednio z aplikacji do natywnej książki adresowej są usuwane.  Nie można wyczyścić wszystkich kontaktów zsynchronizowanych z natywnej książki adresowej do innego źródła zewnętrznego. <br /> <br />Aktualnie obsługiwana jest tylko aplikacja Outlook.

**Android**

|Typ danych|Android|Android Samsung KNOX|
|-------------|-----------|------------------------|
|Linki sieci Web|Usuwane.|Zostaną usunięte|
|Aplikacje niezarządzane ze sklepu Google Play|Aplikacje i dane pozostają zainstalowane.|Aplikacje i dane pozostają zainstalowane.|
|Niezarządzane aplikacje biznesowe|Aplikacje i dane pozostają zainstalowane.|Aplikacje zostaną odinstalowane i w rezultacie dane lokalne aplikacji zostaną usunięte. Żadne dane poza aplikacją (na karcie SD itp.) nie zostaną usunięte.|
|Aplikacje zarządzane ze sklepu Google Play|Dane aplikacji zostaną usunięte. Aplikacja nie zostanie usunięta. Dane chronione przez szyfrowanie MAM poza aplikacją (karta SD itp.) pozostaną zaszyfrowane i nie będzie można ich używać, ale nie zostaną usunięte.|Dane aplikacji zostaną usunięte. Aplikacja nie zostanie usunięta. Dane chronione przez szyfrowanie MAM poza aplikacją (karta SD itp.) pozostaną zaszyfrowane, ale nie zostaną usunięte.|
|Zarządzane aplikacje biznesowe|Dane aplikacji zostaną usunięte. Aplikacja nie zostanie usunięta. Dane chronione przez szyfrowanie MAM poza aplikacją (karta SD itp.) pozostaną zaszyfrowane i nie będzie można ich używać, ale nie zostaną usunięte.|Dane aplikacji zostaną usunięte. Aplikacja nie zostanie usunięta. Dane chronione przez szyfrowanie MAM poza aplikacją (karta SD itp.) pozostaną zaszyfrowane i nie będzie można ich używać, ale nie zostaną usunięte.|
|Ustawienia|Konfiguracje, które zostały określone przez zasady usługi Intune, przestaną być wymuszane, a użytkownicy będą mogli zmieniać ustawienia.|Konfiguracje, które zostały określone przez zasady usługi Intune, przestaną być wymuszane, a użytkownicy będą mogli zmieniać ustawienia.|
|Ustawienia profili sieci Wi-Fi i sieci VPN|Zostaną usunięte|Zostaną usunięte|
|Ustawienia profili certyfikatów|Certyfikaty zostaną odwołane, ale nie zostaną usunięte.|Certyfikaty zostaną usunięte i odwołane.|
|Agent zarządzania|Uprawnienie administratora urządzenia jest odwoływane.|Uprawnienie administratora urządzenia jest odwoływane.|
|Poczta e-mail|Poczta e-mail odebrana w aplikacji Microsoft Outlook dla systemu Android zostanie usunięta.|Profile poczty e-mail obsługiwane za pośrednictwem usługi Intune i poczta e-mail zapisana w pamięci podręcznej na urządzeniu zostaną usunięte.|
|Odłączanie usługi Azure Active Directory (AAD)|Rekord usługi AAD zostanie usunięty|Rekord usługi AAD zostanie usunięty|
|Kontakty | Kontakty synchronizowane bezpośrednio z aplikacji do natywnej książki adresowej są usuwane.  Nie można wyczyścić wszystkich kontaktów zsynchronizowanych z natywnej książki adresowej do innego źródła zewnętrznego. <br /> <br />Aktualnie obsługiwana jest tylko aplikacja Outlook.|Kontakty synchronizowane bezpośrednio z aplikacji do natywnej książki adresowej są usuwane.  Nie można wyczyścić wszystkich kontaktów zsynchronizowanych z natywnej książki adresowej do innego źródła zewnętrznego. <br /> <br />Aktualnie obsługiwana jest tylko aplikacja Outlook.

**Windows**

|Typ danych|Windows 8.1 (MDM) i Windows RT 8.1|Windows RT|Windows Phone 8 i Windows Phone 8.1|Windows 10|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Aplikacje firmowe i skojarzone dane zainstalowane za pomocą usługi Intune.|Klucz plików chronionych przez system szyfrowania plików zostanie odwołany i użytkownik nie będzie mógł otwierać plików.|Nie spowoduje usunięcia aplikacji firmowych.|Aplikacje zainstalowane pierwotnie za pośrednictwem portalu firmy zostaną odinstalowane. Dane aplikacji firmowych zostaną usunięte.|Aplikacje są dezinstalowane, a klucze ładowania bezpośredniego są usuwane.|
|Ustawienia|Konfiguracje, które zostały określone przez zasady usługi Intune, przestaną być wymuszane, a użytkownicy będą mogli zmieniać ustawienia.|Konfiguracje, które zostały określone przez zasady usługi Intune, przestaną być wymuszane, a użytkownicy będą mogli zmieniać ustawienia.|Konfiguracje, które zostały określone przez zasady usługi Intune, przestaną być wymuszane, a użytkownicy będą mogli zmieniać ustawienia.|Konfiguracje, które zostały określone przez zasady usługi Intune, przestaną być wymuszane, a użytkownicy będą mogli zmieniać ustawienia.|
|Ustawienia profili sieci Wi-Fi i sieci VPN|Zostaną usunięte|Zostaną usunięte|Nieobsługiwane|Zostaną usunięte|
|Ustawienia profili certyfikatów|Certyfikaty zostaną usunięte i odwołane.|Certyfikaty zostaną usunięte i odwołane.|Nieobsługiwane|Certyfikaty zostaną usunięte i odwołane.|
|Poczta e-mail|Usuwa wiadomości e-mail z obsługą systemu szyfrowania plików, w tym wiadomości e-mail i załączniki z aplikacji poczty dla systemu Windows.|Nieobsługiwane|Profile poczty e-mail obsługiwane za pośrednictwem usługi Intune i poczta e-mail zapisana w pamięci podręcznej na urządzeniu zostaną usunięte.|Usuwa wiadomości e-mail z obsługą systemu szyfrowania plików, w tym wiadomości e-mail i załączniki z aplikacji poczty dla systemu Windows. Usuwa konta poczty zaaprowizowane przez usługę Intune.|
|Odłączanie usługi Azure Active Directory (AAD)|Nie|Nie|Rekord usługi AAD zostanie usunięty|Nie dotyczy. System Windows 10 nie obsługuje selektywnego czyszczenia danych na urządzeniach przyłączonych do usługi Azure Active Directory|

### Zdalne czyszczenie urządzenia z poziomu konsoli administratora usługi Intune

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

3.  Zostanie wyświetlony komunikat z prośbą o potwierdzenie wycofania urządzenia.

    -   Aby przeprowadzić **selektywne czyszczenie danych**, które powoduje usunięcie tylko aplikacji i danych firmy, wybierz pozycję **Tak**.

    -   Aby przeprowadzić **pełne czyszczenie danych**, które powoduje usunięcie wszystkich aplikacji i danych, a następnie przywraca domyślne ustawienia fabryczne urządzenia, wybierz pozycję **Wyczyść urządzenie przed jego wycofaniem**. Ta akcja ma zastosowanie do wszystkich platform z wyjątkiem systemu Windows 8.1. **Nie można odzyskać danych usuniętych przez pełne czyszczenie danych**.

Czyszczenie wszystkich typów urządzeń trwa mniej niż 15 minut.

## Czyszczenie zawartości z obsługą systemu szyfrowania plików (EFS)
Selektywne czyszczenie zawartości z obsługą systemu szyfrowania plików jest obsługiwane w systemach Windows 8.1 i Windows RT 8.1. W przypadku selektywnego czyszczenia zawartości z obsługą systemu szyfrowania plików obowiązują następujące reguły:

-   Selektywne czyszczenie zawartości dotyczy tylko aplikacji i danych chronionych przez system szyfrowania plików, który używa tej samej domeny internetowej co konto usługi Intune. Aby uzyskać więcej informacji, zobacz [Selektywne czyszczenie danych w systemie Windows w celu zarządzania danymi urządzenia](http://technet.microsoft.com/library/dn486874.aspx).

-   Wprowadzenie zmian w domenie skojarzonej z systemem szyfrowania plików może zająć do 48 godzin. Dopiero po upływie tego czasu można selektywnie wyczyścić aplikacje i dane, które używają nowej domeny.

-   Każda domena zarejestrowana w usłudze Intune zostanie wyczyszczona.

Selektywne czyszczenie zawartości z obsługą systemu szyfrowania plików jest obecnie obsługiwane w przypadku następujących danych i aplikacji:

-   Aplikacja poczty dla systemu Windows

-   Foldery robocze

-   Pliki i foldery zaszyfrowane w systemie szyfrowania plików. Aby uzyskać więcej informacji, zobacz [Najlepsze rozwiązania dotyczące systemu szyfrowania plików](http://support.microsoft.com/kb/223316).

-   Jeśli organizacja ma swoją tożsamość w usłudze Active Directory, należy użyć narzędzia do synchronizacji katalogów (DirSync), aby zsynchronizować informacje z usługą AAD w celu zapewnienia prawidłowego działania selektywnego czyszczenia danych z obsługą systemu szyfrowania plików.  Aby uzyskać więcej informacji dotyczących narzędzia DirSync, zobacz [Scenariusz synchronizacji katalogów](http://technet.microsoft.com/library/dn441212.aspx) w dokumentacji usługi Azure Active Directory.

## Monitorowanie akcji wycofywania, czyszczenia i usuwania
Aby wyświetlić raport urządzeń, które zostały wycofane, wyczyszczone lub usunięte, oraz informacje o tym, kto wykonał akcję:

1.  W [konsoli administratora usługi Intune](https://manage.microsoft.com/) wybierz pozycję **Raporty** &gt; **Raporty dotyczące historii urządzeń**.

2.  Podaj datę początkową i końcową raportu, a następnie wybierz pozycję **Wyświetl raport**.


### Zobacz też
[Wycofywanie urządzeń](retire-devices-from-microsoft-intune-management.md)

[Selektywne czyszczenie danych w systemie Windows w celu zarządzania danymi urządzenia](http://technet.microsoft.com/library/dn486874.aspx)



<!--HONumber=Jul16_HO3-->


