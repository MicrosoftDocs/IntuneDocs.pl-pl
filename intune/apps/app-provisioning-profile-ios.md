---
title: Profile aprowizowania aplikacji systemu iOS w usłudze Microsoft Intune
titleSuffix: ''
description: Usługa Intune udostępnia narzędzia umożliwiające aktywne przypisywanie nowego profilu aprowizowania do urządzeń, na których znajdują się aplikacje bliskie wygaśnięcia.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/14/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: bbc3ba4a-df48-4aeb-988b-69a177764e3a
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c0b5f087494e8033cb9645d0a08edd4e1c481a2c
ms.sourcegitcommit: 0be25b59c8e386f972a855712fc6ec3deccede86
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2019
ms.locfileid: "72584925"
---
# <a name="use-ios-app-provisioning-profiles-to-prevent-your-apps-from-expiring"></a>Użycie profilów aprowizowania aplikacji systemu iOS w celu zapobiegania wygaśnięciu aplikacji

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

## <a name="introduction"></a>Wprowadzenie

Aplikacje biznesowe systemu Apple iOS przypisywane do urządzeń iPhone i iPad są tworzone za pomocą dołączonego profilu aprowizowania i kodu podpisywanego przy użyciu certyfikatu. Gdy aplikacja jest uruchamiana, system iOS potwierdza integralność aplikacji systemu iOS i wymusza zasady zdefiniowane przez profil aprowizacji. Następuje poniższa walidacja:

- **Integralność pliku instalacji** — system iOS porównuje szczegóły aplikacji z kluczem publicznym certyfikatu podpisywania przedsiębiorstwa. Jeśli będą się różnić, zawartość aplikacji mogła ulec zmianie. W takim przypadku aplikacji nie można uruchomić.
- **Wymuszenie możliwości** — system iOS próbuje wymusić możliwości aplikacji z firmowego profilu aprowizacji (nie profilów aprowizacji poszczególnych deweloperów) zawartego w pliku instalacyjnym aplikacji (ipa).


Certyfikat podpisywania przedsiębiorstwa używany do podpisywania aplikacji jest zwykle ważny przez 3 lata. Profil aprowizacji wygasa jednak po roku. Podczas gdy ten certyfikat jest nadal ważny, usługa Intune udostępnia narzędzia umożliwiające aktywne przypisywanie nowego profilu aprowizowania do urządzeń, na których znajdują się aplikacje bliskie wygaśnięcia.
Po wygaśnięciu certyfikatu należy ponownie podpisać aplikację przy użyciu nowego certyfikatu i osadzić nowy profil aprowizacji z kluczem nowego certyfikatu.

Jako administrator możesz dołączać lub wykluczać grupy zabezpieczeń, aby przydzielać konfigurację aprowizacji aplikacji systemu iOS. Na przykład możesz przypisać konfigurację aprowizacji aplikacji systemu iOS do wszystkich użytkowników, ale wykluczyć grupę zarządu.

## <a name="how-to-create-an-ios-mobile-app-provisioning-profile"></a>Jak utworzyć profil aprowizowania aplikacji mobilnych systemu iOS

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. W okienku **Intune** wybierz pozycję **Aplikacje klienckie** > **Profile aprowizacji aplikacji systemu iOS** > **Utwórz profil**.
3. Na stronie **Podstawowe** dodaj następujące wartości:
    - **Nazwa** — podaj nazwę dla tego profilu aprowizowania aplikacji mobilnych.
    - **Opis** — opcjonalnie wprowadź opis zasad.
    - **Przekaż plik profilu** — wybierz ikonę **Otwórz**, a następnie wybierz plik profilu konfiguracji Apple Mobile (z rozszerzeniem `.mobileprovision`) pobrany z [witryny internetowej dla deweloperów firmy Apple](https://developer.apple.com/).

   Pole **Data wygaśnięcia** zostanie wypełnione wartością z dodanego wcześniej pliku profilu konfiguracji Apple Mobile.<br>

   <img alt="Create profile - Basics" src="~/apps/media/app-provisioning-profile-ios/app-provisioning-profile-ios-01.png">

4. Kliknij przycisk **Dalej: Tagi zakresu**.<br>
   Na stronie **Tagi zakresu** można opcjonalnie skonfigurować tagi zakresu, aby określić, kto może zobaczyć profil aprowizacji aplikacji systemu iOS w usłudze Intune. Więcej informacji na temat tagów zakresu można znaleźć w artykule [Use role-based access control and scope tags for distributed IT](../fundamentals/scope-tags.md) (Używanie kontroli dostępu opartej na rolach (RBAC) i tagów zakresu w rozproszonej infrastrukturze informatycznej).
5. Kliknij przycisk **Dalej: Przypisania**.<br>
   Strona **Przypisania** umożliwia przypisanie profilu do użytkowników i urządzeń. Ważne jest, aby pamiętać, że profil można przypisać do urządzenia bez względu na to, czy jest ono zarządzane przez usługę Intune.
6. Kliknij przycisk **Dalej: Przeglądanie + tworzenie**, aby przejrzeć wartości wprowadzone dla profilu.
7. Gdy skończysz, kliknij pozycję **Utwórz**, aby utworzyć profil aprowizacji aplikacji systemu iOS w usłudze Intune. 

## <a name="next-steps"></a>Następne kroki

Przypisz profil do wymaganych urządzeń z systemem iOS. Aby uzyskać więcej informacji, wykonaj czynności opisane w temacie [Jak przypisywać profile urządzeń](../device-profile-assign.md).
