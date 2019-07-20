---
title: Aktualizacje oprogramowania na komputerach z systemem Windows
titleSuffix: Microsoft Intune
description: Usługa Intune, dzięki szybkiej instalacji aktualizacji oprogramowania i najnowszych poprawek, pomaga upewnić się, że oprogramowanie komputerów pozostaje aktualne.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/01/2018
ms.topic: archived
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 48e9c41a-d2de-424e-9610-cfd1ad514210
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.collection: M365-identity-device-management
ms.openlocfilehash: a94c327c8595e83ec9808ed41e788c5756d5510a
ms.sourcegitcommit: bd09decb754a832574d7f7375bad0186a22a15ab
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 07/19/2019
ms.locfileid: "68353879"
---
# <a name="keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune"></a>Zapewnianie aktualności oprogramowania na komputerach z systemem Windows za pomocą aktualizacji w usłudze Microsoft Intune

[!INCLUDE [classic-portal](includes/classic-portal.md)]

> [!NOTE]
> Informacje w tym temacie dotyczą tylko komputerów z systemem Windows, które są zarządzane jako komputery osobiste przy użyciu oprogramowania klienckiego usługi Intune. Aby zarządzać aktualizacjami komputerów z systemem Windows zarejestrowanych jako urządzenia przenośne, zobacz [Zarządzanie aktualizacjami oprogramowania w usłudze Intune](windows-update-for-business-configure.md).

Usługa Microsoft Intune pomaga zabezpieczyć komputery zarządzane na wiele sposobów. Jednym z nich jest zarządzanie aktualizacjami oprogramowania, które zapewniają, że oprogramowanie komputerów jest aktualne, szybko instalując najnowsze poprawki i aktualizacje oprogramowania.

Jeśli klient usługi Intune nie został jeszcze zainstalowany na komputerach, zobacz [Instalowanie klienta komputera z systemem Windows przy użyciu usługi Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).

Jeśli zostanie utworzona aktualizacja innej firmy lub w usłudze Microsoft Update zostaną udostępnione nowe aktualizacje, które dotyczą zarządzanych komputerów, w obszarze roboczym **Aktualizacje** na stronie **Przegląd** zostanie wyświetlone powiadomienie. Po wybraniu linku powiadomienia można wykonywać różne operacje, takie jak wyświetlanie dodatkowych informacji o aktualizacji, zatwierdzanie lub odrzucanie aktualizacji oraz wyświetlanie komputerów, na których zostanie zainstalowana aktualizacja w przypadku jej zatwierdzenia.

> [!IMPORTANT]
> Obszar roboczy **Aktualizacje** zostanie wyświetlony w konsoli administratora dopiero po zainstalowaniu klienta i pomyślnym rozpoczęciu zarządzania co najmniej jednym komputerem klienckim.

Po zatwierdzeniu aktualizacji do zainstalowania w obszarze roboczym **Aktualizacje** konsoli usługi Intune można sprawdzić powodzenie lub niepowodzenie instalacji.

Informacje zawarte w poniższych sekcjach ułatwią zapewnienie aktualności oprogramowania na zarządzanych komputerach.

## <a name="before-you-start"></a>Przed rozpoczęciem
Przed rozpoczęciem tworzenia i zatwierdzania aktualizacji oprogramowania skonfiguruj i wdroż na komputerach zasady umożliwiające sterowanie warunkami i sposobami instalowania aktualizacji.

### <a name="to-configure-update-policy-settings"></a>Aby skonfigurować ustawienia zasad aktualizacji

1. W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/) wybierz pozycje **Zasady** &gt; **Przegląd** &gt; **Dodaj zasady**.

2. Skonfiguruj i wdroż zasady **ustawień agenta usługi Microsoft Intune** dla ustawień aktualizacji. Możesz skorzystać z zalecanych ustawień lub dostosować je. Aby uzyskać więcej informacji dotyczących sposobu tworzenia i wdrażania zasad, zobacz [Typowe zadania związane z zarządzaniem komputerem z systemem Windows za pomocą klienta komputerowego usługi Microsoft Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md).

