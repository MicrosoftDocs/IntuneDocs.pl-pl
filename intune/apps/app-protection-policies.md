---
title: Tworzenie i wdrażanie zasad ochrony aplikacji
titleSuffix: Microsoft Intune
description: W tym temacie opisano, jak tworzyć i przypisywać zasady ochrony aplikacji (APP) usługi Microsoft Intune do użytkowników.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f31b2964-e932-4cee-95c4-8d5506966c85
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4958a35f3a83fecffacf26421e4c1d797f45ddaa
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940391"
---
# <a name="how-to-create-and-assign-app-protection-policies"></a>Tworzenie i przypisywanie zasad ochrony aplikacji

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Dowiedz się, jak tworzyć i przypisywać zasady ochrony aplikacji usługi Microsoft Intune do użytkowników. W tym temacie opisano również sposób wprowadzania zmian istniejących zasad.

## <a name="before-you-begin"></a>Przed rozpoczęciem

Zasady ochrony aplikacji można stosować do aplikacji działających na urządzeniach, które mogą być zarządzane przez usługę Intune lub nie. Aby uzyskać bardziej szczegółowy opis działania zasad ochrony aplikacji oraz informacje dotyczące scenariuszy obsługiwanych przy użyciu zasad ochrony aplikacji usługi Intune, zobacz [What are Microsoft Intune app protection policies? (Co to są zasady ochrony aplikacji usługi Microsoft Intune)](app-protection-policy.md).

