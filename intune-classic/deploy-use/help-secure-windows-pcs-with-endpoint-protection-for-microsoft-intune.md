---
title: Program Endpoint Protection dla komputerów z systemem Windows
description: Zabezpiecz zarządzane komputery przy użyciu programu Endpoint Protection, który zapewnia ochronę w czasie rzeczywistym przed złośliwym oprogramowaniem.
keywords: ''
author: nathbarn
ms.author: nathbarn
manager: dougeby
ms.date: 03/06/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 002241bf-6cd0-4c75-a4f0-891ac7e6721a
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 72a4e977f88a7f397d4f37f723ca1f13c4bc689c
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
ms.locfileid: "31030280"
---
# <a name="help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune"></a>Zabezpieczanie komputerów z systemem Windows przy użyciu programu Endpoint Protection dla usługi Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Usługa Microsoft Intune może pomóc w zabezpieczaniu zarządzanych komputerów za pomocą programu Endpoint Protection, który zapewnia ochronę w czasie rzeczywistym przed złośliwym oprogramowaniem i aktualność definicji złośliwego oprogramowania oraz automatycznie skanuje komputery. Ponadto program Endpoint Protection udostępnia narzędzia, które ułatwiają radzenie sobie z atakami złośliwego oprogramowania i ich monitorowanie.

Jeśli klient usługi Intune nie został jeszcze zainstalowany na komputerach, zobacz [Instalowanie klienta komputera z systemem Windows przy użyciu usługi Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).

W poniższych sekcjach przedstawiono informacje pomocne w konfigurowaniu, wdrażaniu i monitorowaniu programu Endpoint Protection.

## <a name="choose-when-to-use-endpoint-protection"></a>Wybieranie, kiedy należy używać programu Endpoint Protection
Jednym z podstawowych zadań administratora IT jest ochrona zarządzanych komputerów przed złośliwym oprogramowaniem i wirusami. Przed wdrożeniem usługi Intune na komputerach z systemem Windows w organizacji należy podjąć decyzję dotyczącą sposobu ochrony komputerów. W tym celu wybierz jedną z poniższych opcji i skonfiguruj odpowiednie ustawienia zasad:


|                                                                                                                                                                       Zamierzenia:                                                                                                                                                                        |                                                                                                       Ustawienia zasad programu Endpoint Protection                                                                                                        |                                                                                                                                                  Więcej informacji                                                                                                                                                  |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                             Korzystanie z programu Endpoint Protection usługi Microsoft Intune tylko wtedy, gdy nie jest zainstalowana inna aplikacja ochrony punktu końcowego.<br /><br />Możesz użyć programu Endpoint Protection usługi Microsoft Intune na wszystkich komputerach, na których nie jest zainstalowana inna aplikacja ochrony punktu końcowego.                                              | Zainstaluj program Endpoint Protection = <strong>Tak</strong><br /><br />Włącz program Endpoint Protection = <strong>Tak</strong><br /><br />Zainstaluj program Endpoint Protection, nawet jeśli jest zainstalowana inna aplikacja ochrony punktu końcowego = <strong>Nie</strong>  |                                                                      Gdy zostanie wykryta aplikacja ochrony punktu końcowego innej firmy, program Endpoint Protection usługi Microsoft Intune nie zostanie zainstalowany lub zostanie odinstalowany, jeśli został już zainstalowany wcześniej.                                                                       |
| Korzystanie z programu Endpoint Protection usługi Microsoft Intune nawet wtedy, gdy jest zainstalowana inna aplikacja ochrony punktu końcowego.<br /><br />Wybranie tej metody oznacza, że program Endpoint Protection usługi Microsoft Intune oraz aplikacja ochrony punktu końcowego innej firmy będą uruchomione jednocześnie. Ta konfiguracja nie jest zalecana ze względu na potencjalne problemy z wydajnością. | Zainstaluj program Endpoint Protection = <strong>Tak</strong><br /><br />Włącz program Endpoint Protection = <strong>Tak</strong><br /><br />Zainstaluj program Endpoint Protection, nawet jeśli jest zainstalowana inna aplikacja ochrony punktu końcowego = <strong>Tak</strong> |                        Zastosowania:<br /><br />— Chcesz rozpocząć korzystanie z programu Microsoft Intune Endpoint Protection.<br />— Wdrażasz nowego klienta, który będzie używać programu Microsoft Intune Endpoint Protection.<br />— Uaktualniasz dowolnego klienta, który będzie używać programu Microsoft Intune Endpoint Protection.                         |
|                                                                                                             Korzystanie z usługi Intune bez programu Endpoint Protection usługi Microsoft Intune. Zamiast tego będzie używana aplikacja ochrony punktu końcowego innej firmy.                                                                                                             |                                                                                                Zainstaluj program Endpoint Protection = <strong>Nie</strong>                                                                                                 | Ta konfiguracja nie jest zalecana w przypadku nieużywania aplikacji ochrony punktu końcowego innej firmy, ponieważ może spowodować narażenie komputerów w organizacji na działanie złośliwego oprogramowania lub inne ataki.<br /><br />Program Endpoint Protection usługi Microsoft Intune nie zostanie zainstalowany lub zostanie odinstalowany, jeśli był zainstalowany wcześniej. |