W poniższej tabeli przedstawiono ustawienia możliwe do skonfigurowania w ramach zasad oraz ich zalecane wartości, które zostaną użyte, jeśli zrezygnujesz z dostosowania zasad. Te ustawienia można znaleźć w sekcji **Aktualizacje** .

  |Ustawienie zasad|Szczegóły|
    |------------------|--------------------|
    |**Częstotliwość wykrywania aktualizacji i aplikacji (w godzinach)** |Określa częstotliwość sprawdzania obecności nowych aktualizacji i aplikacji przez usługę Intune (od 8 do 22 godzin).<br /><br />Zalecana wartość: **8** godzin.|
    |**Instalacja aktualizacji oraz aplikacji automatyczna lub z monitem** |Określa, czy aktualizacje są instalowane automatycznie, czy przed ich instalacją jest wyświetlany monit dla użytkownika. Ponadto to ustawienie umożliwia zaplanowanie instalacji aktualizacji oraz aplikacji.<br /><br />Opcja **Zainstaluj aktualizacje i aplikacje automatycznie zgodnie z harmonogramem** pozwala na zainstalowanie aktualizacji i aplikacji zgodnie z określonym harmonogramem.<br /><br />Zasada zależna **Użyj automatycznej obsługi dla komputerów z systemem Windows**  określa, że aktualizacje i aplikacje będą instalowane w ramach działania funkcji automatycznej konserwacji systemu Windows.<br /><br />Wybranie opcji **Monituj użytkownika o instalację** powoduje, że użytkownik będzie monitowany o instalację przygotowanej aktualizacji.<br /><br />Zalecane wartości:<br /><br />Wybrana opcja **Zainstaluj aktualizacje i aplikacje automatycznie zgodnie z harmonogramem**<br /><br />**Zaplanowany dzień: codziennie**<br /><br />**Zaplanowana godzina: 3:00**<br /><br />Wybrana opcja **Użyj automatycznej obsługi dla komputerów z systemem Windows**|
    |**Zezwalaj na natychmiastową instalację aktualizacji, które nie przerywają pracy systemu Windows** |Wybranie opcji **Zezwalaj** oznacza, że aktualizacje będą instalowane natychmiast po ich pobraniu, jeśli nie spowoduje to przerwania pracy lub ponownego uruchomienia systemu Windows. Aktualizacje mogące spowodować przerwanie pracy lub ponowne uruchomienie systemu Windows zostaną zainstalowane zgodnie z ustawieniem **Instalacja aktualizacji automatyczna lub z monitem** .<br /><br />Wybranie opcji **Nie zezwalaj** powoduje zainstalowanie aktualizacji zgodnie z ustawieniem **Instalacja aktualizacji automatyczna lub z monitem**.<br /><br />Zalecana wartość: **Zezwalaj** |
    |**Opóźnienie ponownego uruchomienia systemu Windows po zainstalowaniu zaplanowanych aktualizacji oraz aplikacji (w minutach)** |Określa czas oczekiwania (od 1 do 30 minut) na ponowne uruchomienie systemu Windows po zainstalowaniu zaplanowanych aktualizacji oraz aplikacji.<br /><br />Zalecana wartość: **15 minut** |
    |**Opóźnienie po ponownym uruchomieniu systemu Windows poprzedzające rozpoczęcie instalacji pominiętych zaplanowanych aktualizacji oraz aplikacji (w minutach)** |Określa czas oczekiwania (od 1 do 60 minut) na rozpoczęcie instalacji aktualizacji oraz aplikacji po ponownym uruchomieniu systemu Windows, gdy zaplanowana instalacja aktualizacji została pominięta.<br /><br />Zalecana wartość: **5 minut**|
    |**Zezwalaj zalogowanemu użytkownikowi na kontrolowanie ponownego uruchomienia systemu Windows po zainstalowaniu zaplanowanych aktualizacji oraz aplikacji** |Określa, czy zalogowany użytkownik może opóźniać ponowne uruchomienie systemu Windows (jeśli wybrano opcję **Tak**) lub czy ma być powiadamiany o automatycznym ponownym uruchomieniu systemu Windows (jeśli wybrano opcję **Nie**). Jeśli po zakończeniu instalacji zaplanowanych aktualizacji i aplikacji żaden użytkownik nie będzie zalogowany, system Windows zostanie ponownie uruchomiony, gdy będzie to wymagane. Jeśli wybrano domyślną opcję **Nie**, czas, który ma upłynąć przed ponownym uruchomieniem systemu Windows, jest ustawiony na 5 minut.<br /><br />Zalecana wartość: **Tak**|
    |**Monituj użytkownika o ponowne uruchomienie systemu Windows podczas obowiązkowych aktualizacji agenta klienta usługi Intune** |Określa, czy zalogowany użytkownik jest monitowany o ponowne uruchomienie systemu Windows, gdy obowiązkowa aktualizacja klienta usługi Intune wymaga ponownego uruchomienia systemu Windows.<br /><br />Zalecana wartość: **Tak**|
    |**Harmonogram instalacji obowiązkowych aktualizacji agenta klienta Microsoft Intune** |Określa, kiedy mają być instalowane aktualizacje klienta.<br /><br />Zalecana wartość: nie skonfigurowano|
    |**Opóźnienie między monitami o ponowne uruchomienie systemu Windows po instalacji zaplanowanych aktualizacji oraz aplikacji (w minutach)** |Określa, jak często użytkownik ma otrzymywać monit o ponowne uruchomienie systemu Windows po zainstalowaniu zaplanowanych aktualizacji lub aplikacji wymagających ponownego uruchomienia systemu Windows, gdy wybrano opcję opóźnienia ponownego uruchomienia (od 1 do 1440 minut).<br /><br />Zalecana wartość: **30 minut** |

