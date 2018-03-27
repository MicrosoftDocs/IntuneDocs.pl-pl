---
title: Tworzenie zasad dostępu warunkowego opartego na aplikacji dla usługi SharePoint Online
description: ''
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 05/03/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 531b09bb-ddfd-498f-8ee3-6675d2466208
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.openlocfilehash: 5848fc18e0c288f8806f1fc93427d96c48317d64
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/22/2018
---
# <a name="set-up-app-based-conditional-access-ca-policies-for-sharepoint-online"></a>Konfigurowanie zasad dostępu warunkowego opartego na aplikacji dla usługi SharePoint Online

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

W tym temacie znajdują się wskazówki dotyczące sposobu konfigurowania zasad dostępu warunkowego opartego na aplikacji dla usługi SharePoint Online. Dostęp warunkowy oparty na aplikacji pozwala administratorom na zezwolenie wyłącznie na aplikacje mobilne objęte zasadami ochrony aplikacji usługi Intune.

## <a name="to-create-the-app-based-ca-policy-for-sharepoint-online"></a>Tworzenie zasad dostępu warunkowego opartego na aplikacji dla usługi SharePoint Online

1. Przejdź do witryny [Azure Portal](https://portal.azure.com) i zaloguj się przy użyciu swoich poświadczeń.

    > [!NOTE]
    > Jeśli jesteś nowym użytkownikiem witryny Azure Portal, zapoznaj się z tematem [Witryna Azure Portal dla zasad ochrony aplikacji](azure-portal-for-microsoft-intune-mam-policies.md).

2. W menu po lewej stronie wybierz pozycję **Więcej usług**, a następnie w filtrze pola tekstowego wpisz **Intune**.

3. Wybierz pozycję **Ochrona aplikacji usługi Intune** > **Zarządzanie aplikacjami mobilnymi w usłudze Intune** > **Wszystkie ustawienia**.

4. W bloku Zarządzanie aplikacjami mobilnymi w usłudze Intune wybierz kafelek SharePoint Online.

5. W bloku **Dozwolone aplikacje** wybierz opcję **Zezwól na aplikacje obsługujące zasady aplikacji usługi Intune**, aby zezwolić wyłącznie na aplikacje obsługiwane przez zasady ochrony aplikacji usługi Intune.

    > [!NOTE] 
    > Jeśli nadasz uprawnienia dostępu wyłącznie aplikacjom obsługiwanym przez zasady ochrony aplikacjami usługi Intune, zostanie wyświetlona lista zawierająca **wyłącznie** obsługiwane aplikacje.

    ![Zrzut ekranu: blok dozwolonych aplikacji z listą aplikacji](../media/mam-ca-spo-allowed-apps.png)

## <a name="to-assign-app-based-ca-policies-to-your-users"></a>Przypisywanie zasad dostępu warunkowego opartego na aplikacji do użytkowników

1. Otwórz blok **Grupy użytkowników z ograniczeniami**, a następnie wybierz pozycję **Dodaj grupę użytkowników**.

2. Wybierz przynajmniej jedną grupę użytkowników, która powinna pobrać tę zasadę.

    ![Zrzut ekranu przedstawiający blok grupy użytkowników z ograniczeniami z podświetloną opcją Dodaj grupę użytkowników](../media/mam-ca-spo-restricted-groups.png)

    > [!IMPORTANT] 
    > Możesz postanowić, aby niektórych użytkowników w wybranej w poprzednim kroku grupie użytkowników nie dotyczyły te zasady. W takich przypadkach dodaj grupę użytkowników do listy wykluczonych grup użytkowników. 

3. W bloku **SharePoint Online** wybierz pozycję **Wykluczone grupy użytkowników**, a następnie wybierz pozycję **Dodaj grupę użytkowników**, aby otworzyć listę grup użytkowników.

4. Wybierz grupy, które mają być wykluczone z tych zasad.  

## <a name="to-modify-or-delete-user-groups-from-an-existing-app-based-ca-policy"></a>Modyfikowanie lub usuwanie grup użytkowników z istniejących zasad dostępu warunkowego opartego na aplikacji

1. Otwórz blok **Grupy użytkowników z ograniczeniami**, a następnie zaznacz grupę użytkowników, którą chcesz usunąć.
2. Kliknij ikonę wielokropka, aby wyświetlić opcje usuwania.
3. Wybierz pozycję **Usuń**, aby usunąć grupę użytkowników z listy.

> [!NOTE] 
> Wykonując te same kroki, możesz usunąć grupę użytkowników z listy **Wykluczone grupy użytkowników**.

## <a name="next-steps"></a>Następne kroki

[Blokowanie aplikacji, które nie korzystają z nowoczesnego uwierzytelniania](block-apps-with-no-modern-authentication.md)

## <a name="see-also"></a>Zobacz też

[Ochrona danych aplikacji za pomocą zasad ochrony aplikacji](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

[Konfigurowanie dostępu warunkowego opartego na aplikacji dla usługi Exchange Online](mam-ca-for-exchange-online.md)