Aby zmienić obecnie używaną aplikację ochrony punktu końcowego na program Endpoint Protection usługi Microsoft Intune, wykonaj następujące czynności:

1.  Pozostaw włączoną aktualnie używaną aplikację ochrony punktu końcowego i wdróż oprogramowanie klienckie usługi Intune na komputerach.

2.  Upewnij się, że program Endpoint Protection usługi Microsoft Intune jest zainstalowany i pomaga chronić komputery klienckie.

3.  Usuń oprogramowanie ochrony punktu końcowego innej firmy, wykonując następujące czynności:

    -   Przy użyciu dystrybucji oprogramowania usługi Intune wdróż narzędzie do usuwania oprogramowania dostarczone przez producenta aplikacji ochrony punktu końcowego innej firmy. Aby uzyskać więcej informacji, zobacz [Wdrażanie aplikacji przy użyciu usługi Microsoft Intune](deploy-apps.md).

    -   Usuń ręcznie aplikację ochrony punktu końcowego innej firmy.

> [!NOTE]
> Usługa Intune nie odinstaluje automatycznie aplikacji ochrony punktu końcowego innych firm.

## <a name="configure-microsoft-intune-endpoint-protection"></a>Konfigurowanie programu Endpoint Protection usługi Microsoft Intune
Aby skonfigurować program Endpoint Protection usługi Microsoft Intune, wykonaj następujące czynności.

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/) wybierz pozycję **Zasady** > **Dodaj zasady**.

2.  Rozwiń węzeł **Zarządzanie komputerem**, a następnie wybierz pozycję **Ustawienia agenta usługi Microsoft Intune**. Wybierz pozycję **Utwórz zasady niestandardowe i przeprowadź ich wdrożenie**, aby określić zasady ustawień programu Endpoint Protection. Następnie wybierz przycisk **Utwórz zasady**.

Możesz użyć zalecanych ustawień lub dostosować je. Aby uzyskać więcej informacji dotyczących sposobu tworzenia i wdrażania zasad, zobacz temat [Typowe zadania związane z zarządzaniem komputerem z systemem Windows za pomocą klienta komputerowego usługi Microsoft Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md).

  ![Ustawienia programu Endpoint Protection](./media/pol-sa-pc-endpoint-policy.png)

Wdrożone zasady programu Endpoint Protection można wyświetlić w obszarze roboczym **Zasady** na stronie **Wszystkie zasady**.

## <a name="specify-endpoint-protection-service-settings"></a>Określanie ustawień usługi Endpoint Protection

