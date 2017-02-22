---
title: "Konfigurowanie ustawień edukacyjnych usługi Intune dla systemu iOS | Wersja zapoznawcza usługi Intune Azure | Dokumentacja firmy Microsoft"
description: "Wersja zapoznawcza usługi Intune Azure: informacje o ustawieniach, których można użyć do kontroli ustawień edukacyjnych na urządzeniach z systemem iOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 44c427f8-0f22-43c2-8c29-e0f9fa533b1f
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3f05e0018fb202ab5774e935c3f59855e4aa2e75
ms.openlocfilehash: e52fdf8c30a680d62071cd31e308dd0180e8b9dc


---

# <a name="how-to-configure-intune-education-settings-for-ios-devices-in-intune-azure-preview"></a>Jak skonfigurować ustawienia edukacyjne usługi dla urządzeń z systemem iOS w wersji zapoznawczej usługi Intune Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


## <a name="create-a-device-profile-containing-ios-education-settings"></a>Tworzenie profilu urządzenia zawierającego ustawienia edukacyjne dla systemu iOS

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno pozycje **Więcej usług** > **Inne** > **Intune**.
3. W bloku **Intune** wybierz pozycję **Konfiguruj urządzenia**.
2. W bloku **Konfiguracja urządzeń** wybierz kolejno pozycje **Zarządzaj** > **Profile**.
3. W bloku profilów wybierz pozycję **Utwórz profil**.
4. W bloku **Utwórz profil** uzupełnij pola **Nazwa** i **Opis** odnoszące się do profilu uaktualnienia wersji.
5. Z listy rozwijanej **Platforma** wybierz pozycję **iOS**.
6. Z listy rozwijanej **Typ profilu** wybierz pozycję **Edukacja**.
7. W bloku **Edukacja** wybierz następujące pozycje:
    - **Plik certyfikatu głównego nauczyciela**
    - **Profil PKCS12/PFX nauczyciela**
    - **Plik certyfikatu głównego ucznia lub studenta**
    - **Profil PKCS12/PFX ucznia lub studenta**
8. Gdy skończysz, wróć do bloku **Utwórz profil** i wybierz pozycję **Utwórz**.

Profil zostanie utworzony i wyświetlony w bloku listy profilów.



<!--HONumber=Feb17_HO1-->


