---
title: "Jak przypisywać aplikacje do grup w usłudze Microsoft Intune"
titlesuffix: 
description: "Po dodaniu aplikacji do usługi Microsoft Intune należy przypisać ją do grup użytkowników lub urządzeń."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/08/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: eba329be463fbf0593638bd4cf41c404a17f9cc0
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-assign-apps-to-groups-with-microsoft-intune"></a>Jak przypisywać aplikacje do grup w usłudze Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Po dodaniu aplikacji do usługi Microsoft Intune należy ją przypisać użytkownikom i urządzeniom.

Aplikacje można przypisać do urządzeń niezależnie od tego, czy są zarządzane przez usługę Intune. Poniższa tabela pomoże zapoznać się z różnymi opcjami przypisywania aplikacji użytkownikom i urządzeniom:

||||
|-|-|-|-|
|&nbsp;|Urządzenia zarejestrowane w usłudze Intune|Urządzenia niezarejestrowane w usłudze Intune|
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
> Obecnie można przypisać aplikacje iOS i Android (zarówno biznesowe, jak i zakupione w sklepie) do urządzeń, które nie są zarejestrowane w usłudze Intune.<br></br><br></br>
> Aby otrzymywać aktualizacje aplikacji na urządzeniach, które nie są zarejestrowane w usłudze Intune, użytkownicy urządzeń muszą przejść do portalu swojej firmy i ręcznie zainstalować aktualizacje aplikacji.

## <a name="how-to-assign-an-app"></a>Jak przypisać aplikację

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie + zarządzanie**.
3. W bloku **Intune** wybierz pozycję **Aplikacje mobilne**.
1. W obciążeniu **Aplikacje mobilne** wybierz pozycję **Aplikacje** w sekcji **Zarządzaj**.
2. W bloku listy aplikacji kliknij aplikację, którą chcesz przypisać.
3. W bloku **Omówienie** specyficznym dla aplikacji wybierz pozycję **Przypisania** w sekcji **Zarządzaj**.
4. Wybierz pozycję **Dodaj grupę**, aby wyświetlić blok **Dodawanie grupy** powiązany z aplikacją.
5. Dla określonej aplikacji wybierz **typ przypisania** z następujących:
    - **Dostępne dla zarejestrowanych urządzeń** — użytkownicy instalują aplikację z witryny internetowej lub aplikacji Portal firmy.
    - **Dostępne z rejestracją lub bez** — przypisz tę aplikację do grup użytkowników, których urządzenia nie są zarejestrowane w usłudze Intune. Należy pamiętać, że typ **Aplikacja programu Android for Work** nie obsługuje tej opcji. 
    - **Wymagane** — aplikacja jest instalowana na urządzeniach w wybranych grupach.
    - **Odinstaluj** — aplikacja jest odinstalowywana z urządzeń w wybranych grupach.

    > [!NOTE]
    > **Tylko dla aplikacji systemu iOS** — jeśli utworzono profil sieci VPN systemu iOS zawierający ustawienia sieci VPN dla aplikacji, można go wybrać w obszarze **Sieć VPN**. Gdy aplikacja jest uruchomiona, połączenie sieci VPN jest otwarte. Aby uzyskać więcej informacji, zobacz temat [Ustawienia sieci VPN dla urządzeń z systemem iOS](vpn-settings-ios.md).

6. Wybierz pozycję **Uwzględnione grupy**, aby wybrać grupy użytkowników, na które będzie mieć wpływ to przypisanie aplikacji.
7. Po wybraniu co najmniej jednej grupy do uwzględnienia kliknij pozycję **Wybierz**.
8. Kliknij przycisk **OK** w bloku **Przypisanie**, aby ukończyć wybieranie uwzględnionych grup.
9. Kliknij pozycję **Wykluczenie grup**, jeśli chcesz wykluczyć wszystkie grupy użytkowników z objęcia wpływem tego przypisania aplikacji.
10. Jeśli chcesz wykluczyć wszystkie grupy, kliknij pozycję **Wybierz** w bloku **Wybierz grupy**.
11. Kliknij przycisk **OK** w bloku **Dodaj grupę**.
12. Kliknij pozycję **Zapisz** w bloku **Przypisania** aplikacji, aby zapisać swoje przypisania.

Aplikacja jest teraz przypisana do wybranych grup. Aby uzyskać więcej informacji o dołączaniu i wykluczaniu przypisań aplikacji, zobacz [Dołączanie i wykluczanie przypisań aplikacji](apps-inc-exl-assignments.md).

## <a name="how-conflicts-between-app-intents-are-resolved"></a>Jak są rozwiązywane konflikty intencji aplikacji

Czasami ta sama aplikacja zostaje przypisana do wielu grup, ale z różnymi intencjami. W poniższej tabeli przedstawiono wynikowe intencje w takich przypadkach.

