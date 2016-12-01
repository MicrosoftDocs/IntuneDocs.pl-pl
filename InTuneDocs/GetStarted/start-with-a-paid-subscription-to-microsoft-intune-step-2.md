---
title: Konfigurowanie niestandardowej nazwy domeny | Microsoft Intune
description: "Dodawanie niestandardowej nazwy domeny dla subskrypcji usługi Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2382f36f-13d8-4a32-81ad-6cfa604889c3
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 29b6e5a3d319c741482fcc2b600842e2e42b96e2
ms.openlocfilehash: 9fe78bca15ffee1e5e0e7e3758ff70b6bc92b619


---


# <a name="configure-a-custom-domain-name"></a>Konfigurowanie niestandardowej nazwy domeny

Gdy organizacja rejestruje się w usłudze w chmurze firmy Microsoft, takiej jak Intune, otrzymuje początkową nazwę domeny hostowaną w usłudze Azure Active Directory (AD), która wygląda podobnie do następującej: **twojadomena.onmicrosoft.com**. W tym przykładzie **twojadomena** jest nazwą domeny wybraną podczas rejestracji, a **onmicrosoft.com** jest sufiksem przypisanym do kont dodanych do subskrypcji. Jeśli organizacja ma niestandardową domenę, możesz skonfigurować wystąpienie usługi Intune do korzystania z tej domeny zamiast nazwy domeny zapewnionej w ramach subskrypcji.

Przed utworzeniem kont użytkowników lub zsynchronizowaniem lokalnej usługi Active Directory zdecydowanie zalecane jest określenie, czy używana będzie tylko domena .onmicrosoft.com, czy też zostanie dodana co najmniej jedna niestandardowa nazwa domeny. Skonfigurowanie domeny niestandardowej przed dodaniem użytkowników może ułatwić zarządzanie tożsamościami użytkowników subskrypcji przez umożliwienie użytkownikom logowania się przy użyciu poświadczeń, których używają do uzyskiwania dostępu do innych zasobów domeny.

Po zasubskrybowaniu usługi firmy Microsoft w chmurze Twoje wystąpienie tej usługi staje się [dzierżawą usługi Microsoft Azure Active Directory](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant), która zapewnia usługi tożsamości i usługi katalogowe na potrzeby usługi w chmurze. Ponieważ zadania związane z konfiguracją usługi Intune do korzystania z niestandardowej nazwy domeny organizacji są takie same jak w przypadku pozostałych dzierżaw usługi Azure AD, skorzystaj z informacji i procedur dostępnych w temacie [Dodawanie domeny](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).

> [!TIP]
> Aby uzyskać więcej informacji na temat używania domeny niestandardowej z usługą firmy Microsoft w chmurze, zobacz [Conceptual overview of custom domain names in Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain-concepts/) (Poglądowe omówienie niestandardowych nazw domen w usłudze Azure Active Directory).

Nie można zmienić ani usunąć początkowej nazwy domeny. Możesz jednak dodawać, weryfikować i usuwać własne niestandardowe nazwy domeny do użycia z usługą Intune, co jest przydatne, jeśli chcesz zachować tożsamość swojej firmy.

## <a name="to-add-and-verify-your-custom-domain"></a>Aby dodać i zweryfikować domenę niestandardową

1. Przejdź do [portalu zarządzania usługi Office 365](https://portal.office.com/Admin/Default.aspx) i zaloguj się na swoim koncie administratora.

2. W okienku nawigacji wybierz pozycje **Ustawienia** &gt; **Domeny**.

3. Wybierz pozycję **Dodaj domenę** i wpisz niestandardową nazwę domeny.

4. Zostanie otwarte okno dialogowe **Weryfikowanie domeny** udostępniające wartości do utworzenia rekordu TXT u dostawcy hostingu DNS.
    - **Użytkownicy serwisu GoDaddy**: Portal zarządzania usługi Office 365 przekieruje Cię do strony logowania serwisu GoDaddy. Rekord TXT zostanie utworzony automatycznie po wprowadzeniu poświadczeń i zaakceptowaniu umowy uprawnień do zmiany domeny. Możesz też [utworzyć nowy rekord TXT](https://support.office.com/en-us/article/Create-DNS-records-at-GoDaddy-for-Office-365-f40a9185-b6d5-4a80-bb31-aa3bb0cab48a?ui=en-US&rs=en-US&ad=US).
    - **Użytkownicy serwisu Register.com**: postępuj zgodnie z [instrukcjami krok po kroku](https://support.office.com/en-us/article/Create-DNS-records-at-Register-com-for-Office-365-55bd8c38-3316-48ae-a368-4959b2c1684e?ui=en-US&rs=en-US&ad=US#BKMK_verify), aby utworzyć rekord TXT.

    > [!TIP]
    > Utwórz alias DNS (CNAME) dla [rejestracji urządzeń z systemem Windows](/Intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) podczas wprowadzania zmian u dostawcy hostingu DNS.

Kroki służące do dodawania i weryfikowania domeny niestandardowej mogą być alternatywnie [wykonywane w usłudze Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-add-domain/).

W scenariuszu chmury hybrydowej po dodaniu niestandardowej nazwy domeny i zweryfikowaniu jej jako będącej własnością Twojej organizacji możesz zachować zarządzanie kontami użytkowników w lokalnej usłudze Active Directory, a następnie zsynchronizować ją z usługą Azure AD.

## <a name="to-synchronize-on-premises-users-with-azure-ad"></a>Aby zsynchronizować lokalnych użytkowników z usługą Azure AD##

1. [Dodaj sufiks nazwy UPN](https://technet.microsoft.com/en-us/library/cc772007.aspx) dla domeny niestandardowej w lokalnej usłudze Active Directory.
2. Ustaw nowy sufiks nazwy UPN dla użytkowników lokalnych, których chcesz zaimportować.
3. Uruchom [synchronizację programu Azure AD Connect](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/) w celu zintegrowania lokalnych użytkowników z usługą Azure AD.
4. Po pomyślnym zsynchronizowaniu informacji o kontach użytkowników można przypisać licencje usługi Microsoft Intune przy użyciu [portalu zarządzania usługi Office 365](https://portal.office.com/Admin/Default.aspx).

### <a name="see-also"></a>Zobacz także

[Informacje o początkowej domenie onmicrosoft.com w usłudze Office 365](https://support.office.com/en-us/article/About-your-initial-onmicrosoft-com-domain-in-Office-365-B9FC3018-8844-43F3-8DB1-1B3A8E9CFD5A?ui=en-US&rs=en-US&ad=US)

[Co należy wiedzieć przed rozpoczęciem korzystania z usługi Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md)
### <a name="next-steps"></a>Następne kroki
Gratulacje! Krok 2 *przewodnika Szybki start dotyczącego usługi Intune* został ukończony.

>[!div class="step-by-step"]

>[&larr;**Logowanie się do usługi Intune**](.\start-with-a-paid-subscription-to-microsoft-intune-step-1.md)     [**Dodawanie użytkowników do usługi Intune** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-3.md)  



<!--HONumber=Nov16_HO4-->


