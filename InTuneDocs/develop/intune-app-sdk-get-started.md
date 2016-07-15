---
title: "Wprowadzenie do zestawu SDK aplikacji usługi Microsoft Intune | Microsoft Intune"
description: 
keywords: 
author: Msmbaldwin
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38ebd3f5-cfcc-4204-8a75-6e2f162cd7c1
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b7f62c5ee18d8f69fa174f09a1c46b6925c7517c
ms.openlocfilehash: a042f0c6206e9aaf4ec0eb012a70930aa95ecc47


---

# Wprowadzenie do zestawu SDK aplikacji usługi Microsoft Intune

Ten przewodnik wprowadzający ułatwia szybkie włączenie w aplikacji mobilnej obsługi zarządzania aplikacjami mobilnymi za pomocą usługi Microsoft Intune. Przydatne może okazać się uprzednie zrozumienie korzyści zapewnianych przez zestaw SDK aplikacji usługi Intune, które wymieniono w temacie [Omówienie zestawu SDK aplikacji usługi Intune](intune-app-sdk.md).

Ten przewodnik przeprowadzi Cię przez najważniejsze czynności wymagane do włączenia zarządzania aplikacjami mobilnymi w Twojej aplikacji za pomocą usługi Microsoft Intune. Zestaw SDK aplikacji usługi Intune obsługuje podobne scenariusze dla różnych platform i pozwala utworzyć spójne środowisko dla administratorów IT na różnych platformach. Istnieją jednak niewielkie różnice w obsłudze niektórych funkcji ze względu na ograniczenia platform.

# Wprowadzenie

## Rejestracja w witrynie Microsoft Connect

