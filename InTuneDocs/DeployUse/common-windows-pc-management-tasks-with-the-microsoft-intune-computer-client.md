---
# required metadata

title: Typowe zadania związane z zarządzaniem komputerem z systemem Windows | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: eb912c73-54d2-4d78-ac34-3cbe825804c7

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Typowe zadania związane z zarządzaniem komputerem z systemem Windows za pomocą klienta komputerowego usługi Microsoft Intune
Przejrzyj zadania przedstawione w tym temacie, aby dowiedzieć się, jak zarządzać komputerami z uruchomionym klientem usługi Intune. Jeśli klient nie został jeszcze zainstalowany na komputerach, zobacz [Instalowanie klienta komputera z systemem Windows przy użyciu usługi Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).


## Upraszczanie zarządzania komputerami przy użyciu zasad
### Zarządzanie Zaporą systemu Windows
Zastosowanie zasad upraszcza administrowanie ustawieniami Zapory systemu Windows na zarządzanych komputerach. Aby uzyskać szczegółowe informacje, zobacz [Ochrona komputerów z systemem Windows przy użyciu zasad Zapory systemu Windows w usłudze Microsoft Intune](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md).

### Zarządzanie programem Microsoft Intune Center
Program Microsoft Intune Center umożliwia użytkownikom:

-   Pobieranie aplikacji z Portalu firmy.

-   Wyszukiwanie aktualizacji.

-   Zarządzanie programem Endpoint Protection usługi Microsoft Intune.

-   Wysyłanie żądań pomocy zdalnej.

Program Microsoft Intune Center jest instalowany na wszystkich zarządzanych komputerach. W zasadach usługi Intune można skonfigurować następujące ustawienia (są one widoczne dla użytkowników programu Microsoft Intune Center):

|Ustawienie zasad|Szczegóły|
|------------------|--------------------|
|**Nazwa**|Nazwa administratora, który zarządza komputerem.<br /><br />Maksymalna długość: 40 znaków|
|**Numer telefonu**|Numer telefonu administratora, który zarządza komputerem.<br /><br />Maksymalna długość: 20 znaków|
|**Adres e-mail**|Adres e-mail administratora, który zarządza komputerem.<br /><br />Maksymalna długość: 40 znaków|
|**Nazwa witryny sieci Web**|Nazwa witryny sieci Web pomocy technicznej dla użytkowników.<br /><br />Maksymalna długość: 40 znaków|
|**Adres URL witryny sieci Web**|Adres URL witryny sieci Web pomocy technicznej.<br /><br />Maksymalna długość: 150 znaków|
|**Uwagi**|Uwaga widoczna dla użytkowników.<br /><br />Maksymalna długość: 120 znaków|

### Zarządzanie ustawieniami aktualizacji oprogramowania
Zasady umożliwiają konfigurowanie ustawień używanych na zarządzanych komputerach do wyszukiwania aktualizacji oprogramowania firmy Microsoft i innych firm oraz do ich pobierania. Aby uzyskać więcej informacji, zobacz [Zapewnianie aktualności oprogramowania na komputerach z systemem Windows za pomocą aktualizacji w usłudze Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md)..

### Zarządzanie ustawieniami programu Endpoint Protection
Zasady umożliwiają konfigurowanie ustawień programu Endpoint Protection wdrażanych następnie na zarządzanych komputerach. Są one związane między innymi z harmonogramami skanowania i akcjami wykonywanymi w przypadku wykrycia złośliwego oprogramowania. Aby uzyskać więcej informacji, zobacz [Zabezpieczanie komputerów z systemem Windows przy użyciu programu Endpoint Protection dla usługi Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).

## Wyświetlanie spisu sprzętu i oprogramowania
Usługa Intune zbiera szczegółowe informacje o sprzęcie i oprogramowaniu zarządzanych komputerów. Poniżej opisano kroki procedur:

-   Tworzenia raportu zawierającego informacje na temat możliwości sprzętu komputerów.

-   Tworzenia raportu zawierającego listę programów zainstalowanych na każdym komputerze.

-   Odświeżania spisu komputerów w celu upewnienia się, że raport zawiera aktualne dane.

### Aby wyświetlić informacje o komputerach

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/) wybierz kolejno pozycje **Raporty** &gt; **Raporty ze spisu komputerów**.

2.  Na stronie **Utwórz nowy raport** zaakceptuj wartości domyślne lub dostosuj je, aby filtrować wyniki zwracane w raporcie. Możesz na przykład wybrać opcję wyświetlania w raporcie tylko komputerów z systemem Windows 8.1.

3.  Wybierz pozycję **Wyświetl raport** , aby otworzyć nowe okno **Raport o spisie komputerów**.

    Raport można sortować według dowolnej kolumny, na przykład **Nazwa**, **Typ obudowy** lub **Producent** , wybierając jej nagłówek.

### Aby wyświetlić oprogramowanie zainstalowane na komputerach

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/) wybierz kolejno pozycje **Raporty** &gt; **Wykryte raporty oprogramowania**.

