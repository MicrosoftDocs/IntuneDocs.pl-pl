---
title: Dodawanie i przypisywanie aplikacji usługi MTD do usługi Microsoft Intune
titleSuffix: ''
description: Użyj usługi Intune, aby dodać aplikacje usługi Mobile Threat Defense (MTD), aplikację Microsoft Authenticator i zasady konfiguracji systemu iOS w witrynie Azure Portal.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 07/03/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 00356258-76a8-4a84-9cf5-64ceedb58e72
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 08cebf84443e65ded5f7884218fbe17d722bddf2
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="add-and-assign-mobile-threat-defense-mtd-apps-with-intune"></a>Dodawanie i przypisywanie aplikacji usługi Mobile Threat Defense (MTD) za pomocą usługi Intune

> [!NOTE] 
> Niniejszy temat dotyczy wszystkich partnerów usługi Mobile Threat Defense.

Do dodawania i wdrażania aplikacji usługi MTD możesz używać usługi Intune, aby użytkownicy końcowi mogli otrzymywać powiadomienia w chwili zidentyfikowania zagrożenia na ich urządzeniach przenośnych oraz wskazówki dotyczące usuwania zagrożeń.

W przypadku urządzeń z systemem iOS konieczna jest aplikacja [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to), aby tożsamości użytkowników mogły być sprawdzane przez usługę Azure AD. Ponadto konieczne są zasady konfiguracji aplikacji systemu iOS, które sygnalizują aplikację usługi MTD dla systemu iOS do użycia z usługą Intune.

> [!TIP]
> Portal firmy usługi Intune działa na urządzeniach z systemem Android jako broker, aby tożsamości użytkowników mogły być sprawdzane przez usługę Azure AD.

## <a name="before-you-begin"></a>Przed rozpoczęciem

