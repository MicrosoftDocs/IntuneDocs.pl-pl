---
title: Rejestrowanie urządzenia z systemem Windows 10 w usłudze Intune | Microsoft Docs
description: Rejestrowanie urządzenia z systemem Windows 10 w wersji 1607 lub nowszej w usłudze Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 812e82df-76df-402b-bfe9-29302838f40e
searchScope:
- User help
ROBOTS: ''
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 21332f5441d6b2318a8739feb0457021cb7e442b
ms.sourcegitcommit: 8117444cfdddf6d9bdbc4ac715af8d88e72f411d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/03/2018
ms.locfileid: "48260221"
---
# <a name="enroll-your-windows-10-device-in-intune"></a>Rejestrowanie urządzenia z systemem Windows 10 w usłudze Intune

> [!NOTE]
> System Windows 10 działa na wszystkich typach urządzeń. Niezależnie od tego, czy używasz komputera, telefonu, czy tabletu kroki, które wykonujesz, są takie same, nawet jeśli ekran wygląda nieco inaczej niż obrazy na tej stronie.

> [!VIDEO https://channel9.msdn.com/Series/IntuneEnrollment/Windows-Enrollment/player]

1. Przejdź do pozycji **Start**.

   - Jeśli używasz urządzenia z systemem **Windows 10 Desktop**, otwórz **Menu Start**.
   - Jeśli używasz urządzenia z systemem **Windows 10 Mobile**, otwórz **Ekran startowy**, a następnie przesuń do listy **Wszystkie aplikacje**.

2. Otwórz aplikację **Ustawienia** systemu Windows, wyszukując termin „ustawienia” na pasku wyszukiwania.

3. Wybierz kolejno pozycje **Konta** > **Uzyskaj dostęp do miejsca pracy lub nauki** > **Połącz**.

    ![Wybieranie pozycji Uzyskaj dostęp do miejsca pracy lub nauki](./media/w10-enroll-rs1-connect-to-work-or-school.png)

4. Wprowadź służbowy adres e-mail, a następnie wybierz przycisk **Dalej**.

   ![Wprowadź dane konta służbowego](./media/w10-enroll-rs1-set-up-work-or-school-account.png)

5. Zaloguj się do usługi Intune przy użyciu konta służbowego.

    ![Dodaj konto służbowe](./media/w10-enroll-rs1-enter-your-credentials.png)

    Pojawi się komunikat informujący o tym, że firma lub szkoła rejestruje urządzenie.

6. Po wyświetleniu strony **Wszystko jest gotowe!** wybierz opcję **Zamknij**. To wszystko.

   ![Po wyświetleniu ekranu „Wszystko jest gotowe!” wybierz opcję Zamknij](./media/w10-enroll-rs1-youre-all-set.png)

7. Jeśli chcesz się upewnić, że połączenie jest prawidłowo skonfigurowane, wróć do obszaru **Ustawienia** i sprawdź, czy konto służbowe znajduje się na liście.

    ![Sprawdź, czy połączenie zostało poprawnie skonfigurowane](./media/w10-enroll-rs1-validate-successful-enrollment.png)

Jeśli powyższe kroki zostały wykonane, ale nadal nie można uzyskać dostępu do służbowego konta e-mail i plików, wykonaj czynności opisane w części [Rozwiązywanie problemów w przypadku wyświetlenia ekranu Dostęp do zasobów służbowych](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-access-work-or-school).
