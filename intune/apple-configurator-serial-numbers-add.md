---
title: "Dodawanie numerów seryjnych programu Apple Configurator"
titleSuffix: Intune on Azure
description: "Informacje dotyczące dodawania numerów seryjnych do urządzeń firmowych z systemem iOS przy użyciu programu Apple Configurator."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d408aa38-7d1e-40df-9067-246e53f6e26f
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 689008f278e676ce0bab075c6ad6b54748e56313
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2017
---
# <a name="add-apple-configurator-serial-numbers"></a>Dodawanie numerów seryjnych programu Apple Configurator

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

W krokach tych opisano dodawanie numerów seryjnych do usługi Intune w przypadku [rejestracji urządzeń firmowych z systemem iOS przy użyciu programu Apple Configurator i Asystenta ustawień](apple-configurator-setup-assistant-enroll-ios.md). Można dodawać numery seryjne pojedynczo lub załadować plik wartości rozdzielonych przecinkami (CSV) z numerami seryjnymi. Po dodaniu numerów seryjnych można do nich przypisać profil. Profil zawiera określone ustawienia zarządzania, które mają być zastosowane do urządzeń.

Inne metody rejestracji urządzeń z systemem iOS zostały opisane w temacie [Choose how to enroll iOS devices in Intune](enrollment-method-choose-ios.md) (Wybieranie sposobu rejestrowania urządzeń z systemem iOS w usłudze Intune).

**Aby dodać numery seryjne programu Apple Configurator do usługi Intune**

1. Utwórz listę wartości rozdzielonych przecinkami (.csv) zawierającą dwie kolumny, bez nagłówka. Dodaj identyfikator IMEI w lewej kolumnie i szczegółowe informacje w prawej kolumnie. Obecnie maksymalna liczba wierszy na liście wynosi 500. W edytorze tekstu lista .csv wygląda następująco:

    F7TLWCLBX196, szczegóły urządzenia</br>
    DLXQPCWVGHMJ,szczegóły urządzenia

2. W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.

3.  W bloku Intune wybierz pozycję **Zarejestruj urządzenia**, a następnie pozycję **Rejestracja Apple**.

4. W obszarze **Zarządzanie ustawieniami rejestracji programu Apple Configurator** wybierz pozycję **Numery seryjne programu Apple Configurator**.

5. W bloku **Numery seryjne programu Apple Configurator** wybierz przycisk **Dodaj**.

6. W bloku **Dodaj numery seryjne** wybierz profil do zastosowania do importowanych numerów seryjnych. Jeśli importujesz plik z nowymi szczegółami, które zastąpią istniejące, wybierz opcję Zastąp szczegóły istniejących identyfikatorów, aby nowe szczegóły zastąpiły istniejące.

7. Przejdź do pliku .csv numerów seryjnych i wybierz przycisk **Dodaj**.

## <a name="assign-a-profile-to-specific-serial-numbers"></a>Przypisywanie profilu do określonych numerów seryjnych

Usługa Intune umożliwia przypisywanie profilów z dwóch różnych miejsc w portalu Azure. Można wykonać kroki poniżej lub przypisać profile z bloku Profile rejestracji programu Apple Configurator, w którym tworzy się profil (zobacz artykuł [Enroll iOS devices with Apple Configurator by using Setup Assistant](apple-configurator-setup-assistant-enroll-ios.md) (Rejestracja urządzeń z systemem iOS przy użyciu programu Apple Configurator i Asystenta ustawień). Możesz użyć kroków poniżej do przypisania profilu tylko, jeśli profil został już utworzony.

1. W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.

2. W bloku Intune wybierz pozycję **Zarejestruj urządzenia**, a następnie pozycję **Rejestracja Apple**.

3. W bloku **Numery seryjne programu Apple Configurator** wybierz numery seryjne, do których chcesz przypisać profil, a następnie wybierz pozycję **Przypisz profil**.

4. W bloku **Przypisz profil** wybierz profil, który chcesz przypisać, a następnie wybierz przycisk **Przypisz**.

## <a name="delete-serial-numbers"></a>Usuwanie numerów seryjnych
Zaimportowane wcześniej numery seryjne można usunąć. Numery seryjne można usunąć tylko wtedy, gdy urządzenie zostanie najpierw wyrejestrowane. Po usunięciu numeru seryjnego nie można użyć programu Apple Configurator za pomocą Asystenta ustawień, chyba że numer seryjny zostanie ponownie dodany.

## <a name="view-the-state-of-a-device"></a>Wyświetlanie stanu urządzenia
Numery seryjne urządzenia mogą mieć jeden z trzech stanów:

- Zarejestrowane — urządzenie jest zarejestrowane i połączyło się z usługą Intune
- Nie kontaktowano się — urządzenie nigdy nie połączyło się z usługą Intune.
- Oczekuje na zresetowanie — urządzenie jest zarejestrowane, ale wprowadzono zmianę (na przykład zmieniły się ustawienia rejestracji lub zastosowany profil DEP). W przypadku zmiany profilu DEP urządzenia zmiany nie są stosowane, dopóki urządzenie nie zostanie wyrejestrowane, a następnie zarejestrowane ponownie.

**Aby wyświetlić stan numeru seryjnego**

W bloku **Numery seryjne programu Apple Configurator** wybierz numer seryjny, którego stan chcesz zobaczyć, i poszukaj w obszarze elementu **Stan**.
