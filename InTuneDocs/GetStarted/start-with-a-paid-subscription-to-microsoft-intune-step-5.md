---
# required metadata

title: Tworzenie grup w celu zorganizowania użytkowników i urządzeń | Usługa Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 5fdf98c8-fe67-4d7a-9837-ed1234348014

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Tworzenie grup w celu zorganizowania użytkowników i urządzeń
Grupy w usłudze Intune zapewniają dużą elastyczność zarządzania urządzeniami i użytkownikami. Grupy można skonfigurować zgodnie z potrzebami geograficznymi (na przykład według lokalizacji geograficznej, działu lub charakterystyki sprzętu) i używać ich do różnych zadań administracyjnych, od wdrażania zasad dla zestawu użytkowników po wdrażanie aplikacji w grupach urządzeń.

Grupy urządzeń i użytkowników są tworzone w obszarze roboczym GRUPY konsoli administracyjnej usługi Intune.

![Obszar roboczy grup konsoli administracyjnej](./media/groups.png)


> [!TIP]
> Aby uzyskać więcej informacji na temat korzystania z grup, zobacz [Używanie grup do zarządzania użytkownikami i urządzeniami w usłudze Microsoft Intune](/intune/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune)..


## Tworzenie grupy urządzeń
Grupy urządzeń umożliwiają wdrażanie aplikacji i aktualizacji, jak również konfigurowanie innych funkcji. Możesz na przykład skonfigurować grupę „Moje urządzenia”, wykonując następujące kroki:

1.  W [konsoli administracyjnej usługi Intune](https://manage.microsoft.com/) wybierz pozycje **Grupy** > **Przegląd** > **Utwórz grupę**.

2.  W polu **Nazwa grupy** wpisz ciąg „Moje urządzenia”, z listy grup nadrzędnych wybierz pozycję **Wszystkie urządzenia**, a następnie wybierz przycisk **Dalej**..

3.  Na stronie **Zdefiniuj kryteria członkostwa** wybierz pozycję **Wszystkie urządzenia** , aby wskazać, że grupa zawiera zarówno urządzenia przenośne, jak i komputery.

4.  Na stronie **Definiowanie członkostwa bezpośredniego** wybierz pozycję **Dalej**. Jeśli wcześniej została utworzona grupa, która nie zawiera wszystkich urządzeń, i chcesz dodać określone urządzenia do tej nowej grupy, możesz to zrobić na tej stronie.

5.  Na stronie **Podsumowanie** przejrzyj akcje, które zostaną wykonane, a następnie wybierz pozycję **Zakończ**..

Nowo utworzona grupa znajduje się na liście **Grupy** w obszarze roboczym **Grupy** w obszarze grupy nadrzędnej **Wszystkie urządzenia**. W tym miejscu możesz także edytować lub usunąć grupę.

## Tworzenie grupy użytkowników
Grupa użytkowników umożliwia wdrażanie zasad dotyczących oprogramowania i urządzeń. Możesz na przykład skonfigurować grupę „Użytkownicy usługi Intune”, wykonując następujące kroki:

1.  W [konsoli administracyjnej usługi Intune](https://manage.microsoft.com/) wybierz pozycje **Grupy** > **Przegląd** > **Utwórz grupę**.

2.  W polu **Nazwa grupy** wpisz ciąg „Użytkownicy usługi Intune”, z listy grup nadrzędnych wybierz pozycję **Wszyscy użytkownicy**, a następnie wybierz przycisk **Dalej**..

3.  Na stronie **Definiowanie kryteriów członkostwa** ustaw parametr **Uruchom członkostwo grupy w** na wartość **Wszyscy użytkownicy w grupie nadrzędnej**..

4.  Wybierz pozycję **Przeglądaj** obok pozycji **Wyklucz członków z następujących grup zabezpieczeń**, a następnie wybierz pozycję **Administrator firmy**. To wykluczenie umożliwia zarządzanie grupą „Użytkownicy usługi Intune” bez wpływu na konto administratora firmy (znanego również jako administrator dzierżawy).

5.  Na stronie **Definiowanie członkostwa bezpośredniego** wybierz pozycję **Dalej**. Nie musisz tutaj niczego robić, ponieważ chcesz, aby grupa „Użytkownicy usługi Intune” zawierała wszystkich użytkowników z wyjątkiem administratora firmy.

6.  Na stronie **Podsumowanie** przejrzyj akcje, które zostaną wykonane, a następnie wybierz pozycję **Zakończ**..

Nowo utworzona grupa znajduje się na liście **Grupy** w obszarze roboczym **Grupy** w obszarze grupy nadrzędnej **Wszyscy użytkownicy**. W tym miejscu możesz także edytować lub usunąć grupę.



### Następne kroki
Gratulacje! Krok 5 *Przewodnika Szybki start dotyczącego usługi Intune* został ukończony..

>[!div class="step-by-step"]

>[&larr; **Zarządzanie licencjami usługi Intune**](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)       [**Tworzenie zasad i aplikacji** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-6.md)  


<!--HONumber=May16_HO1-->


