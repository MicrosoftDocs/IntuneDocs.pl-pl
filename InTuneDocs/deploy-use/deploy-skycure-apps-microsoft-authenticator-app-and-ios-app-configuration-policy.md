---
title: "Wdrażanie aplikacji Skycure, aplikacji Microsoft Authenticator i zasad konfiguracji systemu iOS | Dokumentacja firmy Microsoft"
description: "Wdróż aplikacje Skycure, aplikację Microsoft Authenticator i zasady konfiguracji systemu iOS w klasycznej konsoli usługi Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45826fbc-6df5-41b2-8e80-d1353f904b43
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e10453155343bb7fd91a4fd3874d393ef78d0b1a
ms.openlocfilehash: 0b6f9bde77b5b88cc66ab10419b7d6e083f7cb6b
ms.lasthandoff: 04/25/2017


---

# <a name="deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy"></a>Wdrażanie aplikacji Skycure, aplikacji Microsoft Authenticator i zasad konfiguracji systemu iOS

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="before-you-begin"></a>Przed rozpoczęciem

-   Poniższe kroki należy wykonać w [klasycznej konsoli usługi Intune](https://manage.microsoft.com/).

-   Użyj tego samego konta usługi Azure AD, które zostało wcześniej skonfigurowane w konsoli zarządzania Skycure. Powinno to być konto używane podczas logowania się do klasycznej konsoli usługi Intune.

-   Upewnij się, że znasz następujące procesy:

    -   [Wdrażanie aplikacji za pomocą usługi Intune](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune).

    -   [Wdrażanie zasad konfiguracji aplikacji systemu iOS](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

## <a name="to-deploy-skycure-apps-microsoft-authenticator-app-and-the-ios-app-configuration-policy"></a>Aby wdrożyć aplikacje Skycure, aplikację Microsoft Authenticator i zasady konfiguracji aplikacji systemu iOS

1.  W klasycznej konsoli usługi Intune wybierz opcję **Aplikacje** &gt; **Aplikacje**, aby wyświetlić listę aplikacji, którymi można zarządzać.

2.  Wybierz następujące aplikacje:

    a.  Microsoft Authenticator

    b.  Aplikacja Skycure dla systemu Android

    c.  Aplikacja Skycure dla systemu iOS

       ![Wszystkie aplikacje klasycznej konsoli usługi Intune do wdrożenia](../media/mtp/skycure-deploy-app-1.png)

3.  Wybierz opcję **Zarządzaj wdrożeniami,** wskaż grupę zabezpieczeń usługi Azure AD obejmującą użytkowników programu Skycure, a następnie kliknij przycisk **Dalej**.

4.  Na stronie **Akcja wdrażania** z listy rozwijanej **Zatwierdzenie** wybierz opcję **Wymagana instalacja**, a następnie kliknij przycisk **Dalej**.

    ![Akcja wdrażania klasycznej konsoli usługi Intune](../media/mtp/skycure-deploy-app-2.png)

5.  Na stronie **Profil sieci VPN** z listy rozwijanej **Zasady sieci VPN** wybierz opcję **Brak**, a następnie kliknij przycisk **Dalej**.

6.  Na stronie **Konfiguracja aplikacji mobilnej** wybierz zasady konfiguracji aplikacji systemu iOS utworzone wcześniej na podstawie listy rozwijanej **Zasady konfiguracji aplikacji**, a następnie kliknij przycisk **Zakończ**.

    ![Konfiguracja aplikacji mobilnej klasycznej konsoli usługi Intune](../media/mtp/skycure-deploy-app-3.png)

## <a name="next-steps"></a>Następne kroki

[Konfiguracja integracji z programem Skycure w usłudze Intune](https://docs.microsoft.com/intune/deploy-use/setup-the-skycure-integration-with-Intune)

