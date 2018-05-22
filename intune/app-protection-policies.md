---
title: Tworzenie i wdrażanie zasad ochrony aplikacji
titleSuffix: Microsoft Intune
description: Dowiedz się, jak tworzyć i przypisywać zasady ochrony aplikacji usługi Microsoft Intune.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f31b2964-e932-4cee-95c4-8d5506966c85
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9132000f5fcf43251bcc1e9b903ea03551e0b85e
ms.sourcegitcommit: af0cc27b05bf0743f7d0970f5f3822f0aab346af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/16/2018
---
# <a name="how-to-create-and-assign-app-protection-policies"></a>Tworzenie i przypisywanie zasad ochrony aplikacji

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Dowiedz się, jak tworzyć i przypisywać zasady ochrony aplikacji usługi Microsoft Intune do użytkowników. W tym temacie opisano również sposób wprowadzania zmian istniejących zasad.

## <a name="before-you-begin"></a>Przed rozpoczęciem

Jeśli szukasz instrukcji dotyczących portalu klasycznego usługi Intune, zobacz, [jak tworzyć zasady ochrony aplikacji](https://docs.microsoft.com/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune).

Zasady ochrony aplikacji można stosować do aplikacji działających na urządzeniach, które mogą być zarządzane przez usługę Intune lub nie. Bardziej szczegółowy opis działania zasad ochrony aplikacji oraz scenariuszy obsługiwanych przy użyciu zasad ochrony aplikacji usługi Intune znajduje się w artykule [What is Microsoft Intune app protection policies](app-protection-policy.md) (Co to są zasady ochrony aplikacji usługi Microsoft Intune).

Jeśli szukasz listy aplikacji z obsługą zasad MAM, zobacz [listę aplikacji z zarządzaniem aplikacjami mobilnymi](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

##  <a name="create-an-app-protection-policy"></a>Tworzenie zasad ochrony aplikacji
1. W obciążeniu **Aplikacje mobilne** wybierz pozycję **Zasady ochrony aplikacji** w sekcji **Zarządzanie**. Ten wybór spowoduje otwarcie szczegółów obszaru **Zasady ochrony aplikacji**, w którym można tworzyć nowe zasady i edytować istniejące.
2. Wybierz pozycję **Dodaj zasady**.

   ![Zrzut ekranu przedstawiający blok „Dodawanie zasad”](./media/app-protection-add-policy.png)

3. Wpisz nazwę zasad, dodaj ich krótki opis i wybierz typ platformy swoich zasad. W razie potrzeby dla każdej platformy można utworzyć większą liczbę zasad.

4. Wybierz pozycję **Aplikacje**, aby otworzyć blok **Aplikacje**, w którym jest wyświetlana lista dostępnych aplikacji. Z listy wybierz jedną lub więcej aplikacji do powiązania z tworzonymi zasadami.
5. Po wybraniu aplikacji wybierz pozycję **Wybierz**, aby zapisać swoje opcje.

    > [!IMPORTANT]
    > W celu utworzenia zasad należy wybrać co najmniej jedną aplikację.

6. Wybierz pozycję **Skonfiguruj wymagane ustawienia** w bloku **Dodawanie zasad**, aby otworzyć obszar **Ustawienia**.

   Istnieją dwie kategorie ustawień zasad, **Przeniesienie danych** i **Dostęp**.  Zasady relokacji danych są stosowane w przypadku przenoszenia danych do i z aplikacji. Zasady dostępu określają, jak użytkownicy końcowi uzyskują dostęp do aplikacji w kontekście roboczym.
   Ustawienia zasad mają wartości domyślne, co ułatwia rozpoczęcie pracy. Jeśli wartości domyślne spełniają Twoje wymagania, nie musisz wprowadzać żadnych zmian.

   > [!TIP]
   > Te ustawienia zasad obowiązują tylko w przypadku stosowania aplikacji w kontekście pracy. Gdy użytkownicy końcowi używają aplikacji do wykonywania zadania osobistego, te zasady nie obowiązują.

7. Wybierz pozycję **OK**, aby zapisać tę konfigurację. Znajdziesz się ponownie w okienku **Dodawanie zasad**. Wybierz pozycję **Utwórz**, aby utworzyć zasady i zapisać ustawienia.
8. Wybierz pozycję **OK**, aby zapisać tę konfigurację. Znajdziesz się ponownie w bloku **Dodawanie zasad**.
9. Wybierz pozycję **Utwórz**, aby utworzyć zasady i zapisać ustawienia.

Po zakończeniu tworzenia zasad zgodnie z opisem w poprzedniej procedurze nie są one wdrażane dla żadnych użytkowników. Aby wdrożyć zasady, zobacz [Wdrażanie zasad dla użytkowników](app-protection-policies.md#deploy-a-policy-to-users).

## <a name="deploy-a-policy-to-users"></a>Wdrażanie zasad dla użytkowników


1. W okienku **Zasady ochrony aplikacji** wybierz zasady.

1. W okienku **Zasady** wybierz pozycję **Przypisania**. Spowoduje to otwarcie okienka **Intune App Protection — przypisania**. Wybierz pozycję **Wybierz grupy do uwzględnienia** w okienku **Przypisania**, aby otworzyć okienko **Wybieranie grup do uwzględnienia**.

   ![Zrzut ekranu okienka Przypisania z wyróżnioną opcją menu Wybierz grupy do uwzględnienia](./media/app-protection-policy-add-users.png)

2.  W okienku **Dodawanie grupy użytkowników** zostanie wyświetlona lista grup użytkowników. Jest to lista wszystkich grup zabezpieczeń w usłudze **Azure Active Directory**. Wybierz grupy użytkowników, których mają dotyczyć te zasady, a następnie wybierz pozycję **Wybierz**. Wybranie pozycji **Wybierz** wdraża zasady dla użytkowników.

    ![Zrzut ekranu przedstawiający okienko Dodawanie grupy użytkowników z listą użytkowników usługi Azure Active Directory](./media/azure-ad-user-group-list.png)

Zasady zostały utworzone i wdrożone dla użytkowników.

Zasady wpływają tylko na użytkowników z przypisanymi licencjami usługi Microsoft Intune. Nie mają one wpływu na użytkowników w wybranej grupie zabezpieczeń, którym nie przypisano licencji usługi Intune.

>[!IMPORTANT]
> Jeśli używasz usługi Intune z programem Configuration Manager do zarządzania urządzeniami, zasady są stosowane tylko do użytkowników należących bezpośrednio do wybranej grupy. Nie mają one wpływu na członków grup podrzędnych zagnieżdżonych w wybranej grupie.

Użytkownicy końcowi mogą pobrać aplikacje ze sklepu App Store lub Google Play. Aby uzyskać więcej informacji, zobacz:
* [Czego można oczekiwać, gdy aplikacja systemu Android jest zarządzana przy użyciu zasad ochrony aplikacji](app-protection-enabled-apps-android.md)
* [Czego można oczekiwać, gdy aplikacja systemu iOS jest zarządzana przy użyciu zasad ochrony aplikacji](app-protection-enabled-apps-ios.md)

##  <a name="change-existing-policies"></a>Zmiana istniejących zasad
Możesz edytować istniejące zasady i zastosować je do użytkowników docelowych. Jednak w przypadku zmiany istniejących zasad użytkownicy zalogowani do aplikacji zobaczą zmiany dopiero po 8 godzinach.

Aby zobaczyć efekt zmian natychmiast, użytkownik końcowy musi wylogować się z aplikacji i ponownie do niej zalogować.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>Aby zmienić listę aplikacji powiązanych z zasadami

1.  W okienku **Zasady ochrony aplikacji** wybierz zasady do zmodyfikowania, aby otworzyć okienko powiązane z właśnie wybranymi zasadami.

2.  W okienku zasad wybierz pozycję **Aplikacje docelowe**, aby otworzyć listę aplikacji.

3.  Usuń lub dodaj aplikacje do listy i wybierz pozycję **Zapisz**, aby zapisać zmiany.

### <a name="to-change-the-list-of-user-groups"></a>Aby zmienić listę grup użytkowników


1.  W okienku **Zasady ochrony aplikacji** wybierz zasady do zmodyfikowania, aby otworzyć okienko powiązane z wybranymi zasadami.

2.  W okienku zasad wybierz pozycję **Przypisania**, aby otworzyć okienko **Intune App Protection — przypisania** zawierające listę bieżących grup użytkowników, których dotyczą dane zasady.

3.  Aby dodać nową grupę użytkowników do zasad, na karcie **Uwzględnianie** wybierz pozycję **Wybierz grupy do uwzględnienia** i wybierz grupę użytkowników. Wybierz pozycję **Wybierz**, aby wdrożyć zasady dla wybranej grupy.

4.  Aby usunąć grupę użytkowników, na karcie **Wykluczanie** wybierz pozycję **Wybierz grupy do wykluczenia** i wybierz grupę użytkowników. Wybierz pozycję **Wybierz**, aby usunąć grupę użytkowników.

### <a name="to-change-policy-settings"></a>Aby zmienić ustawienia zasad

1.  W okienku **Zasady ochrony aplikacji** wybierz zasady do zmodyfikowania, aby otworzyć okienko powiązane z właśnie wybranymi zasadami.

2.  Wybierz pozycję **Ustawienia zasad**, aby otworzyć okienko **Ustawienia zasad**.

3.  Zmień ustawienia i wybierz ikonę **Zapisz**, aby zapisać zmiany.

## <a name="target-app-protection-policies-based-on-device-management-state"></a>Zasady ochrony aplikacji docelowych oparte na stanie zarządzania urządzeniem
W wielu organizacjach jest powszechne korzystanie przez użytkowników końcowych zarówno z urządzeń zarządzanych przez rozwiązanie do zarządzania urządzeniami mobilnymi usługi Intune, takich jak urządzenia należące do firmy, jak i urządzeń niezarządzanych chronionych tylko za pomocą zasad ochrony aplikacji usługi Intune, takich jak urządzenia BYOD.

Ponieważ zasady ochrony aplikacji usługi Intune dotyczą tożsamości użytkownika, ustawienia ochrony dla użytkownika zwyczajowo stosują się zarówno do urządzeń zarejestrowanych (zarządzanych przez rozwiązanie MDM), jak i niezarejestrowanych (niezarządzanych przez rozwiązanie MDM). Dlatego można określić zasady ochrony aplikacji usługi Intune dla zarejestrowanych lub niezarejestrowanych w usłudze Intune urządzeń z systemem iOS lub Android. Jedne zasady ochrony mogą być przeznaczone dla urządzeń niezarządzanych, w przypadku których są wdrożone ścisłe środki ochrony przed utratą danych, a inne zasady mogą być przeznaczone dla urządzeń zarządzanych przez rozwiązanie MDM, w przypadku których środki ochrony przed utratą danych mogą być mniej restrykcyjne. 

Aby utworzyć te zasady, przejdź do zasad **Aplikacje mobilne** > **Ochrona aplikacji** w konsoli usługi Intune i kliknij polecenie **Dodaj zasady**. Istniejące zasady ochrony aplikacji są także dostępne do edycji. Jeśli chcesz stosować zasady ochrony aplikacji do urządzeń zarządzanych i niezarządzanych, potwierdź, że pozycja **Przeznaczone dla wszystkich typów aplikacji** ma domyślną wartość **Tak**. Jeśli chcesz przypisać z większą dokładnością na podstawie stanu zarządzania, określ dla pozycji **Przeznaczone dla wszystkich typów aplikacji** wartość **Nie**. 

> [!NOTE]
> Informacje dotyczące obsługi zasad ochrony aplikacji stosowanych na podstawie stanu zarządzania urządzeniem przez konkretną wersję systemu iOS zawiera artykuł [MAM protection policies targeted based on management state (Zasady ochrony rozwiązania MAM stosowane na podstawie stanu zarządzania)](whats-new.md#mam-protection-policies-targeted-based-on-management-state-).

## <a name="policy-settings"></a>Ustawienia zasad
Aby wyświetlić pełną listę ustawień zasad dla systemów iOS i Android, wybierz jeden z następujących linków:

- [Zasady systemu iOS](app-protection-policy-settings-ios.md)
- [Zasady systemu Android](app-protection-policy-settings-android.md)

## <a name="next-steps"></a>Następne kroki
[Monitorowanie zgodności i stanu użytkownika](app-protection-policies-monitor.md)

### <a name="see-also"></a>Zobacz też
* [Czego można oczekiwać, gdy aplikacja systemu Android jest zarządzana przy użyciu zasad ochrony aplikacji](app-protection-enabled-apps-android.md)
* [Czego można oczekiwać, gdy aplikacja systemu iOS jest zarządzana przy użyciu zasad ochrony aplikacji](app-protection-enabled-apps-ios.md)
