---
title: "Dodawanie użytkowników do 30-dniowej wersji ewaluacyjnej usługi Intune | Microsoft Intune"
description: "Jak dodawać użytkowników, indywidualnie lub grupowo, w przypadku zarejestrowania w celu korzystania z bezpłatnej, 30-dniowej wersji ewaluacyjnej usługi Intune"
keywords: 
author: lindavr
manager: angrobe
ms.date: 08/09/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9e40999b-46f7-447b-8974-72af82bec7ef
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 51fba2b01d8978bc062c50c4388714609be0fdf0
ms.openlocfilehash: 4276d0fed0fc30490a640a067d78096ff0cf78ae


---

# Dodawanie użytkowników do 30-dniowej wersji ewaluacyjnej usługi Microsoft Intune
Po skonfigurowaniu konta użyjesz **Kreatora nowych użytkowników**, aby dodać indywidualne konta użytkowników do usługi Intune, lub **Kreatora zbiorczego dodawania użytkowników**, aby dodać użytkowników zbiorczo (zobacz instrukcje w tej sekcji).  Jest ważne, aby przed rozpoczęciem pracy zrozumieć, w jaki sposób usługa Intune obsługuje konta administratorów.

Administrator dzierżawy używa centrum administracyjnego usługi Office 365, aby dodać użytkowników do **grupy użytkowników** usługi Microsoft Intune. Dodanie użytkowników do  **grupy użytkowników** spowoduje przypisanie licencji subskrypcji usługi Intune do użytkowników. Rezultatem jest także to, że będą oni wyświetlani w konsoli administracyjnej usługi Microsoft Intune.

Kont administratorów usługi Intune nie tworzy się w centrum administracyjnym usługi Office 365, tak jak w przypadku kont zwykłych użytkowników. Zamiast tego przypisuje się użytkownikom prawa administracyjne (tylko do odczytu lub z pełnym dostępem) za pomocą konsoli administracyjnej w obszarze roboczym **Administracja** w obszarze **Zarządzanie administracyjne**. Administratorzy usługi z dostępem tylko do odczytu nie mogą zmieniać ustawień usługi Intune, ale mogą wyświetlać dane i uruchamiać raporty. Administratorzy usługi z pełnym dostępem mają wszystkie dostępne prawa administracyjne.

Możesz wyświetlić informacje o administratorach dzierżawy przy użyciu konsoli administracyjnej usługi Intune, ale nie możesz tam utworzyć administratorów dzierżawy. Domyślnie właściciel subskrypcji staje się administratorem dzierżawy usługi Microsoft Intune i ma pełny dostęp do centrum administracyjnego usługi Office 365 oraz do konsoli administracyjnej usługi Intune. Zalecamy utworzenie co najmniej jednego dodatkowego konta administratora dzierżawy przy użyciu centrum administracyjnego usługi Office 365, co ułatwi delegowanie zadań i będzie stanowić zabezpieczenie przed zablokowaniem dostępu do konta administratora usługi Intune w przypadku zapomnienia hasła.

## Dodawanie indywidualnych kont użytkowników
Następujące kroki umożliwiają utworzenie dodatkowych kont użytkowników w dzierżawie w wersji ewaluacyjnej. Pamiętaj, że każde dodane konto użytkownika używa jednej ze 100 licencji, które otrzymujesz w ramach bezpłatnej wersji ewaluacyjnej usługi Intune.

