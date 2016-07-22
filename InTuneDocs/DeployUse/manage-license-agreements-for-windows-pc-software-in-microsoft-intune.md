---
# required metadata

title: Zarządzanie umowami licencyjnymi na oprogramowanie na komputerze z systemem Windows w usłudze Microsoft Intune | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: c59d8635-3f66-40f5-824a-a71c738e0341

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Zarządzanie umowami licencyjnymi na oprogramowanie na komputerze z systemem Windows w usłudze Microsoft Intune
Usługa Microsoft Intune umożliwia dodawanie informacji o umowach licencyjnych dotyczących oprogramowania zakupionego w ramach umów licencjonowania zbiorowego firmy Microsoft oraz oprogramowania firmy Microsoft i innych firm zakupionego w inny sposób. Możliwe jest także zarządzanie tymi informacjami. Możesz również dzielić informacje na logiczne grupy.

> [!IMPORTANT]
> Ta funkcja dostarczana jest jedynie jako udogodnienie i jej dokładność nie jest gwarantowana. Nie należy polegać na niej podczas określania zgodności z umowami licencjonowania zbiorowego firmy Microsoft. Firma Microsoft nie będzie używać zbieranych danych na potrzeby analizowania potencjalnych naruszeń umów licencjonowania ani zgodności z nimi w przypadku umów licencyjnych, które mogą wiązać Ciebie z nami.
> 
> Licencje dodane do usługi Intune nie mają wpływu na Twoje umowy licencyjne ani uprawnienia do używania oprogramowania.  Na przykład usunięcie pary umowa/licencja z usługi Intune nie powoduje rozwiązania ani zniesienia umów licencyjnych zawartych między Tobą a firmą Microsoft.

Obszar roboczy **Licencje** konsoli administratora usługi Intune umożliwia wykonanie następujących czynności:

-   Dodawanie i edytowanie umów w ramach licencjonowania zbiorowego firmy Microsoft

-   Dodawanie i edytowanie umów licencyjnych na inne oprogramowanie

-   Zarządzanie licencjami i grupami

-   Porównywanie informacji dotyczących uprawnień, które są pobierane przez usługę Intune z Centrum usługi licencjonowania zbiorowego (VLSC, Volume Licensing Service Center), do spisu oprogramowania firmy Microsoft wykrytego przez usługę Intune na Twoich zarządzanych komputerach z systemem Windows.

Ponadto możesz generować raporty, które zawierają liczby instalacji i licencji dotyczące tytułów oprogramowania. Raporty o licencjach mogą ułatwić oszacowanie całkowitego stanu licencji na tytuły oprogramowania firmy Microsoft i innych firm.

> [!TIP]
> Obszar roboczy **Licencje** zostanie wyświetlony w konsoli administratora dopiero po rozpoczęciu zarządzania co najmniej jednym komputerem z systemem Windows przy użyciu klienta komputerowego usługi Intune dla systemu Windows.

