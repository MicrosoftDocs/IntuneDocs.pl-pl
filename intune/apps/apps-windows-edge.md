---
title: Dodawanie przeglądarki Microsoft Edge dla systemu Windows 10 do usługi Microsoft Intune
titleSuffix: ''
description: Dowiedz się więcej na temat dodawania przeglądarki Microsoft Edge dla systemu Windows do usługi Microsoft Intune.
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
ms.openlocfilehash: b4839340ba1f3bad6f28a1120d882d0f600b1d44
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/27/2019
ms.locfileid: "74563563"
---
# <a name="add-microsoft-edge-for-windows-10-to-microsoft-intune"></a>Dodawanie przeglądarki Microsoft Edge dla systemu Windows 10 do usługi Microsoft Intune

Aby móc wdrażać, konfigurować, monitorować lub zabezpieczać aplikacje, trzeba je najpierw dodać do usługi Intune. Jednym z dostępnych [typów aplikacji](~/apps/apps-add.md#app-types-in-microsoft-intune) jest przeglądarka Microsoft Edge *w wersji 77 lub nowszej*. Po wybraniu tego typu aplikacji w usłudze Intune możesz przypisać i zainstalować przeglądarkę Microsoft Edge *w wersji 77 lub nowszej* na zarządzanych urządzeniach z systemem Windows 10.

> [!IMPORTANT]
> Ten typ aplikacji znajduje się w **publicznej wersji zapoznawczej** i oferuje kanały deweloperskie i wersji beta dla systemu Windows 10. Wdrożenie jest tylko w języku angielskim (EN), jednak użytkownicy końcowi mogą zmienić język wyświetlania w przeglądarce w obszarze **Ustawienia** > **Języki**. Microsoft Edge jest aplikacją systemu Win32 instalowaną w kontekście systemu oraz na takich samych architekturach (aplikacja x86 w systemie operacyjnym x86, a aplikacja x64 w systemie operacyjnym x64). Usługa Intune wykryje wszystkie istniejące wcześniej instalacje aplikacji Microsoft Edge. Jeśli została ona zainstalowana w kontekście użytkownika, instalacja systemu spowoduje jej nadpisanie. Jeśli została ona zainstalowana w kontekście systemu, będzie zgłaszany sukces instalacji. Ponadto automatyczne aktualizacje przeglądarki Microsoft Edge są domyślnie **włączone**, a przeglądarki Microsoft Edge nie można odinstalować.

> [!NOTE]
> Przeglądarka Microsoft Edge *w wersji 77 lub nowszej* jest również dostępna dla systemu macOS.
> 
> Nie można użyć wbudowanego wdrożenia aplikacji przeglądarki Microsoft Edge w przypadku komputerów dołączanych do miejsca pracy. Wbudowane wdrożenie aplikacji wymaga rozszerzenia zarządzania usługi Intune, które istnieje tylko w przypadku urządzeń dołączonych do usługi AAD. Nadal można wdrożyć przeglądarkę Microsoft Edge *w wersji 77 lub nowszej* przy użyciu pliku *.msi* przekazanego do **aplikacji**. Zobacz [Dodawanie aplikacji biznesowej dla systemu Windows do usługi Microsoft Intune](~/apps/lob-apps-windows.md).

## <a name="prerequisites"></a>Wymagania wstępne
- Wymagany jest system Windows 10 RS2 lub nowszy.
- Wszystkie wstępnie zainstalowane wersje przeglądarki Microsoft Edge *w wersji 77 lub nowszej* dla kanałów **dewelopera** i **wersji beta** w kontekście użytkownika zostaną zastąpione przeglądarką Microsoft Edge instalowaną w kontekście systemu.

## <a name="configure-the-app-in-intune"></a>Konfigurowanie aplikacji w usłudze Intune
Do usługi Intune można dodać przeglądarkę Microsoft Edge w wersji 77 lub nowszej, wykonując następujące czynności:

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz kolejno pozycje **Aplikacje** > **Wszystkie aplikacje** > **Dodaj**.
3. Na liście **Typ aplikacji** w pozycji **Microsoft Edge, wersja 77 lub nowsza** wybierz opcję **Windows 10**.

## <a name="configure-app-information"></a>Konfigurowanie informacji o aplikacji
W tym kroku podajesz informacje o tym wdrożeniu aplikacji. Te informacje pomagają zidentyfikować aplikację w usłudze Intune i ułatwiają użytkownikom odnalezienie aplikacji w portalu firmy.

1. Kliknij **Informacje o aplikacji**, aby wyświetlić okienko **Informacje o aplikacji**.
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

## <a name="configure-app-settings"></a>Konfigurowanie ustawień aplikacji
W tym kroku skonfigurujesz opcje instalacji aplikacji.

1. W okienku **Dodaj aplikację** wybierz pozycję **Ustawienia aplikacji**.
2. W okienku **Ustawienia aplikacji** wybierz opcję **Beta** lub **Deweloper** z listy **Kanał**, aby określić, z którego kanału przeglądarki Microsoft Edge będziesz wdrażać aplikację.
    - Kanał **Beta** to najbardziej stabilne środowisko przeglądarki Microsoft Edge w wersji zapoznawczej oraz najlepszy wybór w przypadku pełnego pilotażu w organizacji. W przypadku najważniejszych aktualizacji przeprowadzanych co sześć tygodni poszczególne wersje uwzględniają informacje i ulepszenia z kanału deweloperów.
    - Kanał **Deweloper** jest przygotowany do przesyłania informacji zwrotnych z przedsiębiorstwa w zakresie systemu Windows, Windows Server oraz macOS. Jest aktualizowany co tydzień i zawiera najnowsze ulepszenia i poprawki.

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
Po zakończeniu konfigurowania aplikacji kliknij opcję **Dodaj** w okienku **Aplikacja**. 

Utworzona aplikacja będzie wyświetlana na liście aplikacji, z której można ją przypisać do wybranych grup. 

> [!NOTE]
> Obecnie po cofnięciu przypisania wdrożenia przeglądarki Microsoft Edge pozostanie ono na urządzeniu.

## <a name="troubleshooting"></a>Rozwiązywanie problemów
**Microsoft Edge w wersji 77 lub nowszej dla systemu Windows 10:**<br>
Usługa Intune używa rozszerzenia zarządzania usługi Intune do pobrania i wdrożenia Instalatora przeglądarki Microsoft Edge do przypisanych urządzeń z systemem Windows 10, a następnie przekazuje ustawienia wdrożenia do Instalatora przeglądarki Microsoft Edge, który pobiera i instaluje przeglądarkę Microsoft Edge bezpośrednio z sieci CDN. Zapoznaj się z [wymaganiami wstępnymi dla rozszerzenia zarządzania usługi Intune](~/apps/intune-management-extension.md#prerequisites) oraz najlepszymi rozwiązaniami dotyczącymi uzyskiwania dostępu do usług aktualizacji platformy Azure oraz sieci CDN, aby upewnić się, że Twoja konfiguracja sieci zezwala urządzeniom z systemem Windows 10 na dostęp do tych lokalizacji. Ponadto, aby zezwolić na dostęp do plików instalacyjnych z sieci CDN w celu zainstalowania przeglądarki, należy zezwolić na dostęp do punktów końcowych usługi Windows Update. Aby uzyskać więcej informacji, zobacz [Zarządzanie punktami końcowymi połączenia dla systemu Windows 10 w wersji 1809 — Windows Update](https://docs.microsoft.com/windows/privacy/manage-windows-1809-endpoints#windows-update) i [Punkty końcowe sieci dla usługi Microsoft Intune](~/fundamentals/intune-endpoints.md).

## <a name="next-steps"></a>Następne kroki
- [Przypisywanie aplikacji do grup](~/apps/apps-deploy.md)
