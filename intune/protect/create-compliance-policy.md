---
title: Zasady zgodności urządzeń w usłudze Microsoft Intune na platformie Azure | Microsoft Docs
description: 'Wprowadzenie do następujących zagadnień: korzystanie z zasad zgodności urządzeń, omówienie stanu i poziomów ważności, korzystanie ze stanu InGracePeriod, praca z dostępem warunkowym, obsługa urządzeń bez przypisanych zasad oraz różnice w zgodności między witryną Azure Portal i portalem klasycznym w usłudze Microsoft Intune'
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c8b3a99744f830da3c88473e79bce78c97875d73
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71722634"
---
# <a name="create-a-compliance-policy-in-microsoft-intune"></a>Tworzenie zasad zgodności w usłudze Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Zasady zgodności urządzeń to kluczowa funkcja w przypadku ochrony zasobów organizacji za pomocą usługi Intune. W usłudze Intune możesz utworzyć reguły, które muszą być spełniane przez urządzenia, i ustawienia, które muszą być na nich określone, aby można je było uznać za zgodne, np. minimalna wersja systemu operacyjnego. Jeśli urządzenie nie jest zgodne, możesz wtedy zablokować dostęp do danych i zasobów przy użyciu [dostępu warunkowego](conditional-access.md).

Ponadto możesz wykonywać akcje w przypadku braku zgodności, np. wysłać wiadomość e-mail z powiadomieniem do użytkownika. Omówienie działania zasad zgodności i sposobu ich używania można znaleźć w temacie [Wprowadzenie do zasad zgodności urządzeń](device-compliance-get-started.md).

W tym artykule:

- Znajduje się lista wymagań wstępnych i kroków tworzenia zasad zgodności.
- Przedstawiono sposób przypisywania zasad do grup użytkowników i urządzeń.
- Opisano dodatkowe funkcje, w tym zakresy tagów służące do „filtrowania”, oraz czynności, które można wykonać na niezgodnych urządzeniach.
- Znajduje się lista czasów cykli odświeżania zaewidencjonowania, gdy urządzenia otrzymują aktualizacje profilów.

## <a name="before-you-begin"></a>Przed rozpoczęciem

Aby korzystać z zasad zgodności urządzeń, upewnij się, że spełniono następujące warunki:

- Użyj następujących subskrypcji:

  - Intune
  - Jeśli korzystasz z dostępu warunkowego, potrzebujesz wersji Premium usługi Azure Active Directory (AD). Artykuł [Azure Active Directory — cennik](https://azure.microsoft.com/pricing/details/active-directory/) przedstawia funkcje oferowane w poszczególnych wersjach. Zgodność usługi Intune nie wymaga usługi Azure AD.

- Użyj obsługiwanej platformy:

  - Android
  - Android Enterprise
  - iOS
  - macOS (wersja zapoznawcza)
  - Windows 10
  - Windows 8.1
  - Windows Phone 8,1

- Urządzenia zostały zarejestrowane w usłudze Intune (wymagane na wyświetlenia stanu zgodności)

- Urządzenia zostały zarejestrowane dla jednego użytkownika lub bez użytkownika podstawowego. Urządzenia zarejestrowane dla wielu użytkowników nie są obsługiwane.

## <a name="create-the-policy"></a>Tworzenie zasad

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz pozycję **Zgodność urządzenia**. Do wyboru są następujące opcje:

    - **Omówienie**: powoduje wyświetlenie podsumowania i liczby urządzeń, które są zgodne, nie zostały oceniane itd. Jest również wyświetlana lista zasad i poszczególnych ustawień zasad. Pomocne informacje można znaleźć w temacie [Monitorowanie zasad zgodności urządzeń Intune](compliance-policy-monitor.md).
    - **Zarządzanie**: twórz zasady urządzenia, wysyłaj [powiadomienia](quickstart-send-notification.md) do niezgodnych urządzeń i włączaj [odgradzanie sieci](use-network-locations.md).
    - **Monitorowanie**: sprawdzaj stan zgodności urządzeń na poziomie ustawienia i zasad. Pomocnym zasobem jest artykuł [Monitorowanie zasad zgodności urządzeń Intune](compliance-policy-monitor.md). Możesz również wyświetlać dzienniki i sprawdzać stan agenta zagrożeń urządzenia.
    - **Instalator**: używaj [wbudowanych zasad zgodności](device-compliance-get-started.md#ways-to-deploy-device-compliance-policies), włączaj [Zaawansowaną ochronę przed zagrożeniami (ATP) w usłudze Microsoft Defender](advanced-threat-protection.md), dodawaj [łącznik Mobile Threat Defense](mobile-threat-defense.md) i używaj oprogramowania [Jamf](conditional-access-integrate-jamf.md).

3. Wybierz pozycję **Zasady** > **Utwórz zasady**. Wprowadź następujące właściwości:

    - **Nazwa**: wprowadź opisową nazwę zasad. Nadaj nazwę zasadom, aby można było je później łatwo rozpoznać. Na przykład dobrą nazwą zasad jest **Oznaczanie urządzeń ze zdjętymi zabezpieczeniami systemu iOS jako niezgodnych**.
    - **Opis**: wprowadź opis zasad. To ustawienie jest opcjonalne, ale zalecane.
    - **Platforma**: Wybierz platformę urządzeń. Dostępne opcje:  

       - **Android**
       - **Android enterprise**
       - **iOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 lub nowszy**
       - **Windows 10 lub nowszy**

    - **Ustawienia**: listę i opis poszczególnych typów profilów można znaleźć w następujących artykułach:

        - [Android](compliance-policy-create-android.md)
        - [Android Enterprise](compliance-policy-create-android-for-work.md)
        - [iOS](compliance-policy-create-ios.md)
        - [macOS](compliance-policy-create-mac-os.md)
        - [Windows Phone 8.1, Windows 8.1 lub nowszy](compliance-policy-create-windows-8-1.md)
        - [Windows 10 lub nowszy](compliance-policy-create-windows.md)

4. Po zakończeniu wybierz pozycję **OK**  >  **Utwórz**, aby zapisać zmiany. Zasady zostaną utworzone i wyświetlone na liście. Następnie przypisz zasady do grup.

## <a name="assign-user-groups"></a>Przypisywanie grup użytkowników

Po utworzeniu zasad następnym krokiem jest przypisanie zasad do grup:

1. Wybierz utworzone zasady. Dostęp do istniejących zasad można uzyskać po wybraniu pozycji **Zgodność urządzeń** > **Zasady**.
2. Wybierz zasady > **Przypisania**. Możesz włączyć lub wyłączyć grupy zabezpieczeń usługi Azure Active Directory (AD).
3. Wybierz pozycję **Wybrane grupy**, aby wyświetlić grupy zabezpieczeń usługi Azure AD. Wybierz grupy użytkowników, których mają dotyczyć te zasady > **Zapisz**, aby wdrożyć zasady do użytkowników.

Zasady zostały zastosowane do użytkowników. Urządzenia, którymi posługują się użytkownicy objęci zasadami, będą oceniane pod kątem zgodności.

### <a name="evaluate-how-many-users-are-targeted"></a>Ocenianie, ilu użytkowników jest uwzględnianych

Po przypisaniu zasad możesz również **ocenić**, ilu użytkowników jest uwzględnianych. Ta funkcja oblicza liczbę użytkowników; nie oblicza liczby urządzeń.

1. W usłudze Intune wybierz pozycję **Zgodność urządzenia** > **Zasady**.
2. Wybierz zasady > **Przypisania** > **Oceń**. Zostanie wyświetlony komunikat z informacją o liczbie użytkowników uwzględnionych w tych zasadach.

Jeśli przycisk **Oceń** jest szary, upewnij się, że zasady zostały przypisane do co najmniej jednej grupy.

## <a name="actions-for-noncompliance"></a>Akcje w przypadku niezgodności

W przypadku urządzeń niespełniających zasad zgodności możesz dodać sekwencję akcji do automatycznego zastosowania. Ten harmonogram oznaczania urządzenia jako niezgodnego możesz zmienić (np. oznaczać je po jednym dniu). Możesz również skonfigurować drugą akcję, która wysyła wiadomość e-mail do użytkownika, gdy urządzenie nie jest zgodne.

Sekcja dotycząca [dodawania akcji dla niezgodnych urządzeń](actions-for-noncompliance.md) zawiera więcej informacji, między innymi o tworzeniu wiadomości e-mail z powiadomieniem do użytkowników.

Na przykład używasz funkcji Lokalizacje i dodasz lokalizację w zasadach zgodności. Domyślna akcja w przypadku niezgodności jest stosowana, gdy zostanie wybrana co najmniej jedna lokalizacja. Jeśli urządzenie nie jest połączone z wybranymi lokalizacjami, jest natychmiast uznawane za niezgodne. Użytkownikom można przyznać okres prolongaty, np. jeden dzień.

## <a name="scope-tags"></a>Tagi zakresu

Tagi zakresu to doskonały sposób przypisywania i filtrowania zasad do określonych grup, takich jak pracownicy działu kadr lub sprzedaży albo wszyscy pracownicy w stanie Północna Karolina w USA itd. Po dodaniu ustawień możesz również dodać tag zakresu do zasad zgodności. Pomocnym zasobem jest artykuł [Używanie tagów zakresu do filtrowania zasad](../fundamentals/scope-tags.md).

## <a name="refresh-cycle-times"></a>Czasy cyklu odświeżania

Usługa Intune używa różnych cykli odświeżania w celu sprawdzania dostępności aktualizacji zasad zgodności. Jeśli urządzenie zostało zarejestrowane ostatnio, sprawdzanie odbywa się częściej. Szacowane czasy odświeżania znajdują się w sekcji dotyczącej [cyklów odświeżania zasad i profilów](../configuration/device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).

W dowolnym momencie użytkownicy mogą otwierać aplikację Portal firmy i synchronizować urządzenie, aby natychmiast wyszukiwać aktualizacje zasad.

### <a name="assign-an-ingraceperiod-status"></a>Przypisywanie stanu InGracePeriod

Stan InGracePeriod zasad zgodności jest wartością. Tę wartość określa kombinacja okresu prolongaty urządzenia oraz rzeczywistego stanu urządzenia dla zasad zgodności.

W szczególności gdy urządzenie ma stan niezgodności (NonCompliant) dla przypisanych zasad zgodności oraz:

- do urządzenia nie przypisano okresu prolongaty — przypisaną wartością zasad zgodności jest NonCompliant
- do urządzenia przypisano okres prolongaty, który wygasł — przypisaną wartością zasad zgodności jest NonCompliant
- do urządzenia przypisano okres prolongaty, którego termin przypada w przyszłości — przypisaną wartością zasad zgodności jest InGracePeriod

Poniższa tabela zawiera podsumowanie tych informacji:

|Rzeczywisty stan zgodności|Wartość przypisanego okresu prolongaty|Ostateczny stan zgodności|
|---------|---------|---------|
|NonCompliant |Nie przypisano okresu prolongaty |NonCompliant |
|NonCompliant |Data przeszła|NonCompliant|
|NonCompliant |Data przyszła|InGracePeriod|

Aby uzyskać więcej informacji na temat monitorowania zasad zgodności urządzeń, zobacz [Monitor Intune Device compliance policies](compliance-policy-monitor.md) (Monitorowanie zasad zgodności urządzeń w usłudze Intune).

### <a name="assign-a-resulting-compliance-policy-status"></a>Przypisywanie wynikowego stanu zasad zgodności

Jeśli urządzenie ma wiele zasad zgodności i dla co najmniej dwóch przypisanych zasad zgodności ma ono różne stany zgodności, zostanie przypisany jeden wynikowy stan zgodności. To przypisanie jest oparte na poziomie ważności koncepcyjnej przypisanym do poszczególnych stanów zgodności. Poszczególnym stanom zgodności odpowiadają następujące poziomy ważności:

|Stan  |Ważność  |
|---------|---------|
|Nieznane     |1|
|NotApplicable     |2|
|Zgodny|3|
|InGracePeriod|4|
|NonCompliant|5|
|Error|6|

Jeśli urządzenie ma wiele zasad zgodności, do urządzenia jest przypisywany najwyższy spośród poziomów ważności wszystkich zasad.

Na przykład urządzenie może mieć przypisane trzy rodzaje zasad zgodności: stan Unknown (nieznane, ważność = 1), stan Compliant (zgodne, ważność = 3) i stan InGracePeriod (prolongata, ważność = 4). Stan InGracePeriod ma najwyższy poziom ważności. Dlatego wszystkie trzy zasady mają stan zgodności InGracePeriod.

## <a name="next-steps"></a>Następne kroki

[Monitorowanie zasad](compliance-policy-monitor.md).