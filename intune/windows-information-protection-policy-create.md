---
title: "Tworzenie i wdrażanie zasad ochrony aplikacji w funkcji Windows Information Protection (WIP) za pomocą usługi Intune"
titlesuffix: Azure portal
description: "Tworzenie i wdrażanie zasad ochrony aplikacji w funkcji WIP za pomocą usługi Intune"
keywords: 
author: Erikre
ms.author: erikre
manager: doubeby
ms.date: 02/16/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4e3627bd-a9fd-49bc-b95e-9b7532f0ed55
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 647e6fd129593156f2ba24299a19e96686206165
ms.sourcegitcommit: 1978a30ab1af0f43aa5f447690d0bbcdcb9b563b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/24/2018
---
# <a name="create-and-deploy-windows-information-protection-wip-app-protection-policy-with-intune"></a>Tworzenie i wdrażanie zasad ochrony aplikacji w funkcji Windows Information Protection (WIP) za pomocą usługi Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Począwszy od usługi Intune w wersji 1704, można używać zasad ochrony aplikacji z systemem Windows 10, aby zabezpieczać aplikacje bez rejestracji urządzeń.

## <a name="before-you-begin"></a>Przed rozpoczęciem

Omówmy kilka założeń dotyczących dodawania zasad funkcji WIP.

### <a name="list-of-allowed-and-exempt-apps"></a>Lista aplikacji dozwolonych i wykluczonych

-   **Dozwolone aplikacje:** są to aplikacje, które muszą stosować się do tych zasad.

-   **Wykluczone aplikacje:** te aplikacje nie podlegają tym zasadom i mogą uzyskiwać dostęp do danych firmowych bez ograniczeń.

### <a name="types-of-apps"></a>Typy aplikacji

-   **Zalecane aplikacje:** wstępnie wypełniona lista aplikacji (przede wszystkim pakietu Microsoft Office), którą możesz łatwo zaimportować do zasad. <!---I really don't know what you mean by "easily import into policy"--->

-   **Aplikacje ze sklepu:** możesz dodać do zasad dowolną aplikację ze sklepu Windows.

-   **Aplikacje klasyczne systemu Windows:** możesz dodać do zasad dowolne aplikacje klasyczne systemu Windows (np. plik exe, dll)

## <a name="pre-requisites"></a>Wymagania wstępne

Aby można było utworzyć zasady ochrony aplikacji w funkcji WIP, musisz skonfigurować dostawcę usług MAM. Dowiedz się więcej na temat [konfiguracji dostawcy usług MAM za pomocą usługi Intune](app-protection-policies-configure-windows-10.md).

Ponadto wymagane są następujące licencje i aktualizacje:

-   Licencja [Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium).
-   [Aktualizacja systemu Windows dla twórców](https://blogs.windows.com/windowsexperience/2017/04/11/how-to-get-the-windows-10-creators-update/#o61bC2PdrHslHG5J.97)

> [!IMPORTANT]
> Funkcja WIP nie obsługuje wielu tożsamości, jednorazowo może istnieć tylko jedna zarządzana tożsamość.
<!---Should you be linking to a topic that explains what multi-identity is?--->

## <a name="to-add-a-wip-policy"></a>Aby dodać zasady funkcji WIP

Po skonfigurowaniu usługi Intune w organizacji można utworzyć zasady dotyczące funkcji WIP za pośrednictwem witryny [Azure Portal](https://docs.microsoft.com/intune-classic/deploy-use/azure-portal-for-microsoft-intune-mam-policies). <!---Is there an azure topic you can use instead of a classic? if not, should this topic be moved into the azure doc set?--->

1.  Przejdź do **pulpitu nawigacyjnego zarządzania aplikacjami mobilnymi usługi Intune**, wybierz pozycję **Wszystkie ustawienia** > **Zasady aplikacji**.

2.  W bloku **Zasady aplikacji** wybierz pozycję **Dodaj zasady**, następnie wprowadź następujące wartości:

    a.  **Nazwa:**wpisz nazwę (wymaganą) dla nowych zasad.

    b.  **Opis:** wpisz opcjonalny opis.

    c.  **Platforma:** wybierz **Windows 10** jako obsługiwaną platformę dla zasad ochrony aplikacji.

    d.  **Stan rejestracji:** wybierz **Bez rejestracji** jako stan rejestracji dla zasad.

3.  Wybierz pozycję **Utwórz**. Zasady zostaną utworzone i pojawią się w tabeli w bloku **Zasady aplikacji**.

## <a name="to-add-recommended-apps-to-your-allowed-apps-list"></a>Aby dodać aplikacje zalecane do listy Dozwolone aplikacje

1.  W bloku **Zasady aplikacji** wybierz nazwę swoich zasad, a następnie wybierz pozycję **Dozwolone aplikacje** w bloku **Dodaj zasady**. Zostanie otwarty blok **Dozwolone aplikacje** zawierający wszystkie aplikacje, które zostały już dołączone do listy dla tych zasad ochrony aplikacji.

2.  W bloku **Dozwolone aplikacje** wybierz pozycję **Dodaj aplikacje**. Informacje **Dodawanie aplikacji** zawierają wszystkie aplikacje, które są częścią tej listy.

3.  Wybierz każdą aplikację, która ma uzyskiwać dostęp do danych firmowych, a następnie wybierz przycisk **OK**. Blok **Dozwolone aplikacje** zostanie zaktualizowany i będzie zawierać wszystkie wybrane aplikacje.

## <a name="add-a-store-app-to-your-allowed-apps-list"></a>Dodawanie aplikacji ze Sklepu do listy Dozwolone aplikacje

**Aby dodać aplikację ze Sklepu**

1.  W bloku **Zasady aplikacji** wybierz nazwę zasad, następnie wybierz pozycję **Dozwolone aplikacje** z wyświetlonego menu, które zawiera wszystkie aplikacje dołączone już do listy dla tych zasad ochrony aplikacji.

2.  W bloku **Dozwolone aplikacje** wybierz pozycję **Dodaj aplikacje**.

3.  W bloku **Dodaj aplikacje** z listy rozwijanej wybierz pozycję **Aplikacje ze Sklepu**. Informacje zostaną zmienione, aby udostępnić pola umożliwiające dodanie **wydawcy** oraz **nazwy** aplikacji.

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

## <a name="wip-learning"></a>Uczenie funkcji WIP
<!---You've already defined WIP earlier in the topic. You don't need to keep doing so. --->
Po dodaniu aplikacji, które chcesz chronić za pomocą funkcji WIP, konieczne jest zastosowanie trybu ochrony z wykorzystaniem opcji **Uczenie funkcji WIP**.

### <a name="before-you-begin"></a>Przed rozpoczęciem

Uczenie funkcji WIP to raport, który umożliwia monitorowanie aplikacji obsługujących funkcję WIP i nieznanych aplikacji funkcji WIP. Nieznane aplikacje to te, które nie zostały wdrożone przez dział informatyczny organizacji użytkownika. Możesz wyeksportować te aplikacje z raportu i dodać je do swoich zasad funkcji WIP, aby uniknąć zakłóceń produktywności przed wymuszeniem działania funkcji WIP w trybie „Zablokowanie”.

<!-- 1631908 --> In addition to viewing information about WIP-enabled apps, you can view a summary of the devices that have shared work data with websites. With this information, you can determine which websites should be added to group and user WIP policies. The summary shows which website URLs are accessed by WIP-enabled apps.

Podczas pracy z aplikacjami obsługującymi funkcję WIP i nieznanych aplikacji funkcji WIP zalecamy rozpoczęcie od opcji **Cichy** lub **Zezwalaj na przesłonięcia** i zweryfikowanie w małej grupie, czy na liście aplikacji dozwolonych znajdują się odpowiednie aplikacje. Po wykonaniu tych czynności można przełączyć na ostateczne zasady wymuszania, **Zablokowanie**.

### <a name="what-are-the-protection-modes"></a>Jakie są tryby ochrony?

#### <a name="block"></a>Zablokowanie
Funkcja WIP szuka niewłaściwych praktyk udostępniania danych i powstrzymuje użytkownika przed ukończeniem akcji. Może to obejmować udostępnianie informacji aplikacjom nieobjętym firmową ochroną oraz udostępnianie danych firmowych innym osobom i urządzeniem poza organizacją.

#### <a name="allow-overrides"></a>Zezwalaj na przesłonięcia
Funkcja WIP szuka niewłaściwych przypadków udostępniania danych, ostrzegając użytkowników, gdy robią coś, co zostanie uznane za potencjalnie niebezpieczne. Ten tryb pozwala jednak użytkownikowi przesłonić zasady i udostępnić dane, przy czym dana akcja jest rejestrowana w dzienniku inspekcji.

#### <a name="silent"></a>Dyskretnej
Funkcja WIP jest uruchamiana w trybie cichym: niewłaściwe udostępnianie danych jest rejestrowane i nie są blokowane żadne akcje, które w trybie zezwolenia na przesłonięcia pojawiłyby się w monicie wymagającym interakcji z pracownikiem. Niedozwolone akcje, np. gdy aplikacje podejmują próby uzyskania nieuprawnionego dostępu do zasobów sieciowych lub danych chronionych przy użyciu funkcji WIP, są nadal zatrzymywane.

#### <a name="off-not-recommended"></a>Wyłączona (niezalecane)
Funkcja WIP zostanie wyłączona i nie będzie używana do ochrony ani inspekcji danych.

Po wyłączeniu funkcji WIP zostanie podjęta próba odszyfrowania wszystkich plików oznakowanych przy użyciu funkcji WIP na dyskach podłączonych lokalnie. Zauważ, że informacje dotyczące poprzedniego odszyfrowywania i poprzednich zasad nie są automatycznie stosowane ponownie po ponownym włączeniu ochrony WIP.

### <a name="add-a-protection-mode"></a>Dodawanie trybu ochrony

1.  W bloku **Zasady aplikacji** wybierz nazwę swoich zasad, a następnie wybierz pozycję **Wymagane ustawienia**.

    ![Zrzut ekranu trybu uczenia](./media/learning-mode-sc1.png)

2.  Wybierz polecenie **Zapisz**.

### <a name="use-wip-learning"></a>Korzystanie z opcji Uczenie funkcji WIP

1. Otwórz witrynę Azure Portal. Wybierz pozycję **Więcej usług**. Wpisz **Intune** w polu tekstowym filtru.

3. Wybierz pozycje **Intune** > **Mobile Apps**.

4. Wybierz pozycje **Stan ochrony aplikacji** > **Raporty** > **Windows Information Protection — nauka**.  
 
    Gdy aplikacje pojawią się w raporcie rejestracji funkcji Uczenie funkcji WIP, możesz dodać je do zasad ochrony aplikacji.

## <a name="allow-windows-search-indexer-to-search-encrypted-items"></a>Zezwalanie indeksatorowi programu Windows Search na wyszukiwanie zaszyfrowanych elementów
Zezwala lub nie zezwala na indeksowanie elementów. Ten przełącznik jest przeznaczony dla indeksatora programu Windows Search, który kontroluje, czy indeksuje on elementy, które są zaszyfrowane, takie jak pliki chronione przez funkcję Windows Information Protection (WIP).

Ta opcja zasad ochrony aplikacji znajduje się w **Ustawieniach zaawansowanych** zasad Windows Information Protection. Zasady ochrony aplikacji muszą być ustawione na platformę *Windows 10*, a zasady aplikacji **Stan rejestracji** muszą być ustawione na wartość **Z rejestracją**. 

Gdy te zasady są włączone, elementy chronione przez funkcję WIP są indeksowane, a dotyczące ich metadane są przechowywane w lokalizacji niezaszyfrowanej. Metadane obejmują takie informacje, jak ścieżka do pliku i data modyfikacji.

Gdy zasady są wyłączone, elementy chronione przez funkcję WIP nie są indeksowane i nie są wyświetlane w wynikach w Cortanie ani Eksploratorze plików. Jeśli na urządzeniu istnieje wiele plików multimedialnych chronionych przez funkcję WIP, może to także mieć wpływ na wydajność dla zdjęć i aplikacji Groove.

## <a name="add-encrypted-file-extensions"></a>Dodawanie rozszerzeń szyfrowanych plików

Oprócz ustawienia opcji **Zezwalaj indeksatorowi programu Windows Search na wyszukiwanie elementów zaszyfrowanych** możesz określić listę rozszerzeń nazw plików. Pliki z tymi rozszerzeniami są szyfrowane podczas kopiowania z udziału bloku komunikatów serwera (SMB, Server Message Block) w obrębie przedsiębiorstwa zgodnie z definicją na liście lokalizacji sieciowych. Gdy te zasady nie zostaną określone, jest stosowane istniejące zachowanie automatycznego szyfrowania. Gdy te zasady zostaną skonfigurowane, będą szyfrowane tylko pliki mające rozszerzenia znajdujące się na liście.

## <a name="deploy-your-wip-app-protection-policy"></a>Wdrażanie zasad ochrony aplikacji w funkcji WIP

> [!IMPORTANT]
> Te informacje mają zastosowanie do funkcji WIP bez rejestracji urządzeń.

<!---not sure why you need the Important note. Isn't this what the topic is about? app protection w/o enrollment?--->

Po utworzeniu zasad ochrony aplikacji w funkcji WIP trzeba je wdrożyć do organizacji przy użyciu funkcji MAM.

1.  W bloku **Zasady aplikacji** wybierz swoje nowo utworzone zasady ochrony aplikacji i wybierz pozycje **Grupy użytkowników** > **Dodaj grupę użytkowników**.

    Lista grup użytkowników zawierająca wszystkie grupy zabezpieczeń w usłudze Azure Active Directory zostanie otwarta w bloku **Dodaj grupę użytkowników**.

2.  Wybierz grupę, do której mają się odnosić zasady, a następnie wybierz pozycję **Wybierz**, aby wdrożyć zasady.

## <a name="next-steps"></a>Następne kroki

- Aby dowiedzieć się więcej na temat funkcji Windows Information Protection, zobacz [Protect your enterprise data using Windows Information Protection (Chronienie danych przedsiębiorstwa przy użyciu funkcji Windows Information Protection [WIP])](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip). 
