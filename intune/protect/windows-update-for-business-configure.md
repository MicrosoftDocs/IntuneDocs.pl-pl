---
title: Konfigurowanie ustawień usługi Windows Update dla firm w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zarządzanie aktualizacjami oprogramowania systemu Windows 10 przy użyciu pierścieni aktualizacji i zasad aktualizacji funkcji. Możesz przejrzeć informacje o zgodności i wstrzymać instalację aktualizacji przy użyciu ustawień witryny Windows Update dla firm w usłudze Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/29/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: c9245ca028bdb5589df8c76b10560d9130a1108c
ms.sourcegitcommit: 9ee2401a2f01373a962749b0728c22385dbcba6d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/29/2020
ms.locfileid: "78181725"
---
# <a name="manage-windows-10-software-updates-in-intune"></a>Zarządzanie aktualizacjami oprogramowania systemu Windows 10 w usłudze Intune

Usługa Intune umożliwia zarządzanie instalowaniem aktualizacji oprogramowania systemu Windows 10 z witryny Windows Update dla firm.

Używając usługi Windows Update dla firm, można uprościć środowisko zarządzania aktualizacjami. Nie musisz zatwierdzać poszczególnych aktualizacji dla grup urządzeń. Możesz zarządzać ryzykiem w środowiskach, konfigurując strategię wdrażania aktualizacji. Usługa Intune zapewnia możliwość [konfigurowania ustawień aktualizacji](windows-update-settings.md) na urządzeniach oraz odraczania instalacji aktualizacji. Można również uniemożliwić urządzeniom instalowanie funkcji z nowych wersji systemu Windows, aby zapewnić ich stabilność, jednocześnie pozwalając tym urządzeniom na kontynuowanie instalowania aktualizacji w celu zachowania jakości i bezpieczeństwa.

Usługa Intune przechowuje tylko przypisania zasad aktualizacji, a nie same aktualizacje. W celu pobrania aktualizacji urządzenia uzyskują dostęp bezpośrednio do usługi Windows Update.

Usługa Intune udostępnia następujące typy zasad do zarządzania aktualizacjami:

- **Pierścień aktualizacji systemu Windows 10**: te zasady to kolekcja ustawień określająca, kiedy mają być instalowane aktualizacje systemu Windows 10.

- **Aktualizacje funkcji systemu Windows 10 (publiczna wersja zapoznawcza)** : te zasady gwarantują użycie na urządzeniach określonej przez Ciebie wersji systemu Windows i blokują funkcję ustawioną na tych urządzeniach, dopóki nie zostaną one zaktualizowane do nowszej wersji systemu Windows.  Mimo że wersja funkcji pozostaje statyczna, urządzenia mogą nadal instalować aktualizacje dotyczące jakości i zabezpieczeń, które są dostępne dla ich wersji funkcji.

Do grup urządzeń można przypisywać zasady dotyczące pierścieni aktualizacji systemu Windows 10 i aktualizacji funkcji systemu Windows 10. Możesz użyć obu typów zasad w tym samym środowisku usługi Intune do zarządzania aktualizacjami oprogramowania dla urządzeń z systemem Windows 10 i tworzenia strategii aktualizacji, która odzwierciedli Twoje potrzeby biznesowe.

Aby uzyskać więcej informacji, zobacz artykuł [Zarządzanie aktualizacjami za pomocą usługi Windows Update dla firm](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb).

## <a name="prerequisites"></a>Wymagania wstępne

Aby korzystać z aktualizacji systemu Windows dla urządzeń z systemem Windows 10 w usłudze Intune, należy spełnić poniższe wymagania wstępne.

- Na komputerach z systemem Windows 10 muszą zostać uruchomione następujące wersje systemu Windows 10:
  - **Pierścienie aktualizacji systemu Windows 10**: wersja 1607 lub nowsza
  - **Aktualizacje funkcji systemu Windows 10**: wersja 1703 lub nowsza

