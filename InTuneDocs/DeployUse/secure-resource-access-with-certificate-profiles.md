---
title: "Profile certyfikatów zapewniające dostęp do zasobów | Microsoft Intune"
description: "Bezpieczna sieć VPN, sieć Wi-Fi i dostęp do poczty e-mail przy użyciu certyfikatu zainstalowanego na każdym urządzeniu użytkownika."
keywords: 
author: Nbigman
manager: angrobe
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8cbb8499-611d-4217-a7b4-e9b864785dd0
ms.reviewer: kmyrup
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 300df17fd5844589a1e81552d2d590aee5615897
ms.openlocfilehash: 98c32f924b60734d9a592ebdd7e00429dc32af26


---

# Bezpieczny dostęp do zasobów przy użyciu profilów certyfikatów w usłudze Microsoft Intune
Po włączeniu dostępu do zasobów firmowych za pośrednictwem sieci VPN, sieci Wi-Fi lub profilów poczty e-mail możesz zabezpieczyć dostęp przy użyciu certyfikatu zainstalowanego na urządzeniu każdego użytkownika. Oto jak to działa:

1. Upewnij się, że jest dostępna właściwa infrastruktura certyfikatu, zgodna z opisem w temacie [Konfigurowanie infrastruktury certyfikatów dla profilu SCEP](configure-certificate-infrastructure-for-scep.md) lub [Konfigurowanie infrastruktury certyfikatów dla profilu PFX](configure-certificate-infrastructure-for-pfx.md).

2. Zainstaluj certyfikat główny (lub certyfikat pośredniego urzędu certyfikacji) na każdym urządzeniu, aby urządzenia rozpoznawały urząd certyfikacji jako wiarygodny. W tym celu należy utworzyć i wdrożyć **profil zaufanego certyfikatu**. Po wdrożeniu tego profilu urządzenia zarządzane przy użyciu usługi Intune zażądają certyfikatu głównego i otrzymają go. Należy utworzyć oddzielny profil dla każdej platformy. **Profil zaufanego certyfikatu** jest dostępny dla następujących platform:
 -  System iOS 7.1 lub nowszy
 -  System Mac OS X 10.9 lub nowszy
 -  Android 4.0 i nowsze
 -  Windows 8.1 i nowsze
 -  System Windows Phone 8.1 lub nowszy

3. Dla poszczególnych urządzeń zażądaj certyfikatu, który będzie używany do uwierzytelniania dostępu do poczty e-mail, sieci VPN i sieci Wi-Fi — zgodnie z opisem w temacie [Configure intune certificate profiles](configure-intune-certificate-profiles.md) (Konfigurowanie profilów certyfikatów usługi Intune). Dla urządzeń z następującymi platformami można utworzyć i wdrożyć **profil certyfikatu PKCS #12 (PFX)** albo **profil certyfikatu protokołu SCEP**:

-  Android 4.0 i nowsze
-  System iOS 7.1 lub nowszy
-  System Windows 10 (Desktop i Mobile) i nowsze

**Profil certyfikatu protokołu SCEP** powinien być używany dla następujących systemów:
-   System Mac OS X 10.9 lub nowszy
-   System Windows Phone 8.1 lub nowszy

Należy utworzyć oddzielny profil dla każdej platformy. Po utworzeniu certyfikatu należy skojarzyć go z utworzonym **profilem zaufanego certyfikatu głównego**.

> [!NOTE]           
> -    Jeśli nie masz urzędu certyfikacji przedsiębiorstwa, musisz go utworzyć.
>- Jeśli na podstawie platform urządzeń zdecydujesz się na użycie prostego protokołu rejestrowania certyfikatów (SCEP), musisz również skonfigurować serwer usługi rejestracji urządzeń sieciowych (NDES).
>-  Niezależnie od tego, czy zamierzasz używać protokołu SCEP czy profilów PFX, musisz pobrać i skonfigurować łącznik certyfikatów usługi Microsoft Intune.
> Konfiguracja wszystkich tych elementów jest opisana w tematach [Konfigurowanie infrastruktury certyfikatów dla profilu SCEP](configure-certificate-infrastructure-for-scep.md) i [Konfigurowanie infrastruktury certyfikatów dla profilu PFX](configure-certificate-infrastructure-for-pfx.md).

### Następne kroki
- [Konfigurowanie infrastruktury certyfikatów dla profilu SCEP](configure-certificate-infrastructure-for-scep.md)
- [Konfigurowanie infrastruktury certyfikatów dla profilu PFX](configure-certificate-infrastructure-for-pfx.md)
- [Konfigurowanie profilów certyfikatów usługi Intune](configure-intune-certificate-profiles.md)



<!--HONumber=Jul16_HO4-->


