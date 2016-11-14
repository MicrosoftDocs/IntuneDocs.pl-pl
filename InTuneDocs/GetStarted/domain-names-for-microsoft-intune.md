---
title: "Nazwy domen w usłudze Microsoft Intune | Microsoft Intune"
description: "dodawanie nazwy domeny usługi Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: swadhwa
ms.date: 10/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c3c136f0-330d-432a-a91f-16f7dd097e55
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 38159f6dbcae2eeb4dca47141e60eed12cd7f6ee
ms.openlocfilehash: abcf37e7ec3150b5a2fe4cda910631f83d4c510a


---



# Niestandardowe nazwy domen w usłudze Microsoft Intune

Gdy organizacja rejestruje się w usłudze w chmurze firmy Microsoft, takiej jak Intune, otrzymuje początkową nazwę domeny hostowaną w usłudze Azure Active Directory, która wygląda podobnie do następującej: **twojadomena.onmicrosoft.com**. W tym przykładzie **twojadomena** jest nazwą domeny wybraną podczas rejestracji, a **onmicrosoft.com** jest sufiksem przypisanym do kont dodanych do subskrypcji.

Nie można zmienić ani usunąć początkowej nazwy domeny. Możesz jednak dodawać, weryfikować i usuwać własne niestandardowe nazwy domeny do użycia z usługą Intune, co jest przydatne, jeśli chcesz zachować tożsamość swojej firmy.

## Aby dodać i zweryfikować domenę niestandardową 

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

## Aby zsynchronizować lokalnych użytkowników z usługą Azure AD##

1. [Dodaj sufiks nazwy UPN](https://technet.microsoft.com/en-us/library/cc772007.aspx) dla domeny niestandardowej w lokalnej usłudze Active Directory.
2. Ustaw nowy sufiks nazwy UPN dla użytkowników lokalnych, których chcesz zaimportować.
3. Uruchom [synchronizację programu Azure AD Connect](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/) w celu zintegrowania lokalnych użytkowników z usługą Azure AD.
4. Po pomyślnym zsynchronizowaniu informacji o kontach użytkowników można przypisać licencje usługi Microsoft Intune przy użyciu [portalu zarządzania usługi Office 365](https://portal.office.com/Admin/Default.aspx).

### Zobacz także

[Informacje o początkowej domenie onmicrosoft.com w usłudze Office 365](https://support.office.com/en-us/article/About-your-initial-onmicrosoft-com-domain-in-Office-365-B9FC3018-8844-43F3-8DB1-1B3A8E9CFD5A?ui=en-US&rs=en-US&ad=US)

[Co należy wiedzieć przed rozpoczęciem korzystania z usługi Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md)



<!--HONumber=Oct16_HO2-->


