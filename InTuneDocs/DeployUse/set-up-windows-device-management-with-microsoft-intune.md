---
title: "Konfigurowanie zarządzania urządzeniami z systemem Windows przy użyciu usługi Microsoft Intune | Microsoft Intune"
description: "Włącz zarządzanie urządzeniami przenośnymi (MDM) dla komputerów z systemem Windows, w tym urządzeń z systemem Windows 10, w usłudze Microsoft Intune."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ebb1648ab13d31a2ba1ab17615814be8dda8a08c
ms.openlocfilehash: 9b063c1e6b1ff5dcab16fce958ede49303284b18


---

# Konfigurowanie zarządzania urządzeniami z systemem Windows

Administrator usługi Intune może włączyć rejestrację i zarządzanie dla komputerów z systemem Windows na dwa sposoby:

- **[Automatyczna rejestracja w usłudze Azure AD](#azure-active-directory-enrollment)** — użytkownicy systemów Windows 10 i Windows 10 Mobile rejestrują swoje urządzenia przez dodanie konta służbowego do urządzenia
- **[Rejestracja za pomocą Portalu firmy](#company-portal-app-enrollment)** — urządzenia z systemem Windows 8.1 i nowszymi są rejestrowane przez pobranie i zainstalowanie aplikacji Portal firmy, a następnie wprowadzenie poświadczeń konta służbowego użytkownika w tej aplikacji.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## Konfigurowanie rejestracji przy użyciu aplikacji Portal firmy
Można pozwolić, aby użytkownicy rejestrowali swoje urządzenia przez zainstalowanie aplikacji Portal firmy usługi Intune i zarejestrowanie urządzeń przy użyciu tej aplikacji. Utworzenie rekordu CNAME systemu DNS ułatwia użytkownikom łączenie się i rejestrowanie w usłudze Intune bez podawania nazwy serwera.

1. **Konfigurowanie usługi Intune**<br>
Jeśli usługa ta nie została jeszcze skonfigurowana, przygotuj się do zarządzania urządzeniami przenośnymi, [ustawiając urząd zarządzania urządzeniami przenośnymi](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority) na usługę **Microsoft Intune** i konfigurując zarządzanie urządzeniami przenośnymi.

2. **Tworzenie rekordów CNAME** (opcjonalnie)<br>Utwórz rekordy zasobów **CNAME** systemu DNS dla domeny swojej firmy w celu uproszczenia rejestracji. Chociaż tworzenie wpisów DNS rekordów CNAME jest opcjonalne, utworzenie rekordów CNAME ułatwia użytkownikom rejestrację. Jeśli rekord CNAME nie zostanie znaleziony, użytkownicy są proszeni o ręczne wprowadzenie nazwy serwera MDM, `https://manage.microsoft.com`.  Rekordy zasobów CNAME muszą zawierać następujące informacje:

  |TYPE|Nazwa hosta|Przekierowanie na|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.domena_firmowa.com|EnterpriseEnrollment-s.manage.microsoft.com |1 godzina|
  |CNAME|EnterpriseRegistration.domena_firmowa.com|EnterpriseRegistration.windows.net|1 godzina|

  `EnterpriseEnrollment-s.manage.microsoft.com` — obsługuje przekierowanie do usługi Intune z rozpoznawaniem domeny na podstawie nazwy domeny adresu e-mail.

  `EnterpriseRegistration.windows.net` — obsługuje urządzenia z systemem Windows 8.1 i Windows 10 Mobile, które będą rejestrować się za pośrednictwem usługi Azure Active Directory przy użyciu kont służbowych użytkowników.

  Jeśli firma używa wielu domen dla poświadczeń użytkowników, należy utworzyć rekordy CNAME dla każdej domeny.

  Jeśli na przykład witryna internetowa firmy to contoso.com, w systemie DNS należy utworzyć rekord CNAME, który przekierowuje domenę EnterpriseEnrollment.contoso.com do domeny EnterpriseEnrollment-s.manage.microsoft.com. Propagowanie zmian rekordów DNS może potrwać do 72 godzin. Nie można zweryfikować zmiany w systemie DNS w usłudze Intune, dopóki trwa propagowanie rekordu DNS.

3.  **Weryfikowanie rekordu CNAME**<br>W [konsoli administracyjnej usługi Intune](http://manage.microsoft.com) kliknij pozycje **Administracja** &gt; **Zarządzanie urządzeniami przenośnymi** &gt; **Windows**. W polu **Podaj nazwę zweryfikowanej domeny** wpisz adres URL zweryfikowanej domeny witryny sieci Web firmy, a następnie kliknij przycisk **Przetestuj automatyczne wykrywanie**.

  ![Okno dialogowe Zarządzanie urządzeniami z systemem Windows](../media/enroll-intune-winenr.png)

4.  **Kroki opcjonalne**<br>Krok **Dodaj klucze pobierania lokalnego** jest zbędny w przypadku systemu Windows 10. Krok **Prześlij certyfikat podpisywania kodu** jest niezbędny tylko w przypadku, jeśli będziesz dystrybuować aplikacje biznesowe do urządzeń, które nie są dostępne w Sklepie Windows. [Dowiedz się więcej](set-up-windows-phone-8.0-management-with-microsoft-intune.md)

6.  **Informowanie użytkowników**<br>Musisz powiedzieć użytkownikom, jak mają zarejestrować swoje urządzenia i czego oczekiwać po rozpoczęciu zarządzania nimi:
      - [Co mówić użytkownikom końcowym na temat korzystania z usługi Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
      - [Wskazówki dla użytkowników końcowych urządzeń z systemem Windows](../enduser/using-your-windows-device-with-intune.md)

### Zobacz także
[Przygotowanie do rejestracji urządzeń w usłudze Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Aug16_HO5-->


