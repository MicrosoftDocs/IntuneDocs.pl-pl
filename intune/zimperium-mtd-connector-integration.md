---
title: Integracja rozwiązania Zimperium MTD z usługą Microsoft Intune
titleSuffix: Microsoft Intune
description: Jak skonfigurować rozwiązanie Zimperium Mobile Threat Defense (MTD) za pomocą usługi Microsoft Intune w celu kontrolowania dostępu urządzeń przenośnych do zasobów firmy.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/04/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 363fd280-1865-4a61-855b-eb75c3c62753
ms.reviewer: davidra
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3eb18c45f81e427f1d14ce77086e0d7684994e82
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/15/2019
ms.locfileid: "67884160"
---
# <a name="integrate-zimperium-with-intune"></a>Integracja rozwiązania Zimperium z usługą Intune

Aby zintegrować rozwiązanie Zimperium Mobile Threat Defense z usługą Intune, wykonaj kroki opisane poniżej.

## <a name="before-you-begin"></a>Przed rozpoczęciem

> [!NOTE]
> Poniższe kroki należy wykonać w [konsoli Zimperium MTD](https://www.zimperium.com/platform).

Przed rozpoczęciem procesu integracji rozwiązania Zimperium z usługą Intune upewnij się, że przygotowano następującą subskrypcję i poświadczenia:

- Subskrypcja usługi Microsoft Intune

- Poświadczenia administratora globalnego usługi Azure Active Directory umożliwiające przyznanie następujących uprawnień:

  - Logowanie i odczyt profilu użytkownika

  - Dostęp do katalogu jako zalogowany użytkownik

  - Odczyt danych katalogu

  - Wysyłanie informacji o urządzeniu do usługi Intune

- Poświadczenia administratora służące do uzyskania dostępu do konsoli Zimperium MTD.

### <a name="zimperium-app-authorization"></a>Autoryzacja aplikacji Zimperium

Następuje proces autoryzacji aplikacji Zimperium:

- Udziel usłudze Zimperium uprawnień do przekazywania informacji związanych z kondycją urządzenia z powrotem do usługi Intune. Aby udzielić tych uprawnień, należy użyć poświadczeń administratora globalnego. Udzielanie uprawnień jest operacją jednorazową. Po udzieleniu uprawnień poświadczenia administratora globalnego nie są wymagane do codziennych operacji.

- Usługa Zimperium synchronizuje się z członkostwem grupy rejestracji usługi Azure Active Directory (AD), aby zapełnić bazę danych urządzeń.

- Zezwól konsoli administratora Zimperium na używanie logowania jednokrotnego usługi Azure AD.

- Zezwól aplikacji Zimperium na zalogowanie się przy użyciu logowania jednokrotnego usługi Azure AD.

Aby uzyskać więcej informacji na temat zgody i aplikacji usługi Azure Active Directory, zobacz [Request the permissions from a directory admin](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#request-the-permissions-from-a-directory-admin) (Żądanie uprawnień od administratora katalogu) w artykule dotyczącym usługi Azure Active Directory *Permissions and consent in the Azure Active Directory v2.0 endpoint* (Uprawnienia i zgoda w punkcie końcowym usługi Azure Active Directory w wersji 2.0).


## <a name="to-set-up-zimperium-integration"></a>Aby skonfigurować integrację rozwiązania Zimperium

1. Przejdź do [konsoli Zimperium MTD](https://www.zimperium.com/platform) i zaloguj się przy użyciu poświadczeń. Aby przeprowadzić proces konfiguracji integracji rozwiązania Zimperium, należy zalogować się jako użytkownik usługi Azure Active Directory, który ma przypisaną rolę administratora globalnego. Podczas tej jednorazowej operacji konfiguracji prawa administratora globalnego są używane w celu udzielenia uprawnień dla aplikacji Zimperium do komunikacji z usługą Intune w organizacji. 

2. Z menu po lewej stronie wybierz element **Zarządzanie**.

3. Wybierz kartę **Ustawienia zarządzania urządzeniami przenośnymi**.

4. Wybierz pozycję **Dodaj zarządzanie urządzeniami przenośnymi**, a następnie wybierz element **Microsoft Intune** z listy **Dostawcy rozwiązań do zarządzania urządzeniami przenośnymi**.

5. Po ustawieniu usługi Microsoft Intune jako usługi MDM zostanie wyświetlone okno**Konfiguracja usługi Microsoft Intune**. Wybierz opcję **Dodaj usługę Azure Active Directory** dla każdej opcji: **Zimperium zConsole**, **Aplikacje zIPS dla systemów iOS i Android**, aby autoryzować rozwiązanie Zimperium do komunikowania się z usługami Intune i Azure AD za pomocą logowania jednokrotnego usługi Azure AD.

    > [!IMPORTANT]  
    > Aby ukończyć proces integracji z usługą Intune, należy dodać rozwiązanie Zimperium zConsole i aplikacje zIPS dla systemów iOS i Android.

6. Wybierz opcję **Akceptuj**, aby autoryzować aplikację Zimperium do komunikacji z usługami Intune i Azure Active Directory.

7. Po dodaniu rozwiązania **Zimperium zConsole** i **aplikacji zIPS dla systemów iOS i Android** do usługi Azure AD dodaj grupy zabezpieczeń usługi Azure AD. To dodanie umożliwi rozwiązaniu Zimperium synchronizację grupy zabezpieczeń usługi Azure AD z jej usługą.

8. Wybierz polecenie **Zakończ**, aby zapisać konfigurację i uruchomić pierwszą synchronizację grupy zabezpieczeń usługi Azure AD.

9. Wyloguj się z konsoli rozwiązania Zimperium MTD.

## <a name="next-steps"></a>Następne kroki

- [Konfigurowanie aplikacji Zimperium](mtd-apps-ios-app-configuration-policy-add-assign.md)
