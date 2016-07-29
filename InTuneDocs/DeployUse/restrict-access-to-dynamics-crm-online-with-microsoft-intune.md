---
title: "Ograniczanie dostępu poczty e-mail do usługi Dynamics CRM Online | Microsoft Intune"
description: "Ochrona i kontrola dostępu do usługi  Dynamics CRM Online przy użyciu dostępu warunkowego."
keywords: 
author: karthikaraman
manager: arob98
ms.date: 07/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f1c4522b-5a34-4f5a-89d2-7809c4352af7
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2038ed6219a94dc4285891d71ce00fd51310f3e3
ms.openlocfilehash: 402ef2a65b45d8adcf36ddae5c935c52a516c8d5


---

# Ograniczanie dostępu poczty e-mail do usługi Dynamics CRM Online przy użyciu usługi Microsoft Intune
Dostęp do usługi Microsoft Dynamics CRM Online na urządzeniach z systemem iOS i Android można kontrolować przy użyciu dostępu warunkowego usługi Microsoft Intune.  Dostęp warunkowy usługi Intune ma dwa składniki:
* [Zasady zgodności urządzenia](introduction-to-device-compliance-policies-in-microsoft-intune.md), które urządzenie musi spełniać, aby było uznawane za zgodne.
* [Zasady dostępu warunkowego](restrict-access-to-email-and-o365-services-with-microsoft-intune.md), w ramach których określane są warunki, które urządzenie musi spełniać w celu uzyskania dostępu do usługi.

Aby dowiedzieć się więcej o sposobie działania dostępu warunkowego, przeczytaj artykuł [Ograniczanie dostępu do poczty e-mail, usługi O365 i innych usług](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).

Jeśli wybrany użytkownik próbuje użyć aplikacji Dynamics CRM na swoim urządzeniu, sprawdzane są następujące kwestie:

![Diagram przedstawiający punkty decyzyjne używane do określenia, czy urządzenie ma mieć dostęp do usługi, czy ma być blokowane](../media/mdm-ca-dynamics-crm-flow-diagram.png)

Urządzenie, dla którego wymagany jest dostęp do usługi Dynamics CRM Online, musi:
* Być urządzeniem z system **Android** lub **iOS**.
* Być **zarejestrowane** w usłudze Microsoft Intune.
* Być zgodne z wszelkimi **wdrożonymi** zasadami zgodności usługi Intune.

Stan urządzenia jest przechowywany w usłudze Azure Active Directory, która na podstawie wybranych warunków blokuje dostęp lub go przydziela.

Jeśli warunek nie jest spełniony, użytkownik zobaczy podczas logowania jeden z następujących komunikatów:
* Jeśli urządzenie nie zostało zarejestrowane w usłudze Microsoft Intune lub usłudze Azure Active Directory, zostanie wyświetlony komunikat z instrukcjami dotyczącymi sposobu instalowania aplikacji portalu firmy i rejestrowania.
* Jeśli urządzenie nie jest zgodne, zostanie wyświetlony komunikat kierujący użytkownika do witryny internetowej portalu firmy usługi Intune lub aplikacji Portal firmy, gdzie można znaleźć informacje o problemie i sposobie jego rozwiązania.

## Konfigurowanie dostępu warunkowego dla usługi Dynamics CRM Online  
### Krok 1. Konfigurowanie grup zabezpieczeń usługi Active Directory

Przed rozpoczęciem skonfiguruj grupy zabezpieczeń usługi Azure Active Directory dla zasad dostępu warunkowego. Możesz skonfigurować te grupy w **centrum administracyjnym usługi Office 365**. Grupy te zostaną użyte do objęcia użytkowników zasadami lub wykluczenia użytkowników z zasad. Jeśli zasady obejmują użytkownika, każde używane przez niego urządzenie musi być zgodne, aby mógł uzyskać dostęp do zasobów.

