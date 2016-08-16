---
title: "Typowe zadania związane z zarządzaniem komputerem z systemem Windows | Microsoft Intune"
description: "Przejrzyj zadania przedstawione w tym temacie, aby dowiedzieć się, jak zarządzać komputerami z uruchomionym oprogramowaniem klienckim usługi Intune."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 08/04/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: eb912c73-54d2-4d78-ac34-3cbe825804c7
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: dcfa3af374a7e64e931508e1a8022bf8a50c71a7
ms.openlocfilehash: 93d5718fcd9949945180434b0f89eea96e92bbc6


---

# Typowe zadania związane z zarządzaniem komputerem z systemem Windows za pomocą klienta komputerowego usługi Microsoft Intune
Przejrzyj zadania przedstawione w tym temacie, aby dowiedzieć się, jak zarządzać komputerami z uruchomionym oprogramowaniem klienckim usługi Intune. Jeśli klient nie został jeszcze zainstalowany na komputerach, zobacz [Instalowanie klienta komputera z systemem Windows przy użyciu usługi Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).


## Upraszczanie zarządzania komputerami przy użyciu zasad
### Zarządzanie Zaporą systemu Windows
Zastosowanie zasad upraszcza administrowanie ustawieniami Zapory systemu Windows na zarządzanych komputerach. Aby uzyskać szczegółowe informacje, zobacz [Ochrona komputerów z systemem Windows przy użyciu zasad Zapory systemu Windows w usłudze Microsoft Intune](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md).

### Zarządzanie programem Microsoft Intune Center
Program Microsoft Intune Center umożliwia użytkownikom:

-   Pobieranie aplikacji z Portalu firmy.

-   Wyszukiwanie aktualizacji.

-   Zarządzanie programem Endpoint Protection usługi Microsoft Intune.

-  Wysyłanie żądań pomocy zdalnej.

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
Zasady umożliwiają konfigurowanie ustawień używanych na zarządzanych komputerach do wyszukiwania aktualizacji oprogramowania firmy Microsoft i innych firm oraz do ich pobierania. Aby uzyskać więcej informacji, zobacz [Zapewnianie aktualności oprogramowania na komputerach z systemem Windows za pomocą aktualizacji w usłudze Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).

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

3.  Wybierz pozycję **Wyświetl raport**, aby otworzyć nowe okno **Raport o spisie komputerów**.

    Raport można sortować według dowolnej kolumny, na przykład **Nazwa**, **Typ obudowy** lub **Producent** , wybierając jej nagłówek.

### Aby wyświetlić oprogramowanie zainstalowane na komputerach

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/) wybierz kolejno pozycje **Raporty** &gt; **Wykryte raporty oprogramowania**.

2.  Na stronie **Utwórz nowy raport** zaakceptuj wartości domyślne lub dostosuj je, aby filtrować wyniki zwracane w raporcie. Na przykład możesz określić, że w raporcie będzie wyświetlane tylko oprogramowanie opublikowane przez firmę Microsoft.

3.  Wybierz pozycję **Wyświetl raport**, aby otworzyć nowe okno **Raport z wykrytego oprogramowania**.

    Raport można sortować według dowolnej kolumny, na przykład **Nazwa**, **Wydawca** lub **Kategoria**, wybierając jej nagłówek. Można rozwinąć aktualizacje na liście w celu wyświetlenia większej liczby szczegółów (takich jak komputery, na których zainstalowano aktualizacje), wybierając strzałkę kierunkową obok elementu listy.

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

2.  Wybierz urządzenia do wycofania, a następnie wybierz pozycję **Wycofaj/wyczyść**.

Aby ponownie zarejestrować komputer w usłudze Intune, należy jeszcze raz zainstalować oprogramowanie klienckie na komputerze, korzystając z informacji przedstawionych w temacie [Instalowanie klienta komputera z systemem Windows przy użyciu usługi Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).

