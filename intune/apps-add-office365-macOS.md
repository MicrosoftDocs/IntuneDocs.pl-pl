---
title: "Instalowanie usługi Office 365 na urządzeniach z systemem macOS przy użyciu usługi Intune"
titlesuffix: Azure portal
description: "Dowiedz się, jak przy użyciu usługi Intune możesz łatwiej instalować aplikacje usługi Office 365 na urządzeniach z systemem macOS."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2372332a-7e3a-4a9c-91a9-86654e0fabe2
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5e0ad0b99a2c8a602b5e542530a1d437065461b2
ms.sourcegitcommit: 22ab1c6a6bfeb4fef9850d12b29829c3fecbbeed
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/12/2018
---
# <a name="how-to-assign-office-365-to-macos-devices-with-microsoft-intune"></a>Jak przypisać usługę Office 365 do urządzeń z systemem macOS za pomocą usługi Microsoft Intune

Ten typ aplikacji ułatwia przypisywanie aplikacji usługi Office 365 do urządzeń z systemem macOS. Nowy typ aplikacji umożliwia instalowanie programów Word, Excel, PowerPoint, Outlook i OneNote. Do aplikacji jest dołączony program Microsoft AutoUpdate (MAU), który poprawia ich bezpieczeństwo i zapewnia aktualność. Wybrane aplikacje są wyświetlane jako jedna aplikacja na liście aplikacji w konsoli usługi Intune.


## <a name="before-you-start"></a>Przed rozpoczęciem

- Na urządzeniach, na których aplikacje są wdrażane, musi być zainstalowany system macOS w wersji 10.10 lub nowszej.
- Usługa Intune obsługuje tylko dodawanie aplikacji pakietu Office zawartych z pakiecie Office 2016 dla komputerów Mac.
- Jeśli jakiekolwiek aplikacje pakietu Office zostaną otwarte w czasie, gdy usługa Intune będzie instalować pakiet aplikacji, użytkownicy końcowi mogą utracić dane z niezapisanych plików.


## <a name="get-started"></a>Wprowadzenie
Dodaj usługę Office 365 przy użyciu bloku **Aplikacje**.
1.  Zaloguj się do portalu Azure Portal.
2.  Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3.  W bloku **Intune** wybierz pozycję **Aplikacje mobilne**.
4.  W obciążeniu **Aplikacje mobilne** wybierz pozycję **Aplikacje** w grupie **Zarządzaj**. Wybierz pozycję **Dodaj**.
5.  W bloku **Dodaj aplikację** wybierz pozycje **Office 365** > **macOS**.
6.  Wybierz pozycję **Dodaj**.

## <a name="configure-the-app-suite"></a>Konfigurowanie pakietu aplikacji

Podaj informacje o pakiecie aplikacji. Te informacje pomagają zidentyfikować pakiet w usłudze Intune, a także ułatwiają użytkownikom wyszukiwanie go w aplikacji Portal firmy.

1.  W bloku **Dodawanie aplikacji** wybierz pozycję **Informacje o pakiecie aplikacji**.
2.  Podaj następujące informacje:
    - **Nazwa pakietu** — wprowadź nazwę pakietu aplikacji wyświetlaną w portalu firmy. Upewnij się, że wszystkie używane nazwy pakietów są unikatowe. Jeśli dana nazwa pakietu aplikacji występuje dwa razy, użytkownicy portalu firmy będą widzieć tylko jedną z aplikacji o tej nazwie.
    - **Opis pakietu** — wprowadź opis pakietu aplikacji.
    - **Wydawca** — w roli wydawcy występuje firma Microsoft.
    - **Kategoria** — opcjonalnie wybierz co najmniej jedną wbudowaną lub utworzoną przez siebie kategorię aplikacji. Ułatwi to użytkownikom znajdowanie pakietu aplikacji podczas przeglądania portalu firmy.
    - **Wyświetl jako polecaną aplikację w Portalu firmy** — spowoduje to wyróżnienie pakietu aplikacji na stronie głównej portalu firmy podczas przeglądania aplikacji przez użytkowników.
    - **Adres URL informacji** — opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Adres URL zasad ochrony prywatności** — opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o zasadach ochrony prywatności mających zastosowanie do aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Deweloper** — w roli dewelopera występuje firma Microsoft.
    - **Właściciel** — w roli właściciela występuje firma Microsoft.
    - **Uwagi** — wprowadź wszelkie uwagi, które chcesz skojarzyć z aplikacją.
    - **Przekaż ikonę** — przekaż ikonę, która jest wyświetlana jako ikona aplikacji podczas przeglądania Portalu firmy.
3.  Wybierz przycisk **OK**. Pakiet zostanie wyświetlony na liście aplikacji jako pojedynczy wpis.

## <a name="configure-app-assignments"></a>Konfigurowanie przypisań aplikacji

W tym kroku skonfigurujesz przypisania pakietu aplikacji. Należy pamiętać, że wkrótce będzie dostępny typ aplikacji.

1.  Wybierz pakiet aplikacji z listy aplikacji, a następnie wybierz pozycję **Przypisania**.
2.  Wybierz pozycję **Wybierz grupy**.
3.  Przypisz pakiet do wybranych grup. Aby uzyskać więcej informacji, zobacz artykuł [How to assign apps to groups with Microsoft Intune](/intune/apps-deploy) (Jak przypisać aplikacje do grup w usłudze Microsoft Intune).
4.  Dla każdej grupy wybierz opcję **Wymagaj instalacji**.
        >[!Note]
        > You cannot uninstall Office 365 through Intune.

5. Wybierz przycisk **Zapisz**, aby zatwierdzić swoje przypisania.

## <a name="next-steps"></a>Następne kroki

Aby uzyskać informacje na temat dodawania aplikacji usługi Office 365 do urządzeń z systemem Windows 10, zobacz temat [Jak przypisać aplikacje usługi Office 365 ProPlus 2016 do urządzeń z systemem Windows 10 przy użyciu usługi Microsoft Intune](/intune/apps-add-office365).
