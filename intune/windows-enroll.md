---
title: Konfigurowanie rejestracji dla urządzeń z systemem Windows przy użyciu usługi Microsoft Intune
titlesuffix: ''
description: Skonfiguruj rejestrację dla urządzeń z systemem Windows.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 31c3e7b6d255cd99efee134f0276fd4d15dab6b9
ms.sourcegitcommit: 2795255e89cbe97d0b17383d446cca57c7335016
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2018
ms.locfileid: "47403565"
---
# <a name="set-up-enrollment-for-windows-devices"></a>Konfigurowanie rejestracji dla urządzeń z systemem Windows

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ten artykuł ułatwia administratorom IT uproszczenie rejestracji urządzeń z systemem Windows dla użytkowników. Po [skonfigurowaniu usługi Intune](setup-steps.md) użytkownicy rejestrują urządzenia z systemem Windows, [logując się](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows) za pomocą konta służbowego.  

Jako administrator usługi Intune możesz uprościć rejestrację, korzystając z następujących sposobów:
- [Włączenie rejestracji automatycznej](#enable-windows-10-automatic-enrollment) (wymagana usługa Azure AD Premium)
- [Rejestracja rekordu CNAME](#simplify-windows-enrollment-without-azure-ad-premium)
- [Włączenie rejestracji zbiorczej](windows-bulk-enroll.md) (wymagana usługa Azure AD Premium i aplikacja Windows Configuration Designer)

O tym, jak można uprościć proces rejestrowania urządzenia z systemem Windows, decydują dwie kwestie:

- **Czy korzystasz z usługi Azure Active Directory w wersji Premium?** <br>Usługa [Azure AD w wersji Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) jest częścią planu Enterprise Mobility + Security i innych planów licencjonowania.
- **Jakie wersje klientów systemu Windows będą rejestrować użytkownicy?** <br>Urządzenia z systemem Windows 10 można rejestrować automatycznie, dodając konto służbowe. Starsze wersje należy rejestrować przy użyciu aplikacji Portal firmy.

||**Usługa Azure AD w wersji Premium**|**Inna usługa AD**|
|----------|---------------|---------------|  
|**Windows 10**|[Rejestrowanie automatyczne](#enable-windows-10-automatic-enrollment) |[Rejestrowanie przez użytkownika](#enable-windows-enrollment-without-azure-ad-premium)|
|**Starsze wersje systemu Windows**|[Rejestrowanie przez użytkownika](#enable-windows-enrollment-without-azure-ad-premium)|[Rejestrowanie przez użytkownika](#enable-windows-enrollment-without-azure-ad-premium)|

Organizacje, które mogą używać rejestrowania automatycznego, mogą także skonfigurować [zbiorcze rejestrowanie urządzeń](windows-bulk-enroll.md) za pomocą aplikacji Windows Configuration Designer.

## <a name="multi-user-support"></a>Obsługa wielu użytkowników

Usługa Intune obsługuje zarządzanie wieloma użytkownikami na urządzeniach z aktualizacją systemu Windows 10 dla twórców, które zostały dołączone do domeny usługi Azure Active Directory. Gdy użytkownicy standardowi logują się przy użyciu poświadczeń usługi Azure AD, otrzymują aplikacje i zasady przypisane do ich nazwy użytkownika. Obecnie użytkownicy nie mogą używać witryny Portal firmy na potrzeby samoobsługowych scenariuszy, takich jak instalowanie aplikacji.

[!INCLUDE [AAD-enrollment](./includes/win10-automatic-enrollment-aad.md)]

## <a name="simplify-windows-enrollment-without-azure-ad-premium"></a>Uproszczenie rejestrowania systemu Windows bez usługi Azure AD Premium
Aby uprościć rejestrację, możesz utworzyć alias serwera nazw domen (DNS) (typ rekordu CNAME), który przekierowuje żądania rejestrowania do serwerów usługi Intune. W przeciwnym razie użytkownicy próbujący nawiązać połączenie z usługą Intune będą musieli wprowadzić nazwę serwera usługi Intune podczas rejestracji.

**Krok 1. Tworzenie rekordu CNAME** (opcjonalnie)<br>
Utwórz rekordy zasobów CNAME systemu DNS dla domeny Twojej firmy. Jeśli na przykład witryna internetowa firmy to contoso.com, w systemie DNS należy utworzyć rekord CNAME, który przekierowuje domenę EnterpriseEnrollment.contoso.com do domeny enterpriseenrollment-s.manage.microsoft.com.

Chociaż tworzenie wpisów DNS rekordów CNAME jest opcjonalne, rekordy CNAME ułatwiają użytkownikom rejestrację. Jeśli rekord CNAME nie zostanie znaleziony, użytkownicy są proszeni o ręczne wprowadzenie nazwy serwera MDM: enrollment.manage.microsoft.com.

|Typ|Nazwa hosta|Przekierowanie na|TTL|
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.domena_firmowa.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 godzina|
|CNAME|EnterpriseRegistration.domena_firmowa.com|EnterpriseRegistration.windows.net|1 godzina|

Jeśli firma używa więcej niż jednego sufiksu głównej nazwy użytkownika (UPN), musisz utworzyć jeden rekord CNAME dla każdej nazwy domeny i wskazać każdy z nich w witrynie EnterpriseEnrollment-s.manage.microsoft.com. Na przykład użytkownicy w firmie Contoso jako adresu e-mail/nazwy UPN używają następujących formatów:

- name@contoso.com
- name@us.contoso.com
- name@eu.constoso.com\

Administrator systemu DNS firmy Contoso powinien utworzyć następujące rekordy CNAME:

|Typ|Nazwa hosta|Przekierowanie na|TTL|  
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 godzina|
|CNAME|EnterpriseEnrollment.us.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 godzina|
|CNAME|EnterpriseEnrollment.eu.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 godzina|

`EnterpriseEnrollment-s.manage.microsoft.com` — obsługuje przekierowanie do usługi Intune z rozpoznawaniem domeny na podstawie nazwy domeny adresu e-mail

Propagowanie zmian rekordów DNS może potrwać do 72 godzin. Nie można zweryfikować zmiany w systemie DNS w usłudze Intune, dopóki trwa propagowanie rekordu DNS.

**Krok 2. Weryfikacja rekordu CNAME** (opcjonalnie)<br>
1. W usłudze [Intune w witrynie Azure Portal](https://aka.ms/intuneportal) wybierz kolejno pozycje **Rejestrowanie urządzenia**  >  **Rejestracja w systemie Windows**  >  **Weryfikacja rekordu CNAME**.
2. W polu **Domena** wprowadź witrynę internetową firmy, a następnie wybierz pozycję **Testuj**.

## <a name="tell-users-how-to-enroll-windows-devices"></a>Informowanie użytkowników o sposobie rejestrowania urządzeń z systemem Windows
Poinformuj użytkowników, jak mogą zarejestrować swoje urządzenia z systemem Windows i czego mogą oczekiwać po włączeniu ich do zarządzania.

> [!NOTE]
> Użytkownicy końcowi muszą uzyskać dostęp do witryny Portal firmy przy użyciu przeglądarki Microsoft Edge, aby wyświetlać aplikacje systemu Windows przypisane do konkretnych wersji systemu Windows. Inne przeglądarki, w tym Google Chrome, Mozilla Firefox oraz Internet Explorer nie obsługują tego typu filtrowania.

Instrukcje dotyczące rejestrowania przez użytkownika końcowego można znaleźć w temacie [Rejestrowanie urządzenia z systemem Windows w usłudze Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows). Możesz również poinformować użytkowników, aby zapoznali się z tematem [Co widzi administrator IT na moim urządzeniu](https://docs.microsoft.com/intune-user-help/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows).

>[!IMPORTANT]
> Jeśli nie włączono automatycznej rejestracji w rozwiązaniu MDM, ale masz urządzenia z systemem Windows 10, które zostały dołączone do usługi Azure AD, po rejestracji w konsoli usługi Intune będą widoczne dwa rekordy. Możesz rozwiązać ten problem, upewniając się, że użytkownicy z urządzeniami dołączonymi do usługi Azure AD przechodzą do pozycji **Konta** > **Uzyskaj dostęp do miejsca pracy lub nauki** i **Połącz** przy użyciu tego samego konta. 

Aby uzyskać więcej informacji o zadaniach użytkowników końcowych, zobacz [Zasoby dotyczące środowiska użytkownika końcowego w usłudze Microsoft Intune](end-user-educate.md).

## <a name="next-steps"></a>Następne kroki

- [Uwagi dotyczące zarządzania urządzeniami z systemem Windows przy użyciu usługi Intune na platformie Azure](/intune-classic/deploy-use/intune-on-azure).
