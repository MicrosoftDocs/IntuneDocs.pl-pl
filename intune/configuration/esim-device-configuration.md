---
title: Włączanie połączeń danych na karcie eSIM w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Możesz dodać kartę eSIM i korzystać z niej w celu uzyskania dostępu do Internetu i danych przy użyciu różnych planów taryfowych. W usłudze Intune możesz dodawać lub importować kody aktywacji, a następnie przypisywać je, korzystając z profilu konfiguracji. Możesz również monitorować profile kart eSIM i sprawdzać stan urządzeń, na których włączono obsługę karty eSIM.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: ericor
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: fbe2377bfd353dc00ddfdf53a6d091c486644194
ms.sourcegitcommit: 78cebd3571fed72a3a99e9d33770ef3d932ae8ca
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2019
ms.locfileid: "74059373"
---
# <a name="configure-esim-cellular-profiles-in-intune---public-preview"></a>Konfigurowanie profilów sieci komórkowej karty eSIM w usłudze Intune — publiczna wersja zapoznawcza

Karta eSIM to wbudowany mikroukład SIM, który umożliwia łączenie się z Internetem za pomocą połączenia danych komórkowych na urządzeniu obsługującym kartę eSIM, na przykład urządzeniu [Surface LTE Pro](https://www.microsoft.com/surface/business/surface-pro). Dzięki karcie eSIM nie trzeba uzyskiwać karty SIM od operatora sieci komórkowej. Podróżując po całym świecie, możesz także przełączać się między operatorami komórkowymi i planami taryfowymi, zawsze utrzymując połączenie.

Możesz mieć na przykład jeden plan taryfowy do celów służbowych i drugi (u innego operatora) do celów prywatnych. W podróży możesz uzyskać dostęp do Internetu po odnalezieniu operatora sieci komórkowej udostępniającego plany taryfowe na określonym obszarze.

W usłudze Intune można importować jednorazowe kody aktywacji uzyskane od operatora. Aby skonfigurować plany danych komórkowych w module eSIM, należy wdrożyć te kody aktywacji na urządzeniach z kartą eSIM. Po zainstalowaniu kodu aktywacji w usłudze Intune sprzętowy moduł eSIM używa danych z kodu aktywacji, aby skontaktować się z operatorem sieci komórkowej. Po wykonaniu tych czynności profil karty eSIM jest pobierany na urządzenie i konfigurowany w celu aktywowania sieci komórkowej.

Aby wdrożyć kartę eSIM na urządzeniach za pomocą usługi Intune, potrzebne są następujące elementy:

- **Urządzenia obsługujące kartę eSIM** takie jak Surface LTE: Sprawdź, [czy Twoje urządzenie obsługuje kartę eSIM](https://support.microsoft.com/help/4020763/windows-10-use-esim-for-cellular-data). Możesz też wyświetlić listę [niektórych znanych urządzeń obsługujących karty eSIM](#esim-capable-devices) (w tym artykule).
- **Komputer PC z systemem Windows 10 i aktualizacją Fall Creators Update**  (wersja 1709 lub nowsza) zarejestrowany w usłudze Intune i zarządzany za pomocą funkcji MDM.
- **Kody aktywacji** dostarczone przez operatora sieci komórkowej. Te jednorazowe kody aktywacji są dodawane do usługi Intune i wdrażane na urządzeniach obsługujących kartę eSIM. Skontaktuj się z operatorem sieci komórkowej, aby uzyskać kody aktywacji karty eSIM.

## <a name="deploy-esim-to-devices---overview"></a>Wdrażanie karty eSIM na urządzeniach — omówienie

Aby wdrożyć kartę eSIM na urządzeniach, administrator musi wykonać następujące zadania:

1. Zaimportować kody aktywacji dostarczone przez operatora sieci komórkowej.
2. Utworzyć grupę urządzeń usługi Azure Active Directory (Azure AD), która zawiera urządzenia obsługujące karty eSIM.
3. Przypisać grupę usługi Azure AD do zaimportowanej puli subskrypcji.
4. Monitorować wdrożenie.

Ten artykuł zawiera omówienie tych czynności.

## <a name="esim-capable-devices"></a>Urządzenia obsługujące kartę eSIM

Następujące urządzenia obsługujące kartę eSIM są dostępne na rynku lub zostały zapowiedziane. Sprawdź również, czy [Twoje urządzenie obsługuje kartę eSIM](https://support.microsoft.com/help/4020763/windows-10-use-esim-for-cellular-data).

- Acer Swift 7
- Asus NovoGo TP370QL
- Asus TP401
- Asus Transformer Mini T103
- HP Elitebook G5
- HP Envy x2
- HP Probook G5
- Lenovo Miix 630
- Lenovo T480
- Samsung Galaxy Book
- Surface Pro LTE
- HP Spectre Folio 13
- Lenovo Yoga C630

## <a name="step-1-add-cellular-activation-codes"></a>Krok 1. Dodawanie kodów aktywacji sieci komórkowej

Kody aktywacji sieci komórkowej są dostarczane przez operatora sieci komórkowej w pliku rozdzielonym przecinkami (csv). Po otrzymaniu pliku dodaj go do usługi Intune, wykonując następujące czynności:

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Urządzenia** > **Profile komórkowe eSIM** > **Dodaj**.
3. Wybierz plik CSV zawierający Twoje kody aktywacji.
4. Wybierz przycisk **OK**, aby zapisać zmiany.

### <a name="csv-file-requirements"></a>Wymagania dotyczące pliku CSV

Podczas pracy z plikiem csv zawierającym kody aktywacji upewnij się, że następujące wymagania są spełnione przez Ciebie i operatora:

- Plik musi być w formacie csv (nazwa_pliku.csv).
- Struktura pliku musi być zgodna z określonym formatem. W przeciwnym razie importowanie zakończy się niepowodzeniem. Usługa Intune sprawdza plik w trakcie importowania i kończy je niepowodzeniem, jeśli występują w nim błędy.
- Kody aktywacji są jednorazowe. Nie zaleca się importowania wcześniej zaimportowanych kodów aktywacji, ponieważ może to spowodować problemy podczas wdrażania na to samo lub inne urządzenie.
- Każdy plik powinien odpowiadać jednemu operatorowi sieci komórkowej, a wszystkie kody aktywacji — temu samemu planowi rozliczeniowemu. Usługa Intune losowo rozdziela kody aktywacji pomiędzy urządzenia docelowe. Nie ma żadnej gwarancji, które urządzenie otrzyma określony kod aktywacji.
- W jednym pliku csv można zaimportować maksymalnie 1000 kodów aktywacji.

### <a name="csv-file-example"></a>Przykładowy plik CSV

1. Pierwszy wiersz i pierwsza komórka pliku csv to adres URL usługi aktywacji karty eSIM operatora komórkowego, która nazywa się SM-DP + (serwer przygotowywania danych Menedżera subskrypcji). Adres URL powinien być w pełni kwalifikowaną nazwą domeny (FQDN) bez żadnych przecinków.
2. Drugi wiersz i wszystkie kolejne to unikatowe jednorazowe kody aktywacji zawierające dwie wartości:

    1. Pierwsza kolumna to unikatowy identyfikator ICCID (identyfikator mikroukładu SIM).
    2. Druga kolumna to identyfikator dopasowania. Obie wartości są oddzielone jednym przecinkiem (na końcu nie ma przecinka). Zapoznaj się z poniższym przykładem:

        ![Przykładowy plik csv kodu aktywacji operatora sieci komórkowej](./media/esim-device-configuration/url-activation-code-examples.png)

3. Nazwa pliku csv staje się nazwą puli subskrypcji sieci komórkowej w witrynie Azure Portal. Na poprzedniej ilustracji nazwa pliku to `UnlimitedDataSkynet.csv`. A więc usługa Intune nazywa pulę subskrypcji `UnlimitedDataSkynet.csv`:

    ![Pula subskrypcji sieci komórkowej otrzymuje nazwę taką, jak nazwa przykładowego pliku csv z kodami aktywacji](./media/esim-device-configuration/subscription-pool-name-csv-file.png)

## <a name="step-2-create-an-azure-ad-device-group"></a>Krok 2: Tworzenie grupy urządzeń usługi Azure AD

Utwórz grupę urządzeń, która zawiera urządzenia obsługujące kartę eSIM. Instrukcje znajdują się w temacie [Dodawanie grup](../fundamentals/groups-add.md).

> [!NOTE]
> - Wskazywane są wyłącznie urządzenia, nie użytkownicy.
> - Zaleca się utworzenie statycznej grupy urządzeń usługi Azure AD zawierającej urządzenia obsługujące kartę eSIM. Korzystanie z grupy pozwala mieć pewność, że wskazywane są tylko urządzenia obsługujące kartę eSIM.

## <a name="step-3-assign-esim-activation-codes-to-devices"></a>Krok 3: Przypisywanie kodów aktywacji karty eSIM do urządzeń

Przypisz profil do grupy usługi Azure AD, która zawiera urządzenia obsługujące kartę eSIM.

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Urządzenia** > **Profile komórkowe eSIM**.
3. Na liście profilów wybierz pulę subskrypcji sieci komórkowej eSIM, którą chcesz przypisać, a następnie wybierz pozycję **Przypisania**.
4. Wybierz **dołączenie** lub **wykluczenie** grup, a następnie wybierz grupy.

    ![Dołączenie grupy urządzeń w celu przypisania profilu](./media/esim-device-configuration/include-exclude-groups.png)

5. Wybierane grupy są grupami usługi Azure AD. Aby wybrać wiele grup, naciśnij klawisz **Ctrl**, a następnie wybierz grupy.
6. Po zakończeniu **Zapisz** zmiany.

Kodów aktywacji karty eSIM można użyć tylko raz. Po zainstalowaniu kodu na urządzeniu w usłudze Intune moduł karty eSIM kontaktuje się z operatorem sieci komórkowej w celu pobrania profilu sieci komórkowej. Ten kontakt kończy rejestrację urządzenia w sieci operatora.

## <a name="step-4-monitor-deployment"></a>Krok 4. Monitorowanie wdrożenia

### <a name="review-the-deployment-status"></a>Sprawdzanie stanu wdrożenia

Po przypisaniu profilu możesz monitorować stan wdrożenia puli subskrypcji.

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Urządzenia** > **Profile komórkowe eSIM**. Zostanie wyświetlona lista zawierająca wszystkie istniejące pule subskrypcji sieci komórkowej eSIM.
3. Wybierz subskrypcję i zapoznaj się z jej **stanem wdrożenia**.

### <a name="check-the-profile-status"></a>Sprawdzanie stanu profilu

Po utworzeniu profilu urządzenia usługa Intune udostępnia wykresy graficzne. Te wykresy zawierają stan profilu, taki jak pomyślne przypisanie do urządzeń lub wyświetlanie konfliktu w tym profilu.

1. Wybierz kolejno pozycje **Urządzenia** > **Profile sieci komórkowej eSIM** > wybierz istniejącą subskrypcję.
2. Na karcie **Przegląd** górny wykres graficzny przedstawia liczbę urządzeń przypisanych do określonego wdrożenia puli subskrypcji sieci komórkowej eSIM.

    Zawiera on również liczbę urządzeń dla innych platform, które zostały przypisane do tego samego profilu urządzenia.

    W usłudze Intune wyświetlany jest stan dostarczenia i instalacji kodów aktywacji na docelowych urządzeniach.

    - **Urządzenie nie jest zsynchronizowane**: docelowe urządzenie nie połączyło się z usługą Intune od momentu utworzenia zasad wdrażania karty eSIM.
    - **Oczekiwanie na aktywację**: stan przejściowy, gdy usługa Intune instaluje kod aktywacji na urządzeniu.
    - **Aktywne**: instalacja kodu aktywacji zakończyła się powodzeniem.
    - **Niepowodzenie aktywacji**: instalacja kodu aktywacji nie powiodła się — zapoznaj się z przewodnikiem rozwiązywania problemów.

#### <a name="view-the-detailed-device-status"></a>Wyświetlanie szczegółowego stanu urządzeń

Szczegółową listę urządzeń możesz wyświetlać i monitorować w obszarze Stan urządzenia.**

1. Wybierz kolejno pozycje **Urządzenia** > **Profile sieci komórkowej eSIM** > wybierz istniejącą subskrypcję.
2. Wybierz pozycję **Stan urządzenia**. W usłudze Intune wyświetlane są dodatkowe informacje dotyczące urządzenia:

    - **Nazwa urządzenia**: nazwa urządzenia docelowego
    - **Użytkownik**: użytkownik zarejestrowanego urządzenia
    - **Identyfikator ICCID**: unikatowy kod dostarczony przez operatora sieci komórkowej w ramach kodu aktywacji zainstalowanego na urządzeniu
    - **Stan aktywacji**: stan dostarczenia i instalacji kodu aktywacji na urządzeniu w usłudze Intune
    - **Stan sieci komórkowej**: stan dostarczony przez operatora sieci komórkowej. Skontaktuj się z operatorem sieci komórkowej, aby rozwiązać problem.
    - **Ostatnie zaewidencjonowanie**: data ostatniej komunikacji urządzenia z usługą Intune

### <a name="monitor-esim-profile-details-on-the-actual-device"></a>Monitorowanie szczegółów profilu karty eSIM na urządzeniu

1. Na urządzeniu otwórz **Ustawienia**, a następnie przejdź do pozycji **Sieć i Internet**.
2. Wybierz pozycję **Sieć komórkowa** > **Zarządzaj profilami karty eSIM**
3. Zostanie wyświetlona lista profilów karty eSIM:

    ![Wyświetlanie profilów karty eSIM w ustawieniach urządzenia](./media/esim-device-configuration/device-settings-cellular-profiles.png)

## <a name="remove-the-esim-profile-from-device"></a>Usuwanie profilu karty eSIM z urządzenia

Po usunięciu urządzenia z grupy usługi Azure AD profil karty eSIM również jest usuwany. Pamiętaj, aby:

1. Upewnić się, że korzystasz z grupy usługi Azure AD zawierającej urządzenia eSIM.
2. Przejdź do grupy Azure AD i usuń urządzenie z grupy.
3. Gdy usunięte urządzenie skontaktuje się z usługą Intune, zostaną ocenione zaktualizowane zasady, a profil karty eSIM zostanie usunięty.

Profil karty eSIM zostanie również usunięty, jeśli urządzenie zostanie [wycofane](../remote-actions/devices-wipe.md#retire) lub jego rejestracja zostanie cofnięta przez użytkownika, lub jeśli na urządzeniu zostanie uruchomione [zdalne działanie resetowania urządzenia](../remote-actions/devices-wipe.md#wipe).

> [!NOTE]
> Usunięcie profilu nie jest równoznaczne z zatrzymaniem naliczania opłat. Skontaktuj się z operatorem sieci komórkowej, aby sprawdzić stan rozliczeń urządzenia.

## <a name="best-practices--troubleshooting"></a>Najlepsze rozwiązania i rozwiązywanie problemów

- Upewnij się, że plik csv jest poprawnie sformatowany. Upewnij się, że plik nie zawiera zduplikowanych kodów, nie obejmuje wielu operatorów sieci komórkowych i nie zawiera różnych planów taryfowych. Pamiętaj, że każdy plik musi być unikatowy dla operatora sieci komórkowej i planu taryfowego.
- Utwórz grupę usługi Azure AD urządzeń statycznych, która będzie zawierała wyłącznie docelowe urządzenia obsługujące kartę eSIM.
- Jeśli wystąpi problem ze stanem wdrożenia, sprawdź następujące elementy:
  - **Nieprawidłowy format pliku**: Patrz **Krok 1. Dodawanie kodów aktywacji sieci komórkowej** (w tym artykule), aby zapoznać się z prawidłowym formatem pliku.
  - **Aktywacja sieci komórkowej zakończyła się niepowodzeniem, skontaktuj się z operatorem sieci komórkowej**: kod aktywacji nie został aktywowany w sieci. Możliwe również, że pobieranie profilu i aktywacja w sieci komórkowej zakończyły się niepowodzeniem.

## <a name="next-steps"></a>Następne kroki
[Konfigurowanie profilów urządzeń](../device-profiles.md)
