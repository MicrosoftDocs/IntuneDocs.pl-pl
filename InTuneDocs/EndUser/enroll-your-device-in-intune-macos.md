---
title: "Rejestrowanie urządzenia z systemem macOS w usłudze Intune | Microsoft Docs"
description: "Opis sposobu rejestrowania urządzenia z systemem macOS w usłudze Intune"
keywords: Mac OS X, macOS, OS X
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 58eb0e7a-1321-4c66-a281-88fb01e72c1c
searchScope:
- Company Portal
ROBOTS: 
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 70b11804b6b96e76b43cc450ac4c433fb31be6f8


---

# <a name="enroll-your-macos-device-in-intune"></a>Rejestrowanie urządzenia z systemem macOS w usłudze Intune

Uzyskiwanie dostępu do aplikacji, danych i zasobów organizacji umożliwia Ci wykonywanie pracy. Jeśli używasz urządzenia z systemem macOS w miejscu pracy, musisz zainstalować __profil zarządzania__. Jest to po prostu plik skonfigurowany przez administratora IT, umożliwiający załadowanie ustawień i informacji dotyczących dostępu na komputerze Mac. Chcesz dowiedzieć się więcej? Sprawdź, [co dzieje się w przypadku zainstalowania aplikacji Portal firmy i zarejestrowania urządzenia w usłudze Intune](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md).

  > [!NOTE]
  > Jeśli próbujesz zarejestrować urządzenie z systemem iOS, takie jak iPhone lub iPad, [zamiast tego spróbuj wykonać te instrukcje](enroll-your-device-in-intune-ios.md).

1. Na __Docku__ znajdź pozycję __Safari__ i otwórz nowe okno, a następnie otwórz [witrynę aplikacji Portal firmy](http://portal.manage.microsoft.com).
2. Zaloguj się do witryny aplikacji Portal firmy przy użyciu konta służbowego.

  [!INCLUDE[wit_nextref](../includes/end-user-password-guidance.md)]

3. Po zalogowaniu zobaczysz dostępne __aplikacje__, __Moje urządzenia__ i __informacje kontaktowe__ dotyczące pracowników działu IT. W górnej części strony pojawi się następujący komunikat: **Either this device isn't enrolled, or the Company Portal can't identify it. <u>Tap Here</u> to select a different device.** (To urządzenie nie zostało zarejestrowane lub aplikacja Portal firmy nie może go zidentyfikować. Naciśnij tutaj, aby wybrać inne urządzenie). Kliknij pozycję __Tap Here__ (Naciśnij tutaj).

 ![Strona docelowa aplikacji Portal firmy w systemie macOS](./media/macOS_enroll_001_landing_page.png)

4. Zostanie wyświetlone wyskakujące okienko z krótkim wyjaśnieniem powodów __identyfikowania lub rejestrowania urządzenia__. Zapoznaj się z tymi informacjami, a następnie kliknij pozycję __Zarejestruj__, aby kontynuować.

 ![Okno identyfikowania lub rejestrowania urządzenia w systemie macOS](./media/macOS_enroll_002_IDenroll_popup.png)

5. Zostanie wyświetlone drugie wyskakujące okienko z krótkim wyjaśnieniem skutków __zarejestrowania urządzenia__. Zapoznaj się z tymi informacjami, a następnie kliknij pozycję __Zainstaluj__, aby kontynuować.

 ![Okno rejestrowania urządzenia w systemie macOS](./media/macOS_enroll_003_enroll_popup.png)

  > [!NOTE]
  > Usługa Intune musi mieć dostęp do komputera, aby sprawdzić, czy urządzenie jest wystarczająco bezpieczne, aby mogło uzyskiwać dostęp do zasobów organizacji. Sprawdź, [co stanie się po zarejestrowaniu urządzenia w usłudze Intune](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-ios.md).

6. Zostanie otwarte okno __Preferencje systemowe__ z pytaniem, czy chcesz __zainstalować „profil zarządzania”.__ Kliknij pozycję __Zainstaluj__, aby kontynuować, lub kliknij pozycję __Pokaż profil__, aby uzyskać dalsze informacje.

 ![Instalowanie profilu zarządzania](./media/macOS_enroll_004_sysprefs_mgmt_profile.png)

7. Zostanie wyświetlone wyskakujące okienko systemu macOS. Potwierdź wprowadzenie zmian, podając __nazwę użytkownika__ i __hasło__ komputera, a następnie klikając przycisk __OK__. Spowoduje to zainstalowanie profilu zarządzania na komputerze Mac.

 ![Wyskakujące okienko instalowania profilu w systemie macOS](./media/macOS_enroll_005_sysprefs_admin_login.png)

8. Na komputerze Mac możesz zobaczyć dodatkowe komunikaty zawierające więcej szczegółowych informacji o profilu lub ułatwiających podjęcie decyzji o __instalacji__. Za ich pośrednictwem kliknij pozycje __Kontynuuj__ i __Zainstaluj__, aby kontynuować. Po zakończeniu instalacji będzie można przeglądać nowo zainstalowany __profil zarządzania__ na liście __Profile urządzeń__.

 ![Zainstalowany profil w systemie macOS](./media/macOS_enroll_006_sysprefs_installed_profile.png)

Nadal potrzebujesz pomocy? Skonsultuj się z administratorem IT. Odpowiednie informacje kontaktowe możesz znaleźć w [witrynie aplikacji Portal firmy](http://portal.manage.microsoft.com).



<!--HONumber=Dec16_HO2-->


