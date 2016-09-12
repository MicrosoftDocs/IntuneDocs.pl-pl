---
title: "Konfigurowanie zarządzania systemem Windows 10 Mobile i Windows Phone | Microsoft Intune"
description: "Włącz zarządzanie urządzeniami przenośnymi (MDM) dla urządzeń z systemem Windows 10 Mobile lub Windows Phone w usłudze Microsoft Intune."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5615051-2dd1-453b-9872-d3fdcefb2cb8
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 06d6c8ce97ba6a259055e94f0eba87f7c5a96531
ms.openlocfilehash: 344f1cf4367deb12288f9c361e043d345f9846bb


---


# Konfigurowanie zarządzania systemem Windows 10 Mobile i Windows Phone przy użyciu usługi Microsoft Intune
Pomoc dotyczącą konfigurowania urządzenia z systemem Windows możesz znaleźć [tutaj](../enduser/using-your-windows-device-with-intune.md).

Aby można było zarządzać urządzeniami z systemem Windows 10 Mobile lub Windows Phone w usłudze Microsoft Intune, urządzenia muszą być w stanie nawiązać połączenia z usługą Intune. W celu uproszczenia tego procesu należy utworzyć rekord DNS, aby użytkownicy nie musieli wprowadzać adresu serwera. Poniżej opisano sposób uproszczenia rejestracji dla użytkowników.  

W przypadku większości scenariuszy użytkownicy mogą zainstalować aplikację Portal firmy ze Sklepu Windows. Jeśli zarządzasz urządzeniami z systemem Windows Phone 8.0 lub potrzebne jest wdrożenie aplikacji Portal firmy na urządzeniach z systemem Windows Phone, musisz pobrać i podpisać aplikację Portal firmy. Zobacz [Konfigurowanie zarządzania systemem Windows Phone 8.0](set-up-windows-phone-8.0-management-with-microsoft-intune.md).

1.  **Skonfiguruj usługę** Jeśli usługa ta nie została jeszcze skonfigurowana, przygotuj się do zarządzania urządzeniami przenośnymi, [ustawiając urząd zarządzania urządzeniami przenośnymi](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority) na usługę **Microsoft Intune** i konfigurując zarządzanie urządzeniami przenośnymi.

2.  **Ustaw alias systemu DNS dla adresu serwera rejestracji** (opcjonalnie)

    Utworzenie aliasu systemu DNS (typ rekordu CNAME) ułatwia użytkownikom rejestrowanie swoich urządzeń. Mimo że wpis CNAME DNS jest opcjonalny do zarejestrowania urządzenia z systemem Windows, zalecane jest tworzenie zgodnie z potrzebami jednego lub wielu rekordów w celu ułatwienia procesu rejestracji urządzenia z systemem Windows. Jeśli nie zostanie znaleziony żaden rekord CNAME, użytkownik jest monitowany o ręczne wprowadzenie nazwy serwera MDM.

  1.  Utworzyć rekordy zasobów **CNAME** systemu DNS dla domeny Twojej firmy. Jeśli na przykład witryna internetowa firmy to contoso.com, w systemie DNS należy utworzyć rekord CNAME, który przekierowuje domenę EnterpriseEnrollment.contoso.com do domeny manage.microsoft.com. Jeśli zweryfikowano więcej niż jedną domenę, należy utworzyć rekord CNAME dla każdej z nich. Rekordy zasobów CNAME muszą zawierać następujące informacje:

      |TYPE|Nazwa hosta|Przekierowanie na|TTL|
      |--------|-------------|-------------|-------|
      |CNAME|EnterpriseEnrollment.domena_firmowa.com|EnterpriseEnrollment-s.manage.microsoft.com |1 godzina|
      |CNAME|EnterpriseRegistration.domena_firmowa.com|EnterpriseRegistration.windows.net|1 godzina|

      Propagowanie zmian rekordów DNS może potrwać do 72 godzin. Nie można zweryfikować zmiany w systemie DNS w usłudze Intune, dopóki trwa propagowanie rekordu DNS.

      **EnterpriseEnrollment-s.manage.microsoft.com** — obsługuje przekierowanie do usługi Intune z rozpoznawaniem domeny na podstawie nazwy domeny adresu e-mail.

      **EnterpriseRegistration.windows.net** — obsługuje urządzenia z systemem Windows 8.1 i Windows 10 Mobile, które będą rejestrować się za pośrednictwem usługi Azure Active Directory przy użyciu kont służbowych użytkowników.

    2.  W [konsoli administracyjnej usługi Intune](http://manage.microsoft.com) kliknij pozycję **Administracja** &gt; **Zarządzanie urządzeniami przenośnymi** &gt; **Windows Phone**.

      ![Okno dialogowe konfiguracji zarządzania urządzeniami przenośnymi w systemie Windows](../media/windows-device-enrollment.png)

    3.  W polu **Podaj nazwę zweryfikowanej domeny** wpisz adres URL zweryfikowanej domeny witryny sieci Web firmy, a następnie kliknij przycisk **Przetestuj automatyczne wykrywanie**.

    4.  Użytkownicy muszą dowiedzieć się, jak zarejestrować swoje urządzenia i czego oczekiwać po rozpoczęciu zarządzania nimi.
        - [Co mówić użytkownikom końcowym na temat korzystania z usługi Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
        - [Wskazówki dla użytkowników końcowych urządzeń z systemem Windows](../enduser/using-your-windows-device-with-intune.md)



Nie są wymagane żadne dodatkowe czynności, chyba że nastąpi wdrożenie aplikacji Portal firmy na urządzeniach.  Kroki 2 i 3 w konsoli administracyjnej można bezpiecznie zignorować.



<!--HONumber=Aug16_HO1-->