## <a name="update-software-made-by-microsoft"></a>Aktualizowanie oprogramowania firmy Microsoft
Aktualizowanie oprogramowania firmy Microsoft wymaga bardzo małego wysiłku z Twojej strony. Jednak przed rozpoczęciem pracy należy skonfigurować ustawienia w dwóch obszarach:

- **Kategorie produktów i klasyfikacje aktualizacji** — definiują kategorie i klasyfikacje aktualizacji, które mają być dostępne dla komputerów. Możesz na przykład określić, że mają być instalowane tylko aktualizacje krytyczne pakietu Microsoft Office.

- **Reguły automatycznego zatwierdzania** — umożliwiają automatyczne zatwierdzanie określonych typów aktualizacji, co pozwala zmniejszyć liczbę czynności administracyjnych. Możesz na przykład automatycznie zatwierdzać wszystkie krytyczne aktualizacje oprogramowania.

Poniższe dwie procedury ułatwią przygotowanie się do korzystania z aktualizacji oprogramowania:

### <a name="configure-the-product-categories-and-update-classifications-you-want-to-make-available-to-managed-computers"></a>Konfigurowanie kategorii produktów i klasyfikacji aktualizacji, które mają być dostępne dla zarządzanych komputerów

1. W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/) wybierz kolejno pozycje **Administracja** &gt; **Aktualizacje**.

2. Na stronie **Ustawienia usługi: Aktualizacje** na liście **Kategoria produktu** wybierz kategorie aktualizacji, które mają być dostępne na komputerach. Najbardziej typowe aktualizacje są wybrane domyślnie.

    > [!IMPORTANT]
    > Aby mieć pewność, że będą instalowane aktualizacje zatwierdzone przez administratora, na komputerach zarejestrowanych w usłudze Intune nie może być stosowane ustawienie zasad grupy programu Windows Server Update Services (WSUS), **Określ lokalizację intranetowej usługi aktualizującej firmy Microsoft**.

3. Na liście **Klasyfikacja aktualizacji** wybierz klasy aktualizacji, które mają być dostępne dla zarządzanych komputerów. Najbardziej typowe opcje są również domyślnie zaznaczone.

4. Wybierz pozycję **Zapisz**, aby zapisać ustawienia.