Zestaw SDK aplikacji usługi Intune jest obecnie dostępny za pośrednictwem witryny Microsoft Connect i wymaga utworzenia konta. Aby to zrobić, zarejestruj się w celu utworzenia [konta Microsoft](https://connect.microsoft.com/ConfigurationManagervnext/InvitationUse.aspx?ProgramID=8967&InvitationID=8967-YJYJ-8G6X) za pomocą firmowego adresu e-mail.

Rejestracja będzie w stanie oczekiwania do czasu sprawdzenia żądania przez zespół usługi Intune. Typowy czas odpowiedzi to od 2 do 3 dni roboczych. Gdy żądanie zostanie zatwierdzone, otrzymasz wiadomość e-mail z linkami umożliwiającymi pobranie zestawu SDK aplikacji usługi Intune dla odpowiednich platform i wszystkich powiązanych przewodników. Te przewodniki są też dostępne w witrynie MSDN.

## Rejestrowanie aplikacji ze sklepu w usłudze Microsoft Intune

**Jeśli włączona aplikacja jest wewnętrzną aplikacją firmową i nie będzie dostępna w sklepie z aplikacjami firmy Apple lub Google**: nie musisz rejestrować aplikacji. Administrator IT ładuje takie aplikacje wewnętrzne bezpośrednio w konsoli usługi Microsoft Intune na potrzeby wdrożenia, usługa Intune wykrywa, że aplikacja została utworzona za pomocą zestawu SDK, i umożliwia administratorowi IT zastosowanie do niej zasad zarządzania aplikacjami mobilnymi. Możesz przejść do sekcji [Włączanie obsługi zarządzania aplikacjami mobilnymi dla aplikacji mobilnej systemu iOS lub Android przy użyciu zestawu SDK](#enable-your-ios-or-android-mobile-app-for-mam-with-the-sdk).

**Jeśli jesteś niezależnym dostawcą oprogramowania i opracowujesz aplikację, która będzie dostępna dla klientów w sklepie z aplikacjami firmy Apple lub Google**: najpierw musisz zarejestrować aplikację w usłudze Microsoft Intune i zaakceptować warunki rejestracji. Możesz wtedy udostępnić link bezpośredni do aplikacji. Następnie administrator IT może zastosować do aplikacji zasady zarządzania aplikacjami mobilnymi usługi Intune. Do czasu ukończenia rejestracji i potwierdzenia jej przez zespół usługi Microsoft Intune link bezpośredni do aplikacji nie będzie umożliwiać zastosowania zasad zarządzania aplikacjami mobilnymi w konsoli administracyjnej. Firma Microsoft udostępnia również witrynę partnerów usługi Microsoft Intune, w której jest zarejestrowana aplikacja, dzięki czemu klienci wiedzą, że aplikacja obsługuje zasady zarządzania aplikacjami mobilnymi usługi Microsoft Intune.

Aby rozpocząć proces rejestracji, **przejrzyj i podpisz** [umowę partnera usługi Microsoft Intune](https://connect.microsoft.com/ConfigurationManagervnext/Survey/Survey.aspx?SurveyID=17806). Przedstawiono w niej postanowienia, które firma musi zaakceptować, aby stać się partnerem aplikacji usługi Microsoft Intune. Aby móc wyświetlić ten dokument, musisz się zalogować. Umowa jest dostępna w witrynie Microsoft Connect zestawu SDK aplikacji usługi Intune na karcie Ankiety lub tutaj. Zostanie również wyświetlony monit o podanie nazwy aplikacji, nazwy firmy i linku bezpośredniego do aplikacji w sklepie iTunes lub Google.

![Microsoft Connect](../media/microsoft-connect.png)

Adres e-mail użyty podczas rejestracji umożliwi nam potwierdzenie i ukończenie procesu rejestracji. Ponadto będziemy go używać, aby kontaktować się z Tobą w razie jakichkolwiek pytań.

**Oczekiwany przebieg procesu rejestracji**: gdy prześlesz formularz, firma Microsoft skontaktuje się z Tobą za pomocą adresu e-mail użytego podczas rejestracji w celu potwierdzenia pomyślnego odebrania żądania lub poproszenia o podanie dodatkowych informacji niezbędnych do ukończenia rejestracji. Otrzymasz również wiadomość, gdy aplikacja zostanie pomyślnie zarejestrowana w usłudze Microsoft Intune oraz gdy aplikacja zostanie udostępniona w witrynie partnerów usługi Microsoft Intune. Po potwierdzeniu otrzymania informacji link bezpośredni do aplikacji zostanie dołączony do następnej miesięcznej aktualizacji usługi Intune. Jeśli na przykład informacje niezbędne do rejestracji zostaną podane w lipcu, link bezpośredni do aplikacji będzie obsługiwany od połowy sierpnia. Jeśli link bezpośredni do sklepu z aplikacjami zmieni się w przyszłości, będzie konieczne ponowne zarejestrowanie aplikacji. Ponadto musisz nas poinformować o aktualizacji aplikacji za pomocą nowej wersji zestawu SDK aplikacji usługi Intune.

**Uwaga**: wszystkie informacje zebrane w powyższym formularzu i pocztą e-mail w ramach korespondencji z zespołem usługi Intune podlegają [zasadom zachowania poufności informacji firmy Microsoft](https://www.microsoft.com/en-us/privacystatement/default.aspx).

## Włączanie obsługi zarządzania aplikacjami mobilnymi dla aplikacji mobilnej systemu iOS lub Android przy użyciu zestawu SDK

Do włączenia aplikacji mobilnej systemu iOS są potrzebne następujące elementy:

1. **[Przewodnik dla deweloperów korzystających z zestawu SDK aplikacji usługi Intune dla systemu iOS](intune-app-sdk-ios.md)**: ten dokument zawiera szczegółowe instrukcje dotyczące włączania aplikacji mobilnej systemu iOS przy użyciu zestawu SDK aplikacji usługi Intune. Jest on dostępny w folderze dokumentacji pobranym jako część pakietu zestawu SDK aplikacji usługi Intune.
2. **Zestaw SDK aplikacji usługi Intune dla systemu iOS**: pakiet SDK aplikacji usługi Intune pobrany z usługi Microsoft Intune zawiera podpisany folder „Intune App SDK for iOS”. Znajduje się w nim cała zawartość zestawu SDK aplikacji usługi Intune dla systemu iOS.

Do włączenia aplikacji mobilnej systemu Android przy użyciu zestawu SDK aplikacji usługi Intune są potrzebne następujące elementy:

1. **[Przewodnik dla deweloperów korzystających z zestawu SDK aplikacji usługi Intune dla systemu Android](intune-app-sdk-android.md)**: ten dokument zawiera szczegółowe instrukcje dotyczące włączania aplikacji mobilnej systemu Android przy użyciu zestawu SDK aplikacji usługi Intune. Jest on dostępny w folderze dokumentacji pobranym jako część pakietu zestawu SDK aplikacji usługi Intune.
2. **Zestaw SDK aplikacji usługi Intune dla systemu Android**: pakiet SDK aplikacji usługi Intune pobrany z usługi Microsoft Intune zawiera podpisany folder „Intune App SDK for Android”. Znajduje się w nim cała zawartość zestawu SDK aplikacji usługi Intune dla systemu Android.

## Wyłączanie telemetrii aplikacji

**Zestaw SDK aplikacji usługi Intune dla systemu iOS**: zestaw SDK domyślnie rejestruje dane telemetryczne zestawu SDK dotyczące zdarzeń użycia. Te dane są wysyłane do usługi Microsoft Intune.

Jeśli zrezygnujesz z wysyłania danych telemetrycznych zestawu SDK do usługi Microsoft Intune z aplikacji, **musisz wyłączyć** funkcję przesyłania danych telemetrycznych zestawu SDK przez ustawienie dla właściwości `MAMTelemetryDisabled` wartości „YES” w lokalizacji `IntuneMAMSettings`.

**Zestaw SDK aplikacji usługi Intune dla systemu Android**: zestaw SDK nie rejestruje danych telemetrycznych zestawu SDK.

## Testowanie aplikacji z obsługą zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune

Po wykonaniu czynności niezbędnych do usprawnienia (zintegrowania zestawu SDK aplikacji usługi Intune) zestawu SDK aplikacji usługi Intune dla systemu iOS lub Android musisz upewnić się, że wszystkie zasady zarządzania aplikacjami są włączone i działają dla użytkownika końcowego oraz administratora IT. Do przetestowania usprawnionej aplikacji są potrzebne następujące elementy:

1. **Testowanie aplikacji z obsługą zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune**: ten dokument zawiera szczegółowe instrukcje dotyczące testowania aplikacji systemu iOS lub Android z obsługą zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune. Jest on dostępny w folderze dokumentacji pobranym jako część pakietu zestawu SDK aplikacji usługi Intune.
2. **Konto usługi Microsoft Intune**: do testowania aplikacji z obsługą zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune jest potrzebne konto usługi Microsoft Intune. Jeśli jesteś niezależnym dostawcą oprogramowania i włączasz obsługę zarządzania aplikacjami mobilnymi dla aplikacji systemu iOS lub Android ze sklepu, otrzymasz kod promocyjny po ukończeniu rejestracji w usłudze Microsoft Intune w sposób opisany w kroku rejestracji. Ten kod promocyjny pozwala zarejestrować się w celu korzystania z wersji próbnej usługi Microsoft Intune przez dodatkowy rok. Jeśli opracowujesz aplikację biznesową, która nie zostanie dostarczona do sklepu, dostęp do usługi Microsoft Intune możesz uzyskiwać za pośrednictwem swojej organizacji. Możesz też zarejestrować się w celu korzystania z miesięcznej bezpłatnej wersji próbnej usługi [Microsoft Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0).




<!--HONumber=Jun16_HO4-->