Jeśli szukasz listy aplikacji z obsługą zasad MAM, zobacz [listę aplikacji z zarządzaniem aplikacjami mobilnymi](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

Aby uzyskać informacje o dodawaniu aplikacji biznesowych (LOB) Twojej organizacji do usługi Microsoft Intune w celu przygotowania do zastosowania zasad ochrony aplikacji, zobacz [Dodawanie aplikacji do usługi Microsoft Intune](apps-add.md).

## <a name="create-an-app-protection-policy"></a>Tworzenie zasad ochrony aplikacji
1. W portalu usługi Intune przejdź do obszaru **Aplikacje klienckie** > **Zasady ochrony aplikacji**. Ten wybór spowoduje otwarcie szczegółów obszaru **Zasady ochrony aplikacji**, w którym można tworzyć nowe zasady i edytować istniejące.
2. Wybierz pozycję **Utwórz zasady**.

   ![Zrzut ekranu przedstawiający blok „Dodawanie zasad”](./media/app-protection-policies/app-protection-add-policy.png)

3. Określ nazwę zasad, dodaj ich krótki opis i wybierz typ platformy swoich zasad. Dla każdej platformy można utworzyć większą liczbę zasad.

4. Wybierz pozycję **Aplikacje**, aby otworzyć blok **Aplikacje**, w którym jest wyświetlana lista dostępnych aplikacji. Z listy wybierz jedną lub więcej aplikacji do powiązania z tworzonymi zasadami. W celu utworzenia zasad wybierz co najmniej jedną aplikację.  

5. Po wybraniu aplikacji wybierz pozycję **Wybierz**, aby zapisać swoje opcje.

6. W bloku **Dodawanie zasad** wybierz pozycję **Skonfiguruj wymagane ustawienia**, aby otworzyć obszar **Ustawienia**.

   Istnieją trzy kategorie ustawień zasad:
   - **Ochrona danych** — ta grupa obejmuje kontrolki ochrony przed utratą danych ograniczające działania takie jak wycinanie, kopiowanie, wklejanie i zapisywanie pod nową nazwą. Te ustawienia określają, jak użytkownicy używają danych w aplikacjach.
   - **Wymagania dotyczące dostępu** — ta grupa zawiera opcje numeru PIN dla poszczególnych aplikacji, które określają, w jaki sposób użytkownik uzyskuje dostęp do aplikacji w kontekście służbowym.  
   - **Uruchamianie warunkowe** — ta grupa zawiera ustawienia takie jak minimalna wersja systemu operacyjnego, wykrywanie urządzeń ze zdjętymi zabezpieczeniami systemu i z dostępem do konta root oraz okresy prolongaty trybu offline.

   Ustawienia zasad mają wartości domyślne, co ułatwia rozpoczęcie pracy. Jeśli wartości domyślne spełniają Twoje wymagania, nie musisz wprowadzać żadnych zmian.

   > [!TIP]
   > Te ustawienia zasad obowiązują tylko w przypadku stosowania aplikacji w kontekście pracy. Gdy użytkownicy końcowi używają aplikacji do wykonywania zadania osobistego, te zasady nie obowiązują. Należy pamiętać, że nowo utworzony plik jest uznawany za plik osobisty. 

7. Wybierz pozycję **OK**, aby zapisać tę konfigurację. Znajdziesz się ponownie w bloku **Dodawanie zasad**.
8. Wybierz pozycję **Utwórz**, aby utworzyć zasady i zapisać ustawienia.

Nowe tworzone zasady nie zostaną wdrożone dla żadnych użytkowników, dopóki tego jawnie to zrobisz. Aby wdrożyć zasady, zobacz [Wdrażanie zasad dla użytkowników](app-protection-policies.md#deploy-a-policy-to-users).

## <a name="deploy-a-policy-to-users"></a>Wdrażanie zasad dla użytkowników

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

## <a name="change-existing-policies"></a>Zmiana istniejących zasad
Możesz edytować istniejące zasady i zastosować je do użytkowników docelowych. Jednak w przypadku zmiany istniejących zasad użytkownicy zalogowani do aplikacji zobaczą zmiany dopiero po 8 godzinach.

Aby zobaczyć efekt zmian natychmiast, użytkownik końcowy musi wylogować się z aplikacji i ponownie do niej zalogować.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>Aby zmienić listę aplikacji powiązanych z zasadami

1. W okienku **Zasady ochrony aplikacji** wybierz zasady, które chcesz zmienić.

2. W okienku *Intune App Protection* wybierz pozycję **Aplikacje docelowe**, aby otworzyć listę aplikacji.

3. Usuń aplikacje z listy lub dodaj je do niej, a następnie wybierz ikonę **Zapisz**, aby zapisać zmiany.

### <a name="to-change-the-list-of-user-groups"></a>Aby zmienić listę grup użytkowników


1. W okienku **Zasady ochrony aplikacji** wybierz zasady, które chcesz zmienić.

2. W okienku *Intune App Protection* wybierz pozycję **Przypisania**, aby otworzyć okienko **Intune App Protection — przypisania** zawierające listę bieżących grup użytkowników, których dotyczą dane zasady.

3. Aby dodać nową grupę użytkowników do zasad, na karcie *Uwzględnianie* wybierz pozycję **Wybierz grupy do uwzględnienia** i wybierz grupę użytkowników. Wybierz pozycję **Wybierz**, aby dodać grupę. 

4. Aby wykluczyć grupę użytkowników, na karcie *Wykluczanie* wybierz pozycję **Wybierz grupy do wykluczenia** i wybierz grupę użytkowników. Wybierz pozycję **Wybierz**, aby usunąć grupę użytkowników.  

5. Aby usunąć grupy dodane wcześniej, na karcie *Dołączanie* lub *Wykluczanie* wybierz wielokropek (...) i wybierz pozycję **Usuń**. 

5. Gdy zmiany przypisań będą gotowe, wybierz pozycję **Zapisz**, aby zapisać konfigurację i wdrożyć zasady do zestawu nowych użytkowników. Jeśli przed zapisaniem konfiguracji wybierzesz pozycję **Odrzuć**, wszystkie zmiany wprowadzone na kartach *Dołączanie* i *Wykluczanie* zostaną odrzucone.

### <a name="to-change-policy-settings"></a>Aby zmienić ustawienia zasad

1. W okienku **Zasady ochrony aplikacji** wybierz zasady, które chcesz zmienić.

2. W okienku *Intune App Protection* wybierz pozycję **Właściwości**, aby otworzyć listę obszarów ustawień, które możesz edytować. 

3. Wybierz obszar ustawień zawierający ustawienia, które chcesz zmienić, takie jak **Relokacja danych** lub **Wymagania dotyczące dostępu**. Następnie zmień te ustawienia na nowe wartości.

4. Wybierz ikonę **Zapisz**, aby zapisać zmiany. Powtórz te czynności, aby wybrać obszar ustawień, zmodyfikować go i zapisać zmiany, dopóki nie zostaną zakończone wszystkie zmiany. Następnie możesz zamknąć okienko *Intune App Protection — właściwości*. 

## <a name="target-app-protection-policies-based-on-device-management-state"></a>Zasady ochrony aplikacji docelowych oparte na stanie zarządzania urządzeniem
W wielu organizacjach powszechne jest zezwalanie na korzystanie przez użytkowników końcowych zarówno z urządzeń zarządzanych przez rozwiązanie do zarządzania urządzeniami mobilnymi usługi Intune, takich jak urządzenia należące do firmy, jak i z urządzeń niezarządzanych, które są chronione tylko za pomocą zasad ochrony aplikacji usługi Intune. Urządzenia niezarządzane są często określane jako urządzenia BYOD.

Ponieważ zasady ochrony aplikacji usługi Intune dotyczą tożsamości użytkownika, ustawienia ochrony dla użytkownika można stosować zarówno do urządzeń zarejestrowanych (zarządzanych przez rozwiązanie MDM), jak i niezarejestrowanych (niezarządzanych przez rozwiązanie MDM). W związku z tym można określić zasady ochrony aplikacji usługi Intune dla zarejestrowanych lub niezarejestrowanych w usłudze Intune urządzeń z systemem iOS lub Android. Jedne zasady ochrony mogą być przeznaczone dla urządzeń niezarządzanych, w przypadku których są wdrożone ścisłe środki ochrony przed utratą danych, a inne zasady mogą być przeznaczone dla urządzeń zarządzanych przez rozwiązanie MDM, w przypadku których środki ochrony przed utratą danych mogą być mniej restrykcyjne. Aby uzyskać więcej informacji na temat tego, jak to wygląda w przypadku urządzeń osobistych z systemem Android Enterprise, zobacz temat [Zasady ochrony aplikacji i profile służbowe na urządzeniach z systemem Android Enterprise w usłudze Intune](android-deployment-scenarios-app-protection-work-profiles.md).

Aby utworzyć te zasady, przejdź do zasad **Aplikacje klienckie** > **Ochrona aplikacji** w konsoli usługi Intune, a następnie kliknij pozycję **Utwórz zasady**. Istniejące zasady ochrony aplikacji są także dostępne do edycji. Aby zastosować zasady ochrony aplikacji do zarówno do urządzeń zarządzanych, jak i niezarządzanych, potwierdź, że pozycja **Przeznaczone dla wszystkich typów aplikacji** ma domyślną wartość **Tak**. Jeśli chcesz przypisać z większą dokładnością na podstawie stanu zarządzania, ustaw pozycję **Przeznaczone dla wszystkich typów aplikacji** na wartość **Nie**. 

![Zrzut ekranu przedstawiający blok Dodawanie zasad z pozycją Dotyczy wszystkich typów aplikacji](./media/app-protection-policies/app-protection-policies-target-all.png)

### <a name="app-types"></a>Typy aplikacji

- **Aplikacje na urządzeniach niezarządzanych**: Urządzenia niezarządzane to urządzenia, na których nie wykryto zarządzania urządzeniami mobilnymi usługi Intune. Obejmuje to dostawców rozwiązań do zarządzania urządzeniami mobilnymi innych firm.
- **Aplikacje na urządzeniach zarządzanych przez usługę Intune**: Urządzenia zarządzane są zarządzane przez zarządzanie urządzeniami mobilnymi usługi Intune.
- **Aplikacje w profilu służbowym systemu Android**: Urządzenia zarządzane, które zostały zarejestrowane jako urządzenia profilu służbowego systemu Android Enterprise.

> Należy pamiętać, że w przypadku urządzeń z systemem Android zostanie wyświetlony monit o zainstalowanie aplikacji Intune — Portal firmy niezależnie od tego, który typ aplikacji został wybrany. Jeśli na przykład wybierzesz pozycję „Aplikacje na urządzeniach zarządzanych przez usługę Intune”, nadal będą wyświetlane monity dla użytkowników z niezarządzanymi urządzeniami z systemem Android.

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