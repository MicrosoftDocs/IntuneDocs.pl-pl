---
title: "Integracja rozwiązania Zimperium z usługą Intune"
titleSuffix: Intune on Azure
description: "Integracja usługi Intune z rozwiązaniem Zimperium"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 09/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 363fd280-1865-4a61-855b-eb75c3c62753
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1b4adb2db14c2e1c83be8e7b3644944c1910cb97
ms.sourcegitcommit: d434dfab7ef7a6c4082d675717fa22d5581b4f51
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/19/2017
---
# <a name="integrate-zimperium-with-intune"></a>Integracja rozwiązania Zimperium z usługą Intune

Aby zintegrować rozwiązanie Zimperium Mobile Threat Defense z usługą Intune, należy wykonać kroki opisane poniżej.

## <a name="before-you-begin"></a>Przed rozpoczęciem

> [!NOTE]
> W [konsoli rozwiązania Zimperium MTD](https://staging2-console.zimperium.com) należy podjąć poniższe kroki.

Przed rozpoczęciem procesu integracji rozwiązania Zimperium z usługą Intune upewnij się, że przygotowano następujące elementy:

-   Subskrypcja usługi Microsoft Intune

-   Poświadczenia administratora usługi Azure Active Directory umożliwiające przyznanie następujących uprawnień:

    -   Logowanie i odczyt profilu użytkownika

    -   Dostęp do katalogu jako zalogowany użytkownik

    -   Odczyt danych katalogu

    -   Wysyłanie informacji o urządzeniu do usługi Intune

-   Poświadczenia administratora służące do uzyskania dostępu do konsoli Zimperium MTD.

### <a name="zimperium-app-authorization"></a>Autoryzacja aplikacji Zimperium

Proces autoryzacji aplikacji Zimperium składa się z następujących etapów:

-   Zezwól usłudze Zimperium na przekazywanie informacji związanych z kondycją urządzenia z powrotem do usługi Intune.

-   Usługa Zimperium synchronizuje się z członkostwem grupy rejestracji usługi Azure AD, aby wypełnić bazę danych urządzeń.

-   Zezwól konsoli administratora Zimperium na używanie logowania jednokrotnego usługi Azure AD.

-   Zezwól aplikacji Zimperium na zalogowanie się przy użyciu logowania jednokrotnego usługi Azure AD.

## <a name="to-set-up-zimperium-integration"></a>Aby skonfigurować integrację rozwiązania Zimperium

1.  Przejdź do [konsoli Zimperium MTD](https://staging2-console.zimperium.com) i zaloguj się przy użyciu poświadczeń.

2.  Z menu po lewej stronie wybierz element **Zarządzanie**.

3.  Wybierz kartę **Ustawienia zarządzania urządzeniami przenośnymi**.

4.  Wybierz pozycję **Dodaj zarządzanie urządzeniami przenośnymi**, a następnie wybierz element **Microsoft Intune** z listy **Dostawcy rozwiązań do zarządzania urządzeniami przenośnymi**.

5.  Po ustawieniu usługi Microsoft Intune jako dostawcy rozwiązania do zarządzania urządzeniami przenośnymi pojawia się okienko **Konfiguracja usługi Microsoft Intune**. Wybierz polecenie **Dodaj usługę Azure Active Directory** dla każdej opcji: **Zimperium zConsole** i **Aplikacje zIPS dla systemów iOS i Android**, aby autoryzować rozwiązanie Zimperium do komunikowania się z usługami Intune i Azure AD za pomocą logowania jednokrotnego usługi Azure AD.

    > [!IMPORTANT]
    > Aby ukończyć proces integracji z usługą Intune, należy dodać rozwiązanie Zimperium zConsole i aplikacje zIPS dla systemów iOS i Android.

6.  Wybierz opcję **Akceptuj**, aby autoryzować aplikację Zimperium do komunikacji z usługami Intune i Azure Active Directory.

7.  Po dodaniu rozwiązania **Zimperium zConsole** i **aplikacji zIPS dla systemów iOS i Android** do usługi Azure AD należy dodać grupy zabezpieczeń usługi Azure AD, aby rozwiązanie Zimperium mogło synchronizować grupę zabezpieczeń usługi Azure AD ze swoją usługą.

8.  Wybierz polecenie **Zakończ**, aby zapisać konfigurację i uruchomić pierwszą synchronizację grupy zabezpieczeń usługi Azure AD.

## <a name="next-steps"></a>Następne kroki

-   [Konfigurowanie aplikacji Zimperium](mtd-apps-ios-app-configuration-policy-add-assign.md)