### <a name="to-configure-automatic-approval-rules-for-software-updates"></a>Aby skonfigurować reguły automatycznego zatwierdzania aktualizacji oprogramowania

1. W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/) wybierz kolejno pozycje **Administracja** &gt; **Aktualizacje**.

2. W sekcji **Reguły automatycznego zatwierdzania** na stronie **Ustawienia serwera: Aktualizacje** wybierz pozycję **Nowy**.

3. Na stronie **Ogólne** kreatora tworzenia reguły automatycznego zatwierdzania wprowadź nazwę i opcjonalny opis reguły.

4. Na stronie **Kategorie produktów** zaznacz produkty, dla których aktualizacje mają być automatycznie zatwierdzane.

5. Na stronie **Klasyfikacje aktualizacji** określ klasyfikacje aktualizacji, które mają być automatycznie zatwierdzane.

6. Na stronie **Wdrożenie** wykonaj następujące czynności:

    - Wybierz grupy komputerów, w których chcesz wdrożyć nową regułę, a następnie wybierz pozycję **Dodaj**.

    - Aby określić ostateczny termin instalacji aktualizacji, zaznacz pole wyboru **Wymuś termin instalacji dla tych aktualizacji** , a następnie wybierz ostateczny termin instalacji na liście **Termin instalacji** .

        > [!NOTE]
        > W przypadku określenia ostatecznego terminu instalacji po upływie interwału terminu może być wymagane co najmniej jednokrotne ponowne uruchomienie zarządzanego komputera.

    - Gdy skończysz, wybierz pozycję **Dalej**.

7. Na stronie **Podsumowanie** sprawdź ustawienia nowej reguły, a następnie wybierz pozycję **Zakończ**.

Nowa reguła zostanie wyświetlona w sekcji **Reguły automatycznego zatwierdzania** na stronie **Ustawienia serwera: Aktualizacje** .

> [!NOTE]
> Nowo utworzona reguła automatycznego zatwierdzania dotyczy tylko przyszłych aktualizacji i nie powoduje automatycznego zatwierdzenia istniejących aktualizacji w usłudze Intune. Aby zatwierdzić istniejące aktualizacje, musisz uruchomić regułę automatycznego zatwierdzania.


### <a name="to-edit-run-or-delete-an-automatically-approved-update-rule"></a>Aby edytować, uruchomić lub usunąć automatycznie zatwierdzoną regułę aktualizacji

1. W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/) wybierz kolejno pozycje **Administracja** &gt; **Aktualizacje**.

2. W sekcji **Reguły automatycznego zatwierdzania** wybierz regułę, a następnie wykonaj jedną z następujących czynności:

    - Aby edytować regułę, wybierz pozycję **Edytuj**, a następnie zmień parametry reguły w **kreatorze reguły automatycznego zatwierdzania aktualizacji**.

    - Aby uruchomić regułę, wybierz pozycję **Uruchom wybrane**.

    - Aby usunąć regułę, wybierz pozycję **Usuń**.

        > [!NOTE]
        > Usunięcie reguły nie ma wpływu na poprzednie aktualizacje, które zostały zatwierdzone przez tę regułę.

## <a name="update-software-not-made-by-microsoft"></a>Aktualizowanie oprogramowania innych firm
Możesz wdrażać aktualizacje oprogramowania, które nie zostało utworzone przez firmę Microsoft. Aby to zrobić, użyj kreatora **Przekazywanie aktualizacji** , który umożliwia pobranie aktualizacji do magazynu w chmurze. Następnie możesz zatwierdzić lub odrzucić daną aktualizację tak jak w przypadku aktualizacji oprogramowania firmy Microsoft.

### <a name="to-upload-and-configure-a-third-party-update"></a>Aby przekazać i skonfigurować aktualizację innej firmy

1. W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/) wybierz kolejno pozycje **Aktualizacje** &gt; **Przegląd** &gt; **Przekaż**.

