---
title: Monitorowanie zasad zgodności urządzeń w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Pulpit nawigacyjny zgodności urządzeń służy do monitorowania ogólnej zgodności urządzeń, wyświetlania raportów i wyświetlania zgodności urządzeń z poszczególnymi zasadami i ustawieniami.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 7/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 557bdbace1752b8680cd15d7ba190577bec23e24
ms.sourcegitcommit: 2e849eea920dcd6ef1b78e5aee26434bb7b01bff
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/18/2018
ms.locfileid: "39132463"
---
# <a name="monitor-intune-device-compliance-policies"></a>Monitorowanie zasad zgodności urządzeń Intune

Raporty zgodności umożliwiają administratorom analizowanie stanu zgodności urządzeń w organizacji i szybkie rozwiązywanie problemów ze zgodnością napotykanych przez użytkowników w organizacji. Można wyświetlić informacje o ogólnym stanie zgodności urządzeń, stanie zgodności poszczególnych ustawień, stanie zgodności dla poszczególnych zasad, a także przejść do poszczególnych urządzeń, aby wyświetlić konkretne ustawienia i zasady, które wpływają na urządzenie.

## <a name="before-you-begin"></a>Przed rozpoczęciem

Wykonaj następujące kroki, aby znaleźć **pulpit nawigacyjny zgodności urządzeń Intune** w witrynie Azure Portal:

1. W witrynie [Azure Portal](https://portal.azure.com) zaloguj się przy użyciu poświadczeń usługi Intune.

2. Wybierz opcję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.

3. Wybierz pozycję **Zgodność urządzenia** > **Przegląd**. Zostanie otwarty **pulpit nawigacyjny zgodności urządzeń**.

> [!IMPORTANT]
> Aby otrzymać zasady zgodności urządzeń, urządzenia muszą być zarejestrowane w usłudze Intune.

## <a name="device-compliance-dashboard"></a>Pulpit nawigacyjny zgodności urządzeń

Za pomocą **pulpitu nawigacyjnego zgodności urządzeń** można monitorować zgodność różnych urządzeń, ich stan ochrony i inne dane. Istnieje możliwość wyświetlenia następujących raportów:

- Ogólna zagregowana zgodność urządzeń

- Zgodność urządzeń wg zasady

- Zgodność urządzeń wg ustawienia

- Stan ochrony urządzenia

- Stan agenta zagrożeń

![Obraz przedstawiający pulpit nawigacyjny zgodności urządzeń](./media/idc-1.png)

Można także wyświetlić określone zasady i ustawienia zgodności, które mają zastosowanie do poszczególnych urządzeń, oraz końcowy stan zgodności dla każdego z tych ustawień na urządzeniu.

### <a name="overall-device-compliance-aggregate-report"></a>Raport ogólnej zagregowanej zgodności urządzeń

Jest to wykres pierścieniowy przedstawiający zagregowany stan zgodności dla wszystkich urządzeń zarejestrowanych w usłudze Intune. Stany zgodności urządzeń są przechowywane w dwóch różnych bazach danych, Intune i Azure Active Directory. Poniżej przedstawiono szczegółowe informacje o stanach zasad zgodności urządzeń:

- **Zgodne**: urządzenie pomyślnie zastosowało co najmniej jedno ustawienie zasady zgodności urządzenia przepisane przez administratora.

- **Niezgodne**: nie udało się zastosować co najmniej jednego ustawienia zasady zgodności urządzenia przepisanego przez administratora lub też użytkownik nie spełnił zasad zgodności przepisanych przez administratora.

- **Okres prolongaty**: administrator przepisał do urządzenia co najmniej jedno ustawienie zasady zgodności, ale użytkownik nie zastosował tych zasad, co oznacza, że urządzenie nie jest zgodne ze specyfikacją, ale trwa okres prolongaty zdefiniowany przez administratora.

  - Dowiedz się więcej o akcjach dla niezgodnych urządzeń.

- **Urządzenie nie jest zsynchronizowane**: urządzenie nie zgłosiło stanu zasad zgodności urządzenia z jednej z następujących przyczyn:

  - **Nieznany**: urządzenie jest w trybie offline lub nie nawiązało łączności z usługą Intune lub Azure AD z innych przyczyn.

  - **Błąd**: urządzenie nie skomunikowało się z usługą Intune i Azure AD i otrzymało komunikat o błędzie z podanym powodem.

> [!IMPORTANT]
> Urządzenia, które są zarejestrowane w usłudze Intune, ale nie są objęte żadnymi zasadami zgodności urządzeń, są uwzględnione w raporcie w obszarze **Zgodne**.

#### <a name="drill-down-option"></a>Opcja przechodzenia do informacji szczegółowych

Na **pulpicie nawigacyjnym zgodności urządzeń** wybierz kafelek zgodności urządzenia, aby przejść do określonego **stanu zgodności**, **aliasu adresu e-mail użytkownika**, **modelu urządzenia** i **lokalizacji** dla każdego urządzenia, które jest objęte zasadami zgodności urządzeń.

![Obraz przedstawiający przechodzenie do informacji szczegółowych na pulpicie nawigacyjnym zgodności urządzeń](./media/idc-2.png)

Aby uzyskać więcej szczegółów na temat określonego użytkownika, można filtrować raport wykresu zgodności urządzeń, wpisując alias adresu e-mail użytkownika.

![Obraz przedstawiający konkretnego użytkownika pulpitu nawigacyjnego zgodności urządzeń](./media/idc-3.png)

Możesz również kliknąć inny stan zgodności na wykresie zgodności urządzeń, aby zobaczyć bardziej szczegółowe informacje o stanach zasady zgodności urządzeń użytkownika.

![Obraz przedstawiający różne stany pulpitu nawigacyjnego zgodności urządzeń](./media/idc-4.png)

#### <a name="filter"></a>Filtr

Po wybraniu **przycisku Filtr** będą dostępne następujące opcje:

- Model

  - Pole tekstowe, w którym można wpisać dowolny wyszukiwany ciąg

- Platforma

  - Android

  - iOS

  - macOS

  - Windows

  - Windows Phone

- Stan

  - Zgodny

  - Niezgodny

  - Okres prolongaty

  - Nieznane

  - Error

Po wybraniu **przycisku Aktualizuj** wyświetlane elementy zostaną zamknięte, a wyniki zostaną zaktualizowane przy użyciu wybranych kryteriów filtrowania.

##### <a name="device-details"></a>Szczegóły urządzenia

Wybranie urządzenia powoduje otwarcie okna **Urządzenia** z wybranym urządzeniem. Dzięki temu jest dostępnych więcej szczegółów dotyczących ustawienia zasad zgodności urządzenia zastosowanego do danego urządzenia.

Po wybraniu samego ustawienia zasad urządzenia zostanie wyświetlona nazwa zasad zgodności urządzenia wskazująca, że ustawienie zgodności urządzenia zostało zalecone przez administratora.

### <a name="devices-without-compliance-policy"></a>Urządzenia bez zasad zgodności
Ten raport wskazuje urządzenia, które nie mają przypisanych żadnych zasad zgodności. Wraz z wprowadzeniem ustawienia zabezpieczeń, które oznacza wszystkie urządzenia bez zasad zgodności jako „niezgodne”, ważne jest, aby można było zidentyfikować te urządzenia. Następnie możesz im przypisać co najmniej jedne zasady zgodności.

> [!NOTE]
> Nowe ustawienie zabezpieczeń można skonfigurować w portalu usługi Intune. Wybierz opcję **Zgodność urządzenia**, a następnie w obszarze **Konfiguracja** wybierz opcję **Ustawienia zasad zgodności**. Następnie użyj przełącznika, aby ustawić opcję **Oznaczaj urządzenia bez przypisanych zasad zgodności jako** na wartość **Zgodne** lub **Niezgodne**. Dowiedz się więcej o tym [ulepszeniu zabezpieczeń w usłudze Intune](https://blogs.technet.microsoft.com/intunesupport/2018/02/09/updated-upcoming-security-enhancements-in-the-intune-service/).

![Obraz przedstawiający raport urządzeń bez zasad zgodności](./media/idc-12.png)

Kafelek **Urządzenia bez zasad zgodności** jest dostępny z poziomu pulpitu nawigacyjnego zgodności urządzeń i przedstawia wszystkie urządzenia bez zasad zgodności, użytkownika urządzenia, stan zgodności i model urządzenia.

> [!NOTE]
> Użytkownicy z przypisanymi zasadami zgodności dowolnego typu nie będą wyświetlani w raporcie, niezależnie od platformy urządzeń. Jeśli na przykład przypadkowo przypiszesz zasady zgodności systemu Windows do użytkownika z systemem Android, urządzenie nie będzie ujęte w raporcie. Jednak usługa Intune uzna urządzenie z systemem Android za niezgodne. Aby uniknąć problemów, firma Microsoft zaleca utworzenie zasad dla każdej platformy urządzeń i wdrożenie ich do wszystkich użytkowników.

### <a name="per-policy-device-compliance-report"></a>Raport zgodności urządzeń wg zasady

Ten raport zawiera widok wg zasady zgodności oraz łączną liczbę urządzeń znajdujących się w poszczególnych stanach zgodności. Kafelek **Zgodność z zasadami** jest dostępny na **pulpicie nawigacyjnym zgodności urządzenia** i zawiera wszystkie zasady wcześniej utworzone przez administratora, platformy, na których zasady są stosowane, liczbę zgodnych urządzeń oraz liczbę urządzeń niezgodnych.

![Obraz przedstawiający raport zgodności urządzeń wg zasad](./media/idc-8.png)

Kliknięcie na pulpicie nawigacyjnym zgodności urządzeń kafelka Zgodność z zasadami umożliwia przejście do określonego **stanu zgodności**, **aliasu adresu e-mail użytkownika**, **modelu urządzenia** i **lokalizacji** dla każdego urządzenia, które było objęte daną zasadą zgodności urządzeń.

## <a name="setting-compliance-report"></a>Raport o zgodności ustawień

Ten raport umożliwia zapoznanie się z łączną liczbą urządzeń znajdujących się w poszczególnych stanach zgodności dla każdego ustawienia zgodności. Kafelek **Zgodność ustawień** jest dostępny na **pulpicie nawigacyjnym zgodności urządzenia** i pokazuje wszystkie ustawienia zasad zgodności urządzeń dla wszystkich zasad zgodności urządzeń utworzonych przez administratora, platformy, do których zastosowano ustawienia zasad, oraz liczbę niezgodnych urządzeń.

![Obraz przedstawiający raport zgodności urządzeń wg ustawienia](./media/idc-10.png)

Kliknięcie na pulpicie nawigacyjnym zgodności urządzeń kafelka Zgodność ustawień umożliwia przejście do określonego **stanu zgodności**, **aliasu adresu e-mail użytkownika**, **modelu urządzenia** i **lokalizacji** dla każdego urządzenia, które było objęte daną zasadą zgodności urządzeń.

## <a name="view-status-of-device-policies"></a>Wyświetlanie stanu zasad dotyczących urządzenia

Różne stany zasad można sprawdzać według platformy. Na przykład masz zasady zgodności systemu macOS. Chcesz wyświetlić urządzenia, na które wpływają te zasady, i dowiedzieć się, czy występują konflikty lub błędy.

Ta funkcja jest uwzględniana w obszarze raportowania stanu urządzenia:

1. Wybierz kolejno pozycje **Zgodność urządzenia** > **Zasady**. Zostanie wyświetlona lista zasad, w tym platforma, informacja o przypisaniu zasad i dalsze szczegóły.
2. Wybierz zasadę > **Omówienie**. W tym widoku przypisanie zasad uwzględnia następujące stany:

  - Powodzenie: zasady zostały zastosowane.
  - Błąd: nie można zastosować zasad. Ten stan jest przeważnie wyświetlany z kodem błędu stanowiącym link do wyjaśnienia. 
  - Konflikt: na tym samym urządzeniu zostały zastosowane dwa ustawienia, a usługa Intune nie może rozwiązać konfliktu. Administrator powinien zapoznać się z tą sytuacją.
  - Oczekujące: urządzenie nie zostało jeszcze zaewidencjonowane w usłudze Intune w celu odebrania zasad. 
  - Nie dotyczy: urządzenie nie może odebrać zasad. Na przykład zasady aktualizują ustawienie specyficzne dla systemu iOS 11.1, ale urządzenie używa systemu iOS 10. 

3. Aby wyświetlić szczegóły urządzeń używających danych zasad, wybierz jeden z stanów. Na przykład wybierz pozycję **Powodzenie**. W następnym oknie jest wyświetlana lista szczegółów określonego urządzenia, w tym nazwa i stan jego wdrażania.

## <a name="how-intune-resolves-policy-conflicts"></a>Jak są rozwiązywane konflikty zasad usługi Intune
Konflikty zasad mogą wystąpić, gdy na urządzeniu stosuje się wiele zasad usługi Intune. Jeśli ustawienia zasad nakładają się na siebie, usługa Intune rozwiązuje konflikty, używając następujących reguł:

- Jeżeli sprzeczne ustawienia pochodzą z zasad konfiguracji usługi Intune i zasad zgodności, ustawienia w zasadach zgodności mają pierwszeństwo względem ustawień w zasadach konfiguracji. Dzieje się tak nawet wtedy, gdy ustawienia w zasadach konfiguracji są bardziej bezpieczne.

- Jeśli wdrożono wiele zasad zgodności, usługa Intune używa najbezpieczniejszych z nich.
