---
title: Tworzenie i wdrażanie zasad ochrony aplikacji w funkcji Windows Information Protection (WIP)
titlesuffix: Microsoft Intune
description: Tworzenie i wdrażanie zasad ochrony aplikacji w funkcji Windows Information Protection (WIP) za pomocą usługi Intune
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4e3627bd-a9fd-49bc-b95e-9b7532f0ed55
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: b5599e98b9712d30979c327167b19b159d3ff5dc
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52181334"
---
# <a name="create-and-deploy-windows-information-protection-wip-app-protection-policy-with-intune"></a>Tworzenie i wdrażanie zasad ochrony aplikacji w funkcji Windows Information Protection (WIP) za pomocą usługi Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Za pomocą zasad ochrony aplikacji i aplikacji systemu Windows 10 można chronić aplikacje bez rejestracji urządzenia.

## <a name="before-you-begin"></a>Przed rozpoczęciem

Podczas dodawania zasad funkcji WIP należy zrozumieć kilka koncepcji:

### <a name="list-of-allowed-and-exempt-apps"></a>Lista aplikacji dozwolonych i wykluczonych

-   **Chronione aplikacje:** są to aplikacje, które muszą stosować się do tych zasad.

-   **Wykluczone aplikacje:** te aplikacje nie podlegają tym zasadom i mogą uzyskiwać dostęp do danych firmowych bez ograniczeń.

### <a name="types-of-apps"></a>Typy aplikacji

-   **Zalecane aplikacje:** wstępnie wypełniona lista aplikacji (przede wszystkim pakietu Microsoft Office), którą możesz łatwo zaimportować do zasad.
-   **Aplikacje ze sklepu:** możesz dodać do zasad dowolną aplikację ze sklepu Windows.
-   **Aplikacje klasyczne systemu Windows:** możesz dodać do zasad dowolne aplikacje klasyczne systemu Windows (np. plik exe, dll)

## <a name="prerequisites"></a>Wymagania wstępne

Aby można było utworzyć zasady ochrony aplikacji w funkcji WIP, musisz skonfigurować dostawcę usług MAM. Dowiedz się więcej na temat [konfiguracji dostawcy usług MAM za pomocą usługi Intune](app-protection-policies-configure-windows-10.md).  

> [!IMPORTANT]
> Funkcja WIP nie obsługuje wielu tożsamości, jednorazowo może istnieć tylko jedna zarządzana tożsamość.

Ponadto wymagane są następujące licencje i aktualizacje:

-   Licencja usługi [Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium)
-   [Aktualizacja systemu Windows dla twórców](https://blogs.windows.com/windowsexperience/2017/04/11/how-to-get-the-windows-10-creators-update/#o61bC2PdrHslHG5J.97)





## <a name="to-add-a-wip-app-protection-policy"></a>Aby dodać zasady ochrony aplikacji w funkcji WIP

Po skonfigurowaniu usługi Intune w organizacji można utworzyć zasady dotyczące funkcji WIP.

> [!TIP]  
> Aby uzyskać powiązane informacje dotyczące tworzenia zasad funkcji WIP usługi Intune, w tym dostępnych ustawień i sposobu ich konfigurowania, zobacz [Create a Windows Information Protection (WIP) policy with MAM using the Azure portal for Microsoft Intune ](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-mam-intune-azure) (Tworzenie zasad rozwiązania Windows Information Protection (WIP) przy użyciu funkcji MAM w witrynie Azure Portal dla usługi Microsoft Intune) w bibliotece dokumentacji dotyczącej zabezpieczeń systemu Windows. 


1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi** > **Intune**.
3. W bloku **Microsoft Intune** wybierz pozycję **Aplikacje klienckie**.
4. W bloku **Aplikacje klienckie** wybierz pozycję **Zasady ochrony aplikacji**.
5. Wybierz pozycję **Dodaj zasady**, aby wyświetlić blok **Dodawanie zasad**.
6. Dodaj następujące wartości:
    - **Nazwa:** wpisz nazwę (wymaganą) dla nowych zasad.
    - **Opis:** (opcjonalnie) wpisz opis.
    - **Platforma:** wybierz **Windows 10** jako obsługiwaną platformę dla zasad ochrony aplikacji.
    - **Stan rejestracji:** wybierz **Bez rejestracji** jako stan rejestracji dla zasad.
7.  Wybierz pozycję **Utwórz**. Zasady zostaną utworzone i pojawią się w tabeli w bloku **Zasady ochrony aplikacji**.

## <a name="to-add-recommended-apps-to-your-protected-apps-list"></a>Aby dodać aplikacje zalecane do listy Chronione aplikacje

1. W bloku **Microsoft Intune** wybierz pozycję **Aplikacje klienckie**.
2. W bloku **Aplikacje klienckie** wybierz pozycję **Zasady ochrony aplikacji**.
3. W bloku **Zasady ochrony aplikacji** wybierz zasady, które chcesz zmodyfikować. Zostanie wyświetlony blok **Ochrona aplikacji w usłudze Intune**.
4. Z bloku **Ochrona aplikacji w usłudze Intune** wybierz pozycję **Chronione aplikacje**. Zostanie otwarty blok **Chronione aplikacje** zawierający wszystkie aplikacje, które zostały już dołączone do listy dla tych zasad ochrony aplikacji.
5. Wybierz pozycję **Dodaj aplikacje**. W obszarze **Dodawanie aplikacji** jest wyświetlana filtrowana lista aplikacji. Lista w górnej części bloku pozwala na zmianę filtru listy.
6. Wybierz każdą aplikację, która ma mieć dostęp do danych firmowych.
7. Kliknij przycisk **OK**. Blok **Chronione aplikacje** zostanie zaktualizowany w celu wyświetlenia wszystkich wybranych aplikacji.
8. Kliknij polecenie **Zapisz**.

## <a name="add-a-store-app-to-your-protected-apps-list"></a>Dodawanie aplikacji ze Sklepu do listy Chronione aplikacje

**Aby dodać aplikację ze Sklepu**
1. W bloku **Microsoft Intune** wybierz pozycję **Aplikacje klienckie**.
2. W bloku **Aplikacje klienckie** wybierz pozycję **Zasady ochrony aplikacji**.
3. W bloku **Zasady ochrony aplikacji** wybierz zasady, które chcesz zmodyfikować. Zostanie wyświetlony blok **Ochrona aplikacji w usłudze Intune**.
4. Z bloku **Ochrona aplikacji w usłudze Intune** wybierz pozycję **Chronione aplikacje**. Zostanie otwarty blok **Chronione aplikacje** zawierający wszystkie aplikacje, które zostały już dołączone do listy dla tych zasad ochrony aplikacji.
5. Wybierz pozycję **Dodaj aplikacje**. W obszarze **Dodawanie aplikacji** jest wyświetlana filtrowana lista aplikacji. Lista w górnej części bloku pozwala na zmianę filtru listy.
6. Wybierz z listy pozycję **Aplikacje ze sklepu**.
7. Wprowadź wartości w polach **Nazwa**, **Wydawca**, **Nazwa produktu** i **Akcja**. Ustaw w polu **Akcja** wartość **Zezwalaj**, aby aplikacja miała dostęp do danych firmowych.
9. Kliknij przycisk **OK**. Blok **Chronione aplikacje** zostanie zaktualizowany w celu wyświetlenia wszystkich wybranych aplikacji.
10. Kliknij polecenie **Zapisz**.

## <a name="add-a-desktop-app-to-your-protected-apps-list"></a>Dodawanie aplikacji klasycznej do listy Chronione aplikacje

**Aby dodać aplikację klasyczną**
1. W bloku **Microsoft Intune** wybierz pozycję **Aplikacje klienckie**.
2. W bloku **Aplikacje klienckie** wybierz pozycję **Zasady ochrony aplikacji**.
3. W bloku **Zasady ochrony aplikacji** wybierz zasady, które chcesz zmodyfikować. Zostanie wyświetlony blok **Ochrona aplikacji w usłudze Intune**.
4. Z bloku **Ochrona aplikacji w usłudze Intune** wybierz pozycję **Chronione aplikacje**. Zostanie otwarty blok **Chronione aplikacje** zawierający wszystkie aplikacje, które zostały już dołączone do listy dla tych zasad ochrony aplikacji.
5. Wybierz pozycję **Dodaj aplikacje**. W obszarze **Dodawanie aplikacji** jest wyświetlana filtrowana lista aplikacji. Lista w górnej części bloku pozwala na zmianę filtru listy.
6. Wybierz z listy pozycję **Aplikacje klasyczne**.
7. Wprowadź wartości w polach **Nazwa**, **Wydawca**, **Nazwa produktu**, **Plik**, **Minimalna wersja**, **Maksymalna wersja** i **Akcja**. Ustaw w polu **Akcja** wartość **Zezwalaj**, aby aplikacja miała dostęp do danych firmowych.
9. Kliknij przycisk **OK**. Blok **Chronione aplikacje** zostanie zaktualizowany w celu wyświetlenia wszystkich wybranych aplikacji.
10. Kliknij polecenie **Zapisz**.

## <a name="wip-learning"></a>Uczenie funkcji WIP
Po dodaniu aplikacji, które chcesz chronić za pomocą funkcji WIP, konieczne jest zastosowanie trybu ochrony z wykorzystaniem opcji **Uczenie funkcji WIP**.

### <a name="before-you-begin"></a>Przed rozpoczęciem

Uczenie funkcji WIP to raport, który umożliwia monitorowanie aplikacji obsługujących funkcję WIP i nieznanych aplikacji funkcji WIP. Nieznane aplikacje to te, które nie zostały wdrożone przez dział informatyczny organizacji użytkownika. Możesz wyeksportować te aplikacje z raportu i dodać je do swoich zasad funkcji WIP, aby uniknąć zakłóceń produktywności przed wymuszeniem działania funkcji WIP w trybie „Zablokowanie”.

<!-- 1631908 --> Oprócz wyświetlania informacji o aplikacjach z włączoną funkcją WIP możesz wyświetlać podsumowanie urządzeń, które udostępniły dane robocze witrynom internetowym. Dzięki tym informacjom można ustalić, które witryny sieci Web należy dodać do zasad WIP dotyczących grupy i użytkownika. Podsumowanie pokazuje, które adresy URL witryn internetowych są dostępne dla aplikacji obsługujących funkcję WIP.

Podczas pracy z aplikacjami obsługującymi funkcję WIP i nieznanych aplikacji funkcji WIP zalecamy rozpoczęcie od opcji **Cichy** lub **Zezwalaj na przesłonięcia** i zweryfikowanie w małej grupie, czy na liście chronionych aplikacji znajdują się odpowiednie aplikacje. Po wykonaniu tych czynności można przełączyć na ostateczne zasady wymuszania, **Zablokowanie**.

### <a name="what-are-the-protection-modes"></a>Jakie są tryby ochrony?

#### <a name="block"></a>Zablokowanie
Funkcja WIP szuka niewłaściwych praktyk udostępniania danych i powstrzymuje użytkownika przed ukończeniem akcji. Zablokowane akcje mogą obejmować udostępnianie informacji aplikacjom nieobjętym firmową ochroną oraz udostępnianie danych firmowych innym osobom i urządzeniem poza organizacją.

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

1.  Wybierz ustawienie, a następnie wybierz pozycję **Zapisz**.

### <a name="use-wip-learning"></a>Korzystanie z opcji Uczenie funkcji WIP

1. Otwórz [witrynę Azure Portal](https://portal.azure.com). Wybierz pozycję **Wszystkie usługi**. Wpisz **Intune** w polu tekstowym filtru.

3. Wybierz pozycję **Intune** > **Aplikacje klienckie**.

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

Aby dowiedzieć się więcej na temat funkcji Windows Information Protection, zobacz [Protect your enterprise data using Windows Information Protection (Chronienie danych przedsiębiorstwa przy użyciu funkcji Windows Information Protection [WIP])](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).
