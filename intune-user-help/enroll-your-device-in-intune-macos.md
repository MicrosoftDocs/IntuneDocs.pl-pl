---
title: "Rejestrowanie urządzenia z systemem macOS w usłudze Intune | Microsoft Docs"
description: "Opis sposobu rejestrowania urządzenia z systemem macOS w usłudze Intune"
keywords: Mac OS X, macOS, OS X
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 58eb0e7a-1321-4c66-a281-88fb01e72c1c
searchScope:
- User help
ROBOTS: 
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
translationtype: Human Translation
ms.sourcegitcommit: 10c7bc5461c746ab50e83c2ffc590b89efe75e5f
ms.openlocfilehash: bb4238472277ec579abdde7830a9abc50a7bae97
ms.lasthandoff: 03/13/2017


---

# <a name="enroll-your-macos-device-in-intune"></a>Rejestrowanie urządzenia z systemem macOS w usłudze Intune

Uzyskiwanie dostępu do aplikacji, danych i zasobów organizacji umożliwia Ci wykonywanie pracy. Jeśli używasz urządzenia z systemem macOS w miejscu pracy, musisz zainstalować __profil zarządzania__. Jest to po prostu plik skonfigurowany przez administratora IT, umożliwiający załadowanie ustawień i informacji dotyczących dostępu na komputerze Mac. Chcesz wiedzieć więcej? Sprawdź, [co dzieje się w przypadku zainstalowania aplikacji Portal firmy i zarejestrowania urządzenia w usłudze Intune](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md)

  > [!NOTE]
  > Jeśli próbujesz zarejestrować urządzenie z systemem iOS, takie jak iPhone lub iPad, [zamiast tego spróbuj wykonać te instrukcje](enroll-your-device-in-intune-ios.md).

1. Na __Docku__ znajdź pozycję __Safari__ i otwórz nowe okno, a następnie otwórz [witrynę aplikacji Portal firmy](http://portal.manage.microsoft.com).
2. Zaloguj się do witryny aplikacji Portal firmy przy użyciu konta służbowego.

  [!INCLUDE[wit_nextref](includes/end-user-password-guidance.md)]

3. Po zalogowaniu zostaną wyświetlone wszystkie dostępne karty __Strona główna__, __Aplikacje__ i __Kategorie__. Na tej stronie będą wyświetlane wszystkie aplikacje dostępne do zainstalowania. Jeśli nie masz jeszcze zarejestrowanych urządzeń, zostanie wyświetlone powiadomienie, że **Nie można wyświetlić żadnych aplikacji.** Aby kontynuować, wybierz pozycję __Moje urządzenia__.

 ![Zrzut ekranu strony początkowej portalu sieci Web z informacją, że nie można jeszcze zainstalować żadnych aplikacji, oraz przyciskiem Moje urządzenia poniżej.](./media/macOS_enroll_001_landing_page.png)

4. Na stronie __Moje urządzenia__ zostanie wyświetlona lista zarejestrowanych urządzeń lub transparent. Jest to zależne od tego, czy masz już zarejestrowane urządzenia z systemem macOS lub inne. Aby zarejestrować urządzenie, którego nie ma na liście, wybierz transparent z informacją __Jeśli urządzenie jest na liście, naciśnij tutaj, aby je zidentyfikować. Możesz również nacisnąć tutaj, aby zarejestrować urządzenie, jeśli nie ma go na liście__.

  ![Zrzut ekranu strony Moje urządzenia przedstawiający kilka niezidentyfikowanych urządzeń oraz znajdujący się poniżej transparent z monitem o zarejestrowanie urządzeń nieznajdujących się na liście lub zidentyfikowanie tych niezidentyfikowanych.](./media/macOS_enroll_002_tap_here_banner.png)

5. Zostanie wyświetlone wyskakujące okienko z krótkim wyjaśnieniem powodów __identyfikowania lub rejestrowania urządzenia__. Zapoznaj się z tymi informacjami, a następnie kliknij pozycję __Zarejestruj__, aby kontynuować.

 ![Okno identyfikowania lub rejestrowania urządzenia w systemie macOS](./media/macOS_enroll_003_IDenroll_popup.png)

6. Zostanie wyświetlone drugie wyskakujące okienko z krótkim wyjaśnieniem skutków __zarejestrowania urządzenia__. Zapoznaj się z tymi informacjami, a następnie kliknij pozycję __Zainstaluj__, aby kontynuować.

 ![Okno rejestrowania urządzenia w systemie macOS](./media/macOS_enroll_004_enroll_popup.png)

  > [!NOTE]
  > Usługa Intune musi mieć dostęp do komputera, aby sprawdzić, czy urządzenie jest wystarczająco bezpieczne, aby mogło uzyskiwać dostęp do zasobów organizacji. Sprawdź, [co stanie się po zarejestrowaniu urządzenia w usłudze Intune](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-ios.md).

7. Zostanie otwarte okno __Preferencje systemowe__ z pytaniem, czy chcesz __zainstalować „profil zarządzania”.__ Kliknij pozycję __Zainstaluj__, aby kontynuować, lub kliknij pozycję __Pokaż profil__, aby uzyskać dalsze informacje.

 ![Instalowanie profilu zarządzania](./media/macOS_enroll_005_sysprefs_mgmt_profile.png)

8. Zostanie wyświetlone wyskakujące okienko systemu macOS. Potwierdź wprowadzenie zmian, podając __nazwę użytkownika__ i __hasło__ komputera, a następnie klikając przycisk __OK__. Spowoduje to zainstalowanie profilu zarządzania na komputerze Mac.

 ![Wyskakujące okienko instalowania profilu w systemie macOS](./media/macOS_enroll_006_sysprefs_admin_login.png)

9. Na komputerze Mac możesz zobaczyć dodatkowe komunikaty zawierające więcej szczegółowych informacji o profilu lub ułatwiających podjęcie decyzji o __instalacji__. Za ich pośrednictwem kliknij pozycje __Kontynuuj__ i __Zainstaluj__, aby kontynuować. Po zakończeniu instalacji będzie można przeglądać nowo zainstalowany __profil zarządzania__ na liście __Profile urządzeń__.

 ![Zainstalowany profil w systemie macOS](./media/macOS_enroll_007_sysprefs_installed_profile.png)

Nadal potrzebujesz pomocy? Skonsultuj się z administratorem IT. Odpowiednie informacje kontaktowe możesz znaleźć w [witrynie aplikacji Portal firmy](http://portal.manage.microsoft.com).

