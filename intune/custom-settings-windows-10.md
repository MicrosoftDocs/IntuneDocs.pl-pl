---
title: "Ustawienia niestandardowe dla urządzeń z systemem Windows 10 w usłudze Intune"
titlesuffix: Azure portal
description: "Informacje dotyczące ustawień, których można używać w niestandardowym profilu systemu Windows 10."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 05/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7bcea136-7260-4042-b21b-c7dab86b380d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0758aed9672c4d1279c5deb24e23beea728df81d
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/12/2017
---
# <a name="custom-device-settings-for-windows-10-devices-in-microsoft-intune"></a>Ustawienia niestandardowe dla urządzeń z systemem Windows 10 w usłudze Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

 Profil **niestandardowy** usługi Microsoft Intune dla systemów Windows 10 i Windows 10 Mobile umożliwia wdrożenie ustawień OMA-URI (Open Mobile Alliance Uniform Resource Identifier), których można użyć do sterowania funkcjami na urządzeniach. System Windows 10 zapewnia dostęp do wielu ustawień dostawcy usług konfiguracji, np. [Dostawca usługi konfiguracji zasad](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).
Jeśli szukasz konkretnego ustawienia, pamiętaj, że [profil ograniczeń urządzenia z systemem Windows 10](device-restrictions-windows-10.md) zawiera wiele ustawień, które są wbudowane w usłudze Intune i nie wymagają określenia wartości niestandardowych.

1. Aby rozpocząć pracę, postępuj zgodnie z instrukcjami w artykule [How to configure custom device settings in Microsoft Intune](custom-settings-configure.md) (Jak skonfigurować niestandardowe ustawienia urządzenia w usłudze Microsoft Intune).
2. W bloku **Tworzenie profilu** wybierz pozycję **Ustawienia**, aby dodać co najmniej jedno ustawienie OMA-URI.
3. W bloku **Ustawienia niestandardowe OMA-URI** kliknij przycisk **Dodaj**, aby dodać nową wartość. Możesz również kliknąć przycisk **Eksportuj**, aby utworzyć listę wszystkich wartości skonfigurowanych w pliku wartości rozdzielanych przecinkami (.csv).
4. Dla każdego ustawienia OMA-URI, które chcesz dodać, wprowadź następujące informacje. Lista w tym temacie zawiera informacje dotyczące ustawień, których można użyć:
    - **Nazwa ustawienia** — Wprowadź unikatową nazwę dla ustawienia OMA-URI, aby ułatwić jego identyfikację na liście ustawień.
    - **Opis** — Opcjonalnie wprowadź opis ustawienia.
    - **Typ danych** — Wybierz spośród opcji:
        - **Ciąg**
        - **Ciąg (XML)**
        - **Data i godzina**
        - **Liczba całkowita**
        - **Liczba zmiennoprzecinkowa**
        - **Wartość logiczna**
    - **OMA-URI (z uwzględnieniem wielkości liter)** — Określ identyfikator OMA-URI, dla którego chcesz podać ustawienie.
    - **Wartość** — Określ wartość, która będzie kojarzona z określonym wcześniej identyfikatorem OMA-URI.
5. Gdy skończysz, wróć do bloku **Utwórz profil** i wybierz pozycję **Utwórz**.
Profil zostanie utworzony i wyświetlony w bloku listy profilów.

## <a name="example"></a>Przykład
Na poniższym zrzucie ekranu ustawienie **Connectivity/AllowVPNOverCellular** jest włączone. Pozwala to urządzeniu z systemem Windows 10 na otwarcie połączenia sieci VPN w sieci komórkowej.

> ![Przykład zasad niestandardowych zawierających ustawienia sieci VPN](./media/custom-policy-example.png)


## <a name="how-to-find-the-policies-you-can-configure"></a>Jak znaleźć zasady, które można skonfigurować

Pełna lista wszystkich dostawców usług konfiguracji (CSP) obsługiwanych w systemie Windows 10 jest przedstawiona w artykule [Configuration service provider reference](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) (Informacje dotyczące dostawcy usługi konfiguracji) w bibliotece dokumentacji systemu Windows.

Nie wszystkie ustawienia są zgodne ze wszystkimi wersjami systemu Windows 10. Table w temacie poświęconym systemowi Windows zawiera informacje o tym, które wersje są obsługiwane w przypadku każdego z dostawców usług konfiguracji.

Ponadto usługa Intune nie obsługuje wszystkich ustawień wymienionych w temacie. Aby dowiedzieć się, czy usługa Intune obsługuje dane ustawienie, otwórz temat dotyczący tego ustawienia. Na stronie każdego ustawienia znajdują się informacje dotyczące obsługiwanych operacji. Aby ustawienie mogło być używane z usługą Intune, musi obsługiwać operacje **Dodaj** lub **Zastąp**.


