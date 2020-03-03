---
title: Wysyłanie powiadomień niestandardowych do użytkowników za pomocą usługi Microsoft Intune
titleSuffix: Microsoft Intune
description: Tworzenie i wysyłanie niestandardowych powiadomień push do użytkowników urządzeń z systemami iOS/iPadOS i Android przy użyciu usługi Intune
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/25/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: jinyoon
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5195ee83efb68cea061e69f5cad49e9d43458450
ms.sourcegitcommit: 29f3ba071c9348686d3ad6f3b8864d8557e05b97
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/26/2020
ms.locfileid: "77609360"
---
# <a name="send-custom-notifications-in-intune"></a>Wysyłanie powiadomień niestandardowych w usłudze Intune  

Za pomocą usługi Microsoft Intune można wysyłać niestandardowe powiadomienia do użytkowników urządzeń zarządzanych z systemami iOS/iPadOS i Android. Te komunikaty są wyświetlane w postaci standardowych powiadomień push z aplikacji Portal firmy i aplikacji Microsoft Intune na urządzeniu użytkownika, podobnie jak powiadomienia z innych aplikacji wyświetlane na urządzeniu. Powiadomienia niestandardowe usługi Intune nie są obsługiwane na urządzeniach z systemem macOS ani Windows.   

Niestandardowe komunikaty powiadomień zawierają krótki tytuł i treść komunikatu składającą się maksymalnie z 500 znaków. Te komunikaty można dostosować do wszelkich celów komunikacji ogólnej.

### <a name="what-the-notification-looks-like-on-an-iosipados-device"></a>Jak wygląda powiadomienie na urządzeniu z systemem iOS/iPadOS

Jeśli aplikacja Portal firmy zostanie otwarta na urządzeniu z systemem iOS/iPadOS, powiadomienie będzie podobne do poniższego zrzutu ekranu:

> [!div class="mx-imgBorder"]
> ![Powiadomienie testowe Portalu firmy w systemie iOS/iPadOS](./media/custom-notifications/105046-1.png)

Jeśli urządzenie zostało zablokowane, powiadomienie jest podobne do poniższego zrzutu ekranu:

> [!div class="mx-imgBorder"]
> ![Powiadomienie testowe na zablokowanym urządzeniu z systemem iOS/iPadOS](./media/custom-notifications/105046-2.png)

### <a name="what-the-notification-looks-like-on-an-android-device"></a>Jak wygląda powiadomienie na urządzeniu z systemem Android

Jeśli aplikacja Portal firmy zostanie otwarta na urządzeniu z systemem Android, powiadomienie będzie podobne do poniższego zrzutu ekranu:

> [!div class="mx-imgBorder"]
> ![Powiadomienie testowe w systemie Android](./media/custom-notifications/105046-3.png)

## <a name="common-scenarios-for-sending-custom-notifications"></a>Typowe scenariusze wysyłania powiadomień niestandardowych  

- Można również powiadomić wszystkich pracowników o zmianie harmonogramu, na przykład o zamknięciach budynków z powodu niesprzyjających warunków pogodowych.
- Wyślij powiadomienie do użytkownika pojedynczego urządzenia w celu przekazania pilnego żądania, takiego jak ponowne uruchomienie urządzenia w celu ukończenia instalacji aktualizacji.

## <a name="considerations-for-using-custom-notifications"></a>Zagadnienia dotyczące korzystania z powiadomień niestandardowych

**Konfiguracja urządzeń**

- Aby użytkownicy mogli odbierać powiadomienia niestandardowe, na urządzeniach musi być zainstalowana aplikacja Portal firmy lub aplikacja Microsoft Intune. Użytkownicy muszą także mieć skonfigurowane uprawnienia, aby umożliwić aplikacji Portal firmy lub aplikacji Microsoft Intune wysyłanie powiadomień push. W razie potrzeby aplikacje Portal firmy i Microsoft Intune mogą monitować użytkowników o zezwolenie na powiadomienia.
- W systemie Android Usługi Google Play są wymaganą zależnością.
- Urządzenie musi być zarejestrowane w usłudze MDM.

**Uprawnienia**:

- Aby wysyłać powiadomienia do grup, Twoje konto musi mieć następujące uprawnienia RBAC w usłudze Intune: *Organizacja* > **Aktualizowanie**
- Aby wysyłać powiadomienia do urządzenia, Twoje konto musi mieć następujące uprawnienia RBAC w usłudze Intune: *Zadania zdalne* > **Wysyłanie powiadomień niestandardowych**.

