---
title: Przygotowywanie do konfigurowania zasad ochrony aplikacji dla systemu Windows 10
titleSuffix: Microsoft Intune
description: Konfigurowanie dostawcy zarządzania aplikacjami mobilnymi (MAM) w usłudze Azure AD.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 949fddec-5318-4c9a-957e-ea260e6e05be
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a394b3b218613459d993b84fcb0ea7a37d4ac4dd
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/17/2018
---
# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a>Przygotowywanie do konfigurowania zasad ochrony aplikacji dla systemu Windows 10 

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Włącz zarządzanie aplikacjami mobilnymi (MAM) dla systemu Windows 10, ustawiając dostawcę MAM w usłudze Azure AD. Ustawienie dostawcy MAM w usłudze Azure AD umożliwia definiowanie stanu rejestracji podczas tworzenia nowych zasad funkcji Windows Information Protection (WIP) za pomocą usługi Intune. Stanem rejestracji może być albo MAM, albo zarządzanie urządzeniami przenośnymi (MDM).

> [!NOTE]
> Urządzenia ze stanem rejestracji MAM muszą być dołączone do usługi Azure AD.

## <a name="to-configure-the-mam-provider"></a>Aby skonfigurować dostawcę MAM

1. Zaloguj się w witrynie Azure Portal i wybierz pozycję **Azure Active Directory**.

2. Wybierz pozycję **Mobilność (zarządzanie urządzeniami przenośnymi i aplikacjami mobilnymi)** w grupie **Zarządzanie**.

3. Kliknij pozycję **Microsoft Intune**.

4. Skonfiguruj ustawienia w grupie **Przywróć domyślne adresy URL funkcji zarządzania aplikacjami przenośnymi** w bloku **Konfigurowanie**.

   **Zakres użytkownika funkcji zarządzania aplikacjami mobilnymi**  
   Automatyczna rejestracja w usłudze MAM umożliwia zarządzanie danymi przedsiębiorstwa na należących do pracowników urządzeniach z systemem Windows. Automatyczna rejestracja w usłudze MAM zostanie skonfigurowana na potrzeby scenariuszy obejmujących przynoszenie własnego urządzenia.<ul><li>**Brak**<br>Wybierz tę opcję, jeśli żaden użytkownik nie może zostać zarejestrowany w usłudze MAM.</li><li>**Niektóre**<br>Wybierz grupy usługi Azure AD zawierające użytkowników, którzy zostaną zarejestrowani w usłudze MAM.</li><li>**Wszystkie**<br>Wybierz tę opcję, jeśli wszyscy użytkownicy mogą rejestrować się w usłudze MAM.</li></ul>

   **Adres URL warunków użytkowania usługi zarządzania aplikacjami mobilnymi**  
   Adres URL warunków użytkowania usługi zarządzania aplikacjami mobilnymi nie jest obsługiwany w przypadku usługi Microsoft Intune. Aby zasady ochrony zostały zastosowane, to pole wejściowe musi pozostać puste.

   **Adres URL odnajdywania usługi zarządzania aplikacjami mobilnymi**  
   Adres URL punktu końcowego rejestracji usługi MAM. Punkt końcowy rejestracji umożliwia rejestrowanie urządzeń na potrzeby zarządzania w usłudze MAM.

   **Adres URL informacji o zgodności usługi zarządzania aplikacjami mobilnymi**  
   Adres URL informacji o zgodności usługi zarządzania aplikacjami mobilnymi nie jest obsługiwany w przypadku usługi Microsoft Intune. Aby zasady ochrony zostały zastosowane, to pole wejściowe musi pozostać puste. 

5.  Kliknij polecenie **Zapisz**.

## <a name="next-steps"></a>Następne kroki

[Tworzenie zasad ochrony aplikacji w funkcji WIP](windows-information-protection-policy-create.md)
