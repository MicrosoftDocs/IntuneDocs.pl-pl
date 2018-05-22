---
title: Instalowanie usługi Office 365 na urządzeniach z systemem macOS przy użyciu usługi Microsoft Intune
titlesuffix: ''
description: Dowiedz się, jak przy użyciu usługi Microsoft Intune możesz zainstalować aplikacje usługi Office 365 na urządzeniach z systemem macOS.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2372332a-7e3a-4a9c-91a9-86654e0fabe2
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 78158afeb9c12e8056f42066be78c37f962b4462
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
---
# <a name="assign-office-365-to-macos-devices-with-microsoft-intune"></a>Przypisywanie usługi Office 365 do urządzeń z systemem macOS za pomocą usługi Microsoft Intune

Typ *Aplikacja ze sklepu* ułatwia przypisywanie aplikacji usługi Office 365 do urządzeń z systemem macOS. Korzystając z tego typu aplikacji, można instalować programy Word, Excel, PowerPoint, Outlook i OneNote. Aby pomóc w zachowaniu bezpieczeństwa i aktualności aplikacji, dołączamy do nich program Microsoft AutoUpdate (MAU). Wybrane aplikacje są wyświetlane jako jedna aplikacja na liście aplikacji w konsoli usługi Intune.


## <a name="before-you-start"></a>Przed rozpoczęciem

Przed rozpoczęciem dodawania usługi Office 365 na urządzeniach z systemem macOS należy zrozumieć następujące informacje:

- Na urządzeniach, na których aplikacje są wdrażane, musi być zainstalowany system macOS w wersji 10.10 lub nowszej.
- Usługa Intune obsługuje dodawanie tylko aplikacji pakietu Office zawartych w pakiecie Office 2016 dla komputerów Mac.
- Jeśli jakiekolwiek aplikacje pakietu Office są otwarte, gdy usługa Intune instaluje pakiet aplikacji, użytkownicy mogą utracić dane z niezapisanych plików.

## <a name="create-and-configure-the-app-suite"></a>Tworzenie i konfigurowanie pakietu aplikacji

Dodaj usługę Office 365 z okienka **Aplikacje**.
1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Monitorowanie + zarządzanie** > **Intune**.
3. W okienku **Intune** wybierz pozycję **Aplikacje mobilne**.
4. W okienku obciążenia **Aplikacje mobilne** w obszarze **Zarządzaj** wybierz pozycję **Aplikacje**. 
5. Wybierz pozycję **Dodaj**.
6. Na liście **Typ aplikacji** w grupie **Pakiet Office 365**wybierz pozycję **macOS**.
7. Aby uzyskać informacje na temat pakietu aplikacji, wybierz pozycję **Informacje o pakiecie aplikacji**.  
    Te informacje pomagają zidentyfikować pakiet aplikacji w usłudze Intune i ułatwiają użytkownikom wyszukiwanie tego pakietu w portalu firmy.
8. Wprowadź następujące informacje:
    - **Nazwa pakietu**: wprowadź nazwę pakietu aplikacji wyświetlaną w portalu firmy. Upewnij się, że wszystkie używane nazwy pakietów są unikatowe. Jeśli dana nazwa pakietu aplikacji występuje dwa razy, użytkownicy portalu firmy będą widzieć tylko jedną z aplikacji o tej nazwie.
    - **Opis pakietu**: wprowadź opis pakietu aplikacji.
    - **Wydawca**: w roli wydawcy występuje firma Microsoft.
    - **Kategoria**: wybierz co najmniej jedną wbudowaną lub utworzoną przez siebie kategorię aplikacji. To ustawienie ułatwi użytkownikom znajdowanie pakietu aplikacji podczas przeglądania portalu firmy.
    - **Wyświetl jako polecaną aplikację w Portalu firmy**: wybierz tę opcję, aby wyświetlić pakiet aplikacji na stronie głównej portalu firmy podczas przeglądania aplikacji przez użytkowników.
    - **Adres URL informacji**: opcjonalnie wprowadź adres URL witryny internetowej zawierającej informacje o tej aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Adres URL zasad ochrony prywatności**: opcjonalnie wprowadź adres URL witryny internetowej zawierającej informacje o zasadach ochrony prywatności w tej aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Deweloper**: w roli dewelopera występuje firma Microsoft.
    - **Właściciel**: w roli właściciela występuje firma Microsoft.
    - **Uwagi**: opcjonalnie wprowadź wszelkie uwagi, które chcesz skojarzyć z tą aplikacją.
    - **Logo**: logo usługi Office 365 jest wyświetlane razem z nazwą aplikacji podczas przeglądania portalu firmy.
9. Wybierz przycisk **OK**.
10. W okienku **Dodaj aplikację** wybierz pozycję **Dodaj**.  
    Pakiet zostanie wyświetlony na liście aplikacji jako pojedynczy wpis.

## <a name="configure-app-assignments"></a>Konfigurowanie przypisań aplikacji

W tym kroku skonfigurujesz przypisania pakietu aplikacji. 

1. Na liście aplikacji wybierz pakiet aplikacji**Office 365**, aby wyświetlić okienko omówienia usługi **Office 365**.
2. W okienku **Office 365** wybierz pozycję **Przypisania**.
3. Aby dodać grupę, która będzie używać pakietu aplikacji, wybierz pozycję **Dodaj grupę**.  
    Zostanie wyświetlone okienko **Dodawanie grupy**.
4. Ustaw pozycję **Typ przypisania** na wartość **Wymagane**.
5. Przypisz pakiet do wybranych grup. Aby uzyskać więcej informacji, zobacz [Przypisywanie aplikacji do grup w usłudze Microsoft Intune](apps-deploy.md).

    >[!Note]
    > Nie można odinstalować pakietu aplikacji usługi Office 365 za pomocą usługi Intune.

5. W okienku **Przypisywanie** wybierz przycisk **OK**.
6. W okienku **Dodawanie grupy** wybierz przycisk **OK**.
7. Aby zatwierdzić swoje przypisania, wybierz przycisk **Zapisz**.

## <a name="next-steps"></a>Następne kroki

- Aby uzyskać informacje na temat dodawania aplikacji usługi Office 365 do urządzeń z systemem Windows 10, zobacz [Przypisywanie aplikacji usługi Office 365 ProPlus 2016 do urządzeń z systemem Windows 10 przy użyciu usługi Microsoft Intune](apps-add-office365.md).
- Aby dowiedzieć się więcej o dołączaniu i wykluczaniu przypisań aplikacji względem grup użytkowników, zobacz [Dołączanie i wykluczanie przypisań aplikacji](apps-inc-exl-assignments.md).
