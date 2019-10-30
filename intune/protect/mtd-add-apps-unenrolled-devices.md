---
title: Dodawanie aplikacji usługi Mobile Threat Defense do niezarejestrowanych urządzeń
titleSuffix: Microsoft Intune
description: Dodawanie aplikacji usługi Mobile Threat Defense do niezarejestrowanych urządzeń przez ich użytkowników.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: f8dd7127594a0e23c85b9f8141ce6d398d9a447a
ms.sourcegitcommit: 06a1fe83fd95c9773c011690e8520733e1c031e3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2019
ms.locfileid: "72794462"
---
# <a name="add-mobile-threat-defense-apps-to-unenrolled-devices"></a>Dodawanie aplikacji usługi Mobile Threat Defense do niezarejestrowanych urządzeń

Domyślnie w przypadku korzystania z zasad ochrony aplikacji usługi Intune w ramach usługi Mobile Threat Defense usługa Intune prowadzi użytkownika końcowego na urządzeniu przez kroki instalowania i logowania dla wszystkich wymaganych aplikacji, aby umożliwić nawiązywanie połączeń z odpowiednimi usługami.

Użytkownicy końcowi potrzebują aplikacji Microsoft Authenticator (iOS), aby zarejestrować swoje urządzenie, oraz aplikacji Mobile Threat Defense (Android i iOS), aby odbierać powiadomienia o znalezieniu zagrożenia na urządzeniu przenośnym i wskazówki dotyczące korygowania zagrożeń.

Opcjonalnie można użyć usługi Intune do dodawania i wdrażania aplikacji Microsoft Authenticator i Mobile Threat Defense (MTD).

> [!NOTE] 
> Ten artykuł dotyczy wszystkich partnerów usługi Mobile Threat Defense, którzy obsługują zasady ochrony aplikacji: Better Mobile (Android), Zimperium (iOS), Lookout for Work (Android/iOS).
> 
> W przypadku niezarejestrowanych urządzeń **nie potrzebujesz zasad konfiguracji aplikacji systemu iOS**, które konfigurują aplikację Mobile Threat Defense dla systemu iOS używaną z usługą Intune. Jest to kluczowa różnica w porównaniu do urządzeń zarejestrowanych w usłudze Intune. 

## <a name="configure-microsoft-authenticator-for-ios-via-intune-optional"></a>Konfigurowanie aplikacji Microsoft Authenticator dla systemu iOS za pośrednictwem usługi Intune (opcjonalnie)
W przypadku korzystania z zasad ochrony aplikacji usługi Intune w połączeniu z usługą Mobile Threat Defense usługa Intune prowadzi użytkownika końcowego przez proces instalowania, logowania i rejestrowania urządzenia za pomocą aplikacji Microsoft Authenticator (iOS).

Jednak jeśli aplikacja ma być dostępna dla użytkowników końcowych za pośrednictwem aplikacji Intune — Portal firmy, zapoznaj się z instrukcjami dotyczącymi [dodawania aplikacji ze sklepu dla systemu iOS do usługi Microsoft Intune](../apps/store-apps-ios.md). Użyj tego [adresu URL aplikacji Microsoft Authenticator w sklepie App Store dla systemu iOS](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) podczas wykonywania działań opisanych w sekcji **Konfigurowanie informacji o aplikacji**. Nie zapomnij o [przypisaniu aplikacji do grup za pomocą usługi Intune](../apps/apps-deploy.md) w ramach ostatniego kroku.

> [!NOTE] 
> W przypadku urządzeń z systemem iOS konieczna jest aplikacja [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to), aby tożsamości użytkowników mogły być sprawdzane przez usługę Azure AD. Portal firmy usługi Intune działa na urządzeniach z systemem Android jako broker, aby tożsamości użytkowników mogły być sprawdzane przez usługę Azure AD.

## <a name="making-mobile-threat-defense-apps-available-via-intune-optional"></a>Udostępnianie aplikacji usługi Mobile Threat Defense za pośrednictwem usługi Intune (opcjonalnie)
W przypadku korzystania z zasad ochrony aplikacji usługi Intune w połączeniu z usługą Mobile Threat Defense usługa Intune prowadzi użytkownika końcowego przez proces instalowania i logowania do wymaganej aplikacji klienckiej usługi Mobile Threat Defense. 