2.  Na stronie **Utwórz nowy raport** zaakceptuj wartości domyślne lub dostosuj je, aby filtrować wyniki zwracane w raporcie. Na przykład możesz określić, że w raporcie będzie wyświetlane tylko oprogramowanie opublikowane przez firmę Microsoft.

3.  Wybierz pozycję **Wyświetl raport** , aby otworzyć nowe okno **Raport z wykrytego oprogramowania**.

    Raport można sortować według dowolnej kolumny, na przykład **Nazwa**, **Wydawca** lub **Kategoria**, wybierając jej nagłówek. Można rozwinąć aktualizacje na liście w celu wyświetlenia większej liczby szczegółów (takich jak komputery, na których zainstalowano aktualizacje), klikając strzałkę kierunkową obok elementu listy.

### Aby odświeżyć spis komputerów w celu upewnienia się, że jest on aktualny

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/) wybierz kolejno pozycje **Grupy** &gt; **Wszystkie urządzenia** (lub inną grupę zawierającą komputer, dla którego chcesz odświeżyć spis).

2.  Wybierz komputer lub naciśnij i przytrzymaj klawisz **Ctrl** , aby wybrać wiele komputerów.

3.  Na pasku zadań wybierz kolejno pozycje **Zadania zdalne** &gt; **Odśwież zapasy**.

4.  Aby wyświetlić stan zadania, wybierz pozycję **Zadania zdalne** w prawym dolnym rogu strony.

    W oknie dialogowym **Stan zadania** są wyświetlane bieżące zadania zdalne, stan zadania, nazwa urządzenia i wszelkie zgłoszone błędy. Okno zawiera również link do informacji dotyczących rozwiązywania problemów.


## Zdalne ponowne uruchamianie komputera z systemem Windows

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/) wybierz kolejno pozycje **Grupy** &gt; **Wszystkie urządzenia** (lub inną grupę zawierającą komputer, który chcesz ponownie uruchomić).

2.  Wybierz co najmniej jeden komputer, a następnie wybierz kolejno pozycje **Zadania zdalne** &gt; **Uruchom ponownie komputer**.

3.  Aby wyświetlić stan zadania, wybierz pozycję **Zadania zdalne** w prawym dolnym rogu strony.

4.  W oknie dialogowym **Stan zadania** przejrzyj bieżące zadania zdalne, stan zadania, nazwę urządzenia i wszystkie zgłoszone błędy.

## Wycofywanie komputera

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/) wybierz kolejno pozycje **Grupy** &gt; **Wszystkie urządzenia** (lub inną grupę zawierającą komputer, który chcesz wycofać).

2.  Wybierz urządzenia do wycofania, a następnie wybierz pozycję **Wycofaj/wyczyść**..

Aby ponownie zarejestrować komputer w usłudze Intune, należy jeszcze raz zainstalować oprogramowanie klienckie na komputerze, korzystając z informacji przedstawionych w temacie [Instalowanie klienta komputera z systemem Windows przy użyciu usługi Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).

Jeśli komputer nie może nawiązać połączenia z usługą Intune, w obszarze roboczym **Pulpit nawigacyjny** zostanie wyświetlony komunikat.

W przypadku wycofywania komputera:

-   Komputer jest usuwany ze spisu usługi Intune, a skojarzona z nim licencja jest udostępniana do ponownego użycia.

-   Jego stan nie jest już wyświetlany w konsoli usługi Intune.

-   Usługa Intune usuwa oprogramowanie klienckie z komputera. Jeśli komputer jest połączony z usługą Intune, oprogramowanie klienckie zostanie usunięte po kolejnym nawiązaniu połączenia.

-   Program Microsoft Intune Endpoint Protection jest usuwany z komputera. Jeśli na komputerze zainstalowano inną aplikację ochrony punktu końcowego, która jest wyłączona, można ją ponownie włączyć po usunięciu programu Microsoft Intune Endpoint Protection, aby upewnić się, że komputery są chronione.

-   Wszystkie zasady są usuwane z komputera, a wartości ustawione przez zasady są zmieniane.

-   Komputer nie będzie już otrzymywać aktualizacji oprogramowania ani aktualizacji definicji złośliwego oprogramowania z usługi Intune.

-   W zależności od konfiguracji wycofane komputery mogą nadal otrzymywać aktualizacje w ramach usług Windows Server Update Services, Windows Update lub Microsoft Update.

    > [!IMPORTANT]
    > Jeśli oprogramowanie klienckie zostało zainstalowany przy użyciu obiektu zasad grupy, przed usunięciem tego oprogramowania należy usunąć obiekt zasad grupy, aby zapobiec ponownej instalacji oprogramowania.

    Jeśli odinstalowanie klienta nie powiedzie się, zapoznaj się z sekcją [Rozwiązywanie problemów z programem Endpoint Protection](/intune/troubleshoot/troubleshoot-endpoint-protection-in-microsoft-intune), aby uzyskać dalszą pomoc.

