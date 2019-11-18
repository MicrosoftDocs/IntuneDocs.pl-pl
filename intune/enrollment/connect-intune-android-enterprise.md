---
title: Łączenie konta usługi Intune z kontem zarządzanego sklepu Google Play.
titleSuffix: Microsoft Intune
description: Dowiedz się, jak połączyć konto usługi Intune z kontem zarządzanego sklepu Google Play.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 5/13/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a89b94f098292bf44122d6d2d144c7f35967cd32
ms.sourcegitcommit: 556b7ea2049014c9027f0e44affd3f301fab55fc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2019
ms.locfileid: "73709456"
---
# <a name="connect-your-intune-account-to-your-managed-google-play-account"></a>Łączenie konta usługi Intune z kontem zarządzanego sklepu Google Play

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Aby obsługiwać [urządzenia z profilami służbowymi systemu Android Enterprise](android-work-profile-enroll.md), [w pełni zarządzane urządzenia z systemem Android Enterprise](android-fully-managed-enroll.md) i [urządzenia dedykowane z systemem Android Enterprise](android-kiosk-enroll.md), należy połączyć konto dzierżawy usługi Intune z kontem zarządzanego sklepu Google Play.  

Aby ułatwić Ci konfigurowanie i używanie funkcji zarządzania systemu Android Enterprise, podczas łączenia ze sklepem Google Play usługa Intune automatycznie doda do konsoli administracyjnej cztery popularne aplikacje powiązane z systemem Android Enterprise. Są to następujące cztery aplikacje w usłudze Android Enterprise:

- **[Microsoft Intune](https://play.google.com/store/apps/details?id=com.microsoft.intune)**  — używana w scenariuszach w pełni zarządzanych za pomocą Android Enterprise.
- **[Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)** — pomaga zalogować się do kont w przypadku używania weryfikacji dwuskładnikowej.
- **[Intune — Portal firmy](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)**  — używana w przypadku scenariuszy obejmujących zasady ochrony aplikacji i profil służbowy Android Enterprise.
- [Zarządzany ekran główny](https://play.google.com/store/apps/details?id=com.microsoft.launcher.enterprise) — używana w scenariuszach z użyciem Android Enterprise dla urządzeń dedykowanych/działających w trybie kiosku.

> [!NOTE]
> Ze względu na interakcję między domenami firm Google i Microsoft ten krok może wymagać dostosowania ustawień przeglądarki.  Upewnij się, że adresy „portal.azure.com” i „play.google.com” znajdują się w tej samej strefie zabezpieczeń w przeglądarce.

1. Jeśli nie zostało to jeszcze zrobione, przygotuj się do zarządzania urządzeniami mobilnymi przez [skonfigurowanie jako urzędu zarządzania urządzeniami mobilnymi](../fundamentals/mdm-authority-set.md) usługi **Microsoft Intune**.
2. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), a następnie wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja systemu Android** > **Zarządzany sklep Google Play**.  Jeśli używasz niestandardowej roli administratora usługi Intune, dostęp wymaga uprawnień odczytu i aktualizacji w organizacji.
   
   ![Ekran rejestracji w rozwiązaniu Android enterprise](./media/connect-intune-android-enterprise/android-work-bind.png)

3. Wybierz pozycję **Zgadzam się**, aby udzielić firmie Microsoft uprawnień do [wysłania informacji o użytkowniku i urządzeniu do firmy Google](../protect/data-intune-sends-to-google.md). 
   
4. Wybierz pozycję **Uruchom usługę Google, aby połączyć teraz**, aby otworzyć witrynę internetową zarządzanego sklepu Google Play. Witryna internetowa jest otwierana w nowej karcie w przeglądarce.
  
5. Na stronie logowania do usługi Google wprowadź konto Google, które zostanie skojarzone ze wszystkimi zadaniami zarządzania systemu Android Enterprise dla tej dzierżawy. Jest to konto Google używane przez administratorów IT organizacji do zarządzania aplikacjami i ich publikowania w konsoli sklepu Google Play. Możesz użyć istniejącego konta Google lub utworzyć nowe konto. Wybrane konto nie może być skojarzone z domeną G-Suite.
    
    > [!Note]
    > Jeśli używasz przeglądarki Microsoft Edge, kliknij pozycję **Zaloguj** w prawym górnym rogu, aby zalogować się do swojego konta Google.

6. Podaj nazwę firmy w polu **Organization name** (Nazwa organizacji). W polu **Enterprise mobility management (EMM) provider** (Dostawca usługi zarządzania mobilnością w przedsiębiorstwie (EMM)) powinna być wyświetlona wartość **Microsoft Intune**.

7. Zaakceptuj warunki umowy systemu Android, a następnie wybierz pozycję **Confirm** (Potwierdź). Twoje żądanie zostanie przetworzone.

## <a name="disconnect-your-android-enterprise-administrative-account"></a>Rozłączanie konta administracyjnego systemu Android Enterprise

Rejestrację systemu Android Enterprise i zarządzanie w tym systemu możesz wyłączyć. W tym celu należy najpierw wycofać wszystkie zarejestrowane urządzenia z systemem Android Enterprise, w tym urządzenia z profilem służbowym, urządzenia dedykowane i urządzenia w pełni zarządzane. Następnie wybierz pozycję **Rozłącz** w konsoli administracyjnej usługi Intune, aby usunąć wszystkie zarejestrowane urządzenia z profilem służbowym systemu Android Enterprise, urządzenia dedykowane i urządzenia w pełni zarządzane. Zostanie również usunięta relacja między kontem zarządzanego sklepu Google Play i usługą Intune.

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) jako administrator usługi Intune.
2. Wybierz pozycję **Rejestracja urządzeń** > **Rejestracja systemu Android** > **Zarządzany sklep Google Play** > **Rozłącz**.
3. Wybierz pozycję **Tak**, aby rozłączyć i wyrejestrować wszystkie urządzenia z rozwiązaniem Android enterprise z usługi Intune.

## <a name="next-steps"></a>Następne kroki

Po nawiązaniu połączenia z kontem zarządzanego sklepu Google Play możesz [skonfigurować urządzenia z profilem służbowym systemu Android Enterprise](android-work-profile-enroll.md), [skonfigurować dedykowane urządzenia z systemem Android Enterprise](android-kiosk-enroll.md) oraz [skonfigurować w pełni zarządzane urządzenia z systemem Android Enterprise](android-kiosk-enroll.md)