2. Na stronie **Pliki aktualizacji** wybierz pozycję **Przeglądaj** i wybierz pliki instalacyjne wymagane do zainstalowania pakietu aktualizacji. Może to być plik Instalatora Windows (msi), plik poprawki Instalatora Windows (msp) albo plik programu (exe). Możesz również dołączać dodatkowe pliki i foldery, które znajdują się w tym samym folderze co plik instalacyjny.

    Zostanie wyświetlony całkowity rozmiar plików do przekazania. Zwróć uwagę na to, że wyświetlona wartość nie obejmuje nieskompresowanych lub rozszerzonych plików instalacyjnych.

3. Po określeniu plików instalacyjnych na stronie **Opis aktualizacji** zostanie wyświetlona nazwa, opis i klasyfikacja oprogramowania. Są to informacje wyodrębnione przez usługę Intune z plików instalacyjnych oprogramowania. Możesz wybrać etykietę klasyfikacji dla typu wdrażanej aktualizacji (aktualizacje, aktualizacje krytyczne, aktualizacje zabezpieczeń, pakiety zbiorcze aktualizacji lub dodatki Service Pack). Gdy wszystko będzie gotowe, wybierz pozycję **Dalej**.

4. Na stronie **Wymagania** kreatora wybierz architekturę (32-bitową lub 64-bitową albo oba typy) i systemy operacyjne zarządzanych komputerów, których dotyczy ta aktualizacja.

5. Na stronie **Reguły wykrywania** określ sposób wykrywania aktualizacji na zarządzanych komputerach przez usługę Intune. W przypadku wybrania opcji domyślnej **Użyj domyślnych reguł wykrywania** pakiet aktualizacji na poszczególnych komputerach docelowych zostanie zainstalowany przez usługę Intune tylko raz.

    > [!NOTE]
    > Jeśli określony plik instalacyjny aktualizacji jest plikiem Instalatora Windows lub plikiem msp, strona **Reguły wykrywania** kreatora nie będzie widoczna. Jest tak dlatego, że pliki Instalatora Windows i pliki msp zawierają własne instrukcje dotyczące wykrywania poprzednich instalacji aktualizacji.

    Wybierz co najmniej jedną z następujących reguł umożliwiających określenie, czy aktualizacja jest już zainstalowana na zarządzanych komputerach:

    - **Plik istnieje**

    - **Kod produktu MSI istnieje**

    - **Klucz rejestru istnieje**

6. Wprowadź wszelkie dodatkowe informacje wymagane do skonfigurowania reguły wykrywania, takie jak ścieżka do pliku i nazwa pliku, kod produktu Instalatora Windows albo klucz rejestru, a następnie wybierz pozycję **Dalej**.

7. Na stronie **Wymagania wstępne** kreatora określ nazwy programów, które muszą być zainstalowane, aby można było zainstalować tę aktualizację. Możesz wybrać opcję **Brak**, wybrać pakiet oprogramowania, który został już dodany do usługi Intune i jest przez nią zarządzany, albo określić jedną z następujących reguł opisujących oprogramowanie:

    - **Plik istnieje**

    - **Kod produktu MSI istnieje**

    - **Klucz rejestru istnieje**

8. Wprowadź wszelkie dodatkowe informacje wymagane do skonfigurowania reguły wykrywania, takie jak ścieżka do pliku i nazwa pliku, kod produktu Instalatora Windows albo klucz rejestru, a następnie wybierz pozycję **Dalej**.

9. Na stronie **Argumenty wiersza polecenia** kreatora możesz dodać wymagane właściwości instalacji do wiersza polecenia instalacji w celu zmodyfikowania zachowania pliku instalacyjnego. Na przykład niektóre programy obsługują właściwość **/q**, która umożliwia przeprowadzenie instalacji dyskretnej. Więcej informacji o obsługiwanych argumentach wiersza polecenia można znaleźć w dokumentacji pakietu oprogramowania. Określ wymagane argumenty wiersza polecenia, a następnie wybierz pozycję **Dalej**.

    > [!NOTE]
    > Jeśli aktualizacja nie obsługuje instalacji dyskretnej, nie można zainstalować tej aktualizacji przy użyciu usługi Intune.