|                                                 Ustawienie zasad                                                  |                                                                                                                                                                                                                                                                                                                                                                                                             Szczegóły                                                                                                                                                                                                                                                                                                                                                                                                             |
|-----------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                  <strong>Zainstaluj program Endpoint Protection</strong>                                   | Ustawienie wartości <strong>Tak</strong> spowoduje zainstalowanie programu Endpoint Protection na zarządzanych komputerach. Jeśli podczas instalacji zostanie wykryta aplikacja ochrony punktu końcowego innej firmy, program Endpoint Protection nie zostanie zainstalowany, chyba że ustawienie <strong>Zainstaluj program Endpoint Protection, nawet jeśli jest zainstalowana inna aplikacja ochrony punktu końcowego</strong> ma wartość <strong>Tak</strong>. <strong>Uwaga</strong>: program Endpoint Protection usługi Intune jest domyślnie instalowany na zarządzanych komputerach. Jeśli nie chcesz instalować programu Endpoint Protection na zarządzanych komputerach, musisz jawnie ustawić te zasady na wartość <strong>Nie</strong>. Jeśli program Endpoint Protection został wcześniej zainstalowany i zasady zostaną zmienione na wartość <strong>Nie</strong>, klient programu Endpoint Protection zostanie odinstalowany.<br />Zalecana wartość: <strong>Tak</strong> |
| <strong>Zainstaluj program Endpoint Protection, nawet jeśli jest zainstalowana inna aplikacja ochrony punktu końcowego</strong> |                                                                                                                                                                                                                                                                                                                Ustaw wartość <strong>Tak</strong>, aby zainstalować program Endpoint Protection usługi Microsoft Intune nawet wtedy, gdy inna aplikacja ochrony punktu końcowego zostanie wykryta.<br /><br />Zalecana wartość: <strong>Tak</strong>                                                                                                                                                                                                                                                                                                                |
|                                   <strong>Włącz program Endpoint Protection</strong>                                   |                                                                                                                                                                                                            Ustaw wartość <strong>Tak</strong>, aby włączyć program Endpoint Protection usługi Microsoft Intune na komputerach, na których jest zainstalowany klient programu Endpoint Protection.<br /><br />Jeśli ustawisz wartość <strong>Nie</strong>, a program Endpoint Protection usługi Microsoft Intune jest zainstalowany, interfejs użytkownika klienta programu Endpoint Protection nie będzie widoczny dla użytkowników i wszystkie funkcje ochrony będą nieaktywne.<br /><br />Zalecana wartość: <strong>Tak</strong>                                                                                                                                                                                                             |
|                                       <strong>Wyłącz interfejs użytkownika klienta</strong>                                        |                                                                                                                                                                                                                                                                                                      Ustawienie wartości <strong>Tak</strong> spowoduje ukrycie interfejsu użytkownika klienta programu Endpoint Protection usługi Microsoft Intune (wprowadzenie zmian wymaga ponownego uruchomienia komputera klienta).<br /><br />Zalecana wartość: <strong>Nie</strong>                                                                                                                                                                                                                                                                                                       |
| <strong>Zainstaluj program Endpoint Protection, nawet jeśli jest zainstalowana inna aplikacja ochrony punktu końcowego</strong> |                                                                                                                                                                                                                                                                                                       Ustaw wartość <strong>Tak</strong>, aby wymusić instalację programu Endpoint Protection usługi Microsoft Intune nawet wtedy, gdy inna aplikacja ochrony punktu końcowego zostanie wykryta.<br /><br />Zalecana wartość: <strong>Nie</strong>                                                                                                                                                                                                                                                                                                       |
|                    <strong>Utwórz punkt przywracania systemu przed korygowaniem złośliwego oprogramowania</strong>                    |                                                                                                                                                                                                                                                                                                                                 Ustawienie wartości <strong>Tak</strong> spowoduje utworzenie punktu przywracania systemu Windows przed rozpoczęciem wszelkich działań naprawczych po wykryciu złośliwego oprogramowania<br /><br />Zalecana wartość: <strong>Tak</strong>                                                                                                                                                                                                                                                                                                                                  |
|                                 <strong>Śledź usunięte złośliwe oprogramowanie (dni)</strong>                                  |                                                                                                                                                                                                                                                                                      Umożliwia programowi Endpoint Protection śledzenie usuniętego złośliwego oprogramowania przez określony czas, co pozwala na ręczne sprawdzenie zainfekowanych wcześniej komputerów.<br /><br />Można określić wartość z zakresu od 0 do 30 dni.<br /><br />Zalecana wartość: <strong>7 dni</strong>                                                                                                                                                                                                                                                                                       |

