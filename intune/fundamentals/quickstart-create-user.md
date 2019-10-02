---
title: Przewodnik Szybki start — tworzenie użytkownika w usłudze Intune
description: Przewodnik Szybki start — tworzenie użytkownika w usłudze Intune.
services: microsoft-intune
author: ErikjeMS
ms.service: microsoft-intune
ms.localizationpriority: high
ms.topic: quickstart
ms.date: 03/25/2019
ms.author: erikje
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: 16d8eb3b3a0117495fe8740160e9ebcec299d764
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71727093"
---
# <a name="quickstart-create-a-user-in-intune-and-assign-them-a-license"></a>Szybki start: Tworzenie użytkownika w usłudze Intune i przypisywanie do niego licencji

W tym przewodniku Szybki start utworzysz użytkownika, a następnie przypiszesz do niego licencję usługi Intune. W przypadku korzystania z usługi Intune każda osoba, która ma mieć dostęp do danych firmy, musi mieć własne konto użytkownika. Administratorzy usługi Intune mogą później konfigurować tych użytkowników na potrzeby zarządzania kontrolą dostępu.

Jeśli nie masz subskrypcji usługi Intune, [utwórz konto bezpłatnej wersji próbnej](free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Logowanie się do usługi Intune

Zaloguj się w usłudze [Intune](https://aka.ms/intuneportal) jako [administrator globalny lub administrator usługi Intune](users-add.md#types-of-administrators). Jeśli utworzono subskrypcję wersji próbnej usługi Intune, konto, którego użyto do utworzenia subskrypcji, jest administratorem globalnym.

## <a name="create-a-user"></a>Tworzenie użytkownika

Użytkownicy, którzy chcą zarejestrować się w zarządzaniu urządzeniami w usłudze Intune, muszą mieć konto użytkownika. Aby utworzyć nowego użytkownika:

1. W usłudze Intune wybierz pozycję **Użytkownicy** > **Wszyscy użytkownicy** > **Nowy użytkownik**.
![Przeglądarka](./media/quickstart-create-user/create-user.png)
2. W polu **Nazwa** wpisz imię i nazwisko, na przykład *Dewey Kellum*.
3. W polu **Nazwa użytkownika** wpisz identyfikator użytkownika, na przykład Dewey@contoso.onmicrosoft.com.

    > [!NOTE]
    > Jeśli nie skonfigurowano nazwy domeny klienta, użyj zweryfikowanej nazwy domeny, której użyto do utworzenia subskrypcji usługi Intune (lub [bezpłatnej wersji próbnej](free-trial-sign-up.md#sign-up-for-a-microsoft-intune-free-trial)). 

4. Wybierz pozycję **Pokaż hasło** i zanotuj automatycznie wygenerowane hasło, aby użyć go do zalogowania się na urządzeniu testowym.
5. Wybierz pozycję **Utwórz**.

## <a name="assign-a-license-to-the-user"></a>Przypisywanie użytkownikowi licencji

Po utworzeniu użytkownika należy użyć [centrum administracyjnego platformy Microsoft 365](http://go.microsoft.com/fwlink/p/?LinkId=698854), aby przypisać do niego licencję usługi Intune. Jeśli nie przypiszesz licencji do użytkownika, nie będzie on mógł zarejestrować urządzenia w usłudze Intune. 

Aby przypisać licencję usługi Intune do użytkownika:

1. Zaloguj się do [centrum administracyjnego platformy Microsoft 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) przy użyciu tych samych poświadczeń co użyte do zalogowania się do usługi Intune.
2. Wybierz pozycję **Użytkownicy** > **Aktywni użytkownicy** > i wybierz utworzonego przed chwilą użytkownika.
3. Obok pozycji **Licencje produktów** wybierz pozycję **Edytuj**.
4. W obszarze **Lokalizacja** wybierz lokalizację dla użytkownika.
5. Kliknij przycisk **Włączona** obok licencji usługi Intune (lub innej posiadanej licencji obejmującej usługę Intune). Wyświetlana [nazwa produktu](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)** jest używana jako plan usługi w zarządzaniu platformą Azure 

   > [!NOTE]
   > To ustawienie spowoduje użycie jednej z Twoich licencji na potrzeby tego użytkownika. Jeśli używasz wersji próbnej środowiska, możesz później ponownie przypisać tę licencję do prawdziwego użytkownika w działającym środowisku.
6. Wybierz pozycję **Zapisz** > **Zamknij**.

W przypadku nowego aktywnego użytkownika usługi Intune będzie wyświetlana informacja, że używa licencji usługi **Intune**.

## <a name="clean-up-resources"></a>Oczyszczanie zasobów

Jeśli już nie potrzebujesz tego użytkownika, możesz go usunąć, przechodząc do [centrum administracyjnego platformy Microsoft 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) i wybierając pozycję **Użytkownicy** > **Aktywni użytkownicy** > *wybierz użytkownika z listy* > **Usuń użytkownika** > **Usuń użytkownika** > **Potwierdź zmiany** > **Zamknij**.

## <a name="next-steps"></a>Następne kroki

W tym przewodniku Szybki start utworzono użytkownika i przypisano do niego licencję usługi Intune. Aby uzyskać więcej informacji na temat dodawania użytkowników do usługi Intune, zobacz [Dodawanie użytkowników i przyznawanie uprawnień administracyjnych do usługi Intune](users-add.md).

Aby zapoznać się kolejnymi przewodnikami Szybki start dotyczącymi usługi Intune, przejdź do kolejnego przewodnika Szybki start.

> [!div class="nextstepaction"]
> [Szybki start: Tworzenie grupy do zarządzania użytkownikami](../quickstart-create-group.md)
