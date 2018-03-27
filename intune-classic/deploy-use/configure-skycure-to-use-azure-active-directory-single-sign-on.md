---
title: Konfigurowanie programu Skycure do użycia z funkcją logowania jednokrotnego usługi Azure Active Directory
description: Konfigurowanie programu Skycure do użycia z funkcją logowania jednokrotnego (SSO) usługi Azure Active Directory
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 03/16/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 34d5d359-5c7c-4225-a205-8ce890b6f890
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: aef978e3d8431238a5b717628b13b875aa5b89cc
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/22/2018
---
# <a name="configure-skycure-to-use-azure-active-directory-single-sign-on-sso"></a>Konfigurowanie programu Skycure do użycia z funkcją logowania jednokrotnego (SSO) usługi Azure Active Directory

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Funkcja logowania jednokrotnego usługi Azure AD jest używana po zintegrowaniu usługi Intune z programem Skycure. Poniżej przedstawiono główne zalety:

-   **Administratorzy** mogą korzystać z tych samych poświadczeń bez konieczności ich ponownego wpisywania przy każdym logowaniu i wylogowaniu z portali firmy Microsoft (Intune, Azure) i konsoli zarządzania Skycure.

-   **Użytkownicy końcowi** mogą używać tych samych poświadczeń usługi Azure AD bez konieczności ich ponownego wpisywania przy każdym logowaniu i wylogowaniu z aplikacji Skycure.

Poniżej przedstawiono kroki, które należy wykonać, aby zintegrować program Skycure z funkcją logowania jednokrotnego (SSO) usługi Azure Active Directory.

## <a name="to-retrieve-the-azure-active-directory-tenant-id"></a>Aby pobrać identyfikator dzierżawy usługi Azure Active Directory

Należy pobrać identyfikator dzierżawy usługi Azure AD.

1.  Przejdź do witryny [Portal Azure](https://portal.azure.com/) i zaloguj się przy użyciu swoich poświadczeń.

2.  Gdy zostanie wyświetlony **Pulpit nawigacyjny,** wybierz opcję **Azure Active Directory**.

![Pulpit nawigacyjny usługi Azure AD](../media/mtp/skycure-sso-1.png)

1.  Po otwarciu bloku **Azure Active Directory** wybierz polecenie **Właściwości**.

![Blok Właściwości usługi Azure AD](../media/mtp/skycure-sso-2.png)

1.  W bloku **Właściwości usługi Azure Active Directory** kliknij **ikonę Kopiuj** znajdującą się pod opcją **Identyfikator katalogu dzierżawy**.

> Wklej skopiowaną wartość identyfikatora katalogu do pliku tekstowego, aby można było później z niej skorzystać. Wartość identyfikatora katalogu będzie wymagana w dalszej części procesu integracji programu Skycure i usługi Intune.

![Pulpit nawigacyjny usługi Azure AD](../media/mtp/skycure-sso-3.png)

## <a name="allow-skycure-to-communicate-with-azure-active-directory"></a>Zezwalaj programowi Skycure na komunikowanie się z usługą Azure Active Directory

1.  Wprowadź poniższy adres URL w przeglądarce. Zamiast **DIRECTORY_ID** wprowadź skopiowany wcześniej do pliku tekstowego identyfikator dzierżawy usługi Azure Active Directory.

        https://login.microsoftonline.com/<DIRECTORY_ID>/oauth2/authorize?client_id=28fd67fdb1794629a8b0dad420b697c7&prompt=admin_consent&redirect_uri=https%3A%2F%2Fmc.skycure.com%2Fapi%2Fexternal%2Fmdm%2Faad_app_consent%2Fmanagement_callback&response_type=code

2.  Musisz zalogować się przy użyciu poświadczeń usługi Azure Active Directory. Aby kontynuować, kliknij przycisk **Akceptuj**.

![Strona logowania usługi Azure AD](../media/mtp/skycure-sso-4.png)

## <a name="create-an-azure-ad-security-group-for-skycure-optional"></a>Utwórz grupę zabezpieczeń usługi Azure AD dla programu Skycure (opcjonalnie)

Jeśli chcesz, możesz utworzyć specjalną grupę obejmującą użytkowników korzystających z programu Skycure (np. Użytkownicy Skycure). Może ona okazać się przydatna podczas analizowania działania programu Skycure za pomocą raportów.

-   Dowiedz się więcej o [sposobie tworzenia grupy i dodawania elementów członkowskich w usłudze Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).

> [!NOTE] 
> Możesz również wykorzystać istniejącą grupę zabezpieczeń usługi Azure AD.

## <a name="configure-the-azure-ad-account-to-integrate-intune-with-skycure"></a>Skonfiguruj konto usługi Azure AD do integracji programu Intune z usługą Skycure

1.  Z poziomu [konsoli zarządzania Skycure](https://aad.skycure.com/) wprowadź zapisany wcześniej w pliku tekstowym identyfikator dzierżawy usługi Azure Active Directory.

![Pole Identyfikator dzierżawy usługi Azure AD konsoli zarządzania Skycure](../media/mtp/skycure-sso-5.png)

> [!IMPORTANT] 
> Program Skycure sprawdza, czy identyfikator dzierżawy usługi Azure AD istnieje, badając usługę Azure AD. Po znalezieniu go przez program Skycure administrator może przejść do następnego kroku, którym jest konfiguracja podstawowa.

## <a name="next-steps"></a>Następne kroki

[Pobieranie zasad konfiguracji aplikacji Skycure dla systemu iOS](/intune-classic/deploy-use/download-skycure-ios-app-configuration-policy)
