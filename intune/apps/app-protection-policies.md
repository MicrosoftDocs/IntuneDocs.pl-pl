---
title: Tworzenie i wdrażanie zasad ochrony aplikacji
titleSuffix: Microsoft Intune
description: W tym temacie opisano, jak tworzyć i przypisywać zasady ochrony aplikacji (APP) usługi Microsoft Intune do użytkowników.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f31b2964-e932-4cee-95c4-8d5506966c85
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a8e105dae43c4e7139c8e44a8c6535baebe31cc4
ms.sourcegitcommit: 0be25b59c8e386f972a855712fc6ec3deccede86
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2019
ms.locfileid: "72585468"
---
# <a name="how-to-create-and-assign-app-protection-policies"></a>Tworzenie i przypisywanie zasad ochrony aplikacji

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Dowiedz się, jak tworzyć i przypisywać zasady ochrony aplikacji usługi Microsoft Intune do użytkowników w organizacji. W tym temacie opisano również sposób wprowadzania zmian istniejących zasad.

## <a name="before-you-begin"></a>Przed rozpoczęciem

Zasady ochrony aplikacji można stosować do aplikacji działających na urządzeniach, które mogą być zarządzane przez usługę Intune lub nie. Aby uzyskać bardziej szczegółowy opis działania zasad ochrony aplikacji oraz informacje dotyczące scenariuszy obsługiwanych przy użyciu zasad ochrony aplikacji usługi Intune, zobacz [What are Microsoft Intune app protection policies? (Co to są zasady ochrony aplikacji usługi Microsoft Intune)](app-protection-policy.md).