Jeśli ustawiono zasady dla ustawień **Zainstaluj program Endpoint Protection** i **Włącz program Endpoint Protection** na wartość **Tak**, a zasady **Zainstaluj program Endpoint Protection, nawet jeśli jest zainstalowana inna aplikacja ochrony punktu końcowego** na wartość **Nie**, program Endpoint Protection usługi Microsoft Intune wykryje obecność aplikacji ochrony punktu końcowego innej firmy. To oznacza, że program Endpoint Protection nie zostanie zainstalowany lub zostanie odinstalowany, jeśli jest już obecny. Jednak program Endpoint Protection usługi Microsoft Intune umożliwia wyświetlenie raportu o kondycji aplikacji ochrony punktu końcowego innej firmy w usłudze Intune.

  Program Microsoft Security Essentials zapewnia ochronę w czasie rzeczywistym i powiadamia użytkownika, jeśli potencjalnie niebezpieczne programy, np. wirusy i programy szpiegujące, próbują zainstalować i uruchomić się na komputerze. Gdy tylko do tego dojdzie, użytkownik otrzyma komunikat w obszarze powiadomień z prawej strony paska zadań.

### <a name="specify-real-time-protection-settings"></a>Określanie ustawień ochrony w czasie rzeczywistym

|Ustawienie zasad|Szczegóły|
|------------------|--------------------|
|**Włącz ochronę w czasie rzeczywistym**|Umożliwia monitorowanie i skanowanie wszystkich używanych plików i aplikacji. Ponadto pozwala na blokowanie złośliwych plików i aplikacji, zanim zostaną one uruchomione na komputerach.<br /><br />Zalecana wartość: **Tak**|
|**Skanuj wszystkie pobrane pliki**|Umożliwia skanowanie wszystkich plików i załączników pobieranych z Internetu na komputery.<br /><br />Zalecana wartość: **Tak**|
|**Monitoruj działanie plików i programów na komputerach**|Umożliwia monitorowanie plików przychodzących i wychodzących oraz działania programów na komputerach. To ustawienie pozwala na monitorowanie przez program Endpoint Protection uruchamianych plików i programów oraz informowanie o ich działaniach lub działaniach wykonywanych na nich.<br /><br />Zalecana wartość: **Tak**|
|**Pliki monitorowane**|Umożliwia określenie, czy mają być monitorowane tylko pliki przychodzące, tylko pliki wychodzące, czy wszystkie pliki.<br /><br />Zalecana wartość: **Monitoruj wszystkie pliki**|
|**Włącz monitorowanie zachowania**|Umożliwia programowi Endpoint Protection usługi Microsoft Intune sprawdzanie określonych wzorców podejrzanej aktywności na komputerach klienckich.<br /><br />Zalecana wartość: **Tak**|
|**Włącz system inspekcji sieci**|Włącza system inspekcji sieci (NIS) na komputerach klienckich. System NIS korzysta z sygnatur znanych zagrożeń dostępnych w [Centrum firmy Microsoft ds. ochrony przed złośliwym oprogramowaniem](https://go.microsoft.com/fwlink/?LinkId=234249) , aby ułatwić wykrycie i zablokowanie ruchu sieciowego złośliwego oprogramowania.<br /><br />Zalecana wartość: **Tak**|

  ![Ustawienia ochrony w czasie rzeczywistym programu Endpoint Protection](./media/pol-sa-pc-policy-realtime.png)

### <a name="specify-scan-schedule-settings"></a>Określanie ustawień harmonogramu skanowania

|Ustawienie zasad|Więcej informacji|
|------------------|--------------------|
|**Zaplanuj codzienne szybkie skanowanie**|Umożliwia zaplanowanie codziennego szybkiego skanowania często używanych plików oraz ważnych plików systemowych na komputerach. Ten tryb skanowania ma minimalny wpływ na wydajność.<br /><br />Zalecana wartość: **Tak**|
|**Przeprowadzaj szybkie skanowanie, gdy pominięto dwa kolejne szybkie skanowania**|Umożliwia skonfigurowanie programu Endpoint Protection do automatycznego uruchamiania szybkiego skanowania na komputerach, jeśli pominięto dwa kolejne szybkie skanowania.<br /><br />Zalecana wartość: **Tak**|
|**Zaplanuj pełne skanowanie**|Umożliwia skonfigurowanie pełnego skanowania wszystkich plików i zasobów na dyskach twardych komputerów lokalnych. To skanowanie może zająć trochę czasu i może mieć wpływ na wydajność komputera (długość skanowania zależy od liczby skanowanych plików i zasobów).<br /><br />Zalecana wartość: **Nie**|
|**Przeprowadzaj pełne skanowanie, gdy pominięto dwa kolejne pełne skanowania**|Umożliwia skonfigurowanie programu Endpoint Protection do automatycznego uruchamiania pełnego skanowania na komputerach, jeśli pominięto dwa kolejne skanowania.<br /><br />Zalecana wartość: Nieskonfigurowane|

### <a name="specify-scan-options-settings"></a>Określanie ustawień opcji skanowania

|Ustawienie zasad|Szczegóły|
|------------------|--------------------|
|**Przeprowadź pełne skanowanie po instalacji programu Endpoint Protection**|Ustawienie wartości **Tak** umożliwia programowi Endpoint Protection automatyczne uruchamianie pełnego skanowania po zainstalowaniu go na komputerach. To skanowanie jest przeprowadzane, gdy komputery są w stanie bezczynności, aby zminimalizować wpływ na wydajność pracy użytkownika.<br /><br />Zalecana wartość: **Tak**|
|**Automatycznie przeprowadź pełne skanowanie, gdy jest wymagane monitowanie usunięcia złośliwego oprogramowania**|Ustawienie wartości **Tak** umożliwia programowi Endpoint Protection automatyczne uruchomienie pełnego skanowania komputerów po usunięciu złośliwego oprogramowania w celu uzyskania potwierdzenia, że inne pliki nie zostały zainfekowane.<br /><br />Zalecana wartość: **Tak**|
|**Uruchom zaplanowane skanowanie tylko wtedy, gdy komputer jest w stanie bezczynności**|Ustawienie wartości **Tak** uniemożliwia uruchomienie zaplanowanych skanowań, gdy komputery są używane, co pozwala zapobiec zmniejszeniu wydajności pracy użytkownika.<br /><br />Zalecana wartość: **Tak**|
|**Sprawdź przed rozpoczęciem skanowania, czy są dostępne najnowsze definicje złośliwego oprogramowania**|Ustawienie wartości **Tak** umożliwia programowi Endpoint Protection automatyczne sprawdzenie dostępności najnowszych definicji złośliwego oprogramowania przed rozpoczęciem skanowania komputerów.<br /><br />Zalecana wartość: **Tak**|
|**Skanuj pliki archiwum**|Ustawienie wartości **Tak** umożliwia skonfigurowanie programu Endpoint Protection w celu skanowania plików archiwów (takich jak pliki zip lub cab) na komputerach w poszukiwaniu złośliwego oprogramowania.<br /><br />Zalecana wartość: **Nie**|
|**Skanuj wiadomości e-mail**|Ustawienie wartości **Tak** umożliwia skonfigurowanie programu Endpoint Protection w celu skanowania przychodzących wiadomości e-mail.<br /><br />Zalecana wartość: **Tak**|
|**Skanuj pliki otwierane z udostępnionych folderów sieciowych**|Ustawienie wartości **Tak** umożliwia skonfigurowanie programu Endpoint Protection w celu skanowania plików otwieranych z udostępnionych folderów sieciowych. Zazwyczaj są to pliki otwierane przy użyciu ścieżki Universal Naming Convention (UNC). Włączenie tej funkcji może spowodować problemy w przypadku użytkowników, którym przyznano dostęp tylko do odczytu, ponieważ nie będą oni mogli usunąć złośliwego oprogramowania.<br /><br />Zalecana wartość: **Nie**|
|**Skanuj zamapowane dyski sieciowe**|Ustawienie wartości **Tak** umożliwia skonfigurowanie programu Endpoint Protection w celu skanowania plików znajdujących się na zamapowanych dyskach sieciowych. Włączenie tej funkcji może spowodować problemy w przypadku użytkowników, którym przyznano dostęp tylko do odczytu, ponieważ nie będą oni mogli usunąć złośliwego oprogramowania.<br /><br />Zalecana wartość: **Nie**|
|**Skanuj dyski wymienne**|Ustawienie wartości **Tak** umożliwia skonfigurowanie programu Endpoint Protection w celu skanowania zawartości dysków wymiennych, takich jak dyski flash USB, w poszukiwaniu złośliwego lub niechcianego oprogramowania po uruchomieniu pełnego skanowania na komputerach.<br /><br />Zalecana wartość: **Tak**|
|**Ogranicz użycie procesora CPU podczas skanowania**|Umożliwia ustawienie maksymalnej wartości procentowej użycia procesora CPU na komputerach podczas przeprowadzania zaplanowanych skanowań. Tę wartość można ustawić w zakresie od 1 do 100 procent.<br /><br />Zalecana wartość: **50%**|

### <a name="choose-default-actions-settings"></a>Wybieranie domyślnych ustawień akcji

Ustawienie **Wybierz sposób działania programu Endpoint Protection w przypadku złośliwego oprogramowania o następujących poziomach alertu** określa domyślną akcję, którą podejmie program Endpoint Protection, jeśli zostanie wykryte złośliwe oprogramowanie o różnych poziomach alertu. W ramach poszczególnych poziomów alertów można usunąć złośliwe oprogramowanie, poddać je kwarantannie lub wykonać działanie zalecane przez firmę Microsoft.

Zalecana wartość: **Zalecane działanie**, które umożliwia programowi Endpoint Protection zalecenie akcji.   

### <a name="decide-whether-to-choose-the-excluded-files-and-folders-settings"></a>Decyzja o wyborze ustawień wykluczonych plików i folderów

Ustawienie **Pliki i foldery do wykluczenia w trakcie skanowania lub używania ochrony w czasie rzeczywistym** wyklucza określone pliki lub foldery, jeśli na komputerach zostanie uruchomione skanowanie lub jeśli jest włączona funkcja ochrony w czasie rzeczywistym.

### <a name="decide-whether-to-choose-the-excluded-processes-settings"></a>Decyzja o wyborze ustawień wykluczonych procesów

Ustawienie **Procesy, które mają zostać wykluczone podczas przeprowadzania skanowania lub stosowania ochrony w czasie rzeczywistym** umożliwia wykluczenie określonych procesów, jeśli na komputerach zostanie uruchomione skanowanie lub jeśli jest włączona funkcja ochrony w czasie rzeczywistym. Można wykluczać tylko pliki z następującymi rozszerzeniami: **exe**, **com** i **scr**.

### <a name="decide-whether-to-choose-the-excluded-file-types-settings"></a>Decyzja o wyborze ustawień wykluczonych typów plików

Ustawienie **Rozszerzenia plików, które mają zostać wykluczone podczas przeprowadzania skanowania lub stosowania ochrony w czasie rzeczywistym** umożliwia wykluczenie konkretnych rozszerzeń nazw plików, jeśli na komputerach zostanie uruchomione skanowanie lub jeśli jest włączona funkcja ochrony w czasie rzeczywistym.

### <a name="specify-microsoft-active-protection-service-settings"></a>Określanie ustawień usługi Microsoft Active Protection
Usługa Microsoft Active Protection to społeczność online ułatwiająca odpowiadanie na potencjalne zagrożenia. Społeczność ta pomaga także w zatrzymywaniu rozpowszechniania nowych infekcji złośliwym oprogramowaniem. Możesz użyć opcji **Dołącz do społeczności Microsoft Active Protection Service**, wybierając pozycję **Tak**, a następnie podając swój **Poziom członkostwa**:
  - **Podstawowe** — do firmy Microsoft są wysyłane podstawowe informacje dotyczące wykrytego złośliwego oprogramowania. Zawierają one informacje o pochodzeniu oprogramowania, działaniach podjętych przez użytkownika lub automatycznie przez program Endpoint Protection, a także informacje o tym, czy działania były skuteczne.
  - **Zaawansowane** — do firmy Microsoft są wysyłane dodatkowe informacje dotyczące złośliwego i potencjalnie niechcianego oprogramowania oraz programów szpiegujących. Obejmują one informacje o lokalizacji oprogramowania, nazwach plików, sposobie działania oprogramowania oraz jego wpływie na komputer.

Możesz też **odbierać definicje dynamiczne utworzone na podstawie raportów społeczności Microsoft Active Protection Service**.

## <a name="choose-management-tasks-for-endpoint-protection"></a>Wybieranie zadań zarządzania dla programu Endpoint Protection
Poniższe zadania ułatwiają wykonywanie różnych czynności w zakresie zarządzania komputerami, na których działa program Endpoint Protection.
- Aktualizacja definicji złośliwego oprogramowania
  - Konsola usługi Intune — w obszarze roboczym **Grupy** wybierz komputery do zaktualizowania. Wybierz kolejno pozycje **Zadania zdalne** &gt; **Aktualizuj definicje złośliwego oprogramowania**.
  - Zarządzany komputer — uruchom oprogramowanie klienckie programu Endpoint Protection z poziomu obszaru powiadomień systemu Windows. Wybierz kartę **Aktualizacja**, a następnie kliknij pozycję **Aktualizuj**.
- Uruchom skanowanie w poszukiwaniu złośliwego oprogramowania:
  - Konsola usługi Intune — w obszarze roboczym **Grupy** wybierz komputery do przeskanowania. Wybierz pozycję **Uruchom pełne skanowanie w poszukiwaniu złośliwego oprogramowania** lub **Uruchom szybkie skanowanie w poszukiwaniu złośliwego oprogramowania**.
  - Zarządzany komputer — uruchom oprogramowanie klienckie programu Endpoint Protection z poziomu obszaru powiadomień systemu Windows. Wybierz pozycję **Szybkie**, **Pełne** lub **Niestandardowe**, a następnie wybierz pozycję **Skanuj teraz**.

Stan zadania zdalnego można wyświetlić, wybierając link **Zadania zdalne** w prawym dolnym rogu konsoli usługi Intune. W oknie dialogowym **Stan zadania zdalnego** są wyświetlane bieżące zadania zdalne, stan zadania, nazwa urządzenia i wszelkie zgłoszone błędy. Okno zawiera również link do informacji dotyczących rozwiązywania problemów, jeśli są one dostępne.

## <a name="monitor-endpoint-protection"></a>Monitorowanie programu Endpoint Protection
Do monitorowania stanu złośliwego oprogramowania na komputerach służy obszar roboczy **Ochrona** w [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/). Ten obszar roboczy zawiera dwie strony:
- **Omówienie ochrony** — ważne informacje są wyświetlane jako linki, które można wybrać, aby uzyskać więcej informacji. Te informacje dotyczą problemów w następujących obszarach:
  - **Wystąpienia złośliwego oprogramowania wymagające monitowania** — kliknięcie linku umożliwia wyświetlenie listy problemów dotyczących złośliwego oprogramowania wraz z akcjami, które należy podjąć w celu rozwiązania tych problemów. Możesz bliżej zapoznać się z tą listą, aby zobaczyć, których komputerów dotyczy problem.
  - **Komputery ze złośliwym oprogramowaniem, które wymagają monitowania** — kliknięcie linku umożliwia wyświetlenie listy komputerów z nierozwiązanymi problemami dotyczącymi złośliwego oprogramowania wraz z działaniami, które należy podjąć w celu rozwiązania tych problemów.
  - **Urządzenia, które nie są chronione** — kliknięcie linku umożliwia wyświetlenie listy komputerów, które nie są chronione przez oprogramowanie ochrony punktu końcowego, ponieważ nie jest ono zainstalowane lub wystąpił błąd. Po wybraniu komputera można zobaczyć więcej szczegółów.
  - **Urządzenia z uruchomioną inną aplikacją ochrony punktu końcowego** — kliknięcie linku umożliwia wyświetlenie komputerów, na których działa aplikacja ochrony punktu końcowego innej firmy.
- **Wszystkie złośliwe oprogramowania** — zawiera listę wszystkich aktywnych wystąpień złośliwego oprogramowania wykrytych na komputerach. Możesz zapoznać się z tą listą, aby zobaczyć, których komputerów dotyczy problem związany z określonym wystąpieniem złośliwego oprogramowania, lub wybrać jedno z następujących zadań:
  - **Wyświetl właściwości** — umożliwia otwarcie strony z dodatkowymi informacjami na temat wybranego złośliwego oprogramowania.
  - **Więcej informacji na temat tego złośliwego oprogramowania** — umożliwia przejście do Centrum firmy Microsoft ds. ochrony przed złośliwym oprogramowaniem i wyświetlenie tematu zawierającego więcej informacji.

> [!IMPORTANT]
> Obszar roboczy **Ochrona** zostanie wyświetlony w konsoli administracyjnej dopiero po zainstalowaniu klienta i rozpoczęciu zarządzania co najmniej jednym komputerem klienckim.

  ![Monitorowanie programu Endpoint Protection](./media/pol-sa-ep-monitor.png)

### <a name="how-to-view-recent-detection-paths-for-malware-on-computers"></a>Wyświetlanie ostatnich ścieżek wykrywania dla złośliwego oprogramowania na komputerach
Usługa Intune może wyświetlać ścieżki do maksymalnie 10 ostatnio wykrytych wystąpień złośliwego oprogramowania na urządzeniu. Widok **Ostatnie ścieżki wykrywania** jest domyślnie wyłączony. Aby włączyć ten widok:

1. W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/) wybierz kolejno pozycje **Grupy** > **Wszystkie urządzenia** > **Wszystkie komputery**.
2. Kliknij prawym przyciskiem myszy komputer, którego ostatnie ścieżki wykrywania chcesz zobaczyć, i wybierz polecenie **Właściwości**.
3. Z kart u góry wybierz pozycję **Złośliwe oprogramowanie**.

   ![Wybierz kartę Złośliwe oprogramowanie, a następnie kliknij pole wyboru Ostatnie ścieżki wykrywania.](../media/malware-path-column.png)
