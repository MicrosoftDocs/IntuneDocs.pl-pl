---
title: "Azure Portal — zasady zarządzania aplikacjami mobilnymi | Microsoft Intune"
description: "Utwórz zasady zarządzania aplikacjami mobilnymi za pomocą witryny Azure Portal. Zasady tworzone w tym miejscu można zastosować do urządzeń z rejestracją lub bez rejestracji w usłudze Intune."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7d6dae94-a833-40b7-9016-14ea234bb33c
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9eb7e79bee2bc36dffab97ffdb6f665218bc739e
ms.openlocfilehash: 0acef421f179ebf922ec8af71ba336e3e5f96bd2


---

# Azure Portal — zasady zarządzania aplikacjami mobilnymi
## Korzystanie z witryny Azure Portal
Witryna Azure Portal pozwala tworzyć zasady zarządzania aplikacjami mobilnymi oraz zarządzać tymi zasadami.

Portal Azure obsługuje tworzenie zasad zarządzania aplikacjami mobilnymi dla następujących składników:
- Aplikacje działające na urządzeniach **zarejestrowanych w usłudze Intune i zarządzanych przez tę usługę**.
- Aplikacje działające na urządzeniach, które **nie są zarejestrowane** w żadnym rozwiązaniu do zarządzania aplikacjami mobilnymi
- Aplikacje działające na urządzeniach, które **są zarejestrowane w rozwiązaniu do zarządzania aplikacjami mobilnymi innej firmy**.

>[!IMPORTANT]

> Jeśli używasz konsoli administracyjnej usługi Intune do zarządzania urządzeniami, możesz utworzyć zasady zarządzania aplikacjami mobilnymi obsługujące aplikacje dla urządzeń zarejestrowanych w usłudze Intune przy użyciu [konsoli administracyjnej usługi Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).

> W konsoli administracyjnej usługi Intune mogą nie być wyświetlane wszystkie ustawienia zasad zarządzania aplikacjami mobilnymi. Witryna Azure Portal to nowa konsola administracyjna do tworzenia zasad zarządzania aplikacjami mobilnymi. Jeśli utworzysz zasady zarządzania aplikacjami mobilnymi zarówno za pomocą konsoli administracyjnej usługi Intune, jak i witryny Azure Portal, zasady utworzone w witrynie Azure Portal zostaną zastosowane dla aplikacji i wdrożone dla użytkowników.

## Zaloguj się do witryny Azure Portal i dostosuj swoją stronę początkową

1.  Przejdź do witryny [Azure Portal](https://portal.azure.com) i zaloguj się przy użyciu swoich poświadczeń usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

    ![Zrzut ekranu przedstawiający stronę logowania się do witryny Azure Portal](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  Po zalogowaniu pojawi się strona **Pulpit nawigacyjny**. Stronę **Pulpit nawigacyjny** można dostosować.

    ![Zrzut ekranu pulpitu nawigacyjnego portalu Azure](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  W menu **Przeglądaj** znajdź pozycję **Intune**.![Zrzut ekranu przedstawiający menu Przeglądaj z wyróżnioną pozycją Intune](../media/AppManagement/AzurePortal_MAM_Browse_Intune.png)

4.  Wybierz pozycję **Intune** > **Zarządzanie aplikacjami mobilnymi w usłudze Intune** > **Ustawienia**.

    ![Zrzut ekranu przedstawiający blok zarządzania aplikacjami mobilnymi usługi Intune](../media/AppManagement/AzurePortal_MAM_Mainblade.png)

    > [!TIP]
    > Kliknij ikonę przypinania w bloku **Zarządzanie aplikacjami mobilnymi usługi Intune**, aby przypiąć go do strony **Start**.

    ![Zrzut ekranu przedstawiający blok zarządzania aplikacjami mobilnymi usługi Intune z wyróżnioną ikoną przypinania](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Zrzut ekranu pulpitu nawigacyjnego z przypiętym kafelkiem usługi Intune](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)
## Następne kroki
[Przygotowywanie się do konfigurowania zasad zarządzania aplikacjami mobilnymi](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO3-->


