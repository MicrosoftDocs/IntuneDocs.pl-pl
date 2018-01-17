---
title: "Integracja rozwiązania Zimperium z usługą Intune"
titleSuffix: Intune on Azure
description: "Integracja usługi Intune z rozwiązaniem Zimperium"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 363fd280-1865-4a61-855b-eb75c3c62753
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 515f99f694a9125d60bb9210becc6722bfb9e24f
ms.sourcegitcommit: a3a744ea55f38a360ca9f788c77a5b3018d1add5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/30/2017
---
# <a name="integrate-zimperium-with-intune"></a>Integracja rozwiązania Zimperium z usługą Intune

Aby zintegrować rozwiązanie Zimperium Mobile Threat Defense z usługą Intune, wykonaj kroki opisane poniżej.

## <a name="before-you-begin"></a>Przed rozpoczęciem

> [!NOTE]
> Poniższe kroki należy wykonać w [konsoli Zimperium MTD](https://staging2-console.zimperium.com).

Przed rozpoczęciem procesu integracji rozwiązania Zimperium z usługą Intune upewnij się, że przygotowano następujące elementy:

-   Subskrypcja usługi Microsoft Intune

-   Poświadczenia administratora usługi Azure Active Directory umożliwiające przyznanie następujących uprawnień:

    -   Logowanie i odczyt profilu użytkownika

    -   Dostęp do katalogu jako zalogowany użytkownik

    -   Odczyt danych katalogu

    -   Wysyłanie informacji o urządzeniu do usługi Intune

-   Poświadczenia administratora służące do uzyskania dostępu do konsoli Zimperium MTD.

### <a name="zimperium-app-authorization"></a>Autoryzacja aplikacji Zimperium

Następuje proces autoryzacji aplikacji Zimperium:

-   Zezwól usłudze Zimperium na przekazywanie informacji związanych z kondycją urządzenia z powrotem do usługi Intune.

-   Usługa Zimperium synchronizuje się z członkostwem grupy rejestracji usługi Azure AD, aby wypełnić bazę danych urządzeń.

-   Zezwól konsoli administratora Zimperium na używanie logowania jednokrotnego usługi Azure AD.

-   Zezwól aplikacji Zimperium na zalogowanie się przy użyciu logowania jednokrotnego usługi Azure AD.

## <a name="to-set-up-zimperium-integration"></a>Aby skonfigurować integrację rozwiązania Zimperium

1.  Przejdź do [konsoli Zimperium MTD](https://staging2-console.zimperium.com) i zaloguj się przy użyciu poświadczeń.

2.  Z menu po lewej stronie wybierz element **Zarządzanie**.

3.  Wybierz kartę **Ustawienia zarządzania urządzeniami przenośnymi**.

4.  Wybierz pozycję **Dodaj zarządzanie urządzeniami przenośnymi**, a następnie wybierz element **Microsoft Intune** z listy **Dostawcy rozwiązań do zarządzania urządzeniami przenośnymi**.

5.  Po ustawieniu usługi Microsoft Intune jako usługi zarządzania urządzeniami mobilnymi pojawia się okienko **Konfiguracja usługi Microsoft Intune**. Wybierz polecenie **Dodaj usługę Azure Active Directory** dla każdej opcji: **Zimperium zConsole** i **zIPS iOS and Android apps** (Aplikacje zIPS dla systemów iOS i Android), aby autoryzować rozwiązanie Zimperium do komunikowania się z usługami Intune i Azure AD za pomocą logowania jednokrotnego usługi Azure AD.

    > [!IMPORTANT]
    > Aby ukończyć proces integracji z usługą Intune, należy dodać rozwiązanie Zimperium zConsole i aplikacje zIPS dla systemów iOS i Android.

6.  Wybierz opcję **Akceptuj**, aby autoryzować aplikację Zimperium do komunikacji z usługami Intune i Azure Active Directory.

7.  Po dodaniu rozwiązania **Zimperium zConsole** i **aplikacji zIPS dla systemów iOS i Android** do usługi Azure AD dodaj grupy zabezpieczeń usługi Azure AD, aby rozwiązanie Zimperium mogło synchronizować grupę zabezpieczeń usługi Azure AD ze swoją usługą.

8.  Wybierz polecenie **Zakończ**, aby zapisać konfigurację i uruchomić pierwszą synchronizację grupy zabezpieczeń usługi Azure AD.

## <a name="next-steps"></a>Następne kroki

-   [Konfigurowanie aplikacji Zimperium](mtd-apps-ios-app-configuration-policy-add-assign.md)
