---
title: Przewodnik Szybki start — tworzenie użytkownika w usłudze Intune
description: Przewodnik Szybki start — tworzenie użytkownika w usłudze Intune.
services: microsoft-intune
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: quickstart
ms.date: 10/30/2018
ms.author: erikje
ms.openlocfilehash: ffc1f0140f98b17e060df3308af779ddcb77549e
ms.sourcegitcommit: 4c4e87cb0d8906085fcb7cdd170bd6b0cfeb23ff
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2018
ms.locfileid: "51510928"
---
# <a name="quickstart-create-a-user-and-assign-a-license-to-it"></a>Przewodnik Szybki start: tworzenie użytkownika i przypisywanie mu licencji

W tym przewodniku Szybki start utworzysz użytkownika, a następnie przypiszesz licencję temu użytkownikowi. W przypadku korzystania z usługi Intune każda osoba, która ma mieć dostęp do danych firmy, musi mieć konto użytkownika. Administratorzy usługi Intune mogą później konfigurować tych użytkowników na potrzeby zarządzania kontrolą dostępu.

Jeśli nie masz subskrypcji usługi Intune, [utwórz konto bezpłatnej wersji próbnej](free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Logowanie się do usługi Intune

Zaloguj się w usłudze [Intune](https://aka.ms/intuneportal) jako [administrator globalny lub administrator usługi Intune](users-add.md#types-of-administrators). Jeśli utworzono subskrypcję wersji próbnej usługi Intune, konto, którego użyto do utworzenia subskrypcji, jest administratorem globalnym.

## <a name="create-a-user"></a>Utworzenie użytkownika

Osoby, które chcą zarejestrować się w zarządzaniu urządzeniami w usłudze Intune, muszą mieć konta użytkowników.

1. W usłudze Intune wybierz pozycję **Użytkownicy** > **Wszyscy użytkownicy** > **Nowy użytkownik**.
![Przeglądarka](media/quickstart-create-user/create-user.png)
2. W polu **Nazwa** wpisz imię i nazwisko, na przykład *Dewey Kellum*.
3. W polu **Nazwa użytkownika** wpisz identyfikator użytkownika, na przykład Dewey@contoso.onmicrosoft.com.

    > [!NOTE]
    > Jeśli nie skonfigurowano nazwy domeny klienta, użyj zweryfikowanej nazwy domeny, której użyto do utworzenia subskrypcji usługi Intune (lub [bezpłatnej wersji próbnej](free-trial-sign-up.md#sign-up-for-a-microsoft-intune-free-trial)). 

4. Wybierz pozycję **Pokaż hasło** i zanotuj automatycznie wygenerowane hasło, aby użyć go do zalogowania się na urządzeniu testowym.
5. Wybierz pozycję **Utwórz**.

## <a name="assign-a-license-to-the-user"></a>Przypisywanie użytkownikowi licencji

Po utworzeniu użytkownika trzeba użyć [portalu usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854), aby przypisać licencję usługi Intune do tego użytkownika. Jeśli użytkownikom nie zostaną przypisane licencje, nie będą oni mogli zarejestrować swoich urządzeń w usłudze Intune. 

1. Zaloguj się do [portalu usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) przy użyciu tych samych poświadczeń, które zostały użyte do zalogowania się do usługi Intune.
2. Wybierz pozycję **Użytkownicy** > **Aktywni użytkownicy** > wybierz utworzonego przed chwilą użytkownika.
3. Obok pozycji **Licencje produktów** wybierz pozycję **Edytuj**.
4. W obszarze **Lokalizacja** wybierz lokalizację dla użytkownika.
5. Kliknij przycisk **Włączona** obok licencji usługi Intune (lub innej posiadanej licencji obejmującej usługę Intune). Wyświetlana [nazwa produktu](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)** jest używana jako plan usługi w zarządzaniu platformą Azure 

   > [!NOTE]
   > To ustawienie spowoduje użycie jednej z Twoich licencji na potrzeby tego użytkownika. Jeśli używasz wersji próbnej środowiska, możesz później ponownie przypisać tę licencję do prawdziwego użytkownika w działającym środowisku.
6. Wybierz pozycję **Zapisz** > **Zamknij**.

W przypadku nowego aktywnego użytkownika usługi Intune będzie wyświetlana informacja, że używa licencji usługi **Intune**.

## <a name="clean-up-resources"></a>Oczyszczanie zasobów

Jeśli już nie potrzebujesz tego użytkownika, możesz go usunąć, przechodząc do [portalu usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) i wybierając pozycję **Użytkownicy** > **Aktywni użytkownicy** > *wybierając użytkownika z listy* > **Usuń użytkownika** > **Usuń użytkownika** > **Potwierdź zmiany** > **Zamknij**.

## <a name="next-steps"></a>Następne kroki

W tym przewodniku Szybki start utworzono użytkownika i przypisano licencję temu użytkownikowi. Aby uzyskać więcej informacji na temat dodawania użytkowników do usługi Intune, zobacz [Dodawanie użytkowników i przyznawanie uprawnień administracyjnych do usługi Intune](users-add.md).

Aby zapoznać się kolejnymi przewodnikami Szybki start dotyczącymi usługi Intune, przejdź do kolejnego przewodnika Szybki start.

> [!div class="nextstepaction"]
> [Przewodnik Szybki start: tworzenie grupy do zarządzania użytkownikami](quickstart-create-group.md)
