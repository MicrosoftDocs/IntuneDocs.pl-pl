---
title: "Tworzenie i wdrażanie zasad ochrony aplikacji"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: dowiedz się, jak zasady ochrony aplikacji usługi Intune mogą chronić dane firmy używane przez aplikacje, którymi zarządzasz."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 04/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f31b2964-e932-4cee-95c4-8d5506966c85
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: d63e99561766268941b2c6d8b3bb6a1dd028f72c
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017

---

# <a name="how-to-create-and-assign-app-protection-policies"></a>Tworzenie i przypisywanie zasad ochrony aplikacji

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

**Jeśli nie jesteś w usłudze Intune w programie wersji zapoznawczej witryny Azure Portal**, w tym temacie opisano [tworzenie zasad ochrony aplikacji](https://docs.microsoft.com/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) w klasycznej konsoli usługi Intune.

Zasady ochrony aplikacji można stosować do aplikacji działających na urządzeniach, które mogą być zarządzane przez usługę Intune lub nie. Bardziej szczegółowy opis działania zasad ochrony aplikacji oraz scenariuszy obsługiwanych przy użyciu zasad ochrony aplikacji usługi Intune znajduje się w artykule [What is Microsoft Intune app protection policies](app-protection-policy.md) (Co to są zasady ochrony aplikacji usługi Microsoft Intune).

##  <a name="create-an-app-protection-policy"></a>Tworzenie zasad ochrony aplikacji
1.  W obciążeniu **Aplikacje mobilne** wybierz kolejno pozycje **Zarządzaj** > **Zasady ochrony aplikacji**.

2.  Spowoduje to otwarcie bloku **Zasady ochrony aplikacji**, w którym można tworzyć nowe zasady i edytować istniejące. Wybierz pozycję **Dodaj zasady**.

  ![Zrzut ekranu przedstawiający blok Dodawanie zasad](./media/app-protection-add-policy.png)

3.  Wpisz nazwę zasad, dodaj ich krótki opis i wybierz typ platformy do utworzenia zasad dla systemu iOS lub Android. Dla każdej platformy można utworzyć większą liczbę zasad.

4.  Wybierz pozycję **Aplikacje**, aby otworzyć **blok Aplikacje**, w którym jest wyświetlana lista dostępnych aplikacji. Z listy wybierz jedną lub więcej aplikacji do powiązania z tworzonymi zasadami. Po wybraniu aplikacji wybierz opcję **Wybierz** w dolnej części bloku **Aplikacje**, aby zapisać wybrane opcje.

    > [!IMPORTANT]
    > W celu utworzenia zasad należy wybrać co najmniej jedną aplikację.

5.  W bloku **Dodawanie zasad** wybierz pozycję **Skonfiguruj wymagane ustawienia**, aby otworzyć blok ustawień zasad.

    Istnieją dwie kategorie ustawień zasad, **Przeniesienie danych** i **Dostęp**.  Zasady przeniesienia danych stosują się do przenoszenia danych do i z aplikacji, podczas gdy zasady dostępu określają metodę dostępu użytkownika końcowego do aplikacji w kontekście pracy.
    Ustawienia zasad mają wartości domyślne, co ułatwia rozpoczęcie pracy. Jeśli wartości domyślne spełniają Twoje wymagania, nie musisz wprowadzać żadnych zmian.

    > [!TIP]
    > Te ustawienia zasad obowiązują tylko w przypadku stosowania aplikacji w kontekście pracy.  W przypadku gdy użytkownik końcowy używa aplikacji do wykonywania zadań osobistych, zasady te nie obowiązują.



6.  Wybierz pozycję **OK**, aby zapisać tę konfigurację. Znajdziesz się ponownie w bloku **Dodawanie zasad** . Wybierz pozycję **Utwórz**, aby utworzyć zasady i zapisać ustawienia.


Po zakończeniu tworzenia zasad zgodnie z opisem w poprzedniej procedurze nie są one wdrażane dla żadnych użytkowników. Aby wdrożyć zasady, zobacz następującą sekcję: „Wdrażanie zasad dla użytkowników”.

## <a name="deploy-a-policy-to-users"></a>Wdrażanie zasad dla użytkowników

1.  W bloku **Zasady** wybierz pozycję **Grupy użytkowników**, co spowoduje otwarcie bloku **Grupy użytkowników**. Wybierz pozycję **Dodaj grupę użytkowników** w bloku **Grupy użytkowników**, aby otworzyć blok **Dodawanie grupy użytkowników**.

  ![Zrzut ekranu przedstawiający blok Grupy użytkowników z podświetloną opcją menu Dodaj grupę użytkowników](./media/app-protection-policy-add-users.png)

2.  W bloku **Dodawanie grupy użytkowników** zostanie wyświetlona lista grup użytkowników. Jest to lista wszystkich grup zabezpieczeń w usłudze **Azure Active Directory**. Wybierz grupy użytkowników, których mają dotyczyć te zasady, a następnie wybierz pozycję **Wybierz**. Wybranie pozycji **Wybierz** wdraża zasady dla użytkowników.
  ![Zrzut ekranu przedstawiający blok Dodaj grupę użytkowników z listą użytkowników usługi Azure Active Directory](./media/azure-ad-user-group-list.png)

Zasady zostały utworzone i wdrożone dla użytkowników.

Zasady wpływają tylko na użytkowników, którym przypisano licencje usługi Microsoft Intune. Zasady nie wpływają na użytkowników należących do wybranej grupy zabezpieczeń, którym nie przypisano licencji usługi Microsoft Intune.

>[!IMPORTANT]
> Jeśli używasz usługi Intune z programem Configuration Manager do zarządzania urządzeniami z systemami Android i iOS, zasady są stosowane tylko do użytkowników należących bezpośrednio do wybranej grupy. Nie mają one wpływu na członków grup podrzędnych zagnieżdżonych w wybranej grupie.

Użytkownicy końcowi mogą pobrać aplikacje ze sklepu App Store lub Google Play. Aby uzyskać więcej informacji, zobacz:
* [Czego można oczekiwać, gdy aplikacja systemu Android jest zarządzana przy użyciu zasad ochrony aplikacji](app-protection-enabled-apps-android.md)
* [Czego można oczekiwać, gdy aplikacja systemu iOS jest zarządzana przy użyciu zasad ochrony aplikacji](app-protection-enabled-apps-ios.md)

##  <a name="change-existing-policies"></a>Zmiana istniejących zasad
Możesz edytować istniejące zasady i zastosować je do użytkowników docelowych. Jednak w przypadku zmiany istniejących zasad użytkownicy zalogowani do aplikacji zobaczą zmiany dopiero po 8 godzinach.

Aby zobaczyć efekt zmian natychmiast, użytkownik końcowy musi wylogować się z aplikacji i ponownie do niej zalogować.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>Aby zmienić listę aplikacji powiązanych z zasadami

1.  W bloku **Zasady aplikacji** wybierz zasady, które chcesz zmienić. Spowoduje to otwarcie bloku specyficznego dla właśnie wybranych zasad.

2.  W bloku zasad wybierz pozycję **Aplikacje docelowe**, aby otworzyć listę aplikacji.

3.  Usuń lub dodaj aplikacje do listy i wybierz pozycję **Zapisz**, aby zapisać zmiany.

### <a name="to-change-the-list-of-user-groups"></a>Aby zmienić listę grup użytkowników

1.  W bloku **Zasady aplikacji** wybierz zasady, które chcesz zmienić. Spowoduje to otwarcie bloku specyficznego dla wybranych zasad.

2.  W bloku zasad wybierz pozycję **Grupy użytkowników**, aby otworzyć blok **Grupa użytkowników** z listą bieżących grup użytkowników, których dotyczą dane zasady.

3.  Aby dodać nową grupę użytkowników do zasad, wybierz pozycję **Dodaj grupę użytkowników** i wybierz grupę użytkowników. Wybierz pozycję **Wybierz**, aby wdrożyć zasady dla wybranej grupy.

4.  Aby usunąć grupę użytkowników, wyróżnij grupę użytkowników, którą chcesz usunąć. Następnie kliknij przycisk wielokropka (...) i wybierz polecenie **Usuń**, aby usunąć grupę użytkowników.
  ![Zrzut ekranu przedstawiający opcję Usuń ](./media/app-protection-policy-delete-user.png)

### <a name="to-change-policy-settings"></a>Aby zmienić ustawienia zasad

1.  W bloku **Zasady aplikacji** wybierz zasady, które chcesz zmienić. Spowoduje to otwarcie bloku specyficznego dla właśnie wybranych zasad.


2.  Wybierz pozycję **Ustawienia zasad**, aby otworzyć blok **Ustawienia zasad**.

3.  Zmień ustawienia i wybierz ikonę **Zapisz**, aby zapisać zmiany.

## <a name="policy-settings"></a>Ustawienia zasad
Aby wyświetlić pełną listę ustawień zasad dla systemów iOS i Android, wybierz jeden z następujących elementów:

> [!div class="op_single_selector"]
- [Zasady systemu iOS](app-protection-policy-settings-ios.md)
- [Zasady systemu Android](app-protection-policy-settings-android.md)

## <a name="next-steps"></a>Następne kroki
[Monitorowanie zgodności i stanu użytkownika](app-protection-policies-monitor.md)

### <a name="see-also"></a>Zobacz także
* [Czego można oczekiwać, gdy aplikacja systemu Android jest zarządzana przy użyciu zasad ochrony aplikacji](app-protection-enabled-apps-android.md)
* [Czego można oczekiwać, gdy aplikacja systemu iOS jest zarządzana przy użyciu zasad ochrony aplikacji](app-protection-enabled-apps-ios.md)

