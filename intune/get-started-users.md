---
title: "Rozpoczynanie pracy z użytkownikami"
titlesuffix: Azure portal
description: "Dodaj użytkownika do usługi Intune, aby umożliwić mu dostęp do zasobów firmy na urządzeniach przenośnych."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 22a232de-ab93-44ab-b0b5-d2b3ccb007fe
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a33eb2d5dc96a2647cf2582bbc6cd4ba2d9c0961
ms.sourcegitcommit: fa6aaf12611c3e03e38e467806fc30b1d0255e88
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/12/2017
---
# <a name="get-started-with-managing-users"></a>Wprowadzenie do zarządzania użytkownikami

Pomyśl o wszystkich osobach w Twojej organizacji. Dla każdej osoby korzystającej z danych firmy będzie potrzebny użytkownik, aby zarządzać dostępem do tych danych w usłudze Intune.

## <a name="how-do-i-create-a-user"></a>Jak utworzyć użytkownika?

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Za pomocą pola **Wyszukaj zasoby** wyszukaj usługę **Intune**.
3. Po otwarciu bloku **Microsoft Intune** wybierz opcję **Użytkownicy**. Na stronie **Wszyscy użytkownicy** wybierz pozycję **+ Nowy użytkownik**.
4. Wprowadź szczegółowe informacje dotyczące użytkownika, takie jak **nazwa** i **nazwa użytkownika**. Część nazwy użytkownika stanowiąca nazwę domeny musi być początkową, domyślną nazwą domeny, „contoso.onmicrosoft.com”, lub zweryfikowaną, niefederacyjną nazwą domeny, na przykład „contoso.com”.
5. W obszarze **Grupy** wybierz grupę testową, do której zostanie dodany użytkownik.
6. Zapisz automatycznie wygenerowane hasło użytkownika, aby użyć go do zalogowania się na urządzeniu testowym. To hasło należy przekazać użytkownikom, aby mogli zmienić je na normalne, łatwiejsze do zapamiętania hasło.
7. W bloku **Użytkownik** wybierz pozycję **Utwórz**.

## <a name="assigning-licenses-to-users"></a>Przypisywanie licencji użytkownikom

Po utworzeniu użytkownika należy użyć [portalu usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854), aby przypisać licencję usługi Intune do tego użytkownika. Jeśli użytkownikom nie zostanie przypisana licencja, nie będą oni mogli zarejestrować swojego urządzenia w systemie zarządzania.

1. Zaloguj się do [portalu usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) przy użyciu tych samych poświadczeń, które zostały użyte do zalogowania się do usługi Intune.
2. Wybierz pozycję **Użytkownicy** > **Aktywni użytkownicy**, a następnie wybierz wcześniej utworzonego użytkownika.
3. Może chwilę potrwać, aż wszystkie informacje dotyczące użytkownika zostaną załadowane. Po ich załadowaniu wybierz pozycję **Edytuj** dla **licencji produktu** użytkownika.
4. Przypisz użytkownikowi **lokalizację**, a następnie przełącz usługę Intune na wartość **Włączona**.

 > [!NOTE]
 > Spowoduje to użycie jednej z Twoich licencji na potrzeby tego użytkownika. Jeśli używasz swojego działającego środowiska, możesz później wyłączyć używanie tej licencji, aby przypisać ją ponownie do rzeczywistego użytkownika.

5. Wybierz pozycję **Zapisz**.

## <a name="next-steps"></a>Następne kroki

[Wprowadzenie do grup](get-started-groups.md) — umieszczaj użytkowników w grupach, aby ułatwić zarządzanie zasadami i aplikacjami, do których mogą uzyskiwać dostęp.
