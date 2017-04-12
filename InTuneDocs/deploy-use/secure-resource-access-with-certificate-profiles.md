---
title: "Profile certyfikatów zapewniające dostęp do zasobów | Microsoft Docs"
description: "Bezpieczna sieć VPN, sieć Wi-Fi i dostęp do poczty e-mail przy użyciu certyfikatu zainstalowanego na każdym urządzeniu użytkownika."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8cbb8499-611d-4217-a7b4-e9b864785dd0
ms.reviewer: kmyrup
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 9cf53cb240ba14317fbb680ad4f4c40c8320506d


---

# <a name="secure-resource-access-with-certificate-profiles-in-microsoft-intune"></a>Bezpieczny dostęp do zasobów przy użyciu profilów certyfikatów w usłudze Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Po zapewnieniu użytkownikom dostępu do zasobów firmowych za pośrednictwem sieci VPN, sieci Wi-Fi lub profilów poczty e-mail możesz zabezpieczyć dostęp przy użyciu certyfikatu zainstalowanego na urządzeniu każdego użytkownika. Oto jak to działa:

1. Upewnij się, że jest dostępna właściwa infrastruktura certyfikatu, zgodna z opisem w tematach [Konfigurowanie infrastruktury certyfikatów dla profilu SCEP](configure-certificate-infrastructure-for-scep.md) i [Konfigurowanie infrastruktury certyfikatów dla profilu PFX](configure-certificate-infrastructure-for-pfx.md).

2. Zainstaluj certyfikat główny lub certyfikat pośredniego urzędu certyfikacji (CA) na każdym urządzeniu, aby urządzenia rozpoznawały urząd certyfikacji jako wiarygodny. W tym celu należy utworzyć i wdrożyć **profil zaufanego certyfikatu**. Po wdrożeniu tego profilu urządzenia zarządzane przy użyciu usługi Intune zażądają certyfikatu głównego i otrzymają go. Należy utworzyć oddzielny profil dla każdej platformy. **Profil zaufanego certyfikatu** jest dostępny dla następujących platform:
 -  System iOS 8.0 i nowsze
 -  System Mac OS X 10.9 lub nowszy
 -  Android 4.0 i nowsze
 -  Program Android for Work
 -  Windows 8.1 i nowsze
 -  System Windows Phone 8.1 lub nowszy

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

3. Utwórz profile certyfikatów, tak aby poszczególne urządzenia żądały certyfikatu do użytku podczas uwierzytelniania dostępu do poczty e-mail, sieci VPN i sieci Wi-Fi — zgodnie z opisem w temacie [Configure Intune certificate profiles](configure-intune-certificate-profiles.md) (Konfigurowanie profilów certyfikatów usługi Intune). Dla urządzeń korzystających z następujących platform można utworzyć i wdrożyć **profil certyfikatu PKCS #12 (PFX)** *albo* **profil certyfikatu protokołu SCEP**:

  -  System iOS 8.0 i nowsze
  -  Android 4.0 i nowsze
  -  Program Android for Work
  -  System Windows 10 (Desktop i Mobile) i nowsze

  Użyj **profilu certyfikatu protokołu SCEP** dla urządzeń z następującymi platformami:
    -   System Mac OS X 10.9 lub nowszy
    -   Windows Phone 8,1

Dla każdej platformy należy utworzyć oddzielny profil. Po utworzeniu certyfikatu należy go skojarzyć z utworzonym **profilem zaufanego certyfikatu głównego**.

> [!NOTE]           
> - Jeśli nie masz urzędu certyfikacji przedsiębiorstwa, musisz go utworzyć.
>- Jeśli na podstawie platform urządzeń zdecydujesz się na użycie uproszczonego protokołu rejestrowania certyfikatów (SCEP), musisz również skonfigurować serwer usługi rejestracji urządzeń sieciowych (NDES).
>-  Niezależnie od tego, czy zamierzasz używać profilów certyfikatów protokołu SCEP czy PFX, musisz pobrać i skonfigurować łącznik certyfikatów usługi Microsoft Intune.
>-  Konfiguracja wszystkich wymaganych usług została opisana w tematach [Konfigurowanie infrastruktury certyfikatów dla profilu SCEP](configure-certificate-infrastructure-for-scep.md) i [Konfigurowanie infrastruktury certyfikatów dla profilu PFX](configure-certificate-infrastructure-for-pfx.md).

### <a name="next-steps"></a>Następne kroki
- [Konfigurowanie infrastruktury certyfikatów dla profilu SCEP](configure-certificate-infrastructure-for-scep.md)
- [Konfigurowanie infrastruktury certyfikatów dla profilu PFX](configure-certificate-infrastructure-for-pfx.md)
- [Konfigurowanie profilów certyfikatów usługi Intune](configure-intune-certificate-profiles.md)



<!--HONumber=Dec16_HO2-->