Jednak jeśli aplikacja ma być dostępna dla użytkowników końcowych za pośrednictwem aplikacji Intune — Portal firmy, możesz wykonać poniższe kroki w [witrynie Azure Portal](https://portal.azure.com/). Upewnij się, że znasz następujące procesy:

- [Dodawanie aplikacji w usłudze Intune](../apps/apps-add.md).
- [Przypisywanie aplikacji za pomocą usługi Intune](../apps/apps-deploy.md).

### <a name="making-lookout-for-work-available-to-end-users"></a>Udostępnianie aplikacji Lookout for Work użytkownikom końcowym
- **Android**  
  - Zapoznaj się z instrukcjami dotyczącymi [dodawania aplikacji w sklepie dla systemu Android do usługi Microsoft Intune](../apps/store-apps-android.md). Użyj tego [adresu URL aplikacji Lookout for Work w Sklepie Play](https://play.google.com/store/apps/details?id=com.lookout.enterprise) podczas wykonywania działań opisanych w sekcji **Konfigurowanie informacji o aplikacji**.

- **iOS**
  - Zapoznaj się z instrukcjami dotyczącymi [dodawania aplikacji w sklepie dla systemu iOS do usługi Microsoft Intune](../apps/store-apps-ios.md). Użyj tego [adresu URL aplikacji Lookout for Work w sklepie App Store dla systemu iOS](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8) podczas wykonywania działań opisanych w sekcji **Konfigurowanie informacji o aplikacji**.

<!-- ### Making Symantec Endpoint Protection Mobile available to end users
- **Android**
  - See the instructions for [adding Android store apps to Microsoft Intune](../apps/store-apps-android.md). When completing the **Configure app information** section, use this [SEP Mobile app store URL](https://play.google.com/store/apps/details?id=com.skycure.skycure). For **Minimum operating system**, select **Android 4.0 (Ice Cream Sandwich)**.

- **iOS**
  - See the instructions for [adding iOS store apps to Microsoft Intune](../apps/store-apps-ios.md). Use this [SEP Mobile - App Store URL](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) when completing the **Configure app information** section.

### Making Check Point SandBlast Mobile available to end users
- **Android**  
  - See the instructions for [adding Android store apps to Microsoft Intune](../apps/store-apps-android.md). Use this [Check Point SandBlast Mobile - Play Store URL](https://play.google.com/store/apps/details?id=com.lacoon.security.fox) when completing the **Configure app information** section. 

- **iOS**
  - See the instructions for [adding iOS store apps to Microsoft Intune](../apps/store-apps-ios.md). Use this [Check Point SandBlast Mobile - App Store URL](https://apps.apple.com/us/app/sandblast-mobile-protect/id1006390797) when completing the **Configure app information** section. -->

### <a name="making-zimperium-available-to-end-users"></a>Udostępnianie usługi Zimperium użytkownikom końcowym
<!-- - **Android**
  - See the instructions for [adding Android store apps to Microsoft Intune](../apps/store-apps-android.md). Use this [Zimperium - Play Store URL](https://play.google.com/store/apps/details?id=com.zimperium.zips&hl=en) when completing the **Configure app information** section. -->
- **iOS**
  - Zapoznaj się z instrukcjami dotyczącymi [dodawania aplikacji w sklepie dla systemu iOS do usługi Microsoft Intune](../apps/store-apps-ios.md). Użyj tego [adresu URL aplikacji Zimperium w sklepie App Store](https://itunes.apple.com/us/app/zimperium-zips/id1030924459?mt=8) podczas wykonywania działań opisanych w sekcji **Konfigurowanie informacji o aplikacji**.
 
<!-- ### Making Pradeo available to end users
- **Android**
  - See the instructions for [adding Android store apps to Microsoft Intune](../apps/store-apps-android.md). Use this [Pradeo - Play Store URL](https://play.google.com/store/apps/details?id=net.pradeo.service&hl=en_US) when completing the **Configure app information** section.

- **iOS**
  - See the instructions for [adding iOS store apps to Microsoft Intune](../apps/store-apps-ios.md). Use this [Pradeo - App Store URL](https://itunes.apple.com/us/app/pradeo-agent/id547979360?mt=8) when completing the **Configure app information** section. -->

### <a name="making-better-mobile-available-to-end-users"></a>Udostępnianie aplikacji Better Mobile użytkownikom końcowym 
- **Android**
  - Zapoznaj się z instrukcjami dotyczącymi [dodawania aplikacji w sklepie dla systemu Android do usługi Microsoft Intune](../apps/store-apps-android.md). Użyj tego [adresu URL aplikacji Active Shield w Sklepie Play](https://play.google.com/store/apps/details?id=com.better.active.shield.enterprise) podczas wykonywania działań opisanych w sekcji **Konfigurowanie informacji o aplikacji**.
<!-- - **iOS**
  - See the instructions for [adding iOS store apps to Microsoft Intune](../apps/store-apps-ios.md). Use this [ActiveShield - App Store URL](https://itunes.apple.com/us/app/activeshield/id980234260?mt=8&uo=4) when completing the **Configure app information** section. -->

<!-- ### Making Sophos available to end users
- **Android**
  - See the instructions for [adding Android store apps to Microsoft Intune](../apps/store-apps-android.md). Use this [Sophos - Play Store URL](https://play.google.com/store/apps/details?id=com.sophos.smsec) when completing the **Configure app information** section.

- **iOS**
  - See the instructions for [adding iOS store apps to Microsoft Intune](../apps/store-apps-ios.md). Use this [ActiveShield - App Store URL](https://itunes.apple.com/us/app/sophos-mobile-security/id1086924662?mt=8) when completing the **Configure app information** section.

### Making Wandera available to end users
- **Android**
  - See the instructions for [adding Android store apps to Microsoft Intune](../apps/store-apps-android.md). Use this [Wandera Mobile - Play Store URL](https://play.google.com/store/apps/details?id=com.wandera.android) when completing the **Configure app information** section. For **Minimum operating system**, select **Android 5.0**.

- **iOS**
  - See the instructions for [adding iOS store apps to Microsoft Intune](../apps/store-apps-ios.md). Use this [Wandera Mobile - - App Store URL](https://itunes.apple.com/app/wandera/id605469330) when completing the **Configure app information** section. -->

## <a name="next-steps"></a>Następne kroki  

- [Włączanie łącznika usługi Mobile Threat Defense dla niezarejestrowanych urządzeń w usłudze Intune](~/protect/mtd-enable-unenrolled-devices.md)