||||
|-|-|-|
|Intencja grupy 1|Intencja grupy 2|Intencja wynikowa|
|Użytkownik, wymagane|Użytkownik, dostępne|Wymagane i dostępne|
|Użytkownik, wymagane|Użytkownik, niedostępne|Wymagane|
|Użytkownik, wymagane|Użytkownik, odinstalowywanie|Wymagane|
|Użytkownik, dostępne|Użytkownik, niedostępne|Niedostępny|
|Użytkownik, dostępne|Użytkownik, odinstalowywanie|Odinstalowanie|
|Użytkownik, niedostępne|Użytkownik, odinstalowywanie|Odinstalowanie
|Użytkownik, wymagane|Urządzenie, wymagane|Oba elementy istnieją, brama traktuje jako wymagane
|Użytkownik, wymagane|Urządzenie, odinstalowywanie|Oba elementy istnieją, brama rozstrzyga jako wymagane
|Użytkownik, dostępne|Urządzenie, wymagane|Oba elementy istnieją, brama rozstrzyga jako wymagane (wymagane i dostępne)
|Użytkownik, dostępne|Urządzenie, odinstalowywanie|Oba elementy istnieją, brama rozstrzyga jako dostępne.<br>Aplikacja jest wyświetlana w Portalu firmy.<br>Jeśli aplikacja jest już zainstalowana (jako aplikacja wymagana z wcześniejszą intencją), wówczas ta aplikacja zostaje odinstalowana.<br>Jeśli jednak użytkownik kliknie w Portalu firmy polecenie instalacji, aplikacja zostanie zainstalowana, a intencja odinstalowania nie zostanie uznana.|
|Użytkownik, niedostępne|Urządzenie, wymagane|Wymagane|
|Użytkownik, niedostępne|Urządzenie, odinstalowywanie|Odinstalowanie|
|Użytkownik, odinstalowywanie|Urządzenie, wymagane|Oba elementy istnieją, brama rozstrzyga jako wymagane|
|Użytkownik, odinstalowywanie|Urządzenie, odinstalowywanie|Oba elementy istnieją, brama rozstrzyga jako odinstalowywanie|
|Urządzenie, wymagane|Urządzenie, odinstalowywanie|Wymagane|
|Użytkownik, wymagane i dostępne|Użytkownik, dostępne|Wymagane i dostępne|
|Użytkownik, wymagane i dostępne|Użytkownik, odinstalowywanie|Wymagane i dostępne|
|Użytkownik, wymagane i dostępne|Użytkownik, niedostępne|Wymagane i dostępne|
|Użytkownik, wymagane i dostępne|Urządzenie, wymagane|Oba elementy istnieją, wymagane i dostępne
|Użytkownik, wymagane i dostępne|Urządzenie, niedostępne|Wymagane i dostępne|
|Użytkownik, wymagane i dostępne|Urządzenie, odinstalowywanie|Oba elementy istnieją, brama rozstrzyga jako wymagane. Wymagane i dostępne
|Użytkownik, niedostępne|Urządzenie, niedostępne|Niedostępny|
|Użytkownik, dostępne|Urządzenie, niedostępne|Dostępne|
|Użytkownik, wymagane|Urządzenie, niedostępne|Wymagane|
|Użytkownik, dostępne bez rejestracji|Użytkownik, wymagane i dostępne|Wymagane i dostępne
|Użytkownik, dostępne bez rejestracji|Użytkownik, wymagane|Wymagane
|Użytkownik, dostępne bez rejestracji|Użytkownik, niedostępne|Niedostępny
|Użytkownik, dostępne bez rejestracji|Użytkownik, dostępne|Dostępne|
|Użytkownik, dostępne bez rejestracji|Urządzenie, wymagane|Wymagane i dostępne bez rejestracji|
|Użytkownik, dostępne bez rejestracji|Urządzenie, niedostępne|Dostępne bez rejestracji|
|Użytkownik, dostępne bez rejestracji|Urządzenie, odinstalowywanie|Odinstalowywanie i dostępne bez rejestracji.<br>Jeśli użytkownik nie zainstalował aplikacji z Portalu firmy, odinstalowywanie zostanie uznane.<br>Jeśli użytkownik instaluje aplikację z Portalu firmy, instalowanie ma priorytet nad odinstalowywaniem.|

>[!NOTE]
>W przypadku dodania zarządzanych aplikacji ze sklepu iOS do usługi Microsoft Intune i przypisania ich jako **Wymagane** są one automatycznie tworzone z intencjami **Wymagane** i **Dostępne**.

## <a name="next-steps"></a>Następne kroki

Informacje przydatne do monitorowania przypisań aplikacji znajdują się w artykule [How to monitor apps](apps-monitor.md) (Jak monitorować aplikacje).
