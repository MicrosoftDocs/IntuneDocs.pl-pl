---
title: "Ustawienia niestandardowe urządzeń z systemem Windows Holographic for Business w usłudze Intune"
titlesuffix: Azure portal
description: "Informacje dotyczące ustawień, których można używać w niestandardowym profilu systemu Holographic for Business."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 1/24/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ae46aef10ca294637a4d433ce273d3c53e695d64
ms.sourcegitcommit: 93622d740cbd12043eedc25a9699cc4256e23e7e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2018
---
# <a name="custom-device-settings-for-windows-holographic-for-business-devices-in-microsoft-intune"></a>Niestandardowe ustawienia urządzenia z systemem Windows Holographic for Business w usłudze Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

 Profil **niestandardowy** usługi Microsoft Intune dla systemu Windows Holographic for Business umożliwia wdrożenie ustawień OMA-URI (Open Mobile Alliance Uniform Resource Identifier), których można użyć do sterowania funkcjami na urządzeniach. System Windows Holographic for Business udostępnia wiele ustawień dostawców usługi konfiguracji (CSP). Aby zapoznać się z omówieniem dostawcy usługi konfiguracji, zobacz [Introduction to configuration service providers (CSPs) for IT pros](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers) (Wprowadzenie do dostawców usługi konfiguracji dla specjalistów IT). Aby uzyskać informacje o konkretnym dostawcy usługi konfiguracji obsługiwanym w systemie Windows Holographic, zobacz [CSPs supported in Windows Holographic](https://docs.microsoft.com/en-us/windows/client-management/mdm/configuration-service-provider-reference#hololens) (Dostawcy usługi konfiguracji obsługiwani w systemie Windows Holographic).

Jeśli szukasz konkretnego ustawienia, pamiętaj, że [profil ograniczeń urządzenia z systemem Windows Holographic for Business](device-restrictions-windows-holographic.md) zawiera wiele wbudowanych ustawień i nie wymaga określenia wartości niestandardowych.

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
5. Gdy skończysz, wróć do bloku **Utwórz profil** i kliknij pozycję **Utwórz**.
Profil zostanie utworzony i wyświetlony w bloku listy profilów.

## <a name="supported-custom-settings"></a>Obsługiwane ustawienia niestandardowe

System Windows Holographic for Business obsługuje następujące ustawienia niestandardowe:


|Nazwa ustawienia|Identyfikator URI OMA|Typ danych  |
|---------|---------|---------|
|AllowFastReconnect     |./Vendor/MSFT/Policy/Config/Authentication/AllowFastReconnect|Liczba całkowita (0 — niedozwolone, 1 — dozwolone)|
|AllowVPN     |./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Liczba całkowita (0 — niedozwolone, 1 — dozwolone)|



## <a name="how-to-find-the-policies-you-can-configure"></a>Jak znaleźć zasady, które można skonfigurować

W tabeli [CSPs supported in Windows Holographic](https://docs.microsoft.com/en-us/windows/client-management/mdm/configuration-service-provider-reference#hololens) (Dostawcy usługi konfiguracji obsługiwani w systemie Windows Holographic) znajduje się pełna lista wszystkich dostawców usługi konfiguracji (CSP) obsługiwanych w systemie Windows Holographic. Nie wszystkie ustawienia są zgodne ze wszystkimi wersjami systemu Windows Holographic. Table w temacie poświęconym systemowi Windows zawiera informacje o tym, które wersje są obsługiwane w przypadku każdego z dostawców usług konfiguracji.

Ponadto usługa Intune nie obsługuje wszystkich ustawień wymienionych w temacie. Aby dowiedzieć się, czy usługa Intune obsługuje dane ustawienie, otwórz temat dotyczący tego ustawienia. Na stronie każdego ustawienia znajdują się informacje dotyczące obsługiwanych operacji. Aby ustawienie mogło być używane z usługą Intune, musi obsługiwać operacje **Dodaj** lub **Zastąp**.