Można określić dwa typy grup używane dla zasad usługi Dynamics CRM:
* **Grupy docelowe** — grupy użytkowników, do których zasady będą stosowane.
* **Wykluczone grupy** — grupy użytkowników, którzy są wykluczeni z zasad.

Jeśli użytkownik należy do obu grup, będzie wykluczony z zasad.

### Krok 2. Konfigurowanie i wdrażanie zasad zgodności
[Utwórz](create-a-device-compliance-policy-in-microsoft-intune.md) i [wdróż](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md) zasady zgodności na wszystkich urządzeniach, które będą objęte zasadami. Będą to wszystkie urządzenia, które są używane przez użytkowników z grup docelowych.

> [!NOTE]
> Podczas gdy zasady zgodności są wdrażane w grupach usługi Microsoft Intune, zasady dostępu warunkowego są stosowane dla grup zabezpieczeń usługi Azure Active Directory.

> [!IMPORTANT]
> Jeśli zasady zgodności nie zostały wdrożone, urządzenia będą traktowane jako zgodne.

Gdy wszystko będzie gotowe, przejdź do kroku 3.
### Krok 3. Konfigurowanie zasad usługi Dynamics CRM
Skonfiguruj zasady wymagające, aby tylko urządzenia zarządzane i zgodne miały dostęp do usługi Dynamics CRM. Te zasady będą przechowywane w usłudze Azure Active Directory.

1.  W konsoli administracyjnej usługi Microsoft Intune wybierz pozycje **Zasady > Dostęp warunkowy > Zasady usługi Dynamics CRM Online**.

  ![Zrzut ekranu przedstawiający stronę zasad dostępu warunkowego usługi Dynamics CRM Online](../media/mdm-ca-dynamics-crm-policy-configuration.png)

2.  Wybierz pozycję **Włącz zasady dostępu warunkowego**.
3.  W obszarze **Dostęp do aplikacji** możesz wybrać platformy, do których zostaną zastosowane zasady dostępu warunkowego:
  * **iOS**
  * **Android**
4.  W obszarze **Grupy docelowe** wybierz pozycję **Modyfikuj**, aby wybrać grupy zabezpieczeń usługi Azure Active Directory, do których zasady zostaną zastosowane. Możesz objąć zasadami wszystkich użytkowników lub ich wybrane grupy.
5.  W obszarze **Wykluczone grupy** możesz wybrać pozycję **Modyfikuj**, jeśli chcesz, aby zasady nie były stosowane dla wskazanych grup zabezpieczeń usługi Azure Active Directory.
6.  Gdy wszystko będzie gotowe, wybierz pozycję **Zapisz**.

Dostęp warunkowy dla usługi Dynamics CRM został skonfigurowany. Nie musisz wdrażać zasad dostępu warunkowego; są one aktywne natychmiast.
##  Monitorowanie zgodności i zasad dostępu warunkowego

W obszarze roboczym **Grupy** można przeglądać informacje o stanie warunkowego dostępu do urządzeń.

Wybierz dowolną grupę urządzeń przenośnych, a następnie na karcie **Urządzenia** wybierz jeden z następujących **filtrów**:
* **Urządzenia, które nie zostały zarejestrowane przy użyciu usługi AAD** — dostęp tych urządzeń do usługi Dynamics CRM jest zablokowany.
* **Urządzenia, które nie są zgodne** — dostęp tych urządzeń do usługi Dynamics CRM jest zablokowany.
* **Urządzenia, które zostały zarejestrowane przy użyciu usługi AAD i są zgodne** — te urządzenia mogą uzyskiwać dostęp do usługi Dynamics CRM.

##  Następne kroki
[Ograniczanie dostępu do usługi Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)

[Ograniczanie dostępu do lokalnego programu Exchange](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
[Ograniczanie dostępu do usługi SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)

[Ograniczanie dostępu do usługi Skype dla firm Online](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)



<!--HONumber=Jul16_HO4-->


