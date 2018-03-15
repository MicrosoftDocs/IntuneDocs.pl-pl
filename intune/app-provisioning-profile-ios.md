---
title: "Profile aprowizowania aplikacji systemu iOS w usłudze Microsoft Intune"
titlesuffix: 
description: "Usługa Intune udostępnia narzędzia umożliwiające aktywne przypisywanie nowego profilu aprowizowania do urządzeń, na których znajdują się aplikacje bliskie wygaśnięcia."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbc3ba4a-df48-4aeb-988b-69a177764e3a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7637dcb3aba4f46a3e97c8de47d974b46af27b47
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/05/2018
---
# <a name="use-ios-mobile-provisioning-profiles-in-intune-to-prevent-your-apps-from-expiring"></a>Użycie profilów aprowizowania aplikacji mobilnych systemu iOS w usłudze Intune w celu zapobiegania wygaśnięciu aplikacji

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="introduction"></a>Wprowadzenie

Aplikacje biznesowe systemu Apple iOS przypisywane do urządzeń iPhone i iPad są tworzone za pomocą dołączonego profilu aprowizowania i kodu podpisywanego przy użyciu certyfikatu. Gdy aplikacja jest uruchamiana, system iOS potwierdza integralność aplikacji systemu iOS i wymusza zasady zdefiniowane przez profil aprowizacji. Następuje poniższa walidacja:

- **Integralność pliku instalacji** — system iOS porównuje szczegóły aplikacji z kluczem publicznym certyfikatu podpisywania przedsiębiorstwa. Jeśli będą się różnić, zawartość aplikacji mogła ulec zmianie. W takim przypadku aplikacji nie można uruchomić.
- **Wymuszenie możliwości** — system iOS próbuje wymusić możliwości aplikacji z firmowego profilu aprowizacji (nie profilów aprowizacji poszczególnych deweloperów) zawartego w pliku instalacyjnym aplikacji (ipa).


Certyfikat podpisywania przedsiębiorstwa używany do podpisywania aplikacji jest zwykle ważny przez 3 lata. Profil aprowizacji wygasa jednak po roku. Podczas gdy ten certyfikat jest nadal ważny, usługa Intune udostępnia narzędzia umożliwiające aktywne przypisywanie nowego profilu aprowizowania do urządzeń, na których znajdują się aplikacje bliskie wygaśnięcia.
Po wygaśnięciu certyfikatu należy ponownie podpisać aplikację przy użyciu nowego certyfikatu i osadzić nowy profil aprowizacji z kluczem nowego certyfikatu.


## <a name="how-to-create-an-ios-mobile-app-provisioning-profile"></a>Jak utworzyć profil aprowizowania aplikacji mobilnych systemu iOS

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie + zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Aplikacje mobilne**.
1.  W obciążeniu **Aplikacje mobilne** wybierz kolejno pozycje **Zarządzanie** > **Profile aprowizacji aplikacji systemu iOS**.
2.  W okienku listy profilów wybierz pozycję **Utwórz profil**.
3. W okienku **Tworzenie profilu** skonfiguruj następujące wartości:
    - **Nazwa** — podaj nazwę dla tego profilu aprowizowania aplikacji mobilnych.
    - **Opis** — opcjonalnie wprowadź opis zasad.
    - **Przekaż plik profilu** — wybierz przycisk **Importuj**, a następnie wybierz plik profilu konfiguracji Apple Mobile (z rozszerzeniem **.mobileprovision**) pobrany z witryny dla deweloperów firmy Apple.
4. Po wykonaniu tych czynności wybierz przycisk **Utwórz**.

## <a name="next-steps"></a>Następne kroki

Przypisz profil do wymaganych urządzeń z systemem iOS. Aby uzyskać więcej informacji, wykonaj czynności opisane w temacie [Jak przypisywać profile urządzeń](device-profile-assign.md).
