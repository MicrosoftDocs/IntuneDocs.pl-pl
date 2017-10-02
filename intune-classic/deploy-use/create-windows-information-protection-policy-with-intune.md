---
title: "Tworzenie i wdrażanie zasad ochrony aplikacji w funkcji Windows Information Protection (WIP) za pomocą usługi Intune"
description: "Tworzenie i wdrażanie zasad ochrony aplikacji w funkcji WIP za pomocą usługi Intune"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 9/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 51e53e28-5c34-4d0f-a4b1-6390a337514c
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 040ce88c47eb12bbe9b228189d90ca422e5185e7
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2017
---
# <a name="create-and-deploy-windows-information-protection-wip-app-protection-policy-with-intune"></a>Tworzenie i wdrażanie zasad ochrony aplikacji w funkcji Windows Information Protection (WIP) za pomocą usługi Intune

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Począwszy od usługi Intune w wersji 1704, można używać zasad ochrony aplikacji z systemem Windows 10 w ramach scenariusza zarządzania aplikacjami mobilnymi (MAM) bez rejestracji.

## <a name="before-you-begin"></a>Przed rozpoczęciem

Omówmy kilka założeń dotyczących dodawania zasad funkcji WIP.

### <a name="list-of-allowed-and-exempt-apps"></a>Lista aplikacji dozwolonych i wykluczonych

-   **Dozwolone aplikacje:** są to aplikacje, które muszą stosować się do tych zasad.

-   **Wykluczone aplikacje:** te aplikacje nie podlegają tym zasadom i mogą uzyskiwać dostęp do danych firmowych bez ograniczeń.

### <a name="types-of-apps"></a>Typy aplikacji

-   **Zalecane aplikacje:** wstępnie wypełniona lista aplikacji (przede wszystkim pakietu Microsoft Office), którą administratorzy mogą łatwo zaimportować do zasad.

-   **Aplikacje ze sklepu:** administrator może dodać do zasad dowolną aplikację ze sklepu Windows.

-   **Aplikacje klasyczne systemu Windows:** administrator może dodać do zasad dowolne aplikacje klasyczne systemu Windows (np. plik exe, dll itd.).

## <a name="pre-requisites"></a>Wymagania wstępne

Aby można było utworzyć zasady ochrony aplikacji w funkcji WIP, trzeba skonfigurować dostawcę usług MAM.

-   Dowiedz się więcej na temat [konfiguracji dostawcy usług MAM za pomocą usługi Intune](/intune-classic/deploy-use/get-ready-to-configure-app-protection-policies-for-windows-10).

Ponadto wymagane są następujące elementy:

