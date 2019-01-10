---
title: Dodawanie i przypisywanie aplikacji usługi MTD do usługi Microsoft Intune | Microsoft Intune
description: Użyj usługi Intune, aby dodać aplikacje usługi Mobile Threat Defense (MTD), aplikację Microsoft Authenticator i zasady konfiguracji systemu iOS w witrynie Azure Portal.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/02/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 00356258-76a8-4a84-9cf5-64ceedb58e72
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: d08a7332ba96f552b488ad3f5d00004d0445d7ec
ms.sourcegitcommit: 6058c611d5a54076121af1d327a43ad861a43f8a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/03/2019
ms.locfileid: "53996001"
---
# <a name="add-and-assign-mobile-threat-defense-mtd-apps-with-intune"></a>Dodawanie i przypisywanie aplikacji usługi Mobile Threat Defense (MTD) za pomocą usługi Intune

> [!NOTE] 
> Niniejszy temat dotyczy wszystkich partnerów usługi Mobile Threat Defense.

Do dodawania i wdrażania aplikacji usługi Mobile Threat Defense (MTD) możesz używać usługi Intune, aby użytkownicy końcowi mogli otrzymywać powiadomienia w chwili zidentyfikowania zagrożenia na ich urządzeniach przenośnych oraz wskazówki dotyczące usuwania zagrożeń.


## <a name="before-you-begin"></a>Przed rozpoczęciem

