---
title: Przewodnik Szybki start — tworzenie użytkownika w usłudze Intune
description: Przewodnik Szybki start — tworzenie użytkownika w usłudze Intune.
services: microsoft-intune
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: quickstart
ms.date: 09/21/2018
ms.author: erikje
ms.openlocfilehash: 6a1d591e635dccd99551d9b8d40e099724a85d77
ms.sourcegitcommit: 27eed5aba5c8bfafb079171081b68f75a6cbffaf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2018
ms.locfileid: "46581806"
---
# <a name="quickstart-create-a-user-and-assign-a-license-to-it"></a>Przewodnik Szybki start: tworzenie użytkownika i przypisywanie mu licencji

W tym przewodniku Szybki start utworzysz użytkownika, a następnie przypiszesz mu licencję. W przypadku korzystania z usługi Intune każda osoba, która ma mieć dostęp do danych firmy, musi mieć konto użytkownika. Administratorzy usługi Intune mogą konfigurować tych użytkowników na potrzeby zarządzania kontrolą dostępu.

Jeśli nie masz subskrypcji usługi Intune, [utwórz konto bezpłatnej wersji próbnej](free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Logowanie się do usługi Intune

Zaloguj się w usłudze [Intune](https://aka.ms/intuneportal) jako administrator globalny lub administrator usługi Intune.

## <a name="create-a-user"></a>Utworzenie użytkownika

Osoby, które chcą zarejestrować się w zarządzaniu urządzeniami w usłudze Intune, muszą mieć konta użytkowników.

1. W usłudze Intune wybierz pozycję **Użytkownicy** > **Wszyscy użytkownicy** > **Nowy użytkownik**.
![Przeglądarka](media/quickstart-create-user/create-user.png)
2. W polu **Nazwa** wprowadź nazwisko *Dewey Kellum*.
3. W polu **Nazwa użytkownika** wprowadź nazwę *Dewey@contoso.onmicrosoft.com*.
4. Wybierz pozycję **Grupy** > **Wszyscy** > **Wybierz**.
5. Wybierz pozycję **Pokaż hasło** i zanotuj automatycznie wygenerowane hasło, aby użyć go do zalogowania się na urządzeniu testowym.
6. Wybierz pozycję **Utwórz**.

## <a name="assign-a-license-to-the-user"></a>Przypisywanie użytkownikowi licencji

Po utworzeniu użytkownika trzeba użyć [portalu usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854), aby przypisać licencję usługi Intune do tego użytkownika. Jeśli użytkownikom nie zostaną przypisane licencje, nie będą oni mogli zarejestrować swoich urządzeń w usłudze Intune. 

1. Zaloguj się do [portalu usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) przy użyciu tych samych poświadczeń, które zostały użyte do zalogowania się do usługi Intune.
2. Wybierz pozycję **Użytkownicy** > **Aktywni użytkownicy** > wybierz utworzonego przed chwilą użytkownika.
3. W obszarze **Lokalizacja** wybierz lokalizację dla użytkownika.
3. Wybierz pozycję **Licencje na produkty** i dla pozycji **Enterprise Mobility + Security E3** (lub dla innej posiadanej licencji obejmującej usługę Intune) ustaw wartość **Włączone**.
   > [!NOTE]
   > Spowoduje to użycie jednej z Twoich licencji na potrzeby tego użytkownika. Jeśli używasz swojego działającego środowiska, możesz później wyłączyć używanie tej licencji, aby przypisać ją ponownie do rzeczywistego użytkownika.
5. Wybierz polecenie **Zapisz**.

## <a name="clean-up-resources"></a>Oczyszczanie zasobów

Jeśli dany użytkownik nie jest już potrzebny, można go usunąć, wybierając pozycję **Użytkownicy** > **Wszyscy użytkownicy** > wybierz użytkownika z listy > **Usuń użytkownika** > **Tak**.

## <a name="next-steps"></a>Następne kroki

W tym przewodniku Szybki start utworzono użytkownika i przypisano mu licencję. Teraz można przypisać tego użytkownika do grupy.

> [!div class="nextstepaction"]
> [Tworzenie grupy](quickstart-create-group.md)
