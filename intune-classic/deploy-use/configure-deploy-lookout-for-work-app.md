---
title: "Wdrażanie aplikacji Lookout for Work"
description: "Konfiguruj i wdrażaj aplikacje Lookout for Work dla systemu Android."
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 524c4209-ad57-4d35-955e-a00d796bf858
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: fd0ad36f40463ab56f1a5ab0a11fa9eeb0c35db4
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2017
---
# <a name="configure-and-deploy-lookout-for-work-app"></a>Konfigurowanie i wdrażanie aplikacji Lookout for Work

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

W tym artykule opisano sposób konfigurowania i wdrażania aplikacji Lookout for Work dla urządzeń z systemem Android i iOS.

## <a name="android-google-play-store-app"></a>System Android (aplikacja ze sklepu Google Play)

1.  W [konsoli administratora usługi Microsoft Intune](https://manage.microsoft.com) przejdź do obszaru **Aplikacje** i wybierz pozycję **Dodaj aplikacje**.
2.  Na stronie **Instalator oprogramowania** wydawcy wybierz pozycję **Link zewnętrzny** i podaj następujący adres URL: https://play.google.com/store/apps/details?id=com.lookout.enterprise
  >[!NOTE]
  >Nie klikaj pola wymagającego programu Managed Browser.

3.  Na stronie **Opis oprogramowania** wprowadź następujące informacje:
  * **Wydawca:** zabezpieczenia urządzeń przenośnych usługi Lookout
  * **Nazwa:** Lookout for Work
  * **Opis:** usługa Lookout zapewnia najlepszą ochronę przed zagrożeniami mobilnymi i pozwala zapewnić bezpieczeństwo urządzenia. Po zainstalowaniu na urządzeniu aplikacja Lookout chroni je przed zagrożeniami i powiadomi Cię oraz administratora firmy, jeśli jakiekolwiek zagrożenia zostaną znalezione.
  * **Kategoria:** zarządzanie komputerami

4. Po pomyślnym zakończeniu zostanie wyświetlony komunikat **Przekazywanie danych do usługi Microsoft Intune zostało zakończone pomyślnie**.

  W konsoli usługi Intune po kliknięciu pozycji **Aplikacje** aplikacja **Lookout for Work** zostanie wyświetlona na liście ![zrzut ekranu przedstawiający stronę aplikacji konsoli administracyjnej usługi Intune z wyświetloną na liście aplikacją Lookout for Work](../media/mtp/lookout-app-listed-intune-console.png)

5. Wdróż aplikację dla użytkowników przez wybranie aplikacji Lookout for Work, a następnie wybranie pozycji **Zarządzanie wdrożeniem**.

  Należy wybrać tych samych użytkowników, którzy zostali dodani za pomocą opcji Zarządzanie wdrożeniem w konsoli usługi Lookout MTP.  Zobacz krok 3 w sekcji [konfigurowania subskrypcji za pomocą usługi MTP](configure-deploy-lookout-for-work-app.md), aby uzyskać informacje na temat dodawania grup użytkowników do usługi Lookout MTP.

  >[!IMPORTANT]
  > Kreator wdrażania aplikacji usługi Intune nie posiada informacji o grupach użytkowników usługi Azure AD i zamiast nich używa grup użytkowników usługi Intune. W związku z tym należy utworzyć grupę użytkowników usługi Intune na podstawie grupy użytkowników usługi Azure AD zarejestrowanej w konsoli usługi Lookout MTP w sposób opisany w [tym](plan-your-user-and-device-groups.md) temacie.

6. Wybierz opcję **Wymagana instalacja**, jeśli aplikacja Lookout musi być zainstalowania na urządzeniu użytkownika.

## <a name="ios-enterprise-signed-version-of-lookout-app"></a>System iOS (podpisana przez przedsiębiorstwo wersja aplikacji Lookout)

1. Upewnij się, że na urządzeniu skonfigurowano **zarządzanie systemem iOS**. Aby uzyskać instrukcje dotyczące sposobu konfigurowania urządzenia pod kątem zarządzania systemem iOS, zobacz [Konfigurowanie zarządzania systemem iOS i komputerami Mac](set-up-ios-and-mac-management-with-microsoft-intune.md).

2. **Ponownie podpisz** aplikację Lookout for Work systemu iOS. Usługa Lookout dystrybuuje swoją aplikację Lookout for Work systemu iOS poza sklepem App Store systemu iOS. **Przed dystrybucją aplikacji** należy ją ponownie podpisać za pomocą certyfikatu dewelopera przedsiębiorstwa systemu iOS. Aby uzyskać szczegółowe instrukcje dotyczące ponownego podpisywania aplikacji Lookout for Work systemu iOS, zobacz [Proces ponownego podpisywania aplikacji Lookout for Work systemu iOS](https://personal.support.lookout.com/hc/articles/114094038714) w witrynie usługi Lookout.

3. Włącz uwierzytelnianie za pomocą usługi Azure Active Directory dla użytkowników systemu iOS, wykonując poniższe czynności:
  1.  Zaloguj się do [portalu zarządzania usługi Azure Active Directory](https://manage.windowsazure.com) i przejdź do strony aplikacji.
  2.  Dodaj **aplikację Lookout for Work systemu iOS** jako **natywną aplikację kliencką**.
  ![Zrzut ekranu przedstawiający okno dialogowe Dodawanie aplikacji z wyświetloną opcją Natywna aplikacja kliencka](../media/mtp/aad-add-app.png)
  3. Zastąp ciąg **com.lookout.enterprise.nazwa_Twojej_firmy** identyfikatorem pakietu klienta wybranym podczas podpisywania pakietu aplikacji (IPA).
  4.  Dodaj dodatkowy identyfikator URI przekierowania: **&lt;companyportal://kod/>**, a po nim zakodowaną w adresie URL wersję Twojego oryginalnego identyfikatora URI przekierowania.
  5.  Dodaj **Uprawnienia delegowane** do Twojej aplikacji.

  Aby uzyskać szczegółowe informacje, zobacz [Konfigurowanie natywnej aplikacji klienckiej](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).

4. Przekaż ponownie podpisany plik ipa, jak opisano w temacie [Dodawanie aplikacji dla urządzeń przenośnych w usłudze Microsoft Intune](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune). Ustaw minimalną wersję systemu operacyjnego na iOS 8.0 lub nowszy.

  ![Zrzut ekranu przedstawiający stronę aplikacji w konsoli administratora usługi Intune z wyświetloną aplikacją Lookout for Work na liście aplikacji](../media/mtp/ios-app-uploaded-intune.png)

5. Utwórz zasady konfiguracji zarządzanej aplikacji, jak opisano w temacie [Konfigurowanie aplikacji systemu iOS przy użyciu zasad konfiguracji aplikacji mobilnych w usłudze Microsoft Intune](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

  ![Zrzut ekranu przedstawiający Kreatora tworzenia nowych zasad z wyróżnionymi zasadami konfiguracji aplikacji systemu iOS 8.0 lub nowszego](../media/mtp/ios-app-config.png)

6. **Aby wdrożyć aplikację dla użytkowników**, wybierz aplikację Lookout for Work, a następnie wybierz pozycję **Zarządzanie wdrożeniem**.

  Musisz wybrać tych samych użytkowników, którzy zostali dodani za pomocą opcji Zarządzanie rejestracją w konsoli usługi Lookout.  Zobacz krok 3 w [sekcji konfigurowania subskrypcji programu Lookout](https://docs.microsoft.com/sccm/protect/deploy-use/configure-and-deploy-lookout-for-work-apps), aby uzyskać informacje na temat dodawania grup użytkowników do usługi Lookout MTP.

  >[!IMPORTANT]
  > Kreator wdrażania aplikacji usługi Intune nie ma informacji o grupach użytkowników usługi Azure AD i zamiast nich używa grup użytkowników usługi Intune. W związku z tym należy utworzyć grupę użytkowników usługi Intune na podstawie grupy użytkowników usługi Azure AD zarejestrowanej w konsoli usługi Lookout w sposób opisany w [tym](plan-your-user-and-device-groups.md) temacie.

  Wybierz opcję **Wymagana instalacja**, jeśli aplikacja Lookout musi być zainstalowania na urządzeniu użytkownika.

## <a name="what-happens-when-the-deployed-app-is-opened-on-the-device"></a>Co się stanie po otwarciu wdrożonej aplikacji na urządzeniu
https://github.com/Microsoft/Docs/blob/master/ContributorGuide/index.md Gdy użytkownik otworzy aplikację Lookout for Work na urządzeniu, zostanie wyświetlony monit o aktywację aplikacji. Następnie należy wybrać opcję Sign in with Azure Active Directory (Zaloguj się przy użyciu usługi Azure Active Directory). Szczegółowy przewodnik z przepływem użytkownika końcowego można znaleźć w następujących tematach:

* [Pojawia się monit o zainstalowanie aplikacji Lookout for Work na urządzeniu z systemem Android](https://docs.microsoft.com/intune-user-help/you-are-prompted-to-install-lookout-for-work-android)

* [Należy rozwiązać problem związany z zagrożeniem wykrytym przez aplikację Lookout for Work na urządzeniu z systemem Android](https://docs.microsoft.com/intune-user-help/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)

## <a name="next-steps"></a>Następne kroki
* [Tworzenie zasad zgodności urządzeń z rozwiązaniem Lookout w usłudze Intune](https://docs.microsoft.com/sccm/protect/deploy-use/enable-device-threat-protection-rule-compliance-policy)
