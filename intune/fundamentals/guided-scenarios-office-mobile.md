---
title: Scenariusz z przewodnikiem — bezpieczne aplikacje mobilne Microsoft Office
titleSuffix: Microsoft Intune
description: Zapoznaj się ze scenariuszem z przewodnikiem dotyczącym wdrażania bezpiecznych aplikacji mobilnych Microsoft Office w portalu zarządzania urządzeniami na platformie Microsoft 365.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/06/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0232855773626693d848f77e561c51d281739215
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514612"
---
# <a name="guided-scenario---secure-microsoft-office-mobile-apps"></a>Scenariusz z przewodnikiem — bezpieczne aplikacje mobilne Microsoft Office 

Postępując zgodnie ze wskazówkami zawartymi w tym scenariuszu, możesz włączyć w portalu zarządzania urządzeniami podstawową ochronę aplikacji na urządzeniach z systemem iOS/iPadOS i Android za pomocą usługi Intune.

Gdy włączysz ochronę aplikacji, wymuszone zostaną następujące akcje: 
- Szyfrowanie plików służbowych.
- Konieczność podania kodu PIN w celu uzyskania dostępu do plików służbowych.
- Konieczność resetowania kodu PIN po pięciu nieudanych próbach.
- Blokowanie tworzenia kopii zapasowych plików służbowych w usługach iTunes, iCloud lub usługach tworzenia kopii zapasowych systemu Android.  
- Konieczność zapisywania plików służbowych tylko w usłudze OneDrive lub programie SharePoint.
- Zapobieganie ładowaniu plików służbowych przez chronione aplikacje na urządzeniach ze zdjętymi zabezpieczeniami lub odblokowanym dostępem.
- Blokowanie dostępu do plików służbowych, jeśli urządzenie od 720 minut znajduje się w trybie offline.
- Usuwanie plików służbowych, jeśli urządzenie od 90 dni jest w trybie offline. 

## <a name="background"></a>Informacje dodatkowe

Aplikacje mobilne pakietu Office, jak również przeglądarka Microsoft Edge dla urządzeń przenośnych, obsługują podwójną tożsamość. Podwójna tożsamość umożliwia aplikacjom osobne zarządzanie plikami służbowymi i osobistymi. 

![Obraz przedstawiający dane firmowe i osobiste](./media/guided-scenarios-office-mobile/guided-scenarios-office-mobile-01.png)

[Zasady ochrony aplikacji w usłudze Intune](~/apps/app-protection-policy.md) pomagają chronić pliki służbowe na urządzeniach zarejestrowanych w usłudze Intune. Możesz również korzystać z zasad ochrony aplikacji na urządzeniach należących do pracowników, które nie zostały zarejestrowane na potrzeby zarządzania przez usługę Intune. W takim przypadku, nawet jeśli firma nie zarządza danym urządzeniem, musisz upewnić się, że służbowe pliki i zasoby zostały odpowiednio zabezpieczone.

Zasady ochrony aplikacji pozwalają zapobiegać zapisywaniu plików służbowych w niechronionych lokalizacjach przez użytkowników. Można również ograniczyć przenoszenie danych do innych aplikacji, które nie są chronione przez zasady ochrony aplikacji. Ustawienia zasad ochrony aplikacji obejmują:
- Zasady relokacji danych, takie jak **Zapisz kopie danych organizacji** i **Ogranicz wycinanie, kopiowanie i wklejanie**.
- Ustawienia zasad dostępu, takie jak „Wymagaj prostego numeru PIN w celu udzielenia dostępu” i „Blokuj uruchamianie aplikacji zarządzanych na urządzeniach ze zdjętymi zabezpieczeniami systemu lub odblokowanym dostępem do konta administratora”.

Dostęp warunkowy oparty na aplikacjach oraz zarządzanie aplikacjami klienckimi tworzą dodatkową warstwę zabezpieczeń i gwarantują, że tylko aplikacje klienckie, które obsługują zasady ochrony aplikacji usługi Intune, mogą uzyskać dostęp do usługi Exchange Online i innych usług pakietu Office 365.

