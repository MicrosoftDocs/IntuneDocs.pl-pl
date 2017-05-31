---
title: "Ustawianie warunków i postanowień w usłudze Microsoft Intune"
titleSuffix: Intune Azure preview
description: "Ustawianie warunków i postanowień widocznych dla użytkowników w aplikacji Portal firmy dla usługi Intune. "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 05/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a3a11a8-9c0c-4334-8c6b-6fea4d0a2efb
ms.reviewer: amyro
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: d53e91e24988d1bc71ff8df425f0d82e0fc43b58
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017

---

# <a name="ensure-users-accept-company-terms-for-access"></a>Zapewnienie akceptacji firmowych warunków dostępu przez użytkowników

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Jako administrator usługi Intune możesz wymagać, aby użytkownicy zaakceptowali warunki i postanowienia obowiązujące w firmie, zanim rozpoczną korzystanie z aplikacji Portal firmy w celu zarejestrowania swoich urządzeń oraz uzyskania dostępu do zasobów firmowych, takich jak aplikacje i wiadomości e-mail. Konfiguracja warunków i postanowień jest opcjonalna.

Możesz utworzyć wiele zestawów warunków i postanowień oraz przypisać je do różnych grup, np. w celu obsługi wielu języków.

## <a name="create-terms-and-conditions"></a>Tworzenie warunków i postanowień
Wykonaj następujące kroki, aby utworzyć warunki i postanowienia. Wyświetlana nazwa i opis są przeznaczone do użytku administracyjnego, natomiast właściwości dotyczące warunków są widoczne dla użytkowników w aplikacji Portal firmy.

1. W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.

2. W bloku Intune wybierz pozycję **Rejestrowanie urządzenia**, a następnie **Warunki i postanowienia**.

3. Wybierz przycisk **Utwórz**.
![Zrzut ekranu portalu usługi Intune przedstawiający przycisk Utwórz służący do tworzenia warunków i postanowień](media/terms-create-terms.png)

4. W rozwiniętym bloku określ następujące informacje:

   - **Nazwa wyświetlana**: nazwa warunków w portalu usługi Intune. Użytkownicy nie widzą tej nazwy.

   - **Opis**: opcjonalne szczegółowe informacje ułatwiające identyfikację danego zbioru warunków w portalu usługi Intune.

5. Wybierz strzałkę obok pozycji Definiuj warunki użytkowania, aby otworzyć blok Warunki i postanowienia, a następnie wprowadź następujące informacje:

   ![Zrzut ekranu akceptacji warunków i postanowień użytkownika końcowego z podsumowaniem warunków](./media/terms-summary-create.png)

   - **Tytuł**: tytuł widoczny dla użytkowników w aplikacji Portal firmy.

   - **Podsumowanie warunków**: wyjaśniono tutaj, co się dzieje, jeśli użytkownicy zaakceptują warunki. Na przykład: „Rejestrując swoje urządzenie, akceptujesz warunki i postanowienia określone przez firmę Contoso. Zanim przejdziesz dalej, przeczytaj uważnie niniejsze warunki”.

   - **Warunki i postanowienia**: warunki i postanowienia, które użytkownicy muszą zaakceptować lub odrzucić.

6. Wybierz pozycję **OK**, a następnie pozycję **Utwórz**.

## <a name="assign-terms-and-conditions"></a>Przypisywanie warunków i postanowień

Warunki i postanowienia można przypisywać do grup użytkowników, które muszą je zaakceptować przed rozpoczęciem korzystania z aplikacji Portal firmy.

1. W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.

2. W bloku Intune wybierz pozycję **Rejestrowanie urządzenia**, a następnie **Warunki i postanowienia**.

3. Na liście warunków i postanowień wybierz warunki i postanowienia, które chcesz przypisać, a następnie wybierz pozycję **Przypisane grupy**.
![Zrzut ekranu przedstawiający blok Przypisz grupę portalu usługi Intune z przyciskami Wybierz grupę oraz Wybierz służącymi do przypisywania warunków i postanowień](media/terms-assign-groups.png)

4. Kliknij przycisk **Wybierz grupę** i w bloku **Wybierz grupy** wybierz te grupy, do których chcesz przypisać warunki, a następnie kliknij przycisk **Wybierz**.

5. W bloku **Przypisane grupy** kliknij przycisk **Zapisz**.  Warunki i postanowienia są teraz przypisane do użytkowników z wybranych grup. Użytkownicy będą monitowani o zaakceptowanie warunków i postanowień przy następnej próbie uzyskania dostępu do aplikacji Portal firmy.

   ![Zrzut ekranu akceptacji warunków i postanowień użytkownika końcowego z podsumowaniem warunków](./media/terms-summary-accept.png)

## <a name="monitor-a-terms-and-conditions"></a>Monitorowanie warunków i postanowień

1. W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**. W bloku Intune wybierz pozycję **Rejestrowanie urządzenia**, a następnie **Warunki i postanowienia**.
2. Na liście warunków i postanowień wybierz warunki i postanowienia, które mają zostać zaakceptowane, a następnie wybierz pozycję **Stany akceptacji**.

## <a name="work-with-multiple-versions-of-terms-and-conditions"></a>Praca z wieloma wersjami warunków i postanowień
Możesz edytować warunki i postanowienia oraz zarządzać ich wersjami. Zalecamy zwiększenie numeru wersji i wymaganie akceptacji po każdym wprowadzeniu znaczących zmian w warunkach i postanowieniach. Jeśli zmiany obejmują na przykład poprawki błędów pisowni lub zmiany formatowania, zachowaj bieżący numer wersji.

1. W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.

2. W bloku Intune wybierz kolejno pozycje **Rejestrowanie urządzenia** i **Warunki i postanowienia**, a następnie wybierz warunki i postanowienia, które chcesz zmodyfikować i wybierz pozycję **Właściwości**.

4. W bloku **Właściwości** wybierz pozycję **Warunki i postanowienia**, a następnie zmodyfikuj wartość pól **Tytuł**, **Podsumowanie warunków** i **Warunki i postanowienia** odpowiednio do potrzeb. Jeśli dokonane zmiany wymagają ponownej akceptacji nowych warunków przez użytkowników, kliknij pozycję **Wymagaj od użytkowników ponownego zaakceptowania i zwiększ numer wersji do**

4.  Wybierz pozycję **OK**, a następnie pozycję **Zapisz**.

