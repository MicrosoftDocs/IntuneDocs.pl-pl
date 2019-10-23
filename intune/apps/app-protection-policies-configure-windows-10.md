---
title: Konfigurowanie zasad ochrony aplikacji dla systemu Windows 10
titleSuffix: Microsoft Intune
description: W tym temacie opisano sposób konfigurowania zasad ochrony aplikacji (APP) dla urządzeń z systemem Windows 10.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 949fddec-5318-4c9a-957e-ea260e6e05be
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: e0e1ff8fd39d301bd685e9806c319f49e9189d7f
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72507417"
---
# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a>Przygotowywanie do konfigurowania zasad ochrony aplikacji dla systemu Windows 10 

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Włącz zarządzanie aplikacjami mobilnymi (MAM) dla systemu Windows 10, ustawiając dostawcę MAM w usłudze Azure AD. Ustawienie dostawcy MAM w usłudze Azure AD umożliwia definiowanie stanu rejestracji podczas tworzenia nowych zasad funkcji Windows Information Protection (WIP) za pomocą usługi Intune. Stanem rejestracji może być albo MAM, albo zarządzanie urządzeniami przenośnymi (MDM).

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

5. Kliknij polecenie **Zapisz**.

## <a name="next-steps"></a>Następne kroki

[Tworzenie zasad ochrony aplikacji w funkcji WIP](windows-information-protection-policy-create.md)
