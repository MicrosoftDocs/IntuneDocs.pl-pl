---
title: "Uwierzytelnianie wieloskładnikowe na potrzeby rejestracji urządzeń w usłudze Intune | Microsoft Docs"
description: "Ustawianie wymogu uwierzytelniania wieloskładnikowego w usłudze Azure AD do celów rejestracji urządzeń."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angerobe
ms.date: 02/17/2017
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 47abdabd-dcd6-48d8-aade-3f3eefb92ee1
ROBOTS: 
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 7768013a1cc764b6dfbf4b7d22be4f5cf95f50bf
ms.openlocfilehash: dba070ef76de8015b347e760b424a5e28ce6ddec
ms.lasthandoff: 02/18/2017


---

# <a name="multi-factor-authentication-for-intune-device-enrollments"></a>Uwierzytelnianie wieloskładnikowe na potrzeby rejestracji urządzeń w usłudze Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Usługę Intune można zintegrować z usługą uwierzytelniania wieloskładnikowego (MFA) przy użyciu usługi Azure AD pod kątem rejestracji urządzeń, aby zabezpieczyć zasoby firmowe.

Uwierzytelnianie wieloskładnikowe wymaga co najmniej dwóch poniższych metod weryfikacji: 

- Coś, co wiesz (zwykle hasło lub numer PIN).
- Coś, co masz (zaufane urządzenie, którego nie można łatwo zduplikować, takie jak telefon).
- Coś, co Ciebie cechuje (biometria).

Uwierzytelnianie wieloskładnikowe jest obsługiwane w systemach iOS, Android, Windows 8.1 i nowszych, jak również na urządzeniach z systemem Windows Phone 8.1 lub nowszym.

> [!NOTE]
> W starszych wersjach programu Configuration Manager (wcześniejszych niż 1610) w konsoli administracyjnej programu Configuration Manager nadal widoczne jest ustawienie uwierzytelniania wieloskładnikowego. Nie należy próbować skonfigurować uwierzytelniania wieloskładnikowego w konsoli administracyjnej programu Configuration Manager, ponieważ nie będzie ono działać. Należy skonfigurować uwierzytelnianie wieloskładnikowe zgodnie z opisem zawartym w tym temacie.

### <a name="configure-intune-to-require-multi-factor-authentication-at-device-enrollment"></a>Konfigurowanie usługi Intune pod kątem wymogu uwierzytelniania wieloskładnikowego na etapie rejestracji urządzeń
Aby ustawić wymóg uwierzytelniania wieloskładnikowego na etapie rejestracji urządzenia, wykonaj następujące kroki:

1. Zaloguj się do [portalu usługi Microsoft Azure](https://manage.windowsazure.com) przy użyciu poświadczeń administratora.
2. Wybierz dzierżawcę.
2. Wybierz kartę **Aplikacje**. Zostanie wyświetlona lista usług, dla których można skonfigurować funkcje zabezpieczeń usługi Azure AD.
3. Wybierz opcję **Rejestracja w usłudze Microsoft Intune**.
4. Wybierz pozycję **Konfiguruj**. 
5. W obszarze **Uwierzytelnianie wieloskładnikowe i reguły dostępu na podstawie lokalizacji** można wykonywać następujące czynności:
    
    -  Włączyć reguły dostępu
    -  Określić, czy chcesz, aby reguły miały zastosowanie do wszystkich użytkowników, czy też do określonych grup zabezpieczeń w usłudze Azure AD.
    -  Wymagać uwierzytelniania wieloskładnikowego w celu przeprowadzenia rejestracji wszystkich urządzeń.
    -  Wymagać uwierzytelniania wieloskładnikowego w celu przeprowadzenia rejestracji w przypadku, gdy urządzenie nie znajduje się w miejscu pracy.
    -  Wybierz opcję **Zablokuj dostęp do zasobów firmowych**, aby zapobiec rejestracji urządzeń, które nie są podłączone do sieci firmowej. 
4. Możesz również kliknąć odpowiedni link, aby **zdefiniować/zmodyfikować firmową lokalizację sieciową** w celu skonfigurowania wymagań dotyczących łączności sieciowej pod kątem rejestracji urządzeń.

> [!IMPORTANT]
> 
> Nie należy konfigurować opcji **Reguły dostępu na podstawie urządzeń** pod kątem rejestracji w usłudze Microsoft Intune.

