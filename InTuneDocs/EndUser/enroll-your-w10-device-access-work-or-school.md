---
title: "Rejestrowanie urządzenia z systemem Windows 10 w usłudze Intune | Microsoft Docs"
description: "Rejestrowanie urządzenia z systemem Windows 10 (w wersji 1607) w usłudze Intune"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/17/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 812e82df-76df-402b-bfe9-29302838f40e
searchScope:
- User help
ROBOTS: 
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
translationtype: Human Translation
ms.sourcegitcommit: cfd6d509b6683f563d56ef149ff3739de4772394
ms.openlocfilehash: c87be1a3cdea23d5d40dcd8abe902b4ee5c06bc4
ms.lasthandoff: 02/18/2017


---

# <a name="enroll-your-windows-10-device-in-intune"></a>Rejestrowanie urządzenia z systemem Windows 10 w usłudze Intune

<iframe src="https://channel9.msdn.com/Series/IntuneEnrollment/Windows-Enrollment-with-AAD/player" width="960" height="540" allowFullScreen frameBorder="0"></iframe>

1.  Otwórz aplikację **Ustawienia** systemu Windows, przechodząc do **menu Start** i wybierając przycisk **Ustawienia**. Możesz również wyszukać „ustawienia” na pasku wyszukiwania.

2. Wybierz kolejno pozycje **Konta** > **Uzyskaj dostęp do miejsca pracy lub nauki** > **Połącz**.

    ![Wybieranie pozycji Uzyskaj dostęp do miejsca pracy lub nauki](./media/w10-enroll-rs1-connect-to-work-or-school.png)

3.  Wprowadź służbowy adres e-mail, a następnie wybierz przycisk **Dalej**.

    ![Wprowadź dane konta służbowego](./media/w10-enroll-rs1-set-up-work-or-school-account.png)

4. Zaloguj się do usługi Intune przy użyciu konta służbowego.

    ![Dodaj konto służbowe](./media/w10-enroll-rs1-enter-your-credentials.png)

    Pojawi się komunikat informujący o tym, że firma lub szkoła rejestruje urządzenie.

5. Po wyświetleniu strony **Wszystko jest gotowe!** wybierz opcję **Zamknij**. To wszystko.

  ![Po wyświetleniu ekranu „Wszystko jest gotowe!” wybierz opcję Zamknij](./media/w10-enroll-rs1-youre-all-set.png)

6. Jeśli chcesz się upewnić, że połączenie jest prawidłowo skonfigurowane, wróć do obszaru **Ustawienia** i sprawdź, czy konto służbowe znajduje się na liście.

    ![Sprawdź, czy połączenie zostało poprawnie skonfigurowane](./media/w10-enroll-rs1-validate-successful-enrollment.png)

Jeśli powyższe kroki zostały wykonane, ale nadal nie można uzyskać dostępu do służbowego konta e-mail i plików, wykonaj czynności opisane w części [Rozwiązywanie problemów w przypadku wyświetlenia ekranu Dostęp do zasobów służbowych](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-access-work-or-school).

