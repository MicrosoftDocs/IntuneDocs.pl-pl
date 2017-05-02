---
title: "Konfigurowanie dostępu do aplikacji dla usługi SharePoint Online"
description: 
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 531b09bb-ddfd-498f-8ee3-6675d2466208
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: 992273f88e4bbe234f11f936d6416dbaf0d394e9
ms.lasthandoff: 04/19/2017


---

# <a name="create-a-sharepoint-online-conditional-access-policy-to-only-allow-apps-supported-by-mam"></a>Tworzenie zasad dostępu warunkowego usługi SharePoint Online zezwalających wyłącznie na aplikacje obsługiwane przez zasady zarządzania aplikacjami mobilnymi
Ten temat zawiera szczegółowe instrukcje dotyczące sposobu konfigurowania dostępu warunkowego dla usługi Exchange Online, aby zezwolić tylko na aplikacje mobilne obsługujące zasady zarządzania aplikacjami mobilnymi (MAM) usługi Intune.

## <a name="configure-a-sharepoint-online-policy"></a>Konfigurowanie zasad usługi SharePoint Online
**Krok 1:** Zaloguj się do witryny [Azure Portal](https://portal.azure.com) z funkcją dostępu do aplikacji. Jeśli jesteś nowym użytkownikiem portalu Azure, zapoznaj się z tematem [Portal Azure — zasady zarządzania aplikacjami mobilnymi](azure-portal-for-microsoft-intune-mam-policies.md).

**Krok 2:** Przejdź do pozycji **Przeglądaj > Intune > Blok Zarządzanie aplikacjami mobilnymi w usłudze Intune > Ustawienia**, a następnie w sekcji **Dostęp warunkowy** wybierz pozycję **SharePoint Online**.

![Zrzut ekranu: blok ustawień, sekcja dostępu warunkowego i otwarty blok usługi SharePoint Online](../media/mam-ca-settings-spo.png)

**Krok 3:** W bloku **Dozwolone aplikacje** wybierz opcję **Zezwalaj na aplikacje obsługujące zasady aplikacji usługi Intune**, aby zezwolić na dostęp do usługi SharePoint Online tylko aplikacjom obsługiwanym przez zasady zarządzania aplikacjami mobilnymi usługi Intune. Jeśli nadasz uprawnienia dostępu wyłącznie aplikacjom obsługiwanym przez zasady zarządzania aplikacjami mobilnymi usługi Intune, zostanie wyświetlona lista obsługiwanych aplikacji.

![Zrzut ekranu: blok dozwolonych aplikacji z listą aplikacji](../media/mam-ca-spo-allowed-apps.png)

**Krok 4:** Aby zastosować tę zasadę do użytkowników, otwórz blok **Grupy użytkowników z ograniczeniami** i wybierz polecenie **Dodaj grupę użytkowników**. Wybierz przynajmniej jedną grupę użytkowników, która powinna pobrać tę zasadę.

![Zrzut ekranu przedstawiający blok grupy użytkowników z ograniczeniami z podświetloną opcją Dodaj grupę użytkowników](../media/mam-ca-spo-restricted-groups.png)


**Krok 5:** Możesz postanowić, aby niektórych użytkowników w wybranej w poprzednim kroku grupie użytkowników nie dotyczyły te zasady. W takich przypadkach dodaj grupę użytkowników do listy wykluczonych grup użytkowników. W bloku **SharePoint Online** wybierz pozycję **Wykluczone grupy użytkowników**. Wybierz pozycję **Dodaj grupę użytkowników**, aby otworzyć listę grup użytkowników. Wybierz grupy, które mają być wykluczone z tych zasad.  

## <a name="modifying-an-existing-policy"></a>Modyfikowanie istniejącej zasady
### <a name="adding-or-deleting-user-groups"></a>Dodawanie lub usuwanie grup użytkowników
Aby **usunąć grupę użytkowników** z listy **Grupy użytkowników z ograniczeniami**, otwórz blok Grupy użytkowników z ograniczeniami, zaznacz grupę użytkowników, którą chcesz usunąć, a następnie kliknij ..., aby zobaczyć opcję usuwania. Wybierz pozycję **Usuń**, aby usunąć grupę użytkowników z listy. Za pomocą tej samej procedury możesz usunąć grupę użytkowników z listy **Wykluczone grupy użytkowników**.


## <a name="next-steps"></a>Następne kroki
[Konfigurowanie dostępu aplikacji dla usługi Exchange Online](mam-ca-for-exchange-online.md)

[Blokowanie aplikacji, które nie obsługują nowoczesnego uwierzytelniania](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a>Zobacz także

[Ochrona danych aplikacji za pomocą zasad zarządzania aplikacjami mobilnymi](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

