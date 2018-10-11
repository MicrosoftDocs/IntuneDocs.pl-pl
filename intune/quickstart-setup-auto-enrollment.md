---
title: Szybki start — konfigurowanie automatycznego rejestrowania w usłudze Intune
description: Szybki start — konfigurowanie automatycznego rejestrowania urządzeń z systemem Windows 10 w usłudze Intune.
services: microsoft-intune
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: quickstart
ms.date: 09/21/2018
ms.author: erikje
ms.openlocfilehash: 3b713f090fb6ada884a269e286f55f6e1b1087c4
ms.sourcegitcommit: 27eed5aba5c8bfafb079171081b68f75a6cbffaf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2018
ms.locfileid: "46581781"
---
# <a name="quickstart-set-up-automatic-enrollment-for-windows-10-devices"></a>Szybki start: konfigurowanie automatycznego rejestrowania urządzeń z systemem Windows 10

W tym przewodniku Szybki start skonfigurujesz w usłudze Microsoft Intune automatyczne rejestrowanie urządzeń w przypadku logowania się określonych użytkowników na urządzeniach z systemem Windows 10.

Jeśli nie masz subskrypcji usługi Intune, [utwórz konto bezpłatnej wersji próbnej](free-trial-sign-up.md).

## <a name="prerequisites"></a>Wymagania wstępne

- Aby zrealizować zadania w tym przewodniku Szybki start, musisz najpierw [utworzyć użytkownika](quickstart-create-user.md) i [utworzyć grupę](quickstart-create-group.md).

## <a name="sign-in-to-intune"></a>Logowanie się do usługi Intune

Zaloguj się w usłudze [Intune](https://aka.ms/intuneportal) jako administrator globalny lub administrator usługi Intune.

## <a name="set-up-windows-10-automatic-enrollment"></a>Konfigurowanie automatycznego rejestrowania urządzeń z systemem Windows 10

W tym przykładzie użyjesz rejestracji MDM, aby umożliwić rejestrowanie urządzeń zarówno firmowych, jak i przynoszonych przez użytkowników (BYOD).

1. Na platformie Azure wybierz pozycję **Azure Active Directory** > **Mobilność (MDM i MAM)** > **Microsoft Intune** > **Niektóre**.
![Przeglądarka](media/quickstart-setup-auto-enrollment/setup-automatic-enrollment-win10.png)
2. Wybierz pozycję **Wybierz grupy** > **Contoso Testers (Testerzy Contoso)** > **Wybierz**.
3. Użyj wartości domyślnych dla następujących adresów URL:
    - Adres URL warunków użytkowania zarządzania urządzeniami przenośnymi
    - Adres URL odnajdywania zarządzania urządzeniami przenośnymi
    - Adres URL zgodności zarządzania urządzeniami przenośnymi
4. Wybierz polecenie **Zapisz**.
5. Zaloguj się jako użytkownik w grupie na urządzeniu z systemem Windows 10 i postępuj zgodnie z monitami.

## <a name="clean-up-resources"></a>Oczyszczanie zasobów

Aby ponownie skonfigurować automatyczne rejestrowanie w usłudze Intune, zobacz [Konfigurowanie rejestracji dla urządzeń z systemem Windows](windows-enroll.md).

## <a name="next-steps"></a>Następne kroki

W tym przewodniku Szybki start przedstawiono sposób konfigurowania automatycznego rejestrowania urządzeń z systemem Windows 10. Możesz też zapoznać się z innymi sposobami rejestrowania urządzeń na wszystkich platformach.

> [!div class="nextstepaction"]
> [Artykuł: Co to jest rejestrowanie urządzenia?](device-enrollment.md)