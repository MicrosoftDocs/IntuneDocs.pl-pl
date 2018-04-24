---
title: Profile aprowizowania aplikacji
description: Usługa Intune udostępnia narzędzia umożliwiające aktywne wdrażanie nowych zasad profilu aprowizowania na urządzeniach, na których znajdują się aplikacje bliskie wygaśnięcia.
keywords: ''
author: mattbriggs
ms.author: mabrigg
manager: dougeby
ms.date: 12/27/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 86fbe736-7bdb-4f5e-ae21-13c91eb2462c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 8d55531dab4b6904fc9552f2be3ac7444073d0d7
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="use-ios-mobile-provisioning-profile-policies-to-prevent-your-apps-from-expiring"></a>Użyj zasad profilów aprowizacji aplikacji mobilnych systemu iOS, aby zapobiec wygaśnięciu aplikacji

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

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
