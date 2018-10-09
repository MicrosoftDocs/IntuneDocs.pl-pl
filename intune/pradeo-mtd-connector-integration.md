---
title: Konfiguracja integracji usługi Pradeo z usługą Intune
titleSuffix: Intune on Azure
description: Integracja łącznika usługi Pradeo z usługą Intune
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 82872ba6-80f8-4cc9-adf4-0ccd8ff26dd2
ms.openlocfilehash: 1f59463eeaa9926f2a4ca0d9a9b9b60dd63a8537
ms.sourcegitcommit: fffa64f28278573dc83a846b647315def2108781
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2018
ms.locfileid: "48231178"
---
# <a name="integrate-pradeo-with-intune"></a>Integracja usługi Pradeo z usługą Intune

Aby zintegrować rozwiązanie Pradeo Mobile Threat Defense z usługą Intune, wykonaj kroki opisane poniżej.

## <a name="before-you-begin"></a>Przed rozpoczęciem

> [!NOTE]
> Poniższe kroki należy wykonać w [konsoli zabezpieczeń Pradeo](https://www.apps-security.com).

Przed rozpoczęciem procesu integracji rozwiązania Pradeo z usługą Intune upewnij się, że przygotowano następujące elementy:

-   Subskrypcja usługi Microsoft Intune

-   Poświadczenia administratora usługi Azure Active Directory umożliwiające przyznanie następujących uprawnień:

    -   Logowanie i odczyt profilu użytkownika

    -   Dostęp do katalogu jako zalogowany użytkownik

    -   Odczyt danych katalogu

    -   Wysyłanie informacji o urządzeniu do usługi Intune

-   Poświadczenia administratora służące do uzyskania dostępu do konsoli zabezpieczeń Pradeo.

### <a name="pradeo-app-authorization"></a>Autoryzacja aplikacji Pradeo

Przebieg procesu autoryzacji aplikacji Pradeo jest następujący:

-   Zezwól usłudze Pradeo na przekazywanie informacji związanych z kondycją urządzenia z powrotem do usługi Intune.

-   Usługa Pradeo synchronizuje się z członkostwem grupy rejestracji usługi Azure AD, aby wypełnić bazę danych urządzeń.

-   Zezwól konsoli administratora Pradeo na używanie logowania jednokrotnego usługi Azure AD.

-   Zezwól aplikacji Pradeo na zalogowanie się przy użyciu logowania jednokrotnego usługi Azure AD.

## <a name="to-set-up-pradeo-integration"></a>Aby skonfigurować integrację usługi Pradeo

1.  Przejdź do [konsoli zabezpieczeń Pradeo](https://www.apps-security.com) i zaloguj się przy użyciu swoich poświadczeń.

2.  Wybierz pozycję **Administration - Enterprise Mobility Management** (Administracja — Zarządzanie mobilnością w przedsiębiorstwie) z menu.

3.  Wybierz **logo usługi Intune**.

4.  W oknie **EMM (Enterprise mobility management - Intune** (EMM, Zarządzanie mobilnością w przedsiębiorstwie — usługa Intune) ramach **kroku 1** wybierz przycisk **Pradeo Connector** (Łącznik Pradeo). 

    ![Okno zarządzania mobilnością w przedsiębiorstwie Pradeo w usłudze Intune](./media/pradeo_setup.png)

5. W oknie połączenia usługi Microsoft Intune wprowadź swoje poświadczenia usługi Intune.

5.  Zostanie ponownie otwarta strona internetowa Pradeo. W ramach **kroku 2** wybierz przycisk **Pradeo Device Health** (Kondycja urządzenia Pradeo).

7. W oknie łącznika usługi Intune Pradeo wybierz pozycję **Accept** (Akceptuj). 

8. W oknie łącznika interfejsu API urządzenia Pradeo wybierz pozycję **Accept** (Akceptuj).

9. Zostanie ponownie otwarta strona internetowa Pradeo. W ramach **kroku 3** wybierz przycisk **Connect to Microsoft** (Połącz z firmą Microsoft). 

10. W oknie uwierzytelniania usługi Microsoft Intune wprowadź swoje poświadczenia usługi Intune.

11. Gdy zostanie wyświetlony komunikat **Successful Integration** (Pomyślna integracja), integracja będzie zakończona.

## <a name="next-steps"></a>Następne kroki

-   [Konfiguracja aplikacji Pradeo](mtd-apps-ios-app-configuration-policy-add-assign.md)