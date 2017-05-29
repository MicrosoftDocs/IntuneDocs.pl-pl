---
title: Profile aprowizowania aplikacji | Microsoft Docs
description: "Usługa Intune udostępnia narzędzia umożliwiające aktywne wdrażanie nowych zasad profilu aprowizowania na urządzeniach, na których znajdują się aplikacje bliskie wygaśnięcia."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 86fbe736-7bdb-4f5e-ae21-13c91eb2462c
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: adebcc5a8d8f43bed383b51bb094fa122ebabc0a
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---

# <a name="use-ios-mobile-provisioning-profile-policies-to-prevent-your-apps-from-expiring"></a>Użyj zasad profilów aprowizacji aplikacji mobilnych systemu iOS, aby zapobiec wygaśnięciu aplikacji

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Aplikacje biznesowe systemu Apple iOS wdrażane na urządzeniach iPhone i iPad są tworzone za pomocą dołączonego profilu aprowizacji i kodu podpisywanego przy użyciu certyfikatu. Gdy aplikacja jest uruchamiana, system iOS potwierdza integralność aplikacji systemu iOS i wymusza zasady zdefiniowane przez profil aprowizacji. Następuje poniższa walidacja:

- **Integralność pliku instalacji** — system iOS porównuje szczegóły aplikacji z kluczem publicznym certyfikatu podpisywania przedsiębiorstwa. Jeśli będą się różnić, zawartość aplikacji mogła ulec zmianie. W takim przypadku aplikacji nie będzie można uruchomić.
- **Wymuszenie możliwości** — system iOS próbuje wymusić możliwości aplikacji z firmowego profilu aprowizacji (nie profilów aprowizacji poszczególnych deweloperów) zawartego w pliku instalacyjnym aplikacji (ipa).


Certyfikat podpisywania przedsiębiorstwa używany do podpisywania aplikacji jest zwykle ważny przez 3 lata. Profil aprowizacji wygasa jednak po roku. Podczas gdy ten certyfikat jest nadal ważny, usługa Intune udostępnia narzędzia umożliwiające aktywne wdrażanie nowych zasad profilu aprowizacji na urządzeniach, na których znajdują się aplikacje bliskie wygaśnięcia.
Po wygaśnięciu certyfikatu należy ponownie podpisać aplikację przy użyciu nowego certyfikatu i osadzić nowy profil aprowizacji z kluczem nowego certyfikatu.



## <a name="how-to-find-out-when-a-line-of-business-app-will-expire"></a>Jak ustalić, kiedy wygasa aplikacja biznesowa

1. W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) wybierz pozycję **Aplikacje** > **Aplikacje**.
2. Na liście aplikacji przyjrzyj się kolumnie **Data wygaśnięcia**, aby zobaczyć datę wygaśnięcia aplikacji. Możesz również ustawić listę rozwijaną **Filtry** na opcję **Wygasłe/wkrótce wygasną**, aby zobaczyć tylko te aplikacje, dla których należy podjąć odpowiednie działania.

## <a name="how-to-create-an-ios-mobile-provisioning-profile-policy"></a>Tworzenie zasad profilu aprowizacji aplikacji mobilnych dla systemu iOS


1. W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) kliknij pozycję **Zasady** > **Przegląd** > **Dodaj zasady**.
2. W oknie dialogowym **Tworzenie nowych zasad** wybierz pozycję **iOS** > **Zasady profilu aprowizacji aplikacji mobilnych**, a następnie wybierz opcję **Utwórz zasady**.
3. Na stronie **Ogólne** skonfiguruj następujące wartości:
    - **Nazwa** — podaj nazwę dla tych zasad profilu aprowizacji aplikacji mobilnych.
    - **Opis** — opcjonalnie wprowadź opis zasad.
    - **Plik profilu konfiguracji** — kliknij przycisk **Importuj**, a następnie wybierz plik profilu konfiguracji Apple Mobile (z rozszerzeniem **mobileprovision**) pobrany z witryny dla deweloperów firmy Apple.
4. Gdy wszystko będzie gotowe, wybierz pozycję **Zapisz zasady**.
5. Następnie przeprowadź wdrożenie zasad na wybranych urządzeniach z systemem iOS. Aby uzyskać dodatkowe informacje, zobacz [Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