## Zarządzanie łączeniem użytkownika z urządzeniem
Przed wdrożeniem oprogramowania dla użytkownika należy połączyć użytkownika z komputerem. Użytkownika można połączyć z wieloma komputerami, ale każdy komputer można połączyć tylko z jednym użytkownikiem. Użytkownicy są automatycznie łączeni ze wszystkimi komputerami, które są przez nich rejestrowane w usłudze Intune przy użyciu Portalu firmy.

### Aby połączyć użytkownika z komputerem

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/) wybierz kolejno pozycje **Grupy** &gt; **Wszystkie urządzenia** (lub inną grupę zawierającą komputer, który chcesz połączyć z użytkownikiem).

2.  Wybierz komputer, który chcesz połączyć z użytkownikiem, a następnie wybierz pozycję **Połącz użytkownika**.

    W oknie dialogowym **Połącz użytkownika** jest wyświetlana lista dostępnych użytkowników z następującymi informacjami: nazwa wyświetlana, identyfikator użytkownika i liczba komputerów, z którymi użytkownik jest aktualnie połączony. Jeśli użytkownik został już połączony z wybranym komputerem, jego nazwa i identyfikator są wyświetlane w obszarze **Bieżący użytkownik**. Jeśli komputer nie został połączony z żadnym użytkownikiem, w obszarze **Bieżący użytkownik** zostanie wyświetlona wartość **Brak użytkownika**.

3.  Wykonaj jedną z następujących czynności:

    -   Aby opuścić komputer połączony z bieżącym użytkownikiem (jeśli istnieje), wybierz pozycję **Anuluj**.

    -   Aby usunąć połączenie z bieżącym użytkownikiem (jeśli istnieje), wybierz kolejno pozycje **Usuń łącze**&gt;**OK**.

    -   Aby połączyć komputer z nowym użytkownikiem, wybierz użytkownika na liście **Wszyscy użytkownicy** . Potwierdź, że dane użytkownika są prawidłowe, a następnie wybierz pozycję **OK**.

> [!TIP]
> Jeśli chcesz ograniczyć użytkownikom końcowym możliwość łączenia z komputerami, włącz opcję **Ogranicz użytkownikowi możliwość łączenia z komputerami** w zasadach **Ustawienia agenta usługi Microsoft Intune**.

## Odpowiadanie na żądanie pomocy zdalnej
Użytkownicy mogą zgłosić żądanie pomocy przy użyciu funkcji Pomoc zdalna za pośrednictwem usługi Microsoft Easy Assist, która jest automatycznie instalowana na zarządzanych komputerach. Po wysłaniu żądania w konsoli usługi Intune zostanie wyświetlony alert.

> [!IMPORTANT]
> Pomoc zdalna nie jest obsługiwana na komputerach z systemem Windows 8 lub nowszym.
>
> W przypadku zaakceptowania żądania pomocy zdalnej wysłanego z komputera bez zainstalowanej usługi Microsoft Easy Assist użytkownik otrzyma monit o jej zainstalowanie. Po zakończeniu instalacji należy ponownie uruchomić komputer. Rozważ wstępne pobranie usługi Microsoft Easy Assist na komputerach użytkownika, aby uniknąć konieczności ponownego uruchamiania.

### Aby zarządzać żądaniem pomocy zdalnej

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/) wybierz kolejno pozycje **Alerty** &gt; **Pomoc zdalna**.

2.  Wybierz żądanie pomocy zdalnej na liście **Alerty** , aby otworzyć stronę właściwości żądania.

3.  Wybierz pozycję **Zatwierdź żądanie i uruchom pomoc zdalną**, aby otworzyć okno dialogowe z opcjami postępowania po otrzymaniu alertu.

4.  Wykonaj jedną z następujących czynności:

    -   **Zaakceptuj żądanie** — aby dołączyć do sesji zdalnej, wybierz pozycję **Zaakceptuj żądanie pomocy zdalnej**..

        Użytkownik zobaczy następujący komunikat: **Żądanie zostało zaakceptowane. Postępuj zgodnie z instrukcjami usługi Easy Assist, aby udostępnić program lub pulpit administratorowi systemu**.

        > [!IMPORTANT]
        > Nie można zaakceptować żądania pomocy zdalnej na komputerze Mac, na którym uruchomiono konsolę administratora usługi Intune.

    -   **Odrzuć żądanie** — zamknij okno **Wyświetl informacje dotyczące rozwiązywania problemów**, a następnie wybierz pozycję **Zamknij ten alert** w oknie właściwości alertu.

        Żądanie zostanie zamknięte, a użytkownik zobaczy komunikat informujący o odrzuceniu żądania. Aby jeszcze raz poprosić o pomoc zdalną, użytkownik musi wysłać nowe żądanie pomocy zdalnej. Jeśli alert dotyczący pomocy zdalnej zostanie przypadkowo zamknięty, skontaktuj się z użytkownikiem, który wysłał żądanie pomocy zdalnej, aby poprosić go o wysłanie nowego żądania.


<!--HONumber=May16_HO1-->


