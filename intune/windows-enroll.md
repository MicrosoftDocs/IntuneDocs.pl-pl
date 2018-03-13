---
title: "Rejestrowanie urządzeń z systemem Windows"
titlesuffix: Azure portal
description: "Włączanie zarządzania urządzeniami mobilnymi (MDM) dla urządzeń z systemem Windows w usłudze Intune."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fea5a61da77a3f96e006ee9ceb4ec3d8de645072
ms.sourcegitcommit: 80a2eefc1896a42cc2bc16be23093d1abf58b088
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/27/2018
---
# <a name="enroll-windows-devices"></a>Rejestrowanie urządzeń z systemem Windows

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ten temat ułatwia administratorom IT uproszczenie rejestracji urządzeń z systemem Windows dla użytkowników. Po [skonfigurowaniu usługi Intune](setup-steps.md) użytkownicy rejestrują urządzenia z systemem Windows, [logując się](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows) za pomocą konta służbowego.  

Jako administrator usługi Intune możesz uprościć rejestrację, korzystając z następujących sposobów:
- [Włączenie rejestracji automatycznej](#enable-windows-10-automatic-enrollment) (wymagana usługa Azure AD Premium)
- [Rejestracja rekordu CNAME](#simplify-windows-enrollment-without-azure-ad-premium)
- [Włączenie rejestracji zbiorczej](windows-bulk-enroll.md) (wymagana usługa Azure AD Premium i aplikacja Windows Configuration Designer)
- [Dodanie niestandardowego komunikatu](windows-enrollment-status.md) w celu powitania użytkowników podczas rejestracji i wyświetlania postępu ustawień zasad, kiedy są one stosowane

O tym, jak można uprościć proces rejestrowania urządzenia z systemem Windows, decydują dwie kwestie:

- **Czy korzystasz z usługi Azure Active Directory w wersji Premium?** <br>Usługa [Azure AD w wersji Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) jest częścią planu Enterprise Mobility + Security i innych planów licencjonowania.
- **Jakie wersje klientów systemu Windows będą rejestrować użytkownicy?** <br>Urządzenia z systemem Windows 10 można rejestrować automatycznie, dodając konto służbowe. Starsze wersje należy rejestrować przy użyciu aplikacji Portal firmy.

||**Usługa Azure AD w wersji Premium**|**Inna usługa AD**|
|----------|---------------|---------------|  
|**Windows 10**|[Rejestrowanie automatyczne](#enable-windows-10-automatic-enrollment) |[Rejestrowanie przez użytkownika](#enable-windows-enrollment-without-azure-ad-premium)|
|**Starsze wersje systemu Windows**|[Rejestrowanie przez użytkownika](#enable-windows-enrollment-without-azure-ad-premium)|[Rejestrowanie przez użytkownika](#enable-windows-enrollment-without-azure-ad-premium)|

Organizacje, które mogą używać rejestrowania automatycznego, mogą także skonfigurować [zbiorcze rejestrowanie urządzeń](windows-bulk-enroll.md) za pomocą aplikacji Windows Configuration Designer.

**Obsługa wielu użytkowników**<br>
Obecnie obsługiwane jest zarządzanie wieloma użytkownikami w usłudze Intune na urządzeniach z aktualizacją systemu Windows 10 dla twórców, które zostały dołączone do domeny usługi Azure Active Directory. Gdy użytkownicy standardowi logują się przy użyciu poświadczeń usługi Azure AD, otrzymują aplikacje i zasady przypisane do ich nazwy użytkownika. Obecnie użytkownicy nie mogą używać witryny internetowej Portal firmy na potrzeby samoobsługowych scenariuszy, takich jak instalowanie aplikacji.

[!INCLUDE[AAD-enrollment](./includes/win10-automatic-enrollment-aad.md)]

## <a name="simplify-windows-enrollment-without-azure-ad-premium"></a>Uproszczenie rejestrowania systemu Windows bez usługi Azure AD Premium
Aby uprościć rejestrację dla użytkowników, możesz utworzyć alias serwera nazw domen (DNS) (typ rekordu CNAME), który automatycznie przekierowuje żądania rejestrowania do serwerów usługi Intune. Jeśli nie utworzysz rekordu zasobu CNAME systemu DNS, użytkownicy próbujący nawiązać połączenie z usługą Intune muszą wprowadzić nazwę serwera usługi Intune podczas rejestracji.

**Krok 1. Tworzenie rekordu CNAME** (opcjonalnie)<br>
Utwórz rekordy zasobów CNAME systemu DNS dla domeny Twojej firmy. Jeśli na przykład witryna internetowa firmy to contoso.com, w systemie DNS należy utworzyć rekord CNAME, który przekierowuje domenę EnterpriseEnrollment.contoso.com do domeny enterpriseenrollment-s.manage.microsoft.com.

Chociaż tworzenie wpisów DNS rekordów CNAME jest opcjonalne, rekordy CNAME ułatwiają użytkownikom rejestrację. Jeśli rekord CNAME nie zostanie znaleziony, użytkownicy są proszeni o ręczne wprowadzenie nazwy serwera MDM: enrollment.manage.microsoft.com.

|Typ|Nazwa hosta|Przekierowanie na|TTL|
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.domena_firmowa.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 godzina|
|CNAME|EnterpriseRegistration.domena_firmowa.com|EnterpriseRegistration.windows.net|1 godzina|

Jeśli masz więcej niż jeden sufiks głównej nazwy użytkownika (UPN), musisz utworzyć jeden rekord CNAME dla każdej nazwy domeny i wskazać każdy z nich w witrynie EnterpriseEnrollment-s.manage.microsoft.com. Jeśli użytkownicy w firmie Contoso jako adresu e-mail/nazwy UPN używają adresu name@contoso.com, ale także adresów name@us.contoso.com i name@eu.constoso.com, administrator systemu DNS firmy Contoso powinien utworzyć poniższe rekordy CNAME:

|Typ|Nazwa hosta|Przekierowanie na|TTL|  
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 godzina|
|CNAME|EnterpriseEnrollment.us.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 godzina|
|CNAME|EnterpriseEnrollment.eu.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 godzina|

`EnterpriseEnrollment-s.manage.microsoft.com` — obsługuje przekierowanie do usługi Intune z rozpoznawaniem domeny na podstawie nazwy domeny adresu e-mail

Propagowanie zmian rekordów DNS może potrwać do 72 godzin. Nie można zweryfikować zmiany w systemie DNS w usłudze Intune, dopóki trwa propagowanie rekordu DNS.

**Krok 2. Weryfikacja rekordu CNAME** (opcjonalnie)<br>
W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**. W bloku Intune wybierz kolejno opcje **Zarejestruj urządzenia** > **Rejestracja Windows**. W polu **Podaj nazwę zweryfikowanej domeny** wpisz adres URL witryny internetowej firmy, a następnie wybierz pozycję **Przetestuj automatyczne wykrywanie**.

## <a name="tell-users-how-to-enroll-windows-devices"></a>Informowanie użytkowników o sposobie rejestrowania urządzeń z systemem Windows
Poinformuj użytkowników, jak mogą zarejestrować swoje urządzenia z systemem Windows i czego mogą oczekiwać po włączeniu ich do zarządzania.

> [!NOTE]
> Użytkownicy końcowi muszą uzyskać dostęp do witryny Portal firmy przy użyciu przeglądarki Microsoft Edge, aby wyświetlać aplikacje systemu Windows przypisane do konkretnych wersji systemu Windows. Inne przeglądarki, w tym Google Chrome, Mozilla Firefox oraz Internet Explorer nie obsługują tego typu filtrowania.

Instrukcje dotyczące rejestrowania przez użytkownika końcowego można znaleźć w temacie [Rejestrowanie urządzenia z systemem Windows w usłudze Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows). Możesz również poinformować użytkowników, aby zapoznali się z tematem [Co widzi administrator IT na moim urządzeniu](https://docs.microsoft.com/intune-user-help/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows).

Aby uzyskać więcej informacji o zadaniach użytkowników końcowych, zobacz [Zasoby dotyczące środowiska użytkownika końcowego w usłudze Microsoft Intune](end-user-educate.md).

## <a name="next-steps"></a>Następne kroki

- [Uwagi dotyczące zarządzania urządzeniami z systemem Windows przy użyciu usługi Intune na platformie Azure](/intune-classic/deploy-use/intune-on-azure).