## Dodawanie umów w ramach licencjonowania zbiorowego firmy Microsoft
Umowy licencjonowania zbiorowego usługi Intune zawierają informacje o licencji na oprogramowanie, które zostało zakupione w ramach umów licencjonowania zbiorowego firmy Microsoft. Możesz dodać umowy licencjonowania zbiorowego firmy Microsoft do usługi Intune, podając dopasowane pary numerów umów. Numery umowy lub autoryzacji muszą być zgodne z poprawnymi numerami licencji lub rejestracji. Pary numerów umów są uzyskiwane podczas zakupu umów licencyjnych w [Centrum usługi licencjonowania zbiorowego firmy Microsoft (VLSC)](http://go.microsoft.com/fwlink/?LinkID=223842).

1.  W [konsoli administratora usługi Microsoft Intune](https://account.manage.microsoft.com/admin/default.aspx)kliknij pozycję **Licencje**.

2.  Na stronie **Dodawanie umów** w obszarze **Wybierz typ umowy**wybierz pozycję **Umowa licencjonowania zbiorowego**.

3.  W sekcji **Dodaj szczegóły umowy** wybierz jedną z następujących pozycji:

    -   **Przekaż plik CSV zawierający szczegóły umowy** — kliknij przycisk Przeglądaj i wybierz plik CSV, który chcesz przekazać.

        -   Plik może zawierać 2 lub 3 kolumny — dwie dla par umów i trzecią opcjonalną z przyjazną nazwą dla każdej pary.

        -   Całkowita liczba znaków w parze numerów licencji nie może przekraczać 16 znaków ASCII.

        -   Są obsługiwane tylko znaki ACSII.

        -   Następujące znaki są niedozwolone w nazwie umowy: **~ ! @ # $ ^ &amp; &#42; ( ) = + [ ] { } \ | ; : ' " &lt; &gt; /**. Nazwa może zawierać spacje.

        -   Długość nazwy pliku nie może przekraczać 128 znaków.

        -   Plik musi zawierać co najmniej jedną parę umów i nie może zawierać więcej niż 5000 par umów.

        **Format pliku**

        Ten plik możesz utworzyć przez dodanie par umów do pliku tekstowego w jednym z następujących formatów w zależności od typu organizacji zarejestrowanego w centrum VLSC. W jednym wierszu może znajdować się jedna para numerów umowy.

        -   **Klienci programu Open Value:** *numer umowy*, *powtórzony numer umowy*, *nazwa umowy*

        -   **Klienci programu Open:** *numer autoryzacji*, *powiązany numer licencji*, *nazwa umowy*

        -   **Klienci z umowami Select i Enterprise:** *numer umowy*, *powiązany numer rejestracji*, *nazwa umowy*

        Formularz **Dodawanie umów** wyświetla monit o podanie tego pliku przy dodawaniu nowej umowy.

        Oto przykład zawartości pliku csv dla klienta programu Open Value.

        `01-07001, 01-07001, Office agreements`

    -   **Dodaj szczegóły umowy ręcznie** — podaj następujące informacje, a następnie wpisz pary numerów umów w polach **Numer autoryzacji/umowy** i **Numer licencji/rejestracji/klienta**. Po wpisaniu obu numerów kliknij ikonę **Dodaj parę** , aby zapisać numery, a następnie opcjonalnie dodaj nową parę.

        -   **Nazwa umowy** — podaj unikatową nazwę umowy.

            Nazwa umowy może mieć co najwyżej 256 znaków i nie może zawierać następujących znaków: **~ ! @ # $ ^ &amp; &#42; ( ) = + [ ] { } \ | ; : ' " &lt; &gt; /**. Nazwa może zawierać spacje.

        -   **Numer autoryzacji/umowy** — podaj numer autoryzacji/umowy pary licencji.

        -   **Numer licencji/rejestracji/klienta** — podaj numer licencji/rejestracji/klienta pary licencji.

        > [!NOTE]
        > Jeśli dodasz kilka par numerów umów, usługa Intune utworzy jedną umowę o podanej nazwie, a wszystkie dodane pary będą częścią tej umowy.

    Możesz kliknąć przycisk **+**, aby dodać kolejną parę numerów umowy, lub przycisk **-**, aby usunąć podaną już parę numerów umowy.

4.  W obszarze **Wybierz grupę licencji** wykonaj jedno z następujących działań:

    -   **Dodaj umowy do grupy Umowy nieprzypisane** — wybierz tę pozycję, jeśli nie chcesz dodawać nowych umów do grupy licencji.

    -   **Dodaj umowy do nowej grupy licencji** — podaj nazwę dla nowej grupy licencji.

    -   **Dodaj umowy do istniejącej grupy licencji** — z listy **Nazwa grupy** wybierz grupę licencji, do której chcesz dodać umowy.

5.  Kliknij przycisk **OK**.

Zostanie wyświetlony widok **Wszystkie umowy**, a usługa Intune połączy się z Centrum usługi licencjonowania zbiorowego firmy Microsoft w celu zweryfikowania podanych par numerów umów.

Aby zaktualizować informacje o licencji zbiorczej po dodaniu umów licencyjnych w usłudze Intune, na stronie **Omówienie licencji** kliknij polecenie **Odśwież teraz**. To działanie powoduje pobranie bieżących informacji o licencjach z [Centrum usługi licencjonowania zbiorowego firmy Microsoft (VLSC)](http://go.microsoft.com/fwlink/?LinkId=223842)..

> [!IMPORTANT]
> Do czasu odświeżenia informacji o licencjach zbiorczych informacje na liście umów i informacje o uprawnieniach na stronie **Omówienie umów** mogą się różnić.

Po odświeżeniu informacji o licencjach zbiorczych możesz porównać informacje o licencjach z wykrytym oprogramowaniem firmy Microsoft w obszarze roboczym **Aplikacje** . Możesz też uruchomić następujące raporty dotyczące licencji:

-   **Raporty zakupu licencji** — umożliwiają wyświetlanie licencjonowanego oprogramowania w wybranych grupach licencji, co ułatwia znalezienie przerw w okresie obowiązywania licencji.

-   **Raporty instalacji licencji** — pozwalają określić, czy okres obowiązywania umowy licencyjnej jest wystarczający.

> [!NOTE]
> **Tytuł produktu** wyświetlany dla wszystkich umów licencjonowania zbiorowego firmy Microsoft to **Niedostępny**.

## Dodawanie i edytowanie umów licencyjnych na inne oprogramowanie
Oprócz umów licencjonowania zbiorowego firmy Microsoft do usługi Intune możesz także dodawać umowy licencyjne innego typu. Umowy te mogą obejmować oprogramowanie firmy Microsoft lub innych firm, które zostało zakupione w sprzedaży detalicznej.

> [!IMPORTANT]
> Przed dodaniem umowy musisz zarejestrować w usłudze Intune co najmniej jeden komputer z systemem Windows.  Ponadto co najmniej jeden zarejestrowany komputer musi zawierać pakiet oprogramowania objętego licencją, który chcesz dodać do umowy licencyjnej.

### Dodawanie innych umów dotyczących oprogramowania

1.  W [konsoli administratora usługi Microsoft Intune](https://account.manage.microsoft.com/admin/default.aspx)kliknij pozycję **Licencje**.

2.  Kliknij polecenie **Dodaj umowy** w sekcji **Inne umowy licencyjne na oprogramowanie** .

3.  Wybierz pozycję **Inne umowy licencjonowania oprogramowania** w sekcji **Wybierz typ umowy** na stronie **Dodawanie umów** .

4.  W obszarze **Dodaj szczegóły umowy** podaj następujące informacje:

    -   **Agreement name** (wymagane). Nazwa umowy może mieć co najwyżej 256 znaków i nie może zawierać następujących znaków: **~ ! @ # $ ^ &amp; &#42; ( ) = + [ ] { } \ | ; : ' " &lt; &gt; /**. Nazwa może zawierać spacje.

    -   **Wydawca** (wymagane). Podczas wpisywania nazwy wydawcy usługa pobiera nazwy wszystkich wydawców zawierające wpisane litery. Na przykład jeśli wpiszesz „soft”, usługa pobierze wszystkie nazwy wydawców zawierające ciąg „soft”, takie jak „Microsoft” i „Microsoft Research”. Nazwy wydawców są pobierane z katalogu zasobów oprogramowania. Musisz wybrać wydawcę, aby można było podać nazwę produktu.

        > [!IMPORTANT]
        > Firma, którą chcesz dodać, może nie być wyświetlana na tej liście. Możesz dodać umowy dotyczące oprogramowania tylko dla firm, które już znajdują się w katalogu zasobów oprogramowania. Firma Microsoft stale pracuje nad dodawaniem najpopularniejszych programów. Jeśli chcesz przesłać żądanie dodania firmy do tej listy, możesz to zrobić w [witrynie Intune Uservoice](https://microsoftintune.uservoice.com/).

    -   **Nazwa produktu** (wymagane). Podczas wpisywania nazwy produktu usługa pobiera nazwy wszystkich produktów zawierające wpisane litery. Musisz określić wartość pozycji **Wydawca** , aby można było określić wartość pozycji **Tytuł produktu**.

    -   **Liczba licencji** (wymagane). Podaj liczbę zakupionych licencji.

    -   **Data początkowa licencji**. Podaj datę początkową obowiązywania licencji.

    -   **Data końcowa licencji**. Podaj datę końcową obowiązywania licencji.

    -   **Szczegóły umowy**. Opcjonalnie możesz określić informacje kontaktowe, klucze rejestracji i inne informacje.

5.  W obszarze **Wybierz grupę licencji** wykonaj jedno z następujących działań:

    -   Wybierz pozycję **Dodaj umowy do grupy Nieprzypisane umowy** , jeśli nie chcesz dodać nowych umów do nowej ani istniejącej grupy licencji. W dowolnym momencie możesz dodać umowy do grup licencji zdefiniowanych przez użytkownika.

    -   Wybierz pozycję **Dodaj umowy do nowej grupy licencji** , aby dodać nowe umowy do nowej grupy licencji. Zostanie wyświetlony monit o podanie nazwy dla nowej grupy licencji.

    -   Wybierz pozycję **Dodaj umowy do istniejącej grupy licencji** , aby dodać nowe umowy do istniejącej grupy licencji. Z listy **Nazwa grupy** wybierz grupę licencji, do której chcesz dodać umowy.

6.  Kliknij przycisk **OK**.

Zostanie wyświetlony widok listy **Wszystkie umowy** .

## Zarządzanie umowami licencyjnymi
Umowy licencjonowania dotyczące oprogramowania można dodać do grup licencji. Możesz użyć grup licencji do organizowania umów licencyjnych w logiczne jednostki odpowiednie dla Twojej organizacji. Ponadto możesz usunąć wcześniej utworzone umowy licencyjne.

|||
|-|-|
|Zadanie|Szczegóły|
|Tworzenie grupy licencji|Na stronie **Przegląd** w obszarze roboczym **Licencje** kliknij polecenie **Utwórz grupę licencji** w menu **Zadania** . **Uwaga:** możesz utworzyć maksymalnie 500 grup licencji.|
|Zmienianie nazwy grupy licencji|W obszarze roboczym **Licencje** wybierz grupę licencji, a następnie kliknij polecenie **Edytuj grupę licencji** w menu **Zadania** .|
|Usuwanie grupy licencji|W obszarze roboczym **Licencje** wybierz grupę licencji, a następnie kliknij polecenie **Usuń grupę licencji** w menu **Zadania** . **Porada:** wszystkie licencje należące do usuniętej grupy zostaną przeniesione do grupy licencji **Nieprzypisane umowy**.|
|Usuwanie umowy licencyjnej|W obszarze roboczym **Licencje** wybierz umowę, a następnie kliknij opcję **Usuń**. **Porada:** aby zaktualizować informacje o licencjach po usunięciu umów licencjonowania zbiorowego, kliknij polecenie **Odśwież teraz** na stronie **Omówienie licencji** lub na karcie **Ogólne** dla konkretnej grupy licencji.|





<!--HONumber=May16_HO1-->


