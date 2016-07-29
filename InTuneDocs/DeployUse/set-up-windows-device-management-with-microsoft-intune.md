---
title: "Konfigurowanie zarządzania urządzeniami z systemem Windows przy użyciu usługi Microsoft Intune | Microsoft Intune"
description: "Włącz zarządzanie urządzeniami przenośnymi (MDM) dla komputerów z systemem Windows, w tym urządzeń z systemem Windows 10, w usłudze Microsoft Intune."
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5f336cf52cbecd93cb7b2850560327e6024302e0
ms.openlocfilehash: 710e34f8f97377bf57a398f74773788df3794654


---

# Konfigurowanie zarządzania urządzeniami z systemem Windows
Usługa Intune umożliwia rejestrację komputerów z systemem Windows zgodnie z modelem BYOD („bring your own device”) w celu udzielenia dostępu użytkownikom tych komputerów do firmowych aplikacji i poczty e-mail. Takie rozwiązanie razem z usługą Azure Active Directory umożliwia również szybkie, bezdotykowe przenoszenie nowych urządzeń z systemem Windows 10 do zarządzania i uzyskania dostępu do zasobów firmowych bez konieczności odtwarzania komputera z obrazu. Zarejestrowani użytkownicy mogą się logować, a ustawianie zasad, aplikacji i ustawień dla ich urządzeń będzie możliwe przy użyciu konsoli administracyjnej usługi Intune. Być może zechcesz również [skonfigurować zarządzanie systemem Windows Phone przy użyciu usługi Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md) lub [zarządzać komputerami za pomocą oprogramowania klienckiego usługi Intune](manage-windows-pcs-with-microsoft-intune.md).

Utworzenie rekordu CNAME systemu DNS ułatwia użytkownikom łączenie się i rejestrowanie w usłudze Intune bez podawania nazwy serwera.

### Konfigurowanie zarządzania urządzeniami z systemem Windows

  1.  Utwórz rekord zasobów **CNAME** systemu DNS dla domeny firmy. Jeśli na przykład witryna internetowa firmy to contoso.com, w systemie DNS należy utworzyć rekord CNAME, który przekierowuje domenę EnterpriseEnrollment.contoso.com do domeny EnterpriseEnrollment-s.manage.microsoft.com. Mimo że wpis CNAME DNS jest opcjonalny do zarejestrowania urządzenia z systemem Windows, zalecane jest tworzenie zgodnie z potrzebami jednego lub wielu rekordów w celu ułatwienia procesu rejestracji urządzenia z systemem Windows. Jeśli nie zostanie znaleziony żaden rekord CNAME, użytkownik jest monitowany o ręczne wprowadzenie nazwy serwera MDM.

  Jeśli zweryfikowano więcej niż jedną domenę, należy utworzyć rekord CNAME dla każdej z nich. Rekordy zasobów CNAME muszą zawierać następujące informacje:

  |TYPE|Nazwa hosta|Przekierowanie na|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.domena_firmowa.com|EnterpriseEnrollment-s.manage.microsoft.com |1 godzina|
  |CNAME|EnterpriseRegistration.domena_firmowa.com|EnterpriseRegistration.windows.net|1 godzina|

  Propagowanie zmian rekordów DNS może potrwać do 72 godzin. Nie można zweryfikować zmiany w systemie DNS w usłudze Intune, dopóki trwa propagowanie rekordu DNS.

  **EnterpriseEnrollment-s.manage.microsoft.com** — obsługuje przekierowanie do usługi Intune z rozpoznawaniem domeny na podstawie nazwy domeny adresu e-mail.

  **EnterpriseRegistration.windows.net** — obsługuje urządzenia z systemem Windows 8.1 i Windows 10 Mobile, które będą rejestrować się za pośrednictwem usługi Azure Active Directory przy użyciu kont służbowych użytkowników.

  2.  W [konsoli administracyjnej usługi Intune](http://manage.microsoft.com) kliknij pozycje **Administracja** &gt; **Zarządzanie urządzeniami przenośnymi** &gt; **Windows**.
  ![Okno dialogowe Zarządzanie urządzeniami z systemem Windows](../media/enroll-intune-winenr.png)
  3.  W polu **Podaj nazwę zweryfikowanej domeny** wpisz adres URL zweryfikowanej domeny witryny sieci Web firmy, a następnie kliknij przycisk **Przetestuj automatyczne wykrywanie**.

### Zobacz także
[Przygotowanie do rejestracji urządzeń w usłudze Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Jul16_HO3-->


