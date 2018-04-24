---
title: Przypisywanie profili urządzeń w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Przypisz zasady i profile urządzeń do użytkowników i urządzeń za pomocą witryny Azure Portal. Dowiedz się, jak wykluczyć grupy z przypisania profilu w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fa1a1b1085d196411a03a6228eefa808399397ea
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="assign-user-and-device-profiles-in-microsoft-intune"></a>Przypisywanie profili użytkowników i urządzeń w usłudze Microsoft Intune

Po utworzeniu profilu można przypisać go do grup usługi Azure Active Directory (Azure AD).

## <a name="assign-a-device-profile"></a>Przypisywanie profilu urządzenia

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi** i wyszukaj usługę **Microsoft Intune**.
2. W obszarze **Microsoft Intune** wybierz pozycję **Konfiguracja urządzeń**, a następnie **Profile**.
3. Na liście profili zaznacz profil, który chcesz przypisać, a następnie wybierz pozycję **Przypisania**.
4. Wybierz **dołączenie** lub **wykluczenie** grup, a następnie wybierz grupy.  

    ![Zrzut ekranu przedstawiający opcje dołączania grup do przypisania profilu i wykluczania grup z przypisania profilu](./media/group-include-exclude.png)

5. Wybierane grupy są grupami usługi Azure AD. Aby wybrać wiele grup, możesz nacisnąć i przytrzymać klawisz **Ctrl**.
6. Gdy wszystko będzie gotowe, wybierz pozycję **Zapisz**.

## <a name="exclude-groups-from-a-profile-assignment"></a>Wykluczanie grup z przypisania profilu

Profile konfiguracji urządzeń w usłudze Intune umożliwiają wykluczanie grup z przypisania zasad. Można na przykład przypisać profil urządzenia do grupy **Wszyscy użytkownicy firmowi**, ale z wykluczeniem wszystkich członków grupy **Wyższa kadra kierownicza**.

Podczas wykluczania grup z przypisania należy uwzględnić tylko grupy użytkowników lub tylko grupy urządzeń (a nie oba rodzaje grup). Usługa Intune nie uwzględnia relacji między użytkownikami a urządzeniami. Dołączanie grup użytkowników przy jednoczesnym wykluczaniu grup urządzeń może nie przynieść oczekiwanych rezultatów. Jeśli są używane mieszane grupy lub występują inne konflikty, operacja dołączania ma pierwszeństwo przed operacją wykluczania.

Możesz na przykład chcieć przypisać profil urządzenia do wszystkich urządzeń w organizacji z wyjątkiem kiosków. Musisz dołączyć grupę **Wszyscy użytkownicy**, ale wykluczyć grupę **Wszystkie urządzenia**. Zasady zostaną wtedy zastosowane do wszystkich użytkowników i ich urządzeń, nawet jeśli dane urządzenie użytkownika należy do grupy **Wszystkie urządzenia**.

Podczas wykluczania są uwzględniani tylko członkowie konkretnych grup. Urządzenia skojarzone z użytkownikami nie są uwzględniane. Jednak urządzenia nieskojarzone z żadnym użytkownikiem nie otrzymają zasad. Dzieje się tak, ponieważ te urządzenia nie mają relacji z grupą **Wszyscy użytkownicy**.

Jeśli dołączysz grupę **Wszystkie urządzenia**, a wykluczysz grupę **Wszyscy użytkownicy**, zasady zostaną zastosowane do wszystkich urządzeń. W tym przypadku celem jest wykluczenie z zasad urządzeń, które są skojarzone z użytkownikami. Jednak urządzenia nie zostaną wykluczone, ponieważ funkcja wykluczania porównuje tylko członków grup.

>[!TIP]
>Wykluczenia nie są dostępne w zasadach zgodności lub na potrzeby przypisania aplikacji. Aby wykluczyć członków z przypisania, można użyć przypisań **Dostępny** i **Nie dotyczy**. Można na przykład przypisać aplikację do grupy **Wszyscy użytkownicy firmowi** z celem **Dostępny** oraz do grupy **Wyższa kadra kierownicza** z celem **Nie dotyczy**. Aplikacja zostanie przypisana do wszystkich użytkowników *z wyjątkiem* użytkowników w grupie **Wyższa kadra kierownicza**. W przypadku przypisania aplikacji do grupy **Wszyscy użytkownicy firmowi** z celem **Wymagany** użytkownicy w grupie **Wyższa kadra kierownicza** również zostaną dołączeni do przypisania.

## <a name="next-steps"></a>Następne kroki
Zobacz artykuł [How to monitor device profiles](device-profile-monitor.md) (Sposoby monitorowania profili urządzeń), aby uzyskać wskazówki dotyczące monitorowania przypisań profilu urządzenia.
