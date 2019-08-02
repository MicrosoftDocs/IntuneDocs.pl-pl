---
title: Szybki start — rejestrowanie urządzenia z systemem Windows 10 Desktop w usłudze Microsoft Intune
description: Szybki start — rejestrowanie urządzenia z systemem Windows 10 Desktop w usłudze Microsoft Intune za pomocą Portalu firmy.
services: microsoft-intune
author: ErikRe
ms.author: erikre
manager: dougeby
ms.date: 07/30/2019
ms.topic: quickstart
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 658a7655-a6df-4dbe-b56c-22c7fc60e706
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: efd4e8d013f0205541f6fcc37bb0bb8b5ea75bac
ms.sourcegitcommit: 99b74d7849fbfc8f5cf99cba33e858eeb9f537aa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/31/2019
ms.locfileid: "68670845"
---
# <a name="quickstart-enroll-your-windows-10-device"></a>Szybki start: Rejestrowanie urządzenia z systemem Windows 10

W tym przewodniku Szybki start najpierw przyjmiesz rolę użytkownika usługi Intune i zarejestrujesz urządzenie z systemem Windows 10 w usłudze Microsoft Intune. Następnie wrócisz do usługi Intune i potwierdzisz, że urządzenie zostało zarejestrowane.

Zarejestrowanie urządzeń z systemem Windows 10 w usłudze Microsoft Intune umożliwia pracownikom organizacji uzyskiwanie dostępu do zabezpieczonych danych, w tym plików, wiadomości e-mail i innych zasobów. Dotyczy to urządzeń z systemami Windows 10 Desktop i Windows 10 Mobile. Zarejestrowanie urządzeń ułatwia zabezpieczenie dostępu zarówno z perspektywy administratora, jak i całej organizacji, a także pomaga w rozdzieleniu danych służbowych od prywatnych.

> [!TIP]
> Dowiedz się, co się dzieje po [zarejestrowaniu urządzenia w usłudze Intune](/intune-user-help/what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows) i jak ten proces wpływa na [informacje przechowywane na urządzeniu](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).

Jeśli nie masz subskrypcji usługi Intune, [utwórz konto bezpłatnej wersji próbnej](free-trial-sign-up.md).

## <a name="prerequisites"></a>Wymagania wstępne

- Subskrypcja usługi Microsoft Intune — [zarejestruj się, aby uzyskać bezpłatne konto](free-trial-sign-up.md)
- Aby ukończyć ten przewodnik Szybki start, musisz ukończyć procedurę [konfigurowania automatycznej rejestracji w usłudze Intune](quickstart-setup-auto-enrollment.md).

## <a name="confirm-your-windows-10-desktop-version"></a>Sprawdzanie posiadanej wersji systemu Windows 10 Desktop

Zanim zarejestrujesz system Windows 10 Desktop, musisz sprawdzić, którą wersję tego systemu masz zainstalowaną.

1. Kliknij prawym przyciskiem myszy ikonę **Start** systemu Windows i wybierz pozycję **Ustawienia** w celu wyświetlenia opcji ustawień systemu Windows.

   ![Zrzut ekranu z ustawieniami systemu Windows — System](media/quickstart-enroll-windows-device/quickstart-enroll-windows-device-01.png)

2. Wybierz pozycje **System** > **Informacje**. 

   ![Zrzut ekranu przedstawiający ustawienia systemu](media/quickstart-enroll-windows-device/quickstart-enroll-windows-device-02.png)

    > [!TIP]
    > Możesz też wpisać wyrażenie „informacje o komputerze” w **pasku wyszukiwania**, a następnie wybrać pozycję **Informacje o komputerze**.

3. W oknie **Ustawienia** zobaczysz listę **specyfikacji systemu Windows** dla swojego komputera. Znajdź pozycję **Wersja** na tej liście.

4. Upewnij się, że system Windows 10 jest w **wersji** **1607 lub nowszej**.

    > [!IMPORTANT]
    > Kroki przedstawione w tym przewodniku Szybki start dotyczą systemu Windows 10 w wersji **1607 lub nowszej**. Jeśli używasz wersji **1511 lub starszej**, przejdź do [tych kroków](/intune-user-help/enroll-windows-10-device).  

