---
title: "Jak przypisywać aplikacje do grup w usłudze Microsoft Intune"
titlesuffix: 
description: "Po dodaniu aplikacji do usługi Microsoft Intune należy przypisać ją do grup użytkowników lub urządzeń."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 78a9e9f4af41cdb97efd017eec56e676eda82856
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/02/2018
---
# <a name="how-to-assign-apps-to-groups-with-microsoft-intune"></a>Jak przypisywać aplikacje do grup w usłudze Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Po dodaniu aplikacji do usługi Intune należy ją przypisać użytkownikom i urządzeniom.

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
2. Wybierz pozycję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W bloku **Intune** wybierz pozycję **Aplikacje mobilne**.
1. W obciążeniu **Aplikacje mobilne** wybierz kolejno pozycje **Zarządzaj** > **Aplikacje**.
2. W bloku listy aplikacji kliknij aplikację, którą chcesz przypisać.
3. W bloku **Przegląd** wybierz pozycję **Zarządzaj** > **Przypisania**.
4. Wybierz pozycję **Dodaj grupę**, a następnie w bloku **Dodawanie grupy** wybierz grupy usługi Azure AD, które mają zostać uwzględnione w przypisywaniu aplikacji lub z niego wykluczone.
5. Dla każdej wybranej aplikacji wybierz **typ przypisania** dla aplikacji:
    - **Dostępne dla zarejestrowanych urządzeń** — użytkownicy instalują aplikację z witryny internetowej lub aplikacji Portal firmy.
    - **Dostępne z rejestracją lub bez** — przypisz tę aplikację do grup użytkowników, których urządzenia nie są zarejestrowane w usłudze Intune.
    - **Wymagane** — aplikacja jest instalowana na urządzeniach w wybranych grupach.
    - **Odinstaluj** — aplikacja jest odinstalowywana z urządzeń w wybranych grupach.
6. **Tylko dla aplikacji systemu iOS** — jeśli utworzono profil sieci VPN systemu iOS zawierający ustawienia sieci VPN dla aplikacji, można go wybrać w obszarze **Sieć VPN**. Gdy aplikacja jest uruchomiona, połączenie sieci VPN jest otwarte. Aby uzyskać więcej informacji, zobacz temat [Ustawienia sieci VPN dla urządzeń z systemem iOS](vpn-settings-ios.md).
6. Gdy wszystko będzie gotowe, wybierz przycisk **OK**, a następnie wybierz przycisk **Zapisz**.

Aplikacja jest teraz przypisana do wybranych grup.

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
>W przypadku dodania zarządzanych aplikacji ze sklepu iOS do usługi Intune i przypisania ich jako Wymagane są one automatycznie tworzone z intencjami Wymagane i Dostępne.

## <a name="next-steps"></a>Następne kroki

Informacje przydatne do monitorowania przypisań aplikacji znajdują się w artykule [How to monitor apps](apps-monitor.md) (Jak monitorować aplikacje).
