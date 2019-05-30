---
title: Szybki start — zasady zgodności haseł dla urządzeń z systemem Android
titleSuffix: Microsoft Intune
description: W tym przewodniku Szybki start użyjesz usługi Microsoft Intune do ustawienia długości hasła wymaganej w przypadku urządzeń z systemem Android.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/15/2019
ms.topic: quickstart
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 81b4fa08-5333-4c54-9f49-8db5f6984ed2
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1dec78e0b1e323e99b6e70f71db982256aa98d18
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/23/2019
ms.locfileid: "66041221"
---
# <a name="quickstart-create-a-password-compliance-policy-for-android-devices"></a>Szybki start: Tworzenie zasad zgodności haseł dla urządzeń z systemem Android

W tym przewodniku Szybki start użyjesz usługi Microsoft Intune, aby wymagać od pracowników korzystających z systemu Android wprowadzenia hasła o określonej długości przed uzyskaniem dostępu do informacji na ich urządzeniach z systemem Android. 

Zasady zgodności urządzeń w usłudze Intune określają reguły i ustawienia, które urządzenia muszą spełnić, aby zostały uznane za zgodne. Można wykorzystać zasady zgodności do stosowania dostępu warunkowego, aby zezwolić na dostęp do zasobów firmy lub go zablokować. Można również pobrać raporty urządzeń i podjąć akcje w przypadku niezgodności.

> [!IMPORTANT]
> Oprócz ustawień hasła należy również rozważyć użycie innych ustawień zabezpieczeń systemu, które pomogą Ci chronić pracowników. Aby uzyskać więcej informacji, zobacz [Ustawienia zabezpieczeń systemu](compliance-policy-create-android-for-work.md).

Jeśli nie masz subskrypcji usługi Intune, [utwórz konto bezpłatnej wersji próbnej](free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Logowanie się do usługi Intune

Zaloguj się w usłudze [Intune](https://aka.ms/intuneportal) jako administrator globalny lub administrator usługi Intune. 

## <a name="create-a-device-compliance-policy"></a>Tworzenie zasad zgodności urządzenia

W tym przewodniku Szybki start użyjesz usługi Intune, aby wymagać od pracowników korzystających z systemu Android wprowadzenia hasła o określonej długości przed uzyskaniem dostępu do informacji na ich urządzeniach z systemem Android.

1. W usłudze Intune wybierz pozycję **Zgodność urządzeń** > **Zasady** > **Utwórz zasady**.
2. Dodaj pozycję **Zgodność dla systemu Android** jako **nazwę**. Następnie dodaj **opis**.
3. W polu **Platforma** wybierz opcję **Android**. 
4. Wybierz kolejno pozycje **Ustawienia** > **Zabezpieczenia systemu**, aby wyświetlić blok **Zabezpieczenia systemu** dla systemu Android.
5. Kliknij polecenie **Wymagaj** znajdujące się obok polecenia **Wymagaj hasła do odblokowania urządzeń przenośnych**.
6. Wybierz opcję **Co najmniej numeryczne** obok pozycji **Wymagany typ hasła**.
7. Wprowadź liczbę **6** obok pozycji **Minimalna długość hasła**. 

    ![Zrzut ekranu przedstawiający tworzenie grupy w usłudze Microsoft Intune](media/quickstart-set-password-length-android/quickstart-set-password-length-android-01.png)

7. Gdy wszystko będzie gotowe, kliknij pozycję **OK** > **OK** > **Utwórz**, aby utworzyć zasady.

Jeśli zasady zostały pomyślnie utworzone, pojawią się na liście zasad zgodności urządzenia. 

## <a name="clean-up-resources"></a>Oczyszczanie zasobów

Gdy te zasady nie będą już potrzebne, usuń je. Aby to zrobić, wybierz zasady i kliknij przycisk **Usuń**.

## <a name="next-steps"></a>Następne kroki

W tym przewodniku Szybki start użyto usługi Intune do utworzenia zasad zgodności dla urządzeń z systemem Android pracowników, które będą wymagać wprowadzenia hasła składającego się z co najmniej sześciu znaków. Aby dowiedzieć się więcej na temat tworzenia zasad zgodności, zobacz [Wprowadzenie do zasad zgodności urządzeń w usłudze Intune](device-compliance-get-started.md).

Aby zapoznać się kolejnymi przewodnikami Szybki start dotyczącymi usługi Intune, przejdź do kolejnego przewodnika Szybki start.

> [!div class="nextstepaction"]
> [Szybki start: Wysyłanie powiadomień do niezgodnych urządzeń](quickstart-send-notification.md)
