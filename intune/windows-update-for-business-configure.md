---
title: Konfigurowanie ustawień usługi Windows Update dla firm w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zaktualizuj ustawienia aktualizacji oprogramowania w profilu, aby tworzyć pierścień aktualizacji, sprawdzać zgodność i wstrzymywać aktualizacje w ustawieniach usługi Windows Update dla firm za pomocą usługi Microsoft Intune na urządzeniach z systemem Windows 10.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/12/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: coryfe
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 05fd362ff6f068669b85b9b78cb1dfd7d3c8011f
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57397276"
---
# <a name="manage-software-updates-in-intune"></a>Zarządzanie aktualizacjami oprogramowania w usłudze Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Użyj usługi Intune w celu zdefiniowania pierścieni aktualizacji, które określają, jak i kiedy system Windows jako usługa aktualizuje urządzenia z systemem Windows 10. Pierścienie aktualizacji to zasady, które można przypisać do grup urządzeń. Za pomocą pierścieni aktualizacji można utworzyć strategię aktualizacji, która uwzględnia potrzeby biznesowe. Aby uzyskać więcej informacji, zobacz artykuł [Manage updates using Windows Update for Business](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb) (Zarządzanie aktualizacjami za pomocą usługi Windows Update dla firm).

W systemie Windows 10 nowe aktualizacje funkcji oraz aktualizacje dotyczące jakości obejmują zawartość wszystkich poprzednich aktualizacji. Po zainstalowaniu najnowszej aktualizacji masz pewność, że urządzenia z systemem Windows 10 są aktualne. W odróżnieniu od wcześniejszych wersji systemu Windows teraz musisz zainstalować całą aktualizację, a nie tylko jej część.


Używając usługi Windows Update dla firm, można uprościć środowisko zarządzania aktualizacjami. Nie musisz zatwierdzać poszczególnych aktualizacji dla grup urządzeń. Możesz zarządzać ryzykiem w środowiskach, konfigurując strategię wdrażania aktualizacji. Usługa Intune zapewnia możliwość [konfigurowania ustawień aktualizacji](windows-update-settings.md) na urządzeniach oraz odraczania instalacji aktualizacji. Usługa Intune nie przechowuje aktualizacji, a jedynie przypisanie zasad aktualizacji. W celu pobrania aktualizacji urządzenia uzyskują dostęp bezpośrednio do usługi Windows Update. Ta kolekcja ustawień — określająca, kiedy mają być instalowane aktualizacje systemu Windows 10 — jest nazywana *pierścieniem aktualizacji systemu Windows 10*.

Pierścienie aktualizacji systemu Windows 10 obsługują [tagi zakresu](scope-tags.md). Tagów zakresu można używać wraz z pierścieniami aktualizacji, aby ułatwić Ci filtrowanie używanych zestawów konfiguracji i zarządzanie nimi.

## <a name="prerequisites"></a>Wymagania wstępne  

Aby korzystać z aktualizacji systemu Windows dla urządzeń z systemem Windows 10 w usłudze Intune, należy spełnić poniższe wymagania wstępne.  

- Na komputerach z systemem Windows 10 musi być uruchomiony co najmniej system Windows 10 Pro z Rocznicową aktualizacją systemu Windows (wersja 1607 lub nowszy).
- Usługa Windows Update obsługuje następujące wersje systemu Windows 10:
  - Windows 10
  - Windows 10 Team (dla urządzeń Surface Hub)
  - Windows Holographic for Business  

    System Windows Holographic for Business obsługuje podzestaw ustawień aktualizacji systemu Windows, w tym:
    - **Zachowanie automatycznych aktualizacji**
    - **Aktualizacje produktów firmy Microsoft**
    - **Kanał obsługi**: Obsługiwane są opcje **Półroczny kanał** i **Półroczny kanał (kierowany)**  

    Aby uzyskać więcej informacji, zobacz [Zarządzanie platformą Windows Holographic](windows-holographic-for-business.md).  
  
  Urządzenia z systemem Windows 10 Mobile nie są obsługiwane.

- Na urządzeniach z systemem Windows opcja **Opinia i diagnostyka** > **Dane diagnostyczne i dane użycia** musi mieć wartość **Podstawowa**, **Rozszerzona** lub **Pełna**.  

  To ustawienie można skonfigurować ręcznie lub użyć profilu ograniczeń urządzenia usługi Intune dla systemu Windows 10 i nowszych. Aby używać profilu ograniczeń urządzenia, należy skonfigurować ustawienie **Ogólne** > **Przesłanie danych diagnostycznych** na wartość co najmniej **Podstawowe**. Aby uzyskać więcej informacji o profilach urządzenia, zobacz artykuł [Konfigurowanie ustawień ograniczeń dotyczących urządzeń](device-restrictions-configure.md).  

