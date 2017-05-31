---
title: "Azure Portal — zasady zarządzania aplikacjami mobilnymi | Microsoft Docs"
description: "Utwórz zasady zarządzania aplikacjami mobilnymi za pomocą witryny Azure Portal. Zasady tworzone w tym miejscu można zastosować do urządzeń z rejestracją lub bez rejestracji w usłudze Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7d6dae94-a833-40b7-9016-14ea234bb33c
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: e7fd0a83e21d499da39bd65502d8981bc3b1f61c
ms.contentlocale: pl-pl
ms.lasthandoff: 05/31/2017


---

# <a name="azure-portal-for-intune-app-protection-policies"></a>Witryna Azure Portal dla zasad ochrony aplikacji usługi Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Witryna Azure Portal służy do tworzenia zasad ochrony aplikacji oraz zarządzania tymi zasadami w odniesieniu do następujących aplikacji:

- Aplikacje działające na urządzeniach **zarejestrowanych w usłudze Intune i zarządzanych przez tę usługę**.

- Aplikacje działające na urządzeniach, które **nie są zarejestrowane** w żadnym rozwiązaniu do zarządzania aplikacjami mobilnymi
- Aplikacje działające na urządzeniach, które **są zarejestrowane w rozwiązaniu do zarządzania aplikacjami mobilnymi innej firmy**.

>[!IMPORTANT]
> Witryna Azure Portal to nowa konsola administracyjna służąca do tworzenia zasad ochrony aplikacji. Jednak dla scenariuszy zarządzania urządzeniami przenośnymi istnieje także możliwość utworzenia zasad ochrony aplikacji, które będą obsługiwać aplikacje dla urządzeń zarejestrowanych w usłudze Intune, za pomocą [konsoli administracyjnej usługi Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).

> W konsoli administracyjnej usługi Intune mogą nie być wyświetlane wszystkie dostępne ustawienia zasad ochrony aplikacji. Ponadto w przypadku utworzenia zasad ochrony aplikacji zarówno w konsoli administracyjnej usługi Intune, jak i w witrynie Azure Portal, zasady utworzone w konsoli administracyjnej usługi Intune zostaną przesłonięte przez zasady utworzone w witrynie Azure Portal. W tym scenariuszu zasady ochrony aplikacji z witryny Azure Portal będą stosowane do aplikacji i wdrażane dla użytkowników.


## <a name="sign-in-to-the-azure-portal-and-customize-your-start-page"></a>Zaloguj się do witryny Azure Portal i dostosuj swoją stronę początkową

1.  Przejdź do witryny [Azure Portal](https://portal.azure.com) i zaloguj się przy użyciu swoich poświadczeń usługi Intune.

    ![Zrzut ekranu przedstawiający stronę logowania się do witryny Azure Portal](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  Po pomyślnym zalogowaniu pojawi się strona **Pulpit nawigacyjny**. Stronę **Pulpit nawigacyjny** można dostosować.

    ![Zrzut ekranu pulpitu nawigacyjnego portalu Azure](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  W menu po lewej stronie wybierz pozycję **Więcej usług**, a następnie w filtrze pola tekstowego wpisz **Intune**.

    ![Zrzut ekranu przedstawiający menu Przeglądaj z wyróżnioną pozycją Intune](../media/AppManagement/MAM-Azure-Portal-1.png)

4.  Wybierz pozycję **Ochrona aplikacji usługi Intune** > **Zarządzanie aplikacjami mobilnymi w usłudze Intune** > **Wszystkie ustawienia**.

    ![Zrzut ekranu przedstawiający blok zarządzania aplikacjami mobilnymi usługi Intune](../media/AppManagement/MAM-Azure-Portal-2.png)

5. (Opcjonalnie): Aby przypiąć blok do strony **Start**, możesz użyć opcji **przypinania** w bloku. Kliknij ikonę przypinania w **bloku zarządzania aplikacjami mobilnymi usługi Intune**, aby przypiąć go do strony **Start**.

    ![Zrzut ekranu przedstawiający blok zarządzania aplikacjami mobilnymi usługi Intune z wyróżnioną ikoną przypinania](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Zrzut ekranu pulpitu nawigacyjnego z przypiętym kafelkiem usługi Intune](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)

## <a name="next-steps"></a>Następne kroki
[Przygotowywanie do konfigurowania zasad ochrony aplikacji](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)

