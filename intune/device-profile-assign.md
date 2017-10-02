---
title: "Jak przypisywać profile urządzeń usługi Intune"
titlesuffix: Azure portal
description: "Po utworzeniu profilu urządzenia w usłudze Intune zapoznaj się z tym tematem, aby dowiedzieć się, jak przypisać profil do urządzeń."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 07/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ba1438fe9227e0c7933fda7e9a2b60c8d4a5dca4
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2017
---
# <a name="how-to-assign-microsoft-intune-device-profiles"></a>Jak przypisywać profile urządzeń usługi Microsoft Intune

## <a name="assign-a-device-profile"></a>Przypisywanie profilu urządzenia

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Konfiguracja urządzeń**.
1. W bloku **Konfiguracja urządzeń** wybierz kolejno pozycje **Zarządzaj** > **Profile**.
2. W bloku listy profilów wybierz profil, którym chcesz zarządzać, a następnie wybierz w bloku <*nazwa profilu*> **Raporty** pozycje **Zarządzaj** > **Przypisania**.
3. W następnym bloku wybierz pozycję **Dołącz** (aby dołączyć grupy) lub **Wyklucz** (aby wykluczyć grupy), a następnie wybierz pozycję **Wybierz grupy**.
![Dołączanie grup do przypisania profilu i wykluczanie grup z przypisania profilu.](./media/group-include-exclude.png)
4. W bloku **Wybierz grupy** wybierz grupy usługi Azure AD, które chcesz dołączyć do przypisania lub wykluczyć z przypisania. Możesz nacisnąć klawisz **CTRL**, aby wybrać wiele grup.
4. Gdy wszystko będzie gotowe, w bloku **Wybierz grupy** wybierz pozycję **Wybierz**.



## <a name="how-to-exclude-groups-from-a-device-profile-assignment"></a>Jak wykluczyć grupy z przypisania profilu urządzenia

Profile konfiguracji urządzeń w usłudze Intune umożliwiają wykluczanie grup z przypisania zasad. Można na przykład przypisać profil urządzenia do grupy **Wszyscy użytkownicy firmowi**, ale z wykluczeniem wszystkich członków grupy **Wyższa kadra kierownicza**.

Wykluczanie grup z przypisania powinno obejmować tylko grupy użytkowników lub tylko grupy urządzeń, ale nie kombinację tych grup. Podczas wykluczania grup usługa Intune nie uwzględnia żadnych skojarzeń użytkowników z urządzeniami. Dołączanie grup użytkowników przy jednoczesnym wykluczaniu grup urządzeń raczej nie przyniesie oczekiwanych rezultatów. Jeśli są używane mieszane grupy lub występują inne konflikty, operacja dołączania ma pierwszeństwo przed operacją wykluczania.

Możesz na przykład chcieć przypisać profil urządzenia do wszystkich urządzeń w organizacji z wyjątkiem kiosków. Musisz dołączyć grupę **Wszyscy użytkownicy**, ale wykluczyć grupę **Wszystkie urządzenia**.

Zasady zostaną wtedy zastosowane do wszystkich użytkowników i ich urządzeń, nawet jeśli dane urządzenie użytkownika należy do grupy **Wszystkie urządzenia**. 

Podczas wykluczania są uwzględniani tylko członkowie konkretnych grup. Urządzenia skojarzone z użytkownikami nie są uwzględniane. Jednak zasady nie obejmują urządzeń bez użytkowników, ponieważ urządzenia te nie są skojarzone z grupą **Wszyscy użytkownicy**. 

Jeśli dołączysz grupę **Wszystkie urządzenia**, ale wykluczysz grupę **Wszyscy użytkownicy**, zasady zostaną zastosowane do wszystkich urządzeń. W tym przypadku celem jest wykluczenie z zasad urządzeń, które są skojarzone z użytkownikami. Jednak rezultat nie odpowiada oczekiwaniom, ponieważ funkcja wykluczania porównuje tylko członków grup. 

>[!Tip]
>Aktualnie wykluczenia nie są dostępne w zasadach zgodności lub na potrzeby przypisania aplikacji. Aby wykluczyć członków z przypisania, można użyć celów przypisania Dostępny i Nie dotyczy. Można na przykład przypisać aplikację do grupy **Wszyscy użytkownicy firmowi** z celem **Dostępny** oraz do grupy **Wyższa kadra kierownicza** z celem **Nie dotyczy**. Aplikacja zostanie przypisana do wszystkich użytkowników *z wyjątkiem* użytkowników w grupie **Wyższa kadra kierownicza**. W przypadku przypisania aplikacji do grupy **Wszyscy użytkownicy firmowi** z celem **Wymagany** użytkownicy w grupie **Wyższa kadra kierownicza** nie zostaną wykluczeni.
 
    
## <a name="next-steps"></a>Następne kroki
Zobacz artykuł [How to monitor device profiles](device-profile-monitor.md) (Sposoby monitorowania profilów urządzeń), aby uzyskać informacje, które ułatwią Ci monitorowanie przypisań profilu urządzenia.