1.  W [centrum administracyjnym usługi Office 365](http://go.microsoft.com/fwlink/?LinkID=787455) wybierz pozycję **Dodaj użytkowników** &gt; **Nowy**&gt; **Użytkownik**, aby uruchomić **Kreatora nowych użytkowników**.

2.  Na stronie **Szczegóły** wypełnij wymagane pola.

3.  Na stronie **Ustawienia** ustaw wartość w polu **Lokalizacja** dla użytkownika.

4.  Na stronie **Grupa** wybierz pozycję **Dalej**, aby zaakceptować wybór domyślny i przypisać licencję usługi Intune do konta użytkownika.

5.  Na stronie **Adres e-mail** podaj maksymalnie pięć adresów e-mail, na które będzie wysyłane powiadomienie zawierające nazwę użytkownika i tymczasowe hasło dla konta. Poszczególne adresy e-mail należy rozdzielić średnikami (;). Po wykonaniu tych czynności wybierz pozycję **Utwórz**, aby dodać użytkownika do subskrypcji.

6.  Na stronie **Wyniki** można wyświetlić nazwę nowego konta i jego hasło tymczasowe. Usługa Intune automatycznie tworzy hasło tymczasowe.

7.  Gdy nowy użytkownik zostanie wyświetlony w centrum administracyjnym usługi Office 365, sprawdź, czy został on utworzony pomyślnie:

    1.  W [konsoli administracyjnej usługi Intune](https://manage.microsoft.com/) wybierz pozycję **Administracja** &gt; **Portal firmy**, a następnie przewiń do dołu ekranu. Skopiuj adres URL wyświetlany w obszarze **Portal firmy w usłudze Intune**.

    2.  Otwórz nowe okno przeglądarki w trybie prywatności (w programie Internet Explorer wybierz pozycję **Narzędzia** &gt; **Przeglądanie InPrivate**) lub otwórz nowe okno przeglądarki na innym urządzeniu, a następnie przejdź do adresu URL skopiowanego w poprzednim kroku. Podczas pierwszego logowania użytkownik musi podać nowe hasło dla konta.

## Zbiorcze dodawanie użytkowników
Aby dodać zbiorczo użytkowników do usługi Intune, użyj **Kreatora zbiorczego dodawania użytkowników** w celu przekazania pliku wartości rozdzielanych przecinkami (CSV) zawierającego dane użytkowników. Linki w kreatorze umożliwiają pobranie pustego szablonu i przykładowego pliku CSV. Pierwszy wiersz pliku CSV musi zawierać, we właściwej kolejności, wszystkie etykiety kolumn danych użytkownika. Następnie dla każdego użytkownika w pliku CSV należy wprowadzić wartości w kolumnach **Nazwa użytkownika** (na przykład **bob@contoso.com**) i **Nazwa wyświetlana** (na przykład **Bob Kelly**).

1.  W [centrum administracyjnym usługi Office 365](http://go.microsoft.com/fwlink/?LinkID=787455) wybierz pozycję **Użytkownicy** &gt; **Nowy**.

2.  Wybierz pozycję **Dodaj zbiorczo**, aby uruchomić Kreatora zbiorczego dodawania użytkowników.

3.  Na stronie **Wybieranie pliku** wybierz pozycję **Przeglądaj**, aby określić i załadować istniejący plik CSV z komputera. Możesz również pobrać przykładowy plik CSV lub plik pustego szablonu za pomocą linków w kreatorze.

4.  Na stronie **Weryfikacja** przyjrzyj wyniki, a następnie wybierz pozycję **Wyświetl**, aby wyświetlić więcej szczegółów.

5.  Na stronie **Ustawienia** upewnij się, że stan logowania to **Dozwolone**, a następnie ustaw wartość **lokalizacja**. Te ustawienia dotyczą wszystkich kont użytkowników dodanych przy użyciu pliku CSV.

6.  Na stronie **Grupa** wybierz pozycję **Dalej**, aby zaakceptować ustawienie domyślne i przypisać licencję usługi Intune do wszystkich kont użytkowników dodanych przy użyciu pliku CSV. To pole wyboru jest domyślnie zaznaczone, co powoduje przypisanie licencji usługi Intune do każdego z kont.

7.  Na stronie **Adres e-mail** określ do pięciu adresów e-mail, na które zostaną wysłane powiadomienia o nazwach użytkowników i hasłach tymczasowych utworzonych przez usługę Intune dla poszczególnych kont. Poszczególne adresy e-mail należy rozdzielić średnikami (;). Wybierz pozycję **Utwórz**, aby dodać użytkowników do subskrypcji.

8.  Na stronie **Wyniki** można wyświetlić nazwy kont i hasła tymczasowe dla poszczególnych kont użytkowników.

Wszystkie konta użytkowników dodane przez zaimportowanie będą teraz wyświetlane w węźle **Użytkownicy** centrum administracyjnego usługi Office 365. Podczas pierwszego logowania każdy nowy użytkownik musi określić nowe hasło dla swojego konta.

### Następne kroki
Gratulacje! Krok 2 przewodnika *wersji ewaluacyjnej usługi Microsoft Intune* właśnie został ukończony.

>[!div class="step-by-step"]

>[&larr; **Tworzenie konta na potrzeby wersji ewaluacyjnej**](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-1.md)     [**Tworzenie grup** &rarr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-3.md)  



<!--HONumber=Aug16_HO2-->


