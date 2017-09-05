---
title: "Uwierzytelnianie wieloskładnikowe na potrzeby rejestracji urządzeń w usłudze Intune"
titleSuffix: Intune on Azure
description: "Ustawianie wymogu uwierzytelniania wieloskładnikowego w usłudze Azure AD do celów rejestracji urządzeń."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angerobe
ms.date: 08/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 94280c73-c05c-4e72-b0dd-a7cb997782f9
ROBOTS: 
ms.custom: intune-azure
ms.openlocfilehash: 4789f94d06f61219dea3faa64a4ed0c59afcd56b
ms.sourcegitcommit: af013af8d9a63c9aa16e5e9eddf38ad9c5a77898
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2017
---
# <a name="multi-factor-authentication-for-intune-device-enrollments"></a>Uwierzytelnianie wieloskładnikowe na potrzeby rejestracji urządzeń w usłudze Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Usługa Intune może używać usługi uwierzytelniania wieloskładnikowego (MFA) w usłudze Azure Active Directory (AD) podczas rejestracji urządzeń w celu ułatwienia zabezpieczania zasobów firmowych.

Uwierzytelnianie wieloskładnikowe wymaga co najmniej dwóch poniższych metod weryfikacji:

- Coś, co wiesz (zwykle hasło lub numer PIN).
- Coś, co masz (zaufane urządzenie, którego nie można łatwo zduplikować, takie jak telefon).
- Coś Twojego (biometria, np. odcisk palca).

Usługa MFA jest obsługiwana w systemach iOS, Android, Windows 8.1 i nowszych, jak również na urządzeniach z systemem Windows Phone 8.1 Windows 10 Mobile lub nowszym.

Po włączeniu usługi MFA użytkownicy końcowi muszą podać dwie formy poświadczeń, aby zarejestrować urządzenie.

## <a name="configure-intune-to-require-multi-factor-authentication-at-device-enrollment"></a>Konfigurowanie usługi Intune pod kątem wymogu uwierzytelniania wieloskładnikowego na etapie rejestracji urządzeń

Aby ustawić wymóg uwierzytelniania wieloskładnikowego na etapie rejestracji urządzenia, wykonaj następujące kroki:

>[!Important]
>Nie konfiguruj opcji **Reguły dostępu na podstawie urządzeń** pod kątem rejestracji w usłudze Microsoft Intune.

1. Zaloguj się do [witryny Microsoft Azure Portal](https://portal.azure.com) przy użyciu swoich poświadczeń.
2. W portalu wybierz pozycję **Azure Active Directory**.
2. W obszarze **Azure Active Directory** wybierz kolejno pozycje **Zarządzaj** > **Aplikacje dla przedsiębiorstw**.
3. W obszarze **Aplikacje dla przedsiębiorstw** wybierz kolejno pozycje **Zarządzaj** > **Wszystkie aplikacje**. Możesz wyświetlić listę wszystkich aplikacji platformy Azure, którymi zarządzasz.
3. Na liście wybierz pozycję **Rejestracja w usłudze Microsoft Intune**.
4. W obszarze **Rejestracja w usłudze Microsoft Intune** wybierz kolejno pozycje **Zabezpieczenia** > **Dostęp warunkowy**.
5. Wybierz pozycję **Nowe zasady**.
6. W obszarze **Nowe zasady** wpisz nazwę opisową zasad.
7. W sekcji **Przypisania** wybierz pozycję **Użytkownicy i grupy**.
8. W obszarze **Użytkownicy i grupy** wybierz użytkowników lub grupy, które mają otrzymać te zasady, a następnie wybierz pozycję **Gotowe**.
9. W sekcji **Przypisania** wybierz pozycję **Aplikacje w chmurze**.
10. Na karcie **Uwzględnianie** w obszarze **Aplikacje w chmurze** wybierz pozycję **Wybierz aplikacje,**, a następnie wybierz kolejno pozycje **Wybierz** > **Rejestracja w usłudze Microsoft Intune**, a następnie wybierz pozycję **Gotowe**.
11. W sekcji **Przypisania** wybierz pozycję **Warunki**.
12. W obszarze **Warunki** nie musisz konfigurować ustawień usługi MFA.
13. W sekcji **Kontrole dostępu** wybierz pozycję **Udziel**.
14. W obszarze **Udzielanie** wybierz pozycję **Udziel dostępu**, a następnie wybierz pozycję **Wymagaj uwierzytelniania wieloskładnikowego**.
    Nie zaznaczaj pola **Wymagaj, aby urządzenie było oznaczone jako zgodne**, ponieważ nie można sprawdzić zgodności urządzenia, dopóki nie zostanie zarejestrowane.
15. Wybierz pozycję **Wybierz**.
16. W obszarze **Nowe zasady** wybierz pozycję **Włącz zasady** > **Włączono**, a następnie wybierz pozycję **Utwórz**.



## <a name="next-steps"></a>Następne kroki

Gdy użytkownicy końcowi rejestrują swoje urządzenia, muszą teraz uwierzytelniać je przy użyciu drugiej formy identyfikacji, takiej jak numer PIN, telefon lub dane biometryczne.