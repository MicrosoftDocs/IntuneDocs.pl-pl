---
title: Szybki start — ustawianie wymaganej długości hasła dla urządzeń z systemem Android
titlesuffix: Microsoft Intune
description: W tym przewodniku Szybki start użyjesz usługi Microsoft Intune do ustawienia długości hasła wymaganej w przypadku urządzeń z systemem Android.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/17/2018
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 81b4fa08-5333-4c54-9f49-8db5f6984ed2
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f925df731c3ddd45b13d976b0686d76d941c71e6
ms.sourcegitcommit: 2e88ec7a412a2db35034d30a70d20a5014ddddee
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2018
ms.locfileid: "49395299"
---
# <a name="quickstart-set-a-required-password-length-for-android-devices"></a>Szybki start: ustawianie wymaganej długości hasła dla urządzeń z systemem Android

W tym przewodniku Szybki start użyjesz usługi Microsoft Intune, aby wymagać od pracowników korzystających z systemu Android wprowadzenia hasła o określonej długości przed uzyskaniem dostępu do informacji na ich urządzeniach z systemem Android. 

> [!IMPORTANT]
> Oprócz ustawień hasła należy również rozważyć użycie innych ustawień zabezpieczeń systemu, które pomogą Ci chronić pracowników. Aby uzyskać więcej informacji, zobacz [Ustawienia zabezpieczeń systemu](compliance-policy-create-android-for-work.md#system-security-settings).

Jeśli nie masz subskrypcji usługi Intune, [utwórz konto bezpłatnej wersji próbnej](free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Logowanie się do usługi Intune

Zaloguj się w usłudze [Intune](https://aka.ms/intuneportal) jako administrator globalny lub administrator usługi Intune. Dostęp do usługi Intune można uzyskać w witrynie Azure Portal, wybierając pozycję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.

## <a name="create-a-device-compliance-policy"></a>Tworzenie zasad zgodności urządzenia
1. Po otwarciu bloku **Microsoft Intune** wybierz kolejno pozycje **Zgodność urządzenia** > **Zasady** > **Utwórz zasady**.
2. Dodaj pozycję **Zgodność dla systemu Android** jako **nazwę**. Następnie dodaj **opis**.
3. W polu **Platforma** wybierz opcję **Android**. 
4. Wybierz kolejno pozycje **Ustawienia** > **Zabezpieczenia systemu**, aby wyświetlić blok **Zabezpieczenia systemu** dla systemu Android.
5. W sekcji **Hasło** obok pozycji **Wymagaj hasła do odblokowania urządzeń przenośnych** kliknij pozycję **Wymagaj**.
6. Obok pozycji **Minimalna długość hasła** wprowadź wartość **6**.  

    ![Zrzut ekranu przedstawiający tworzenie grupy w usłudze Microsoft Intune](./media/quickstart-set-password-length-android-01.png)

7. Po zakończeniu kliknij przycisk **OK**, aby zamknąć blok **Zabezpieczenia systemu**. 
8. Kliknij przycisk **OK**, aby zamknąć blok **Zasady zgodności dla systemu Android**. 
9. Kliknij pozycję **Utwórz**, aby utworzyć zasady.

Jeśli zasady zostały pomyślnie utworzone, pojawią się na liście **Zgodność urządzenia — zasady**. 

## <a name="next-steps"></a>Następne kroki

W tym przewodniku Szybki start użyto usługi Intune do utworzenia zasad zgodności dla urządzeń z systemem Android pracowników, które będą wymagać wprowadzenia hasła składającego się z co najmniej sześciu znaków.

> [!div class="nextstepaction"]
> [Konfigurowanie automatycznego rejestrowania](quickstart-setup-auto-enrollment.md)
