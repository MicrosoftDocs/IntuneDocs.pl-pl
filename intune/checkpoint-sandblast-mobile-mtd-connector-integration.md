---
title: Rozwiązanie Check Point SandBlast MTD w usłudze Microsoft Intune
titlesuffix: ''
description: Jak skonfigurować rozwiązanie CheckPoint SandBlast Mobile Threat Defense (MTD) za pomocą usługi Microsoft Intune w celu kontrolowania dostępu urządzeń przenośnych do zasobów firmy.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/03/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1e9b1576-b239-48cc-a672-da6b5fb7be0a
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 6c0c9db9955c8fbf08e5a17d3a1f9fb3fdba2cd5
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52184526"
---
# <a name="integrate-check-point-sandblast-mobile-with-intune"></a>Integracja aplikacji mobilnej Check Point SandBlast Mobile z usługą Intune

## <a name="before-you-begin"></a>Przed rozpoczęciem

> [!NOTE] 
> Poniższe kroki należy wykonać w [konsoli MTD rozwiązania Check Point SandBlast Mobile](https://intune-4.eu1.locsec.net/).

Przed rozpoczęciem procesu integracji aplikacji mobilnej Check Point SandBlast Mobile z usługą Intune upewnij się, że przygotowano następujące elementy:

-   Subskrypcja usługi Microsoft Intune

-   Poświadczenia administratora usługi Azure Active Directory umożliwiające przyznanie następujących uprawnień:

    -   Logowanie i odczyt profilu użytkownika

    -   Dostęp do katalogu jako zalogowany użytkownik

    -   Odczyt danych katalogu

    -   Wysyłanie informacji o urządzeniu do usługi Intune

-   Poświadczenia administratora umożliwiające dostęp do konsoli MTD aplikacji mobilnej Check Point SandBlast Mobile.

### <a name="check-point-sandblast-app-authorization"></a>Autoryzacja aplikacji Check Point SandBlast

Proces autoryzacji aplikacji Check Point SandBlast składa się z następujących etapów:

-   Zezwól usłudze Check Point SandBlast Mobile na przekazywanie informacji związanych z kondycją urządzenia z powrotem do usługi Intune.

-   Usługa CheckPoint SandBlast Mobile synchronizuje się z członkostwem grupy rejestracji usługi Azure AD, aby wypełnić bazę danych urządzeń.

-   Zezwól konsoli administratora Check Point SandBlast na używanie logowania jednokrotnego usługi Azure AD.

-   Zezwól aplikacji mobilnej Check Point SandBlast Mobile na logowanie przy użyciu logowania jednokrotnego usługi Azure AD.

## <a name="to-set-up-check-point-sandblast-mobile-integration"></a>Aby skonfigurować integrację rozwiązania Check Point SandBlast Mobile

1.  Przejdź do [konsoli MTD rozwiązania Check Point SandBlast Mobile](https://intune-4.eu1.locsec.net/) i zaloguj się przy użyciu swoich poświadczeń.

2.  Kliknij kartę **Ustawienia**.

3.  Wybierz opcję **Zarządzanie urządzeniami**, a następnie **Ustawienia**.

4.  Wybierz usługę **Microsoft Intune** z listy rozwijanej **Usługa MDM**.

5.  Po ustawieniu usługi Microsoft Intune jako usługi MDM zostanie otwarte okno **Konfiguracja usługi Microsoft Intune**. Wybierz opcję **Dodaj do mojej organizacji** dla każdej platformy urządzeń: iOS, Android i Windows, aby autoryzować rozwiązanie Check Point SandBlast Mobile do komunikacji z usługą Intune i Azure AD.

    ![Obraz przedstawiający konfigurację usługi Check Point MTD w usłudze Intune](./media/checkpoint-MTD-1.PNG)

    > [!IMPORTANT]
    > Musisz dodać wszystkie platformy urządzeń, aby przejść do kolejnego kroku.

6.  Wybierz opcję **Akceptuj**, aby autoryzować aplikację mobilną Check Point SandBlast Mobile do komunikacji z usługą Intune i Azure Active Directory.

7.  Po włączeniu wszystkich platform urządzeń musisz wprowadzić grupę zabezpieczeń usługi Azure AD.

8.  Wybierz opcję **Weryfikuj**. Po pomyślnym zweryfikowaniu grupy zabezpieczeń usługi Azure AD wybierz opcję **Zapisz**.

## <a name="next-steps"></a>Następne kroki

- [Konfiguracja aplikacji Check Point SandBlast Mobile](mtd-apps-ios-app-configuration-policy-add-assign.md)