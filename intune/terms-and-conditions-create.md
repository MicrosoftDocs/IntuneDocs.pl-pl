---
title: "Ustawianie warunków i postanowień w usłudze Microsoft Intune"
titlesuffix: Azure portal
description: "Ustawianie warunków i postanowień widocznych dla użytkowników w aplikacji Portal firmy dla usługi Intune. "
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a3a11a8-9c0c-4334-8c6b-6fea4d0a2efb
ms.reviewer: amyro
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 63434cbbc9edc668d59fb99968727551e0c4cc40
ms.sourcegitcommit: 94d3d86f8ae9f82a9872384bbaae53580036a4ff
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2017
---
# <a name="ensure-users-accept-company-terms-for-access"></a>Zapewnienie akceptacji firmowych warunków dostępu przez użytkowników

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Jako administrator usługi Intune możesz wymagać, aby użytkownicy zaakceptowali warunki i postanowienia obowiązujące w firmie, zanim rozpoczną korzystanie z aplikacji Portal firmy w celu zarejestrowania swoich urządzeń oraz uzyskania dostępu do zasobów firmowych, takich jak aplikacje i wiadomości e-mail. Konfiguracja warunków i postanowień jest opcjonalna.

Możesz utworzyć wiele zestawów warunków i postanowień oraz przypisać je do różnych grup, np. w celu obsługi wielu języków.

## <a name="create-terms-and-conditions"></a>Tworzenie warunków i postanowień
Wykonaj następujące kroki, aby utworzyć warunki i postanowienia. Wyświetlana nazwa i opis są przeznaczone do użytku administracyjnego, natomiast właściwości dotyczące warunków są widoczne dla użytkowników w aplikacji Portal firmy.

1. W witrynie Azure Portal wybierz opcję **Rejestrowanie urządzenia**, a następnie **Warunki i postanowienia**.
2. Wybierz przycisk **Utwórz**.
![Zrzut ekranu witryny Azure Portal przedstawiający przycisk Utwórz służący do tworzenia warunków i postanowień](media/terms-create-terms.png)
3. W rozwiniętym bloku określ następujące informacje:

   - **Nazwa wyświetlana**: nazwa warunków w witrynie Azure Portal. Użytkownicy nie widzą tej nazwy.

   - **Opis**: opcjonalne szczegółowe informacje ułatwiające identyfikację danego zbioru warunków w witrynie Azure Portal.

4. Wybierz strzałkę obok pozycji Definiuj warunki użytkowania, aby otworzyć blok Warunki i postanowienia, a następnie wprowadź następujące informacje:

   ![Zrzut ekranu akceptacji warunków i postanowień użytkownika końcowego z podsumowaniem warunków](./media/terms-summary-create.png)

   - **Tytuł**: nazwa warunków, którą użytkownicy widzą w Portalu firmy powyżej pozycji **Podsumowanie**.
   - **Podsumowanie warunków**: wyjaśnienie, co oznacza zaakceptowanie warunków przez użytkownika. Na przykład: „Rejestrując swoje urządzenie, akceptujesz warunki użytkowania określone przez firmę Contoso. Zanim przejdziesz dalej, przeczytaj uważnie niniejsze warunki”.
   - **Warunki i postanowienia**: warunki i postanowienia, które użytkownicy muszą zaakceptować lub odrzucić.

5. Wybierz pozycję **OK**, a następnie pozycję **Utwórz**.

## <a name="see-how-terms-are-displayed-to-your-users"></a>Zobacz, w jaki sposób warunki są wyświetlane użytkownikom
W poniższym przykładzie przedstawiono **Tytuł** i **Podsumowanie warunków** w konsoli administracyjnej i Portalu firmy.

![Zrzut ekranu przedstawiający Tytuł i Podsumowanie postanowień w konsoli administracyjnej i Portalu firmy.](./media/terms-summary-terms.png)

W poniższym przykładzie przedstawiono warunki i postanowienia w konsoli administracyjnej i Portalu firmy.

![Zrzut ekranu przedstawiający warunki i postanowienia w konsoli administracyjnej i Portalu firmy.](./media/terms-properties-terms.png)

## <a name="assign-terms-and-conditions"></a>Przypisywanie warunków i postanowień

Warunki i postanowienia można przypisywać do grup użytkowników, które muszą je zaakceptować przed rozpoczęciem korzystania z aplikacji Portal firmy.

1. W witrynie Azure Portal wybierz opcję **Rejestrowanie urządzenia**, a następnie **Warunki i postanowienia**.
2. Na liście warunków i postanowień wybierz warunki i postanowienia, które chcesz przypisać, a następnie wybierz pozycję **Przypisane grupy**.
![Zrzut ekranu przedstawiający blok Przypisz grupę witryny Azure Portal z przyciskami Wybierz grupę oraz Wybierz służącymi do przypisywania warunków i postanowień](media/terms-assign-groups.png)
3. Kliknij przycisk **Wybierz grupę** i w bloku **Wybierz grupy** wybierz te grupy, do których chcesz przypisać warunki, a następnie kliknij przycisk **Wybierz**. Warunków i postanowień nie można przypisać do grup dynamicznych.
4. W bloku **Przypisane grupy** kliknij przycisk **Zapisz**.  Warunki i postanowienia są teraz przypisane do użytkowników z wybranych grup. Użytkownicy będą monitowani o zaakceptowanie warunków i postanowień przy następnej próbie uzyskania dostępu do aplikacji Portal firmy. Warunki i postanowienia wymagają jednokrotnej akceptacji. Użytkownicy z wieloma urządzeniami nie muszą ich akceptować na każdym urządzeniu.


## <a name="monitor-terms-and-conditions"></a>Monitorowanie warunków i postanowień

1. W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**. W bloku Intune wybierz pozycję **Rejestrowanie urządzenia**, a następnie **Warunki i postanowienia**.
2. Na liście warunków i postanowień wybierz warunki i postanowienia, które mają zostać zaakceptowane, a następnie wybierz pozycję **Stany akceptacji**.

## <a name="work-with-multiple-versions-of-terms-and-conditions"></a>Praca z wieloma wersjami warunków i postanowień
Możesz edytować warunki i postanowienia oraz zarządzać ich wersjami. Zalecamy zwiększenie numeru wersji i wymaganie akceptacji po każdym wprowadzeniu znaczących zmian w warunkach i postanowieniach. Jeśli zmiany obejmują na przykład poprawki błędów pisowni lub zmiany formatowania, zachowaj bieżący numer wersji.

1. W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.

2. W bloku Intune wybierz kolejno pozycje **Rejestrowanie urządzenia** i **Warunki i postanowienia**, a następnie wybierz warunki i postanowienia, które chcesz zmodyfikować i wybierz pozycję **Właściwości**.

4. W bloku **Właściwości** wybierz pozycję **Warunki i postanowienia**, a następnie zmodyfikuj wartość pól **Tytuł**, **Podsumowanie warunków** i **Warunki i postanowienia** odpowiednio do potrzeb. Jeśli dokonane zmiany wymagają ponownej akceptacji nowych warunków przez użytkowników, kliknij pozycję **Wymagaj od użytkowników ponownego zaakceptowania i zwiększ numer wersji do**

4.  Wybierz pozycję **OK**, a następnie pozycję **Zapisz**.

Użytkownicy muszą tylko raz zaakceptować zaktualizowane warunki i postanowienia. Użytkownicy z wieloma urządzeniami nie muszą akceptować warunków i postanowień na każdym urządzeniu.
