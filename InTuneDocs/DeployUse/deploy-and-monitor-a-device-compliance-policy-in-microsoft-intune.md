---
title: "Wdrażanie i monitorowanie zasad zgodności | Microsoft Intune"
description: "Instrukcje krok po kroku w tym temacie opisują sposób wdrażania i monitorowania zasad zgodności urządzeń."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d8f246d4-0d86-4c8b-a1bf-9977985506d8
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 711e650086d7528f26d9ba7b447ecb0185faff23
ms.openlocfilehash: 8658df1fb9932fb2cab984a13557aad684569df5


---

# Wdrażanie i monitorowanie zasad zgodności urządzenia w usłudze Microsoft Intune
## Wdrażanie zasad zgodności
Wdróż [utworzone](create-a-device-compliance-policy-in-microsoft-intune.md) zasady zgodności w co najmniej jednej grupie użytkowników w Twojej organizacji. Gdy zasady zgodności są wdrażane dla użytkownika, sprawdzana jest zgodność urządzeń użytkownika.

1.  W obszarze roboczym **Zasady** wybierz zasady do wdrożenia, a następnie wybierz pozycję **Zarządzaj wdrożeniem**.
![Zrzut ekranu przedstawiający stronę zasad zgodności z opcją menu Zarządzanie wdrażaniem u góry strony](./media/intune-sa-3c-deploy-compliance-policy2.png)

2.  W oknie dialogowym **Zarządzanie wdrażaniem** wybierz co najmniej jedną grupę, w której chcesz wdrożyć zasady, a następnie wybierz pozycje **Dodaj > OK**.
![Zrzut ekranu okna dialogowego zarządzania wdrażaniem](./media/intune-sa-3d-deploy-compliance-policy3-Manage.png) Zasady zgodności można wdrożyć dla użytkowników. Użyj utworzonych i zsynchronizowanych z usługą Intune grup usługi Active Directory lub utwórz te grupy ręcznie w konsoli usługi Intune. Aby dowiedzieć się więcej na temat wdrażania zasad, zobacz [Wdrażanie zasad konfiguracji](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

Podsumowanie stanu oraz alerty na stronie **Przegląd** obszaru roboczego **Zasady** umożliwiają zidentyfikowanie problemów z zasadami, które wymagają Twojej uwagi. Ponadto w obszarze roboczym **Pulpit nawigacyjny** jest wyświetlane podsumowanie stanu.

> [!IMPORTANT]
> Jeśli zasady zgodności nie zostaną wdrożone i włączysz zasady dostępu warunkowego do programu Exchange, wszystkie objęte nimi urządzenia będą miały dostęp.

## Jak są rozwiązywane konflikty zasad usługi Intune
Konflikty zasad mogą wystąpić z powodu zastosowania wielu zasad usługi Intune na urządzeniu. Jeśli ustawienia zasad nakładają się na siebie, usługa Intune rozwiązuje konflikty, używając następujących reguł:

-   Jeżeli sprzeczne ustawienia pochodzą z zasad konfiguracji usługi Intune i zasad zgodności, ustawienia w zasadach zgodności mają pierwszeństwo względem ustawień w zasadach konfiguracji, nawet jeśli ustawienia w zasadach konfiguracji są bardziej bezpieczne.

-   Jeśli wdrożono wiele zasad zgodności, używane będą najbezpieczniejsze z nich.

## Monitorowanie zasad zgodności

#### Aby wyświetlić urządzenia, które nie są zgodne z zasadami zgodności

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) wybierz pozycje **Grupy > Wszystkie urządzenia**.

2.  Kliknij dwukrotnie nazwę urządzenia na liście urządzeń.

3.  Wybierz kartę **Zasady**, aby wyświetlić listę zasad dla tego urządzenia.

4.  Z listy rozwijanej **Filtry** wybierz pozycję **Niezgodne z zasadami zgodności**.
![Zrzut ekranu przedstawiający listę opcji na liście filtrów](./media/intune-sa-3e-view-device-noncompliance.png)

#### Aby wyświetlić raporty dotyczące zaświadczania kondycji

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) wybierz opcję **Raporty**.

2.  Na stronie **Raport dotyczący zaświadczania kondycji — Utwórz nowy raport** można wyświetlić raport z wszystkimi danymi związanymi z zaświadczaniem kondycji systemu Windows 10 zbieranymi przez usługę Intune. Można również utworzyć raport z podzbiorem danych za pomocą filtrów. Filtry mogą być związane z typem urządzenia, systemem operacyjnym lub podzbiorem punktów danych.


## Następne kroki
Teraz możesz zacząć stosować zasady zgodności wraz z zasadami dostępu warunkowego w celu kontrolowania dostępu do usług w Twojej organizacji.

[Ograniczanie dostępu do usługi poczty e-mail i usługi O365](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)


### Zobacz także
[Wprowadzenie do zasad zgodności urządzeń w usłudze Intune](introduction-to-device-compliance-policies-in-microsoft-intune.md)



<!--HONumber=Aug16_HO3-->


