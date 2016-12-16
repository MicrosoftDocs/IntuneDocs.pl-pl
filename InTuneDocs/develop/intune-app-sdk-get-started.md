---
title: "Wprowadzenie do zestawu SDK aplikacji usługi Microsoft Intune | Dokumentacja firmy Microsoft"
description: 
keywords: 
author: mtillman
manager: angrobe
ms.author: oydang
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38ebd3f5-cfcc-4204-8a75-6e2f162cd7c1
ms.reviewer: oydang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6adfb7375f9747f64e7037164f48918789bd7ee0
ms.openlocfilehash: 7372cdd1c1001d621ba8374284e814951f55ef93


---

# <a name="get-started-with-the-microsoft-intune-app-sdk"></a>Wprowadzenie do zestawu SDK aplikacji usługi Microsoft Intune

Ten przewodnik ułatwia szybkie włączenie w aplikacji mobilnej obsługi zarządzania aplikacjami mobilnymi (MAM, mobile application management) za pomocą usługi Microsoft Intune. Przydatne może okazać się uprzednie zrozumienie korzyści zapewnianych przez zestaw SDK aplikacji usługi Intune, które wyjaśniono w temacie [Omówienie zestawu SDK aplikacji usługi Intune](intune-app-sdk.md).

Ten przewodnik przeprowadzi Cię przez najważniejsze czynności wymagane do włączenia zarządzania aplikacjami mobilnymi w Twojej aplikacji za pomocą usługi Microsoft Intune. Zestaw SDK aplikacji usługi Intune obsługuje podobne scenariusze dla różnych platform i pozwala utworzyć spójne środowisko dla administratorów IT na różnych platformach. Istnieją jednak niewielkie różnice w obsłudze niektórych funkcji ze względu na ograniczenia platform.

## <a name="register-your-store-app-with-microsoft"></a>Rejestrowanie aplikacji ze sklepu w usłudze Microsoft Intune

**Jeśli Twoja aplikacja jest wewnętrzną aplikacją firmową i nie zostanie udostępniona w publicznym sklepie z aplikacjami**:

*Nie musisz* rejestrować swojej aplikacji. W przypadku wewnętrznych aplikacji biznesowych administrator IT wdroży aplikację wewnętrznie. Usługa Intune wykryje, że aplikacja została opracowana za pomocą zestawu SDK, i zezwoli administratorowi IT na zastosowanie do niej ustawień zasad zarządzania aplikacjami mobilnymi. Możesz przejść do sekcji [Włączanie obsługi zarządzania aplikacjami mobilnymi dla aplikacji mobilnej systemu iOS lub Android przy użyciu zestawu SDK](#enable-your-ios-or-android-mobile-app-for-mam-with-the-sdk).

**Jeśli Twoja aplikacja będzie rozpowszechniana w publicznym sklepie z aplikacjami, jak Apple App Store lub Google Play**:

*Musisz* najpierw zarejestrować aplikację w usłudze Microsoft Intune i zaakceptować warunki rejestracji. Administratorzy IT mogą następnie zastosować ustawienia zasad zarządzania aplikacjami mobilnymi usługi Intune do obsługiwanej aplikacji, która będzie wyświetlana jako aplikacja partnerska usługi Intune. Do czasu zakończenia rejestracji i potwierdzenia jej przez zespół usługi Microsoft Intune administratorzy usługi Intune nie będą mogli zastosować zasad zarządzania aplikacjami mobilnymi do Twojej aplikacji. Firma Microsoft doda także aplikację do swojej [strony partnerów usługi Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps). Wyświetlanie ikony aplikacji na tej stronie świadczy o tym, że obsługuje ona zasady zarządzania aplikacjami mobilnymi usługi Microsoft Intune.

Aby rozpocząć proces rejestracji, wypełnij [Kwestionariusz partnera aplikacji usługi Microsoft Intune](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR6oOVGFZ3pxJmwSN1N_eXwJUQUc5Mkw2UVU0VzI5WkhQOEYyMENWNDBWRS4u).

Użyjemy adresów e-mail podanych w odpowiedziach kwestionariusza w celu uzyskania kontaktu i kontynuowania procesu rejestracji. Ponadto skorzystamy z Twojego adresu e-mail użytego podczas rejestracji, aby kontaktować się z Tobą w razie jakichkolwiek pytań.

> [!NOTE]
> Wszystkie informacje zebrane w kwestionariuszu i za pomocą poczty e-mail w ramach korespondencji z zespołem usługi Microsoft Intune podlegają [zasadom zachowania poufności informacji firmy Microsoft](https://www.microsoft.com/en-us/privacystatement/default.aspx).

**Oczekiwany przebieg procesu rejestracji**:

1. Gdy prześlesz kwestionariusz, skontaktujemy się z Tobą za pomocą adresu e-mail użytego podczas rejestracji w celu potwierdzenia pomyślnego odebrania żądania lub poproszenia o podanie dodatkowych informacji niezbędnych do zakończenia rejestracji.
2. Po zebraniu wszystkich niezbędnych informacji otrzymasz od firmy Microsoft umowę partnera aplikacji usługi Microsoft Intune, którą należy podpisać. Przedstawiono w niej postanowienia, które firma musi zaakceptować, aby stać się partnerem aplikacji usługi Microsoft Intune.
3. Otrzymasz również powiadomienie, gdy aplikacja zostanie pomyślnie zarejestrowana w usłudze Microsoft Intune oraz gdy aplikacja zostanie udostępniona w witrynie [partnerów usługi Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps).
4. Link bezpośredni do aplikacji zostanie dodany do następnej comiesięcznej aktualizacji usługi Intune. Jeśli na przykład informacje niezbędne do rejestracji zostaną podane w lipcu, link bezpośredni do aplikacji będzie obsługiwany od połowy sierpnia.

Jeśli link bezpośredni do aplikacji zmieni się w przyszłości, będzie konieczne ponowne zarejestrowanie aplikacji. Ponadto poinformuj nas o aktualizacji aplikacji za pomocą nowej wersji zestawu SDK aplikacji usługi Intune.



## <a name="download-the-sdk-files"></a>Pobieranie plików zestawu SDK

Zestawy SDK aplikacji usługi Intune dla natywnych systemów iOS i Android są hostowane na koncie usługi GitHub firmy Microsoft. Następujące repozytoria publiczne zawierają pliki zestawów SDK odpowiednio dla systemów iOS i Android:

* [Zestaw SDK aplikacji usługi Intune dla systemu iOS](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios)
* [Zestaw SDK aplikacji usługi Intune dla systemu Android](https://github.com/msintuneappsdk/ms-intune-app-sdk-android)

Jeśli Twoja aplikacja jest aplikacją Xamarin lub Cordova, użyj następujących narzędzi deweloperskich:

* [Składnik Xamarin zestawu SDK aplikacji usługi Intune](https://github.com/msintuneappsdk/intune-app-sdk-xamarin)
* [Wtyczka Cordova zestawu SDK aplikacji usługi Intune](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam)

Warto utworzyć konto usługi GitHub, które pozwoli rozwidlać nasze repozytoria i z nich pobierać. Usługa GitHub umożliwia deweloperom komunikowanie się z naszym zespołem produktu, zgłaszanie problemów i uzyskiwanie szybkich odpowiedzi, wyświetlanie informacji o wersjach oraz przesyłanie opinii do firmy Microsoft. W razie pytań dotyczących konta usługi GitHub i repozytoriów, skontaktuj się z nami za pomocą adresu e-mail msintuneappsdk@microsoft.com.





## <a name="enable-your-ios-or-android-mobile-app-for-mam-with-the-sdk"></a>Włączanie obsługi zarządzania aplikacjami mobilnymi dla aplikacji mobilnej systemu iOS lub Android przy użyciu zestawu SDK

Do integracji zestawu SDK aplikacji usługi Intune z Twoją natywną aplikacją systemu iOS wymagany będzie następujący dokument:

* **[Przewodnik dla deweloperów korzystających z zestawu SDK aplikacji usługi Intune dla systemu iOS](intune-app-sdk-ios.md)**: ten dokument zawiera szczegółowe instrukcje dotyczące włączania aplikacji mobilnej systemu iOS przy użyciu zestawu SDK aplikacji usługi Intune.


Do integracji zestawu SDK aplikacji usługi Intune z Twoją natywną aplikacją systemu Android wymagany będzie następujący dokument:

* **[Przewodnik dla deweloperów korzystających z zestawu SDK aplikacji usługi Intune dla systemu Android](intune-app-sdk-android.md)**: ten dokument zawiera szczegółowe instrukcje dotyczące włączania aplikacji mobilnej systemu Android przy użyciu zestawu SDK aplikacji usługi Intune.

Aby kompilować aplikacje Cordova przy użyciu wtyczki Cordova zestawu SDK aplikacji usługi Intune, skorzystaj z następujących informacji:

* **[Przewodnik dotyczący wtyczki Cordova zestawu SDK aplikacji Intune](intune-app-sdk-cordova.md)**: ten dokument pomoże Ci tworzyć aplikacje dla systemów Android i OS przy użyciu oprogramowania Cordova dla funkcji zarządzania aplikacjami mobilnymi usługi Intune.

Aby kompilować aplikacje Xamarin przy użyciu składnika Xamarin zestawu SDK aplikacji usługi Intune, skorzystaj z następujących informacji:

* **[Przewodnik dotyczący składnika Xamarin zestawu SDK aplikacji Intune](intune-app-sdk-xamarin.md)**: ten dokument pomoże Ci tworzyć aplikacje dla systemów Android i OS przy użyciu składnika Xamarin dla funkcji zarządzania aplikacjami mobilnymi usługi Intune.




## <a name="configure-telemetry-for-your-app"></a>Konfigurowanie telemetrii dla aplikacji

Usługa Microsoft Intune zbiera dane dotyczące statystyk użycia aplikacji.

* **Zestaw SDK aplikacji usługi Intune dla systemu iOS**: zestaw SDK domyślnie rejestruje dane telemetryczne zestawu SDK dotyczące zdarzeń użycia. Te dane są wysyłane do usługi Microsoft Intune.

    * Jeśli zrezygnujesz z wysyłania danych telemetrycznych zestawu SDK do usługi Microsoft Intune z aplikacji, musisz wyłączyć funkcję przesyłania danych telemetrycznych przez ustawienie dla właściwości `MAMTelemetryDisabled` wartości „YES” w słowniku IntuneMAMSettings.

* **Zestaw SDK aplikacji usługi Intune dla systemu Android**: zestaw SDK nie rejestruje danych telemetrycznych.

## <a name="test-your-mam-enabled-app-with-microsoft-intune"></a>Testowanie aplikacji z obsługą zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune

Po wykonaniu czynności niezbędnych do zintegrowania Twojej aplikacji systemu iOS lub Android z zestawem SDK aplikacji usługi Intune musisz się upewnić, że wszystkie zasady zarządzania aplikacjami są włączone i działają dla użytkownika końcowego oraz administratora IT. Do przetestowania zintegrowanej aplikacji są potrzebne następujące elementy:

<!--TODO-->

* **Testowanie aplikacji z obsługą zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune**: ten dokument zawiera szczegółowe instrukcje dotyczące testowania aplikacji systemu iOS lub Android z obsługą zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune. Ten dokument możesz znaleźć w repozytoriach usługi GitHub zestawów SDK.

* **Konto usługi Microsoft Intune**: do testowania aplikacji z obsługą zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune potrzebne jest konto usługi Microsoft Intune.
    * Jeśli jesteś niezależnym dostawcą oprogramowania i włączasz obsługę zarządzania aplikacjami mobilnymi usługi Intune dla swoich aplikacji systemu iOS lub Android ze sklepu, po dokonaniu rejestracji w usłudze Microsoft Intune w sposób opisany w kroku rejestracji otrzymasz kod promocyjny. Kod ten pozwala zarejestrować się w celu korzystania z wersji próbnej usługi Microsoft Intune przez dodatkowy rok.
    * Jeśli opracowujesz aplikację biznesową, która nie zostanie dostarczona do sklepu, dostęp do usługi Microsoft Intune możesz uzyskiwać za pośrednictwem swojej organizacji. Możesz też zarejestrować się w celu skorzystania z miesięcznej bezpłatnej wersji próbnej usługi [Microsoft Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0).



<!--HONumber=Dec16_HO2-->