-   Licencja [Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium).
-   [Aktualizacja systemu Windows dla twórców](https://blogs.windows.com/windowsexperience/2017/04/11/how-to-get-the-windows-10-creators-update/#o61bC2PdrHslHG5J.97)

> [!IMPORTANT]
> Funkcja WIP nie obsługuje wielu tożsamości, jednorazowo może istnieć tylko jedna zarządzana tożsamość.

## <a name="to-add-a-wip-policy"></a>Aby dodać zasady funkcji WIP

Po skonfigurowaniu usługi Intune w organizacji można utworzyć zasady dotyczące funkcji WIP za pośrednictwem witryny [Azure Portal](/intune-classic/deploy-use/azure-portal-for-microsoft-intune-mam-policies).

1.  Przejdź do **pulpitu nawigacyjnego zarządzania aplikacjami mobilnymi usługi Intune**, wybierz pozycję **Wszystkie ustawienia**, a następnie pozycję **Zasady aplikacji**.

2.  W bloku **Zasady aplikacji** wybierz pozycję **Dodaj zasady**, następnie wprowadź następujące wartości:

    a.  **Nazwa:**wpisz nazwę (wymaganą) dla nowych zasad.

    b.  **Opis:** wpisz opcjonalny opis.

    c.  **Platforma:** wybierz **Windows 10** jako obsługiwaną platformę dla zasad ochrony aplikacji.

    d.  **Stan rejestracji:** wybierz **Bez rejestracji** jako stan rejestracji dla zasad.

3.  Wybierz pozycję **Utwórz**. Zasady zostaną utworzone i pojawią się w tabeli w bloku **Zasady aplikacji**.

## <a name="to-add-recommended-apps-to-your-allowed-apps-list"></a>Aby dodać aplikacje zalecane do listy Dozwolone aplikacje

1.  W bloku **Zasady aplikacji** wybierz nazwę swoich zasad, a następnie wybierz pozycję **Dozwolone aplikacje** w bloku **Dodaj zasady**. Zostanie otwarty blok **Dozwolone aplikacje** zawierający wszystkie aplikacje, które zostały już dołączone do listy dla tych zasad ochrony aplikacji.

2.  W bloku **Dozwolone aplikacje** wybierz pozycję **Dodaj aplikacje**. Zostanie otwarty blok **Dodaj aplikacje** zawierający wszystkie aplikacje należące do tej listy.

3.  Wybierz każdą aplikację, która ma uzyskiwać dostęp do danych firmowych, a następnie wybierz przycisk **OK**. Blok **Dozwolone aplikacje** zostanie zaktualizowany i będzie zawierać wszystkie wybrane aplikacje.

## <a name="add-a-store-app-to-your-allowed-apps-list"></a>Dodawanie aplikacji ze Sklepu do listy Dozwolone aplikacje

**Aby dodać aplikację ze Sklepu**

1.  W bloku **Zasady aplikacji** wybierz nazwę zasad, następnie wybierz pozycję **Dozwolone aplikacje** z wyświetlonego menu, które zawiera wszystkie aplikacje dołączone już do listy dla tych zasad ochrony aplikacji.

2.  W bloku **Dozwolone aplikacje** wybierz pozycję **Dodaj aplikacje**.

3.  W bloku **Dodaj aplikacje** z listy rozwijanej wybierz pozycję **Aplikacje ze Sklepu**. Blok zostanie zmieniony, aby udostępnić pola umożliwiające dodanie **wydawcy** oraz **nazwy** aplikacji.

4.  Wpisz nazwę aplikacji i nazwę jej wydawcy, a następnie wybierz przycisk **OK**.

    > [!TIP]
    > Oto przykład aplikacji, dla której **Wydawca** to *CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US*, a **nazwa** produktu to *Microsoft.MicrosoftAppForWindows*.

5.  Po wprowadzeniu informacji w polach wybierz przycisk **OK**, aby dodać aplikację do listy **Dozwolone aplikacje**.

> [!NOTE]
> Aby równocześnie dodać wiele aplikacji ze Sklepu, można kliknąć menu **(...)** na końcu wiersza aplikacji, a następnie kontynuować dodawanie dalszych aplikacji. Po zakończeniu tych czynności wybierz przycisk **OK**.

## <a name="add-a-desktop-app-to-your-allowed-apps-list"></a>Dodawanie aplikacji klasycznej do listy Dozwolone aplikacje

**Aby dodać aplikację klasyczną**

1.  W bloku **Zasady aplikacji** wybierz nazwę swoich zasad, a następnie wybierz pozycję **Dozwolone aplikacje**. Zostanie otwarty blok **Dozwolone aplikacje** zawierający wszystkie aplikacje, które zostały już dołączone do listy dla tych zasad ochrony aplikacji.

2.  W bloku **Dozwolone aplikacje** wybierz pozycję **Dodaj aplikacje**.

3.  W bloku **Dodaj aplikacje** z listy rozwijanej wybierz pozycję **Aplikacje klasyczne**.

4.  Po wprowadzeniu informacji w polach wybierz przycisk **OK**, aby dodać aplikację do listy **Dozwolone aplikacje**.

> [!NOTE]
> Aby równocześnie dodać wiele **aplikacji klasycznych**, można kliknąć menu **(...)** na końcu wiersza aplikacji, a następnie kontynuować dodawanie dalszych aplikacji. Po zakończeniu tych czynności wybierz przycisk **OK**.

## <a name="windows-information-protection-wip-learning"></a>Uczenie funkcji Windows Information Protection (WIP)

Po dodaniu aplikacji, które chcesz chronić za pomocą funkcji WIP, konieczne jest zastosowanie trybu ochrony z wykorzystaniem opcji **Uczenie funkcji WIP**.

### <a name="before-you-begin"></a>Przed rozpoczęciem

Uczenie funkcji Windows Information Protection (WIP) to raport, który umożliwia administratorom monitorowanie aplikacji nieznanych funkcji WIP. Nieznane aplikacje to te, które nie zostały wdrożone przez dział informatyczny organizacji użytkownika. Administrator może wyeksportować te aplikacje z raportu i dodać je do swoich zasad funkcji WIP, aby uniknąć zakłóceń produktywności przed wymuszeniem działania funkcji WIP w trybie „Ukryj przesłonięcia”.

Firma Microsoft zaleca rozpoczęcie od opcji **Cichy** lub **Zezwalaj na przesłonięcia** i zweryfikowania w małej grupie, czy na liście aplikacji dozwolonych znajdują się odpowiednie aplikacje. Po wykonaniu tych czynności można przełączyć na ostateczne zasady wymuszania **Ukryj przesłonięcia**.

#### <a name="what-the-protection-modes-are"></a>Jakie są tryby ochrony?

- **Ukryj przesłonięcia:**
    - Funkcja WIP szuka niewłaściwych praktyk udostępniania danych i powstrzymuje użytkownika przed ukończeniem akcji.
    - Może to obejmować udostępnianie informacji aplikacjom nieobjętym firmową ochroną oraz udostępnianie danych firmowych innym osobom i urządzeniem poza organizacją.
<br></br>

- **Zezwalaj na przesłonięcia:**
    - Funkcja WIP szuka niewłaściwych przypadków udostępniania danych, ostrzegając użytkowników, jeśli robią coś, co zostanie uznane za potencjalnie niebezpieczne.
    - Ten tryb pozwala jednak użytkownikowi przesłonić zasady i udostępnić dane, przy czym dana akcja jest rejestrowana w dzienniku inspekcji.
<br></br>
- **Cichy:**
    - Funkcja WIP jest uruchamiana w trybie cichym: niewłaściwe udostępnianie danych jest rejestrowane i nie są blokowane żadne akcje, które w trybie zezwolenia na przesłonięcia pojawiłyby się w monicie wymagającym interakcji z pracownikiem.
    - Niedozwolone akcje, np. gdy aplikacje podejmują próby uzyskania nieuprawnionego dostępu do zasobów sieciowych lub danych chronionych przy użyciu funkcji WIP, są nadal zatrzymywane.
<br></br>
- **Wyłączona (niezalecane):**
    - Funkcja WIP zostanie wyłączona i nie będzie używana do ochrony ani inspekcji danych.
    - Po wyłączeniu funkcji WIP zostanie podjęta próba odszyfrowania wszystkich plików oznakowanych przy użyciu funkcji WIP na dyskach podłączonych lokalnie. Należy mieć świadomość, że informacje dotyczące poprzedniego odszyfrowania i poprzednich zasad nie są automatycznie stosowane ponownie po ponownym włączeniu ochrony WIP.

### <a name="to-add-a-protection-mode"></a>Aby dodać tryb ochrony

1.  W bloku **Zasady aplikacji** wybierz nazwę zasad, a następnie kliknij pozycję **Wymagane ustawienia** w bloku **Dodaj zasady**.

    ![Zrzut ekranu trybu uczenia](../media/AppManagement/learning-mode-sc1.png)

1.  Wybierz polecenie **Zapisz**.

### <a name="to-use-wip-learning"></a>Aby korzystać z opcji Uczenie funkcji WIP

1. Przejdź do pulpitu nawigacyjnego platformy Azure.

2. W menu po lewej stronie wybierz pozycję **Więcej usług**, a następnie w filtrze pola tekstowego wpisz **Intune**.

3. Wybierz pozycję **Intune**, a kiedy zostanie otwarty **pulpit nawigacyjny Intune**, wybierz pozycję **Aplikacje mobilne**.

4. Wybierz pozycję **Uczenie funkcji WIP** w obszarze sekcji **Monitor**. Zostaną wyświetlone nieznane aplikacje zarejestrowane przy użyciu funkcji Uczenie funkcji WIP.

> [!IMPORTANT]
> Gdy aplikacje pojawią się w raporcie rejestracji funkcji Uczenie funkcji WIP, można dodać je do zasad ochrony aplikacji.

## <a name="to-deploy-your-wip-app-protection-policy"></a>Aby wdrożyć zasady ochrony aplikacji w funkcji WIP

> [!IMPORTANT]
> Dotyczy to funkcji WIP w scenariuszu zarządzania aplikacjami mobilnymi (MAM) bez rejestracji.

Po utworzeniu zasad ochrony aplikacji w funkcji WIP trzeba je wdrożyć do organizacji przy użyciu funkcji MAM.

1.  W bloku **Zasady aplikacji** wybierz nowo utworzone zasady ochrony aplikacji, wybierz pozycję **Grupy użytkowników**, następnie wybierz pozycję **Dodaj grupę użytkowników**.

    Lista grup użytkowników zawierająca wszystkie grupy zabezpieczeń w usłudze Azure Active Directory zostanie otwarta w bloku **Dodaj grupę użytkowników**.

1.  Wybierz grupę, do której mają się odnosić zasady, a następnie kliknij pozycję **Wybierz**, aby wdrożyć zasady.