10. Na stronie **Kody powrotne** kreatora możesz określić sposób interpretowania kodów powrotu instalacji aktualizacji. W usłudze Intune są domyślnie używane standardowe kody powrotu umożliwiające komunikowanie powodzenia lub niepowodzenia instalacji pakietu aktualizacji. Obsługiwane kody powrotu są następujące:

|Kod powrotu|Szczegóły|
|---------------|------------------|
|**0**|Powodzenie|
|**3010**|Powodzenie z ponownym uruchomieniem komputera|

11. Wszystkie inne kody powrotu oznaczają niepowodzenie.
Niektóre aktualizacje korzystają z niestandardowych interpretacji kodów powrotu. W takich przypadkach możesz określić własne interpretacje kodów powrotu.

12. Określ lub zmień wymagane kody powrotu, a następnie wybierz pozycję **Dalej**.

13. Na stronie **Podsumowanie** kreatora przejrzyj listę działań, które zostaną podjęte, a następnie wybierz pozycję **Przekaż**, aby zakończyć pracę kreatora.

Przekazana aktualizacja zostanie zapisana w magazynie usługi Intune w chmurze. Jeśli masz za mało wolnego miejsca, aby przekazać pakiet aktualizacji, podczas procesu przekazywania zostanie wyświetlone odpowiednie powiadomienie. Usługa Intune nie może określić ilości potrzebnego miejsca przed rozpoczęciem przekazywania aktualizacji, ponieważ skompresowane pliki konfiguracyjne i instalacyjne wymagają więcej miejsca po zdekompresowaniu.

Po przekazaniu aktualizacji innej firmy do usługi Intune zostanie ona wyświetlona w obszarze roboczym **Aktualizacje** w okienku **Wszystkie aktualizacje**. Możesz ją wtedy zatwierdzić i wdrożyć. Aby uzyskać więcej informacji, zobacz poniższą sekcję „Zatwierdzanie i odrzucanie aktualizacji”.

## <a name="approve-and-decline-updates"></a>Zatwierdzanie i odrzucanie aktualizacji
Gdy aktualizacje będą gotowe do zainstalowania, w obszarze roboczym **Aktualizacje** na stronie **Przegląd aktualizacji** w sekcji **Stan aktualizacji**zostanie wyświetlony komunikat. Wybierz go, aby otworzyć stronę **Wszystkie aktualizacje** i sprawdzić, które aktualizacje są gotowe do zatwierdzenia.

Lista **Filtry** ułatwi znajdowanie aktualizacji. Na przykład możesz wyświetlić tylko aktualizacje, które zostały zastąpione, lub takie, których instalacja nie powiodła się.

Po wybraniu aktualizacji z listy zostaną udostępnione dodatkowe polecenia umożliwiające zarządzanie aktualizacjami. Zostały one przedstawione w poniższej tabeli:

|Zadanie|Szczegóły|
|--------|--------------------|
|**Wyświetl właściwości**|Wyświetla szczegółowe informacje o aktualizacji, w tym liczbę komputerów, których ona dotyczy.|
|**Edytowanie**|Dotyczy tylko aktualizacji innych firm. Umożliwia edytowanie właściwości aktualizacji.|
|**Zatwierdź**|Zatwierdza wybraną aktualizację i umożliwia wybranie grup, w których zostanie ona wdrożona. Więcej informacji można znaleźć w treści procedury **Aby zatwierdzić aktualizacje** w tym temacie.|
|**Odrzuć**|Usuwa wszystkie wcześniejsze zatwierdzenia aktualizacji i ukrywa ją w widokach domyślnych. Ponadto zostaną usunięte wszystkie dane raportów dotyczące aktualizacji.<br /><br />Jeśli zechcesz później odnaleźć odrzuconą aktualizację, na stronie **Wszystkie aktualizacje** ustaw filtr na wartość **Odrzucone**. Umożliwi Ci to zatwierdzenie tej aktualizacji w razie potrzeby.<br /><br />Jeśli aktualizacja wygasła w usłudze Microsoft Update i dlatego została odrzucona, nie może zostać zatwierdzona w konsoli administracyjnej usługi Intune.<br /><br />Usunięcie zasad aktualizacji, które zostały wdrożone na komputerach, spowoduje przywrócenie ustawień zasad aktualizacji do wartości domyślnych dla systemu operacyjnego zainstalowanego na komputerach.|
|**Usuwanie**|Dotyczy tylko aktualizacji innych firm. Usuwa wybraną aktualizację.|
|**Przekaż**|Uruchamia kreatora **Przekazywanie aktualizacji**, który umożliwia przekazywanie aktualizacji innych firm w celu ich wdrożenia.|

