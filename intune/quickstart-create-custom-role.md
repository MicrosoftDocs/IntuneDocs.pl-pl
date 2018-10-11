---
title: Przewodnik Szybki start — tworzenie i przypisywanie roli niestandardowej w usłudze Intune
description: Przewodnik Szybki start — tworzenie i przypisywanie roli niestandardowej w usłudze Intune dla menedżera urządzeń zdalnych.
services: microsoft-intune
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: quickstart
ms.date: 09/21/2018
ms.author: erikje
ms.openlocfilehash: 66426e9e22c2624b9828440906e3b1b947f4b60a
ms.sourcegitcommit: 27eed5aba5c8bfafb079171081b68f75a6cbffaf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2018
ms.locfileid: "46581805"
---
# <a name="quickstart-create-and-assign-a-custom-role"></a>Przewodnik Szybki start: tworzenie i przypisywanie roli niestandardowej

W tym przewodniku Szybki start dotyczącym usługi Intune utworzysz rolę niestandardową z określonymi uprawnieniami dla działu operacji zabezpieczeń. Następnie przypiszesz tę rolę grupie takich operatorów. Istnieje kilka ról domyślnych, których można używać od razu. Jednak tworząc role niestandardowe, takie jak ta, uzyskujesz precyzyjną kontrolę nad dostępem do wszystkich części systemu zarządzania urządzeniami przenośnymi.

Jeśli nie masz subskrypcji usługi Intune, [utwórz konto bezpłatnej wersji próbnej](free-trial-sign-up.md).

## <a name="prerequisites"></a>Wymagania wstępne

- Aby zrealizować zadania w tym przewodniku Szybki start, musisz [utworzyć grupę](quickstart-create-group.md).

## <a name="sign-in-to-intune"></a>Logowanie się do usługi Intune

Zaloguj się w usłudze [Intune](https://aka.ms/intuneportal) jako administrator globalny lub administrator usługi Intune.

## <a name="create-a-custom-role"></a>Tworzenie roli niestandardowej

Podczas tworzenia roli niestandardowej można ustawić uprawnienia dla różnych działań. Dla roli operacji zabezpieczeń ustawimy kilka uprawnień do odczytu, aby operator mógł przeglądać zasady i konfiguracje urządzenia.

1. W usłudze Intune wybierz pozycję **Role** > **Wszystkie role** > **Dodaj**.
![Przeglądarka](media/quickstart-create-custom-role/add-custom-role.png)
2. W obszarze **Dodaj rolę niestandardową** w polu **Nazwa** wprowadź tekst *Security operations* (Operacje zabezpieczeń).
3. W polu **Opis** wprowadź tekst *This role lets a security operator monitor device configuration and compliance information* (Ta rola umożliwia operatorowi zabezpieczeń monitorowanie informacji o zgodności i konfiguracji urządzenia).
4. Wybierz pozycję **Konfiguruj** > **Identyfikatory urządzeń firmowych** > **Tak** obok pozycji **Odczyt** > **OK**.
![Przeglądarka](media/quickstart-create-custom-role/corp-device-id-read.png)
5. Wybierz pozycję **Wszystkie zasady zgodności urządzeń** > **Tak** obok pozycji **Odczyt** > **OK**.
6. Wybierz pozycję **Konfiguracje urządzeń** > **Tak** obok pozycji **Odczyt** > **OK**.
7. Wybierz pozycję **Organizacja** > **Tak** obok pozycji **Odczyt** > **OK**.
8. Wybierz pozycję **OK** > **Utwórz**.

## <a name="assign-the-role-to-a-group"></a>Przypisywanie roli do grupy

Aby operator zabezpieczeń mógł używać nowych uprawnień, należy przypisać tę rolę do grupy, która zawiera tego użytkownika zabezpieczeń.

1. W usłudze Intune wybierz pozycję **Role** > **Wszystkie role** > **Pomoc techniczna dla urządzeń zdalnych**.
2. W obszarze **Role usługi Intune** wybierz pozycję **Przypisania** > **Przypisz**.
3. W polu **Nazwa przypisania** wprowadź tekst *Sec ops* (Operacje zabezpieczeń).
4. Wybierz pozycję **Członek (grupy)** > **Dodaj**.
5. Wybierz grupę **Contoso Testers** (Testerzy Contoso).
6. Wybierz pozycję **Wybierz** > **OK**.
7. Wybierz pozycję **Zakres (grupy)** > **Wybierz grupy do uwzględnienia** > **Contoso Testers** (Testerzy Contoso).
8. Wybierz pozycję **Wybierz** > **OK** > **OK**.

Teraz wszyscy w grupie są członkami roli *Security operations* (Operacje zabezpieczeń) i mogą przeglądać następujące informacje o urządzeniu: identyfikatory urządzeń firmowych, zasady zgodności urządzeń, konfiguracje urządzeń i informacje o organizacji.

## <a name="clean-up-resources"></a>Oczyszczanie zasobów

Jeśli nie chcesz już używać nowej roli niestandardowej, możesz ją usunąć. Wybierz pozycję **Role** > **Wszystkie role** > wybierz wielokropek obok właściwej roli > **Usuń**.

## <a name="next-steps"></a>Następne kroki

W tym przewodniku Szybki start utworzono rolę niestandardową do operacji zabezpieczeń i przypisano ją grupie. Poniższy artykuł pozwala dowiedzieć się więcej na temat problemów z zabezpieczeniami.

> [!div class="nextstepaction"]
> [Wprowadzenie do zasad zgodności urządzeń w usłudze Intune](device-compliance-get-started.md)
