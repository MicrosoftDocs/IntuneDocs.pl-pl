---
title: Wymaganie uwierzytelniania wieloskładnikowego na potrzeby rejestracji urządzeń w usłudze Intune
titlesuffix: Microsoft Intune
description: Instrukcje ustawiania wymogu uwierzytelniania wieloskładnikowego w usłudze Azure AD do celów rejestracji urządzeń w usłudze Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/10/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 94280c73-c05c-4e72-b0dd-a7cb997782f9
ROBOTS: ''
ms.custom: intune-azure
ms.openlocfilehash: 270f19b6f0babb347b04731ca270a3c5bea18217
ms.sourcegitcommit: 5e5004a31207e75e54504d74548735c048676a03
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/07/2018
ms.locfileid: "51225676"
---
# <a name="require-multi-factor-authentication-for-intune-device-enrollments"></a>Wymaganie uwierzytelniania wieloskładnikowego na potrzeby rejestracji urządzeń w usłudze Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

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
>Aby zaimplementować te zasady, należy przypisać do użytkowników usługę Azure Active Directory w warstwie Premium P1 lub wyższej.

>[!Important]
>Nie konfiguruj opcji **Reguły dostępu na podstawie urządzeń** pod kątem rejestracji w usłudze Microsoft Intune.

1. Zaloguj się do [witryny Microsoft Azure Portal](https://portal.azure.com) przy użyciu swoich poświadczeń.
2. W portalu przejdź do pozycji **[Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Overview)**.
3. W usłudze **Azure Active Directory** w obszarze Zabezpieczenia wybierz pozycję **[Dostęp warunkowy](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies)**.
4. Wybierz pozycję **Nowe zasady**.
5. W obszarze **Nowe zasady** wpisz nazwę opisową zasad.
6. W sekcji **Przypisania** wybierz pozycję **Użytkownicy i grupy**.
7. W obszarze **Użytkownicy i grupy** wybierz polecenie **Wybierz użytkowników lub grupy** i zaznacz opcję **Użytkownicy i grupy**. Następnie wybierz użytkowników lub grupy, które mają otrzymać te zasady, a następnie wybierz pozycję **Gotowe**.
8. W sekcji **Przypisania** wybierz pozycję **Aplikacje w chmurze**.
9. Na karcie **Uwzględnianie** w obszarze **Aplikacje w chmurze** wybierz pozycję **Wybierz aplikacje,**, a następnie wybierz kolejno pozycje **Wybierz** > **Rejestracja w usłudze Microsoft Intune**, a następnie wybierz pozycję **Gotowe**.
10. W sekcji **Przypisania** w obszarze**Warunki** nie musisz konfigurować ustawień usługi MFA.
11. W sekcji **Kontrole dostępu** wybierz pozycję **Udziel**.
12. W obszarze **Udzielanie** wybierz pozycję **Udziel dostępu**, a następnie wybierz pozycję **Wymagaj uwierzytelniania wieloskładnikowego**. Nie zaznaczaj pola **Wymagaj, aby urządzenie było oznaczone jako zgodne**, ponieważ nie można sprawdzić zgodności urządzenia, dopóki nie zostanie zarejestrowane. Następnie wybierz opcję **Wybierz**.
13. W obszarze **Nowe zasady** wybierz pozycję **Włącz zasady** > **Włączono**, a następnie wybierz pozycję **Utwórz**.



## <a name="next-steps"></a>Następne kroki

Gdy użytkownicy końcowi rejestrują swoje urządzenia, muszą teraz uwierzytelniać je przy użyciu drugiej formy identyfikacji, takiej jak numer PIN, telefon lub dane biometryczne.
