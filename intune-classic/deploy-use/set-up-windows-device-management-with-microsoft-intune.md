---
title: "Konfigurowanie zarządzania urządzeniami z systemem Windows przy użyciu usługi Microsoft Intune"
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
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: cf77cb313d5a36c5e7975e70d54bf044aa2d30c8
ms.contentlocale: pl-pl
ms.lasthandoff: 06/08/2017


---

# <a name="set-up-windows-device-management"></a>Konfigurowanie zarządzania urządzeniami z systemem Windows

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ten temat ułatwia administratorom IT uproszczenie rejestracji urządzeń z systemem Windows dla użytkowników.  Urządzenia z systemem Windows można rejestrować bez żadnych dodatkowych czynności, ale możesz ułatwić użytkownikom tę rejestrację.

O tym, jak można uprościć proces rejestrowania urządzenia z systemem Windows, decydują dwie kwestie:
- **Czy korzystasz z usługi Azure Active Directory w wersji Premium?** <br>Usługa [Azure AD w wersji Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) jest częścią planu Enterprise Mobility + Security i innych planów licencjonowania.
- **Jakie wersje klientów systemu Windows będą rejestrowane?** <br>Urządzenia z systemem Windows 10 można rejestrować automatycznie, dodając konto służbowe. Starsze wersje należy rejestrować przy użyciu aplikacji Portal firmy.

||**Usługa Azure AD w wersji Premium**|**Inna usługa AD**|
|----------|---------------|---------------|  
|**Windows 10**|[Rejestrowanie automatyczne](#enable-windows-10-automatic-enrollment) |[Rejestrowanie przez użytkownika](#enable-windows-enrollment-without-azure-ad-premium)|
|**Starsze wersje systemu Windows**|[Rejestrowanie przez użytkownika](#enable-windows-enrollment-without-azure-ad-premium)|[Rejestrowanie przez użytkownika](#enable-windows-enrollment-without-azure-ad-premium)|

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="enable-windows-enrollment-without-automatic-enrollment"></a>Włączanie rejestrowania urządzeń z systemem Windows bez rejestrowania automatycznego
Możesz pozwolić użytkownikom na rejestrowanie ich urządzeń bez automatycznego rejestrowania w usłudze Azure AD w wersji Premium. Gdy licencje zostaną już przypisane, użytkownicy będą mogli rejestrować się po dodaniu konta służbowego na swoich urządzeniach osobistych lub połączeniu używanych przez nich urządzeń firmowych z usługą Azure AD. Utworzenie aliasu systemu DNS (typ rekordu CNAME) ułatwia użytkownikom rejestrowanie swoich urządzeń. Utworzenie rekordów zasobów CNAME systemu DNS umożliwia użytkownikom łączenie się i rejestrowanie w usłudze Intune bez podawania nazwy serwera Intune.

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
W [konsoli administracyjnej usługi Intune](https://manage.microsoft.com) wybierz kolejno pozycje **Administrator** &gt; **Zarządzanie urządzeniami przenośnymi** &gt; **Windows**. W polu **Podaj nazwę zweryfikowanej domeny** wpisz adres URL zweryfikowanej domeny witryny sieci Web firmy, a następnie wybierz pozycję **Przetestuj automatyczne wykrywanie**.

## <a name="tell-users-how-to-enroll-windows-devices"></a>Informowanie użytkowników o sposobie rejestrowania urządzeń z systemem Windows
Poinformuj użytkowników, jak mogą zarejestrować swoje urządzenia z systemem Windows i czego mogą oczekiwać po włączeniu ich do zarządzania.
Instrukcje dotyczące rejestrowania przez użytkownika końcowego można znaleźć w temacie [Rejestrowanie urządzenia z systemem Windows w usłudze Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows). Możesz również odesłać użytkowników do artykułu [Jakie informacje może wyświetlać moja firma, gdy zarejestruję swoje urządzenie w usłudze Intune?](https://docs.microsoft.com/intune-user-help/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows).

Aby uzyskać więcej informacji o zadaniach użytkowników końcowych, zobacz [Zasoby dotyczące środowiska użytkownika końcowego w usłudze Microsoft Intune](/intune/end-user-educate).

### <a name="see-also"></a>Zobacz także
[Wymagania wstępne dotyczące rejestrowania urządzeń w usłudze Microsoft Intune](prerequisites-for-enrollment.md)

