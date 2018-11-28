---
title: Przypisywanie aplikacji do grup w usłudze Microsoft Intune
titlesuffix: ''
description: Dowiedz się, jak przypisać aplikację usługi Intune do grup użytkowników lub urządzeń.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/09/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: a9afde942f2784cb2fb42b13d11a127e3c9811a1
ms.sourcegitcommit: 3903f20cb5686532ccd8c36aa43c5150cee7cca2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2018
ms.locfileid: "52267258"
---
# <a name="assign-apps-to-groups-with-microsoft-intune"></a>Przypisywanie aplikacji do grup przy użyciu usługi Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Po [dodaniu aplikacji](apps-add.md) do usługi Microsoft Intune należy ją przypisać do użytkowników i urządzeń. Ważne jest, aby pamiętać, że aplikację można przypisać do urządzenia, bez względu na to, czy jest ono zarządzane przez usługę Intune. 

Poniższa tabela zawiera listę różnych opcji przypisywania aplikacji do użytkowników i urządzeń:

||||
|-|-|-|-|
|&nbsp;|**Urządzenia zarejestrowane w usłudze Intune**|**Urządzenia niezarejestrowane w usłudze Intune**|
|Przypisz do użytkowników|Tak|Tak|
|Przypisz do urządzeń|Tak|Nie|
|Przypisz opakowane aplikacje lub aplikacje zawierające zestaw Intune SDK (dla zasad ochrony aplikacji)|Tak|Tak|
|Przypisz aplikacje jako dostępne|Tak|Tak|
|Przypisz aplikacje jako wymagane|Tak|Nie|
|Odinstaluj aplikacje|Tak|Nie|
|Otrzymuj aktualizacje aplikacji z usługi Intune|Tak|Nie|
|Użytkownicy końcowi instalują dostępne aplikacje z aplikacji Portal firmy|Tak|Nie|
|Użytkownicy końcowi instalują dostępne aplikacje z internetowego Portalu firmy|Tak|Tak|

> [!NOTE]
> Obecnie można przypisać aplikacje systemu iOS i Android (aplikacje biznesowe i zakupione w sklepie) do urządzeń, które nie zostały zarejestrowane w usłudze Intune.
>
> Aby otrzymywać aktualizacje aplikacji na urządzeniach, które nie zostały zarejestrowane w usłudze Intune, użytkownicy urządzeń muszą przejść do Portalu firmy swojej organizacji i ręcznie zainstalować aktualizacje aplikacji.

## <a name="to-assign-an-app"></a>Aby przypisać aplikację

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W menu **Intune** wybierz opcję **Aplikacje klienckie**.
4. W sekcji **Zarządzaj** menu wybierz pozycję **Aplikacje**.
5. W okienku **Aplikacje** wybierz aplikację, którą chcesz przypisać.
6. W sekcji **Zarządzaj** menu wybierz pozycję **Przypisania**.
7. Wybierz pozycję **Dodaj grupę**, aby otworzyć okienko **Dodawanie grupy** powiązane z aplikacją.
8. Dla określonej aplikacji wybierz **typ przypisania**:
   - **Dostępne dla zarejestrowanych urządzeń**: przypisz aplikację do grupy użytkowników, którzy mogą zainstalować aplikację z witryny internetowej lub aplikacji Portal firmy.
   - **Dostępne z rejestracją lub bez**: przypisz tę aplikację do grup użytkowników, których urządzenia nie są zarejestrowane w usłudze Intune. Aplikacje z zarządzanego sklepu Google Play nie obsługują tej opcji. 
   - **Wymagane**: aplikacja jest instalowana na urządzeniach w wybranych grupach.
   - **Odinstaluj**: aplikacja jest odinstalowywana z urządzeń w wybranych grupach.

     > [!NOTE]
     > **Tylko dla aplikacji systemu iOS**: jeśli utworzono profil sieci VPN systemu iOS zawierający ustawienia sieci VPN dla aplikacji, można wybrać ten profil w obszarze **Sieć VPN**. Gdy aplikacja jest uruchomiona, połączenie sieci VPN jest otwarte. Aby uzyskać więcej informacji, zobacz temat [Ustawienia sieci VPN dla urządzeń z systemem iOS](vpn-settings-ios.md).
     >
     > **Tylko dla aplikacji systemu Android**: jeśli aplikacja systemu Android jest wdrażana przy użyciu opcji **Dostępne z rejestracją lub bez niej**, stan raportowania będzie dostępny tylko na zarejestrowanych urządzeniach.

9. Aby wybrać grupy użytkowników, na które ma wpływ to przypisanie aplikacji, wybierz pozycję **Uwzględnione grupy**.
10. Po wybraniu co najmniej jednej grupy do dołączenia wybierz pozycję **Wybierz**.
11. W okienku **Przypisywanie** wybierz przycisk **OK**, aby ukończyć wybieranie uwzględnionych grup.
12. Jeśli chcesz wykluczyć wszystkie grupy użytkowników z objęcia wpływem tego przypisania aplikacji, wybierz pozycję **Wykluczenie grup**.
13. Jeśli chcesz wykluczyć wszystkie grupy, w obszarze **Wybieranie grup** wybierz pozycję **Wybierz**.
14. W okienku **Dodawanie grupy** wybierz przycisk **OK**.
15. W okienku **Przypisania** aplikacji wybierz pozycję **Zapisz**.

Aplikacja jest teraz przypisana do wybranych grup. Aby uzyskać więcej informacji o dołączaniu i wykluczaniu przypisań aplikacji, zobacz [Dołączanie i wykluczanie przypisań aplikacji](apps-inc-exl-assignments.md).

