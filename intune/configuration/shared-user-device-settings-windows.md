---
title: Ustawienia udostępnionego urządzenia z systemem Windows 10 w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dodaj system Windows 10 i używaj go w celu skonfigurowania urządzeń udostępnionych, czyli używanych przez wielu użytkowników w usłudze Microsoft Intune. Wyświetl listę wszystkich ustawień i przekonaj się, jak działają na urządzeniach, na przykład na urządzeniu Microsoft Surface. Profil konfiguracji urządzenia umożliwia kontrolowanie kont gości, zarządzanie kontami, usuwanie kont nieaktywnych, zezwalanie na zapisywanie w magazynie lokalnym lub blokowanie tej możliwości, konfigurowanie opcji zasilania i uśpienia, wybieranie, kiedy mają zostać zainstalowane aktualizacje, oraz korzystanie z urządzeń w środowiskach edukacyjnych.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/01/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 67393f83ecd76250e01deef3eee20aa1206b3f99
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71734287"
---
# <a name="windows-10-and-later-settings-to-manage-shared-devices-using-intune"></a>Ustawienia systemu Windows 10 oraz nowszych wersji służące do zarządzania urządzeniami udostępnionymi przy użyciu usługi Intune

Urządzenia z systemem Windows 10 lub nowszą wersją, na przykład Microsoft Surface, mogą być używane przez wielu użytkowników. Urządzenia, które mają wielu użytkowników, to tak zwane urządzenia udostępnione. Jest to element rozwiązań do zarządzania urządzeniami mobilnymi.

Dzięki usłudze Microsoft Intune użytkownicy końcowi mogą logować się na tych urządzeniach udostępnionych, używając kont gości. Podczas korzystania z urządzenia mają dostęp tylko do tych funkcji, które im udostępnisz. Jako administrator usługi Intune możesz między innymi konfigurować dostęp, decydować o usuwaniu kont i kontrolować ustawienia zarządzania zasilaniem na urządzeniach udostępnionych z systemem Windows 10.

W tym artykule wymieniono i opisano ustawienia używane w profilu konfiguracji urządzenia z systemem Windows 10 (lub nowszą wersją). Po utworzeniu profilu w usłudze Intune możesz wdrożyć lub przypisać profil do grup urządzeń w swojej organizacji. Możesz również przypisać ten profil do grup urządzeń składających się z różnych typów urządzeń i wersji systemu operacyjnego.

