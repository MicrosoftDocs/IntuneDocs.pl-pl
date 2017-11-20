---
title: "Rejestrowanie starszego urządzenia z systemem macOS w usłudze Intune | Microsoft Docs"
description: "Opis sposobu rejestrowania urządzenia z systemem macOS w usłudze Intune"
keywords: Mac OS X, macOS, OS X
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 58eb0e7a-1321-4c66-a281-88fb01e72c1c
searchScope: User help
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 115f32989cfbb991e097404c5297e7997f28f796
ms.sourcegitcommit: e692be57ec7044dfc224b70941affbfd7efba421
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/08/2017
---
# <a name="enroll-your-legacy-macos-device-in-intune"></a>Rejestrowanie starszego urządzenia z systemem macOS w usłudze Intune

Te instrukcje będą działać w przypadku urządzeń z systemem macOS w wersji OS X Yosemite 10.10 i starszych. Instrukcje dotyczące rejestrowania urządzeń z systemem macOS dla nowszych wersji systemu macOS można znaleźć [tutaj](enroll-your-device-in-intune-macos-cp.md).

Uzyskiwanie dostępu do aplikacji, danych i zasobów organizacji umożliwia Ci wykonywanie pracy. Jeśli używasz urządzenia z systemem macOS w miejscu pracy, musisz zainstalować __profil zarządzania__. Jest to po prostu plik skonfigurowany przez dział pomocy technicznej Twojej firmy umożliwiający załadowanie ustawień i informacji dotyczących dostępu na komputerze Mac. Chcesz wiedzieć więcej? Sprawdź, [co dzieje się w przypadku zainstalowania aplikacji Portal firmy i zarejestrowania urządzenia w usłudze Intune](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md)

1. Na __Docku__ znajdź pozycję __Safari__ i otwórz nowe okno, a następnie otwórz [witrynę aplikacji Portal firmy](https://portal.manage.microsoft.com).
2. Zaloguj się do witryny aplikacji Portal firmy przy użyciu konta służbowego.

  [!INCLUDE[wit_nextref](includes/end-user-password-guidance.md)]

3. Po zalogowaniu się kliknij pozycję **Menu** w lewym górnym rogu strony i wybierz pozycję **Moje urządzenia**.

 ![Zrzut ekranu strony początkowej portalu sieci Web z informacją, że nie można jeszcze zainstalować żadnych aplikacji, oraz przyciskiem Moje urządzenia poniżej.](./media/macOS_enroll_001_landing_page.png)

4. Na stronie __Moje urządzenia__ zostanie wyświetlona lista zarejestrowanych urządzeń lub transparent. Jest to zależne od tego, czy masz już zarejestrowane urządzenia z systemem macOS lub inne. Aby zarejestrować urządzenie, którego nie ma na liście, wybierz transparent z informacją __Jeśli urządzenie jest na liście, naciśnij tutaj, aby je zidentyfikować. Możesz również nacisnąć tutaj, aby zarejestrować urządzenie, jeśli nie ma go na liście__. Jeśli nie masz żadnych zarejestrowanych urządzeń, na banerze będzie wyświetlany komunikat **Nie masz żadnych zarejestrowanych urządzeń. Zarejestruj urządzenie, naciskając tutaj.**

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

Niektóre profile mogą informować, że są **Niezweryfikowane**; o ile pochodzą one z Twojej firmy, jest to normalne.

Nadal potrzebujesz pomocy? Skontaktuj się z działem pomocy technicznej Twojej firmy. Odpowiednie informacje kontaktowe możesz znaleźć w [witrynie aplikacji Portal firmy](https://portal.manage.microsoft.com).