## <a name="how-conflicts-between-app-intents-are-resolved"></a>Jak są rozwiązywane konflikty intencji aplikacji

Czasami ta sama aplikacja zostaje przypisana do wielu grup, ale z różnymi intencjami. Informacje przedstawione w poniższej tabeli pomogą w zrozumieniu wynikowej intencji:

||||
|-|-|-|
|**Intencja grupy 1**|**Intencja grupy 2**|**Intencja wynikowa**|
|Użytkownik, wymagane|Użytkownik, dostępne|Wymagane i dostępne|
|Użytkownik, wymagane|Użytkownik, niedostępne|Wymagane|
|Użytkownik, wymagane|Użytkownik, odinstalowywanie|Wymagane|
|Użytkownik, dostępne|Użytkownik, niedostępne|Niedostępny|
|Użytkownik, dostępne|Użytkownik, odinstalowywanie|Odinstalowanie|
|Użytkownik, niedostępne|Użytkownik, odinstalowywanie|Odinstalowanie
|Użytkownik, wymagane|Urządzenie, wymagane|Oba elementy istnieją, usługa Intune traktuje jako wymagane
|Użytkownik, wymagane|Urządzenie, odinstalowywanie|Oba elementy istnieją, usługa Intune rozstrzyga jako wymagane
|Użytkownik, dostępne|Urządzenie, wymagane|Oba elementy istnieją, usługa Intune rozstrzyga jako wymagane (wymagane i dostępne)
|Użytkownik, dostępne|Urządzenie, odinstalowywanie|Oba elementy istnieją, usługa Intune rozstrzyga jako dostępne<br><br>Aplikacja jest wyświetlana w Portalu firmy.<br><br>Jeśli aplikacja została już zainstalowana (jako aplikacja wymagana z wcześniejszą intencją), ta aplikacja zostaje odinstalowana.<br><br>Jeśli użytkownik wybierze pozycję **Zainstaluj z Portalu firmy**, aplikacja zostanie zainstalowana, a intencja odinstalowania nie zostanie uznana.|
|Użytkownik, niedostępne|Urządzenie, wymagane|Wymagane|
|Użytkownik, niedostępne|Urządzenie, odinstalowywanie|Odinstalowanie|
|Użytkownik, odinstalowywanie|Urządzenie, wymagane|Oba elementy istnieją, usługa Intune rozstrzyga jako wymagane|
|Użytkownik, odinstalowywanie|Urządzenie, odinstalowywanie|Oba elementy istnieją, usługa Intune rozstrzyga jako odinstalowywanie|
|Urządzenie, wymagane|Urządzenie, odinstalowywanie|Wymagane|
|Użytkownik, wymagane i dostępne|Użytkownik, dostępne|Wymagane i dostępne|
|Użytkownik, wymagane i dostępne|Użytkownik, odinstalowywanie|Wymagane i dostępne|
|Użytkownik, wymagane i dostępne|Użytkownik, niedostępne|Wymagane i dostępne|
|Użytkownik, wymagane i dostępne|Urządzenie, wymagane|Oba elementy istnieją, wymagane i dostępne
|Użytkownik, wymagane i dostępne|Urządzenie, niedostępne|Wymagane i dostępne|
|Użytkownik, wymagane i dostępne|Urządzenie, odinstalowywanie|Oba elementy istnieją, usługa Intune rozstrzyga jako wymagane (wymagane i dostępne)
|Użytkownik, niedostępne|Urządzenie, niedostępne|Niedostępny|
|Użytkownik, dostępne|Urządzenie, niedostępne|Dostępne|
|Użytkownik, wymagane|Urządzenie, niedostępne|Wymagane|
|Użytkownik, dostępne bez rejestracji|Użytkownik, wymagane i dostępne|Wymagane i dostępne
|Użytkownik, dostępne bez rejestracji|Użytkownik, wymagane|Wymagane
|Użytkownik, dostępne bez rejestracji|Użytkownik, niedostępne|Niedostępny
|Użytkownik, dostępne bez rejestracji|Użytkownik, dostępne|Dostępne|
|Użytkownik, dostępne bez rejestracji|Urządzenie, wymagane|Wymagane i dostępne bez rejestracji|
|Użytkownik, dostępne bez rejestracji|Urządzenie, niedostępne|Dostępne bez rejestracji|
|Użytkownik, dostępne bez rejestracji|Urządzenie, odinstalowywanie|Odinstalowywanie i dostępne bez rejestracji.<br><br>Jeśli użytkownik nie zainstalował aplikacji z Portalu firmy, odinstalowywanie zostanie uznane.<br><br>Jeśli użytkownik instaluje aplikację z Portalu firmy, instalowanie ma priorytet nad odinstalowywaniem.|

> [!NOTE]
> W przypadku dodania zarządzanych aplikacji ze sklepu iOS do usługi Microsoft Intune i przypisania ich jako **Wymagane** są one automatycznie tworzone z intencjami **Wymagane** i **Dostępne**.<br><br>
> Aplikacje ze sklepu dla systemu iOS (nie aplikacje zakupione w ramach programu VPP dla systemu iOS), które mają określony cel i intencję, będą wymuszane na urządzeniach w chwili zameldowania urządzenia i będą także widoczne w aplikacji Portal firmy.

## <a name="next-steps"></a>Następne kroki

Aby dowiedzieć się więcej na temat monitorowania przypisań aplikacji, zobacz [Jak monitorować aplikacje](apps-monitor.md).