Jeśli szukasz listy aplikacji z obsługą zasad MAM, zobacz [listę aplikacji z zarządzaniem aplikacjami mobilnymi](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

Aby uzyskać informacje o dodawaniu aplikacji biznesowych (LOB) Twojej organizacji do usługi Microsoft Intune w celu przygotowania do zastosowania zasad ochrony aplikacji, zobacz [Dodawanie aplikacji do usługi Microsoft Intune](apps-add.md).

Obecnie przepływ procesu tworzenia zasad ochrony aplikacji jest różny na różnych platformach:
- Zasady ochrony aplikacji w systemach iOS/iPadOS i Android
- Zasady ochrony aplikacji w systemie Windows 10

## <a name="app-protection-policies-for-iosipados-and-android-apps"></a>Zasady ochrony aplikacji w systemach iOS/iPadOS i Android

Aby utworzyć zasady ochrony aplikacji w systemach iOS/iPadOS i Android, należy postępować zgodnie ze nowoczesnym przepływem procesu usługi Intune, który powoduje utworzenie nowych zasad ochrony aplikacji.

### <a name="create-an-iosipados-or-android-app-protection-policy"></a>Tworzenie zasad ochrony aplikacji w systemie iOS/iPadOS lub Android
1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. W portalu usługi Intune wybierz pozycję **Aplikacje klienckie** > **Zasady ochrony aplikacji**. Ten wybór spowoduje otwarcie szczegółów obszaru **Zasady ochrony aplikacji**, w którym można tworzyć nowe zasady i edytować istniejące.
3. Wybierz pozycję **Utwórz zasady**, a następnie wybierz system **iOS/iPadOS** lub **Android**. Zostanie wyświetlony blok **Tworzenie zasad**.
4. Na stronie **Podstawowe** dodaj następujące wartości:

    | Wartość | Opis |
    |--------------|------------------------------------------------|
    | Nazwa | Nazwa zasad ochrony aplikacji. |
    | Opis | [Opcjonalnie] Opis zasad ochrony aplikacji. |


    Wartość **Platforma** jest ustawiana na podstawie wybranych wyżej opcji.

    ![Zrzut ekranu przedstawiający stronę Podstawowe w bloku Tworzenie zasad](~/apps/media/app-protection-policies/app-protection-add-policies-01.png)

5. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Aplikacje**.<br>
    Strona **Aplikacje** umożliwia wybranie sposobu zastosowania zasad do aplikacji na różnych urządzeniach. Należy dodać co najmniej jedną aplikację.<p>
    
    | Wartość/opcja | Opis |
    |-------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Jako docelowe ustaw aplikacje na wszystkich typach urządzeń | Ta opcja umożliwia zastosowanie zasad do aplikacji na urządzeniach w dowolnym stanie zarządzania. Wybierz pozycję **Nie**, aby zastosować zasady do aplikacji na konkretnych typach urządzeń. |
    |     Typy urządzeń | Dzięki tej opcji można określić, czy zasady mają zastosowanie do urządzeń zarządzanych przez MDM, czy urządzeń niezarządzanych. W przypadku zasad aplikacji systemu iOS można wybierać spośród urządzeń **Niezarządzanych** i **Zarządzanych**. W przypadku zasad aplikacji systemu Android do wyboru są opcje **Niezarządzane**, **Administrator urządzeń z systemem Android** i **System Android dla firm**.  |
    | Aplikacje publiczne | Kliknij pozycję **Wybierz aplikacje publiczne**, aby wybrać aplikacje docelowe. |
    | Aplikacje niestandardowe | Kliknij pozycję **Wybierz aplikacje niestandardowe**, aby wybrać docelowe aplikacje niestandardowe na podstawie identyfikatora pakietu. |
    
    Wybrane aplikacje będą widoczne na liście aplikacji publicznych i niestandardowych. 
6. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Ochrona danych**.<br>
    Ta strona udostępnia ustawienia funkcji ochrony przed utratą danych ograniczające działania, takie jak wycinanie, kopiowanie, wklejanie i zapisywanie pod nową nazwą. Te ustawienia określają, jak użytkownicy używają danych w aplikacjach, do których mają zastosowanie zasady ochrony.

    **Ustawienia ochrony danych**:<br>
    - **Ochrona danych w systemie iOS/iPadOS** — aby uzyskać więcej informacji, zobacz [Ustawienia zasad ochrony aplikacji dla systemu iOS — ochrona danych](~/apps/app-protection-policy-settings-ios.md#data-protection).
    - **Ochrona danych w systemie Android** — aby uzyskać więcej informacji, zobacz [Ustawienia zasad ochrony aplikacji dla systemu Android — ochrona danych](~/apps/app-protection-policy-settings-android.md#data-protection).

7. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Wymagania dotyczące dostępu**.<br>
    Ta strona zawiera ustawienia pozwalające skonfigurować wymagania dotyczące numeru PIN i poświadczeń, które użytkownicy muszą spełnić, aby uzyskać dostęp do aplikacji w kontekście służbowym. 
 
    **Ustawienia wymagań dotyczących dostępu**:<br>
    - **Wymagania dotyczące dostępu w systemie iOS/iPadOS** — aby uzyskać więcej informacji, zobacz [Ustawienia zasad ochrony aplikacji dla systemu iOS — wymagania dotyczące dostępu](~/apps/app-protection-policy-settings-ios.md#access-requirements).
    - **Wymagania dotyczące dostępu w systemie Android** — aby uzyskać więcej informacji, zobacz [Ustawienia zasad ochrony aplikacji dla systemu Android — wymagania dotyczące dostępu](~/apps/app-protection-policy-settings-android.md#access-requirements).

8. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Uruchamianie warunkowe**.<br>
    Ta strona zawiera ustawienia umożliwiające skonfigurowanie wymagań dotyczących zabezpieczeń logowania na potrzeby zasad ochrony aplikacji. Wybierz pozycję w kolumnie **Ustawienie** i w kolumnie **Wartość** wprowadź wartość, która będzie wymagana od użytkowników, aby mogli zalogować się do aplikacji firmowej. Następnie w kolumnie **Akcja** wybierz akcję, którą chcesz wykonać, jeśli użytkownicy nie spełnili Twoich wymagań. W niektórych przypadkach dla pojedynczego ustawienia można skonfigurować wiele akcji.

    **Ustawienia uruchamiania warunkowego**:<br>
    - **Uruchamianie warunkowe w systemie iOS/iPadOS** — aby uzyskać więcej informacji, zobacz [Ustawienia zasad ochrony aplikacji dla systemu iOS — uruchamianie warunkowe](~/apps/app-protection-policy-settings-ios.md#conditional-launch).
    - **Uruchamianie warunkowe w systemie Android** — aby uzyskać więcej informacji, zobacz [Ustawienia zasad ochrony aplikacji dla systemu Android — uruchamianie warunkowe](~/apps/app-protection-policy-settings-android.md#conditional-launch).

7. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Przypisania**.<br>
   Strona **Przypisania** umożliwia przypisywanie zasad ochrony aplikacji do grup użytkowników. 
8. Kliknij przycisk **Dalej: Przeglądanie + tworzenie**, aby przejrzeć wartości i ustawienia wprowadzone dla tych zasad ochrony aplikacji.
9. Gdy skończysz, kliknij pozycję **Utwórz**, aby utworzyć zasady ochrony aplikacji w usłudze Intune. 

## <a name="app-protection-policies-for-windows-10-apps"></a>Zasady ochrony aplikacji w systemie Windows 10

Tworzenie zasad ochrony aplikacji dla systemu Windows 10 odbywa się zgodnie z klasycznym przepływem procesu usługi Intune.

### <a name="create-a-windows-10-app-protection-policy"></a>Tworzenie zasad ochrony aplikacji dla systemu Windows 10
1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. W portalu usługi Intune wybierz pozycję **Aplikacje klienckie** > **Zasady ochrony aplikacji**. Ten wybór spowoduje otwarcie szczegółów obszaru **Zasady ochrony aplikacji**, w którym można tworzyć nowe zasady i edytować istniejące.
3. Wybierz pozycję **Utwórz zasady**.

    <img alt="Screenshot of the 'Create policy' blade for Windows 10" src="~/apps/media/app-protection-policies/app-protection-add-policy.png" width="350">

4. Określ nazwę zasad, dodaj ich krótki opis i wybierz typ platformy swoich zasad. Dla każdej platformy można utworzyć większą liczbę zasad.

4. Możesz wybrać opcję **Dotyczy wszystkich typów aplikacji**. Ta opcja umożliwia zastosowanie zasad do aplikacji na urządzeniach w dowolnym stanie zarządzania. W przypadku rozwiązywania konfliktów zasad to ustawienie zostanie zastąpione, jeśli użytkownik ma zasady przeznaczone dla określonego stanu zarządzania. Aby uzyskać więcej informacji, zobacz [Zasady ochrony aplikacji docelowych oparte na stanie zarządzania urządzeniem](~/apps/app-protection-policies.md#target-app-protection-policies-based-on-device-management-state).

5. Wybierz pozycję **Aplikacje**, aby otworzyć blok **Aplikacje**, w którym jest wyświetlana lista dostępnych aplikacji. Z listy wybierz jedną lub więcej aplikacji do powiązania z tworzonymi zasadami. W celu utworzenia zasad wybierz co najmniej jedną aplikację.  

6. Po wybraniu aplikacji wybierz pozycję **Wybierz**, aby zapisać swoje opcje.

7. W bloku **Dodawanie zasad** wybierz pozycję **Skonfiguruj wymagane ustawienia**, aby otworzyć obszar **Ustawienia**.

   Istnieją trzy kategorie ustawień zasad:
   - **Ochrona danych** — ta grupa obejmuje kontrolki ochrony przed utratą danych ograniczające działania takie jak wycinanie, kopiowanie, wklejanie i zapisywanie pod nową nazwą. Te ustawienia określają, jak użytkownicy używają danych w aplikacjach.
   - **Wymagania dotyczące dostępu** — ta grupa zawiera opcje numeru PIN dla poszczególnych aplikacji, które określają, w jaki sposób użytkownik uzyskuje dostęp do aplikacji w kontekście służbowym.  
   - **Uruchamianie warunkowe** — ta grupa zawiera ustawienia takie jak minimalna wersja systemu operacyjnego, wykrywanie urządzeń ze zdjętymi zabezpieczeniami systemu i z dostępem do konta root oraz okresy prolongaty trybu offline.

   Ustawienia zasad mają wartości domyślne, co ułatwia rozpoczęcie pracy. Jeśli wartości domyślne spełniają Twoje wymagania, nie musisz wprowadzać żadnych zmian.

   > [!TIP]
   > Te ustawienia zasad obowiązują tylko w przypadku stosowania aplikacji w kontekście pracy. Gdy użytkownicy końcowi używają aplikacji do wykonywania zadania osobistego, te zasady nie obowiązują. Należy pamiętać, że nowo utworzony plik jest uznawany za plik osobisty. 

8. Wybierz pozycję **OK**, aby zapisać tę konfigurację. Znajdziesz się ponownie w bloku **Dodawanie zasad**.
9. Wybierz pozycję **Utwórz**, aby utworzyć zasady i zapisać ustawienia.

Nowo tworzone zasady systemu Windows 10 nie są przypisywane do jakichkolwiek użytkowników, dopóki nie zostanie to wyraźnie zrobione. Aby uzyskać informacje dotyczące przypisywania zasad systemu Windows 10, zobacz [Przypisywanie zasad systemu Windows 10 do użytkowników](~/apps/app-protection-policies.md#assign-a-windows-10-policy-to-users)

### <a name="assign-a-windows-10-policy-to-users"></a>Przypisywanie zasad systemu Windows 10 do użytkowników 

1. W okienku **Zasady ochrony aplikacji** wybierz zasady.

2. W okienku ***Intune App Protection** wybierz pozycję **Przypisania**, aby otworzyć okienko **Intune App Protection — przypisania**. Na karcie *Dołączanie* wybierz pozycję **Wybierz grupy do uwzględnienia**. 

   ![Zrzut ekranu okienka Przypisania z menu Wybierz grupy do uwzględnienia](./media/app-protection-policies/app-protection-policy-add-users.png)

3. Zostanie wyświetlona lista wszystkich grup zabezpieczeń w usłudze **Azure Active Directory**. Wybierz grupy użytkowników, których mają dotyczyć te zasady, a następnie wybierz pozycję **Wybierz**. 

    ![Zrzut ekranu przedstawiający okienko Dodawanie grupy użytkowników z listą użytkowników usługi Azure AD](./media/app-protection-policies/azure-ad-user-group-list.png)

4. Po dołączeniu i wykluczeniu grup wybierz pozycję **Zapisz**, aby zapisać konfigurację i wdrożyć zasady do użytkowników. Jeśli przed zapisaniem konfiguracji wybierzesz pozycję **Odrzuć**, wszystkie zmiany wprowadzone na kartach *Dołączanie* i *Wykluczanie* zostaną odrzucone.   
 
     ![Zrzut ekranu przedstawiający opcje zapisywania i odrzucania](./media/app-protection-policies/save-assignment.png)
  
Zasady zostały utworzone i wdrożone dla użytkowników.

Zasady wpływają tylko na użytkowników z przypisanymi licencjami usługi Microsoft Intune. Nie mają one wpływu na użytkowników w wybranej grupie zabezpieczeń, którym nie przypisano licencji usługi Intune.

>[!IMPORTANT]
> Jeśli używasz usługi Intune z programem Configuration Manager do zarządzania urządzeniami, zasady są stosowane tylko do użytkowników należących bezpośrednio do wybranej grupy. Nie mają one wpływu na członków grup podrzędnych zagnieżdżonych w wybranej grupie.

Użytkownicy końcowi mogą pobrać aplikacje ze sklepu App Store lub Google Play. Aby uzyskać więcej informacji, zobacz:
* [Czego można oczekiwać, gdy aplikacja systemu Android jest zarządzana przy użyciu zasad ochrony aplikacji](../fundamentals/end-user-mam-apps-android.md)
* [Czego można oczekiwać, gdy aplikacja systemu iOS jest zarządzana przy użyciu zasad ochrony aplikacji](../fundamentals/end-user-mam-apps-ios.md)

### <a name="change-existing-windows-10-policies"></a>Zmiana istniejących zasad systemu Windows 10
Możesz edytować istniejące zasady i zastosować je do użytkowników docelowych. Jednak w przypadku zmiany istniejących zasad użytkownicy zalogowani do aplikacji zobaczą zmiany dopiero po 8 godzinach.

Aby zobaczyć efekt zmian natychmiast, użytkownik końcowy musi wylogować się z aplikacji i ponownie do niej zalogować.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>Aby zmienić listę aplikacji powiązanych z zasadami

1. W okienku **Zasady ochrony aplikacji** wybierz zasady, które chcesz zmienić.

2. W okienku *Intune App Protection* wybierz pozycję **Aplikacje docelowe**, aby otworzyć listę aplikacji.

3. Usuń aplikacje z listy lub dodaj je do niej, a następnie wybierz ikonę **Zapisz**, aby zapisać zmiany.

#### <a name="to-change-the-list-of-user-groups"></a>Aby zmienić listę grup użytkowników

1. W okienku **Zasady ochrony aplikacji** wybierz zasady, które chcesz zmienić.

2. W okienku *Intune App Protection* wybierz pozycję **Przypisania**, aby otworzyć okienko **Intune App Protection — przypisania** zawierające listę bieżących grup użytkowników, których dotyczą dane zasady.

3. Aby dodać nową grupę użytkowników do zasad, na karcie *Uwzględnianie* wybierz pozycję **Wybierz grupy do uwzględnienia** i wybierz grupę użytkowników. Wybierz pozycję **Wybierz**, aby dodać grupę. 

4. Aby wykluczyć grupę użytkowników, na karcie *Wykluczanie* wybierz pozycję **Wybierz grupy do wykluczenia** i wybierz grupę użytkowników. Wybierz pozycję **Wybierz**, aby usunąć grupę użytkowników.  

5. Aby usunąć grupy dodane wcześniej, na karcie *Dołączanie* lub *Wykluczanie* wybierz wielokropek (...) i wybierz pozycję **Usuń**. 

5. Gdy zmiany przypisań będą gotowe, wybierz pozycję **Zapisz**, aby zapisać konfigurację i wdrożyć zasady do zestawu nowych użytkowników. Jeśli przed zapisaniem konfiguracji wybierzesz pozycję **Odrzuć**, wszystkie zmiany wprowadzone na kartach *Dołączanie* i *Wykluczanie* zostaną odrzucone.

### <a name="to-change-windows-10-policy-settings"></a>Aby zmienić ustawienia zasad systemu Windows 10

1. W okienku **Zasady ochrony aplikacji** wybierz zasady, które chcesz zmienić.

2. W okienku *Intune App Protection* wybierz pozycję **Właściwości**, aby otworzyć listę obszarów ustawień, które możesz edytować. 

3. Wybierz obszar ustawień zawierający ustawienia, które chcesz zmienić, takie jak **Relokacja danych** lub **Wymagania dotyczące dostępu**. Następnie zmień te ustawienia na nowe wartości.

4. Wybierz ikonę **Zapisz**, aby zapisać zmiany. Powtórz te czynności, aby wybrać obszar ustawień, zmodyfikować go i zapisać zmiany, dopóki nie zostaną zakończone wszystkie zmiany. Następnie możesz zamknąć okienko *Intune App Protection — właściwości*. 

## <a name="target-app-protection-policies-based-on-device-management-state"></a>Zasady ochrony aplikacji docelowych oparte na stanie zarządzania urządzeniem
W wielu organizacjach powszechne jest zezwalanie na korzystanie przez użytkowników końcowych zarówno z urządzeń zarządzanych przez rozwiązanie do zarządzania urządzeniami mobilnymi usługi Intune, takich jak urządzenia należące do firmy, jak i z urządzeń niezarządzanych, które są chronione tylko za pomocą zasad ochrony aplikacji usługi Intune. Urządzenia niezarządzane są często określane jako urządzenia BYOD.

Ponieważ zasady ochrony aplikacji usługi Intune dotyczą tożsamości użytkownika, ustawienia ochrony dla użytkownika można stosować zarówno do urządzeń zarejestrowanych (zarządzanych przez rozwiązanie MDM), jak i niezarejestrowanych (niezarządzanych przez rozwiązanie MDM). W związku z tym można określić zasady ochrony aplikacji usługi Intune dla zarejestrowanych lub niezarejestrowanych w usłudze Intune urządzeń z systemem iOS lub Android. Jedne zasady ochrony mogą być przeznaczone dla urządzeń niezarządzanych, w przypadku których są wdrożone ścisłe środki ochrony przed utratą danych, a inne zasady mogą być przeznaczone dla urządzeń zarządzanych przez rozwiązanie MDM, w przypadku których środki ochrony przed utratą danych mogą być mniej restrykcyjne. Aby uzyskać więcej informacji o działaniu zasad w przypadku urządzeń osobistych z systemem Android Enterprise, zobacz temat [Zasady ochrony aplikacji i profile służbowe](android-deployment-scenarios-app-protection-work-profiles.md).

Aby utworzyć te zasady, przejdź do zasad **Aplikacje klienckie** > **Ochrona aplikacji** w konsoli usługi Intune, a następnie kliknij pozycję **Utwórz zasady**. Istniejące zasady ochrony aplikacji są także dostępne do edycji. Aby zastosować zasady ochrony aplikacji zarówno do urządzeń zarządzanych, jak i niezarządzanych, przejdź na stronę **Aplikacje** i upewnij się, że opcja **Jako docelowe ustaw aplikacje na wszystkich typach urządzeń** ma domyślną wartość **Tak**. Jeśli chcesz przypisać z większą dokładnością na podstawie stanu zarządzania, ustaw opcję **Jako docelowe ustaw aplikacje na wszystkich typach urządzeń** na wartość **Nie**. 

![Zrzut ekranu przedstawiający blok Dodawanie zasad z pozycją Dotyczy wszystkich typów aplikacji](./media/app-protection-policies/app-protection-policies-target-all.png)

### <a name="app-types"></a>Typy aplikacji

- **Aplikacje na urządzeniach niezarządzanych**: Urządzenia niezarządzane to urządzenia, na których nie wykryto zarządzania urządzeniami mobilnymi usługi Intune. Obejmuje to dostawców rozwiązań do zarządzania urządzeniami mobilnymi innych firm.
- **Aplikacje na urządzeniach zarządzanych przez usługę Intune**: Urządzenia zarządzane są zarządzane przez zarządzanie urządzeniami mobilnymi usługi Intune.
- **Aplikacje w profilu służbowym systemu Android**: Urządzenia zarządzane, które zostały zarejestrowane jako urządzenia profilu służbowego systemu Android Enterprise.

> Należy pamiętać, że w przypadku urządzeń z systemem Android zostanie wyświetlony monit o zainstalowanie aplikacji Intune — Portal firmy niezależnie od tego, który typ aplikacji wybrano. Jeśli na przykład wybierzesz pozycję „Aplikacje na urządzeniach zarządzanych przez usługę Intune”, nadal będą wyświetlane monity dla użytkowników z niezarządzanymi urządzeniami z systemem Android.

W przypadku systemu iOS wymagane są dodatkowe ustawienia konfiguracji aplikacji przeznaczone dla ustawień zasad ochrony aplikacji na urządzeniach zarejestrowanych w usłudze Intune:

- Ustawienie **IntuneMAMUPN** musi być skonfigurowane dla wszystkich aplikacji zarządzanych przez oprogramowanie MDM. Aby uzyskać więcej informacji, zobacz [Jak zarządzać przesyłaniem danych między aplikacjami systemu iOS w usłudze Microsoft Intune](data-transfer-between-apps-manage-ios.md#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm).
- Ustawienie **IntuneMAMDeviceID** musi być skonfigurowane dla wszystkich aplikacji innych firm lub aplikacji biznesowych zarządzanych przez rozwiązanie MDM. Ustawienie **IntuneMAMDeviceID** powinno zostać skonfigurowane do tokenu identyfikacyjnego urządzenia. Na przykład `key=IntuneMAMDeviceID, value={{deviceID}}`. Aby uzyskać więcej informacji, zobacz [Dodawanie zasad konfiguracji aplikacji dla zarządzanych urządzeń z systemem iOS](app-configuration-policies-use-ios.md).
- Jeśli skonfigurowane zostanie tylko ustawienie **IntuneMAMDeviceID**, zasady ochrony aplikacji usługi Intune uznają urządzenie za niezarządzane.

> [!NOTE]
> Informacje dotyczące obsługi zasad ochrony aplikacji stosowanych na podstawie stanu zarządzania urządzeniem przez konkretną wersję systemu iOS zawiera artykuł [MAM protection policies targeted based on management state (Zasady ochrony rozwiązania MAM stosowane na podstawie stanu zarządzania)](../fundamentals/whats-new-archive.md#mam-protection-policies-targeted-based-on-management-state-).

## <a name="policy-settings"></a>Ustawienia zasad
Aby wyświetlić pełną listę ustawień zasad dla systemów iOS i Android, wybierz jeden z następujących linków:

- [Zasady systemu iOS](app-protection-policy-settings-ios.md)
- [Zasady systemu Android](app-protection-policy-settings-android.md)

## <a name="next-steps"></a>Następne kroki
[Monitorowanie zgodności i stanu użytkownika](app-protection-policies-monitor.md)

## <a name="see-also"></a>Zobacz także
* [Czego można oczekiwać, gdy aplikacja systemu Android jest zarządzana przy użyciu zasad ochrony aplikacji](../fundamentals/end-user-mam-apps-android.md)
* [Czego można oczekiwać, gdy aplikacja systemu iOS jest zarządzana przy użyciu zasad ochrony aplikacji](../fundamentals/end-user-mam-apps-ios.md)
