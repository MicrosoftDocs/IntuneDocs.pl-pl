---
title: Łączenie konta usługi Intune z kontem rozwiązania Android enterprise
titlesuffix: Microsoft Intune
description: Dowiedz się, jak połączyć konto usługi Intune z kontem rozwiązania Android enterprise.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 6/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 698bc4e7e2d2cf8ece1b1c17b091a91c76a7d178
ms.sourcegitcommit: 911923e9fe0eed52b1c93e400f776956835e582f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/17/2019
ms.locfileid: "54386886"
---
# <a name="connect-your-intune-account-to-your-android-enterprise-account"></a>Łączenie konta usługi Intune z kontem rozwiązania Android enterprise

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Aby obsługiwać [urządzenia z profilami służbowymi](android-work-profile-enroll.md), [w pełni zarządzane urządzenia](android-fully-managed-enroll.md) i [urządzenia dedykowane](android-kiosk-enroll.md) z systemem Android, należy połączyć konto dzierżawy usługi Intune ze swoim kontem rozwiązania Android enterprise.  

> [!NOTE]
> Ze względu na interakcję między domenami firm Google i Microsoft ten krok może wymagać dostosowania ustawień przeglądarki.  Upewnij się, że adresy „portal.azure.com” i „play.google.com” znajdują się w tej samej strefie zabezpieczeń w przeglądarce.

1. Jeśli nie zostało to jeszcze zrobione, przygotuj się do zarządzania urządzeniami mobilnymi przez [skonfigurowanie jako urzędu zarządzania urządzeniami mobilnymi](mdm-authority-set.md) usługi **Microsoft Intune**.
2. Zaloguj się do [usługi Intune w witrynie Azure Portal](https://aka.ms/intuneportal), a następnie wybierz pozycję **Rejestrowanie urządzenia** > **Rejestrowanie systemu Android** > **Zarządzany sklep Google Play**.  Jeśli używasz niestandardowej roli administratora usługi Intune, dostęp wymaga uprawnień odczytu i aktualizacji w organizacji.
   
   ![Ekran rejestracji w rozwiązaniu Android enterprise](./media/android-work-bind.png)

3. Wybierz pozycję **Zgadzam się**, aby udzielić firmie Microsoft uprawnień do [wysłania informacji o użytkowniku i urządzeniu do firmy Google](data-intune-sends-to-google.md). 
   
4. Wybierz pozycję **Uruchom usługę Google, aby połączyć teraz**, aby otworzyć witrynę internetową zarządzanego sklepu Google Play. Witryna internetowa jest otwierana w nowej karcie w przeglądarce.
  
5. Na stronie logowania do usługi Google wprowadź konto Google, które zostanie skojarzone ze wszystkimi zadaniami zarządzania rozwiązania Android enterprise dla tej dzierżawy. Jest to konto Google używane przez administratorów IT organizacji do zarządzania aplikacjami i ich publikowania w konsoli sklepu Google Play. Możesz użyć istniejącego konta Google lub utworzyć nowe konto. Wybrane konto nie może być skojarzone z domeną G-Suite.
    
    > [!Note]
    > Jeśli używasz przeglądarki Microsoft Edge, kliknij pozycję **Zaloguj** w prawym górnym rogu, aby zalogować się do swojego konta Google.

6. Podaj nazwę firmy w polu **Organization name** (Nazwa organizacji). W polu **Enterprise mobility management (EMM) provider** (Dostawca usługi zarządzania mobilnością w przedsiębiorstwie (EMM)) powinna być wyświetlona wartość **Microsoft Intune**.

7. Zaakceptuj warunki umowy systemu Android, a następnie wybierz pozycję **Confirm** (Potwierdź). Twoje żądanie zostanie przetworzone.

## <a name="disconnect-your-android-enterprise-administrative-account"></a>Rozłączanie konta administracyjnego rozwiązania Android enterprise

Rejestrację rozwiązania Android enterprise i zarządzanie w ramach niego możesz wyłączyć. Aby to zrobić, należy najpierw wycofać wszystkie zarejestrowane urządzenia z profilem służbowym systemu Android. Następnie wybierz pozycję **Rozłącz** w konsoli administracyjnej usługi Intune, aby usunąć wszystkie zarejestrowanych urządzenia z profilem służbowym systemu Android z rejestracji. Usunięte zostaną również relacje między kontem rozwiązania Android enterprise a usługą Intune.

1. Jako administrator usługi Intune wybierz w witrynie [Azure Portal](https://portal.azure.com) pozycję **Wszystkie usługi** > **Monitorowanie i zarządzanie** > **Intune**.
2. Wybierz pozycję **Rejestracja urządzeń** > **Rejestracja systemu Android** > **Zarządzany sklep Google Play** > **Rozłącz**.
3. Wybierz pozycję **Tak**, aby rozłączyć i wyrejestrować wszystkie urządzenia z rozwiązaniem Android enterprise z usługi Intune.

## <a name="next-steps"></a>Następne kroki

Po nawiązaniu połączenia z kontem rozwiązania Android enterprise możesz [skonfigurować urządzenia z profilem służbowym systemu Android](android-work-profile-enroll.md) i [skonfigurować urządzenia kiosku z systemem Android](android-kiosk-enroll.md).
