---
title: Przewodnik Szybki start — tworzenie użytkownika w usłudze Intune
description: Przewodnik Szybki start — tworzenie użytkownika w usłudze Intune.
services: microsoft-intune
author: ErikjeMS
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.topic: quickstart
ms.date: 01/17/2020
ms.author: erikje
ms.manager: dougeby
ms.assetid: 820fcb18-0927-4ebd-be79-dce92b51c261
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: f6aa57b71e052e3fc8566fcdff8bdd9ef5d1c39e
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2020
ms.locfileid: "76754494"
---
# <a name="quickstart-create-a-user-in-intune-and-assign-the-user-a-license"></a>Szybki start: Tworzenie użytkownika w usłudze Intune i przypisywanie licencji użytkownika

W tym przewodniku Szybki start utworzysz użytkownika, a następnie przypiszesz do niego licencję usługi Intune. Jeśli używasz usługi Intune, każda osoba, która ma mieć dostęp do danych firmy, musi mieć własne konto użytkownika. Administratorzy usługi Intune mogą później konfigurować tych użytkowników na potrzeby zarządzania kontrolą dostępu.

## <a name="prerequisites"></a>Wymagania wstępne

- Subskrypcja usługi Microsoft Intune. [Utwórz konto bezpłatnej wersji próbnej](../fundamentals/free-trial-sign-up.md).

## <a name="sign-in-to-intune-in-microsoft-endpoint-manager"></a>Logowanie do usługi Intune w programie Microsoft Endpoint Manager

Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) jako [administrator globalny lub administrator usługi Intune](users-add.md#types-of-administrators). Jeśli utworzono subskrypcję wersji próbnej usługi Intune, konto, którego użyto do utworzenia subskrypcji, jest administratorem globalnym.

## <a name="create-a-user"></a>Tworzenie użytkownika

Użytkownik, który chce zarejestrować się w zarządzaniu urządzeniami w usłudze Intune, musi mieć konto użytkownika. Aby utworzyć nowego użytkownika:

1. W programie Microsoft Endpoint Manager wybierz pozycję **Użytkownicy** > **Wszyscy użytkownicy** > **Nowy użytkownik**:  ![Wybieranie pozycji Nowy użytkownik w programie Microsoft Endpoint Manager](./media/quickstart-create-user/create-user.png)
2. W polu **Nazwa** wprowadź imię i nazwisko, na przykład *Dewey Kellum*:  ![Dodawanie szczegółów użytkownika](./media/quickstart-create-user/create-user-02.png)
3. W polu **Nazwa użytkownika** wprowadź identyfikator użytkownika, na przykład Dewey@contoso.onmicrosoft.com.

    > [!NOTE]
    > Jeśli nie skonfigurowano nazwy domeny klienta, użyj zweryfikowanej nazwy domeny, której użyto do utworzenia subskrypcji usługi Intune (lub [bezpłatnej wersji próbnej](free-trial-sign-up.md#sign-up-for-a-microsoft-intune-free-trial)). 

4. Wybierz pozycję **Pokaż hasło**. Pamiętaj o zanotowaniu automatycznie wygenerowanego hasła, aby użyć go do zalogowania się na urządzeniu testowym.
5. Wybierz przycisk **Utwórz**.

## <a name="assign-a-license-to-the-user"></a>Przypisywanie użytkownikowi licencji

Po utworzeniu użytkownika należy użyć [centrum administracyjnego platformy Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=698854), aby przypisać licencję usługi Intune do tego użytkownika. Jeśli nie przypiszesz licencji do użytkownika, nie będzie on mógł zarejestrować urządzenia w usłudze Intune.

Aby przypisać licencję usługi Intune do użytkownika:

1. Zaloguj się do [centrum administracyjnego platformy Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=698854) przy użyciu tych samych poświadczeń co użyte do zalogowania się do usługi Intune.
2. Wybierz pozycję **Użytkownicy** > **Aktywni użytkownicy**, a następnie wybierz właśnie utworzonego użytkownika.
3. Wybierz kartę **Licencje i aplikacje**.
4. W obszarze **Wybierz lokalizację** wybierz lokalizację dla użytkownika, jeśli nie została jeszcze ustawiona.
2. Zaznacz pole wyboru **Intune** w sekcji **Licencje**. Jeśli inna licencja obejmuje usługę Intune, możesz wybrać tę licencję. Wyświetlana [nazwa produktu](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference) jest używana jako plan usługi w zarządzaniu platformą Azure.

    ![Wybieranie lokalizacji i licencji usługi Intune](./media/quickstart-create-user/create-user-03.png)

   > [!NOTE]
   > To ustawienie spowoduje użycie jednej z Twoich licencji na potrzeby użytkownika. Jeśli używasz wersji próbnej środowiska, później ponownie przypiszesz tę licencję do prawdziwego użytkownika w działającym środowisku.

6. Wybierz pozycję **Zapisz zmiany**.

W przypadku nowego aktywnego użytkownika usługi Intune będzie wyświetlana informacja, że używa licencji usługi **Intune**.

## <a name="clean-up-resources"></a>Oczyszczanie zasobów

Jeśli ten użytkownik nie jest już potrzebny, możesz go usunąć, przechodząc do [centrum administracyjnego platformy Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=698854) i wybierając pozycję **Użytkownicy** > *użytkownik* > *ikona usuwania użytkownika* > **Usuń użytkownika** > **Zamknij**.

   ![Wybieranie ikony usuwania](./media/quickstart-create-user/create-user-04.png)

## <a name="next-steps"></a>Następne kroki

W tym przewodniku Szybki start utworzono użytkownika i przypisano do niego licencję usługi Intune. Aby uzyskać więcej informacji na temat dodawania użytkowników do usługi Intune, zobacz [Dodawanie użytkowników i przyznawanie uprawnień administracyjnych do usługi Intune](users-add.md).

Aby kontynuować pracę z tą serią przewodników Szybki start dotyczących usługi Intune, przejdź do następnego przewodnika Szybki start:

> [!div class="nextstepaction"]
> [Szybki start: Tworzenie grupy do zarządzania użytkownikami](../quickstart-create-group.md)
