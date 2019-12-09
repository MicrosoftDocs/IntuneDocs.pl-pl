---
title: Dodawanie przeglądarki Microsoft Edge na urządzeniach z systemem macOS przy użyciu usługi Microsoft Intune
titleSuffix: ''
description: Dowiedz się więcej na temat dodawania przeglądarki Microsoft Edge na urządzeniach z systemem macOS przy użyciu usługi Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: kellieei
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: c31dd652022ae0d394ab2229a0c25b362ad8574d
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/27/2019
ms.locfileid: "74563586"
---
# <a name="add-microsoft-edge-to-macos-devices-using-microsoft-intune"></a>Dodawanie przeglądarki Microsoft Edge na urządzeniach z systemem macOS przy użyciu usługi Microsoft Intune

Aby móc wdrażać, konfigurować, monitorować lub zabezpieczać aplikacje, trzeba je najpierw dodać do usługi Intune. Jednym z dostępnych [typów aplikacji](~/apps/apps-add.md#app-types-in-microsoft-intune) jest przeglądarka Microsoft Edge *w wersji 77 lub nowszej*. Po wybraniu tego typu aplikacji w usłudze Intune możesz przypisać i zainstalować przeglądarkę Microsoft Edge *w wersji 77 lub nowszej* na zarządzanych urządzeniach z systemem macOS. Ten typ aplikacji ułatwia przypisanie przeglądarki Microsoft Edge do urządzeń z systemem macOS bez konieczności używania narzędzia opakowującego aplikacje systemu macOS. Aby pomóc w zachowaniu bezpieczeństwa i aktualności aplikacji, dołączamy do nich program Microsoft AutoUpdate (MAU).

> [!IMPORTANT]
> Ten typ aplikacji znajduje się w **publicznej wersji zapoznawczej** i oferuje kanały deweloperskie i wersji beta dla systemu macOS. Wdrożenie jest tylko w języku angielskim (EN), jednak użytkownicy końcowi mogą zmienić język wyświetlania w przeglądarce w obszarze **Ustawienia** > **Języki**. 

> [!NOTE]
> Przeglądarka Microsoft Edge *w wersji 77 lub nowszej* jest również dostępna dla systemu Windows 10.

## <a name="prerequisites"></a>Wymagania wstępne
- Aby móc zainstalować przeglądarkę Microsoft Edge na urządzeniu, musi na nim być zainstalowany system macOS w wersji 10.12 lub nowszej.

## <a name="add-microsoft-edge-to-intune"></a>Dodawanie przeglądarki Microsoft Edge do usługi Intune
Do usługi Intune można dodać przeglądarkę Microsoft Edge w wersji 77 lub nowszej, wykonując następujące czynności:

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz kolejno pozycje **Aplikacje** > **Wszystkie aplikacje** > **Dodaj**.
3. Na liście **Typ aplikacji** w pozycji **Microsoft Edge w wersji 77 lub nowszej** wybierz opcję **macOS**.

## <a name="configure-app-information"></a>Konfigurowanie informacji o aplikacji
W tym kroku podajesz informacje o tym wdrożeniu aplikacji. Te informacje pomagają zidentyfikować aplikację w usłudze Intune i ułatwiają użytkownikom odnalezienie aplikacji w portalu firmy.

1. Kliknij opcję **Informacje o aplikacji**, aby wyświetlić okienko **Informacje o aplikacji**.
2. W okienku **Informacje o aplikacji** należy podać informacje o tym wdrożeniu aplikacji. Te informacje pomagają zidentyfikować aplikację w usłudze Intune i ułatwiają użytkownikom odnalezienie aplikacji w portalu firmy.
    - **Nazwa**: Wprowadź nazwę aplikacji wyświetlaną w Portalu firmy. Upewnij się, że wszystkie nazwy są unikatowe. Jeśli dana nazwa aplikacji występuje dwa razy, użytkownicy Portalu firmy będą widzieć tylko jedną z aplikacji o tej nazwie.
    - **Opis**: Wprowadź opis aplikacji. Przykładowo w opisie możesz wymienić docelowych użytkowników.
    - **Wydawca**: w roli wydawcy występuje firma Microsoft.
    - **Kategoria**: opcjonalnie wybierz co najmniej jedną wbudowaną lub utworzoną przez siebie kategorię aplikacji. To ustawienie ułatwi użytkownikom znajdowanie aplikacji podczas przeglądania portalu firmy.
    - **Wyświetl jako polecaną aplikację w Portalu firmy**: wybierz tę opcję, aby wyświetlić aplikację w dobrze widocznym miejscu na stronie głównej portalu firmy podczas przeglądania aplikacji przez użytkowników.
    - **Adres URL informacji**: Opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o tej aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Adres URL zasad ochrony prywatności**: Opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje dotyczące zasad ochrony prywatności w tej aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Deweloper**: w roli dewelopera występuje firma Microsoft.
    - **Właściciel**: w roli właściciela występuje firma Microsoft.
    - **Uwagi**: opcjonalnie wprowadź wszelkie uwagi, które chcesz skojarzyć z tą aplikacją.
3. Wybierz przycisk **OK**.

## <a name="configure-microsoft-edge-settings"></a>Konfigurowanie ustawień programu Microsoft Edge
W tym kroku skonfigurujesz opcje instalacji aplikacji.

1. W okienku **Dodawanie aplikacji** wybierz pozycję **Ustawienia aplikacji**.
2. W okienku **Ustawienia aplikacji** jest automatycznie wybierany kanał **Beta** i tego ustawienia nie można zmienić.
    - Kanał **Beta** to najbardziej stabilne środowisko przeglądarki Microsoft Edge w wersji zapoznawczej oraz najlepszy wybór w przypadku pełnego pilotażu w organizacji. Ważne aktualizacje są publikowane co sześć tygodni.

    > [!NOTE]
    > Logo przeglądarki Microsoft Edge będzie wyświetlane razem z nazwą aplikacji podczas przeglądania portalu firmy.
3.  Wybierz przycisk **OK**.

## <a name="select-scope-tags-optional"></a>Wybieranie tagów zakresu (opcjonalnie)
Za pomocą tagów zakresu można określić, kto będzie mógł wyświetlać informacje o aplikacji klienckiej w usłudze Intune. Więcej informacji o tagach zakresu zawiera artykuł Używanie kontroli dostępu opartej na rolach i tagów zakresu w rozproszonej infrastrukturze informatycznej.
1.  Wybierz pozycję **Zakres (tagi)**  > **Dodaj**.
2.  Użyj pola **Wybierz**, aby wyszukać tagi zakresu.
3.  Zaznacz pole wyboru obok tagów zakresu, które chcesz przypisać do aplikacji.
4.  Kliknij kolejno pozycje **Wybierz** > **OK**.

## <a name="add-the-app"></a>Dodawanie aplikacji
Po zakończeniu konfigurowania wybierz opcję **Dodaj** w okienku **Aplikacja**. 

Utworzona aplikacja będzie wyświetlana na liście aplikacji, z której można ją przypisać do wybranych grup. 

> [!NOTE]
> Obecnie firma Apple nie udostępnia możliwości odinstalowania przeglądarki Microsoft Edge z urządzenia z systemem macOS za pomocą usługi Intune.

## <a name="next-steps"></a>Następne kroki
- Aby dowiedzieć się, jak skonfigurować program Microsoft Edge na urządzeniach z systemem macOS, zobacz [Configure Microsoft Edge on macOS devices (Konfigurowanie programu Microsoft Edge na urządzeniach z systemem macOS)](https://docs.microsoft.com/deployedge/configure-microsoft-edge-on-mac).
- Aby dowiedzieć się więcej o dołączaniu i wykluczaniu przypisań aplikacji względem grup użytkowników, zobacz [Dołączanie i wykluczanie przypisań aplikacji](~/apps/apps-inc-exl-assignments.md).
- [Przypisywanie aplikacji do grup](~/apps/apps-deploy.md)