Jeśli komputer nie może nawiązać połączenia z usługą Intune, w obszarze roboczym **Pulpit nawigacyjny** zostanie wyświetlony komunikat.

W przypadku wycofywania komputera:

-   Komputer jest usuwany z zarządzania i spisu w usłudze Intune, a skojarzona z nim licencja jest udostępniana do ponownego użycia. Polecenie Wycofaj/wyczyść usuwa oprogramowanie klienckie usługi Intune, ale nie usuwa aplikacji ani danych z komputera.

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
Przed wdrożeniem oprogramowania dla użytkownika należy połączyć użytkownika z komputerem. Użytkownika można połączyć z wieloma komputerami, ale każdy komputer można połączyć tylko z jednym użytkownikiem. Użytkownicy są automatycznie łączeni ze wszystkimi komputerami, które są przez nich rejestrowane w usłudze Intune przy użyciu portalu firmy.

### Aby połączyć użytkownika z komputerem

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/) wybierz kolejno pozycje **Grupy** &gt; **Wszystkie urządzenia** (lub inną grupę zawierającą komputer, który chcesz połączyć z użytkownikiem).

2.  Wybierz komputer, który chcesz połączyć z użytkownikiem, a następnie wybierz pozycję **Połącz użytkownika**.

    W oknie dialogowym **Połącz użytkownika** jest wyświetlana lista dostępnych użytkowników z następującymi informacjami: nazwa wyświetlana, identyfikator użytkownika i liczba komputerów, z którymi użytkownik jest aktualnie połączony. Jeśli użytkownik został już połączony z wybranym komputerem, jego nazwa i identyfikator są wyświetlane w obszarze **Bieżący użytkownik**. Jeśli komputer nie został połączony z żadnym użytkownikiem, w obszarze **Bieżący użytkownik** zostanie wyświetlona wartość **Brak użytkownika**.

3.  Wykonaj jedną z następujących czynności:

    -   Aby pozostawić komputer połączony z bieżącym użytkownikiem (jeśli istnieje), wybierz pozycję **Anuluj**.

    -   Aby usunąć połączenie z bieżącym użytkownikiem (jeśli istnieje), wybierz kolejno pozycje **Usuń łącze** &gt; **OK**.

    -   Aby połączyć komputer z nowym użytkownikiem, wybierz użytkownika na liście **Wszyscy użytkownicy** . Potwierdź, że dane użytkownika są prawidłowe, a następnie wybierz pozycję **OK**.

> [!TIP]
> Jeśli chcesz ograniczyć użytkownikom końcowym możliwość łączenia z komputerami, włącz opcję **Ogranicz użytkownikowi możliwość łączenia z komputerami** w zasadach **Ustawienia agenta usługi Microsoft Intune**.

## Żądanie i zapewnianie pomocy zdalnej na komputerach z systemem Windows, które używają oprogramowania klienckiego usługi Intune

