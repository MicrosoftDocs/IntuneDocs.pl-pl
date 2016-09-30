---
title: "Wdrażanie aplikacji Lookout for Work | Microsoft Intune"
description: "Konfiguruj i wdrażaj aplikacje Lookout for Work dla systemu Android."
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 524c4209-ad57-4d35-955e-a00d796bf858
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c4d05b9ba7249e4068d21480b1c9db342277757e
ms.openlocfilehash: 687a102ccb34cb7acfaab1e8a1d4b67cb54b9e92


---

# Konfigurowanie i wdrażanie aplikacji Lookout for Work
W tym artykule opisano sposób konfigurowania i wdrażania aplikacji Lookout for Work dla zarejestrowanych urządzeń z systemem Android 4.1 lub nowszym.

* **Krok 1.** W [konsoli administratora usługi Microsoft Intune](https://manage.microsoft.com) przejdź do obszaru **Aplikacje** i wybierz pozycję **Dodaj aplikacje**.   
* **Krok 2.** Na stronie **Instalator oprogramowania** wydawcy wybierz pozycję **Link zewnętrzny** i podaj następujący adres URL: https://play.google.com/store/apps/details?id=com.lookout.enterprise
>[!NOTE]
>Nie klikaj pola wymagającego programu Managed Browser.

* **Krok 3.** Na stronie **Opis oprogramowania** wprowadź następujące informacje:
  * **Wydawca:** zabezpieczenia urządzeń przenośnych usługi Lookout
  * **Nazwa:** Lookout for Work
  * **Opis:** usługa Lookout zapewnia najlepszą ochronę przed zagrożeniami mobilnymi i pozwala zapewnić bezpieczeństwo urządzenia. Po zainstalowaniu na urządzeniu aplikacja Lookout chroni je przed zagrożeniami i powiadomi Cię oraz administratora firmy, jeśli jakiekolwiek zagrożenia zostaną znalezione.
  * **Kategoria:** zarządzanie komputerami
* **Krok 4.** Po pomyślnym zakończeniu zostanie wyświetlony komunikat **Przekazywanie danych do usługi Microsoft Intune zostało zakończone pomyślnie**.

Po kliknięciu pozycji **Aplikacje** w konsoli administratora usługi Intune aplikacja Lookout for Work zostanie wyświetlona na liście ![zrzut ekranu przedstawiający stronę aplikacji konsoli administracyjnej usługi Intune z wyświetloną na liście aplikacją Lookout for Work](../media/mtp/lookout-app-listed-intune-console.png)

**Aby wdrożyć aplikację użytkownikom**, wybierz aplikację Lookout for Work wyświetloną na ekranie powyżej i wybierz opcję **Zarządzanie wdrożeniem**.

Należy wybrać tych samych użytkowników, którzy zostali dodani za pomocą opcji Zarządzanie rejestracją w konsoli usługi Lookout MTP.  Zobacz krok 3 w sekcji [konfigurowania subskrypcji za pomocą usługi MTP](set-up-your-subscription-with-lookout-mtp#configure-your-subscription-with-lookout-mtp), aby uzyskać informacje na temat dodawania grup użytkowników do usługi Lookout MTP.
>[!IMPORTANT]
> Kreator wdrażania aplikacji usługi Intune nie ma informacji o grupach użytkowników usługi Azure AD i zamiast nich używa grup użytkowników usługi Intune. W związku z tym należy utworzyć grupę użytkowników usługi Intune na podstawie grupy użytkowników usługi Azure AD zarejestrowanej w konsoli usługi Lookout MTP w sposób opisany w [tym](plan-your-user-and-device-groups.md) temacie.

Wybierz opcję **Wymagana instalacja**, jeśli aplikacja Lookout musi być zainstalowania na urządzeniu użytkownika.


Jeśli na potrzeby wdrożenia została wybrana opcja **Wymagana instalacja**, usługa Intune przeprowadzi wypychanie aplikacji Lookout for Work do urządzenia.   

Gdy użytkownik otworzy aplikację Lookout for Work na urządzeniu, zostanie wyświetlony monit o aktywację aplikacji. Następnie należy wybrać opcję Sign in with Azure Active Directory (Zaloguj się przy użyciu usługi Azure Active Directory). Szczegółowy przewodnik z przepływem użytkownika końcowego można znaleźć w następujących tematach:

* [Pojawia się monit o zainstalowanie aplikacji Lookout for Work na urządzeniu z systemem Android](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

* [Należy rozwiązać problem związany z zagrożeniem wykrytym przez aplikację Lookout for Work na urządzeniu z systemem Android](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)

## Następne kroki
* [Włączanie reguły ochrony urządzenia przed zagrożeniami w zasadach zgodności](enable-device-threat-protection-rule-in-compliance-policy.md)



<!--HONumber=Sep16_HO3-->