**Tworzenie powiadomień**:
 
- Aby utworzyć wiadomość, użyj konta z przypisaną rolą usługi Intune, która zawiera poprawne uprawnienie zgodne z opisem z poprzedniej sekcji *Uprawnienia*. Aby przypisać uprawnienia użytkownikowi, zobacz [Przypisania ról](../fundamentals/role-based-access-control.md#role-assignments).
- Powiadomienia niestandardowe mają ograniczenia do 50 znaków w tytule i 500 znaków w treści komunikatu.  
- Usługa Intune nie zapisuje tekstu z poprzednio wysłanych powiadomień niestandardowych. Aby ponownie wysłać komunikat, należy go ponownie utworzyć.  
- Można wysłać maksymalnie 25 komunikatów do grup na godzinę. To ograniczenie obowiązuje na poziomie dzierżawy. To ograniczenie nie ma zastosowania w przypadku wysyłania powiadomień do poszczególnych urządzeń.
- Można wysłać maksymalnie 25 komunikatów do grup na godzinę. To ograniczenie obowiązuje na poziomie dzierżawy. To ograniczenie nie ma zastosowania w przypadku wysyłania powiadomień do użytkowników indywidualnych.
- Podczas wysyłania komunikatów do poszczególnych urządzeń można wysłać do tego samego urządzenia maksymalnie 10 komunikatów na godzinę.
- Powiadomienia można wysyłać do użytkowników w grupach. W przypadku wysyłania powiadomień do grup każde powiadomienie można kierować bezpośrednio do maksymalnie 25 grup. Grupy zagnieżdżone nie są wliczane do tej liczby. W przypadku wysyłania powiadomienia do grupy wiadomości są kierowane tylko do użytkowników w grupie i są wysyłane do poszczególnych urządzeń z systemem iOS lub Android, które zostały zarejestrowane przez użytkownika. Urządzenia w grupie będą ignorowane podczas kierowania powiadomienia.
- Powiadomienia można wysyłać do pojedynczego urządzenia. Zamiast korzystać z grup wybiera się urządzenie, a następnie używa zdalnej [akcji urządzenia](device-management.md#available-device-actions) w celu wysłania powiadomienia niestandardowego.  

**Dostarczanie**:

- Usługa Intune wysyła komunikaty do aplikacji Portal firmy lub aplikacji Microsoft Intune użytkowników, która następnie tworzy powiadomienie push. Użytkownicy nie muszą być zalogowani do aplikacji, aby powiadomienie zostało wypchnięte do urządzenia, ale urządzenie musi być zarejestrowane przez docelowego użytkownika.
- Usługa Intune, oraz aplikacje Portal firmy i Microsoft Intune nie mogą zagwarantować dostarczania powiadomienia niestandardowego. Powiadomienia niestandardowe mogą pojawiać się nawet z kilkugodzinnym opóźnieniem, dlatego nie powinny być używane do przesyłania pilnych komunikatów.  
- Komunikaty powiadomień niestandardowych z usługi Intune są wyświetlane na urządzeniach jako standardowe powiadomienia push. Jeśli aplikacja Portal firmy jest otwarta na urządzeniu z systemem iOS w momencie odebrania powiadomienia, zostanie ono wyświetlone w aplikacji zamiast w postaci systemowego powiadomienia push.  
- W zależności od ustawień urządzenia powiadomienia niestandardowe mogą być widoczne na ekranach blokady na urządzeniach z systemami iOS/iPadOS i Android.  
- Na urządzeniach z systemem Android inne aplikacje mogą mieć dostęp do danych powiadomień niestandardowych. Nie używaj ich do przesyłania poufnych komunikatów.  
- Użytkownicy urządzenia, które zostało ostatnio wyrejestrowane, lub użytkownicy usunięci z grupy mogą nadal otrzymywać powiadomienia niestandardowe, które są następnie wysyłane do tej grupy.  Podobnie jeśli dodasz użytkownika do grupy po wysłaniu powiadomienia niestandardowego do tej grupy, nowo dodany użytkownik może otrzymać ten wysłany wcześniej komunikat powiadomienia.  

## <a name="send-a-custom-notification-to-groups"></a>Wysyłanie powiadomień niestandardowych do grup

1. Zaloguj się do [centrum administracyjnego usługi Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) przy użyciu konta z uprawnieniami do tworzenia i wysyłania powiadomień, a następnie przejdź do pozycji **Administracja dzierżawą** > **Powiadomienia niestandardowe**.  

2. Na karcie Podstawy określ poniższe opcje, a następnie wybierz przycisk **Dalej**, aby kontynuować.  
   - **Tytuł** — określ tytuł powiadomienia. Tytuły mogą zawierać maksymalnie 50 znaków.  
   - **Treść** — wpisz komunikat. Komunikaty mogą zawierać maksymalnie 500 znaków.

   ![Tworzenie powiadomienia niestandardowego](./media/custom-notifications/custom-notifications.png)  

3. Na karcie **Przypisania** wybierz grupy, do których chcesz wysłać powiadomienie niestandardowe, a następnie wybierz przycisk Dalej, aby kontynuować. Wysłanie powiadomienia do grupy spowoduje jego skierowanie tylko do użytkowników tej grupy. Powiadomienie zostanie przekazane do wszystkich urządzeń z systemem iOS i Android zarejestrowanych przez tych użytkowników.

4. Na karcie **Przeglądanie + tworzenie** przejrzyj informacje, a następnie wybierz pozycję **Utwórz**, aby wysłać powiadomienie.  

Usługa Intune natychmiast przetwarza tworzone komunikaty. Jedynym potwierdzeniem wysłania komunikatu jest powiadomienie wyświetlane w usłudze Intune potwierdzające wysłanie powiadomienia niestandardowego.  

![Potwierdzenie wysłania powiadomienia](./media/custom-notifications/notification-sent.png)  

Usługa Intune nie śledzi wysyłanych powiadomień niestandardowych, a urządzenia nie rejestrują odbioru poza centrum powiadomień urządzenia. Powiadomienie może być zawarte w tymczasowym dzienniku diagnostycznym, jeśli użytkownik żąda obsługi z poziomu aplikacji Portal firmy lub Intune.

## <a name="send-a-custom-notification-to-a-single-device"></a>Wysyłanie powiadomień niestandardowych do pojedynczego urządzenia

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) przy użyciu konta z uprawnieniami do tworzenia i wysyłania powiadomień, a następnie przejdź do pozycji **Urządzenia** > **Wszystkie urządzenia**.

2. Kliknij dwukrotnie nazwę urządzenia zarządzanego, do którego chcesz wysłać powiadomienie, aby otworzyć stronę *Przegląd*.

3. Na stronie **Przegląd** wybierz akcję urządzenia **Wyślij powiadomienie niestandardowe**, aby otworzyć okienko *Wyślij powiadomienie niestandardowe*. Jeśli ta opcja jest niedostępna, kliknij przycisk **...** (wielokropek) w prawym górnym rogu strony, a następnie wybierz pozycję **Wyślij powiadomienie niestandardowe**.

4. W okienku **Wyślij powiadomienie niestandardowe** określ następujące szczegóły komunikatu:  

   - **Tytuł** — określ tytuł powiadomienia. Tytuły mogą zawierać maksymalnie 50 znaków.  
   - **Treść** — wpisz komunikat. Komunikaty mogą zawierać maksymalnie 500 znaków.  

5. Wybierz pozycję **Wyślij**, aby wysłać powiadomienie niestandardowe do urządzenia. W przeciwieństwie do powiadomień wysyłanych do grup nie następuje konfigurowanie przypisania ani przeglądanie komunikatu przed jego wysłaniem.  

Usługa Intune natychmiast przetwarza komunikat. Jedynym potwierdzeniem wysłania komunikatu jest powiadomienie usługi Intune, które otrzymasz w konsoli, zawierające tekst wysyłanego komunikatu.  

## <a name="receive-a-custom-notification"></a>Odbieranie powiadomień niestandardowych

Na urządzeniu użytkownicy widzą komunikaty powiadomień niestandardowych wysyłanych przez usługę Intune jako standardowe powiadomienia push z aplikacji Portal firmy lub aplikacji Microsoft Intune. Te powiadomienia są podobne do powiadomień push otrzymywanych przez użytkowników z innych aplikacji na urządzeniu.  

Jeśli na urządzeniu z systemem iOS/iPadOS aplikacja Portal firmy jest otwarta w momencie odebrania powiadomienia, zostanie ono wyświetlone w aplikacji zamiast w postaci powiadomienia push.  

Powiadomienie pozostaje widoczne do momentu jego odrzucenia przez użytkownika.  

## <a name="next-steps"></a>Następne kroki

[Zarządzanie urządzeniami](device-management.md)
