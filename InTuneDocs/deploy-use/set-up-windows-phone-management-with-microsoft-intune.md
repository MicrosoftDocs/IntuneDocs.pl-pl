---
title: "Konfigurowanie zarządzania systemem Windows 10 Mobile i Windows Phone | Microsoft Docs"
description: "Włącz zarządzanie urządzeniami przenośnymi (MDM) dla urządzeń z systemem Windows 10 Mobile lub Windows Phone w usłudze Microsoft Intune."
keywords: 
author: staciebarker
manager: angrobe
ms.date: 11/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5615051-2dd1-453b-9872-d3fdcefb2cb8
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: d58b2d57ec99add7bbc372584f0ecc430830530a


---


# <a name="set-up-windows-phone-and-windows-10-mobile-management-with-microsoft-intune"></a>Konfigurowanie zarządzania systemem Windows 10 Mobile i Windows Phone przy użyciu usługi Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Administrator usługi Intune może włączyć rejestrację i zarządzanie dla urządzeń z systemem Windows 10 Mobile i Windows Phone na dwa sposoby:

- **[Automatyczna rejestracja w usłudze Azure Active Directory](#azure-active-directory-enrollment)** — użytkownicy systemów Windows 10 i Windows 10 Mobile rejestrują swoje urządzenia przez dodanie konta służbowego do urządzenia
- **[Rejestracja za pomocą Portalu firmy](#company-portal-app-enrollment)** — użytkownicy rejestrują urządzenia z systemem Windows Phone 8.1 i nowszym przez pobranie i zainstalowanie aplikacji Portal firmy, a następnie wprowadzenie poświadczeń konta służbowego użytkownika w tej aplikacji.


[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="company-portal-app-enrollment"></a>Rejestracja przy użyciu aplikacji Portal firmy
Można pozwolić, aby użytkownicy instalowali i rejestrowali swoje urządzenia za pomocą aplikacji Portal firmy usługi Intune. Utworzenie rekordów zasobów CNAME systemu DNS umożliwia użytkownikom łączenie się i rejestrowanie w usłudze Intune bez podawania nazwy serwera.

1.  **Skonfiguruj usługę**<br>Jeśli usługa ta nie została jeszcze skonfigurowana, przygotuj się do zarządzania urządzeniami przenośnymi, [ustawiając urząd zarządzania urządzeniami przenośnymi](prerequisites-for-enrollment.md#step-2-set-mdm-authority) na usługę **Microsoft Intune** i konfigurując zarządzanie urządzeniami przenośnymi.

2.  **Tworzenie rekordów CNAME** (opcjonalnie)<br>Utworzyć rekordy zasobów **CNAME** systemu DNS dla domeny Twojej firmy. Jeśli na przykład witryna internetowa firmy to contoso.com, w systemie DNS należy utworzyć rekord CNAME, który przekierowuje domenę EnterpriseEnrollment.contoso.com do domeny enterpriseenrollment-s.manage.microsoft.com.

    Chociaż tworzenie wpisów DNS rekordów CNAME jest opcjonalne, rekordy CNAME ułatwiają użytkownikom rejestrację. Jeśli rekord CNAME nie zostanie znaleziony, użytkownicy są proszeni o ręczne wprowadzenie nazwy serwera MDM, https://manage.microsoft.com.

    Jeśli w systemie DNS znajduje się rekord CNAME, który przekierowuje domenę EnterpriseEnrollment.contoso.com do domeny manage.microsoft.com, zaleca się jego zastąpienie w systemie DNS rekordem CNAME, który przekierowuje domenę EnterpriseEnrollment.contoso.com do domeny enterpriseenrollment-s.manage.microsoft.com. Ta zmiana jest zalecana, ponieważ rejestracje za pośrednictwem punktu końcowego domeny manage.microsoft.com zostaną wycofane w przyszłej wersji.

    Jeśli zweryfikowano więcej niż jedną domenę, należy utworzyć rekord CNAME dla każdej z nich. Rekordy zasobów CNAME muszą zawierać następujące informacje:

  |TYPE|Nazwa hosta|Przekierowanie na|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.domena_firmowa.com|EnterpriseEnrollment-s.manage.microsoft.com |1 godzina|
  |CNAME|EnterpriseRegistration.domena_firmowa.com|EnterpriseRegistration.windows.net|1 godzina|

  `EnterpriseEnrollment-s.manage.microsoft.com` — obsługuje przekierowanie do usługi Intune z rozpoznawaniem domeny na podstawie nazwy domeny adresu e-mail

  `EnterpriseRegistration.windows.net` — obsługuje urządzenia z systemem Windows 8.1 i Windows 10 Mobile, które będą rejestrowane za pośrednictwem usługi Azure Active Directory przy użyciu kont służbowych użytkowników

  Jeśli firma używa wielu domen dla poświadczeń użytkowników, należy utworzyć rekordy CNAME dla każdej domeny.

  Jeśli na przykład witryna internetowa firmy to contoso.com, w systemie DNS należy utworzyć rekord CNAME, który przekierowuje domenę EnterpriseEnrollment.contoso.com do domeny EnterpriseEnrollment-s.manage.microsoft.com. Propagowanie zmian rekordów DNS może potrwać do 72 godzin. Nie można zweryfikować zmiany w systemie DNS w usłudze Intune, dopóki trwa propagowanie rekordu DNS.

3.  **Weryfikowanie rekordu CNAME**<br>W [konsoli administracyjnej usługi Intune](http://manage.microsoft.com) wybierz kolejno pozycje **Administracja** &gt; **Zarządzanie urządzeniami przenośnymi** &gt; **Windows Phone**. W polu **Podaj nazwę zweryfikowanej domeny** wpisz adres URL zweryfikowanej domeny witryny sieci Web firmy, a następnie wybierz pozycję **Przetestuj automatyczne wykrywanie**.

    ![Okno dialogowe konfiguracji zarządzania urządzeniami przenośnymi w systemie Windows](../media/windows-phone-enrollment.png)

4.  **Kroki opcjonalne**<br>Krok **Dodaj klucze pobierania lokalnego** jest zbędny w przypadku systemu Windows 10. Krok **Prześlij certyfikat podpisywania kodu** jest niezbędny tylko w przypadku, gdy dystrybuujesz do urządzeń aplikacje biznesowe (LOB, line-of-business) niedostępne w Sklepie Windows.

5.  **Poinformuj użytkowników, jak mogą zarejestrować swoje urządzenia w celu uzyskania dostępu do zasobów firmy.**

    Instrukcje dotyczące rejestrowania przez użytkownika końcowego można znaleźć w temacie [Rejestrowanie urządzenia z systemem Windows w usłudze Intune](../enduser/enroll-your-device-in-intune-windows.md). Można również wskazać użytkownikom temat [Co administrator IT może zobaczyć po zarejestrowaniu urządzenia w usłudze Intune?](../enduser/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows.md).

    Aby uzyskać informacje o innych zadaniach użytkownika końcowego, zobacz następujące artykuły:
    - [Co powinni wiedzieć użytkownicy końcowi na temat korzystania z usługi Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
    - [Wskazówki dla użytkowników końcowych korzystających z urządzeń z systemem Windows](../enduser/using-your-windows-device-with-intune.md)

Nie są wymagane żadne dodatkowe czynności, chyba że nastąpi wdrożenie aplikacji Portal firmy na urządzeniach.  Kroki 2 i 3 w konsoli administracyjnej można bezpiecznie zignorować.



<!--HONumber=Dec16_HO2-->


