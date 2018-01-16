---
title: "Tworzenie grup w celu zorganizowania użytkowników i urządzeń"
description: "Tworzenie użytkowników i grup dla subskrypcji usługi Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5fdf98c8-fe67-4d7a-9837-ed1234348014
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 309994268b061f844e26dea8df8ce3c0fd237e95
ms.sourcegitcommit: 22ab1c6a6bfeb4fef9850d12b29829c3fecbbeed
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/12/2018
---
# <a name="create-groups-to-organize-users-and-devices"></a>Tworzenie grup w celu zorganizowania użytkowników i urządzeń

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ten temat zawiera informacje dla administratorów dotyczące tworzenia grup użytkowników w usłudze Intune.

Grupy w usłudze Intune zapewniają dużą elastyczność zarządzania urządzeniami i użytkownikami. Grupy można skonfigurować zgodnie z potrzebami geograficznymi (na przykład według lokalizacji geograficznej, działu lub charakterystyki sprzętu) i używać ich do różnych zadań administracyjnych, od wdrażania zasad dla zestawu użytkowników po wdrażanie aplikacji w grupach urządzeń.

## <a name="group-management-moving-to-azure-ad"></a>Zarządzanie grupami przeniesione do usługi Azure AD

**Od listopada 2016 r.** nowe konta będą zarządzać grupami użytkowników i urządzeń w portalu usługi Azure Active Directory (AD). W grudniu 2016 r. zespół produktu Intune rozpocznie migrowanie istniejących klientów do nowego środowiska zarządzania grupami opartego na usłudze Azure AD. Wszystkie grupy użytkowników i urządzeń będą migrowane do grup zabezpieczeń usługi Azure AD. Migracje zostaną rozpoczęte dopiero wtedy, gdy nie będą miały wpływu na Twoją codzienną pracę i pracę użytkowników. Przed migracją Twojego konta otrzymasz powiadomienie.


>[!IMPORTANT]
>
>Jeśli otworzysz obszar roboczy Grupy w portalu usługi Intune i zobaczysz komunikat **Grupy użytkowników usługi Intune są teraz zarządzane jako grupy w usłudze Azure Active Directory** z linkiem do portalu usługi Azure Active Directory, oznacza to, że w przypadku zarządzania grupami w usłudze Intune jest już używane *nowe* podejście do grup zabezpieczeń usługi Azure AD. Aby dowiedzieć się, jak tworzyć grupy, zobacz [Zarządzanie grupami w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).
>
>Jeśli nie widzisz linku do portalu usługi Azure AD, nadal zarządzasz grupami w portalu usługi Intune.

## <a name="group-management-in-the-intune-portal"></a>Zarządzanie grupami w portalu usługi Intune

Grupy urządzeń i użytkowników są tworzone w obszarze roboczym GRUPY konsoli administracyjnej usługi Intune.

![Obszar roboczy grup konsoli administracyjnej](./media/groups.png)


> [!TIP]
> Aby uzyskać więcej informacji na temat korzystania z grup, zobacz [Używanie grup do zarządzania użytkownikami i urządzeniami w usłudze Microsoft Intune](/intune-classic/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).


## <a name="create-a-device-group"></a>Tworzenie grupy urządzeń
Grupy urządzeń umożliwiają wdrażanie aplikacji i aktualizacji, jak również konfigurowanie innych funkcji. Możesz na przykład skonfigurować grupę „Moje urządzenia”, wykonując następujące kroki:

1.  W [konsoli administracyjnej usługi Intune](https://manage.microsoft.com/) wybierz pozycje **Grupy** > **Przegląd** > **Utwórz grupę**.

2.  W polu **Nazwa grupy** wpisz ciąg „Moje urządzenia”, z listy grup nadrzędnych wybierz pozycję **Wszystkie urządzenia**, a następnie wybierz przycisk **Dalej**.

3.  Na stronie **Zdefiniuj kryteria członkostwa** wybierz pozycję **Wszystkie urządzenia** , aby wskazać, że grupa zawiera zarówno urządzenia przenośne, jak i komputery.

4.  Na stronie **Definiowanie członkostwa bezpośredniego** wybierz pozycję **Dalej**. Jeśli wcześniej została utworzona grupa, która nie zawiera wszystkich urządzeń, i chcesz dodać określone urządzenia do tej nowej grupy, możesz to zrobić na tej stronie.

5.  Na stronie **Podsumowanie** przejrzyj akcje, które zostaną wykonane, a następnie wybierz pozycję **Zakończ**.

Nowo utworzona grupa znajduje się na liście **Grupy** w obszarze roboczym **Grupy** w obszarze grupy nadrzędnej **Wszystkie urządzenia**. W tym miejscu możesz także edytować lub usunąć grupę.

## <a name="create-a-user-group"></a>Tworzenie grupy użytkowników
Grupa użytkowników umożliwia wdrażanie zasad dotyczących oprogramowania i urządzeń. Możesz na przykład skonfigurować grupę „Użytkownicy usługi Intune”, wykonując następujące kroki:

1.  W [konsoli administracyjnej usługi Intune](https://manage.microsoft.com/) wybierz pozycje **Grupy** > **Przegląd** > **Utwórz grupę**.

2.  W polu **Nazwa grupy** wpisz ciąg „Użytkownicy usługi Intune”, z listy grup nadrzędnych wybierz pozycję **Wszyscy użytkownicy**, a następnie wybierz przycisk **Dalej**.

3.  Na stronie **Definiowanie kryteriów członkostwa** ustaw parametr **Uruchom członkostwo grupy w** na wartość **Wszyscy użytkownicy w grupie nadrzędnej**.

4.  Wybierz pozycję **Przeglądaj** obok pozycji **Wyklucz członków z następujących grup zabezpieczeń**, a następnie wybierz pozycję **Administrator firmy**. To wykluczenie umożliwia zarządzanie grupą „Użytkownicy usługi Intune” bez wpływu na konto administratora firmy (znanego również jako administrator dzierżawy).

5.  Na stronie **Definiowanie członkostwa bezpośredniego** wybierz pozycję **Dalej**. Nie musisz tutaj niczego robić, ponieważ chcesz, aby grupa „Użytkownicy usługi Intune” zawierała wszystkich użytkowników z wyjątkiem administratora firmy.

6.  Na stronie **Podsumowanie** przejrzyj akcje, które zostaną wykonane, a następnie wybierz pozycję **Zakończ**.

Nowo utworzona grupa znajduje się na liście **Grupy** w obszarze roboczym **Grupy** w obszarze grupy nadrzędnej **Wszyscy użytkownicy**. W tym miejscu możesz także edytować lub usunąć grupę.

>[!div class="step-by-step"]
/intune/licenses-assign [&larr; **Zarządzanie licencjami usługi Intune**](/intune/licenses-assign)       [**Tworzenie zasad i aplikacji** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-6.md)  
