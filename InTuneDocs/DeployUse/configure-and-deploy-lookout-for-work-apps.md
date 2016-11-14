---
title: "Wdrażanie aplikacji Lookout for Work | Microsoft Intune"
description: "Konfiguruj i wdrażaj aplikacje Lookout for Work dla systemu Android."
author: karthikaraman
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 524c4209-ad57-4d35-955e-a00d796bf858
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 4a69be67c3ef9f028c77c738de5f1fcbd59a8d33
ms.openlocfilehash: 2c626cb0a36c38c7b5deeca0ff1e902018540634


---

# Konfigurowanie i wdrażanie aplikacji Lookout for Work
W tym artykule opisano sposób konfigurowania i wdrażania aplikacji Lookout for Work dla urządzeń z systemem Android i iOS.

## System Android (aplikacja ze sklepu Google Play)

* **Krok 1.** Przekazanie aplikacji Lookout for Work systemu Android w [konsoli administratora usługi Microsoft Intune](https://manage.microsoft.com), jak to opisano w temacie [Dodawanie aplikacji dla urządzeń przenośnych w usłudze Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune).
>[!NOTE]
> Nie klikaj pola wymagającego programu Managed Browser.

![Zrzut ekranu przedstawiający stronę aplikacji w konsoli administratora usługi Intune z wyświetlonymi aplikacjami Lookout for Work na liście](../media/mtp/lookout-app-listed-intune-console.png)

* **Krok 2.** Wdrożenie tej aplikacji dla użytkowników. Wybierz aplikację Lookout for Work wyświetloną na ekranie powyżej i wybierz opcję **Zarządzanie wdrożeniem**.

  Musisz wybrać tych samych użytkowników, którzy zostali dodani za pomocą opcji Zarządzanie rejestracją w konsoli usługi Lookout.  Zobacz krok 3 w sekcji dotyczącej [konfigurowania subskrypcji za pomocą usługi ochrony urządzeń przed zagrożeniami w usłudze Lookout](set-up-your-subscription-with-lookout-mtp#configure-your-subscription-with-lookout-mtp), aby uzyskać informacje na temat dodawania grup użytkowników do usługi Lookout MTP.
>[!IMPORTANT]
> Kreator wdrażania aplikacji usługi Intune nie ma informacji o grupach użytkowników usługi Azure AD i zamiast nich używa grup użytkowników usługi Intune. W związku z tym należy utworzyć grupę użytkowników usługi Intune na podstawie grupy użytkowników usługi Azure AD zarejestrowanej w konsoli usługi Lookout w sposób opisany w [tym](plan-your-user-and-device-groups.md) temacie.

Wybierz opcję **Wymagana instalacja**, jeśli aplikacja Lookout musi być zainstalowania na urządzeniu użytkownika.


## System iOS (podpisana przez przedsiębiorstwo wersja aplikacji Lookout)

* **Krok 1.** Upewnienie się, że na urządzeniu skonfigurowano **zarządzanie systemem iOS**. Aby uzyskać instrukcje dotyczące sposobu konfigurowania urządzenia pod kątem zarządzania systemem iOS, zobacz [Konfigurowanie zarządzania systemem iOS i komputerami Mac](set-up-ios-and-mac-management-with-microsoft-intune.md).

* **Krok 2.** **Ponowne podpisanie** aplikacji Lookout for Work systemu iOS. Usługa Lookout dystrybuuje swoją aplikację Lookout for Work systemu iOS poza sklepem App Store systemu iOS. **Przed dystrybucją aplikacji** należy ją ponownie podpisać za pomocą certyfikatu dewelopera przedsiębiorstwa systemu iOS. Aby uzyskać szczegółowe instrukcje dotyczące ponownego podpisywania aplikacji Lookout for Work systemu iOS, zobacz [Proces ponownego podpisywania aplikacji Lookout for Work systemu iOS](https://personal.support.lookout.com/hc/en-us/articles/114094038714) w witrynie usługi Lookout.


* **Krok 3.** Włączenie uwierzytelniania za pomocą usługi Azure Active Directory dla użytkowników systemu iOS przez wykonanie poniższych czynności:
  1.  Zaloguj się do [portalu zarządzania usługi Azure Active Directory](https://manage.windowsazure.com) i przejdź do strony aplikacji.
  2.  Dodaj **aplikację Lookout for Work systemu iOS** jako **natywną aplikację kliencką**.
  ![Zrzut ekranu przedstawiający okno dialogowe Dodawanie aplikacji z wyświetloną opcją Natywna aplikacja kliencka](../media/mtp/aad-add-app.png)

  3. Zastąp ciąg **com.lookout.enterprise.nazwa_Twojej_firmy** identyfikatorem pakietu klienta wybranym podczas podpisywania pakietu aplikacji (IPA).
  4.  Dodaj dodatkowy identyfikator URI przekierowania: **&lt;companyportal://kod/>**, a po nim zakodowaną w adresie URL wersję Twojego oryginalnego identyfikatora URI przekierowania.
  5.  Dodaj **Uprawnienia delegowane** do Twojej aplikacji.

  Aby uzyskać szczegółowe informacje, zobacz [Konfigurowanie natywnej aplikacji klienckiej](https://azure.microsoft.com/en-us/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).


* **Krok 4.** Przekazanie ponownie podpisanego pliku ipa, jak to opisano w temacie [Dodawanie aplikacji dla urządzeń przenośnych w usłudze Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune). Ustaw minimalną wersję systemu operacyjnego na iOS 8.0 lub nowszy.

  ![Zrzut ekranu przedstawiający stronę aplikacji w konsoli administratora usługi Intune z wyświetloną aplikacją Lookout for Work na liście aplikacji](../media/mtp/ios-app-uploaded-intune.png)

* **Krok 5.** Utworzenie zasad konfiguracji aplikacji zarządzanej, jak to opisano w temacie [Konfigurowanie aplikacji systemu iOS przy użyciu zasad konfiguracji aplikacji mobilnych w usłudze Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

  ![Zrzut ekranu przedstawiający Kreatora tworzenia nowych zasad z wyróżnionymi zasadami konfiguracji aplikacji systemu iOS 8.0 lub nowszego](../media/mtp/ios-app-config.png)

* **Krok 6.** **Wdrożenie aplikacji dla użytkowników** przez wybranie aplikacji Lookout for Work, a następnie wybranie pozycji **Zarządzanie wdrożeniem**.

  Musisz wybrać tych samych użytkowników, którzy zostali dodani za pomocą opcji Zarządzanie rejestracją w konsoli usługi Lookout.  Zobacz krok 3 w sekcji dotyczącej [konfigurowania subskrypcji za pomocą usługi ochrony urządzeń przed zagrożeniami w usłudze Lookout](set-up-your-subscription-with-lookout-mtp#configure-your-subscription-with-lookout-mtp), aby uzyskać informacje na temat dodawania grup użytkowników do usługi Lookout MTP.
>[!IMPORTANT]
> Kreator wdrażania aplikacji usługi Intune nie ma informacji o grupach użytkowników usługi Azure AD i zamiast nich używa grup użytkowników usługi Intune. W związku z tym należy utworzyć grupę użytkowników usługi Intune na podstawie grupy użytkowników usługi Azure AD zarejestrowanej w konsoli usługi Lookout w sposób opisany w [tym](plan-your-user-and-device-groups.md) temacie.

Wybierz opcję **Wymagana instalacja**, jeśli aplikacja Lookout musi być zainstalowania na urządzeniu użytkownika.

## Co się stanie po otwarciu wdrożonej aplikacji na urządzeniu




Gdy użytkownik otworzy aplikację Lookout for Work na urządzeniu, zostanie wyświetlony monit o aktywację aplikacji. Następnie należy wybrać opcję Sign in with Azure Active Directory (Zaloguj się przy użyciu usługi Azure Active Directory). Szczegółowy przewodnik z przepływem użytkownika końcowego można znaleźć w następujących tematach:

* [Pojawia się monit o zainstalowanie aplikacji Lookout for Work na urządzeniu z systemem Android](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

* [Należy rozwiązać problem związany z zagrożeniem wykrytym przez aplikację Lookout for Work na urządzeniu z systemem Android](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)

## Następne kroki
* [Włączanie reguły ochrony urządzenia przed zagrożeniami w zasadach zgodności](enable-device-threat-protection-rule-in-compliance-policy.md)



<!--HONumber=Oct16_HO2-->


