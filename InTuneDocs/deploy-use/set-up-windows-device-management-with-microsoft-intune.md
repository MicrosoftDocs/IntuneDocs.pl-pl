---
title: "Konfigurowanie zarządzania urządzeniami z systemem Windows przy użyciu usługi Microsoft Intune | Microsoft Intune"
description: "Włącz zarządzanie urządzeniami przenośnymi (MDM) dla komputerów z systemem Windows, w tym urządzeń z systemem Windows 10, w usłudze Microsoft Intune."
keywords: 
author: staciebarker
manager: stabar
ms.date: 11/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6adfb7375f9747f64e7037164f48918789bd7ee0
ms.openlocfilehash: 7c518c176e315cbf005b2fceb8d74de09bdcfa98


---

# <a name="set-up-windows-device-management"></a>Konfigurowanie zarządzania urządzeniami z systemem Windows

Administrator usługi Intune może włączyć rejestrację i zarządzanie dla komputerów z systemem Windows na dwa sposoby:

- **[Automatyczna rejestracja w usłudze Azure Active Directory](#azure-active-directory-enrollment)** — użytkownicy systemów Windows 10 i Windows 10 Mobile rejestrują swoje urządzenia przez dodanie konta służbowego do urządzenia
- **[Rejestracja za pomocą Portalu firmy](#company-portal-app-enrollment)** — użytkownicy rejestrują urządzenia z systemem Windows Phone 8.1 i nowszym przez pobranie i zainstalowanie aplikacji Portal firmy, a następnie wprowadzają w aplikacji poświadczenia konta służbowego.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="set-up-company-portal-app-enrollment"></a>Konfigurowanie rejestracji przy użyciu aplikacji Portal firmy
Można pozwolić, aby użytkownicy instalowali i rejestrowali swoje urządzenia za pomocą aplikacji Portal firmy usługi Intune. Utworzenie rekordów zasobów CNAME systemu DNS umożliwia użytkownikom łączenie się i rejestrowanie w usłudze Intune bez podawania nazwy serwera.

1. **Skonfiguruj usługę**<br>
Jeśli usługa ta nie została jeszcze skonfigurowana, przygotuj się do zarządzania urządzeniami przenośnymi, [ustawiając urząd zarządzania urządzeniami przenośnymi](prerequisites-for-enrollment.md#step-2-set-mdm-authority) na usługę **Microsoft Intune** i konfigurując zarządzanie urządzeniami przenośnymi.

2. **Tworzenie rekordów CNAME** (opcjonalnie)<br>Utworzyć rekordy zasobów **CNAME** systemu DNS dla domeny Twojej firmy. Jeśli na przykład witryna internetowa firmy to contoso.com, w systemie DNS należy utworzyć rekord CNAME, który przekierowuje domenę EnterpriseEnrollment.contoso.com do domeny enterpriseenrollment.manage.microsoft.com.

    Jeśli w systemie DNS znajduje się rekord CNAME, który przekierowuje domenę EnterpriseEnrollment.contoso.com do domeny manage.microsoft.com, zaleca się jego zastąpienie w systemie DNS rekordem CNAME, który przekierowuje domenę EnterpriseEnrollment.contoso.com do domeny enterpriseenrollment-s.manage.microsoft.com. Ta zmiana jest zalecana, ponieważ rejestracje za pośrednictwem punktu końcowego domeny manage.microsoft.com zostaną wycofane w przyszłej wersji.

    Rekordy zasobów CNAME muszą zawierać następujące informacje:

  |TYPE|Nazwa hosta|Przekierowanie na|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.domena_firmowa.com|EnterpriseEnrollment-s.manage.microsoft.com |1 godzina|
  |CNAME|EnterpriseRegistration.domena_firmowa.com|EnterpriseRegistration.windows.net|1 godzina|

  `EnterpriseEnrollment-s.manage.microsoft.com` — obsługuje przekierowanie do usługi Intune z rozpoznawaniem domeny na podstawie nazwy domeny adresu e-mail

  `EnterpriseRegistration.windows.net` — obsługuje urządzenia z systemem Windows 8.1 i Windows 10 Mobile, które będą rejestrowane za pośrednictwem usługi Azure Active Directory przy użyciu kont służbowych użytkowników

  Jeśli firma używa wielu domen dla poświadczeń użytkowników, należy utworzyć rekordy CNAME dla każdej domeny.

  Jeśli na przykład witryna internetowa firmy to contoso.com, w systemie DNS należy utworzyć rekord CNAME, który przekierowuje domenę EnterpriseEnrollment.contoso.com do domeny EnterpriseEnrollment-s.manage.microsoft.com. Propagowanie zmian rekordów DNS może potrwać do 72 godzin. Nie można zweryfikować zmiany w systemie DNS w usłudze Intune, dopóki trwa propagowanie rekordu DNS.

3.  **Weryfikowanie rekordu CNAME**<br>W [konsoli administracyjnej usługi Intune](http://manage.microsoft.com) wybierz kolejno pozycje **Administrator** &gt; **Zarządzanie urządzeniami przenośnymi** &gt; **Windows**. W polu **Podaj nazwę zweryfikowanej domeny** wpisz adres URL zweryfikowanej domeny witryny sieci Web firmy, a następnie wybierz pozycję **Przetestuj automatyczne wykrywanie**.

  ![Okno dialogowe Zarządzanie urządzeniami z systemem Windows](../media/enroll-intune-winenr.png)

4.  **Kroki opcjonalne**<br>Krok **Dodaj klucze pobierania lokalnego** jest zbędny w przypadku systemu Windows 10. Krok **Prześlij certyfikat podpisywania kodu** jest niezbędny tylko w przypadku, jeśli będziesz dystrybuować do urządzeń aplikacje biznesowe, które nie są dostępne w Sklepie Windows.

6.  **Poinformuj użytkowników, jak mogą zarejestrować swoje urządzenia i czego mogą oczekiwać po włączeniu ich do zarządzania.**

    Instrukcje dotyczące rejestrowania przez użytkownika końcowego można znaleźć w temacie [Rejestrowanie urządzenia z systemem Windows w usłudze Intune](../enduser/enroll-your-device-in-intune-windows.md).

    Aby uzyskać więcej informacji o innych zadaniach użytkownika końcowego, zobacz następujące artykuły:
      - [Zasoby dotyczące środowiska użytkownika końcowego w usłudze Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
      - [Wskazówki dla użytkowników końcowych korzystających z urządzeń z systemem Windows](../enduser/using-your-windows-device-with-intune.md)

### <a name="see-also"></a>Zobacz też
[Wymagania wstępne dotyczące rejestrowania urządzeń w usłudze Microsoft Intune](prerequisites-for-enrollment.md)



<!--HONumber=Dec16_HO2-->


