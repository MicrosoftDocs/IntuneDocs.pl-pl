---
title: "Dostęp aplikacji dla usługi Exchange Online | Microsoft Docs"
description: "W tym temacie opisano sposób konfigurowania zasad dostępu warunkowego dla aplikacji do zarządzania aplikacjami mobilnymi (MAM)."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f2cd1a1f-fd29-4081-8dfa-c40993a107d5
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: fbb41a8cf6fada76b72213b8cb04fdc0428515e9
ms.openlocfilehash: ab6d1cf6a6b77be6aff6398ff99135674471ba35


---

# <a name="create-an-exchange-online-conditional-access-to-only-allow-apps-supported-by-mam"></a>Tworzenie dostępu warunkowego do usługi Exchange Online, aby zezwolić tylko na aplikacje obsługiwane przez MAM

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ten temat zawiera szczegółowe instrukcje dotyczące sposobu konfigurowania dostępu warunkowego dla usługi Exchange Online w celu zezwolenia tylko na aplikacje mobilne obsługujące zasady ochrony aplikacji usługi Intune.


## <a name="create-an-exchange-online-policy"></a>Tworzenie zasad dotyczących usługi Exchange Online
1.  Zaloguj się do [portalu Azure](https://portal.azure.com) zawierającego funkcję dostępu do aplikacji. Jeśli jesteś nowym użytkownikiem portalu Azure, zapoznaj się z tematem [Witryna Azure Portal dla zasad ochrony aplikacji](azure-portal-for-microsoft-intune-mam-policies.md).

2.  Wybierz opcję **Więcej usług**, a następnie wpisz „Intune”.

3.  Wybierz opcję **Ochrona aplikacji w usłudze Intune**.

4.  W bloku **Zarządzanie aplikacjami mobilnymi w usłudze Intune** wybierz pozycję **Wszystkie ustawienia**.

5.  W sekcji **Dostęp warunkowy** wybierz pozycję **Exchange Online**.

    ![Zrzut ekranu bloku ustawień przedstawiający sekcję dostępu warunkowego z podświetloną opcją Exchange Online](../media/MAM-conditional-access-1.png)

6. W bloku **Dozwolone aplikacje** wybierz opcję **Zezwalaj na aplikacje obsługujące zasady aplikacji usługi Intune**, aby zezwolić na dostęp do usługi Exchange Online tylko aplikacjom obsługiwanym przez zasady ochrony aplikacji usługi Intune. Po wybraniu tej opcji zostanie wyświetlona lista obsługiwanych aplikacji.

    >[!NOTE]
    >Wszyscy klienci poczty programu Exchange Active Sync, w tym wbudowani klienci poczty w systemie iOS i Android łączący się z usługą Exchange Online, nie będą mogli wysyłać ani odbierać wiadomości e-mail. Użytkownicy zamiast tego otrzymają jedną wiadomość e-mail informującą ich o konieczności użycia aplikacji poczty programu Outlook.

7. Aby zastosować tę zasadę do użytkowników, otwórz blok **Grupy użytkowników z ograniczeniami** i wybierz polecenie **Dodaj grupę użytkowników**. Wybierz przynajmniej jedną grupę użytkowników, która powinna pobrać tę zasadę.

    ![Zrzut ekranu przedstawiający blok grupy użytkowników z ograniczeniami z podświetloną opcją Dodaj grupę użytkowników](../media/mam-ca-add-user-group.png)

8. Możesz postanowić, aby niektórych użytkowników w wybranej w poprzednim kroku grupie użytkowników nie dotyczyły te zasady. W takich przypadkach dodaj grupę użytkowników do listy wykluczonych grup użytkowników. W bloku **Exchange Online** wybierz pozycję **Wykluczone grupy użytkowników**. Wybierz pozycję **Dodaj grupę użytkowników**, aby otworzyć listę grup użytkowników. Wybierz grupy, które mają być wykluczone z tych zasad.  

## <a name="modify-an-existing-policy"></a>Modyfikowanie istniejącej zasady
### <a name="add-or-delete-user-groups"></a>Dodawanie lub usuwanie grup użytkowników

Aby **usunąć grupę użytkowników** z listy **Grupy użytkowników z ograniczeniami**, otwórz blok **Grupy użytkowników z ograniczeniami**, zaznacz grupę użytkowników, którą chcesz usunąć, a następnie kliknij **wielokropek (...)**, aby wyświetlić opcję **Usuń**. Wybierz pozycję **Usuń**, aby usunąć grupę użytkowników z listy. Za pomocą tej samej procedury możesz usunąć grupę użytkowników z listy **Wykluczone grupy użytkowników**.


## <a name="next-steps"></a>Następne kroki
[Blokowanie aplikacji, które nie obsługują nowoczesnego uwierzytelniania](block-apps-with-no-modern-authentication.md)
### <a name="see-also"></a>Zobacz także
[Ochrona danych aplikacji za pomocą zasad ochrony aplikacji](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Feb17_HO2-->


