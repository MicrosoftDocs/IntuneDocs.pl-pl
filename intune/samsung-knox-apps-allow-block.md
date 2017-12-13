---
title: "Zasady zezwalania na aplikacje i blokowania ich na urządzeniach z systemem Samsung KNOX w usłudze Intune"
titlesuffix: Azure portal
description: "Tworzenie profilu niestandardowego w celu blokowania aplikacji na urządzeniach z systemem Samsung KNOX Standard lub zezwalania na nie."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: aaa85347dc647658faf981e93d7fb0ea60c9e296
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/12/2017
---
# <a name="use-custom-policies-to-allow-and-block-apps-for-samsung-knox-standard-devices-in-microsoft-intune"></a>Użycie niestandardowych zasad do zezwalania na aplikacje i blokowania ich na urządzeniach z systemem Samsung KNOX Standard w usłudze Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Użyj procedur opisanych w tym temacie, aby utworzyć niestandardowe zasady usługi Microsoft Intune, co powoduje utworzenie następujących elementów:

- Lista aplikacji, których uruchamianie na urządzeniu jest zablokowane. Uruchamianie aplikacji na tej liście jest blokowane, nawet jeśli były one już zainstalowane, gdy zasady zostały zastosowane.
- Lista aplikacji, które użytkownicy urządzenia mogą instalować ze sklepu Google Play. Można zainstalować tylko aplikacje na liście. Nie będzie można instalować żadnych innych aplikacji ze sklepu.

Tych ustawień można używać tylko w przypadku urządzeń z systemem Samsung KNOX Standard.

## <a name="create-an-allowed-or-blocked-app-list"></a>Tworzenie listy dozwolonych lub zablokowanych aplikacji

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Konfiguracja urządzeń**.
2. W bloku **Konfiguracja urządzeń** wybierz kolejno pozycje **Zarządzaj** > **Profile**.
2. W bloku listy profilów wybierz pozycję **Utwórz profil**.
3. W bloku **Utwórz profil** uzupełnij pola **Nazwa** i **Opis** (opcjonalnie) odnoszące się do profilu urządzenia.
2. Wybierz dla pozycji **Typ platformy** wartość **Android**, a dla typu profilu wartość **Niestandardowy**.
3. Kliknij pozycję **Ustawienia**.
3. W bloku **Niestandardowe ustawienia OMA-URI** wybierz pozycję **Dodaj**.
4. W oknie dialogowym **Dodawanie lub edytowanie ustawienia OMA-URI** uzupełnij następujące pozycje:

### <a name="for-a-list-of-apps-that-are-blocked-from-running-on-the-device"></a>W przypadku listy aplikacji, których uruchamianie na urządzeniu jest zablokowane:

- **Nazwa** — wprowadź **PreventStartPackages**.
- **Opis** — podaj opcjonalny opis, taki jak „Lista aplikacji, których uruchamianie jest zablokowane”.
-   **Typ danych** — wybierz z listy rozwijanej opcję **Ciąg**.
-   **OMA-URI** — wpisz ciąg **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages**
-   **Wartość** — wprowadź listę nazw pakietów aplikacji, na których uruchamianie chcesz zezwolić. Jako ogranicznika możesz użyć znaku **; : ,** lub **|**. (Przykład: pakiet1;pakiet2;)

### <a name="for-a-list-of-apps-that-users-are-allowed-to-install-from-the-google-play-store-while-excluding-all-other-apps"></a>Lista aplikacji, które użytkownicy mogą instalować ze sklepu Google Play, przy czym wszystkie inne aplikacje są wykluczone:
- **Nazwa** — podaj ciąg **AllowInstallPackages**.
- **Opis**— wpisz opcjonalny opis, taki jak „Lista aplikacji, które użytkownicy mogą instalować ze sklepu Google Play”.
- **Typ danych** — wybierz z listy rozwijanej opcję **Ciąg**.
- **OMA-URI** — wpisz ciąg **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages**
- **Wartość** — wprowadź listę nazw pakietów aplikacji, na których uruchamianie chcesz zezwolić. Jako ogranicznika możesz użyć znaku **; : ,** lub **|**. (Przykład: pakiet1;pakiet2;)

4. Kliknij przycisk **OK**, a następnie w bloku **Utwórz profil** wybierz pozycję **Utwórz**.

>[!TIP]
> Identyfikator pakietu aplikacji możesz znaleźć, przechodząc do aplikacji w sklepie Google Play. Identyfikator pakietu znajduje się w adresie URL strony aplikacji. Na przykład identyfikator pakietu aplikacji Microsoft Word to **com.microsoft.office.word**.

Gdy docelowe urządzenie nawiąże połączenie następny raz, zostaną zastosowane ustawienia aplikacji.


<!---## Assign the custom profile--->
