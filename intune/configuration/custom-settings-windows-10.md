---
title: Dodawanie ustawień niestandardowych dla urządzeń z systemem Windows 10 w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dodaj lub utwórz profil niestandardowy w celu użycia ustawień identyfikatora URI OMA dla urządzeń z systemem Windows 10 w usłudze Microsoft Intune. Użyj profilu niestandardowego, aby dodać ustawienia niestandardowe.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2018
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e8f896f514223cdb5e5faae5f781421d37fffd01
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72495363"
---
# <a name="use-custom-settings-for-windows-10-devices-in-intune"></a>Używanie ustawień niestandardowych dla urządzeń z systemem Windows 10 w usłudze Intune

Za pomocą usługi Microsoft Intune można dodawać lub tworzyć ustawienia niestandardowe dla urządzeń z systemem Windows 10 przy użyciu „profili niestandardowych”. Profile niestandardowe to funkcja w usłudze Intune. Służą one do dodawania ustawień i funkcji urządzeń, które nie są wbudowane w usłudze Intune.

Profile niestandardowe systemu Windows 10 używają ustawień jednolitego identyfikatora zasobów Open Mobile Alliance (OMA-URI, Open Mobile Alliance Uniform Resource Identifier) w celu skonfigurowania różnych funkcji. Te ustawienia są zwykle używane przez producentów urządzeń przenośnych w celu kontrolowania funkcji na urządzeniu. 

System Windows 10 zapewnia dostęp do wielu ustawień dostawcy usług konfiguracji, takich jak [Dostawca usług konfiguracji zasad](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).

Jeśli szukasz określonego ustawienia, pamiętaj, że [profil ograniczeń urządzenia z systemem Windows 10](device-restrictions-windows-10.md) zawiera wiele wbudowanych ustawień. Dzięki temu być może nie trzeba będzie wprowadzać wartości niestandardowych.

Ten artykuł zawiera następujące informacje:

- Jak utworzyć profil niestandardowy dla urządzeń z systemem Windows 10
- Lista zalecanych ustawień identyfikatora OMA-URI
- Przykład profilu niestandardowego, który otwiera połączenie sieci VPN

## <a name="create-the-profile"></a>Tworzenie profilu

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz pozycję **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Podaj następujące ustawienia:

    - **Nazwa**: wprowadź nazwę profilu, na przykład `windows 10 custom profile`.
    - **Opis:** wprowadź opis profilu.
    - **Platforma**: wybierz **system Windows 10 lub nowszy**.
    - **Typ profilu**: wybierz pozycję **Niestandardowy**.

4. W obszarze **Niestandardowe ustawienia OMA-URI** wybierz pozycję **Dodaj**. Podaj następujące ustawienia:

    - **Nazwa**: wprowadź unikatową nazwę ustawienia OMA-URI, aby ułatwić jego identyfikację na liście ustawień.
    - **Opis elementu**: wprowadź opis ułatwiający identyfikację ustawienia oraz zawierający inne ważne szczegóły.
    - **OMA-URI** (z uwzględnieniem wielkości liter): wprowadź identyfikator OMA-URI, którego chcesz użyć jako ustawienia.
    - **Typ danych**: wprowadź typ danych używany w przypadku tego ustawienia identyfikatora OMA-URI. Dostępne opcje:

        - String
        - Ciąg (plik XML)
        - Data i godzina
        - Integer
        - Liczba zmiennoprzecinkowa
        - Boolean
        - Base64 (plik)

    - **Wartość**: wprowadź wartość danych, którą chcesz skojarzyć z wprowadzonym identyfikatorem OMA-URI. Wartość zależy od wybranego typu danych. Jeśli na przykład wybrano opcję **Data i godzina**, wybierz wartość za pomocą selektora daty.

    Po dodaniu ustawień możesz wybrać pozycję **Eksportuj**. Wybranie pozycji **Eksportuj** spowoduje utworzenie listy wszystkich dodanych wartości w pliku wartości rozdzielanych przecinkami (CSV).

5. Wybierz przycisk **OK**, aby zapisać zmiany. W razie potrzeby kontynuuj dodawanie ustawień.
6. Po zakończeniu wybierz pozycję **OK** > **Utwórz**, aby utworzyć profil usługi Intune. Po utworzeniu profil będzie widoczny na liście **Konfiguracja urządzenia — profile**.

## <a name="example"></a>Przykład

W poniższym przykładzie włączono ustawienie **Connectivity/AllowVPNOverCellular**. To ustawienie pozwala urządzeniu z systemem Windows 10 na otwarcie połączenia sieci VPN w sieci komórkowej.

![Przykład zasad niestandardowych zawierających ustawienia sieci VPN](./media/custom-settings-windows-10/custom-policy-example.png)

## <a name="find-the-policies-you-can-configure"></a>Wyszukiwanie zasad, które można skonfigurować

Pełna lista wszystkich dostawców usług konfiguracji obsługiwanych w systemie Windows 10 znajduje się w artykule [Configuration service provider reference](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) (Informacje dotyczące dostawcy usług konfiguracji).

Nie wszystkie ustawienia są zgodne ze wszystkimi wersjami systemu Windows 10. Artykuł [Configuration service provider reference (Informacje dotyczące dostawcy usług konfiguracji)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) zawiera informacje o tym, które wersje są obsługiwane przez każdego dostawcę usług konfiguracji.

Ponadto usługa Intune nie obsługuje wszystkich ustawień wymienionych w artykule [Configuration service provider reference](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) (Informacje dotyczące dostawcy usług konfiguracji). Aby dowiedzieć się, czy usługa Intune obsługuje dane ustawienie, otwórz artykuł dotyczący tego ustawienia. Na stronie każdego ustawienia znajdują się informacje dotyczące obsługiwanych operacji. Aby ustawienie mogło być używane z usługą Intune, musi obsługiwać operacje **Dodaj**, **Zastąp** i **Pobierz**. Jeśli wartość zwracana przez operację **Pobierz** jest niezgodna z wartością dostarczoną przez operacje **Dodaj** lub **Zastąp**, usługa Intune zgłasza błąd zgodności.

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje jeszcze żadnych czynności. Teraz należy [przypisać profil](device-profile-assign.md).