Poniższe kroki należy wykonać w witrynie [Azure Portal](https://portal.azure.com/). Upewnij się, że znasz następujące procesy:

  -   [Dodawanie aplikacji w usłudze Intune](apps-add.md).
  -   [Dodawanie zasad konfiguracji aplikacji systemu iOS w usłudze Intune](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).
  -   [Przypisywanie aplikacji za pomocą usługi Intune](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune).

> [!TIP]
> Portal firmy usługi Intune działa na urządzeniach z systemem Android jako broker, aby tożsamości użytkowników mogły być sprawdzane przez usługę Azure AD.

## <a name="configure-microsoft-authenticator-for-ios"></a>Konfigurowanie aplikacji Microsoft Authenticator dla systemu iOS
W przypadku urządzeń z systemem iOS konieczna jest aplikacja [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to), aby tożsamości użytkowników mogły być sprawdzane przez usługę Azure AD. Ponadto konieczne są zasady konfiguracji aplikacji systemu iOS, które ustawiają aplikację usługi MTD dla systemu iOS do użycia z usługą Intune.

Zapoznaj się z instrukcjami dotyczącymi [dodawania aplikacji w sklepie dla systemu iOS do usługi Microsoft Intune](store-apps-ios.md). Użyj tego [adresu URL sklepu aplikacji Microsoft Authenticator](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) w **kroku 12**w sekcji **Konfigurowanie informacji o aplikacji**.

## <a name="configure-mtd-applications"></a>Konfigurowanie aplikacji usługi MTD

Wybierz sekcję odpowiadającą Twojemu dostawcy usługi MTD:

  - [Lookout for Work](#configure-lookout-for-work-apps)
  - [Symantec Endpoint Protection Mobile (SEP Mobile)](#configure-symantec-endpoint-protection-mobile-apps)
  - [Check Point SandBlast Mobile](#configure-check-point-sandblast-mobile-apps)
  - [Zimperium](#configure-zimperium-apps)
  - [Pradeo](#configure-pradeo-apps)
  - [Better Mobile](#configure-better-mobile-apps)

### <a name="configure-lookout-for-work-apps"></a>Konfigurowanie aplikacji Lookout for Work

- **Android**
  - Zapoznaj się z instrukcjami dotyczącymi [dodawania aplikacji w sklepie dla systemu Android do usługi Microsoft Intune](store-apps-android.md). Użyj tego [adresu URL sklepu Google aplikacji Lookout for Work](https://play.google.com/store/apps/details?id=com.lookout.enterprise) w **kroku 7**.

- **iOS**

  - Zapoznaj się z instrukcjami dotyczącymi [dodawania aplikacji w sklepie dla systemu iOS do usługi Microsoft Intune](store-apps-ios.md). Użyj tego [adresu URL sklepu aplikacji Lookout for Work dla systemu iOS](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8) w **kroku 12** w sekcji **Konfigurowanie informacji o aplikacji**.

-   **Aplikacja Lookout for Work poza sklepem firmy Apple**
    - Musisz ponownie podpisać aplikację Lookout for Work dla systemu iOS. Usługa Lookout dystrybuuje swoją aplikację Lookout for Work systemu iOS poza sklepem App Store systemu iOS. Przed dystrybucją aplikacji musisz ją ponownie podpisać za pomocą certyfikatu dewelopera przedsiębiorstwa systemu iOS.
    - Aby uzyskać szczegółowe instrukcje dotyczące ponownego podpisywania aplikacji Lookout for Work dla systemu iOS, zobacz [Lookout for Work iOS app re-signing process (Proces ponownego podpisywania aplikacji Lookout for Work dla systemu iOS)](https://personal.support.lookout.com/hc/articles/114094038714) w witrynie internetowej firmy Lookout.

    - **Włącz uwierzytelnianie usługi Azure AD dla użytkowników aplikacji Lookout for Work dla systemu iOS.**

        1. Przejdź do witryny [Azure Portal](https://portal.azure.com), zaloguj się przy użyciu swoich poświadczeń, a następnie przejdź do strony aplikacji.

        2. Dodaj **aplikację Lookout for Work systemu iOS** jako **natywną aplikację kliencką**.

        3. Zastąp ciąg **com.lookout.enterprise.nazwa_Twojej_firmy** identyfikatorem pakietu klienta wybranym podczas podpisywania pakietu aplikacji (IPA).

        4.  Dodaj dodatkowy identyfikator URI przekierowania: **&lt;companyportal://kod/>**, a po nim zakodowaną jako adres URL wersję Twojego oryginalnego identyfikatora URI przekierowania.

        5.  Dodaj **Uprawnienia delegowane** do Twojej aplikacji.

        > [!NOTE] 
        > Aby uzyskać szczegółowe informacje, zobacz [Configure a native client application with Azure AD (Konfigurowanie natywnej aplikacji klienckiej za pomocą usługi Azure AD)](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).

     - **Dodaj plik ipa aplikacji Lookout for Work**

        - Przekaż ponownie podpisany plik ipa, jak opisano w temacie [Add iOS LOB apps with Intune (Dodawanie aplikacji biznesowych dla systemu iOS za pomocą usługi Intune)](lob-apps-ios.md). Musisz też ustawić minimalną wersję systemu operacyjnego iOS na 8.0 lub nowszą.

### <a name="configure-symantec-endpoint-protection-mobile-apps"></a>Konfiguracja aplikacji Symantec Endpoint Protection Mobile

 - **Android**

    - Zapoznaj się z instrukcjami dotyczącymi [dodawania aplikacji w sklepie dla systemu Android do usługi Microsoft Intune](store-apps-android.md). W **kroku 7** użyj tego [adresu URL sklepu aplikacji SEP Mobile](https://play.google.com/store/apps/details?id=com.skycure.skycure).  W obszarze **Minimalny system operacyjny** wybierz pozycję **Android 4.0 (Ice Cream Sandwich)**.

 - **iOS**

    - Zapoznaj się z instrukcjami dotyczącymi [dodawania aplikacji w sklepie dla systemu iOS do usługi Microsoft Intune](store-apps-ios.md). W **kroku 12** użyj tego [adresu URL sklepu aplikacji SEP Mobile](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) w sekcji **Konfigurowanie informacji o aplikacji**.

### <a name="configure-check-point-sandblast-mobile-apps"></a>Konfiguracja aplikacji Check Point SandBlast Mobile

 - **Android**

    - Zapoznaj się z instrukcjami dotyczącymi [dodawania aplikacji w sklepie dla systemu Android do usługi Microsoft Intune](store-apps-android.md). Użyj tego [adresu URL aplikacji Check Point SandBlast Mobile](https://play.google.com/store/apps/details?id=com.lacoon.security.fox) w **kroku 7**.

 - **iOS**

    - Skontaktuj się z zespołem aplikacji [Check Point SandBlast Mobile](https://www.checkpoint.com/products/sandblast-mobile/), aby uzyskać aplikację dla systemu iOS. Zapoznaj się z instrukcjami dotyczącymi [dodawania aplikacji ze sklepu dla systemu iOS do usługi Microsoft Intune](store-apps-ios.md), a następnie użyj adresu URL sklepu Apple Store w **kroku 12** w sekcji dotyczącej **konfigurowania informacji o aplikacji**.

### <a name="configure-zimperium-apps"></a>Konfiguracja aplikacji Zimperium

 - **Android**

    - Zapoznaj się z instrukcjami dotyczącymi [dodawania aplikacji w sklepie dla systemu Android do usługi Microsoft Intune](store-apps-android.md). Użyj tego [adresu URL sklepu aplikacji Zimperium](https://play.google.com/store/apps/details?id=com.zimperium.zips&hl=en) w **kroku 7**.

 - **iOS**

    - Zapoznaj się z instrukcjami dotyczącymi [dodawania aplikacji w sklepie dla systemu iOS do usługi Microsoft Intune](store-apps-ios.md). Użyj tego [adresu URL sklepu aplikacji Zimperium](https://itunes.apple.com/us/app/zimperium-zips/id1030924459?mt=8) w **kroku 12** w sekcji **Konfigurowanie informacji o aplikacji**.

### <a name="configure-pradeo-apps"></a>Konfiguracja aplikacji Pradeo

 - **Android**

    - Zapoznaj się z instrukcjami dotyczącymi [dodawania aplikacji w sklepie dla systemu Android do usługi Microsoft Intune](store-apps-android.md). Użyj tego [adresu URL sklepu aplikacji Pradeo](https://play.google.com/store/apps/details?id=net.pradeo.service&hl=en_US) w **kroku 7**.

 - **iOS**

    - Zapoznaj się z instrukcjami dotyczącymi [dodawania aplikacji w sklepie dla systemu iOS do usługi Microsoft Intune](store-apps-ios.md). Użyj tego [adresu URL sklepu aplikacji Pradeo](https://itunes.apple.com/us/app/pradeo-agent/id547979360?mt=8) w **kroku 12** w sekcji **Konfigurowanie informacji o aplikacji**.

### <a name="configure-better-mobile-apps"></a>Konfigurowanie aplikacji usługi Better Mobile

 - **Android**

    - Zapoznaj się z instrukcjami dotyczącymi [dodawania aplikacji w sklepie dla systemu Android do usługi Microsoft Intune](store-apps-android.md). Użyj tego [adresu URL sklepu z aplikacjami Active Shield](https://play.google.com/store/apps/details?id=com.better.active.shield.enterprise) w **kroku 7**.

 - **iOS**

    - Zapoznaj się z instrukcjami dotyczącymi [dodawania aplikacji w sklepie dla systemu iOS do usługi Microsoft Intune](store-apps-ios.md). Użyj tego [adresu URL sklepu aplikacji ActiveShield](https://itunes.apple.com/us/app/activeshield/id980234260?mt=8&uo=4) w **kroku 12** w sekcji **Konfigurowanie informacji o aplikacji**.

## <a name="configure-your-mtd-apps-with-an-ios-app-configuration-policy"></a>Konfiguracja aplikacji usługi MTD przy użyciu zasad konfiguracji aplikacji systemu iOS

### <a name="lookout-for-work-app-configuration-policy"></a>Zasady konfiguracji aplikacji Lookout for Work

- Utwórz zasady konfiguracji aplikacji systemu iOS zgodnie z opisem w artykule dotyczącym [używania zasad konfiguracji aplikacji systemu iOS](app-configuration-policies-use-ios.md).

### <a name="sep-mobile-app-configuration-policy"></a>Zasady konfiguracji aplikacji SEP Mobile

-   Użyj tego samego konta usługi Azure AD, które zostało wcześniej skonfigurowane w [konsoli zarządzania programu Symantec Endpoint Protection](https://aad.skycure.com). Powinno to być konto używane podczas logowania się do portalu klasycznego usługi Intune.

-   Musisz **pobrać** plik zasad konfiguracji aplikacji systemu iOS: 
    -   Przejdź do [konsoli zarządzania programu Symantec Endpoint Protection](https://aad.skycure.com) i zaloguj się przy użyciu poświadczeń administratora.

    -   Przejdź do obszaru **Ustawienia**, a następnie w obszarze **Integracje** wybierz pozycję **Intune**. Wybierz pozycję **Wybór integracji EMM**. Wybierz pozycję **Microsoft**, a następnie zapisz wybrane opcje.

    -   Kliknij link **Pliki instalacyjne integracji** i zapisz wygenerowany plik \*.zip. Plik ZIP zawiera plik ***.plist**, który będzie używany do tworzenia zasad konfiguracji aplikacji systemu iOS w usłudze Intune.

    -   Zapoznaj się z instrukcjami dotyczącymi [używania zasad konfiguracji aplikacji usługi Microsoft Intune dla systemu iOS](app-configuration-policies-use-ios.md), aby dodać zasady konfiguracji aplikacji SEP Mobile dla systemu iOS.

    - W **kroku 8** użyj opcji **Wprowadź dane XML**, skopiuj zawartość z pliku ***.plist** i wklej jego zawartość do treści zasad konfiguracji.

> [!NOTE]
> Jeśli nie można pobrać plików, skontaktuj się z [działem pomocy technicznej programu Symantec Endpoint Protection Mobile Enterprise](https://support.symantec.com/en_US/contact-support.html).

### <a name="check-point-sandblast-mobile-app-configuration-policy"></a>Zasady konfiguracji aplikacji Check Point SandBlast Mobile

- Zapoznaj się z instrukcjami dotyczącymi [używania zasad konfiguracji aplikacji usługi Microsoft Intune dla systemu iOS](app-configuration-policies-use-ios.md), aby dodać zasady konfiguracji aplikacji Check Point SandBlast Mobile dla systemu iOS.
    - W **kroku 8** użyj opcji **Wprowadź dane XML**, skopiuj treść poniżej i wklej ją do treści zasad konfiguracji.

```
<dict><key>MDM</key><string>INTUNE</string></dict>
```

### <a name="zimperium-app-configuration-policy"></a>Zasady konfiguracji aplikacji Zimperium

- Zapoznaj się z instrukcjami dotyczącymi [używania zasad konfiguracji aplikacji usługi Microsoft Intune dla systemu iOS](app-configuration-policies-use-ios.md), aby dodać zasady konfiguracji aplikacji Zimperium dla systemu iOS.
    - W **kroku 8** użyj opcji **Wprowadź dane XML**, skopiuj treść poniżej i wklej ją do treści zasad konfiguracji.

```
<dict>
<key>provider</key><string>Intune</string>
<key>userprincipalname</key><string>{{userprincipalname}}</string>
<key>deviceid</key>
<string>{{deviceid}}</string>
<key>serialnumber</key>
<string>{{serialnumber}}</string>
<key>udidlast4digits</key>
<string>{{udidlast4digits}}</string>
</dict>
```

### <a name="better-mobile-app-configuration-policy"></a>Zasady konfiguracji aplikacji Better Mobile

- Zapoznaj się z instrukcjami dotyczącymi [używania zasad konfiguracji aplikacji usługi Microsoft Intune dla systemu iOS](app-configuration-policies-use-ios.md), aby dodać zasady konfiguracji aplikacji Better Mobile dla systemu iOS.
    - W **kroku 8** użyj opcji **Wprowadź dane XML**, skopiuj treść poniżej i wklej ją do treści zasad konfiguracji. Zastąp adres URL `https://client.bmobi.net` adresem URL odpowiedniej konsoli.

```
<dict>
<key>better_server_url</key>
<string>https://client.bmobi.net</string>
<key>better_udid</key>
<string>{{aaddeviceid}}</string>
<key>better_user</key>
<string>{{userprincipalname}}</string>
</dict>
```

## <a name="assign-apps-to-groups"></a>Przypisywanie aplikacji do grup

- Ten krok dotyczy wszystkich partnerów usługi MTD. Zapoznaj się z instrukcjami dotyczącymi [przypisywania aplikacji do grup przy użyciu usługi Intune](apps-deploy.md).

## <a name="next-steps"></a>Następne kroki

- [Konfiguracja zasad zgodności urządzeń dla usługi MTD](mtd-device-compliance-policy-create.md)
