---
title: Instalowanie usługi Office 365 na urządzeniach z systemem macOS przy użyciu usługi Microsoft Intune
titleSuffix: ''
description: Dowiedz się, jak przy użyciu usługi Microsoft Intune możesz zainstalować aplikacje usługi Office 365 na urządzeniach z systemem macOS.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/23/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2372332a-7e3a-4a9c-91a9-86654e0fabe2
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3cf4c2abb5506f297af8a4e77145abea5360381b
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2020
ms.locfileid: "76755361"
---
# <a name="assign-office-365-to-macos-devices-with-microsoft-intune"></a>Przypisywanie usługi Office 365 do urządzeń z systemem macOS za pomocą usługi Microsoft Intune

Ten typ aplikacji ułatwia przypisywanie aplikacji usługi Office 365 2016 do urządzeń z systemem macOS. Korzystając z tego typu aplikacji, można instalować programy Word, Excel, PowerPoint, Outlook i OneNote. Aby pomóc w zachowaniu bezpieczeństwa i aktualności aplikacji, dołączamy do nich program Microsoft AutoUpdate (MAU). Wybrane aplikacje są wyświetlane jako jedna aplikacja na liście aplikacji w konsoli usługi Intune.


## <a name="before-you-start"></a>Przed rozpoczęciem

Przed rozpoczęciem dodawania usługi Office 365 na urządzeniach z systemem macOS należy zrozumieć następujące informacje:

- Na urządzeniach, na których aplikacje są wdrażane, musi być zainstalowany system macOS w wersji 10.10 lub nowszej.
- Usługa Intune obsługuje dodawanie tylko aplikacji pakietu Office zawartych w pakiecie Office 2016 dla komputerów Mac.
- Jeśli jakiekolwiek aplikacje pakietu Office są otwarte, gdy usługa Intune instaluje pakiet aplikacji, użytkownicy mogą utracić dane z niezapisanych plików.

## <a name="select-the-office-365-suite-app-type"></a>Wybieranie typu aplikacji pakietu Office 365

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Aplikacje** > **Wszystkie aplikacje** > **Dodaj**.
3. Wybierz pozycję **macOS** w sekcji **Pakiet Office 365** okienka **Wybierz typ aplikacji**.
4. Kliknij pozycję **Wybierz**. Zostaną wyświetlone kroki **dodawania pakietu Office 365**.

## <a name="step-1---app-suite-information"></a>Krok 1. Informacje o pakiecie aplikacji

W tym kroku podajesz informacje o pakiecie aplikacji. Te informacje pomagają zidentyfikować pakiet aplikacji w usłudze Intune i ułatwiają użytkownikom wyszukiwanie tego pakietu w portalu firmy.

1. Na stronie **informacji o pakiecie aplikacji** możesz potwierdzić lub zmodyfikować wartości domyślne:
    - **Nazwa pakietu**: wprowadź nazwę pakietu aplikacji wyświetlaną w portalu firmy. Upewnij się, że wszystkie używane nazwy pakietów są unikatowe. Jeśli dana nazwa pakietu aplikacji występuje dwa razy, użytkownicy portalu firmy będą widzieć tylko jedną z aplikacji o tej nazwie.
    - **Opis pakietu**: wprowadź opis pakietu aplikacji. Możesz na przykład podać listę aplikacji wybranych do uwzględnienia.
    - **Wydawca**: w roli wydawcy występuje firma Microsoft.
    - **Kategoria**: opcjonalnie wybierz co najmniej jedną wbudowaną lub utworzoną przez siebie kategorię aplikacji. To ustawienie ułatwi użytkownikom znajdowanie pakietu aplikacji podczas przeglądania portalu firmy.
    - **Pokaż jako polecaną aplikację w Portalu firmy**: wybierz tę opcję, aby wyświetlić pakiet aplikacji w dobrze widocznym miejscu na stronie głównej portalu firmy podczas przeglądania aplikacji przez użytkowników.
    - **Adres URL informacji**: Opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o tej aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Adres URL zasad ochrony prywatności**: Opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje dotyczące zasad ochrony prywatności w tej aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Deweloper**: w roli dewelopera występuje firma Microsoft.
    - **Właściciel**: w roli właściciela występuje firma Microsoft.
    - **Uwagi**: wprowadź wszelkie uwagi, które chcesz skojarzyć z tą aplikacją.
    - **Logo**: logo usługi Office 365 jest wyświetlane razem z nazwą aplikacji podczas przeglądania portalu firmy.
2. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Tagi zakresu**.

## <a name="step-2---select-scope-tags-optional"></a>Krok 2. Wybieranie tagów zakresu (opcjonalnie)
Za pomocą tagów zakresu można określić, kto będzie mógł wyświetlać informacje o aplikacji klienckiej w usłudze Intune. Więcej informacji o tagach zakresu zawiera artykuł [Używanie kontroli dostępu opartej na rolach i tagów zakresu w rozproszonej infrastrukturze informatycznej](../fundamentals/scope-tags.md).

1. Kliknij pozycję **Wybierz tagi zakresu**, aby opcjonalnie dodać tagi zakresu dla pakietu aplikacji. 
2. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Przypisania**.

## <a name="step-3---assignments"></a>Krok 3. Przypisania

1. Wybierz przypisania grupy **Wymagane** lub **Dostępne dla zarejestrowanych urządzeń** dla pakietu aplikacji. Aby uzyskać więcej informacji, zobacz temat [Dodawanie grup w celu organizowania użytkowników i urządzeń](~/fundamentals/groups-add.md) i [Przypisywanie aplikacji do grup przy użyciu usługi Microsoft Intune](apps-deploy.md).

    >[!Note]
    > Nie można odinstalować pakietu aplikacji usługi Office 365 dla systemu macOS za pomocą usługi Intune.

2. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Recenzja i tworzenie**. 

## <a name="step-4---review--create"></a>Krok 4. Przegląd + tworzenie

1. Przejrzyj wartości i ustawienia wprowadzone dla pakietu aplikacji.
2. Gdy skończysz, kliknij pozycję **Utwórz**, aby dodać aplikację do usługi Intune.

    Zostanie wyświetlony blok **Omówienie** dotyczący utworzonego pakietu aplikacji systemu Windows 10 dla usługi Office 365. Pakiet zostanie wyświetlony na liście aplikacji jako pojedynczy wpis.

## <a name="next-steps"></a>Następne kroki

- Aby uzyskać informacje na temat dodawania aplikacji usługi Office 365 do urządzeń z systemem Windows 10, zobacz [Przypisywanie aplikacji usługi Office 365 ProPlus 2016 do urządzeń z systemem Windows 10 przy użyciu usługi Microsoft Intune](apps-add-office365.md).
- Aby dowiedzieć się więcej o dołączaniu i wykluczaniu przypisań aplikacji względem grup użytkowników, zobacz [Dołączanie i wykluczanie przypisań aplikacji](apps-inc-exl-assignments.md).