Usługa Microsoft Intune może korzystać z oprogramowania [TeamViewer](https://www.teamviewer.com), aby umożliwić użytkownikom komputerów z uruchomionym oprogramowaniem klienckim usługi Intune uzyskiwanie pomocy zdalnej. Gdy użytkownik zażąda pomocy w programie Microsoft Intune Center, otrzymasz alert informujący o żądaniu, a następnie możesz zaakceptować żądanie i udzielić użytkownikowi pomocy.
Ta funkcja zastępuje istniejącą funkcję Pomoc zdalna systemu Windows w usłudze Intune.


### Przed rozpoczęciem

Zanim zaczniesz korzystać z żądań pomocy zdalnej i odpowiadać na nie, musisz upewnić się, że zostały spełnione następujące wymagania wstępne:

- Masz [utworzone konto programu TeamViewer](https://login.teamviewer.com/LogOn#register) w celu logowania się do witryny sieci Web programu TeamViewer.
- Komputery z systemem Windows, którymi chcesz administrować, muszą być [zarządzane przez klienta komputera z systemem Windows](manage-windows-pcs-with-microsoft-intune.md)
- Można administrować wszystkimi systemami operacyjnymi Windows obsługiwanymi przez usługę Intune.

### Konfigurowanie łącznika programu TeamViewer

1. W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) wybierz pozycję **Administracja**.
2. W obszarze roboczym **Administracja** wybierz pozycję **TeamViewer**.
3. Na stronie **TeamViewer** w obszarze **Łącznik programu TeamViewer** wybierz opcję **Włącz**.
4. W oknie dialogowym **Włączanie programu TeamViewer** przejrzyj, a następnie **Zaakceptuj** postanowienia licencyjne. Jeśli nie masz jeszcze licencji programu TeamViewer, wybierz opcję **Kup licencję programu TeamViewer**.
5. Po otwarciu okna przeglądarki programu TeamViewer zaloguj się do witryny przy użyciu poświadczeń programu TeamViewer.
6. W witrynie programu TeamViewer przeczytaj, a następnie zaakceptuj opcje, aby umożliwić usłudze Intune połączenie z programem TeamViewer.
7. W konsoli usługi Intune upewnij się, że element **Łącznik programu TeamViewer** jest wyświetlany jako **Włączony**.


### Otwieranie żądania pomocy zdalnej (użytkownik końcowy)

1. Na komputerze klienckim z systemem Windows otwórz program **Microsoft Intune Center**.
2. W obszarze **Pomoc zdalna** wybierz pozycję **Żądaj pomocy zdalnej**.
3. Po zatwierdzeniu żądania (patrz poniżej) program TeamViewer jest otwierany na komputerze klienckim. Użytkownik musi zaakceptować komunikaty wskazujące, że przeglądarka sieci Web próbuje otworzyć aplikację TeamViewer.
4. Użytkownik zobaczy komunikat z pytaniem, czy możesz przejąć kontrolę nad jego komputerem. Musi zaakceptować ten komunikat, aby kontynuować.
5. Podczas sesji pomocy zdalnej użytkownik widzi okno wskazujące, że masz z nim połączenie. Jeśli zamknie to okno, sesja zdalna zostanie zakończona.

### Odpowiadanie na żądanie pomocy zdalnej

1. Gdy użytkownik prześle żądanie pomocy zdalnej, możesz je wyświetlić w obszarze roboczym **Alerty** w obszarze **Monitorowanie** > **Pomoc zdalna**. Na przykład:
> ![Zrzut ekranu przedstawiający żądanie pomocy zdalnej](./media/team-viewer.png)

<br>Jeśli żądanie pozostanie bez odpowiedzi przez więcej niż 4 godziny, zostanie usunięte.
2. Aby zaakceptować żądanie, wybierz pozycję **Zatwierdź żądanie i uruchom pomoc zdalną**.
3. W oknie dialogowym **Oczekuje nowe żądanie pomocy zdalnej** wybierz pozycję **Zaakceptuj żądanie pomocy zdalnej**. Jeśli jeszcze ich nie zainstalowano, program TeamViewer zainstaluje wszelkie niezbędne aplikacje na komputerze.
4. Program TeamViewer powiadomi następnie użytkownika końcowego, że chcesz przejąć kontrolę nad jego komputerem. Po zatwierdzeniu żądania przez użytkownika okno programu TeamViewer zostanie otwarte i możesz sterować jego komputerem.

Podczas sesji pomocy zdalnej możesz korzystać ze wszystkich dostępnych poleceń programu TeamViewer do sterowania komputerem zdalnym. Aby uzyskać pomoc dotyczącą tych poleceń, pobierz publikację [Manual for remote control](http://www.teamviewer.com/en/support/documents/) (Podręcznik zdalnego sterowania) z witryny sieci Web programu TeamViewer.

### Zamykanie sesji pomocy zdalnej

Z menu **Akcje** okna programu **TeamViewer** wybierz polecenie **Zakończ sesję**.



<!--HONumber=Aug16_HO1-->