4. Kliknij prawym przyciskiem myszy nagłówek kolumny. Zostanie wyświetlona lista dostępnych kolumn. Zaznacz na liście pole wyboru **Ostatnie ścieżki wykrywania**. Pojawi się kolumna **Ostatnie ścieżki wykrywania**, w której jest wyświetlanych maksymalnie 10 ostatnio monitorowanych wystąpień złośliwego oprogramowania na urządzeniu.

## <a name="run-a-malware-scan-or-update-malware-definitions-on-a-computer"></a>Uruchamianie skanowania w poszukiwaniu złośliwego oprogramowania lub aktualizowanie definicji złośliwego oprogramowania na komputerze
Usługa Intune może uruchomić pełne albo szybkie skanowanie w poszukiwaniu złośliwego oprogramowania za pomocą programu Endpoint Protection lub Windows Defender na zdalnie zarządzanym komputerze z zainstalowanym klientem usługi Intune.

1. W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/) wybierz pozycję **Grupy** > **Przegląd** > **Wszystkie urządzenia** > **Wszystkie komputery** i wybierz komputer docelowy.

2. Wybierz listę rozwijaną **Zadania zdalne**, a następnie wybierz zadanie, które ma zostać uruchomione na komputerze zdalnym.

## <a name="need-more-help"></a>Potrzebujesz dodatkowej pomocy?
Aby uzyskać dalszą pomoc i wsparcie techniczne, zobacz [Rozwiązywanie problemów z programem Endpoint Protection w usłudze Microsoft Intune](/intune-classic/troubleshoot/troubleshoot-endpoint-protection-in-microsoft-intune).

### <a name="see-also"></a>Zobacz też
[Zasady ochrony komputerów z systemem Windows](policies-to-protect-windows-pcs-in-microsoft-intune.md)
