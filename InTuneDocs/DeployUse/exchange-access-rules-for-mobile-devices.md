---
# required metadata

title: Reguły dostępu do programu Exchange dla urządzeń przenośnych zarządzanych przez usługę Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 208b9f45-02d9-413a-b86a-8bad9b5008fa

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Reguły dostępu do programu Exchange dla urządzeń przenośnych
Reguły dostępu do programu Exchange dla urządzeń przenośnych określają poziom dostępu tych urządzeń do programu Exchange. Te ustawienia dotyczą wszystkich urządzeń przenośnych, włącznie z urządzeniami niezarejestrowanymi w usłudze Microsoft Intune. Możesz rozpocząć od zdefiniowania opcji **Reguła domyślna** która będzie stosowana dla wszystkich urządzeń przenośnych, dla których nie zastosowano reguły niestandardowej. Poniższa tabela zawiera poziomy dostępu zarządzane przez program Exchange ActiveSync:

|Poziom dostępu|Opis|
|----------------|---------------|
|**Zezwalaj tym urządzeniom przenośnym na dostęp do programu Exchange, o ile w regule niestandardowej nie ma innego polecenia**|Gdy *dostęp jest dozwolony*, urządzenia przenośne mogą przeprowadzać synchronizację za pomocą programu Exchange ActiveSync i łączyć się z serwerem Exchange w celu pobrania poczty e-mail i zarządzania informacji kalendarza, kontaktów, zadań i notatek. Będzie to możliwe tak długo, jak długo urządzenie będzie zgodne ze skonfigurowanymi **Zasadami zabezpieczeń urządzeń przenośnych w usłudze Intune**, o ile administrator programu Exchange nie zablokował użytkownika lub danego urządzenia.|
|**Blokuj tym urządzeniom przenośnym dostęp do programu Exchange, o ile w regule niestandardowej nie ma innego polecenia**|Gdy *dostęp jest zablokowany*, urządzenia przenośne są zablokowane i nie mogą łączyć się z serwerem Exchange. Na urządzeniach będzie zwracany błąd HTTP 403 — Dostęp zabroniony. Użytkownik otrzyma wiadomość e-mail od serwera Exchange z informacją o tym, że dostęp urządzenia przenośnego do skrzynki pocztowej został zablokowany. Ta wiadomość nie może być wyświetlana na zablokowanym urządzeniu przenośnym. Możesz dodać do tej wiadomości własny tekst z instrukcjami dla użytkowników, których urządzenia zostały zablokowane, za pomocą zadania **Ustaw powiadomienie użytkownika**.|
|**Poddaj te urządzenia przenośne kwarantannie, aby decyzję w sprawie każdego z nich można było podjąć później, o ile w regule niestandardowej nie ma innego polecenia**|Gdy urządzenie przenośne jest objęte kwarantanną, może połączyć się z serwerem Exchange. Jednak będzie mieć tylko ograniczony dostęp do danych. Użytkownik będzie mógł dodawać zawartość do własnych folderów Kalendarz, Kontakty, Zadania i Notatki, ale serwer nie będzie zezwalać urządzeniu na pobranie jakiejkolwiek zawartości ze skrzynki pocztowej użytkownika. Użytkownik otrzyma pojedynczą wiadomość e-mail z informacją, że urządzenie przenośne jest objęte kwarantanną. Ta wiadomość zostanie odebrana na urządzeniu i w skrzynce pocztowej użytkownika. Możesz dodać do tej wiadomości własny tekst z instrukcjami dla użytkowników, których urządzenia zostały objęte kwarantanną, za pomocą zadania **Ustaw powiadomienie użytkownika** .|

Strategia dostępu jest połączeniem opcji **Reguła domyślna** i **Reguły niestandardowe** , które są stosowane do wszystkich urządzeń przenośnych połączonych z programem Exchange. W tabeli poniżej wymieniono kilka przykładowych strategii dostępu.

|Strategia dostępu|Opis|
|-------------------|---------------|
|Lista dozwolonych|*Lista dozwolonych* umożliwia udzielenie dostępu dla znanych urządzeń z listy i ograniczenie dostępu dla wszystkich innych urządzeń. W tym celu musisz utworzyć reguły niestandardowe, aby umożliwić wybranym urządzeniom dostęp do skrzynek pocztowych użytkowników. Po utworzeniu takiej reguły musisz ustawić domyślną regułę dostępu blokującą lub poddającą kwarantannie wszystkie inne urządzenia. Aby dodać nowe urządzenie do listy dozwolonych, utwórz nową regułę niestandardową.|
|Lista zablokowanych|*Listy zablokowanych* możesz użyć, aby domyślnie przyznać dostęp wszystkim urządzeniom, lecz blokować zbiór urządzeń, które nie mają mieć dostępu do Twojej organizacji. Listę zablokowanych tworzy się za pomocą reguł niestandardowych blokujących urządzenia, które nie mają być synchronizowane ze skrzynkami pocztowymi organizacji. Należy ustawić regułę domyślną zezwalającą na dostęp wszystkich urządzeń, które nie są jawnie zablokowane przez istniejące reguły. Aby dodać nowe urządzenie lub zbiór urządzeń do listy zablokowanych, utwórz nową regułę niestandardową.|
|Mieszane zezwalanie i blokowanie|Oprócz tworzenia list dozwolonych i zablokowanych możesz poddawać kwarantannie nowe urządzenia przenośne wprowadzane do organizacji, na czas oceny. Na przykład jeśli masz listę zablokowanych urządzeń przenośnych, które są niedozwolone w organizacji, i listę dozwolonych urządzeń przenośnych, które są dozwolone w organizacji, możesz ustawić kwarantannę jako regułę domyślną. Wszystkie inne urządzenia zostaną automatycznie poddane kwarantannie. Takie działanie umożliwia wykrywanie nowych urządzeń w miarę ich wprowadzania do organizacji i decydowanie, czy mają zostać dodane do listy dozwolonych, czy zablokowanych.|
Poniższa procedura opisuje sposób tworzenia reguły niestandardowej.

## Tworzenie domyślnej reguły dostępu

1.  Przejdź do [konsoli administracyjnej usługi Microsoft Intune](http://manage.microsoft.com) &gt; **Zasady** &gt; **Reguły dostępu do serwera Exchange dla urządzeń przenośnych**.

2.  Na liście **Reguła domyślna** wybierz regułę dostępu, która ma być stosowana dla wszystkich urządzeń przenośnych, które nie są objęte wyjątkiem określonym za pomocą reguły ani wyjątkiem osobistym. Wybierz polecenie **Zapisz**.

Poniższa procedura opisuje sposób tworzenia reguły niestandardowej.

## Tworzenie niestandardowej reguły dostępu

1. Przejdź do [konsoli administracyjnej usługi Microsoft Intune](http://manage.microsoft.com) &gt; **Zasady** &gt; **Reguły dostępu do serwera Exchange dla urządzeń przenośnych**.

2.  Na liście **Reguły niestandardowe** wybierz polecenie **Dodaj regułę** i utwórz regułę niestandardową. Wybierz polecenie **Zapisz**.


<!--HONumber=May16_HO1-->