Aplikacje poczty wbudowane w systemach iOS/iPadOS i Android można zablokować, zezwalając na dostęp do usługi Exchange Online wyłącznie aplikacji Microsoft Outlook. Ponadto aplikacjom, które nie mają zastosowanych zasad ochrony aplikacji usługi Intune, można zablokować dostęp do usługi SharePoint Online.

W tym przykładzie administrator zastosował zasady ochrony aplikacji w odniesieniu do aplikacji Outlook, a następuje zastosował regułę dostępu warunkowego, która powoduje dodanie aplikacji Outlook do listy zatwierdzonych aplikacji, które mogą być używane podczas uzyskiwania dostępu do firmowej poczty e-mail.

![Przepływ procesów dostępu warunkowego aplikacji Outlook](./media/guided-scenarios-office-mobile/guided-scenarios-office-mobile-02.png)

## <a name="prerequisites"></a>Wymagania wstępne

Wymagane są następujące uprawnienia administratora usługi Intune:

   - Uprawnienia do odczytu, tworzenia, usuwania i przypisywania aplikacji zarządzanych
   - Uprawnienia do odczytu, tworzenia i przypisywania zestawów zasad
   - Uprawnienia do odczytu w organizacji

## <a name="step-1---introduction"></a>Krok 1. Wprowadzenie

Postępowanie zgodnie ze scenariuszem z przewodnikiem **Ochrona aplikacji w usłudze Intune** zapobiega udostępnianiu danych lub ich wyciekowi poza organizację. 

Przypisani użytkownicy systemów iOS/iPadOS i Android muszą wprowadzić kod PIN przy każdym otwarciu aplikacji pakietu Office. Po pięciu nieudanych próbach wprowadzenia kodu PIN użytkownicy muszą zresetować kod PIN. Ta zmiana nie ma wpływu na użytkowników, którzy już teraz muszą wprowadzać kod PIN na urządzeniach.

### <a name="what-you-will-need-to-continue"></a>Co jest konieczne, aby przejść dalej

Będą potrzebne informacje na temat aplikacji, których potrzebują użytkownicy, i na temat sposobu uzyskiwania dostępu do nich. Upewnij się, że masz pod ręką następujące informacje:
- Lista aplikacja pakietu Office zatwierdzonych do użytku firmowego.
- Wszelkie wymagania dotyczące kodu PIN do uruchamiania zatwierdzonych aplikacji na urządzeniach niezarządzanych.

## <a name="step-2---basics"></a>Krok 2. Podstawowe informacje

W tym kroku należy wprowadzić **prefiks** oraz **opis** nowej zasady ochrony aplikacji. Po dodaniu **prefiksu** szczegóły związane z zasobami tworzonymi w scenariuszu z przewodnikiem zostaną zaktualizowane. Te szczegóły ułatwią odnalezienie zasad później, gdyby konieczna była zmiana przypisań lub konfiguracji. 

> [!TIP]
> Dobrym pomysłem jest zanotowanie utworzonych zasobów, aby można je było odnaleźć w przyszłości.

## <a name="step-3---apps"></a>Krok 3. Aplikacje

Aby ułatwić rozpoczęcie pracy, w tym scenariuszu z przewodnikiem zostały już wstępnie wybrane następujące aplikacje mobilne, które mają być chronione na urządzeniach z systemem iOS/iPadOS i Android:
- Microsoft Excel 
- Microsoft Word 
- Microsoft Teams 
- Microsoft Edge 
- Microsoft PowerPoint 
- Microsoft Outlook 
- Microsoft OneDrive 

W tym scenariuszu z przewodnikiem te aplikację zostaną również skonfigurowane do otwierania linków internetowych w przeglądarce Microsoft Edge w celu zagwarantowania, że witryny służbowe są otwierane w chronionej przeglądarce.

Zmodyfikuj listę aplikacji zarządzanych przy użyciu zasad, które chcesz chronić. Dodaj lub usuń aplikacje na tej liście. 

Po wybraniu aplikacji kliknij pozycję **Dalej**.

## <a name="step-4---configuration"></a>Krok 4. Konfiguracja