- Usługa Windows Update obsługuje następujące wersje systemu Windows 10:
  - Windows 10
  - Windows 10 Team — dla urządzeń Surface Hub (nie obsługuje *aktualizacji funkcji systemu Windows 10*)
  - Windows Holographic for Business

    System Windows Holographic for Business obsługuje podzestaw ustawień aktualizacji systemu Windows, w tym:
    - **Zachowanie automatycznych aktualizacji**
    - **Aktualizacje produktów firmy Microsoft**
    - **Kanał obsługi**: Obsługiwane są opcje **Półroczny kanał** i **Półroczny kanał (kierowany)** . Aby uzyskać więcej informacji, zobacz [Zarządzanie platformą Windows Holographic](../fundamentals/windows-holographic-for-business.md).

  > [!NOTE]
  > **Nieobsługiwane wersje i wydania**:
  > - Windows 10 Mobile  
  > - Windows 10 Enterprise LTSC. Usługa Windows Update for Business (WufB) obecnie nie obsługuje wersji *Długoterminowy kanał obsługi*. Zaplanuj użycie alternatywnych metod dodawania poprawek, np. WSUS czy Configuration Manager.

- Na urządzeniach z systemem Windows opcja **Opinia i diagnostyka** > **Dane diagnostyczne i dane użycia** musi mieć wartość **Podstawowa**, **Rozszerzona** lub **Pełna**.

  W przypadku urządzeń z systemem Windows 10 możesz ręcznie skonfigurować ustawienie *Dane diagnostyczne i dane użycia* lub użyć profilu ograniczeń dotyczących urządzenia w usłudze Intune w systemie Windows 10 lub nowszym. Korzystając z profilu ograniczeń dotyczących urządzenia, w [ustawieniu ograniczeń dotyczących urządzeń](../configuration/device-restrictions-windows-10.md#reporting-and-telemetry)**Udostępnij dane użycia** wybierz co najmniej opcję **Basic**. To ustawienie jest dostępne w kategorii **Raportowanie i telemetria** podczas konfigurowania zasad ograniczeń dotyczących urządzenia w systemie Windows 10 lub nowszym.

  Aby uzyskać więcej informacji o profilach urządzenia, zobacz artykuł [Konfigurowanie ustawień ograniczeń dotyczących urządzeń](../configuration/device-restrictions-configure.md).

## <a name="windows-10-update-rings"></a>Pierścienie aktualizacji systemu Windows 10

Utwórz pierścienie aktualizacji, które określają, jak i kiedy system Windows jako usługa aktualizuje urządzenia z systemem Windows 10 za pomocą aktualizacji dotyczących funkcji i jakości. W systemie Windows 10 nowe aktualizacje funkcji oraz aktualizacje dotyczące jakości obejmują zawartość wszystkich poprzednich aktualizacji. Po zainstalowaniu najnowszej aktualizacji masz pewność, że urządzenia z systemem Windows 10 są aktualne. W odróżnieniu od wcześniejszych wersji systemu Windows teraz musisz zainstalować całą aktualizację, a nie tylko jej część.

Pierścienie aktualizacji systemu Windows 10 obsługują [tagi zakresu](../fundamentals/scope-tags.md). Tagów zakresu można używać wraz z pierścieniami aktualizacji, aby ułatwić Ci filtrowanie używanych zestawów konfiguracji i zarządzanie nimi.

### <a name="create-and-assign-update-rings"></a>Tworzenie i przypisywanie pierścieni aktualizacji

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Wybierz pozycję **Urządzenia** > **Windows** > **Pierścienie aktualizacji systemu Windows 10** > **Utwórz**.

3. W obszarze *Podstawowe* podaj nazwę i opis (opcjonalnie), a następnie wybierz przycisk **Dalej**.
  ![Tworzenie pierścienia aktualizacji](./media/windows-update-for-business-configure/basics-tab.png)

4. W obszarze **Aktualizuj ustawienia pierścienia** skonfiguruj ustawienia na potrzeby Twojej firmy. Aby uzyskać informacje na temat dostępnych ustawień, zobacz artykuł [Ustawienia aktualizacji systemu Windows](../protect/windows-update-settings.md). Po skonfigurowaniu ustawień *Aktualizacja i Środowisko użytkownika* wybierz przycisk **Dalej**.

5. Jeśli chcesz zastosować tagi do pierścienia aktualizacji, w obszarze **Tagi zakresu** wybierz pozycję **+ Wybierz zakres tagów**, aby otworzyć okienko *Wybierz tagi*. Wybierz co najmniej jeden tag, a następnie kliknij pozycję **Wybierz**, aby dodać je do pierścienia aktualizacji i wrócić na stronę *Tagi zakresu*.

   Gdy wszystko będzie gotowe, wybierz przycisk **Dalej**, aby przejść do karty *Przypisania*.

6. W obszarze **Przypisania** wybierz pozycję **+ Wybierz grupy do uwzględnienia**, a następnie przypisz pierścień aktualizacji do co najmniej jednej grupy. Użyj opcji **+ Wybierz grupy do wykluczenia**, aby dopracować przypisanie. Wybierz przycisk **Dalej**, aby kontynuować.

7. W obszarze **Przeglądanie + tworzenie** przejrzyj ustawienia i wybierz pozycję **Utwórz**, gdy wszystko będzie gotowe do zapisania pierścienia aktualizacji systemu Windows 10. Nowy pierścień aktualizacji zostanie wyświetlony na liście pierścieni aktualizacji.

### <a name="manage-your-windows-10-update-rings"></a>Zarządzanie pierścieniami aktualizacji systemu Windows 10

W portalu przejdź do pozycji **Urządzenia** > **Windows** > **Pierścienie aktualizacji systemu Windows 10** i wybierz zasady, którymi chcesz zarządzać.  Zasady zostaną otwarte na stronie **omówienia**.

Na tej stronie można wyświetlić stan przypisania pierścieni i wybrać następujące akcje w górnej części okienka omówienia, aby zarządzać pierścieniem aktualizacji:

- [Usuwanie](#delete)
- [Wstrzymanie](#pause)
- [Wznawianie](#resume)
- [Rozwijanie](#extend)
- [Odinstalowywanie](#uninstall)

![Dostępne akcje](./media/windows-update-for-business-configure/overview-actions.png)

#### <a name="delete"></a>Usuwanie

Wybierz pozycję **Usuń**, aby zatrzymać wymuszanie ustawień wybranego pierścienia aktualizacji systemu Windows 10. Usunięcie pierścienia powoduje usunięcie jego konfiguracji z usługi Intune, a usługa Intune nie stosuje ani nie wymusza już tych ustawień.

Usunięcie pierścienia z usługi Intune nie modyfikuje ustawień na urządzeniach, do których przypisano pierścień aktualizacji.  Na urządzeniu zachowywane są bieżące ustawienia. Urządzenia nie przechowują historycznego rekordu ustawień, które były wcześniej przechowywane. Urządzenia mogą również odbierać ustawienia z dodatkowych pierścieni aktualizacji, które pozostaną aktywne.

##### <a name="to-delete-a-ring"></a>Aby usunąć pierścień

1. Na wyświetlonej stronie omówienia pierścienia aktualizacji wybierz pozycję **Usuń**.
2. Wybierz przycisk **OK**.

#### <a name="pause"></a>Wstrzymanie

Wybierz pozycję **Wstrzymaj**, aby uniemożliwić otrzymywanie przez przypisane urządzenia aktualizacji dotyczących funkcji lub jakości przez okres do 35 dni od chwili wstrzymania pierścienia. Po upływie maksymalnej liczby dni automatycznie wygasa działanie funkcji wstrzymania i urządzenie rozpoczyna skanowanie usługi Windows Update w poszukiwaniu odpowiednich aktualizacji. Po tym skanowaniu można ponownie wstrzymać aktualizacje.
Jeśli wznowisz wstrzymany pierścień aktualizacji, a następnie ponownie wstrzymasz ten pierścień, okres wstrzymania zostanie zresetowany do 35 dni.

##### <a name="to-pause-a-ring"></a>Aby wstrzymać pierścień

1. Na wyświetlonej stronie omówienia pierścienia aktualizacji wybierz pozycję **Wstrzymaj**.
2. Wybierz pozycję **Funkcja** lub **Jakość**, aby wstrzymać dany typ aktualizacji, a następnie wybierz przycisk **OK**.
3. Po wstrzymaniu jednego typu aktualizacji możesz ponownie wybrać pozycję Wstrzymaj, aby wstrzymać drugi typ aktualizacji.

Jeśli typ aktualizacji został wstrzymany, okienko omówienia tego pierścienia zawiera liczbę dni pozostałych do wznowienia typu aktualizacji.

> [!IMPORTANT]
> Gdy wydasz polecenie wstrzymania, urządzenia otrzymają je przy następnym zarejestrowaniu się w usłudze. Istnieje możliwość, że urządzenia mogą zainstalować zaplanowaną aktualizację przed zarejestrowaniem. Ponadto jeśli urządzenie docelowe jest wyłączone w momencie wydania polecenia wstrzymania, może ono po włączeniu pobrać i zainstalować zaplanowane aktualizacje przed zarejestrowaniem się w usłudze Intune.

#### <a name="resume"></a>Wznawianie

Jeśli pierścień aktualizacji został wstrzymany, możesz wybrać pozycję **Wznów**, aby przywrócić aktywne działanie aktualizacji dotyczących funkcji i jakości. Po wznowieniu pierścienia aktualizacji możesz ponownie wstrzymać ten pierścień.

##### <a name="to-resume-a-ring"></a>Aby wznowić pierścień

1. Na wyświetlonej stronie omówienia wstrzymanego pierścienia aktualizacji wybierz pozycję **Wznów**.
2. Z listy dostępnych opcji wybierz odpowiednią pozycję, aby wznowić aktualizacje dotyczące **funkcji** lub **jakości**, a następnie wybierz przycisk **OK**.
3. Po wznowieniu jednego typu aktualizacji możesz ponownie wybrać pozycję Wznów, aby wznowić drugi typ aktualizacji.

#### <a name="extend"></a>Rozwijanie  

Jeśli pierścień aktualizacji został wstrzymany, możesz wybrać pozycję **Rozszerz**, aby zresetować okres wstrzymania aktualizacji dotyczących funkcji i jakości tego pierścienia aktualizacji do 35 dni.

##### <a name="to-extend-the-pause-period-for-a-ring"></a>Aby rozszerzyć okres wstrzymania pierścienia

1. Na wyświetlonej stronie omówienia wstrzymanego pierścienia aktualizacji wybierz pozycję **Rozszerz**.
2. Z listy dostępnych opcji wybierz odpowiednią pozycję, aby wznowić aktualizacje dotyczące **funkcji** lub **jakości**, a następnie wybierz przycisk **OK**.
3. Po rozszerzeniu wstrzymania dla jednego typu aktualizacji możesz ponownie wybrać pozycję Rozszerz, aby rozszerzyć drugi typ aktualizacji.

#### <a name="uninstall"></a>Odinstalowanie  

Administrator usługi Intune może użyć pozycji **Odinstaluj** w celu odinstalowania (wycofania) najnowszej aktualizacji dotyczącej *funkcji* lub najnowszej aktualizacji dotyczącej *jakości* dla aktywnego lub wstrzymanego pierścienia aktualizacji. Po odinstalowaniu jednego typu możesz odinstalować drugi typ. Usługa Intune nie obsługuje możliwości odinstalowywania aktualizacji przez użytkowników ani nie zarządza nią.  

> [!IMPORTANT]
> W przypadku korzystania z opcji *Odinstaluj* usługa Intune natychmiast przekaże żądanie odinstalowania do urządzeń.
>
> - Urządzenia z systemem Windows rozpoczynają usuwanie aktualizacji zaraz po odebraniu zmiany zasad usługi Intune. Usuwanie aktualizacji nie jest ograniczone do harmonogramów konserwacji nawet wtedy, gdy zostały one skonfigurowane jako część pierścienia aktualizacji.
> - Jeśli usuwanie aktualizacji wymaga ponownego uruchomienia urządzenia, urządzenie zostanie ponownie uruchomione, nie oferując użytkownikom urządzenia opcji opóźnienia.

Aby odinstalowywanie zakończyło się powodzeniem:

- Na urządzeniu musi działać aktualizacja systemu Windows 10 z kwietnia 2018 (wersja 1803) lub nowsza.

Urządzenie musi mieć zainstalowaną najnowszą aktualizację. Ponieważ aktualizacje są zbiorcze, urządzenia z zainstalowaną najnowszą aktualizacją będą mieć najnowszą aktualizację dotyczącą funkcji i jakości. Przykładem zastosowania tej opcji może być wycofanie ostatniej aktualizacji po wykryciu problemu powodującego niezgodności na maszynach z systemem Windows 10.

Podczas korzystania z odinstalowywania uwzględnij następujące kwestie:

- Odinstalowywanie aktualizacji funkcji lub jakości jest dostępne tylko dla kanału obsługi dostępnego na urządzeniu.

- Użycie odinstalowywania aktualizacji funkcji lub jakości wyzwala zasady w celu przywrócenia poprzedniej aktualizacji na maszynach z systemem Windows 10.

- Po pomyślnym wycofaniu aktualizacji dotyczącej jakości na urządzeniu z systemem Windows 10 użytkownicy urządzenia nadal będą widzieć tę aktualizację wymienioną w obszarze **Ustawienia systemu Windows** > **Aktualizacje** > **Historia aktualizacji**.

- Szczególnie w przypadku aktualizacji funkcji czas, w ciągu którego można odinstalować aktualizację, jest ograniczony od 2 do 60 dni. Ten okres jest konfigurowany przy użyciu ustawienia aktualizacji pierścieni aktualizacji **Ustaw okres deinstalacji aktualizacji funkcji (od 2 do 60 dni)** . Nie można wycofać aktualizacji funkcji, która została zainstalowana na urządzeniu, jeśli aktualizacja była zainstalowana dłużej niż skonfigurowany okres odinstalowywania.

  Na przykład rozważ użycie pierścienia aktualizacji z okresem odinstalowywania aktualizacji funkcji o długości 20 dni. Po 25 dniach decydujesz się na wycofanie najnowszej aktualizacji funkcji i użycie opcji Odinstaluj.  Urządzenia, na których aktualizacja funkcji została zainstalowana ponad 20 dni temu, nie mogą jej odinstalować, ponieważ niezbędne elementy zostały usunięte w ramach konserwacji urządzenia. Natomiast urządzenia, na których aktualizacja funkcji została zainstalowana maksymalnie 19 dni temu, mogą odinstalować aktualizację, jeśli zostaną pomyślnie zaewidencjonowane w celu odebrania polecenia odinstalowania przed przekroczeniem 20-dniowego okresu odinstalowywania.

Aby uzyskać więcej informacji na temat zasad usługi Windows Update, zobacz artykuł [Dostawca konfiguracji usługi aktualizacji](https://docs.microsoft.com/windows/client-management/mdm/update-csp) w dokumentacji dotyczącej zarządzania klientem systemu Windows.

##### <a name="to-uninstall-the-latest-windows-10-update"></a>Aby odinstalować najnowszą aktualizację systemu Windows 10

1. Na wyświetlonej stronie omówienia wstrzymanego pierścienia aktualizacji wybierz pozycję **Odinstaluj**.
2. Z listy dostępnych opcji wybierz odpowiednią pozycję, aby odinstalować aktualizacje dotyczące **funkcji** lub **jakości**, a następnie wybierz przycisk **OK**.
3. Po wyzwoleniu odinstalowywania jednego typu aktualizacji możesz ponownie wybrać pozycję Odinstaluj, aby odinstalować pozostały typ aktualizacji.

## <a name="windows-10-feature-updates"></a>Aktualizacje funkcji systemu Windows 10

*Ta funkcja jest dostępna w publicznej wersji zapoznawczej.*

W przypadku *aktualizacji funkcji systemu Windows 10* wybierz wersję funkcji systemu Windows, która ma pozostać na urządzeniach, na przykład Windows 10 w wersji 1803 lub 1809. Poziom funkcji można ustawić na wersję 1803 lub nowszą.

Gdy urządzenie otrzyma zasady aktualizacji funkcji systemu Windows 10:

- Urządzenie zostanie zaktualizowane do wersji systemu Windows określonej w zasadzie. Urządzenie, na którym uruchomiono już nowszą wersję systemu Windows, pozostanie w bieżącej wersji. Po zablokowaniu wersji zestaw funkcji urządzenia pozostaje stabilny na czas obowiązywania zasad.

- Mimo że zainstalowana wersja systemu Windows pozostanie ustawiona, urządzenia mogą nadal otrzymywać i instalować aktualizacje jakości i zabezpieczeń dla swojej wersji systemu Windows przez czas świadczenia pomocy technicznej dla tej wersji, co pomaga zapewnić aktualność i bezpieczeństwo urządzeń.

- W przeciwieństwie do użycia w stosunku do pierścienia aktualizacji akcji *Wstrzymaj*, która wygaśnie po 35 dniach, zasady aktualizacji funkcji systemu Windows 10 nadal obowiązują. Urządzenia nie będą instalować nowej wersji systemu Windows, dopóki zasady aktualizacji funkcji systemu Windows 10 nie zostaną zmodyfikowane lub usunięte. Jeśli edytujesz zasady w celu określenia nowszej wersji, urządzenia będą mogły zainstalować funkcje z tej wersji systemu Windows.

### <a name="prerequisites-for-windows-10-feature-updates"></a>Warunki wstępne dotyczące aktualizacji funkcji systemu Windows 10

Aby korzystać z aktualizacji funkcji systemu Windows 10 w usłudze Intune, należy spełnić poniższe wymagania wstępne.

- Urządzenia muszą zostać zarejestrowane w oprogramowania do zarządzania urządzeniami mobilnymi usługi Intune i dołączone do usługi Azure AD lub zarejestrowane w usłudze Azure AD.
- Aby można było używać zasad aktualizacji funkcji w usłudze Intune, na urządzeniach należy włączyć funkcję telemetrii z minimalnym ustawieniem [*Podstawowa*](../configuration/device-restrictions-windows-10.md#reporting-and-telemetry). Telemetria jest konfigurowana w obszarze *Raportowanie i telemetria* w ramach [zasad ograniczeń urządzeń](../configuration/device-restrictions-configure.md).
  
  Urządzenia, które otrzymują zasady aktualizacji funkcji i które mają telemetrię ustawioną na *Nie skonfigurowano* (wyłączoną), mogą mieć zainstalować nowszą wersję systemu Windows niż zdefiniowana w zasadach aktualizacji funkcji. Wymaganie wstępne, które wskazuje, że telemetria ma być wymagana, jest obecnie analizowane, ponieważ ta funkcja zmierza w kierunku ogólnej dostępności.

### <a name="limitations-for-windows-10-feature-updates"></a>Ograniczenia dotyczące aktualizacji funkcji systemu Windows 10

- Po wdrożeniu zasad *aktualizacji funkcji systemu Windows 10* na urządzeniu, które otrzymuje również *pierścień aktualizacji systemu Windows 10*, przejrzyj pierścień aktualizacji pod kątem następujących konfiguracji:
  - Opcja **Okres odroczenia aktualizacji funkcji (dni)** musi być ustawiona na **0**.
  - Aktualizacje funkcji dla pierścienia aktualizacji muszą być *uruchomione*. Nie mogą być wstrzymane.

- Zasady aktualizacji funkcji systemu Windows 10 nie mogą być stosowane w trybie OOBE (out-of-box experience) rozwiązania Autopilot. Zostaną one zastosowane tylko podczas pierwszego skanowania funkcji Windows Update po ukończeniu aprowizacji urządzenia (zazwyczaj trwa to jeden dzień).

### <a name="create-and-assign-windows-10-feature-updates"></a>Tworzenie i przypisywanie aktualizacji funkcji systemu Windows 10

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Wybierz pozycję **Urządzenia** > **Windows** > **Aktualizacje funkcji systemu Windows 10** > **Utwórz**.

3. W obszarze **Podstawowe** określ nazwę i opis (opcjonalnie), a w polu **Aktualizacja funkcji do wdrożenia** wybierz wersję systemu Windows z żądanym zestawem funkcji i wybierz pozycję **Dalej**.

4. W obszarze **Przypisania** wybierz pozycję **+ Wybierz grupy do uwzględnienia**, a następnie przypisz wdrożenie aktualizacji funkcji do co najmniej jednej grupy. Wybierz przycisk **Dalej**, aby kontynuować.

5. W obszarze **Przeglądanie + tworzenie** przejrzyj ustawienia i wybierz pozycję **Utwórz**, gdy wszystko będzie gotowe do zapisania zasad aktualizacji funkcji systemu Windows 10.  

### <a name="manage-windows-10-feature-updates"></a>Zarządzanie aktualizacjami funkcji systemu Windows 10

W centrum administracyjnym przejdź do pozycji **Urządzenia** > **Windows** > **Aktualizacje funkcji systemu Windows 10** i wybierz zasady, którymi chcesz zarządzać. Zasady zostaną otwarte w okienku **omówienia**.

W tym okienku można:

- Wybrać pozycję **Usuń**, aby usunąć zasady z usługi Intune oraz z urządzeń.
- Wybrać pozycję **Właściwości**, aby zmodyfikować wdrożenie.  W okienku *Właściwości* wybierz pozycję **Edytuj**, aby otworzyć obszar *ustawień wdrożenia lub przydziałów*, w którym można następnie zmodyfikować wdrożenie.
- Wybrać pozycję **Stan aktualizacji użytkownika końcowego**, aby wyświetlić informacje dotyczące zasad.

## <a name="validation-and-reporting-for-windows-10-updates"></a>Walidacja i raportowanie na potrzeby aktualizacji systemu Windows 10

W przypadku pierścieni aktualizacji systemu Windows 10 i aktualizacji funkcji systemu Windows 10 użyj [raportów zgodności usługi Intune na potrzeby aktualizacji](../windows-update-compliance-reports.md) do monitorowania stanu aktualizacji urządzeń. To rozwiązanie używa funkcji [Update Compliance](https://docs.microsoft.com/windows/deployment/update/update-compliance-monitor) z subskrypcją platformy Azure.

## <a name="next-steps"></a>Następne kroki

[Ustawienia aktualizacji systemu Windows obsługiwane przez usługę Intune](../windows-update-settings.md)

[Rozwiązywanie problemów z pierścieniami aktualizacji systemu Windows 10](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Troubleshooting-Windows-10-Update-Ring-Policies/ba-p/714046)
