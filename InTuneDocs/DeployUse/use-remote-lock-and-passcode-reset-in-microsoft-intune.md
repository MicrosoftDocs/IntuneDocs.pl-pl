---
title: Korzystanie z funkcji zdalnego blokowania i resetowania kodu dostępu | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 970f8c81-7c7f-4789-9ed4-2133d50b9db6

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: [ALIAS]
#ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:
---
# Łatwiejsza ochrona urządzeń za pomocą funkcji zdalnego blokowania i resetowania kodu dostępu
Usługa Microsoft Intune umożliwia zdalne blokowanie i resetowanie kodu dostępu.

## Zdalne blokowanie urządzenia
Jeśli użytkownik utraci urządzenie, można zablokować je zdalnie. W poniższej tabeli przedstawiono sposób zdalnego blokowania na różnych platformach mobilnych.

|Platforma|Zdalne blokowanie|
|------------|---------------|
|iOS|Obsługiwane|
|Android|Obsługiwane|
|Windows 10 Mobile|Obsługiwane|
|Windows Phone 8 i Windows Phone 8.1|Obsługiwane|
|Windows RT 8.1 i Windows RT|Obsługiwane, jeśli bieżący użytkownik urządzenia jest tym samym użytkownikiem, który zarejestrował urządzenie.|
|Windows 8.1|Obsługiwane, jeśli bieżący użytkownik urządzenia jest tym samym użytkownikiem, który zarejestrował urządzenie.|


### Aby zdalnie zablokować urządzenie przenośne za pośrednictwem konsoli usługi Intune

1.  W [konsoli administratora usługi Intune](https://manage.microsoft.com/) wybierz pozycje **Grupy** &gt; **Wszystkie urządzenia** &gt; **Wszystkie urządzenia przenośne**..

2.  Wybierz pozycję **Wszystkie urządzenia zarządzane bezpośrednio** w przypadku urządzeń zarejestrowanych w usłudze Intune lub wybierz pozycję **Wszystkie urządzenia zarządzane za pośrednictwem programu Exchange ActiveSync**..

    > [!TIP]
    > Można także przechodzić do urządzeń poszczególnych użytkowników. Wybierz pozycję **Wszyscy użytkownicy**. Na stronie właściwości użytkownika wybierz pozycję **Urządzenia**, a następnie wybierz nazwę urządzenia przenośnego, które chcesz wyczyścić.

3.  Na liście wybierz urządzenia, które chcesz zablokować. Na pasku zadań wybierz pozycję **Zadania zdalne** i wybierz pozycję **Zdalne blokowanie**..

## Resetowanie kodu dostępu na urządzeniu
Jeśli użytkownik zapomni swój kod dostępu, możesz mu pomóc przez usunięcie kodu dostępu z urządzenia lub wymuszenie nowego hasła tymczasowego na urządzeniu. W poniższej tabeli przedstawiono sposób działania resetowania kodu dostępu na różnych platformach mobilnych.

|Platforma|Resetowanie kodu dostępu|
|------------|------------------|
|iOS|Obsługiwane czyszczenie kodu dostępu z urządzenia. Nie powoduje utworzenia nowego hasła tymczasowego.|
|Android|Jest obsługiwane i powoduje utworzenie tymczasowego kodu dostępu.|
|Windows 10 Mobile|Obsługiwane|
|Windows Phone 8 i Windows Phone 8.1|Obsługiwane|
|Windows RT 8.1 i Windows RT|Nieobsługiwane|
|Windows 8.1|Nieobsługiwane|

### Aby zresetować kod dostępu

1.  W [konsoli administratora usługi Intune](https://manage.microsoft.com/) wybierz pozycję **Grupy** &gt; **Wszystkie urządzenia** &gt; **Wszystkie urządzenia przenośne**..

2.  Wybierz pozycję **Wszystkie urządzenia zarządzane bezpośrednio** w przypadku urządzeń zarejestrowanych w usłudze Intune lub wybierz pozycję **Wszystkie urządzenia zarządzane za pośrednictwem programu Exchange ActiveSync**..

    > [!TIP]
    > Można także przechodzić do urządzeń poszczególnych użytkowników. Kliknij pozycję **Wszyscy użytkownicy**. Na stronie właściwości użytkownika kliknij kartę **Urządzenia**, a następnie kliknij nazwę urządzenia przenośnego, które chcesz wyczyścić.

3.  Na liście wybierz urządzenia, które chcesz zablokować. Na pasku zadań wybierz pozycję **Zadania zdalne** i wybierz pozycję **Resetowanie kodu dostępu**..


### Zobacz także
[Wycofywanie urządzeń](retire-devices-from-microsoft-intune-management.md)
[Selektywne czyszczenie danych w systemie Windows w celu zarządzania danymi urządzenia](http://technet.microsoft.com/library/dn486874.aspx)


<!--HONumber=May16_HO1-->


