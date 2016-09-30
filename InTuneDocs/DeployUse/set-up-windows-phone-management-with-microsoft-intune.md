---
title: "Konfigurowanie zarządzania systemem Windows 10 Mobile i Windows Phone | Microsoft Intune"
description: "Włącz zarządzanie urządzeniami przenośnymi (MDM) dla urządzeń z systemem Windows 10 Mobile lub Windows Phone w usłudze Microsoft Intune."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5615051-2dd1-453b-9872-d3fdcefb2cb8
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c880bd9dfb998355a18e78af898a96d4cee393f7
ms.openlocfilehash: d88405e913fe61cef2c297f9d50408e10674cf3f


---


# Konfigurowanie zarządzania systemem Windows 10 Mobile i Windows Phone przy użyciu usługi Microsoft Intune

Administrator usługi Intune może włączyć rejestrację i zarządzanie dla urządzeń z systemem Windows 10 Mobile i Windows Phone na dwa sposoby:

- **[Automatyczna rejestracja w usłudze Azure AD](#azure-active-directory-enrollment)** — użytkownicy systemów Windows 10 i Windows 10 Mobile rejestrują swoje urządzenia przez dodanie konta służbowego do urządzenia
- **[Rejestracja za pomocą Portalu firmy](#company-portal-app-enrollment)** — urządzenia z systemem Windows Phone 8.1 i nowszymi są rejestrowane przez pobranie i zainstalowanie aplikacji Portal firmy, a następnie wprowadzenie poświadczeń konta służbowego użytkownika w tej aplikacji.


[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## Rejestracja przy użyciu aplikacji Portal firmy
Można pozwolić, aby użytkownicy rejestrowali swoje urządzenia przez zainstalowanie aplikacji Portal firmy usługi Intune i zarejestrowanie urządzeń przy użyciu tej aplikacji. Utworzenie rekordu CNAME systemu DNS ułatwia użytkownikom łączenie się i rejestrowanie w usłudze Intune bez podawania nazwy serwera. Jeśli zarządzasz urządzeniami z systemem Windows Phone 8.0 lub potrzebne jest wdrożenie aplikacji Portal firmy na urządzeniach z systemem Windows Phone, musisz pobrać i podpisać aplikację Portal firmy. Zobacz [Konfigurowanie zarządzania systemem Windows Phone 8.0](set-up-windows-phone-8.0-management-with-microsoft-intune.md).

1.  **Konfigurowanie usługi Intune**<br>Jeśli usługa ta nie została jeszcze skonfigurowana, przygotuj się do zarządzania urządzeniami przenośnymi, [ustawiając urząd zarządzania urządzeniami przenośnymi](prerequisites-for-enrollment.md#set-mobile-device-management-authority) na usługę **Microsoft Intune** i konfigurując zarządzanie urządzeniami przenośnymi.

2.  **Tworzenie rekordów CNAME** (opcjonalnie)<br>Utworzyć rekordy zasobów **CNAME** systemu DNS dla domeny Twojej firmy. Jeśli na przykład witryna internetowa firmy to contoso.com, w systemie DNS należy utworzyć rekord CNAME, który przekierowuje domenę EnterpriseEnrollment.contoso.com do domeny manage.microsoft.com. Jeśli zweryfikowano więcej niż jedną domenę, należy utworzyć rekord CNAME dla każdej z nich. Rekordy zasobów CNAME muszą zawierać następujące informacje:

  |TYPE|Nazwa hosta|Przekierowanie na|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.domena_firmowa.com|EnterpriseEnrollment-s.manage.microsoft.com |1 godzina|
  |CNAME|EnterpriseRegistration.domena_firmowa.com|EnterpriseRegistration.windows.net|1 godzina|
  Propagowanie zmian rekordów DNS może potrwać do 72 godzin. Nie można zweryfikować zmiany w systemie DNS w usłudze Intune, dopóki trwa propagowanie rekordu DNS.

  `EnterpriseEnrollment-s.manage.microsoft.com` — obsługuje przekierowanie do usługi Intune z rozpoznawaniem domeny na podstawie nazwy domeny adresu e-mail.

  `EnterpriseRegistration.windows.net` — obsługuje urządzenia z systemem Windows 8.1 i Windows 10 Mobile, które będą rejestrować się za pośrednictwem usługi Azure Active Directory przy użyciu kont służbowych użytkowników.

  Jeśli firma używa wielu domen dla poświadczeń użytkowników, należy utworzyć rekordy CNAME dla każdej domeny.

  Jeśli na przykład witryna internetowa firmy to contoso.com, w systemie DNS należy utworzyć rekord CNAME, który przekierowuje domenę EnterpriseEnrollment.contoso.com do domeny EnterpriseEnrollment-s.manage.microsoft.com. Propagowanie zmian rekordów DNS może potrwać do 72 godzin. Nie można zweryfikować zmiany w systemie DNS w usłudze Intune, dopóki trwa propagowanie rekordu DNS.

3.  **Weryfikowanie rekordu CNAME**<br>W [konsoli administracyjnej usługi Intune](http://manage.microsoft.com) kliknij pozycję **Administracja** &gt; **Zarządzanie urządzeniami przenośnymi** &gt; **Windows Phone**. W polu **Podaj nazwę zweryfikowanej domeny** wpisz adres URL zweryfikowanej domeny witryny sieci Web firmy, a następnie kliknij przycisk **Przetestuj automatyczne wykrywanie**.

    ![Okno dialogowe konfiguracji zarządzania urządzeniami przenośnymi w systemie Windows](../media/windows-phone-enrollment.png)

4.  **Kroki opcjonalne**<br>Krok **Dodaj klucze pobierania lokalnego** jest zbędny w przypadku systemu Windows 10. Krok **Prześlij certyfikat podpisywania kodu** jest niezbędny tylko w przypadku, jeśli będziesz dystrybuować aplikacje biznesowe do urządzeń, które nie są dostępne w Sklepie Windows. [Dowiedz się więcej](set-up-windows-phone-8.0-management-with-microsoft-intune.md)

5.  **Informowanie użytkowników**<br>Użytkownicy muszą dowiedzieć się, jak zarejestrować swoje urządzenia i czego oczekiwać po rozpoczęciu zarządzania nimi.
    - [Co mówić użytkownikom końcowym na temat korzystania z usługi Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
    - [Wskazówki dla użytkowników końcowych urządzeń z systemem Windows](../enduser/using-your-windows-device-with-intune.md)

Nie są wymagane żadne dodatkowe czynności, chyba że nastąpi wdrożenie aplikacji Portal firmy na urządzeniach.  Kroki 2 i 3 w konsoli administracyjnej można bezpiecznie zignorować.



<!--HONumber=Sep16_HO4-->