- Jeśli używasz klasycznej witryny Azure Portal, [przeprowadź migrację ustawień do witryny Azure Portal](#migrate-update-settings-to-the-azure-portal).  

## <a name="create-and-assign-update-rings"></a>Tworzenie i przypisywanie pierścieni aktualizacji

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz pozycję **Aktualizacje oprogramowania** > **Pierścienie aktualizacji systemu Windows 10** > **Utwórz**.
4. Wprowadź nazwę i opis (opcjonalnie), a następnie wybierz pozycję **Konfiguruj**.
5. W obszarze **Ustawienia** skonfiguruj ustawienia zgodnie z potrzebami biznesowymi. Aby uzyskać informacje na temat dostępnych ustawień, zobacz artykuł [Ustawienia aktualizacji systemu Windows](windows-update-settings.md).  
6. Po zakończeniu wybierz przycisk **OK**. W obszarze **Tworzenie pierścienia aktualizacji**, wybierz pozycję **Utwórz**. Nowy pierścień aktualizacji jest wyświetlany na liście pierścieni aktualizacji.
7. Aby przypisać pierścień, wybierz go na liście, a następnie na karcie \<nazwa pierścienia> wybierz pozycję **Przypisania**.
8. Użyj kart **Dołączanie** i **Wykluczanie**, aby określić, do których grup przypisano ten pierścień, a następnie wybierz pozycję **Zapisz**, aby ukończyć przypisanie.

## <a name="manage-your-windows-10-update-rings"></a>Zarządzanie pierścieniami aktualizacji systemu Windows 10
W portalu możesz wybrać pierścień aktualizacji systemu Windows 10, aby otworzyć odpowiednie okienko **Omówienie**. Z poziomu tego okienka możesz wyświetlić stan przypisania pierścieni i wykonać dodatkowe akcje zarządzania pierścieniem. 
### <a name="to-view-an-updates-rings-overview-pane"></a>Aby wyświetlić okienko omówienia pierścieni aktualizacji: 
1. Zaloguj się do witryny Azure Portal.
2. Przejdź do pozycji **Intune** > **Aktualizacje oprogramowania** > **Pierścienie aktualizacji systemu Windows 10**.
3. Wybierz pierścień aktualizacji do wyświetlenia lub zarządzania.  

Oprócz wyświetlania stanu przypisania można wybrać następujące akcje w górnej części okienka omówienia, aby zarządzać pierścieniem aktualizacji:  
- [Usuwanie](#delete)  
- [Wstrzymanie](#pause)  
- [Wznawianie](#resume)  
- [Rozwijanie](#extend)  
- [Odinstalowywanie](#uninstall)  

![Dostępne akcje](./media/windows-update-for-business-configure/overview-actions.png)

### <a name="delete"></a>Usuwanie  
Wybierz pozycję **Usuń**, aby zatrzymać wymuszanie ustawień wybranego pierścienia aktualizacji systemu Windows 10. Usunięcie pierścienia powoduje usunięcie jego konfiguracji z usługi Intune, a usługa Intune nie stosuje ani nie wymusza już tych ustawień.  

Usunięcie pierścienia z usługi Intune nie modyfikuje ustawień na urządzeniach, do których przypisano pierścień aktualizacji.  Na urządzeniu zachowywane są bieżące ustawienia. Dzieje się tak, ponieważ urządzenia nie utrzymują historycznego rekordu zawierającego informacje na temat poprzednio stosowanych ustawień, a także ponieważ urządzenie mogło otrzymać ustawienia z dodatkowych pierścieni aktualizacji, które pozostają aktywne.  

#### <a name="to-delete-a-ring"></a>Aby usunąć pierścień  
1. Na wyświetlonej stronie omówienia pierścienia aktualizacji wybierz pozycję **Usuń**.  
2. Wybierz przycisk **OK**.  

### <a name="pause"></a>Wstrzymaj  
Wybierz pozycję **Wstrzymaj**, aby uniemożliwić otrzymywanie przez przypisane urządzenia aktualizacji dotyczących funkcji lub jakości przez okres do 35 dni od chwili wstrzymania pierścienia. Po upływie maksymalnej liczby dni automatycznie wygasa działanie funkcji wstrzymania i urządzenie rozpoczyna skanowanie usługi Windows Update w poszukiwaniu odpowiednich aktualizacji. Po tym skanowaniu można ponownie wstrzymać aktualizacje. Jeśli wznowisz wstrzymany pierścień aktualizacji, a następnie ponownie wstrzymasz ten pierścień, okres wstrzymania zostanie zresetowany do 35 dni.  

 #### <a name="to-pause-a-ring"></a>Aby wstrzymać pierścień  
1. Na wyświetlonej stronie omówienia pierścienia aktualizacji wybierz pozycję **Wstrzymaj**.  
2. Wybierz pozycję **Funkcja** lub **Jakość**, aby wstrzymać dany typ aktualizacji, a następnie wybierz przycisk **OK**.  
3. Po wstrzymaniu jednego typu aktualizacji możesz ponownie wybrać pozycję Wstrzymaj, aby wstrzymać drugi typ aktualizacji.  

Jeśli typ aktualizacji został wstrzymany, okienko omówienia tego pierścienia zawiera liczbę dni pozostałych do wznowienia typu aktualizacji.

> [!IMPORTANT]  
> Gdy wydasz polecenie wstrzymania, urządzenia otrzymają je przy następnym zarejestrowaniu się w usłudze. Istnieje możliwość, że urządzenia mogą zainstalować zaplanowaną aktualizację przed zarejestrowaniem. Ponadto jeśli urządzenie docelowe jest wyłączone w momencie wydania polecenia wstrzymania, może ono po włączeniu pobrać i zainstalować zaplanowane aktualizacje przed zarejestrowaniem się w usłudze Intune.

### <a name="resume"></a>Wznowienie  
Jeśli pierścień aktualizacji został wstrzymany, możesz wybrać pozycję **Wznów**, aby przywrócić aktywne działanie aktualizacji dotyczących funkcji i jakości. Po wznowieniu pierścienia aktualizacji możesz ponownie wstrzymać ten pierścień.  

#### <a name="to-resume-a-ring"></a>Aby wznowić pierścień  
1. Na wyświetlonej stronie omówienia wstrzymanego pierścienia aktualizacji wybierz pozycję **Wznów**.  
2. Z listy dostępnych opcji wybierz odpowiednią pozycję, aby wznowić aktualizacje dotyczące **funkcji** lub **jakości**, a następnie wybierz przycisk **OK**.  
3. Po wznowieniu jednego typu aktualizacji możesz ponownie wybrać pozycję Wznów, aby wznowić drugi typ aktualizacji.  

### <a name="extend"></a>Rozszerzanie  
Jeśli pierścień aktualizacji został wstrzymany, możesz wybrać pozycję **Rozszerz**, aby zresetować okres wstrzymania aktualizacji dotyczących funkcji i jakości tego pierścienia aktualizacji do 35 dni.  

#### <a name="to-extend-the-pause-period-for-a-ring"></a>Aby rozszerzyć okres wstrzymania pierścienia  
1. Na wyświetlonej stronie omówienia wstrzymanego pierścienia aktualizacji wybierz pozycję **Rozszerz**. 
2. Z listy dostępnych opcji wybierz odpowiednią pozycję, aby wznowić aktualizacje dotyczące **funkcji** lub **jakości**, a następnie wybierz przycisk **OK**.  
3. Po rozszerzeniu wstrzymania dla jednego typu aktualizacji możesz ponownie wybrać pozycję Rozszerz, aby rozszerzyć drugi typ aktualizacji.  

### <a name="uninstall"></a>Odinstalowanie  
Administrator usługi Intune może użyć pozycji **Odinstaluj** w celu odinstalowania (wycofania) najnowszej aktualizacji dotyczącej *funkcji* lub najnowszej aktualizacji dotyczącej *jakości* dla aktywnego lub wstrzymanego pierścienia aktualizacji. Po odinstalowaniu jednego typu możesz odinstalować drugi typ. Usługa Intune nie obsługuje możliwości odinstalowywania aktualizacji przez użytkowników ani nie zarządza nią.  

Aby odinstalowywanie zakończyło się powodzeniem:  
- Na urządzeniu musi działać aktualizacja systemu Windows 10 z kwietnia 2018 (wersja 1803) lub nowsza.  

Urządzenie musi mieć zainstalowaną najnowszą aktualizację. Ponieważ aktualizacje są zbiorcze, urządzenia z zainstalowaną najnowszą aktualizacją będą mieć najnowszą aktualizację dotyczącą funkcji i jakości. Przykładem zastosowania tej opcji może być wycofanie ostatniej aktualizacji po wykryciu problemu powodującego niezgodności na maszynach z systemem Windows 10.  

Podczas korzystania z odinstalowywania uwzględnij następujące kwestie:  
- Odinstalowywanie aktualizacji funkcji lub jakości jest dostępne tylko dla kanału obsługi dostępnego na urządzeniu.  

- Użycie odinstalowywania aktualizacji funkcji lub jakości wyzwala zasady w celu przywrócenia poprzedniej aktualizacji na maszynach z systemem Windows 10.  

- Po pomyślnym wycofaniu aktualizacji dotyczącej jakości na urządzeniu z systemem Windows 10 użytkownicy końcowi nadal będą widzieć tę aktualizację wymienioną w obszarze **Ustawienia systemu Windows** > **Aktualizacje** > **Historia aktualizacji**.  

- W szczególności aktualizacje dotyczące funkcji można odinstalować w ograniczonym czasie od 2 do 60 dni, zgodnie z konfiguracją ustawienia aktualizacji pierścieni aktualizacji **Ustaw okres deinstalacji aktualizacji funkcji (od 2 do 60 dni)**. Nie można wycofać aktualizacji funkcji, która została zainstalowana na urządzeniu, jeśli aktualizacja funkcji była zainstalowana dłużej niż skonfigurowany okres odinstalowywania.  

  Na przykład rozważ użycie pierścienia aktualizacji z okresem odinstalowywania aktualizacji funkcji o długości 20 dni. Po 25 dniach decydujesz się na wycofanie najnowszej aktualizacji funkcji i użycie opcji Odinstaluj.  Urządzenia, na których aktualizacja funkcji została zainstalowana ponad 20 dni temu, nie mogą jej odinstalować, ponieważ niezbędne elementy zostały usunięte w ramach konserwacji urządzenia. Natomiast urządzenia, na których aktualizacja funkcji została zainstalowana maksymalnie 19 dni temu, mogą odinstalować aktualizację, jeśli zostaną pomyślnie zaewidencjonowane w celu odebrania polecenia odinstalowania przed przekroczeniem 20-dniowego okresu odinstalowywania.  

Aby uzyskać więcej informacji na temat zasad usługi Windows Update, zobacz artykuł [Update CSP](https://docs.microsoft.com/windows/client-management/mdm/update-csp) (Dostawca konfiguracji usługi aktualizacji) w dokumentacji dotyczącej zarządzania klientem systemu Windows.  

#### <a name="to-uninstall-the-latest-windows-10-update"></a>Aby odinstalować najnowszą aktualizację systemu Windows 10  
1. Na wyświetlonej stronie omówienia wstrzymanego pierścienia aktualizacji wybierz pozycję **Odinstaluj**.  
2. Z listy dostępnych opcji wybierz odpowiednią pozycję, aby odinstalować aktualizacje dotyczące **funkcji** lub **jakości**, a następnie wybierz przycisk **OK**.  
3. Po wyzwoleniu odinstalowywania jednego typu aktualizacji możesz ponownie wybrać pozycję Odinstaluj, aby odinstalować pozostały typ aktualizacji.  

## <a name="migrate-update-settings-to-the-azure-portal"></a>Migrowanie ustawień aktualizacji do witryny Azure Portal  
Klasyczny portal Azure zawiera również w profilu konfiguracji urządzenia ograniczoną liczbę innych ustawień aktualizacji systemu Windows 10. Jeśli dowolne z tych ustawień jest skonfigurowane podczas migracji do witryny Azure Portal, zdecydowanie zalecamy wykonanie następujących czynności:  

1. Utwórz pierścienie aktualizacji systemu Windows 10 w witrynie Azure Portal, używając niezbędnych ustawień. Ustawienie **Zezwolenia na funkcje wersji wstępnej** nie jest obsługiwane w witrynie Azure Portal, ponieważ nie jest już stosowane w najnowszych wersjach systemu Windows 10. Podczas tworzenia pierścieni aktualizacji możesz skonfigurować trzy pozostałe ustawienia, jak również inne ustawienia aktualizacji systemu Windows 10.  

   > [!NOTE]  
   > Ustawienia aktualizacji systemu Windows 10 utworzone w portalu klasycznym nie są wyświetlane w witrynie Azure Portal po migracji. Te ustawienia są jednak stosowane. Ustawienia, które po migracji zostały poddane edycji w witrynie Azure Portal, są usuwane z zasad.  

2. Ustawienia aktualizacji należy usuwać w portalu klasycznym. Po migracji do witryny Azure Portal i dodaniu tego samego ustawienia do pierścienia aktualizacji należy usunąć ustawienie z portalu klasycznego, aby uniknąć potencjalnych konfliktów zasad. Konflikt występuje na przykład wtedy, gdy to samo ustawienie zostanie skonfigurowane z różnymi wartościami. Nie ma prostego sposobu na sprawdzenie tego, ponieważ ustawienie skonfigurowane w portalu klasycznym nie jest wyświetlane w witrynie Azure Portal.  

## <a name="next-steps"></a>Następne kroki
[Ustawienia aktualizacji systemu Windows obsługiwane przez usługę Intune](windows-update-settings.md)  

[Raporty zgodności usługi Intune dla aktualizacji](windows-update-compliance-reports.md)

