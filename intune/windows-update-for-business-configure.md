---
title: Konfigurowanie ustawień usługi Windows Update dla firm w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zaktualizuj ustawienia aktualizacji oprogramowania w profilu, aby tworzyć pierścień aktualizacji, sprawdzać zgodność i wstrzymywać aktualizacje w ustawieniach usługi Windows Update dla firm za pomocą usługi Microsoft Intune na urządzeniach z systemem Windows 10.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 5/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: coryfe
ms.suite: ems
ms.openlocfilehash: fd63fb2023b4712a3ad49838f87f5b7cc8320954
ms.sourcegitcommit: 97b9f966f23895495b4c8a685f1397b78cc01d57
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34744894"
---
# <a name="manage-software-updates-in-intune"></a>Zarządzanie aktualizacjami oprogramowania w usłudze Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

System Windows jako usługa to sposób aktualizowania urządzeń z systemem Windows 10. W systemie Windows 10 nowe aktualizacje funkcji oraz aktualizacje dotyczące jakości obejmują zawartość wszystkich poprzednich aktualizacji. Po zainstalowaniu najnowszej aktualizacji masz pewność, że urządzenia z systemem Windows 10 są aktualne. W odróżnieniu od wcześniejszych wersji systemu Windows teraz musisz zainstalować całą aktualizację, a nie tylko jej część.

Używając usługi Windows Update dla firm, można uprościć środowisko zarządzania aktualizacjami. Nie musisz zatwierdzać poszczególnych aktualizacji dla grup urządzeń. Możesz zarządzać ryzykiem w środowiskach, konfigurując strategię wdrażania aktualizacji. Dzięki usłudze Windows Update masz pewność, że aktualizacje są instalowane w odpowiednich momentach. Usługa Microsoft Intune zapewnia możliwość konfigurowania ustawień aktualizacji na urządzeniach oraz odraczania instalacji aktualizacji. Usługa Intune nie przechowuje aktualizacji, a jedynie przypisanie zasad aktualizacji. W celu pobrania aktualizacji urządzenia uzyskują dostęp bezpośrednio do usługi Windows Update. Przy użyciu usługi Intune możesz konfigurować **pierścienie aktualizacji systemu Windows 10** i zarządzać nimi. Pierścień aktualizacji obejmuje grupę ustawień, które konfigurują, kiedy i w jaki sposób instalowane są aktualizacje systemu Windows 10. Na przykład można skonfigurować następujące ustawienia:

- **Kanał obsługi systemu Windows 10**: wybierz kanał obsługi, z którego grupy urządzeń mają otrzymywać aktualizacje. Dostępne są następujące kanały: 
  - Półroczny kanał
  - Półroczny kanał (kierowany)
  - Niejawny program testów systemu Windows — szybki
  - Niejawny program testów systemu Windows — wolny
  - Wydanie w ramach niejawnego programu testów systemu Windows 
      
  Aby uzyskać więcej informacji o dostępnych kanałach obsługi, zobacz [Omówienie systemu Windows jako usługi](https://docs.microsoft.com/en-us/windows/deployment/update/waas-overview#servicing-channels).
- **Ustawienia opóźnień**: skonfiguruj ustawienia opóźnień aktualizacji w celu opóźnienia instalacji aktualizacji grup urządzeń. Użyj tych ustawień, aby wdrażać aktualizacje w etapach i móc śledzić ich postęp.
- **Wstrzymywanie**: odłóż instalację aktualizacji, jeśli zostanie wykryty problem w dowolnym momencie wdrażania aktualizacji.
- **Okno obsługi**: skonfiguruj godziny, w których można instalować aktualizacje.
- **Typ aktualizacji**: wybierz typy aktualizacji przeznaczone do zainstalowania. Na przykład aktualizacje dotyczące jakości, aktualizacje dotyczące funkcji lub aktualizacje sterowników.
- **Zachowanie podczas instalacji**: określa sposób przeprowadzania instalacji aktualizacji. To ustawienie określa na przykład, czy urządzenie jest automatycznie ponownie uruchamiane po zakończeniu instalacji.
- **Pobieranie elementów równorzędnych**: możesz skonfigurować pobieranie elementów równorzędnych. W przypadku skonfigurowania tej opcji po zakończeniu pobierania przez urządzenie aktualizacji inne urządzenia mogą pobierać aktualizację z tego urządzenia. To ustawienie przyspiesza proces pobierania.

Po utworzeniu pierścieni aktualizacji należy je przypisać do grup urządzeń. Za pomocą pierścieni aktualizacji można utworzyć strategię aktualizacji, która uwzględnia potrzeby biznesowe. Aby uzyskać więcej informacji, zobacz artykuł [Manage updates using Windows Update for Business](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb) (Zarządzanie aktualizacjami za pomocą usługi Windows Update dla firm).

## <a name="before-you-start"></a>Przed rozpoczęciem

- Aby można było zaktualizować komputery z systemem Windows 10, musi na nich być uruchomiony co najmniej system Windows 10 Pro z Rocznicową aktualizacją.

- Usługa Windows Update obsługuje następujące wersje systemu Windows 10:
  - Windows 10
  - Windows 10 Team (dla urządzeń Surface Hub)
  - [Windows Holographic for Business](#windows-holographic-for-business-support)

  Urządzenia z systemem Windows 10 Mobile nie są obsługiwane.

- Na urządzeniach z systemem Windows opcja **Opinia i diagnostyka** > **Dane diagnostyczne i dane użycia** musi mieć co najmniej wartość **Podstawowa**.

    ![Ustawienie systemu Windows dla danych diagnostycznych i danych dotyczących użycia](./media/telemetry-basic.png)

    To ustawienie można skonfigurować ręcznie lub też można użyć profilu ograniczeń urządzenia usługi Intune dla systemu Windows 10 i nowszych. Aby to zrobić, należy skonfigurować ustawienie **Ogólne** > **Przesłanie danych diagnostycznych** do wartości co najmniej **Podstawowe**. Aby uzyskać więcej informacji o profilach urządzenia, zobacz artykuł [Konfigurowanie ustawień ograniczeń dotyczących urządzeń](device-restrictions-configure.md).

- W konsoli administracyjnej usługi Intune istnieją cztery ustawienia określające zachowanie aktualizacji oprogramowania. Te ustawienia są częścią ogólnych zasad konfiguracji systemu Windows 10 dla komputerów stacjonarnych oraz urządzeń przenośnych:
  - **Zezwalaj na aktualizacje automatyczne**
  - **Zezwalaj na funkcje wersji wstępnej**
  - **Planowany dzień instalacji**
  - **Planowana godzina instalacji**

  Klasyczny portal Azure zawiera również w profilu konfiguracji urządzenia ograniczoną liczbę innych ustawień aktualizacji systemu Windows 10. Jeśli dowolne z tych ustawień jest skonfigurowane podczas migracji do witryny Azure Portal, zdecydowanie zalecamy wykonanie następujących czynności:

1. Utwórz pierścienie aktualizacji systemu Windows 10 w witrynie Azure Portal, używając niezbędnych ustawień. Ustawienie **Zezwolenia na funkcje wersji wstępnej** nie jest obsługiwane w witrynie Azure Portal, ponieważ nie jest już stosowane w najnowszych wersjach systemu Windows 10. Podczas tworzenia pierścieni aktualizacji możesz skonfigurować trzy pozostałe ustawienia, jak również inne ustawienia aktualizacji systemu Windows 10.

   > [!NOTE]
   > Ustawienia aktualizacji systemu Windows 10 utworzone w portalu klasycznym nie są wyświetlane w witrynie Azure Portal po migracji. Te ustawienia są jednak stosowane. Ustawienia, które po migracji zostały poddane edycji w witrynie Azure Portal, są usuwane z zasad.

2. Ustawienia aktualizacji należy usuwać w portalu klasycznym. Po migracji do witryny Azure Portal i dodaniu tego samego ustawienia do pierścienia aktualizacji należy usunąć ustawienie z portalu klasycznego, aby uniknąć potencjalnych konfliktów zasad. Konflikt występuje na przykład wtedy, gdy to samo ustawienie zostanie skonfigurowane z różnymi wartościami. Nie ma prostego sposobu na sprawdzenie tego, ponieważ ustawienie skonfigurowane w portalu klasycznym nie jest wyświetlane w witrynie Azure Portal.

## <a name="create-and-assign-update-rings"></a>Tworzenie i przypisywanie pierścieni aktualizacji

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz pozycję **Aktualizacje oprogramowania** > **Pierścienie aktualizacji systemu Windows 10** > **Utwórz**.
4. Wprowadź nazwę i opis (opcjonalnie), a następnie wybierz pozycję **Konfiguruj**.
5. W obszarze **Ustawienia** wprowadź następujące informacje:

   - **Kanał obsługi**: ustaw kanał, z którego urządzenie ma otrzymywać aktualizacje systemu Windows.
   - **Aktualizacje produktów firmy Microsoft**: określ, czy skanować w poszukiwaniu aktualizacji z usługi Microsoft Update.
   - **Sterowniki systemu Windows**: określ, czy podczas aktualizacji chcesz wykluczyć aktualizację sterowników z usługi Windows Update.
   - **Zachowanie automatycznych aktualizacji**: wybierz sposób instalowania automatycznych aktualizacji oraz moment ponownego uruchomienia. Aby uzyskać szczegółowe informacje, zobacz sekcję [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#update-allowautoupdate).
     - **Częstotliwość automatycznego zachowania**: to ustawienie jest wyświetlane, jeśli jako automatyczne zachowanie wybierzesz opcję **Automatycznie instaluj i uruchamiaj ponownie w zaplanowanym czasie**. Za pomocą tego ustawienia możesz planować instalowanie aktualizacji, w tym tydzień, dzień i godzinę.

   - **Testy po ponownym uruchomieniu**: domyślnie włączone. Po ponownym uruchomieniu urządzenia przeprowadzane są testy obejmujące aktywnych użytkowników, poziom naładowania baterii, uruchomione gry oraz inne. Aby pominąć te testy po ponownym uruchomieniu urządzenia, wybierz pozycję **Pomiń**.

   - **Okres opóźnienia aktualizacji dotyczących jakości (dni)**: wprowadź liczbę dni opóźniania aktualizacji dotyczących jakości. Okres opóźnienia aktualizacji dotyczących jakości może wynosić do 30 dni od daty wydania aktualizacji.

     Aktualizacje dotyczące jakości są zazwyczaj poprawkami oraz ulepszeniami istniejących funkcji systemu Windows i są publikowane w pierwszy wtorek każdego miesiąca. Firma Microsoft może jednak je udostępnić w dowolnym momencie. Możesz określić, czy i na jak długo mają zostać opóźnione aktualizacje dotyczące jakości po udostępnieniu ich w usłudze Windows Update.

   - **Okres opóźnienia aktualizacji funkcji (dni)**: wprowadź liczbę dni opóźniania aktualizacji funkcji. Okres opóźnienia aktualizacji funkcji może wynosić do 180 dni od daty wydania aktualizacji.

     Aktualizacje dotyczące funkcji są zazwyczaj nowymi funkcjami systemu Windows. Po skonfigurowaniu ustawienia **Kanał obsługi** możesz określić, czy i na jak długo mają zostać opóźnione aktualizacje funkcji po udostępnieniu ich w usłudze Windows Update.

     Na przykład **jeśli ustawiono kanał obsługi Półroczny kanał (kierowany), a okres opóźnienia wynosi 30 dni**: załóżmy, że aktualizacja dotycząca funkcji X została po raz pierwszy publicznie udostępniona w usłudze Windows Update jako Półroczny kanał (kierowany) w styczniu. Urządzenie nie otrzyma tej aktualizacji do lutego — 30 dni później.

     **Jeśli ustawiono kanał obsługi Półroczny kanał, a okres opóźnienia wynosi 30 dni**: załóżmy, że aktualizacja dotycząca funkcji X została po raz pierwszy publicznie udostępniona w usłudze Windows Update jako Półroczny kanał (kierowany) w styczniu. Cztery miesiące później, w kwietniu, aktualizacja dotycząca funkcji X zostaje wydana jako Półroczny kanał. Urządzenie otrzyma aktualizację funkcji po 30 dniach od opublikowania wersji Półroczny kanał i aktualizacja nastąpi w maju.

   - **Tryb pobierania optymalizacji dostarczania**: wybierz metodę pobierania aktualizacji systemu Windows używaną przez urządzenia. Aby uzyskać szczegółowe informacje, zobacz [DeliveryOptimization/DODownloadMode](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization#download-mode).

6. Po zakończeniu wybierz przycisk **OK**. W obszarze **Tworzenie pierścienia aktualizacji**, wybierz pozycję **Utwórz**.

Nowy pierścień aktualizacji jest wyświetlany na liście pierścieni aktualizacji.

1. Aby przypisać pierścień, wybierz go na liście, a następnie na karcie <*nazwa pierścienia*> wybierz opcję **Przypisania**.
2. Na następnej karcie wybierz pozycję **Wybierz grupy do uwzględnienia**, a następnie wybierz grupy, do których chcesz przypisać ten pierścień.
3. Gdy skończysz, wybierz opcję **Wybierz** w celu zakończenia przypisywania.

## <a name="update-compliance-reporting"></a>Raportowanie zgodności aktualizacji
Zgodność aktualizacji można monitorować w usłudze Intune za pomocą bezpłatnego rozwiązanie wchodzącego w skład pakietu Operations Management Suite (OMS) o nazwie Update Compliance.

### <a name="review-update-compliance-in-intune"></a>Przeglądanie zgodności aktualizacji w usłudze Intune 
<!-- 1352223 -->
Przejrzyj raport zasad, aby poznać stan wdrożenia dla skonfigurowanych pierścieni aktualizacji systemu Windows 10.

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz pozycję **Aktualizacje oprogramowania** > **Przegląd**. Zostaną wyświetlone ogólne informacje o stanie wszystkich przypisanych pierścieni aktualizacji.
4. Otwórz jeden z następujących raportów:

   **Dla wszystkich pierścieni wdrażania**:  
   1. W obszarze **Aktualizacje oprogramowania** > **Pierścienie aktualizacji systemu Windows 10**
   2. W sekcji **Monitorowanie** wybierz pozycję **Stan wdrożenia według pierścienia aktualizacji**.

   **Dla określonych pierścieni wdrażania**:  
   1. W obszarze **Aktualizacje oprogramowania** > **Pierścienie aktualizacji systemu Windows 10** wybierz pierścień wdrażania, który chcesz przejrzeć.
   2. W sekcji **Monitorowanie** wybierz jeden z następujących raportów, aby wyświetlić bardziej szczegółowe informacje o pierścieniu aktualizacji:
      - **Stan urządzenia**
      - **Stan użytkownika**

### <a name="review-update-compliance-using-oms"></a>Przeglądanie zgodności aktualizacji przy użyciu pakietu OMS
Wdrożenia aktualizacji systemu Windows 10 można monitorować za pomocą bezpłatnego rozwiązanie wchodzącego w skład usługi OMS (Operations Management Service) o nazwie Update Compliance. Aby uzyskać szczegółowe informacje, zobacz artykuł [Monitor Windows Updates with Update Compliance](https://technet.microsoft.com/itpro/windows/manage/update-compliance-monitor) (Monitorowanie aktualizacji systemu Windows za pomocą aplikacji Update Compliance). Dzięki temu rozwiązaniu można nadać komercyjny identyfikator dowolnemu urządzeniu z systemem Windows 10 zarządzanemu przez usługę Intune, dla którego chcesz otrzymywać raport zgodności aktualizacji.

W konsoli usługi Intune możesz użyć ustawień ścieżki OMA-URI dla niestandardowych zasad do skonfigurowania identyfikatora komercyjnego. Szczegółowe informacje można znaleźć w artykule [Ustawienia zasad usługi Intune dla urządzeń z systemem Windows 10 w usłudze Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune).   

Ścieżka OMA-URI (z uwzględnieniem wielkości liter) służąca do konfigurowania komercyjnego identyfikatora to: ./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID

Na przykład można użyć następujących wartości w obszarze **Dodaj lub edytuj ustawienie OMA-URI**:

- **Nazwa ustawienia**: identyfikator komercyjny programu Windows Analytics
- **Opis ustawienia**: konfigurowanie komercyjnych identyfikatorów rozwiązań programu Windows Analytics
- **OMA-URI** (wielkość liter jest rozróżniana): ./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID
- **Typ danych:**: ciąg
- **Wartość**: <*użyj identyfikatora GUID wyświetlanego na karcie Telemetria systemu Windows w obszarze roboczym usługi OMS*>

![Ustawienia identyfikatora OMA-URI — Edytowanie wiersza](./media/commID-edit.png)

> [!NOTE]
> Aby uzyskać więcej informacji o programie MS DM, zobacz [Dostawca usługi konfiguracji (CSP) DMClient](https://docs.microsoft.com/windows/client-management/mdm/dmclient-csp).

## <a name="pause-updates"></a>Wstrzymywanie aktualizacji
Można wstrzymać otrzymywanie przez urządzenia aktualizacji dotyczących funkcji lub aktualizacji dotyczących jakości przez okres do 35 dni od chwili wstrzymania aktualizacji. Po upływie maksymalnej liczby dni automatycznie wygasa działanie funkcji wstrzymania i urządzenie rozpoczyna skanowanie usługi Windows Update w poszukiwaniu odpowiednich aktualizacji. Po tym skanowaniu można ponownie wstrzymać aktualizacje.

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz opcję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz pozycję**Aktualizacje oprogramowania** > **Pierścienie aktualizacji systemu Windows 10**.
4. Na liście pierścieni aktualizacji wybierz pierścień, który chcesz wstrzymać, a następnie wybierz pozycję **...** > **Wstrzymaj aktualizacje dotyczące jakości** > lub **Wstrzymaj aktualizacje funkcji** w zależności od typu aktualizacji, który chcesz wstrzymać.

> [!IMPORTANT]
> Gdy wydasz polecenie wstrzymania, urządzenia otrzymają je przy następnej rejestracji w usłudze. Istnieje możliwość, że urządzenia mogą zainstalować zaplanowaną aktualizację przed zarejestrowaniem.
> Ponadto jeśli urządzenie docelowe jest wyłączone w momencie wydania polecenia wstrzymania, może ono po włączeniu pobrać i zainstalować zaplanowane aktualizacje przed zarejestrowaniem się w usłudze Intune.

### <a name="uninstall-the-latest-from-windows-10-software-updates"></a>Odinstalowywanie najnowszych aktualizacji oprogramowania systemu Windows 10 
Jeśli wykryjesz problem powodujący awarię na maszynach z systemem Windows 10, możesz odinstalować (wycofać) najnowszą aktualizację funkcji lub najnowszą aktualizację jakości. Odinstalowywanie aktualizacji funkcji lub jakości jest dostępne tylko dla kanału obsługi dostępnego na urządzeniu. Odinstalowywanie wyzwoli zasady w celu przywrócenia poprzedniej aktualizacji na maszynach z systemem Windows 10. W przypadku aktualizacji funkcji można ograniczyć czas (od 2 do 60 dni), w którym można odinstalować najnowszą wersję. Aby ustawić opcje odinstalowywania aktualizacji oprogramowania, wybierz pozycję **Aktualizacje oprogramowania** w bloku **Microsoft Intune** w witrynie Azure Portal. Następnie wybierz pozycję **Pierścienie aktualizacji systemu Windows 10** w bloku **Aktualizacje oprogramowania**. Następnie możesz wybrać opcję **Odinstaluj** w sekcji **Przegląd**.

> [!NOTE]
> Na maszynach z systemem Windows 10 po pomyślnym wycofaniu aktualizacji jakości użytkownicy końcowi nadal będą mogli wyświetlić pomyślnie wycofaną aktualizację, wybierając pozycję **Ustawienia systemu Windows** > **Aktualizacje** > **Historia aktualizacji**.

## <a name="windows-holographic-for-business-support"></a>Obsługa systemu Windows Holographic for Business

System Windows Holographic for Business obsługuje następujące ustawienia:

- **Zachowanie automatycznych aktualizacji**
- **Aktualizacje produktów firmy Microsoft**
- **Kanał obsługi**: obsługiwane są opcje **Półroczny kanał** oraz **Półroczny kanał (kierowany)**
