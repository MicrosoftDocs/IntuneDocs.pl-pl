---
title: "Konfigurowanie dostępu aplikacji dla usługi Exchange Online | Microsoft Intune"
description: "W tym temacie opisano sposób konfigurowania zasad dostępu warunkowego dla aplikacji do zarządzania aplikacjami mobilnymi (MAM)."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f2cd1a1f-fd29-4081-8dfa-c40993a107d5
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0f78ece8bbaf813c0082e6b764d174cf25bcb618
ms.openlocfilehash: fd00785f5e9eeecddb3840dcb9e2674e8786526e


---

# Tworzenie dostępu warunkowego do usługi Exchange Online, aby zezwolić tylko na aplikacje obsługiwane przez MAM
Ten temat zawiera szczegółowe instrukcje dotyczące sposobu konfigurowania dostępu warunkowego dla usługi Exchange Online, aby zezwolić tylko na aplikacje mobilne obsługujące zasady zarządzania aplikacjami mobilnymi (MAM) usługi Intune.


## Tworzenie zasad dotyczących usługi Exchange Online
1.  Zaloguj się do [portalu Azure](portal.azure.com) zawierającego funkcję dostępu do aplikacji. Jeśli jesteś nowym użytkownikiem portalu Azure, zapoznaj się z tematem [Portal Azure — zasady zarządzania aplikacjami mobilnymi](azure-portal-for-microsoft-intune-mam-policies.md).

2.  Wybierz pozycję **Przeglądaj > Intune > Blok zarządzania aplikacjami mobilnymi w usłudze Intune > Ustawienia**, a następnie w sekcji **Dostęp warunkowy** wybierz pozycję **Exchange Online**.

  ![Zrzut ekranu bloku ustawień przedstawiający sekcję dostępu warunkowego z podświetloną opcją Exchange Online](../media/mam-ca-settings-exo.png)

3.  W bloku **Dozwolone aplikacje** wybierz opcję **Zezwalaj na aplikacje obsługujące zasady aplikacji usługi Intune**, aby zezwolić na dostęp do usługi Exchange Online tylko aplikacjom obsługiwanym przez zasady zarządzania aplikacjami mobilnymi usługi Intune. Po wybraniu tej opcji zostanie wyświetlona lista obsługiwanych aplikacji.

  >[!NOTE]
  >Wszyscy klienci poczty programu Exchange Active Sync, w tym wbudowani klienci poczty w systemie iOS i Android łączący się z usługą Exchange Online, nie będą mogli wysyłać ani odbierać wiadomości e-mail. Użytkownicy zamiast tego otrzymają jedną wiadomość e-mail informującą ich o konieczności użycia aplikacji poczty programu Outlook. 
4.   Aby zastosować tę zasadę do użytkowników, otwórz blok **Grupy użytkowników z ograniczeniami** i wybierz polecenie **Dodaj grupę użytkowników**. Wybierz przynajmniej jedną grupę użytkowników, która powinna pobrać tę zasadę.

  ![Zrzut ekranu przedstawiający blok grupy użytkowników z ograniczeniami z podświetloną opcją Dodaj grupę użytkowników](../media/mam-ca-add-user-group.png)

5.  Możesz postanowić, aby niektórych użytkowników w wybranej w poprzednim kroku grupie użytkowników nie dotyczyły te zasady. W takich przypadkach dodaj grupę użytkowników do listy wykluczonych grup użytkowników. W bloku **Exchange Online** wybierz pozycję **Wykluczone grupy użytkowników**. Wybierz pozycję **Dodaj grupę użytkowników**, aby otworzyć listę grup użytkowników. Wybierz grupy, które mają być wykluczone z tych zasad.  

## Modyfikowanie istniejącej zasady
### Dodawanie lub usuwanie grup użytkowników

Aby **usunąć grupę użytkowników** z listy **Grupy użytkowników z ograniczeniami**, otwórz blok **Grupy użytkowników z ograniczeniami**, zaznacz grupę użytkowników, którą chcesz usunąć, a następnie kliknij **wielokropek (...)**, aby wyświetlić opcję **Usuń**. Wybierz pozycję **Usuń**, aby usunąć grupę użytkowników z listy. Za pomocą tej samej procedury możesz usunąć grupę użytkowników z listy **Wykluczone grupy użytkowników**.


## Następne kroki
[Blokowanie aplikacji bez nowoczesnego uwierzytelniania](block-apps-with-no-modern-authentication.md)
### Zobacz także
[Ochrona danych aplikacji za pomocą zasad zarządzania aplikacjami mobilnymi](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO2-->


