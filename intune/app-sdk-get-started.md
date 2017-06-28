---
title: "Wprowadzenie do zestawu SDK aplikacji usługi Microsoft Intune"
description: "Szybkie włączanie w aplikacji mobilnej obsługi zarządzania aplikacjami mobilnymi (MAM) za pomocą usługi Microsoft Intune."
keywords: 
author: mtillman
manager: angrobe
ms.author: oydang
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38ebd3f5-cfcc-4204-8a75-6e2f162cd7c1
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 1d61432eafef67ca997d4e03d305e1c068ac5fd6
ms.contentlocale: pl-pl
ms.lasthandoff: 06/08/2017


---

# <a name="get-started-with-the-microsoft-intune-app-sdk"></a>Wprowadzenie do zestawu SDK aplikacji usługi Microsoft Intune

Ten przewodnik pomoże szybko włączyć w aplikacji mobilnej obsługę zasad ochrony aplikacji za pomocą usługi Microsoft Intune. Przydatne może okazać się uprzednie zrozumienie korzyści zapewnianych przez zestaw SDK aplikacji usługi Intune, które wyjaśniono w temacie [Omówienie zestawu SDK aplikacji usługi Intune](app-sdk.md).

Zestaw SDK aplikacji usługi Intune obsługuje podobne scenariusze dla systemów iOS i Android oraz pozwala utworzyć spójne środowisko dla administratorów IT na tych platformach. Istnieją jednak niewielkie różnice w obsłudze niektórych funkcji ze względu na ograniczenia platform.

## <a name="register-your-store-app-with-microsoft"></a>Rejestrowanie aplikacji ze sklepu w usłudze Microsoft Intune

### <a name="if-your-app-is-internal-to-your-organization-and-will-not-be-publicly-available"></a>Jeśli Twoja aplikacja jest wewnętrzną aplikacją organizacji i nie będzie dostępna publicznie:

*Nie musisz* rejestrować swojej aplikacji. W przypadku wewnętrznych aplikacji biznesowych administrator IT wdroży aplikację wewnętrznie. Usługa Intune wykryje, że aplikacja została opracowana za pomocą zestawu SDK, i zezwoli administratorowi IT na zastosowanie do niej zasad ochrony aplikacji. Możesz przejść do sekcji [Włączanie obsługi zasad ochrony aplikacji dla aplikacji systemu iOS lub Android](#enable-your-iOS-or-Android-app-for-app-protection-policy).

### <a name="if-your-app-will-be-released-to-a-public-app-store-like-the-apple-app-store-or-google-play"></a>Jeśli Twoja aplikacja będzie rozpowszechniana w publicznym sklepie z aplikacjami, takim jak Apple App Store lub Google Play:

_**Musisz**_ najpierw zarejestrować aplikację w usłudze Microsoft Intune i zaakceptować warunki rejestracji. Administratorzy IT mogą następnie zastosować zasady ochrony aplikacji do obsługiwanej aplikacji, która będzie wyświetlana jako aplikacja partnerska usługi Intune.

Do czasu zakończenia rejestracji i potwierdzenia jej przez zespół usługi Microsoft Intune administratorzy usługi Intune nie będą mieć linku bezpośredniego do opcji zastosowania zasad ochrony aplikacji do Twojej aplikacji. Firma Microsoft doda także aplikację do swojej [strony partnerów usługi Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps). Wyświetlanie ikony aplikacji na tej stronie świadczy o tym, że obsługuje ona zasady ochrony aplikacji usługi Intune.

Aby rozpocząć proces rejestracji, wypełnij [Kwestionariusz partnera aplikacji usługi Microsoft Intune](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR6oOVGFZ3pxJmwSN1N_eXwJUQUc5Mkw2UVU0VzI5WkhQOEYyMENWNDBWRS4u).

Użyjemy adresów e-mail podanych w odpowiedziach kwestionariusza w celu uzyskania kontaktu i kontynuowania procesu rejestracji. Ponadto skorzystamy z Twojego adresu e-mail użytego podczas rejestracji, aby kontaktować się z Tobą w razie jakichkolwiek pytań.

> [!NOTE]
> Wszystkie informacje zebrane w kwestionariuszu i za pomocą poczty e-mail w ramach korespondencji z zespołem usługi Microsoft Intune podlegają [zasadom zachowania poufności informacji firmy Microsoft](https://www.microsoft.com/privacystatement/default.aspx).

**Oczekiwany przebieg procesu rejestracji**:

1. Gdy prześlesz kwestionariusz, skontaktujemy się z Tobą za pomocą adresu e-mail użytego podczas rejestracji w celu potwierdzenia pomyślnego odebrania żądania lub poproszenia o podanie dodatkowych informacji niezbędnych do zakończenia rejestracji.

2. Po zebraniu wszystkich niezbędnych informacji otrzymasz od firmy Microsoft umowę partnera aplikacji usługi Microsoft Intune, którą należy podpisać. Przedstawiono w niej postanowienia, które firma musi zaakceptować, aby stać się partnerem aplikacji usługi Microsoft Intune.

3. Otrzymasz również powiadomienie, gdy aplikacja zostanie pomyślnie zarejestrowana w usłudze Microsoft Intune oraz gdy aplikacja zostanie udostępniona w witrynie [partnerów usługi Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

4. Link bezpośredni do aplikacji zostanie dodany do następnej comiesięcznej aktualizacji usługi Intune. Jeśli na przykład informacje niezbędne do rejestracji zostaną podane w lipcu, link bezpośredni do aplikacji będzie obsługiwany od połowy sierpnia.

Jeśli link bezpośredni do aplikacji zmieni się w przyszłości, będzie konieczne ponowne zarejestrowanie aplikacji.

> [!NOTE]
> Prosimy o poinformowanie nas w przypadku zaktualizowania aplikacji za pomocą nowej wersji zestawu SDK aplikacji usługi Intune.



## <a name="download-the-sdk-files"></a>Pobieranie plików zestawu SDK

Zestawy SDK aplikacji usługi Intune dla natywnych systemów iOS i Android są hostowane na koncie usługi GitHub firmy Microsoft. Następujące repozytoria publiczne zawierają pliki zestawów SDK odpowiednio dla natywnych systemów iOS i Android:

* [Zestaw SDK aplikacji usługi Intune dla systemu iOS](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios)
* [Zestaw SDK aplikacji usługi Intune dla systemu Android](https://github.com/msintuneappsdk/ms-intune-app-sdk-android)

Jeśli Twoja aplikacja jest aplikacją Xamarin lub Cordova, użyj następujących wariantów zestawu SDK:

* [Składnik Xamarin zestawu SDK aplikacji usługi Intune](https://github.com/msintuneappsdk/intune-app-sdk-xamarin)
* [Wtyczka Cordova zestawu SDK aplikacji usługi Intune](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam)

Warto utworzyć konto usługi GitHub, które pozwoli rozwidlać nasze repozytoria i z nich pobierać. Usługa GitHub umożliwia deweloperom komunikowanie się z naszym zespołem produktu, zgłaszanie problemów i uzyskiwanie szybkich odpowiedzi, wyświetlanie informacji o wersjach oraz przesyłanie opinii do firmy Microsoft. Pytania dotyczące strony zestawu SDK aplikacji usługi Intune w usłudze GitHub należy kierować na adres msintuneappsdk@microsoft.com.





## <a name="enable-your-ios-or-android-app-for-app-protection-policy"></a>Włączanie obsługi zasad ochrony aplikacji dla aplikacji systemu iOS lub Android

Aby ułatwić zintegrowanie zestawu SDK aplikacji usługi Intune z aplikacją, będzie potrzebny jeden z następujących przewodników dla deweloperów:

* **[Przewodnik dla deweloperów korzystających z zestawu SDK aplikacji usługi Intune dla systemu iOS](app-sdk-ios.md)**: ten dokument zawiera szczegółowe instrukcje dotyczące włączania aplikacji natywnej systemu iOS przy użyciu zestawu SDK aplikacji usługi Intune.

* **[Przewodnik dla deweloperów korzystających z zestawu SDK aplikacji usługi Intune dla systemu Android](app-sdk-android.md)**: ten dokument zawiera szczegółowe instrukcje dotyczące włączania aplikacji natywnej systemu Android przy użyciu zestawu SDK aplikacji usługi Intune.

* **[Przewodnik dotyczący wtyczki Cordova zestawu SDK aplikacji Intune](app-sdk-cordova.md)**: ten dokument pomoże Ci tworzyć aplikacje dla systemów Android i iOS przy użyciu oprogramowania Cordova i zasad ochrony aplikacji usługi Intune.

* **[Przewodnik dotyczący składnika Xamarin zestawu SDK aplikacji Intune](app-sdk-xamarin.md)**: ten dokument pomoże Ci tworzyć aplikacje dla systemów Android i iOS przy użyciu oprogramowania Cordova i zasad ochrony aplikacji usługi Intune.




## <a name="configure-telemetry-for-your-app"></a>Konfigurowanie telemetrii dla aplikacji

Usługa Microsoft Intune zbiera dane dotyczące statystyk użycia aplikacji.

* **Zestaw SDK aplikacji usługi Intune dla systemu iOS**: zestaw SDK domyślnie rejestruje dane telemetryczne zestawu SDK dotyczące zdarzeń użycia. Te dane są wysyłane do usługi Microsoft Intune.

    * Jeśli zrezygnujesz z wysyłania danych telemetrycznych zestawu SDK do usługi Microsoft Intune z aplikacji, musisz wyłączyć funkcję przesyłania danych telemetrycznych przez ustawienie dla właściwości `MAMTelemetryDisabled` wartości „YES” w słowniku IntuneMAMSettings.


* **Zestaw SDK aplikacji usługi Intune dla systemu Android**: zestaw SDK nie rejestruje danych telemetrycznych.

## <a name="next-steps-after-integration"></a>Następne kroki po integracji

### <a name="test-your-app"></a>Testowanie aplikacji
Po wykonaniu czynności niezbędnych do zintegrowania Twojej aplikacji systemu iOS lub Android z zestawem SDK aplikacji usługi Intune musisz się upewnić, że wszystkie zasady ochrony aplikacji są włączone i działają dla użytkownika oraz administratora IT. Do przetestowania zintegrowanej aplikacji są potrzebne następujące elementy:

* **Testowe konto usługi Microsoft Intune**: aby można było przetestować funkcje ochrony aplikacji usługi Intune w Twojej aplikacji obsługującej usługę Intune, potrzebne jest konto usługi Microsoft Intune.

    * Jeśli jesteś niezależnym dostawcą oprogramowania i włączasz obsługę ochrony aplikacji usługi Intune dla swoich aplikacji systemu iOS lub Android ze sklepu, po dokonaniu rejestracji w usłudze Microsoft Intune w sposób opisany w kroku rejestracji otrzymasz kod promocyjny. Kod ten pozwala zarejestrować się w celu korzystania z wersji próbnej usługi Microsoft Intune przez dodatkowy rok.

    * Jeśli opracowujesz aplikację biznesową, która nie zostanie dostarczona do sklepu, dostęp do usługi Microsoft Intune możesz uzyskiwać za pośrednictwem swojej organizacji. Możesz też zarejestrować się w celu skorzystania z miesięcznej bezpłatnej wersji próbnej usługi [Microsoft Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0).

* **Zasady ochrony aplikacji usługi Intune**: aby przetestować wszystkie zasady ochrony aplikacji usługi Intune w swojej aplikacji, musisz znać oczekiwane zachowanie każdego ustawienia zasad. Zobacz opisy [zasad ochrony aplikacji systemu iOS](/intune-classic/deploy-use/ios-mam-policy-settings) i [zasad ochrony aplikacji systemu Android](/intune-classic/deploy-use/android-mam-policy-settings).

* **Rozwiązywanie problemów**: w razie problemów podczas ręcznego testowania środowiska użytkownika aplikacji zobacz [Rozwiązywanie problemów z zarządzaniem aplikacjami mobilnymi](/intune-classic/troubleshoot/troubleshoot-mam). Ten artykuł zapewnia pomoc dotyczącą typowych problemów, okien dialogowych i komunikatów o błędach, które mogą się pojawić w aplikacjach obsługujących usługę Intune. 

### <a name="badge-your-app-optional"></a>Znakowanie aplikacji (opcjonalne)

Po zweryfikowaniu, czy zasady ochrony aplikacji usługi Intune działają w aplikacji, możesz oznakować ikonę aplikacji za pomocą znaku logo ochrony aplikacji usługi Intune.

Takie oznaczenie wskazuje administratorom IT, użytkownikom końcowym i potencjalnym klientom korzystającym z usługi Intune, że aplikacja współdziała z zasadami ochrony aplikacji usługi Intune. Jest to zachętą do korzystania z aplikacji przez klientów korzystających z usługi Intune.

Oznaczenie jest ikoną aktówki. Przykłady przedstawiono poniżej:

![Przykładowe oznaczenie (1)](./media/badge-example-1.png) ![Przykładowe oznaczenie (2)](./media/badge-example-2.png)

**Co jest potrzebne do oznaczenia aplikacji**:

* Aplikacja do obróbki obrazów, która umożliwia odczytywanie plików **eps**, lub aplikacja firmy Adobe, która umożliwia odczytywanie plików **ai**.

* [Zasoby i wskazówki dotyczące znakowania aplikacji usługi Intune](https://github.com/msintuneappsdk/intune-app-partner-badge) można znaleźć na stronie usługi Microsoft Intune w usłudze GitHub.

