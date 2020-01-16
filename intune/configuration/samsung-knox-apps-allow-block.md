---
title: Zasady zezwalania na aplikacje i blokowania w usłudze Microsoft Intune dla systemu Samsung Knox
titleSuffix: ''
description: Utwórz profil niestandardowy w celu zezwalania na aplikacje i blokowanie ich na urządzeniach z systemem Samsung Knox Standard.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/18/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4b83a0339d87375502159467af323fceae5eb6e2
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2019
ms.locfileid: "75207081"
---
# <a name="use-custom-policies-in-microsoft-intune-to-allow-and-block-apps-for-samsung-knox-standard-devices"></a>Używanie zasad niestandardowych w usłudze Microsoft Intune w celu zezwalania na aplikacje i blokowanie ich dla urządzeń z systemem Samsung Knox Standard 

Użyj procedur opisanych w tym artykule, aby utworzyć niestandardowe zasady usługi Microsoft Intune, co powoduje utworzenie następujących elementów:

- Lista aplikacji, których uruchamianie na urządzeniu jest zablokowane. Uruchamianie aplikacji na tej liście jest blokowane, nawet jeśli były one już zainstalowane, gdy zasady zostały zastosowane.
- Lista aplikacji, które użytkownicy urządzenia mogą instalować ze sklepu Google Play. Można zainstalować tylko aplikacje na liście. Nie będzie można instalować żadnych innych aplikacji ze sklepu.

Tych ustawień można używać tylko na urządzeniach z systemem Samsung Knox Standard.

## <a name="create-an-allowed-or-blocked-app-list"></a>Tworzenie listy dozwolonych lub zablokowanych aplikacji

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Urządzenia** > **Profile konfiguracji** > **Utwórz profil**.
3. Podaj następujące ustawienia:

    - **Nazwa**: Wprowadź opisową nazwę profilu. Nadaj nazwę profilom, aby można było je później łatwo rozpoznać. Na przykład dobrą nazwą profilu jest **profilu niestandardowego systemu Windows Phone**.
    - **Opis**: Wprowadź opis ułatwiający identyfikację ustawienia oraz zawierający inne ważne szczegóły.
    - **Platforma**: — wybierz opcję **Android**.
    - **Typ profilu**: Wybierz **niestandardowe**.

4. W obszarze **Niestandardowe ustawienia OMA-URI** wybierz pozycję **Dodaj**. Podaj następujące ustawienia:

    W przypadku listy aplikacji, których uruchamianie na urządzeniu jest zablokowane:

    - **Nazwa**: Podaj ciąg **PreventStartPackages**.
    - **Opis**: Wprowadź opis, który zawiera omówienie ustawienia oraz inne istotne informacje ułatwiające wyszukanie profilu. Na przykład wprowadź **listę aplikacji, dla których zablokowano uruchamianie**.
    - **OMA-URI** (rozróżniana jest wielkość liter): Wpisz ciąg **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages**.
    - **typu danych**: Wybierz **ciąg**.
    - **Wartość**: Podaj listę nazw pakietów aplikacji, na których uruchamianie chcesz zezwolić. Jako ogranicznika możesz użyć znaku `;`, `:` lub `|`. Na przykład wprowadź `package1;package2;`.

   Lista aplikacji, które użytkownicy mogą instalować ze sklepu Google Play, przy czym wszystkie inne aplikacje są wykluczone:

    - **Nazwa**: Podaj ciąg **AllowInstallPackages**.
    - **Opis**: Wprowadź opis, który zawiera omówienie ustawienia oraz inne istotne informacje ułatwiające wyszukanie profilu. Na przykład wprowadź **listę aplikacji, które użytkownicy mogą instalować z Google Play**.
    - **OMA-URI** (rozróżniana jest wielkość liter): Wpisz ciąg **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages**.
    - **typu danych**: Wybierz **ciąg**.
    - **Wartość**: Podaj listę nazw pakietów aplikacji, na których uruchamianie chcesz zezwolić. Jako ogranicznika możesz użyć znaku `;`, `:` lub `|`. Na przykład wprowadź `package1;package2;`.

5. Wybierz przycisk **OK**, aby zapisać zmiany.
6. Po zakończeniu wybierz pozycję **OK** > **Utwórz**, aby utworzyć profil usługi Intune. Po utworzeniu profil będzie widoczny na liście **Urządzenia — profile konfiguracji**.

>[!TIP]
> Identyfikator pakietu aplikacji możesz znaleźć, przechodząc do aplikacji w sklepie Google Play. Identyfikator pakietu znajduje się w adresie URL strony aplikacji. Na przykład identyfikator pakietu aplikacji Microsoft Word to **com.microsoft.office.word**.

Gdy docelowe urządzenie nawiąże połączenie następny raz, zostaną zastosowane ustawienia aplikacji.

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje jeszcze żadnych czynności. W dalszej części [przypiszesz profil](../device-profile-assign.md) i będziesz [monitorować jego stan](device-profile-monitor.md).
