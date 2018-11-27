---
title: Konfigurowanie integracji z usługą Better Mobile w usłudze Intune
titleSuffix: Intune on Azure
description: Integracja łącznika usługi Better Mobile z usługą Intune
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 7/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.openlocfilehash: aa447721449b2b3733e20d9f65f0253e9123228b
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52184211"
---
# <a name="integrate-better-mobile-with-intune"></a>Integrowanie usługi Better Mobile z usługą Intune

Aby zintegrować rozwiązanie Better Mobile Threat Defense z usługą Intune, wykonaj kroki opisane poniżej.

## <a name="before-you-begin"></a>Przed rozpoczęciem

> [!NOTE]
> Poniższe kroki należy wykonać w [konsoli administracyjnej usługi Better Mobile](https://aad.bmobi.net).

Przed rozpoczęciem procesu integracji rozwiązania Better Mobile z usługą Intune upewnij się, że przygotowano następujące elementy:

-   Subskrypcja usługi Microsoft Intune

-   Poświadczenia administratora usługi Azure Active Directory umożliwiające przyznanie następujących uprawnień:

    -   Logowanie i odczyt profilu użytkownika

    -   Dostęp do katalogu jako zalogowany użytkownik

    -   Odczyt danych katalogu

    -   Wysyłanie informacji o urządzeniu do usługi Intune

-   Poświadczenia administratora umożliwiające dostęp do konsoli administracyjnej rozwiązania Better Mobile.

### <a name="better-mobile-app-authorization"></a>Autoryzacja aplikacji Better Mobile

Przebieg procesu autoryzacji aplikacji Better Mobile jest następujący:

-   Zezwól usłudze Better Mobile na przekazywanie informacji związanych z kondycją urządzenia z powrotem do usługi Intune.

-   Usługa Better Mobile synchronizuje się z członkostwem grupy rejestracji usługi Azure AD, aby wypełnić bazę danych urządzeń.

-   Zezwól konsoli administracyjnej Better Mobile na używanie logowania jednokrotnego usługi Azure AD.

-   Zezwól aplikacji Better Mobile na logowanie się przy użyciu logowania jednokrotnego usługi Azure AD.

## <a name="to-set-up-better-mobile-integration"></a>Aby skonfigurować integrację usługi Better Mobile

1. Przejdź do [konsoli administracyjnej Better Mobile](https://aad.bmobi.net) i zaloguj się przy użyciu swoich poświadczeń.
2. Wybierz kolejno pozycje **Integracja** > **EMM/MDM** > **DODAJ KONTO**.

     ![Konsola administracyjna usługi Better Mobile](media/better_mobile_console.png)
 
3. Wybierz pozycję **Intune**.
4. Obok pozycji **NAZWA KONTA** wpisz deskryptor. 
5. W oknie połączenia usługi **Logowanie Microsoft** wprowadź swoje poświadczenia usługi Intune.
6. W oknie **Żądane uprawnienia** wybierz pozycję **Zaakceptuj**.
7. Wyszukaj grupy zabezpieczeń usługi Azure AD, z których usługa Better Mobile ma synchronizować urządzenia, i wybierz je z listy. Następnie wybierz pozycję **Kontynuuj**.
8. Wybierz pozycję **Gotowe**.
9. Ponownie pojawi się strona **Dodawanie konta**. Zamknij stronę. 

## <a name="next-steps"></a>Następne kroki

-   [Konfigurowanie lepszych aplikacji klienckich](mtd-apps-ios-app-configuration-policy-add-assign.md)