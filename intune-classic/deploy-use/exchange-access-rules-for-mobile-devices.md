---
title: "Reguły dostępu do programu Exchange dla urządzeń przenośnych | Microsoft Docs"
description: "Reguły dostępu do programu Exchange ActiveSync służą do zezwalania na połączenia lub blokowania połączeń urządzeń z programem EAS"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 208b9f45-02d9-413a-b86a-8bad9b5008fa
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8b2bd3ecba0b597bc742ea08872ffe8fc58155cf
ms.openlocfilehash: 47d1437159da85b958e6e6fa91fa743d7746c5ce
ms.lasthandoff: 04/24/2017


---

# <a name="exchange-access-rules-for-mobile-devices"></a>Reguły dostępu do programu Exchange dla urządzeń przenośnych

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Reguły dostępu dla urządzeń przenośnych określają poziom dostępu tych urządzeń do programu Exchange ActiveSync. Te ustawienia dotyczą wszystkich urządzeń przenośnych, w tym niezarejestrowanych w usłudze Microsoft Intune. Można rozpocząć od zdefiniowania **reguły domyślnej**, która dotyczy wszystkich urządzeń przenośnych, do których nie zastosowano reguły niestandardowej.

Poniższa tabela przedstawia poziomy dostępu zarządzane przez program Exchange ActiveSync:

|Poziom dostępu|Opis|
|----------------|---------------|
|**Zezwalaj tym urządzeniom na dostęp do programu Exchange**|W stanie *zezwalaj na dostęp* urządzenia przenośne mogą przeprowadzać synchronizację za pomocą programu Exchange ActiveSync i łączyć się z serwerem Exchange w celu pobrania poczty e-mail i zarządzania Kalendarzem, Kontaktami, Zadaniami i Notatkami. Będzie to możliwe tak długo, jak długo urządzenie będzie zgodne z dowolnymi zasadami skrzynek pocztowych programu Exchange ActiveSync skonfigurowanymi w programie Exchange, o ile administrator programu Exchange nie zablokował użytkownika lub danego urządzenia.|
|**Blokuj tym urządzeniom dostęp do programu Exchange**|W stanie *blokuj dostęp* urządzenia przenośne są zablokowane i nie mogą się łączyć z serwerem Exchange. Urządzenia otrzymują powiadomienie o błędzie HTTP 403 — Dostęp zabroniony. Użytkownik otrzymuje z serwera Exchange wiadomość e-mail z informacją o zablokowaniu dostępu urządzenia przenośnego do skrzynki pocztowej. Ta wiadomość nie może być wyświetlana na zablokowanym urządzeniu przenośnym. Za pomocą zadania **Ustaw powiadomienie użytkownika** można dodać do tej wiadomości własny tekst z instrukcjami dla użytkowników, których urządzenia zostały zablokowane. |
|**Poddaj te urządzenia kwarantannie, aby można było je później zablokować lub zezwolić im na działanie**|Gdy urządzenie przenośne jest objęte kwarantanną, może połączyć się z serwerem Exchange. Jednak będzie mieć tylko ograniczony dostęp do danych. Użytkownik może dodawać zawartość do własnych folderów Kalendarz, Kontakty, Zadania i Notatki, ale serwer nie zezwala urządzeniu na pobranie zawartości ze skrzynki pocztowej użytkownika. Użytkownik otrzymuje jedną wiadomość e-mail z informacją, że urządzenie przenośne jest objęte kwarantanną. Ta wiadomość jest wysyłania do urządzenia i skrzynki pocztowej użytkownika. Za pomocą zadania **Ustaw powiadomienie użytkownika** można dodać do tej wiadomości własny tekst z instrukcjami dla użytkowników, których urządzenia zostały poddane kwarantannie.|

Strategia dostępu jest połączeniem opcji **Reguła domyślna** i **Wyjątki dla platform**, które są stosowane do wszystkich urządzeń przenośnych połączonych z programem Exchange. W poniższej tabeli przedstawiono kilka przykładowych strategii dostępu.

|Strategia dostępu|Opis|
|-------------------|---------------|
|Lista dozwolonych|*Lista dozwolonych* umożliwia udzielenie dostępu znanym urządzeniem z listy i ograniczenie dostępu wszystkim innym urządzeniom. W tym celu musisz utworzyć reguły niestandardowe dotyczące platform urządzeń, która mają dostęp do skrzynek pocztowych użytkowników. Po utworzeniu takiej reguły musisz ustawić domyślną regułę dostępu blokującą lub poddającą kwarantannie wszystkie inne urządzenia. Aby dodać nowe urządzenie do listy dozwolonych, utwórz nową regułę niestandardową.|
|Lista zablokowanych|*Listy zablokowanych* możesz użyć, aby domyślnie przyznać dostęp wszystkim urządzeniom, lecz blokować zbiór urządzeń, które nie mają mieć dostępu do Twojej organizacji. Listę zablokowanych tworzy się za pomocą reguł niestandardowych blokujących platformy urządzeń, które nie mają być synchronizowane ze skrzynkami pocztowymi organizacji. Zalecamy ustawienie reguły domyślnej zezwalającej na dostęp wszystkich urządzeń, które nie są jawnie zablokowane przez istniejące reguły. Aby dodać nowe urządzenie lub zbiór urządzeń do listy zablokowanych, utwórz nową regułę niestandardową.|
|Mieszane zezwalanie i blokowanie|Oprócz tworzenia list dozwolonych i zablokowanych możesz poddawać kwarantannie nowe urządzenia przenośne wprowadzane do organizacji, na czas oceny. Na przykład jeśli masz listę zablokowanych urządzeń przenośnych, które są niedozwolone w organizacji, i listę dozwolonych urządzeń przenośnych, które są dozwolone w organizacji, możesz ustawić kwarantannę jako regułę domyślną. Wszystkie inne urządzenia są automatycznie poddawane kwarantannie. Takie działanie umożliwia wykrywanie nowych urządzeń w miarę ich wprowadzania do organizacji i decydowanie, czy mają zostać dodane do listy dozwolonych, czy zablokowanych.|
Poniższa procedura opisuje sposób tworzenia reguły niestandardowej.

## <a name="create-a-default-access-rule"></a>Tworzenie domyślnej reguły dostępu

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) wybierz pozycję **Zasady** &gt; **Exchange ActiveSync**.

2.  Na liście **Reguła domyślna** wybierz regułę dostępu, którą chcesz stosować do wszystkich urządzeń przenośnych nieobjętych wyjątkiem określonym za pomocą reguły ani wyjątkiem osobistym. Wybierz polecenie **Zapisz**.

Poniższa procedura opisuje sposób tworzenia reguły niestandardowej:

## <a name="create-a-custom-access-rule"></a>Tworzenie niestandardowej reguły dostępu

1. W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) wybierz pozycję **Zasady** &gt; **Exchange ActiveSync**.

2.  Na liście **Wyjątki dla platform** wybierz polecenie **Dodaj regułę**, a następnie utwórz regułę niestandardową. Wybierz polecenie **Zapisz**.

