---
title: "Rejestrowanie urządzeń z systemem Windows"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: włączanie zarządzania urządzeniami przenośnymi (MDM) dla urządzeń z systemem Windows w usłudze Intune."
keywords: 
author: nathbarn
manager: nathbarn
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: 3c764b269916ae1a9b076617842eb26d7fd13bab
ms.lasthandoff: 04/19/2017


---

# <a name="enroll-windows-devices"></a>Rejestrowanie urządzeń z systemem Windows

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Ten temat ułatwia administratorom IT uproszczenie rejestracji urządzeń z systemem Windows dla użytkowników.  Urządzenia z systemem Windows można rejestrować bez żadnych dodatkowych czynności, ale możesz ułatwić użytkownikom tę rejestrację.

Obecnie obsługiwane jest zarządzanie wieloma użytkownikami w usłudze Intune na urządzeniach z aktualizacją systemu Windows 10 dla twórców, które zostały dołączone do domeny usługi Azure Active Directory. Oznacza to, że różni użytkownicy standardowi po zalogowaniu się do urządzenia przy użyciu poświadczeń usługi Azure AD otrzymują wszelkie aplikacje i zasady, które zostały przypisane do ich nazw użytkowników. Obecnie użytkownicy nie mogą używać witryny internetowej Portal firmy na potrzeby samoobsługowych scenariuszy, takich jak instalowanie aplikacji.

O tym, jak można uprościć proces rejestrowania urządzenia z systemem Windows, decydują dwie kwestie:

- **Czy korzystasz z usługi Azure Active Directory w wersji Premium?** <br>Usługa [Azure AD w wersji Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) jest częścią planu Enterprise Mobility + Security i innych planów licencjonowania.
- **Jakie wersje klientów systemu Windows będą rejestrowane?** <br>Urządzenia z systemem Windows 10 można rejestrować automatycznie, dodając konto służbowe. Starsze wersje należy rejestrować przy użyciu aplikacji Portal firmy.

||**Usługa Azure AD w wersji Premium**|**Inna usługa AD**|
|----------|---------------|---------------|  
|**Windows 10**|[Rejestrowanie automatyczne](#enable-windows-10-automatic-enrollment) |[Rejestrowanie przez użytkownika](#enable-windows-enrollment-without-azure-ad-premium)|
|**Starsze wersje systemu Windows**|[Rejestrowanie przez użytkownika](#enable-windows-enrollment-without-azure-ad-premium)|[Rejestrowanie przez użytkownika](#enable-windows-enrollment-without-azure-ad-premium)|

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="enable-windows-enrollment-without-azure-ad-premium"></a>Włączanie rejestrowania dla systemu Windows bez usługi Azure AD Premium
Możesz pozwolić użytkownikom na rejestrowanie ich urządzeń bez automatycznego rejestrowania w usłudze Azure AD w wersji Premium. Gdy licencje zostaną już przypisane, użytkownicy będą mogli rejestrować się po dodaniu konta służbowego na swoich urządzeniach osobistych lub połączeniu używanych przez nich urządzeń firmowych z usługą Azure AD. Utworzenie aliasu systemu DNS (typ rekordu CNAME) ułatwia użytkownikom rejestrowanie swoich urządzeń. Utworzenie rekordów zasobów CNAME systemu DNS umożliwia użytkownikom łączenie się i rejestrowanie w usłudze Intune bez podawania nazwy serwera Intune.

**Krok 1. Tworzenie rekordu CNAME** (opcjonalnie)<br>
Utwórz rekordy zasobów CNAME systemu DNS dla domeny Twojej firmy. Jeśli na przykład witryna internetowa firmy to contoso.com, w systemie DNS należy utworzyć rekord CNAME, który przekierowuje domenę EnterpriseEnrollment.contoso.com do domeny enterpriseenrollment-s.manage.microsoft.com.

Chociaż tworzenie wpisów DNS rekordów CNAME jest opcjonalne, rekordy CNAME ułatwiają użytkownikom rejestrację. Jeśli rekord CNAME nie zostanie znaleziony, użytkownicy są proszeni o ręczne wprowadzenie nazwy serwera MDM: enrollment.manage.microsoft.com.

|Typ|Nazwa hosta|Przekierowanie na|TTL|  
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.domena_firmowa.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 godzina|

Jeśli masz więcej niż jeden sufiks głównej nazwy użytkownika (UPN), musisz utworzyć jeden rekord CNAME dla każdej nazwy domeny i wskazać każdy z nich w witrynie EnterpriseEnrollment-s.manage.microsoft.com. Na przykład jeśli użytkownicy w firmie Contoso jako adresu e-mail/nazwy UPN używają adresu name@contoso.com, ale także adresów name@us.contoso.com i name@eu.constoso.com, administrator systemu DNS firmy Contoso musi utworzyć poniższe rekordy CNAME.

|Typ|Nazwa hosta|Przekierowanie na|TTL|  
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 godzina|
|CNAME|EnterpriseEnrollment.us.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 godzina|
|CNAME|EnterpriseEnrollment.eu.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 godzina|

`EnterpriseEnrollment-s.manage.microsoft.com` — obsługuje przekierowanie do usługi Intune z rozpoznawaniem domeny na podstawie nazwy domeny adresu e-mail

Propagowanie zmian rekordów DNS może potrwać do 72 godzin. Nie można zweryfikować zmiany w systemie DNS w usłudze Intune, dopóki trwa propagowanie rekordu DNS.

**Krok 2. Weryfikacja rekordu CNAME** (opcjonalnie)<br>
W portalu usługi Intune na platformie Azure wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**. W bloku Intune wybierz kolejno opcje **Zarejestruj urządzenia** > **Rejestracja Windows**. W polu **Podaj nazwę zweryfikowanej domeny** wpisz adres URL zweryfikowanej domeny witryny sieci Web firmy, a następnie wybierz pozycję **Przetestuj automatyczne wykrywanie**.

## <a name="tell-users-how-to-enroll-windows-devices"></a>Informowanie użytkowników o sposobie rejestrowania urządzeń z systemem Windows
Poinformuj użytkowników, jak mogą zarejestrować swoje urządzenia z systemem Windows i czego mogą oczekiwać po włączeniu ich do zarządzania. Instrukcje dotyczące rejestrowania przez użytkownika końcowego można znaleźć w temacie [Rejestrowanie urządzenia z systemem Windows w usłudze Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-windows). Możesz również poinformować użytkowników, [co widzi administrator IT na ich urządzeniach](https://docs.microsoft.com/intune/enduser/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows).

Aby uzyskać więcej informacji o zadaniach użytkowników końcowych, zobacz [Zasoby dotyczące środowiska użytkownika końcowego w usłudze Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune).

