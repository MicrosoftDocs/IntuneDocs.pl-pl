---
title: Zasady zezwalania na aplikacje i blokowania w usłudze Microsoft Intune dla systemu Samsung Knox
titleSuffix: ''
description: Utwórz profil niestandardowy w celu zezwalania na aplikacje i blokowanie ich na urządzeniach z systemem Samsung Knox Standard.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/5/2018
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a8486e121e6497eefdd2d098c2421f2f3b53b8a2
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71734352"
---
# <a name="use-custom-policies-in-microsoft-intune-to-allow-and-block-apps-for-samsung-knox-standard-devices"></a>Używanie zasad niestandardowych w usłudze Microsoft Intune w celu zezwalania na aplikacje i blokowanie ich dla urządzeń z systemem Samsung Knox Standard 

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Użyj procedur opisanych w tym artykule, aby utworzyć niestandardowe zasady usługi Microsoft Intune, co powoduje utworzenie następujących elementów:

- Lista aplikacji, których uruchamianie na urządzeniu jest zablokowane. Uruchamianie aplikacji na tej liście jest blokowane, nawet jeśli były one już zainstalowane, gdy zasady zostały zastosowane.
- Lista aplikacji, które użytkownicy urządzenia mogą instalować ze sklepu Google Play. Można zainstalować tylko aplikacje na liście. Nie będzie można instalować żadnych innych aplikacji ze sklepu.

Tych ustawień można używać tylko na urządzeniach z systemem Samsung Knox Standard.

## <a name="create-an-allowed-or-blocked-app-list"></a>Tworzenie listy dozwolonych lub zablokowanych aplikacji

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. W okienku **Intune** wybierz pozycję **Konfiguracja urządzeń**.
2. W okienku **Konfiguracja urządzeń** wybierz pozycję **Zarządzaj** > **Profile**.
2. W okienku z listą profilów wybierz pozycję **Utwórz profil**.
3. W okienku **Tworzenie profilu** wprowadź wartość w polach **Nazwa** i **Opis** (opcjonalnie) dotyczących profilu urządzenia.
2. Wybierz dla pozycji **Platforma** wartość **Android**, a dla pozycji **Typ profilu** wartość **Niestandardowy**.
3. Kliknij pozycję **Ustawienia**.
3. W okienku **Niestandardowe ustawienia OMA-URI** wybierz pozycję **Dodaj**.
4. W oknie dialogowym **Dodawanie lub edytowanie ustawienia OMA-URI** określ następujące ustawienia:

   W przypadku listy aplikacji, których uruchamianie na urządzeniu jest zablokowane:

   - **Nazwa** — wprowadź **PreventStartPackages**.
   - **Opis** — podaj opcjonalny opis, taki jak „Lista aplikacji, których uruchamianie jest zablokowane”.
   - **Typ danych** — wybierz z listy rozwijanej opcję **Ciąg**.
   - **OMA-URI** — wpisz ciąg **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages**
   - **Wartość** — wprowadź listę nazw pakietów aplikacji, na których uruchamianie chcesz zezwolić. Jako ogranicznika możesz użyć znaku **; : ,** lub **|** . (Przykład: pakiet1;pakiet2;)

   Lista aplikacji, które użytkownicy mogą instalować ze sklepu Google Play, przy czym wszystkie inne aplikacje są wykluczone:
   - **Nazwa** — podaj ciąg **AllowInstallPackages**.
   - **Opis**— wpisz opcjonalny opis, taki jak „Lista aplikacji, które użytkownicy mogą instalować ze sklepu Google Play”.
   - **Typ danych** — wybierz z listy rozwijanej opcję **Ciąg**.
   - **OMA-URI** — wpisz ciąg **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages**
   - **Wartość** — wprowadź listę nazw pakietów aplikacji, na których uruchamianie chcesz zezwolić. Jako ogranicznika możesz użyć znaku **; : ,** lub **|** . (Przykład: pakiet1;pakiet2;)

4. Kliknij przycisk **OK**, a następnie w okienku **Tworzenie profilu** wybierz pozycję **Utwórz**.

>[!TIP]
> Identyfikator pakietu aplikacji możesz znaleźć, przechodząc do aplikacji w sklepie Google Play. Identyfikator pakietu znajduje się w adresie URL strony aplikacji. Na przykład identyfikator pakietu aplikacji Microsoft Word to **com.microsoft.office.word**.

Gdy docelowe urządzenie nawiąże połączenie następny raz, zostaną zastosowane ustawienia aplikacji.


<!---## Assign the custom profile--->