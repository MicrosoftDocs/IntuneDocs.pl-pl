---
title: "Konfigurowanie zarządzania urządzeniami z systemem Windows przy użyciu usługi Microsoft Intune | Microsoft Docs"
description: "Włączanie zarządzania urządzeniami przenośnymi (MDM) z systemem Windows w usłudze Microsoft Intune."
keywords: 
author: staciebarker
manager: stabar
ms.date: 02/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 45c32cf08e4d6fd570af287ed64411edc9d9b394
ms.openlocfilehash: e020ac2a4f600a94e7409e04c4c48f0c405c56cf


---

# <a name="set-up-windows-device-management"></a>Konfigurowanie zarządzania urządzeniami z systemem Windows

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Skorzystaj z jednej z następujących metod konfigurowania usługi rejestracji urządzeń z systemem Windows:

- **[Automatyczna rejestracja w systemie Windows 10 i Windows 10 Mobile przy użyciu usługi Azure Active Directory Premium](#set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium)** 
 -  Metoda ta ma zastosowanie tylko w przypadku urządzeń z systemem Windows 10 lub Windows 10 Mobile.
 -  Użycie tej metody wymaga usługi Azure Active Directory Premium. Jeśli nie masz tej usługi, skorzystaj z metody rejestracji dla systemów Windows 8.1 i Windows Phone 8.1.
 -  Jeśli nie wybrano włączenia automatycznego rejestrowania, należy użyć metody rejestracji dla systemów Windows 8.1 i Windows Phone 8.1.


- **[Rejestrowanie w systemie Windows 8.1 lub Windows Phone 8.1 poprzez konfigurowanie rekordu CNAME](#set-up-windows-8--1-and-windows-phone-8--1-enrollment-by-configuring-cname)** 
 - Ta metoda służy do rejestrowania urządzeń z systemem Windows 8.1 lub Windows Phone 8.1.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="set-up-windows-81-and-windows-phone-81-enrollment-by-configuring-cname"></a>Konfigurowanie rejestracji urządzeń z systemem Windows 8.1 lub Windows Phone 8.1 przez skonfigurowanie rekordu CNAME
Można pozwolić, aby użytkownicy instalowali i rejestrowali swoje urządzenia za pomocą aplikacji Portal firmy w usłudze Intune. Utworzenie rekordów zasobów CNAME systemu DNS umożliwia użytkownikom łączenie się i rejestrowanie w usłudze Intune bez podawania nazwy serwera.

1. **Skonfiguruj usługę**<br>
Jeśli usługa ta nie została jeszcze skonfigurowana, przygotuj się do zarządzania urządzeniami przenośnymi, [ustawiając urząd zarządzania urządzeniami przenośnymi](prerequisites-for-enrollment.md#step-2-set-mdm-authority) na usługę **Microsoft Intune** i konfigurując zarządzanie urządzeniami przenośnymi.

2. **Tworzenie rekordów CNAME** (opcjonalnie)<br>
Utworzyć rekordy zasobów **CNAME** systemu DNS dla domeny Twojej firmy. Jeśli na przykład witryna internetowa firmy to contoso.com, w systemie DNS należy utworzyć rekord CNAME, który przekierowuje domenę EnterpriseEnrollment.contoso.com do domeny enterpriseenrollment-s.manage.microsoft.com.

    Chociaż tworzenie wpisów DNS rekordów CNAME jest opcjonalne, rekordy CNAME ułatwiają użytkownikom rejestrację. Jeśli rekord CNAME nie zostanie znaleziony, użytkownicy są proszeni o ręczne wprowadzenie nazwy serwera MDM: enrollment.manage.microsoft.com.    

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

4.  **Poinformuj użytkowników, jak mogą zarejestrować swoje urządzenia i czego mogą oczekiwać po włączeniu ich do zarządzania.**

    Instrukcje dotyczące rejestrowania przez użytkownika końcowego można znaleźć w temacie [Rejestrowanie urządzenia z systemem Windows w usłudze Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-windows).

    Aby uzyskać więcej informacji o zadaniach użytkowników końcowych, zobacz [Zasoby dotyczące środowiska użytkownika końcowego w usłudze Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune).


### <a name="see-also"></a>Zobacz także
[Wymagania wstępne dotyczące rejestrowania urządzeń w usłudze Microsoft Intune](prerequisites-for-enrollment.md)



<!--HONumber=Feb17_HO2-->


