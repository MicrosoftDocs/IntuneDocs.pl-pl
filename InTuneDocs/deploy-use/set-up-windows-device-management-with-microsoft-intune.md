---
title: "Konfigurowanie zarządzania urządzeniami z systemem Windows przy użyciu usługi Microsoft Intune | Microsoft Docs"
description: "Włączanie zarządzania urządzeniami przenośnymi (MDM) z systemem Windows w usłudze Microsoft Intune."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 03/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 771aed4e1c57171183b9a9ea7d9e0f702dc1859c
ms.openlocfilehash: f6014c5500b05762d123b2285ef859d67382e402
ms.lasthandoff: 04/06/2017


---

# <a name="set-up-windows-device-management"></a>Konfigurowanie zarządzania urządzeniami z systemem Windows

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Skorzystaj z jednej z następujących metod konfigurowania usługi rejestracji urządzeń z systemem Windows:

- [**Automatyczna rejestracja w systemie Windows 10 przy użyciu usługi Azure Active Directory Premium**](#set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium)
 -  Ta metoda jest dostępna tylko dla urządzeń z systemem Windows 10.
 -  Użycie tej metody wymaga usługi Azure Active Directory Premium.
 -  Jeśli nie wybrano włączenia automatycznego rejestrowania, należy użyć metody rejestracji dla systemów Windows 8.1 i Windows Phone 8.1.

- [**Rejestracja bez automatycznego rejestrowania w usłudze Azure AD Premium**](#enable-windows-enrollment-without-azure-ad-premium)
 - Ta metoda służy do rejestrowania urządzeń z systemem Windows 8.1 lub Windows Phone 8.1.
 - Jeśli nie chcesz używać usługi Azure Active Directory (AD) Premium, możesz użyć tej metody dla urządzeń z systemem Windows 8.1 i nowszym.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="enable-windows-enrollment-without-automatic-enrollment"></a>Włączanie rejestrowania urządzeń z systemem Windows bez rejestrowania automatycznego
Można umożliwić użytkownikom instalowanie i rejestrowanie urządzeń bez automatycznego rejestrowania w usłudze Azure AD Premium. Gdy przypiszesz licencję do konta użytkownika, użytkownik może dodać takie konto do urządzenia z systemem Windows i wyrazić zgodę na zarejestrowanie urządzenia w środowisku zarządzania. Utworzenie rekordów zasobów CNAME systemu DNS umożliwia użytkownikom łączenie się i rejestrowanie w usłudze Intune bez podawania nazwy serwera.

**Krok 1. Tworzenie rekordów CNAME** (opcjonalnie)<br>
Utwórz rekordy zasobów CNAME systemu DNS dla domeny Twojej firmy. Jeśli na przykład witryna internetowa firmy to contoso.com, w systemie DNS należy utworzyć rekord CNAME, który przekierowuje domenę EnterpriseEnrollment.contoso.com do domeny enterpriseenrollment-s.manage.microsoft.com.

Chociaż tworzenie wpisów DNS rekordów CNAME jest opcjonalne, rekordy CNAME ułatwiają użytkownikom rejestrację. Jeśli rekord CNAME nie zostanie znaleziony, użytkownicy są proszeni o ręczne wprowadzenie nazwy serwera MDM: enrollment.manage.microsoft.com.

Jeśli zweryfikowano więcej niż jedną domenę, należy utworzyć rekord CNAME dla każdej z nich. Rekordy zasobów CNAME muszą zawierać następujące informacje:

Rekordy zasobów CNAME muszą zawierać następujące informacje:

|TYPE|Nazwa hosta|Przekierowanie na|TTL|
|--------|-------------|-------------|-------|
|CNAME|EnterpriseEnrollment.domena_firmowa.com|EnterpriseEnrollment-s.manage.microsoft.com |1 godzina|
|CNAME|EnterpriseRegistration.domena_firmowa.com|EnterpriseRegistration.windows.net|1 godzina|

`EnterpriseEnrollment-s.manage.microsoft.com` — obsługuje przekierowanie do usługi Intune z rozpoznawaniem domeny na podstawie nazwy domeny adresu e-mail

Jeśli firma używa wielu domen dla poświadczeń użytkowników, należy utworzyć rekordy CNAME dla każdej domeny.

Jeśli na przykład witryna internetowa firmy to contoso.com, w systemie DNS należy utworzyć rekord CNAME, który przekierowuje domenę EnterpriseEnrollment.contoso.com do domeny EnterpriseEnrollment-s.manage.microsoft.com. Propagowanie zmian rekordów DNS może potrwać do 72 godzin. Nie można zweryfikować zmiany w systemie DNS w usłudze Intune, dopóki trwa propagowanie rekordu DNS.

**Krok 2. Weryfikacja rekordu CNAME** (opcjonalnie)<br>
W [konsoli administracyjnej usługi Intune](http://manage.microsoft.com) wybierz kolejno pozycje **Administrator** &gt; **Zarządzanie urządzeniami przenośnymi** &gt; **Windows**. W polu **Podaj nazwę zweryfikowanej domeny** wpisz adres URL zweryfikowanej domeny witryny sieci Web firmy, a następnie wybierz pozycję **Przetestuj automatyczne wykrywanie**.

## <a name="tell-users-how-to-enroll-windows-devices"></a>Informowanie użytkowników o sposobie rejestrowania urządzeń z systemem Windows
Poinformuj użytkowników, jak mogą zarejestrować swoje urządzenia z systemem Windows i czego mogą oczekiwać po włączeniu ich do zarządzania.
Instrukcje dotyczące rejestrowania przez użytkownika końcowego można znaleźć w temacie [Rejestrowanie urządzenia z systemem Windows w usłudze Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-windows). Możesz również odesłać użytkowników do artykułu [Jakie informacje może wyświetlać moja firma, gdy zarejestruję swoje urządzenie w usłudze Intune?](https://docs.microsoft.com/intune/enduser/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows).

Aby uzyskać więcej informacji o zadaniach użytkowników końcowych, zobacz [Zasoby dotyczące środowiska użytkownika końcowego w usłudze Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune).

### <a name="see-also"></a>Zobacz także
[Wymagania wstępne dotyczące rejestrowania urządzeń w usłudze Microsoft Intune](prerequisites-for-enrollment.md)

