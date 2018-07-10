---
title: Ustawienia niestandardowe dla urządzeń z systemem Windows 10 w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Konfiguruj ustawienia niestandardowe OMA-URI na urządzeniach z systemem Windows 10 przy użyciu niestandardowego profilu w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bdbb6643a4ee8aace0db22cd7f9189f7ac6445f0
ms.sourcegitcommit: ada99fefe9a612ed753420116f8c801ac4bf0934
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/19/2018
ms.locfileid: "36232830"
---
# <a name="custom-oma-uri-settings-for-windows-10-devices---intune"></a>Niestandardowe ustawienia OMA-URI dla urządzeń z systemem Windows 10 — Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Profil **niestandardowy** usługi Microsoft Intune dla systemów Windows 10 i Windows 10 Mobile umożliwia wdrożenie ustawień OMA-URI (Open Mobile Alliance Uniform Resource Identifier). Tych ustawień można użyć do sterowania funkcjami na urządzeniach. System Windows 10 zapewnia dostęp do wielu ustawień dostawcy usług konfiguracji, takich jak [Dostawca usług konfiguracji zasad](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).

Jeśli szukasz konkretnego ustawienia, pamiętaj, że [profil ograniczeń urządzenia z systemem Windows 10](device-restrictions-windows-10.md) zawiera wiele ustawień, które są wbudowane w usłudze Intune i nie wymagają wartości niestandardowych.

## <a name="configure-custom-settings"></a>Konfigurowanie ustawień niestandardowych

1. Utwórz nowy profil konfiguracji, używając typu profilu **Niestandardowy**. Odpowiednią procedurę można znaleźć w temacie [Jak skonfigurować niestandardowe ustawienia urządzenia](custom-settings-configure.md).
2. W obszarze **Niestandardowe ustawienia OMA-URI** wybierz pozycję **Dodaj**, aby utworzyć nowe ustawienie. Możesz również kliknąć przycisk **Eksportuj**, aby utworzyć listę wszystkich wartości skonfigurowanych w pliku wartości rozdzielanych przecinkami (.csv).
3. Dla każdego ustawienia OMA-URI, które chcesz dodać, wprowadź następujące informacje:

- **Nazwa**: wprowadź unikatową nazwę ustawienia OMA-URI, aby ułatwić jego identyfikację na liście ustawień.
- **Opis**: opcjonalnie wprowadź opis ustawienia.
- **OMA-URI (z uwzględnieniem wielkości liter)**: wprowadź identyfikator OMA-URI, dla którego chcesz podać ustawienie.
- **Typ danych**: Wybierz spośród opcji:
  - **Ciąg**
  - **Ciąg (XML)**
  - **Data i godzina**
  - **Liczba całkowita**
  - **Liczba zmiennoprzecinkowa**
  - **Wartość logiczna**
  - **Base64**
- **Wartość**: wprowadź wartość lub plik w celu skojarzenia z wprowadzonym identyfikatorem OMA-URI.

4. Gdy wszystko będzie gotowe, wybierz pozycję **OK**. W obszarze **Tworzenie profilu** wybierz pozycję **Utwórz**. Profil zostanie utworzony i wyświetlony na liście profilów.

## <a name="example"></a>Przykład
W poniższym przykładzie włączono ustawienie **Connectivity/AllowVPNOverCellular**. To ustawienie pozwala urządzeniu z systemem Windows 10 na otwarcie połączenia sieci VPN w sieci komórkowej.

![Przykład zasad niestandardowych zawierających ustawienia sieci VPN](./media/custom-policy-example.png)

## <a name="find-the-policies-you-can-configure"></a>Wyszukiwanie zasad, które można skonfigurować

Pełna lista wszystkich dostawców usług konfiguracji obsługiwanych w systemie Windows 10 jest przedstawiona w artykule [Configuration service provider reference (Informacje dotyczące dostawcy usług konfiguracji)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference).

Nie wszystkie ustawienia są zgodne ze wszystkimi wersjami systemu Windows 10. Artykuł [Configuration service provider reference (Informacje dotyczące dostawcy usług konfiguracji)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) zawiera informacje o tym, które wersje są obsługiwane przez każdego dostawcę usług konfiguracji.

Ponadto usługa Intune nie obsługuje wszystkich wymienionych ustawień. Aby dowiedzieć się, czy usługa Intune obsługuje dane ustawienie, otwórz artykuł dotyczący tego ustawienia. Na stronie każdego ustawienia znajdują się informacje dotyczące obsługiwanych operacji. Aby ustawienie mogło być używane z usługą Intune, musi obsługiwać operacje **Dodaj** lub **Zastąp**.
