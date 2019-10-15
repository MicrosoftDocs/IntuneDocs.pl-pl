---
title: Konfigurowanie niestandardowej nazwy domeny
titleSuffix: Microsoft Intune
description: Dodawanie niestandardowej nazwy domeny dla subskrypcji usługi Microsoft Intune
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 06/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2382f36f-13d8-4a32-81ad-6cfa604889c3
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: b1087082400b321c07ea5993ca0280bf0ce455b1
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71726092"
---
# <a name="configure-a-custom-domain-name"></a>Konfigurowanie niestandardowej nazwy domeny

[!INCLUDE [both-portals](../../intune-classic/includes/note-for-both-portals.md)]

Ten temat zawiera informacje dla administratorów dotyczące tworzenia rekordu CNAME systemu DNS w celu uproszczenia i dostosowania środowiska logowania przy użyciu usługi Microsoft Intune.

Gdy organizacja rejestruje się w usłudze w chmurze firmy Microsoft, takiej jak Intune, otrzymuje początkową nazwę domeny hostowaną w usłudze Azure Active Directory (AD), która wygląda podobnie do: **twojadomena.onmicrosoft.com**. W tym przykładzie **twojadomena** to nazwa domeny wybrana podczas rejestracji. **onmicrosoft.com** jest sufiksem przypisanym do kont dodanych do subskrypcji. Można skonfigurować domenę niestandardową organizacji zapewniającą dostęp do usługi Intune zamiast nazwy domeny zapewnionej w ramach subskrypcji.

Przed utworzeniem kont użytkowników lub zsynchronizowaniem lokalnej usługi Active Directory zdecydowanie zalecane jest określenie, czy używana będzie tylko domena .onmicrosoft.com, czy też zostanie dodana co najmniej jedna niestandardowa nazwa domeny. Skonfiguruj domenę niestandardową przed dodaniem użytkowników, aby uprościć zarządzanie użytkownikami. Konfigurowanie domeny niestandardowej pozwala użytkownikom na logowanie się przy użyciu poświadczeń, których używają w celu uzyskania dostępu do innych zasobów domeny.

Po zasubskrybowaniu usługi firmy Microsoft w chmurze Twoje wystąpienie tej usługi staje się [dzierżawą usługi Microsoft Azure Active Directory](https://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant), która zapewnia usługi tożsamości i usługi katalogowe na potrzeby usługi w chmurze. Ponieważ zadania związane z konfiguracją usługi Intune do korzystania z niestandardowej nazwy domeny organizacji są takie same jak w przypadku pozostałych dzierżaw usługi Azure AD, skorzystaj z informacji i procedur dostępnych w temacie [Dodawanie domeny](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).

> [!TIP]
> Aby dowiedzieć się więcej na temat domen niestandardowych, zobacz artykuł [Poglądowe omówienie niestandardowych nazw domen w usłudze Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain-concepts/).

Nie można zmienić ani usunąć początkowej nazwy domeny onmicrosoft.com. Można dodać, zweryfikować lub usunąć niestandardowe nazwy domen używane z usługą Intune, aby zapewnić wyraźną tożsamość firmy.

## <a name="to-add-and-verify-your-custom-domain"></a>Aby dodać i zweryfikować domenę niestandardową

1. Przejdź do [centrum administracyjnego platformy Microsoft 365](https://admin.microsoft.com/) i zaloguj się do konta administratora.

2. W okienku nawigacji wybierz pozycje **Konfiguracja** &gt; **Domeny**.

3. Wybierz pozycję **Dodaj domenę** i wpisz niestandardową nazwę domeny. Wybierz pozycję **Dalej**.
   ![Zrzut ekranu centrum administracyjnego platformy Microsoft 365 z wybranymi opcjami Ustawienia > Domeny oraz dodawaną nową nazwą domeny](./media/custom-domain-name-configure/domain-custom-add.png)
4. Zostanie otwarte okno dialogowe **Weryfikowanie domeny** udostępniające wartości do utworzenia rekordu TXT u dostawcy hostingu DNS.
    - **Użytkownicy serwisu GoDaddy**: centrum administracyjne platformy Microsoft 365 przekieruje Cię do strony logowania do serwisu GoDaddy. Rekord TXT zostanie utworzony automatycznie po wprowadzeniu poświadczeń i zaakceptowaniu umowy uprawnień do zmiany domeny. Możesz też [utworzyć nowy rekord TXT](https://support.office.com/article/Create-DNS-records-at-GoDaddy-for-Office-365-f40a9185-b6d5-4a80-bb31-aa3bb0cab48a).
    - **Użytkownicy serwisu Register.com**: postępuj zgodnie z [instrukcjami krok po kroku](https://support.office.com/article/Create-DNS-records-at-Register-com-for-Office-365-55bd8c38-3316-48ae-a368-4959b2c1684e#BKMK_verify), aby utworzyć rekord TXT.
5. [Może być konieczne utworzenie dodatkowych rekordów DNS do rejestracji w usłudze Intune](../enrollment/windows-enroll.md#simplify-windows-enrollment-without-azure-ad-premium).

Kroki umożliwiające dodanie i zweryfikowanie domeny niestandardowej można również [wykonać w usłudze Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).

Dowiedz się więcej na temat [początkowej domeny onmicrosoft.com w usłudze Office 365](https://support.office.com/article/About-your-initial-onmicrosoft-com-domain-in-Office-365-B9FC3018-8844-43F3-8DB1-1B3A8E9CFD5A)

Dowiedz się więcej na temat [upraszczania rejestracji w systemie Windows bez użycia usługi Azure Active Directory w wersji Premium](../enrollment/windows-enroll.md#simplify-windows-enrollment-without-azure-ad-premium) przez utworzenie rekordu CNAME systemu DNS, który przekierowuje rejestrację na serwery usługi Intune.