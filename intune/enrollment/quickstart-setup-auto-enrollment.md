---
title: Szybki start — konfigurowanie automatycznego rejestrowania w usłudze Intune
description: Szybki start — konfigurowanie automatycznego rejestrowania urządzeń z systemem Windows 10 w usłudze Intune.
services: microsoft-intune
author: ErikjeMS
manager: dougeby
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.topic: quickstart
ms.date: 01/17/2020
ms.author: erikje
ms.reviewer: spshumwa
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: e5cc7cf3661caa2b2640d9370d26402b7702d36b
ms.sourcegitcommit: 70b40aa4743c8396f8d6a0163893c4a337d67c48
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2020
ms.locfileid: "76541066"
---
# <a name="quickstart-set-up-automatic-enrollment-for-windows-10-devices"></a>Szybki start: Konfigurowanie automatycznego rejestrowania urządzeń z systemem Windows 10

W tym przewodniku Szybki start skonfigurujesz w usłudze Microsoft Intune automatyczne rejestrowanie urządzeń w przypadku logowania się określonych użytkowników na urządzeniach z systemem Windows 10.

Jeśli nie masz subskrypcji usługi Intune, [utwórz konto bezpłatnej wersji próbnej](../fundamentals/free-trial-sign-up.md).

## <a name="prerequisites"></a>Wymagania wstępne

- Subskrypcja usługi Intune: [utwórz konto bezpłatnej wersji próbnej](../fundamentals/free-trial-sign-up.md).
- Aby zrealizować zadania w tym przewodniku Szybki start, musisz najpierw [utworzyć użytkownika](../fundamentals/quickstart-create-user.md) i [utworzyć grupę](../fundamentals/quickstart-create-group.md).

## <a name="sign-in-to-intune-in-the-microsoft-endpoint-manager"></a>Logowanie do usługi Intune w programie Microsoft Endpoint Manager

Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) jako administrator globalny lub administrator usługi Intune. Jeśli utworzono subskrypcję wersji próbnej usługi Intune, konto, którego użyto do utworzenia subskrypcji, jest administratorem globalnym.

## <a name="set-up-windows-10-automatic-enrollment"></a>Konfigurowanie automatycznego rejestrowania urządzeń z systemem Windows 10

W tym przykładzie użyjesz rejestracji w usłudze zarządzaniami urządzeniami przenośnymi, aby umożliwić automatyczne rejestrowanie urządzeń zarówno firmowych, jak i przynoszonych przez użytkowników (BYOD). Utworzysz bezpłatną subskrypcję usługi Azure Active Directory w wersji Premium.

1. W [centrum administracyjnym programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) wybierz pozycję **Wszystkie usługi** > **M365 Azure Active Directory** > **Azure Active Directory** > **Mobilność (zarządzanie urządzeniami przenośnymi i aplikacjami mobilnymi)** .
2. Wybierz pozycję **Uzyskaj bezpłatnie wersję próbną usługi w warstwie Premium, aby korzystać z tej funkcji**. Wybranie tej opcji umożliwi automatyczne zarejestrowanie przy użyciu wersji próbnej usługi Azure Active Directory w wersji Premium. 

    ![Wybieranie bezpłatnej wersji próbnej usługi Azure Active Directory w wersji Premium](./media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-01.png)

3. Wybierz opcję bezpłatnej wersji próbnej **Enterprise Mobility + Security E5**. 
4. Kliknij pozycję **Bezpłatna wersja próbna** > **Aktywuj** bezpłatną wersję próbną.

    ![Wybieranie bezpłatnej wersji próbnej Enterprise Mobility + Security E5](./media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-02.png)

    > [!NOTE]
    > Aktywacja może potrwać około minuty. 

3. Wybierz pozycję **Microsoft Intune**, aby skonfigurować usługę Intune. 

    ![Wybieranie pozycji Microsoft Intune z listy](./media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-03.png)

4. Wybierz pozycję **Niektóre** w obszarze **Zakres użytkownika oprogramowania MDM**, aby użyć automatycznej rejestracji w rozwiązaniu MDM w celu zarządzania danymi firmowymi na należących do pracowników urządzeniach z systemem Windows. Automatyczna rejestracja w rozwiązaniu MDM zostanie skonfigurowana na potrzeby scenariuszy obejmujących urządzenia połączone na platformie AAD oraz urządzenia własne.

    ![Wybieranie pozycji „Niektóre” na liście Konfiguruj](./media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-04.png)

5. Kliknij kolejno pozycje **Wybierz grupy** > **Contoso Testers** (Testerzy Contoso)  > **Wybierz** jako przypisaną grupę.

    ![Wybieranie grupy do zarejestrowania](./media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-05.png)

6. Wybierz pozycję **Niektóre** w obszarze **Zakres użytkownika funkcji zarządzania aplikacjami mobilnymi**, aby zarządzać danymi na urządzeniach pracowników.

    ![Wybieranie grupy do zarejestrowania](./media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-06.png)

7. Wybierz kolejno pozycje **Wybierz grupy** > **Contoso Testers** (Testerzy Contoso)  > **Wybierz** jako przypisaną grupę. 
8. Użyj domyślnych wartości dla pozostałych wartości konfiguracji.
9. Wybierz polecenie **Zapisz**.

## <a name="clean-up-resources"></a>Oczyszczanie zasobów

Aby ponownie skonfigurować automatyczne rejestrowanie w usłudze Intune, zobacz [Konfigurowanie rejestracji dla urządzeń z systemem Windows](windows-enroll.md).

## <a name="next-steps"></a>Następne kroki

W tym przewodniku Szybki start przedstawiono sposób konfigurowania automatycznego rejestrowania urządzeń z systemem Windows 10. Aby uzyskać informacje na temat rejestrowania urządzenia, zobacz [Co to jest rejestrowanie urządzenia?](device-enrollment.md)

Aby zapoznać się z kolejnymi przewodnikami Szybki start dotyczącymi usługi Intune, przejdź do kolejnego przewodnika Szybki start.

> [!div class="nextstepaction"]
> [Szybki start: Rejestrowanie urządzenia z systemem Windows 10](../quickstart-enroll-windows-device.md)
