---
# required metadata

title: Konfigurowanie zarządzania systemem Windows 10 Mobile i Windows Phone przy użyciu usługi Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f5615051-2dd1-453b-9872-d3fdcefb2cb8

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Konfigurowanie zarządzania systemem Windows 10 Mobile i Windows Phone przy użyciu usługi Microsoft Intune
Aby można było zarządzać urządzeniami z systemem Windows 10 Mobile lub Windows Phone w usłudze Microsoft Intune, urządzenia muszą być w stanie nawiązać połączenia z usługą Intune. W celu uproszczenia tego procesu należy utworzyć rekord DNS, aby użytkownicy nie musieli wprowadzać adresu serwera. Poniżej opisano sposób uproszczenia rejestracji dla użytkowników.  

W przypadku większości scenariuszy użytkownicy mogą zainstalować aplikację Portal firmy ze Sklepu Windows. Jeśli zarządzasz urządzeniami z systemem Windows Phone 8.0 lub potrzebne jest wdrożenie aplikacji Portal firmy na urządzeniach z systemem Windows Phone, musisz pobrać i podpisać aplikację Portal firmy. Zobacz [Konfigurowanie zarządzania systemem Windows Phone 8.0](set-up-windows-phone-8.0-management-with-microsoft-intune.md).

1.  **Konfigurowanie usługi Intune**
    Jeśli usługa ta nie została jeszcze skonfigurowana, przygotuj się do zarządzania urządzeniami przenośnymi, [ustawiając urząd zarządzania urządzeniami przenośnymi](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority) na usługę **Microsoft Intune** i konfigurując zarządzanie urządzeniami przenośnymi.

2.  **Ustaw alias systemu DNS dla adresu serwera rejestracji** (opcjonalnie)

    Utworzenie aliasu systemu DNS (typ rekordu CNAME) ułatwia użytkownikom rejestrowanie swoich urządzeń. Jeśli nie utworzysz aliasu systemu DNS, użytkownicy będą musieli:

  1.  Utworzyć rekordy zasobów **CNAME** systemu DNS dla domeny Twojej firmy. Jeśli na przykład witryna internetowa firmy to contoso.com, w systemie DNS należy utworzyć rekord CNAME, który przekierowuje domenę EnterpriseEnrollment.contoso.com do domeny manage.microsoft.com. Jeśli zweryfikowano więcej niż jedną domenę, należy utworzyć rekord CNAME dla każdej z nich. Rekordy zasobów CNAME muszą zawierać następujące informacje:

      |TYPE|Nazwa hosta|Przekierowanie na|TTL|
      |--------|-------------|-------------|-------|
      |CNAME|EnterpriseEnrollment.domena_firmowa.com|EnterpriseEnrollment-s.manage.microsoft.com |1 godzina|
      |CNAME|EnterpriseRegistration.domena_firmowa.com|EnterpriseRegistration.windows.net|1 godzina|

      Propagowanie zmian rekordów DNS może potrwać do 72 godzin. Nie można zweryfikować zmiany w systemie DNS w usłudze Intune, dopóki trwa propagowanie rekordu DNS.

      **EnterpriseEnrollment-s.manage.microsoft.com** — obsługuje przekierowanie do usługi Intune z rozpoznawaniem domeny na podstawie nazwy domeny adresu e-mail.

      **EnterpriseRegistration.windows.net** — obsługuje urządzenia z systemem Windows 8.1 i Windows 10 Mobile, które będą rejestrować się za pośrednictwem usługi Azure Active Directory przy użyciu kont służbowych użytkowników.

    2.  W [konsoli administracyjnej usługi Intune](http://manage.microsoft.com) kliknij pozycję **Administracja** &gt; **Zarządzanie urządzeniami przenośnymi** &gt; **Windows Phone**..

      ![Okno dialogowe konfiguracji zarządzania urządzeniami przenośnymi w systemie Windows](../media/windows-device-enrollment.png)

    3.  W polu **Podaj nazwę zweryfikowanej domeny** wpisz adres URL zweryfikowanej domeny witryny internetowej firmy, a następnie kliknij przycisk **Przetestuj automatyczne wykrywanie**..



Nie są wymagane żadne dodatkowe czynności, chyba że nastąpi wdrożenie aplikacji Portal firmy na urządzeniach.  Kroki 2, 3 i 4 w konsoli administracyjnej można zignorować.


<!--HONumber=May16_HO1-->