## <a name="enroll-windows-10-desktop"></a>Rejestrowanie komputera z systemem Windows 10

1. Wróć do ustawień systemu Windows i wybierz pozycję **Konta**.

   ![Zrzut ekranu z ustawieniami systemu — Konta](media/quickstart-enroll-windows-device/quickstart-enroll-windows-device-03.png)

2. Wybierz pozycje **Uzyskaj dostęp do miejsca pracy lub nauki** > **Połącz**.

    ![Wybieranie pozycji Uzyskaj dostęp do miejsca pracy lub nauki](media/quickstart-enroll-windows-device/quickstart-enroll-windows-device-04.png)

3. Zaloguj się do usługi Intune przy użyciu konta służbowego, a następnie wybierz pozycję **Dalej**. Jeśli wykonano kroki z przewodnika Szybki start dotyczącego [tworzenia użytkownika i przypisywania licencji](quickstart-create-user.md), możesz zalogować się przy użyciu utworzonego konta użytkownika.

    > [!NOTE]
    > Jeśli konfigurujesz domenę „.onmicrosoft.com”, konto użytkownika będzie mieć w adresie fragment **.onmicrosoft.com**. 

   ![Wprowadzanie konta służbowego](media/quickstart-enroll-windows-device/quickstart-enroll-windows-device-05.png)

    Pojawi się komunikat informujący o tym, że firma lub szkoła rejestruje urządzenie.

4. Po wyświetleniu strony **Wszystko jest gotowe!** wybierz pozycję **Gotowe**. To wszystko.

5. Zobaczysz dodane konto jako część ustawień **Uzyskaj dostęp do miejsca pracy lub nauki** w systemie Windows Desktop.

   ![Zrzut ekranu z nowo dodanym kontem](media/quickstart-enroll-windows-device/quickstart-enroll-windows-device-06.png)

    Jeśli powyższe kroki zostały wykonane, ale nadal nie można uzyskać dostępu do służbowego konta e-mail i plików, wykonaj czynności opisane w części [Rozwiązywanie problemów w przypadku wyświetlenia ekranu Dostęp do zasobów służbowych](/intune-user-help/troubleshoot-your-windows-10-device-windows#troubleshooting-steps-to-follow-if-you-see-access-work-or-school).

## <a name="confirm-your-device-enrollment-in-intune"></a>Potwierdzanie rejestracji urządzenia w usłudze Intune

1. Zaloguj się w usłudze [Intune](https://aka.ms/intuneportal) jako administrator globalny lub administrator usługi Intune.
2. Wybierz pozycje **Urządzenia** > **Wszystkie urządzenia**, aby wyświetlić urządzenia zarejestrowane w usłudze Intune.
3. Sprawdź, czy masz w usłudze Intune zarejestrowane dodatkowe urządzenie.

   ![Zrzut ekranu z urządzeniami zarejestrowanymi w usłudze Intune](media/quickstart-enroll-windows-device/quickstart-enroll-windows-device-07.png)

## <a name="clean-up-resources"></a>Oczyszczanie zasobów

Aby wyrejestrować urządzenie z systemem Windows, zobacz [Usuwanie urządzenia z systemem Windows z zarządzania](/intune-user-help/unenroll-your-device-from-intune-windows).

## <a name="next-steps"></a>Następne kroki

W tym przewodniku Szybki start przedstawiono sposób rejestrowania urządzenia z systemem Windows 10 w usłudze Intune. Możesz też zapoznać się z innymi sposobami rejestrowania urządzeń na wszystkich platformach. Aby uzyskać więcej informacji o używaniu urządzeń z usługą Intune, zobacz [Wykonywanie pracy przy użyciu urządzeń zarządzanych](/intune-user-help/use-managed-devices-to-get-work-done).

Aby zapoznać się kolejnymi przewodnikami Szybki start dotyczącymi usługi Intune, przejdź do kolejnego przewodnika Szybki start.

> [!div class="nextstepaction"]
> [Szybki start: ustawianie wymaganej długości hasła dla urządzeń z systemem Android](quickstart-set-password-length-android.md)