Aby uzyskać więcej informacji na temat tej funkcji w usłudze Intune, zobacz [Control access, accounts, and power features on shared PC or multi-user devices (Kontrola dostępu, konta i funkcje zasilania na komputerze udostępnionym lub urządzeniach obsługujących wielu użytkowników)](shared-user-device-settings.md). Aby uzyskać więcej informacji na temat dostawcy CSP w systemie Windows, zobacz [SharedPC CSP (Dostawca CSP na komputerze udostępnionym)](https://docs.microsoft.com/windows/client-management/mdm/sharedpc-csp).

## <a name="before-your-begin"></a>Zanim rozpoczniesz

[Utwórz profil](shared-user-device-settings.md).

## <a name="shared-multi-user-device-settings"></a>Ustawienia urządzenia udostępnionego obsługującego wielu użytkowników

- **Tryb komputera udostępnionego**: wybierz polecenie **Włącz**, aby włączyć tryb komputera udostępnionego. W tym trybie na urządzeniu może zalogować się jednocześnie tylko jeden użytkownik. Inny użytkownik nie może się zalogować, dopóki pierwszy użytkownik się nie wyloguje. Domyślna opcja **Nieskonfigurowane** oznacza, że to ustawienie jest niezarządzane przez usługę Intune i nie wypycha żadnych zasad w celu kontroli tego ustawienia na urządzeniu.
- **Konto gościa**: wybierz, aby utworzyć opcję Gość na ekranie logowania. Konta gości nie wymagają poświadczeń użytkownika ani uwierzytelniania. To ustawienie tworzy nowe konto lokalne za każdym razem, gdy zostanie użyte. Dostępne opcje:
  - **Gość**: tworzy konto gościa lokalnie na urządzeniu.
  - **Domena**: tworzy konto gościa w usłudze Azure Active Directory (AD).
  - **Gość i domena**: tworzy konto gościa lokalnie na urządzeniu i w usłudze Azure Active Directory (AD).
- **Zarządzanie kontami**: ustaw pozycję **Włącz**, aby automatycznie usuwać konta lokalne utworzone przez gości oraz konta w usługach AD i Azure AD. Gdy użytkownik wyloguje się z urządzenia lub gdy zostanie uruchomiona konserwacja systemu, te konta zostaną usunięte. Gdy to ustawienie jest włączone, należy również skonfigurować:
  - **Usuwanie kont**: określ, kiedy będą usuwane konta — **Po przekroczeniu progu przestrzeni dyskowej**, **Po przekroczeniu progu przestrzeni dyskowej i czasu nieaktywności** lub **Natychmiast po wylogowaniu**. Wprowadź też następujące ustawienia:
    - **Próg rozpoczęcia usuwania (%)** : wprowadź wartość procentową miejsca na dysku (od 0 do 100). Gdy łączna ilość miejsca na dysku/w pamięci urządzenia spadnie poniżej wprowadzonej wartości, konta zostaną usunięte z pamięci podręcznej. Konta są usuwane w trybie ciągłym w celu odzyskiwania miejsca dyskowego. Konta, które są nieaktywne najdłużej, są usuwane w pierwszej kolejności.
    - **Próg zatrzymania usuwania (%)** : wprowadź wartość procentową miejsca na dysku (od 0 do 100). Gdy łączna ilość miejsca na dysku/w pamięci urządzenia będzie odpowiadać wprowadzonej wartości, proces usuwania zostanie zatrzymany.

  Ustaw w pozycji **Wyłącz**, aby zachować konta lokalne, konta usługi AD oraz Azure AD utworzone przez gości.

- **Magazyn lokalny**: wybierz opcję **Włączone**, aby uniemożliwić użytkownikom zapisywanie i wyświetlanie plików na dysku twardym urządzenia. Wybierz opcję **Wyłączone**, aby umożliwić użytkownikom wyświetlanie i zapisywanie plików lokalnie za pomocą Eksploratora plików. Domyślna opcja **Nieskonfigurowane** oznacza, że to ustawienie jest niezarządzane przez usługę Intune i nie wypycha żadnych zasad w celu kontroli tego ustawienia na urządzeniu.
- **Zasady dotyczące zasilania**: po ustawieniu opcji **Włączone** użytkownicy nie mogą wyłączyć opcji hibernacji, nie mogą zmieniać działań związanych z trybem uśpienia (na przykład zamykania pokrywy) ani nie mogą zmieniać ustawień zasilania. Po ustawieniu opcji **Wyłączone**, użytkownicy mogą wprowadzić urządzenie w tryb hibernacji, mogą zamknąć pokrywę, aby wprowadzić urządzenie w stan uśpienia, i mogą zmieniać ustawienia zasilania. Domyślna opcja **Nieskonfigurowane** oznacza, że to ustawienie jest niezarządzane przez usługę Intune i nie wypycha żadnych zasad w celu kontroli tego ustawienia na urządzeniu.
- **Limit czasu uśpienia (w sekundach)** : wpisz, po ilu sekundach (od 0 do 100) nieaktywności urządzenie przejdzie w stan uśpienia. Jeśli nie ustawisz czasu, urządzenie przejdzie w stan uśpienia po upływie 60 minut.
- **Zaloguj, kiedy komputer wznowi pracę po uśpieniu**: ustaw opcję **Włączone**, aby użytkownicy musieli zalogować się przy użyciu hasła, gdy urządzenie wznawia pracę po uśpieniu. Wybierz opcję **Wyłączone**, aby użytkownicy nie musieli wprowadzać nazwy użytkownika i hasła. Domyślna opcja **Nieskonfigurowane** oznacza, że to ustawienie jest niezarządzane przez usługę Intune i nie wypycha żadnych zasad w celu kontroli tego ustawienia na urządzeniu.
- **Godzina rozpoczęcia konserwacji (w minutach od północy)** : wprowadź czas w minutach (od 0 do 1440), po którym zostaną uruchomione automatyczne zadania konserwacji, na przykład Windows Update. Domyślna godzina rozpoczęcia to północ, czyli zero (`0`) minut. Zmień czas rozpoczęcia, wprowadzając czas rozpoczęcia w minutach po północy. Jeśli chcesz na przykład, aby konserwacja rozpoczynała się o 2:00, wprowadź liczbę `120`. Jeśli chcesz, aby konserwacja rozpoczynała się o 20:00, wprowadź liczbę `1200`.
- **Zasady dotyczące edukacji**: wybierz opcję **Włączone**, aby używać ustawień zalecanych, które są bardziej restrykcyjne, podczas korzystania z urządzeń w szkołach. Wybierz opcję **Wyłączone**, aby nie korzystać z domyślnych i zalecanych ustawień dotyczących edukacji. Domyślna opcja **Nieskonfigurowane** oznacza, że to ustawienie jest niezarządzane przez usługę Intune i nie wypycha żadnych zasad w celu kontroli tego ustawienia na urządzeniu.

  Aby uzyskać więcej informacji na temat zasad dotyczących edukacji, zobacz [Windows 10 configuration recommendations for education customers (Zalecenia konfiguracji systemu Windows 10 dla klientów w instytucjach edukacyjnych)](https://docs.microsoft.com/education/windows/configure-windows-for-education).

> [!TIP]
> Artykuł [Set up a shared or guest PC (Konfigurowanie komputera udostępnionego lub komputera gościa)](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc) stanowi doskonałe źródło informacji o tej funkcji systemu Windows 10, w tym o związanych z nią koncepcjach oraz zasadach grup, które można konfigurować w trybie udostępniania (link otwiera osobną stronę witryny Docs).

## <a name="next-steps"></a>Następne kroki

- [Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).
- Sprawdź ustawienia systemu [Windows Holographic for Business](shared-user-device-settings-windows-holographic.md).
