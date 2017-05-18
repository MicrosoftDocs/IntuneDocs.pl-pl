---
title: "Wdrażanie i monitorowanie zasad zgodności | Microsoft Docs"
description: "Instrukcje krok po kroku w tym temacie opisują sposób wdrażania i monitorowania zasad zgodności urządzeń."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d8f246d4-0d86-4c8b-a1bf-9977985506d8
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 59c107b9431d4e2925b13d09ab3e01a25c8351fa


---

# <a name="deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune"></a>Wdrażanie i monitorowanie zasad zgodności urządzenia w usłudze Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="deploy-a-compliance-policy"></a>Wdrażanie zasad zgodności
Wdróż [utworzone](create-a-device-compliance-policy-in-microsoft-intune.md) zasady zgodności w co najmniej jednej grupie użytkowników w Twojej organizacji. Gdy zasady zgodności są wdrażane dla użytkownika, sprawdzana jest zgodność urządzeń użytkownika.

1.  W obszarze roboczym **Zasady** wybierz zasady do wdrożenia, a następnie wybierz pozycję **Zarządzaj wdrożeniem**.
![Zrzut ekranu przedstawiający stronę zasad zgodności z opcją menu Zarządzanie wdrażaniem u góry strony](./media/intune-sa-3c-deploy-compliance-policy2.png)

2.  W oknie dialogowym **Zarządzanie wdrażaniem** wybierz co najmniej jedną grupę, w której chcesz wdrożyć zasady, a następnie wybierz pozycję **Dodaj** > **OK**.
![Zrzut ekranu przedstawiający okno dialogowe Zarządzanie wdrażaniem](./media/intune-sa-3d-deploy-compliance-policy3-Manage.png) Użyj utworzonych i zsynchronizowanych z usługą Intune grup usługi Active Directory lub utwórz te grupy ręcznie w konsoli usługi Intune. Aby dowiedzieć się więcej na temat wdrażania zasad, zobacz [Wdrażanie zasad konfiguracji](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

Podsumowanie stanu oraz alerty na stronie **Przegląd** obszaru roboczego **Zasady** umożliwiają identyfikowanie problemów z zasadami, które wymagają uwagi. Ponadto w obszarze roboczym **Pulpit nawigacyjny** jest wyświetlane podsumowanie stanu.

> [!IMPORTANT]
> Jeśli zasady zgodności nie zostaną wdrożone i włączysz zasady dostępu warunkowego do programu Exchange, wszystkie urządzenia docelowe będą miały dostęp.

## <a name="monitor-the-compliance-policy"></a>Monitorowanie zasad zgodności

#### <a name="to-view-devices-that-do-not-conform-to-a-compliance-policy"></a>Aby wyświetlić urządzenia, które nie są zgodne z zasadami zgodności

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) wybierz kolejno pozycje **Grupy** > **Wszystkie urządzenia**.

2.  Kliknij dwukrotnie nazwę urządzenia na liście urządzeń.

3.  Wybierz kartę **Zasady**, aby wyświetlić listę zasad dla tego urządzenia.

4.  Z listy rozwijanej **Filtry** wybierz pozycję **Niezgodne z zasadami zgodności**.
![Zrzut ekranu przedstawiający listę opcji na liście filtrów](./media/intune-sa-3e-view-device-noncompliance.png)

#### <a name="to-view-the-health-attestation-reports"></a>Aby wyświetlić raporty dotyczące zaświadczania o kondycji

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) wybierz opcję **Raporty**.

2.  Na stronie **Raport zaświadczania o kondycji — Utwórz nowy raport** można wyświetlić raport z wszystkimi danymi związanymi z zaświadczaniem o kondycji systemu Windows 10 zebranymi przez usługę Intune. Można również utworzyć raport z podzbiorem danych za pomocą filtrów. Filtry mogą być związane z typem urządzenia, systemem operacyjnym lub podzbiorem punktów danych.

## <a name="how-intune-resolves-policy-conflicts"></a>Jak są rozwiązywane konflikty zasad usługi Intune
Konflikty zasad mogą wystąpić, gdy na urządzeniu stosuje się wiele zasad usługi Intune. Jeśli ustawienia zasad nakładają się na siebie, usługa Intune rozwiązuje konflikty, używając następujących reguł:

-   Jeżeli sprzeczne ustawienia pochodzą z zasad konfiguracji usługi Intune i zasad zgodności, ustawienia w zasadach zgodności mają pierwszeństwo względem ustawień w zasadach konfiguracji. Dzieje się tak nawet wtedy, gdy ustawienia w zasadach konfiguracji są bardziej bezpieczne.

-   Jeśli wdrożono wiele zasad zgodności, usługa Intune użyje najbezpieczniejszych z nich.

## <a name="next-steps"></a>Następne kroki
Aby dowiedzieć się, jak stosować zasady zgodności wraz z zasadami dostępu warunkowego w celu kontrolowania dostępu do usług w organizacji, zobacz [Ograniczanie dostępu do poczty e-mail i usług O365](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).


### <a name="see-also"></a>Zobacz też
[Wprowadzenie do zasad zgodności urządzeń w usłudze Intune](introduction-to-device-compliance-policies-in-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


