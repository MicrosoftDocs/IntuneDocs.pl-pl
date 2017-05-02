---
title: "Zdalne blokowanie i resetowanie kodu dostępu | Microsoft Docs"
description: "Usługa Intune umożliwia zdalne blokowanie i resetowanie kodu dostępu."
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 03/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 970f8c81-7c7f-4789-9ed4-2133d50b9db6
ms.reviewer: chrisgre
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: f0a477c9eb1ed0580314e79135e377809eaab197
ms.openlocfilehash: 9b0ae19b211373548061e2c2979620739a0bf0a0
ms.lasthandoff: 04/17/2017

---
# <a name="help-protect-your-devices-with-remote-lock-and-passcode-reset"></a>Łatwiejsza ochrona urządzeń za pomocą funkcji zdalnego blokowania i resetowania kodu dostępu

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Usługa Microsoft Intune umożliwia zdalne blokowanie i resetowanie kodu dostępu.

## <a name="lock-a-device-remotely"></a>Zdalne blokowanie urządzenia
Jeśli użytkownik utraci urządzenie, można zablokować je zdalnie. Aby możliwe było użycie funkcji zdalnego blokowania, w urządzeniu musi już być ustawiony kod PIN lub kod dostępu.

W poniższej tabeli przedstawiono sposób zdalnego blokowania na różnych platformach mobilnych.

|Platforma|Zdalne blokowanie|
|------------|---------------|
|macOS|Nieobsługiwane|
|iOS|Obsługiwane|
|Android|Obsługiwane|
|Program Android for Work|Obsługiwane|
|Windows 10 (urządzenia przenośne)|Obsługiwane|
|Windows 10 (komputery)|Nieobsługiwane|
|Windows Phone 8 i Windows Phone 8.1|Obsługiwane|
|Windows RT 8.1 i Windows RT|Obsługiwane, jeśli bieżący użytkownik urządzenia jest tym samym użytkownikiem, który zarejestrował urządzenie.|
|Windows 8.1|Obsługiwane, jeśli bieżący użytkownik urządzenia jest tym samym użytkownikiem, który zarejestrował urządzenie.|

Zdalne blokowanie nie jest obsługiwane w przypadku komputerów z systemem Windows zarejestrowanych przy użyciu oprogramowania klienckiego usługi Intune.

### <a name="lock-a-mobile-device-remotely-through-the-intune-console"></a>Zdalne blokowanie urządzenia przenośnego za pośrednictwem konsoli usługi Intune

1.  W [konsoli administratora usługi Intune](https://manage.microsoft.com/) wybierz pozycje **Grupy** &gt; **Wszystkie urządzenia** &gt; **Wszystkie urządzenia przenośne**.

2.  Wybierz pozycję **Wszystkie urządzenia zarządzane bezpośrednio** w przypadku urządzeń zarejestrowanych w usłudze Intune lub wybierz pozycję **Wszystkie urządzenia zarządzane za pośrednictwem programu Exchange ActiveSync**.

    > [!TIP]
    > Można także przechodzić do urządzeń poszczególnych użytkowników. Wybierz pozycję **Wszyscy użytkownicy**. Na stronie właściwości użytkownika wybierz pozycję **Urządzenia**, a następnie wybierz nazwę urządzenia przenośnego, które chcesz zablokować.

3.  Na liście wybierz urządzenia, które chcesz zablokować. Na pasku zadań wybierz pozycję **Zadania zdalne** i wybierz pozycję **Zdalne blokowanie**.

## <a name="reset-the-passcode-on-a-device"></a>Resetowanie kodu dostępu na urządzeniu
Jeśli użytkownik zapomni kod dostępu, możesz pomóc przez usunięcie kodu dostępu z urządzenia lub wymuszenie nowego, tymczasowego kodu dostępu na urządzeniu. W poniższej tabeli przedstawiono sposób działania resetowania kodu dostępu na różnych platformach mobilnych.

|Platforma|Resetowanie kodu dostępu|
|------------|------------------|
|macOS|Nieobsługiwane|
|iOS|Obsługiwane czyszczenie kodu dostępu z urządzenia. Nie powoduje utworzenia nowego hasła tymczasowego.|
|Android|Obsługiwane w wersjach wcześniejszych niż Android 7.0. Powoduje utworzenie tymczasowego kodu dostępu.|
|Program Android for Work|Nieobsługiwane|
|Windows 10 Mobile|Obsługiwane w przypadku dołączonych do usługi Azure AD urządzeń przenośnych z aktualizacją systemu Windows 10 dla twórców lub nowszą wersją.|
|Windows Phone 8 i Windows Phone 8.1|Obsługiwane|
|Windows RT 8.1|Nieobsługiwane|
|Windows 8.1|Nieobsługiwane|
|Windows 10 Desktop|Nieobsługiwane|

Resetowanie kodu dostępu nie jest obsługiwane w przypadku komputerów z systemem Windows zarejestrowanych przy użyciu oprogramowania klienckiego usługi Intune.

### <a name="reset-a-passcode"></a>Resetowanie kodu dostępu

1.  W [konsoli administratora usługi Intune](https://manage.microsoft.com/) wybierz pozycje **Grupy** &gt; **Wszystkie urządzenia** &gt; **Wszystkie urządzenia przenośne**.

2.  Wybierz pozycję **Wszystkie urządzenia zarządzane bezpośrednio** w przypadku urządzeń zarejestrowanych w usłudze Intune lub wybierz pozycję **Wszystkie urządzenia zarządzane za pośrednictwem programu Exchange ActiveSync**.

    > [!TIP]
    > Można także przechodzić do urządzeń poszczególnych użytkowników. Kliknij pozycję **Wszyscy użytkownicy**. Na stronie właściwości użytkownika kliknij kartę **Urządzenia**, a następnie kliknij nazwę urządzenia przenośnego, które chcesz wyczyścić.

3.  Na liście wybierz urządzenia, które chcesz zablokować. Na pasku zadań wybierz pozycję **Zadania zdalne** i wybierz pozycję **Resetowanie kodu dostępu**.


### <a name="see-also"></a>Zobacz też
[Wycofywanie urządzeń](retire-devices-from-microsoft-intune-management.md) oraz [Selektywne czyszczenie danych w systemie Windows w celu zarządzania danymi urządzenia](http://technet.microsoft.com/library/dn486874.aspx)

