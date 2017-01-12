---
title: "Uwierzytelnianie wieloskładnikowe przy użyciu usługi Azure AD| Microsoft Docs"
description: "Ustawianie wymogu uwierzytelniania wieloskładnikowego w usłudze Azure AD do celów rejestracji urządzeń."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angerobe
ms.date: 12/12/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 47abdabd-dcd6-48d8-aade-3f3eefb92ee1
ROBOTS: 
translationtype: Human Translation
ms.sourcegitcommit: 85462d6cb5e3dc6ce8e94fe8fd1bc1c1c2b6e4f3
ms.openlocfilehash: 6e20eca60886781ae884107a224245639c5f107c


---

# <a name="multi-factor-authentication-for-microsoft-intune"></a>Uwierzytelnianie wieloskładnikowe dla usługi Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Usługę Intune można zintegrować z usługą uwierzytelniania wieloskładnikowego (MFA) przy użyciu usługi Azure AD pod kątem rejestracji urządzeń, aby zabezpieczyć zasoby firmowe. Usługa MFA wymaga — oprócz nazw użytkowników i haseł— składników uwierzytelniania, takich jak uwierzytelnianie tekstowe. Ta funkcja jest obsługiwana w systemach iOS, Android, Windows 8.1 i nowszych, jak również w urządzeniach z systemem Windows Phone 8.1 i nowszymi systemami.

> [!NOTE]
>
> Jest to nowa wersja usługi MFA dla usługi Intune. Starsza wersja, z której są migrowani klienci, została opisana w artykule [Ochrona urządzeń z systemem Windows za pomocą uwierzytelniania wieloskładnikowego](protect-windows-devices-with-multi-factor-authentication.md).
>
> W starszych wersjach programu Configuration Manager (wcześniejszych niż 1610) w konsoli administracyjnej programu Configuration Manager nadal widoczne jest ustawienie uwierzytelniania wieloskładnikowego. Nie należy próbować skonfigurować uwierzytelniania wieloskładnikowego w konsoli administracyjnej programu Configuration Manager, ponieważ nie będzie ono działać. Należy skonfigurować uwierzytelnianie wieloskładnikowe zgodnie z opisem zawartym w tym temacie.

### <a name="configuring-intune-to-require-multi-factor-authentication-at-device-enrollment"></a>Konfigurowanie usługi Intune pod kątem wymogu uwierzytelniania wieloskładnikowego na etapie rejestracji urządzeń
Aby ustawić wymóg uwierzytelniania wieloskładnikowego na etapie rejestracji urządzeń, wykonaj następujące kroki:

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



<!--HONumber=Dec16_HO3-->


