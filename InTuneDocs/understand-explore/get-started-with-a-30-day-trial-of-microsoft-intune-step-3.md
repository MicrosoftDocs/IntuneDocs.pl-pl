---
title: "Tworzenie grup w celu zorganizowania użytkowników i urządzeń w bezpłatnej wersji próbnej | Microsoft Docs"
description: "Tworzenie grup urządzeń i grup użytkowników w przypadku rejestracji w celu korzystania z bezpłatnej 30-dniowej wersji ewaluacyjnej usługi Microsoft Intune."
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 11/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7162cad3-5c14-43f3-a760-833ffd7786b1
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 89e190e6a3e514c0f38b33409cde2abea0776885
ms.openlocfilehash: 0cdf5bf8f9fad1f44dbb0ef11de71aea55949d89


---

# <a name="create-groups-to-organize-evaluation-subscription-users-and-devices"></a>Tworzenie grup w celu organizowania użytkowników i urządzeń subskrypcji ewaluacyjnej

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Grupy w usłudze Intune zapewniają dużą elastyczność zarządzania urządzeniami i użytkownikami. Grupy można skonfigurować zgodnie z potrzebami organizacyjnymi (na przykład według lokalizacji geograficznej, działu lub charakterystyki sprzętu) i używać ich do różnych zadań administracyjnych w dowolnej skali, od ustawiania zasad dla zestawu użytkowników po wdrażanie aplikacji w grupach urządzeń.

## <a name="create-a-device-group"></a>Tworzenie grupy urządzeń
Użyj grup urządzeń do wdrażania aktualizacji i oprogramowania oraz konfigurowania ustawień agenta usługi Microsoft Intune i zasad ustawień zapory systemu Windows. Możesz na przykład skonfigurować grupę „Moje urządzenia próbne”, wykonując następujące kroki:

1.  W [konsoli administracyjnej usługi Intune](https://manage.microsoft.com/) kliknij pozycje **Grupy** &gt; **Przegląd** &gt; **Utwórz grupę**.

2.  W polu **Nazwa grupy** wpisz ciąg „Moje urządzenia próbne”, z listy grup nadrzędnych wybierz pozycję **Wszystkie urządzenia**, a następnie wybierz pozycję **Dalej**.

3.  Na stronie **Zdefiniuj kryteria członkostwa** wybierz pozycję **Wszystkie urządzenia** , aby wskazać, że grupa zawiera zarówno urządzenia przenośne, jak i komputery.

4.  Na stronie **Definiowanie członkostwa bezpośredniego** wybierz pozycję **Dalej**. Jeśli wcześniej została utworzona grupa, która nie zawiera wszystkich urządzeń, i chcesz dodać określone urządzenia do tej nowej grupy, możesz to zrobić na tej stronie.

5.  Na stronie **Podsumowanie** przejrzyj akcje, które zostaną wykonane, a następnie wybierz pozycję **Zakończ**.

Nowo utworzona grupa znajduje się na liście **Grupy** w obszarze roboczym **Grupy** w obszarze grupy nadrzędnej **Wszystkie urządzenia**. W tym miejscu możesz także edytować lub usunąć grupę.

## <a name="create-a-user-group"></a>Tworzenie grupy użytkowników
Grupa użytkowników umożliwia wdrażanie zasad dotyczących oprogramowania i urządzeń. Możesz na przykład skonfigurować grupę „Moi użytkownicy próbni”, wykonując następujące kroki:

1.  W [konsoli administracyjnej usługi Intune](https://manage.microsoft.com/) kliknij pozycje **Grupy** &gt; **Przegląd** &gt; **Utwórz grupę**.

2.  W polu **Nazwa grupy** wpisz ciąg „Moi użytkownicy próbni”, z listy grup nadrzędnych wybierz pozycję **Wszyscy użytkownicy**, a następnie wybierz pozycję **Dalej**.

3.  Na stronie **Definiowanie kryteriów członkostwa** ustaw parametr **Uruchom członkostwo grupy w** na wartość **Wszyscy użytkownicy w grupie nadrzędnej**.

4.  Wybierz pozycję **Przeglądaj** obok pozycji **Wyklucz członków z następujących grup zabezpieczeń**, a następnie wybierz pozycję **Administrator firmy**. To wykluczenie umożliwi Ci zarządzanie grupą „Moi użytkownicy próbni” bez wpływu na konto administratora firmy (znanego również jako administrator dzierżawy).

5.  Na stronie **Definiowanie członkostwa bezpośredniego** wybierz pozycję **Dalej**. Nie musisz tutaj wykonywać żadnych czynności, ponieważ chcesz, aby grupa „Moi użytkownicy próbni” zawierała wszystkich użytkowników z wyjątkiem administratora firmy.

6.  Na stronie **Podsumowanie** przejrzyj akcje, które zostaną wykonane, a następnie wybierz pozycję **Zakończ**.

Nowo utworzona grupa znajduje się na liście **Grupy** w obszarze roboczym **Grupy** w obszarze grupy nadrzędnej **Wszyscy użytkownicy**. W tym miejscu możesz także edytować lub usunąć grupę.

Aby uzyskać więcej informacji na temat korzystania z grup, zobacz [Używanie grup do zarządzania użytkownikami i urządzeniami w usłudze Microsoft Intune](/Intune/Deploy-Use/use-groups-to-manage-users-and-devices-with-microsoft-intune).

## <a name="next-steps"></a>Następne kroki
[Tworzenie zasad](get-started-with-a-30-day-trial-of-microsoft-intune-step-4.md)  



<!--HONumber=Jan17_HO1-->


