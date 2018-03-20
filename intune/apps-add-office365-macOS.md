---
title: "Instalowanie usługi Office 365 na urządzeniach z systemem macOS przy użyciu usługi Microsoft Intune"
titlesuffix: 
description: "Dowiedz się, jak przy użyciu usługi Microsoft Intune możesz zainstalować aplikacje usługi Office 365 na urządzeniach z systemem macOS."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2372332a-7e3a-4a9c-91a9-86654e0fabe2
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8de14184c4d23adc79d5b519fdcf272f0d7f6804
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/08/2018
---
# <a name="how-to-assign-office-365-to-macos-devices-with-microsoft-intune"></a>Jak przypisać usługę Office 365 do urządzeń z systemem macOS za pomocą usługi Microsoft Intune

Typ **Aplikacja ze sklepu** ułatwia przypisywanie aplikacji usługi Office 365 do urządzeń z systemem macOS. Ten typ aplikacji umożliwia instalowanie programów Word, Excel, PowerPoint, Outlook i OneNote. Do aplikacji jest dołączony program Microsoft AutoUpdate (MAU), który poprawia ich bezpieczeństwo i zapewnia aktualność. Wybrane aplikacje są wyświetlane jako jedna aplikacja na liście aplikacji w konsoli usługi Intune.


## <a name="before-you-start"></a>Przed rozpoczęciem

Przed rozpoczęciem dodawania usługi Office 365 na urządzeniach z system macOS należy zrozumieć następujące informacje:

- Na urządzeniach, na których aplikacje są wdrażane, musi być zainstalowany system macOS w wersji 10.10 lub nowszej.
- Usługa Intune obsługuje tylko dodawanie aplikacji pakietu Office zawartych z pakiecie Office 2016 dla komputerów Mac.
- Jeśli jakiekolwiek aplikacje pakietu Office zostaną otwarte w czasie, gdy usługa Intune będzie instalować pakiet aplikacji, użytkownicy końcowi mogą utracić dane z niezapisanych plików.

## <a name="create-and-configure-the-app-suite"></a>Tworzenie i konfigurowanie pakietu aplikacji

Dodaj usługę Office 365 przy użyciu bloku **Aplikacje**.
1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Monitorowanie i zarządzanie** > **Intune**.
3. Wybierz pozycję **Aplikacje mobilne** z bloku **Intune**.
4. W obciążeniu **Aplikacje mobilne** wybierz pozycję **Aplikacje** w sekcji **Zarządzanie**. 
5. Wybierz pozycję **Dodaj**, aby wyświetlić blok **Dodawanie aplikacji**.
6. Na liście **Typ aplikacji** wybierz pozycję **macOS** w grupie **Pakiet Office 365**.
7. Wybierz pozycję **Informacje o pakiecie aplikacji** w celu podania informacji o pakiecie aplikacji. Te informacje pomagają zidentyfikować pakiet aplikacji w usłudze Intune, a także ułatwiają użytkownikom wyszukiwanie go w aplikacji Portal firmy.
8.  Podaj następujące informacje:
    - **Nazwa pakietu** — wprowadź nazwę pakietu aplikacji wyświetlaną w portalu firmy. Upewnij się, że wszystkie używane nazwy pakietów są unikatowe. Jeśli dana nazwa pakietu aplikacji występuje dwa razy, użytkownicy portalu firmy będą widzieć tylko jedną z aplikacji o tej nazwie.
    - **Opis pakietu** — wprowadź opis pakietu aplikacji.
    - **Wydawca** — w roli wydawcy występuje firma Microsoft.
    - **Kategoria** — wybierz co najmniej jedną wbudowaną lub utworzoną przez siebie kategorię aplikacji. To ustawienie ułatwi użytkownikom znajdowanie pakietu aplikacji podczas przeglądania portalu firmy.
    - **Wyświetl jako polecaną aplikację w Portalu firmy** — to ustawienie spowoduje wyróżnienie pakietu aplikacji na stronie głównej portalu firmy podczas przeglądania aplikacji przez użytkowników.
    - **Adres URL informacji** (opcjonalnie) — wprowadź adres URL witryny sieci Web zawierającej informacje o aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Adres URL zasad ochrony prywatności** — opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o ochronie prywatności dotyczące tej aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Deweloper** — w roli dewelopera występuje firma Microsoft.
    - **Właściciel** — w roli właściciela występuje firma Microsoft.
    - **Uwagi** (opcjonalnie) — wprowadź wszelkie uwagi, które chcesz skojarzyć z aplikacją.
    - **Logo** — logo usługi Office 365 jest wyświetlane razem z nazwą aplikacji podczas przeglądania portalu firmy.
9.  Kliknij przycisk **OK** w bloku **Informacje o aplikacji**.
10. Kliknij przycisk **Dodaj** w bloku **Dodawanie aplikacji**.
    Pakiet zostanie wyświetlony na liście aplikacji jako pojedynczy wpis.

## <a name="configure-app-assignments"></a>Konfigurowanie przypisań aplikacji

W tym kroku skonfigurujesz przypisania pakietu aplikacji. 

1. Wybierz pakiet aplikacji**Office 365** na liście aplikacji, aby wyświetlić blok przeglądu **Office 365**.
2. Kliknij pozycję **Przypisania** w bloku **Office 365**.
3. Kliknij pozycję **Dodaj grupę**, aby dodać grupę, w ramach której będzie używany pakiet aplikacji. Zostanie wyświetlony blok **Dodawanie grupy**.
3. Ustaw pozycję **Typ przypisania** na wartość **Wymagane**.
4. Przypisz pakiet do wybranych grup. Aby uzyskać więcej informacji, zobacz artykuł [How to assign apps to groups with Microsoft Intune](apps-deploy.md) (Jak przypisać aplikacje do grup w usłudze Microsoft Intune).

    >[!Note]
    > W przypadku grup, dla których wymagany jest pakiet aplikacji usługi Office 365, nie jest możliwe odinstalowanie go za pomocą usługi Microsoft Intune.

5. Wybierz przycisk **OK** w bloku **Przypisywanie**.
6. Wybierz przycisk **OK** w bloku **Dodawanie grupy**.
7. Wybierz przycisk **Zapisz**, aby zatwierdzić swoje przypisania.

## <a name="next-steps"></a>Następne kroki

- Aby uzyskać informacje na temat dodawania aplikacji usługi Office 365 do urządzeń z systemem Windows 10, zobacz temat [Jak przypisać aplikacje usługi Office 365 ProPlus 2016 do urządzeń z systemem Windows 10 przy użyciu usługi Microsoft Intune](apps-add-office365.md).
- Aby dowiedzieć się więcej o dołączaniu i wykluczaniu przypisań aplikacji względem grup użytkowników, zobacz [Dołączanie i wykluczanie przypisań aplikacji](apps-inc-exl-assignments.md).