-   Poniższe kroki należy wykonać w witrynie [Azure Portal](https://portal.azure.com/).

-   Upewnij się, że znasz następujące procesy:

    -   [Dodawanie aplikacji w usłudze Intune](apps-add.md).

    -   [Dodawanie zasad konfiguracji aplikacji systemu iOS w usłudze Intune](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

    -   [Przypisywanie aplikacji za pomocą usługi Intune](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune).

    -   [Dodawanie zasad konfiguracji aplikacji systemu iOS](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

## <a name="to-add-apps"></a>Aby dodać aplikacje

### <a name="all-mtd-partners"></a>Wszyscy partnerzy usługi MTD

#### <a name="microsoft-authenticator-app-for-ios"></a>Aplikacja Microsoft Authenticator dla systemu iOS

- Zapoznaj się z instrukcjami dotyczącymi [dodawania aplikacji w sklepie dla systemu iOS do usługi Microsoft Intune](store-apps-ios.md). Użyj tego [adresu URL sklepu aplikacji Microsoft Authenticator](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) w **kroku 5**w sekcji **Konfigurowanie informacji o aplikacji**.

### <a name="lookout"></a>Lookout

#### <a name="android"></a>Android
- Zapoznaj się z instrukcjami dotyczącymi [dodawania aplikacji w sklepie dla systemu Android do usługi Microsoft Intune](store-apps-android.md). Użyj tego [adresu URL sklepu Google aplikacji Lookout for Work](https://play.google.com/store/apps/details?id=com.lookout.enterprise) w **kroku 7**.

#### <a name="ios"></a>iOS

- Zapoznaj się z instrukcjami dotyczącymi [dodawania aplikacji w sklepie dla systemu iOS do usługi Microsoft Intune](store-apps-ios.md). Użyj tego [adresu URL sklepu aplikacji Lookout for Work dla systemu iOS](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8) w **kroku 5** w sekcji **Konfigurowanie informacji o aplikacji**.

#### <a name="lookout-for-work-app-outside-the-apple-store"></a>Aplikacja Lookout for Work poza sklepem firmy Apple

Musisz ponownie podpisać aplikację Lookout for Work dla systemu iOS. Usługa Lookout dystrybuuje swoją aplikację Lookout for Work systemu iOS poza sklepem App Store systemu iOS. Przed dystrybucją aplikacji musisz ją ponownie podpisać za pomocą certyfikatu dewelopera przedsiębiorstwa systemu iOS.

Aby uzyskać szczegółowe instrukcje dotyczące ponownego podpisywania aplikacji Lookout for Work dla systemu iOS, zobacz [Lookout for Work iOS app re-signing process (Proces ponownego podpisywania aplikacji Lookout for Work dla systemu iOS)](https://personal.support.lookout.com/hc/articles/114094038714) w witrynie internetowej firmy Lookout.

##### <a name="enable-azure-ad-authentication-for-lookout-for-work-ios-app"></a>Włączanie uwierzytelniania usługi Azure AD dla aplikacji Lookout for Work dla systemu iOS

Włącz uwierzytelnianie za pomocą usługi Azure Active Directory dla użytkowników systemu iOS, wykonując poniższe czynności:

1. Przejdź do witryny [Azure Portal](https://portal.azure.com), zaloguj się przy użyciu swoich poświadczeń, a następnie przejdź do strony aplikacji.

2. Dodaj **aplikację Lookout for Work systemu iOS** jako **natywną aplikację kliencką**.

3. Zastąp ciąg **com.lookout.enterprise.nazwa_Twojej_firmy** identyfikatorem pakietu klienta wybranym podczas podpisywania pakietu aplikacji (IPA).

4.  Dodaj dodatkowy identyfikator URI przekierowania: **&lt;companyportal://kod/>**, a po nim zakodowaną jako adres URL wersję Twojego oryginalnego identyfikatora URI przekierowania.

5.  Dodaj **Uprawnienia delegowane** do Twojej aplikacji.

    > [!NOTE] 
    > Aby uzyskać szczegółowe informacje, zobacz [Configure a native client application with Azure AD (Konfigurowanie natywnej aplikacji klienckiej za pomocą usługi Azure AD)](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).

##### <a name="add-the-lookout-for-work-ipa-file"></a>Dodawanie pliku ipa aplikacji Lookout for Work

- Przekaż ponownie podpisany plik ipa, jak opisano w temacie [Add iOS LOB apps with Intune (Dodawanie aplikacji biznesowych dla systemu iOS za pomocą usługi Intune)](lob-apps-ios.md). Musisz też ustawić minimalną wersję systemu operacyjnego iOS na 8.0 lub nowszą.

### <a name="skycure"></a>Skycure

#### <a name="android"></a>Android

- Zapoznaj się z instrukcjami dotyczącymi [dodawania aplikacji w sklepie dla systemu Android do usługi Microsoft Intune](store-apps-android.md). Użyj tego [adresu URL sklepu aplikacji Skycure](https://play.google.com/store/apps/details?id=com.skycure.skycure) w **kroku 7**.

#### <a name="ios"></a>iOS

- Zapoznaj się z instrukcjami dotyczącymi [dodawania aplikacji w sklepie dla systemu iOS do usługi Microsoft Intune](store-apps-ios.md). Użyj tego [adresu URL sklepu aplikacji Skycure](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) w **kroku 5** w sekcji **Konfigurowanie informacji o aplikacji**.

### <a name="check-point-sandblast-mobile"></a>Check Point SandBlast Mobile

#### <a name="android"></a>Android

- Zapoznaj się z instrukcjami dotyczącymi [dodawania aplikacji w sklepie dla systemu Android do usługi Microsoft Intune](store-apps-android.md). Użyj tego [adresu URL aplikacji Check Point SandBlast Mobile](https://play.google.com/store/apps/details?id=com.lacoon.security.fox) w **kroku 7**.

#### <a name="ios"></a>iOS

- Skontaktuj się z zespołem aplikacji [Check Point SandBlast Mobile](https://www.checkpoint.com/products/sandblast-mobile/), aby uzyskać aplikację dla systemu iOS. Zapoznaj się z instrukcjami dotyczącymi [dodawania aplikacji ze sklepu dla systemu iOS do usługi Microsoft Intune](store-apps-ios.md), a następnie użyj adresu URL sklepu Apple Store w **kroku 5** w sekcji dotyczącej **konfigurowania informacji o aplikacji**.

### <a name="zimperium"></a>Zimperium

#### <a name="android"></a>Android

- Zapoznaj się z instrukcjami dotyczącymi [dodawania aplikacji w sklepie dla systemu Android do usługi Microsoft Intune](store-apps-android.md). Użyj tego [adresu URL sklepu aplikacji Zimperium](https://play.google.com/store/apps/details?id=com.zimperium.zips&hl=en) w **kroku 7**.

#### <a name="ios"></a>iOS

- Zapoznaj się z instrukcjami dotyczącymi [dodawania aplikacji w sklepie dla systemu iOS do usługi Microsoft Intune](store-apps-ios.md). Użyj tego [adresu URL sklepu aplikacji Zimperium](https://itunes.apple.com/us/app/zimperium-zips/id1030924459?mt=8) w **kroku 5** w sekcji **Konfigurowanie informacji o aplikacji**.

## <a name="to-associate-the-mtd-app-with-an-ios-app-configuration-policy"></a>Aby skojarzyć aplikację usługi MTD z zasadami konfiguracji aplikacji systemu iOS

### <a name="for-lookout"></a>W przypadku aplikacji Lookout

- Utwórz zasady konfiguracji aplikacji systemu iOS zgodnie z opisem w temacie [Using iOS app configuration policy (Używanie zasad konfiguracji aplikacji systemu iOS)](app-configuration-policies-use-ios.md).

### <a name="for-skycure"></a>W przypadku aplikacji Skycure

-   Użyj tego samego konta usługi Azure AD, które zostało wcześniej skonfigurowane w [konsoli zarządzania aplikacji Skycure](https://aad.skycure.com). Powinno to być konto używane podczas logowania się do portalu klasycznego usługi Intune.

-   Musisz **pobrać** plik zasad konfiguracji aplikacji systemu iOS: 
    -   Przejdź do [konsoli zarządzania aplikacji Skycure](https://aad.skycure.com) i zaloguj się przy użyciu poświadczeń administratora.

    -   Przejdź do opcji **Ustawienia** &gt; **Integracje zarządzania urządzeniami** &gt; **Wybór integracji EMM**, wybierz opcję **Microsoft Intune**, a następnie zapisz wybór.

    -   Kliknij link **Pliki instalacyjne integracji** i zapisz wygenerowany \*plik ZIP. Plik ZIP zawiera plik **skycure\_configuration.plist**, który będzie używany do tworzenia zasad konfiguracji aplikacji systemu iOS w usłudze Intune.

    -   Zapoznaj się z instrukcjami dotyczącymi [używania zasad konfiguracji aplikacji usługi Microsoft Intune dla systemu iOS](app-configuration-policies-use-ios.md), aby dodać zasady konfiguracji aplikacji Skycure dla systemu iOS.

    - W **kroku 8** użyj opcji **Wprowadź dane XML**, skopiuj zawartość z pliku **skycure_configuration.plist** i wklej jego zawartość do treści zasad konfiguracji.

Zawartość pliku **skycure_configuration.plist** możesz również skopiować z tego miejsca:

```
<dict>
    <key>MdmType</key>
    <string>Intune</string>
    <key>UserEmail</key>
    <string>{{userprincipalname}}</string>
</dict>
```
### <a name="for-check-point-sandblast-mobile"></a>W przypadku aplikacji Check Point SandBlast Mobile

- Zapoznaj się z instrukcjami dotyczącymi [używania zasad konfiguracji aplikacji usługi Microsoft Intune dla systemu iOS](app-configuration-policies-use-ios.md), aby dodać zasady konfiguracji aplikacji Check Point SandBlast Mobile dla systemu iOS.
    - W **kroku 8** użyj opcji **Wprowadź dane XML**, skopiuj treść poniżej i wklej ją do treści zasad konfiguracji.

```
<dict><key>MDM</key><string>INTUNE</string></dict>
```

### <a name="for-zimperium"></a>Dla rozwiązania Zimperium

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

## <a name="to-assign-apps-all-mtd-partners"></a>Aby przypisać aplikacje (wszyscy partnerzy usługi MTD)

- Zapoznaj się z instrukcjami dotyczącymi [przypisywania aplikacji do grup przy użyciu usługi Intune](apps-deploy.md).

## <a name="next-steps"></a>Następne kroki

- [Dodawanie zasad zgodności urządzeń dla rozwiązania MTD](mtd-device-compliance-policy-create.md)
