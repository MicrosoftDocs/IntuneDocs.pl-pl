---
title: "Korzystające z usługi Intune zasady dostępu warunkowego opartego na aplikacji"
description: "W tym temacie opisano sposób konfigurowania zasad dostępu warunkowego opartego na aplikacji z użyciem usługi Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a7f054868d0bae061f348239614f3a40b96a15b1
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/03/2017
---
# <a name="set-up-app-based-conditional-access-policies"></a>Konfigurowanie zasad dostępu warunkowego opartego na aplikacji

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

W tym temacie przedstawiono sposób konfigurowania zasad dostępu warunkowego opartego na aplikacji dla aplikacji znajdujących się na liście zatwierdzonych aplikacji. Lista zatwierdzonych aplikacji składa się z aplikacji, które zostały przetestowane przez firmę Microsoft.

> [!IMPORTANT]
> W tym temacie przedstawiono procedurę dodawania zasad dostępu warunkowego opartego na aplikacji przy użyciu usługi Exchange Online. Z procedury tej można także skorzystać w przypadku dodawania innych aplikacji z listy zatwierdzonych aplikacji (np. SharePoint Online, Microsoft Teams itp.).

## <a name="to-create-an-app-based-conditional-access-policy"></a>Tworzenie zasad dostępu warunkowego opartego na aplikacji
1.  Przejdź do witryny [Azure Portal](https://portal.azure.com) i zaloguj się przy użyciu swoich poświadczeń.

2.  Wybierz opcję **Więcej usług**, a następnie wpisz „Intune”.

3.  Wybierz opcję **Ochrona aplikacji w usłudze Intune**.

4.  W bloku **Zarządzanie aplikacjami mobilnymi w usłudze Intune** wybierz pozycję **Wszystkie ustawienia**.

5.  W sekcji **Dostęp warunkowy** wybierz pozycję **Exchange Online**.

    ![Zrzut ekranu bloku ustawień przedstawiający sekcję dostępu warunkowego z podświetloną opcją Exchange Online](./media/MAM-conditional-access-1.png)

6. W bloku **Dozwolone aplikacje** wybierz opcję **Zezwalaj na aplikacje obsługujące zasady aplikacji usługi Intune**, aby zezwolić na dostęp do usługi Exchange Online tylko aplikacjom obsługiwanym przez zasady ochrony aplikacji usługi Intune. Po wybraniu tej opcji zostanie wyświetlona lista obsługiwanych aplikacji.

    > [!NOTE]
    > Wszyscy klienci poczty programu Exchange Active Sync, w tym wbudowani klienci poczty w systemie iOS i Android łączący się z usługą Exchange Online, nie będą mogli wysyłać ani odbierać wiadomości e-mail. Użytkownicy zamiast tego otrzymają jedną wiadomość e-mail informującą ich o konieczności użycia aplikacji poczty programu Outlook.

7. Aby zastosować tę zasadę do użytkowników, otwórz blok **Grupy użytkowników z ograniczeniami** i wybierz polecenie **Dodaj grupę użytkowników**. Wybierz przynajmniej jedną grupę użytkowników, która powinna pobrać tę zasadę.

    ![Zrzut ekranu przedstawiający blok grupy użytkowników z ograniczeniami z podświetloną opcją Dodaj grupę użytkowników](./media/mam-ca-add-user-group.png)

8. Możesz postanowić, aby niektórych użytkowników w wybranej w poprzednim kroku grupie użytkowników nie dotyczyły te zasady. W takich przypadkach dodaj grupę użytkowników do listy wykluczonych grup użytkowników. W bloku **Exchange Online** wybierz pozycję **Wykluczone grupy użytkowników**. Wybierz pozycję **Dodaj grupę użytkowników**, aby otworzyć listę grup użytkowników. Wybierz grupy, które mają być wykluczone z tych zasad.

## <a name="to-modify-or-delete-user-groups-from-an-existing-app-based-ca-policy"></a>Modyfikowanie lub usuwanie grup użytkowników z istniejących zasad dostępu warunkowego opartego na aplikacji

1. Otwórz blok **Grupy użytkowników z ograniczeniami**, a następnie zaznacz grupę użytkowników, którą chcesz usunąć.
2. Kliknij ikonę wielokropka, aby wyświetlić opcje usuwania.
3. Wybierz pozycję **Usuń**, aby usunąć grupę użytkowników z listy.

## <a name="next-steps"></a>Następne kroki
[Blokowanie aplikacji, które nie obsługują nowoczesnego uwierzytelniania](app-modern-authentication-block.md)

### <a name="see-also"></a>Zobacz także

[Ochrona danych aplikacji za pomocą zasad ochrony aplikacji](app-protection-policies.md)
