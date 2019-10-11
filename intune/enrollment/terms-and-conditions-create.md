---
title: Ustawianie warunków i postanowień w usłudze Microsoft Intune
titleSuffix: ''
description: Ustawianie warunków i postanowień widocznych dla użytkowników w aplikacji Portal firmy dla usługi Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/20/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4a3a11a8-9c0c-4334-8c6b-6fea4d0a2efb
ms.reviewer: amyro
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2ef002b508e484d6967bbdd0908729332d866046
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71726365"
---
# <a name="terms-and-conditions-for-user-access"></a>Warunki i postanowienia dotyczące dostępu użytkowników

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Jako administrator usługi Intune możesz wymagać, aby użytkownicy zaakceptowali warunki i postanowienia firmy przed rozpoczęciem korzystania z Portalu firmy w następujących celach:
- Rejestrowanie urządzeń
- Uzyskiwanie dostępu do zasobów, takich jak firmowe aplikacje i poczta e-mail.

Konfiguracja warunków i postanowień jest opcjonalna.

Możesz utworzyć wiele zestawów warunków i postanowień oraz przypisać je do różnych grup, np. w celu obsługi wielu języków.

Istnieją dwa sposoby tworzenia firmowych warunków i postanowień:
- Za pomocą usługi Intune, zgodnie z opisem w tym artykule.
- Za pomocą [funkcji warunków użytkowania usługi Azure Active Directory](https://docs.microsoft.com/azure/active-directory/governance/active-directory-tou)

Aby dowiedzieć się, która metoda jest najbardziej odpowiednia dla Ciebie, zobacz wpis w blogu [Choosing the right Terms solution for your organization](https://go.microsoft.com/fwlink/?linkid=2010506&clcid=0x409) (Wybieranie odpowiedniego rozwiązania w zakresie warunków dla Twojej organizacji). 

## <a name="create-terms-and-conditions"></a>Tworzenie warunków i postanowień
Wykonaj następujące kroki, aby utworzyć warunki i postanowienia. Wyświetlana nazwa i opis są przeznaczone do użytku administracyjnego, natomiast właściwości dotyczące warunków są widoczne dla użytkowników w aplikacji Portal firmy.

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. W okienku **Intune** wybierz pozycję **Rejestrowanie urządzeń** > **Warunki i postanowienia**.
3. Wybierz pozycję **Utwórz**.
4. Na stronie **Podstawowe** określ następujące informacje:

   - **Nazwa**: nazwa warunków w witrynie Azure Portal. Użytkownicy nie widzą tej nazwy.
   - **Opis**: opcjonalne szczegółowe informacje ułatwiające identyfikację danego zbioru warunków w witrynie Azure Portal.

    ![Zrzut ekranu witryny Azure Portal przedstawiający stronę Podstawowe służącą do tworzenia warunków i postanowień](./media/terms-and-conditions-create/terms-basics-page.png)

5. Wybierz pozycję **Dalej**, aby przejść do strony **Warunki** i podać następujące informacje:

   - **Tytuł**: nazwa warunków, którą użytkownicy widzą w Portalu firmy powyżej pozycji **Podsumowanie**.
   - **Warunki i postanowienia**: warunki i postanowienia, które użytkownicy muszą zaakceptować lub odrzucić.
   - **Podsumowanie warunków**: wyjaśnienie, co oznacza zaakceptowanie warunków przez użytkownika. Na przykład: „Rejestrując swoje urządzenie, akceptujesz warunki użytkowania określone przez firmę Contoso. Zanim przejdziesz dalej, przeczytaj uważnie niniejsze warunki”.

6. Wybierz pozycję **Dalej**, aby przejść na stronę **Tagi zakresu**.

7. Wybierz pozycję **Wybierz tagi zakresu**, wybierz tagi zakresu, które chcesz przypisać do tych warunków i postanowień, a następnie wybierz pozycję **Wybierz**. 

8. Wybierz pozycję **Dalej**, aby przejść do strony **Przypisania**, a następnie wybierz jedną z następujących opcji dla ustawienia **Przypisz do**:
    - **Wszyscy użytkownicy**: Wybierz tę opcję, aby przypisać te warunki i postanowienia do wszystkich użytkowników.
    - **Wybierz grupy**: Wybierz tę opcję, aby przypisać te warunki i postanowienia do wszystkich w grupach, które określisz, wybierając pozycję **Wybierz grupy do uwzględnienia**.

9. Wybierz pozycję **Dalej** > **Utwórz**.

## <a name="see-how-terms-are-displayed-to-your-users"></a>Zobacz, w jaki sposób warunki są wyświetlane użytkownikom
W poniższym przykładzie przedstawiono **Tytuł** i **Podsumowanie warunków** w konsoli administracyjnej i Portalu firmy.

![Zrzut ekranu przedstawiający Tytuł i Podsumowanie postanowień w konsoli administracyjnej i Portalu firmy.](./media/terms-and-conditions-create/terms-summary-terms.png)

W poniższym przykładzie przedstawiono warunki i postanowienia w konsoli administracyjnej i Portalu firmy.

![Zrzut ekranu przedstawiający warunki i postanowienia w konsoli administracyjnej i Portalu firmy.](./media/terms-and-conditions-create/terms-properties-terms.png)


## <a name="monitor-terms-and-conditions"></a>Monitorowanie warunków i postanowień

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973). 
1. W okienku Intune wybierz pozycję **Rejestrowanie urządzeń** > **Warunki i postanowienia**.
2. Na liście warunków i postanowień wybierz warunki, dla których ma zostać wyświetlona akceptacja, a następnie wybierz pozycję **Raportowanie akceptacji**.

## <a name="work-with-multiple-versions-of-terms-and-conditions"></a>Praca z wieloma wersjami warunków i postanowień
Możesz edytować warunki i postanowienia oraz zarządzać ich wersjami. Każdorazowo po wprowadzeniu znaczących zmian w warunkach i postanowieniach wykonaj następujące działania:
- Zwiększ numer wersji.
- Poproś użytkowników o zaakceptowanie nowych warunków i postanowień.

Jeśli zmiany obejmują na przykład poprawki błędów pisowni lub zmiany formatowania, zachowaj bieżący numer wersji.

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).

2. W okienku Intune wybierz pozycję **Rejestrowanie urządzeń** > **Warunki i postanowienia**, wybierz warunki i postanowienia, które chcesz zmodyfikować, a następnie wybierz pozycję **Właściwości**.

4. W okienku **Właściwości** wybierz pozycję **Warunki i postanowienia**, a następnie zmodyfikuj wartość pól **Tytuł**, **Podsumowanie warunków** oraz **Warunki i postanowienia** zgodnie z potrzebami. Jeśli dokonane zmiany wymagają ponownej akceptacji nowych warunków przez użytkowników, wybierz pozycję **Wymagaj od użytkowników ponownego zaakceptowania i zwiększ numer wersji do**

4. Wybierz pozycję **OK** > **Zapisz**.

Użytkownicy muszą tylko raz zaakceptować zaktualizowane warunki i postanowienia. Użytkownicy z wieloma urządzeniami nie muszą akceptować warunków i postanowień na każdym urządzeniu.