### <a name="to-approve-updates"></a>Aby zatwierdzić aktualizacje

1. W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/) kliknij kolejno pozycje **Aktualizacje** &gt; **Przegląd** &gt; **Nowe aktualizacje do zatwierdzenia**.

    W obszarze roboczym **Aktualizacje** wybierz pozycje **Przegląd**&gt;**Nowe aktualizacje do zatwierdzenia**.

    > [!NOTE]
    > Link **Nowe aktualizacje do zatwierdzenia** zostanie wyświetlony w obszarze **Stan aktualizacji** tylko wtedy, gdy będzie istnieć co najmniej jeden zarządzany komputer, który wymaga zatwierdzenia aktualizacji.

2. Wybierz aktualizację, przejrzyj jej właściwości na dole strony, aby upewnić się, że należy ją zatwierdzić, a następnie wybierz pozycję **Zatwierdź**. Możesz wybrać wiele aktualizacji, przytrzymując klawisz **CTRL** podczas zaznaczania poszczególnych pozycji.

3. Na stronie **Wybieranie grup** wybierz grupę, w której chcesz wdrożyć aktualizacje, a następnie wybierz pozycję **Dodaj**. Po wybraniu grup wybierz pozycję **Dalej**.

4. Na stronie **Akcja wdrażania** wykonaj następujące czynności dla każdej grupy na liście:

    - Na liście **Zatwierdzenie** wybierz jedną z następujących pozycji:

        - **Wymagana instalacja** — aktualizacja zostanie zainstalowana na komputerach w określonej grupie.

        - **Nie instaluj** — zostanie zgłoszone spełnienie wymagań zastosowania aktualizacji, ale nie zostanie ona zainstalowana.

        - **Dostępna instalacja** — użytkownik może zainstalować aplikację na żądanie z portalu firmy.

        - **Odinstaluj** — aktualizacje z komputerów w grupie docelowej zostaną usunięte.

            > [!IMPORTANT]
            > Aktualizacja zostanie usunięta, nawet jeśli nie została zainstalowana przez usługę Intune.

    - Na liście **Termin** wybierz jedną z następujących pozycji:

        - **Brak** — oznacza brak ostatecznego terminu wymuszenia instalacji aktualizacji. Użytkownicy mogą stale odrzucać tę aktualizację.

        - **Najszybciej, jak to możliwe** — przy najbliższej okazji aktualizacja zostanie zainstalowana na komputerach docelowych.

        - **Niestandardowy** — określa datę i godzinę instalacji zatwierdzonych aktualizacji.

        - **Jeden tydzień**, **Dwa tygodnie**, **Jeden miesiąc** — aktualizacja zostanie zainstalowana w ustalonym okresie.

5. Wybierz pozycję **Zakończ**, aby zapisać ustawienia, lub **Anuluj**, aby je odrzucić i powrócić do listy aktualizacji.

    > [!IMPORTANT]
    > Jeśli dla grupy podrzędnej nie skonfigurowano jawnie akcji **Nie instaluj**, **Wymagana instalacja**lub **Odinstaluj** , akcja skonfigurowana dla grupy nadrzędnej jest dziedziczona przez wszystkie elementy podrzędne.

6. Przypomnienia dotyczące aktualizacji są dostępne w okienku szczegółów na dole strony **Wszystkie aktualizacje** .


## <a name="see-also"></a>Zobacz także
[Zasady ochrony komputerów z systemem Windows](policies-to-protect-windows-pcs-in-microsoft-intune.md)
