---
title: Ustawienia niestandardowe dla urządzeń z systemem Windows 10 w usłudze Microsoft Intune
titlesuffix: ''
description: Informacje dotyczące ustawień niestandardowych, które można skonfigurować w niestandardowym profilu systemu Windows 10.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/1/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 36705c49a55c88c41470feaad14520e900dcb3dd
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2018
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-windows-10"></a>Ustawienia niestandardowe urządzeń z systemem Windows 10 w usłudze Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

 Profil **niestandardowy** usługi Microsoft Intune dla systemów Windows 10 i Windows 10 Mobile umożliwia wdrożenie ustawień OMA-URI (Open Mobile Alliance Uniform Resource Identifier), których można użyć do sterowania funkcjami na urządzeniach. System Windows 10 zapewnia dostęp do wielu ustawień dostawcy usług konfiguracji, np. [Dostawca usługi konfiguracji zasad](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).
Jeśli szukasz konkretnego ustawienia, pamiętaj, że [profil ograniczeń urządzenia z systemem Windows 10](device-restrictions-windows-10.md) zawiera wiele ustawień, które są wbudowane w usłudze Intune i nie wymagają określenia wartości niestandardowych.

## <a name="configure-custom-settings"></a>Konfigurowanie ustawień niestandardowych

1. Aby rozpocząć pracę, postępuj zgodnie z instrukcjami w artykule [How to configure custom device settings in Microsoft Intune](custom-settings-configure.md) (Jak skonfigurować niestandardowe ustawienia urządzenia w usłudze Microsoft Intune).
1. W okienku **Ustawienia niestandardowe OMA-URI** kliknij przycisk **Dodaj**, aby dodać nową wartość. Możesz również kliknąć przycisk **Eksportuj**, aby utworzyć listę wszystkich wartości skonfigurowanych w pliku wartości rozdzielanych przecinkami (.csv).
1. Dla każdego ustawienia OMA-URI, które chcesz dodać, wprowadź następujące informacje. Lista w tym artykule zawiera informacje dotyczące ustawień, których można użyć:
    - **Nazwa** — wprowadź unikatową nazwę ustawienia OMA-URI, aby ułatwić jego identyfikację na liście ustawień.
    - **Opis** — opcjonalnie wprowadź opis ustawienia.
    - **OMA-URI (z uwzględnieniem wielkości liter)** — Określ identyfikator OMA-URI, dla którego chcesz podać ustawienie.
    - **Typ danych** — Wybierz spośród opcji:
        - **Ciąg**
        - **Ciąg (XML)**
        - **Data i godzina**
        - **Liczba całkowita**
        - **Liczba zmiennoprzecinkowa**
        - **Wartość logiczna**
        - **Base64**
    - **Wartość** — określ wartość lub plik, który będzie skojarzony z określonym wcześniej identyfikatorem OMA-URI.
1. Gdy skończysz, wybierz opcję **OK**, wróć do okienka **Tworzenie profilu** i wybierz pozycję **Utwórz**.
Profil zostanie utworzony i wyświetlony w okienku z listą profilów.

## <a name="example"></a>Przykład
Na poniższym zrzucie ekranu ustawienie **Connectivity/AllowVPNOverCellular** jest włączone. Pozwala to urządzeniu z systemem Windows 10 na otwarcie połączenia sieci VPN w sieci komórkowej.

> ![Przykład zasad niestandardowych zawierających ustawienia sieci VPN](./media/custom-policy-example.png)


## <a name="how-to-find-the-policies-you-can-configure"></a>Jak znaleźć zasady, które można skonfigurować

Pełna lista wszystkich dostawców usług konfiguracji (CSP) obsługiwanych w systemie Windows 10 jest przedstawiona w artykule [Configuration service provider reference](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) (Informacje dotyczące dostawcy usługi konfiguracji) w bibliotece dokumentacji systemu Windows.

Nie wszystkie ustawienia są zgodne ze wszystkimi wersjami systemu Windows 10. Tabela w artykule poświęconym systemowi Windows zawiera informacje o wersjach obsługiwanych w przypadku poszczególnych dostawców usług konfiguracji.

Ponadto usługa Intune nie obsługuje wszystkich ustawień wymienionych w artykule. Aby dowiedzieć się, czy usługa Intune obsługuje dane ustawienie, otwórz artykuł dotyczący tego ustawienia. Na stronie każdego ustawienia znajdują się informacje dotyczące obsługiwanych operacji. Aby ustawienie mogło być używane z usługą Intune, musi obsługiwać operacje **Dodaj** lub **Zastąp**.