W tym kroku należy skonfigurować wymagania dotyczące uzyskiwania dostępu do firmowych plików i wiadomości e-mail w tych aplikacjach oraz ich udostępniania. Domyślnie użytkownicy mogą zapisywać dane na firmowych kontach usługi OneDrive lub programu SharePoint.

| Ustawienie | Opis | Wartość domyślna |
|---------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------|
| Typ kodu PIN | Numeryczne kody PIN składają się tylko z cyfr. Kody dostępu składają się ze znaków alfanumerycznych i znaków specjalnych.  W systemach iOS/iPadOS, aby skonfigurować typ „Kod dostępu”, aplikacja musi mieć zestaw SDK usługi Intune w wersji 7.1.12 lub nowszej. Typ numeryczny nie ma ograniczeń wersji zestawu SDK usługi Intune. | Numeryczne |
| Wybierz minimalną długość kodu PIN | określ minimalną liczbę cyfr w sekwencji numeru PIN. | 6 |
| Ponownie sprawdź wymagania dostępu po (w minutach) | Jeśli aplikacja zarządzana przy użyciu zasad jest nieaktywna dłużej niż określona liczba minut nieaktywności, w aplikacji wyświetli się monit, aby ponownie sprawdzić wymagania dostępu (czyli kod PIN, ustawienia uruchamiania warunkowego) po uruchomieniu aplikacji. | 30 |
| Drukowanie danych organizacji | Jeśli aplikacja jest zablokowana, drukowanie chronionych danych jest niemożliwe. | Zablokowanie |
| Otwieranie linków do aplikacji zarządzanych przy użyciu zasad w przeglądarkach niezarządzanych | Jeśli aplikacja zostanie zablokowana, linki do aplikacji zarządzanych przy użyciu zasad muszą zostać otwarte w zarządzanej przeglądarce. | Zablokowanie |
| Kopiowanie danych do niezarządzanych aplikacji | Jeśli aplikacja zostanie zablokowana, dane zarządzane pozostaną w zarządzanych aplikacjach. | Zezwalaj |

## <a name="step-5---assignments"></a>Krok 5. Przypisania

W tym kroku możesz wybrać grupy użytkowników, którym chcesz przyznać dostęp do danych firmowych. Ochrona aplikacji jest przypisana do użytkowników, a nie urządzeń, a więc dane firmowe będą bezpieczne bez względu na używane urządzenie i jego stan rejestracji.

Użytkownicy bez przypisanych zasad ochrony aplikacji i ustawień dostępu warunkowego będą mogli zapisywać dane z profilu firmowego w aplikacjach osobistych i niezarządzanym magazynie lokalnym na swoich urządzeniach przenośnych. Będą również mogli połączyć aplikacje osobiste z firmowymi usługami danych, takimi jak Microsoft Exchange.

## <a name="step-6---review--create"></a>Krok 6. Przegląd + tworzenie

W ostatnim kroku możesz zapoznać się podsumowaniem skonfigurowanych ustawień. Po sprawdzeniu swoich wyborów kliknij opcję **Utwórz**, aby ukończyć scenariusz z przewodnikiem. Po zakończeniu scenariusza z przewodnikiem zostanie wyświetlona tabela zasobów. Możesz edytować te zasoby później, ale gdy opuścisz widok podsumowania, tabela nie jest zapisywana.

> [!IMPORTANT]
> Po zakończeniu scenariusza z przewodnikiem zostanie wyświetlone podsumowanie. Możesz zmodyfikować zasoby wymienione w podsumowaniu później, ale tabela z tymi zasobami nie zostanie zapisana.
## <a name="next-steps"></a>Następne kroki

- Zwiększ poziom bezpieczeństwa plików służbowych, przypisując użytkownikom zasady dostępu warunkowego oparte na aplikacjach, aby zapobiec wysyłaniu plików służbowych do niechronionych aplikacji przez usługi w chmurze. Aby uzyskać więcej informacji, zobacz temat [Konfigurowanie zasad dostępu warunkowego opartych na aplikacjach z użyciem usługi Intune](~/protect/app-based-conditional-access-intune-create.md).

