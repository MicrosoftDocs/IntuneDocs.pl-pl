---
title: "Wprowadzenie do zestawu SDK aplikacji usługi Microsoft Intune | Microsoft Intune"
description: 
keywords: 
author: Msmbaldwin
manager: jeffgilb
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38ebd3f5-cfcc-4204-8a75-6e2f162cd7c1
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ba9ba203c9ec173dafd1d6f9e4828d4a8a51e1ef
ms.openlocfilehash: 136dd127c5e0f1784746b973ebc5594573f07925


---

# Wprowadzenie do zestawu SDK aplikacji usługi Microsoft Intune

Ten przewodnik wprowadzający ułatwia szybkie włączenie w aplikacji mobilnej obsługi zarządzania aplikacjami mobilnymi za pomocą usługi Microsoft Intune. Przydatne może okazać się uprzednie zrozumienie korzyści zapewnianych przez zestaw SDK aplikacji usługi Intune, które wymieniono w temacie [Omówienie zestawu SDK aplikacji usługi Intune](intune-app-sdk.md).

Ten przewodnik przeprowadzi Cię przez najważniejsze czynności wymagane do włączenia zarządzania aplikacjami mobilnymi w Twojej aplikacji za pomocą usługi Microsoft Intune. Zestaw SDK aplikacji usługi Intune obsługuje podobne scenariusze dla różnych platform i pozwala utworzyć spójne środowisko dla administratorów IT na różnych platformach. Istnieją jednak niewielkie różnice w obsłudze niektórych funkcji ze względu na ograniczenia platform.

# Wprowadzenie

## Rejestrowanie aplikacji ze sklepu w usłudze Microsoft Intune

**Jeśli Twoja aplikacja jest wewnętrzną aplikacją firmową i nie zostanie udostępniona w publicznym sklepie z aplikacjami**:

**Nie musisz** rejestrować swojej aplikacji. W przypadku wewnętrznych aplikacji biznesowych administrator IT wdroży aplikację wewnętrznie za pomocą usługi Microsoft Intune. Usługa Intune wykryje, że aplikacja została opracowana za pomocą zestawu SDK i zezwoli administratorowi IT na zastosowanie do niej ustawień zasad zarządzania aplikacjami mobilnymi. Możesz przejść do sekcji [Włączanie obsługi zarządzania aplikacjami mobilnymi dla aplikacji mobilnej systemu iOS lub Android przy użyciu zestawu SDK](#enable-your-ios-or-android-mobile-app-for-mam-with-the-sdk).

**Jeśli Twoja aplikacja zostanie wydana w publicznym sklepie z aplikacjami, takim jak Apple App Store lub Google Play**: 

**Musisz** najpierw zarejestrować aplikację w usłudze Microsoft Intune i zaakceptować warunki rejestracji. Po zarejestrowaniu administratorzy IT mogą stosować ustawienia zasad zarządzania aplikacjami mobilnymi usługi Intune do obsługiwanej aplikacji, która będzie wyświetlana jako aplikacja partnerska usługi Intune. Do czasu ukończenia rejestracji i potwierdzenia jej przez zespół usługi Microsoft Intune administratorzy usługi Intune nie będą mieć linku bezpośredniego do opcji zastosowania zasad zarządzania aplikacjami mobilnymi do Twojej aplikacji. Ponadto firma Microsoft doda Twoją aplikację do [strony partnerów usługi Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners), na której będzie wyświetlana ikona aplikacji informująca o tym, że aplikacja obsługuje zasady zarządzania aplikacjami mobilnymi usługi Microsoft Intune.

Aby rozpocząć proces rejestracji, **przejrzyj i podpisz** [umowę partnera usługi Microsoft Intune](https://connect.microsoft.com/ConfigurationManagervnext/Survey/Survey.aspx?SurveyID=17806). Przedstawiono w niej postanowienia, które firma musi zaakceptować, aby stać się partnerem aplikacji usługi Microsoft Intune. Aby móc wyświetlić ten dokument, musisz się zalogować. Umowa jest dostępna w witrynie Microsoft Connect zestawu SDK aplikacji usługi Intune na karcie Ankiety lub tutaj. Zostanie również wyświetlony monit o podanie nazwy aplikacji, nazwy firmy i linku bezpośredniego do aplikacji w sklepie iTunes lub Google.

![Microsoft Connect](../media/microsoft-connect.png)

Adres e-mail użyty podczas rejestracji umożliwi nam potwierdzenie i ukończenie procesu rejestracji. Ponadto będziemy go używać, aby kontaktować się z Tobą w razie jakichkolwiek pytań.

**Oczekiwany przebieg procesu rejestracji**: 

gdy prześlesz formularz, firma Microsoft skontaktuje się z Tobą za pomocą adresu e-mail użytego podczas rejestracji w celu potwierdzenia pomyślnego odebrania żądania lub poproszenia o podanie dodatkowych informacji niezbędnych do ukończenia rejestracji. Otrzymasz również wiadomość, gdy aplikacja zostanie pomyślnie zarejestrowana w usłudze Microsoft Intune oraz gdy aplikacja zostanie udostępniona w witrynie partnerów usługi Microsoft Intune. Po potwierdzeniu otrzymania informacji link bezpośredni do aplikacji zostanie dołączony do następnej miesięcznej aktualizacji usługi Intune. Jeśli na przykład informacje niezbędne do rejestracji zostaną podane w lipcu, link bezpośredni do aplikacji będzie obsługiwany od połowy sierpnia. Jeśli link bezpośredni do sklepu z aplikacjami zmieni się w przyszłości, będzie konieczne ponowne zarejestrowanie aplikacji. Ponadto musisz nas poinformować o aktualizacji aplikacji za pomocą nowej wersji zestawu SDK aplikacji usługi Intune.

**Uwaga**: wszystkie informacje zebrane w powyższym formularzu i pocztą e-mail w ramach korespondencji z zespołem usługi Intune podlegają [zasadom zachowania poufności informacji firmy Microsoft](https://www.microsoft.com/en-us/privacystatement/default.aspx).

## Pobieranie plików zestawu SDK

Zestawy SDK aplikacji usługi Intune dla systemów iOS i Android są hostowane na koncie usługi GitHub firmy Microsoft. Poniższe repozytoria publiczne zawierają pliki zestawów SDK odpowiednio dla systemów iOS i Android:

* [Zestaw SDK aplikacji usługi Intune dla systemu iOS](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios)
* [Zestaw SDK aplikacji usługi Intune dla systemu Android](https://github.com/msintuneappsdk/ms-intune-app-sdk-android)

Zalecamy utworzenie konta usługi GitHub, które pozwoli rozwidlać nasze repozytoria i z nich pobierać. Usługa GitHub umożliwia deweloperom komunikowanie się z naszym zespołem produktu, zgłaszanie problemów i uzyskiwanie szybkich odpowiedzi, wyświetlanie informacji o wersjach oraz przesyłanie opinii do firmy Microsoft. W razie pytań dotyczących konta usługi GitHub i repozytoriów, skontaktuj się z nami za pomocą adresu e-mail msintuneappsdk@microsoft.com.

## Włączanie obsługi zarządzania aplikacjami mobilnymi dla aplikacji mobilnej systemu iOS lub Android przy użyciu zestawu SDK

Do integracji zestawu SDK aplikacji usługi Intune z Twoją aplikacją systemu iOS wymagany będzie następujący dokument: 

* **[Przewodnik dla deweloperów korzystających z zestawu SDK aplikacji usługi Intune dla systemu iOS](intune-app-sdk-ios.md)**: ten dokument zawiera szczegółowe instrukcje dotyczące włączania aplikacji mobilnej systemu iOS przy użyciu zestawu SDK aplikacji usługi Intune. 


Do integracji zestawu SDK aplikacji usługi Intune z Twoją aplikacją systemu Android wymagany będzie następujący dokument:

* **[Przewodnik dla deweloperów korzystających z zestawu SDK aplikacji usługi Intune dla systemu Android](intune-app-sdk-android.md)**: ten dokument zawiera szczegółowe instrukcje dotyczące włączania aplikacji mobilnej systemu Android przy użyciu zestawu SDK aplikacji usługi Intune. 



## Konfigurowanie telemetrii dla aplikacji

Usługa Microsoft Intune zbiera dane dotyczące statystyk użycia aplikacji.

* **Zestaw SDK aplikacji usługi Intune dla systemu iOS**: zestaw SDK domyślnie rejestruje dane telemetryczne zestawu SDK dotyczące zdarzeń użycia. Te dane są wysyłane do usługi Microsoft Intune.

    * Jeśli zrezygnujesz z wysyłania danych telemetrycznych zestawu SDK do usługi Microsoft Intune z aplikacji, musisz wyłączyć funkcję przesyłania danych telemetrycznych przez ustawienie dla właściwości `MAMTelemetryDisabled` wartości „YES” w słowniku IntuneMAMSettings.

* **Zestaw SDK aplikacji usługi Intune dla systemu Android**: zestaw SDK nie rejestruje danych telemetrycznych.

## Testowanie aplikacji z obsługą zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune

Po wykonaniu czynności niezbędnych do zintegrowania Twojej aplikacji systemu iOS lub Android z zestawem SDK aplikacji usługi Intune musisz upewnić się, że wszystkie zasady zarządzania aplikacjami są włączone i działają dla użytkownika końcowego oraz administratora IT. Do przetestowania zintegrowanej aplikacji są potrzebne następujące elementy:

<!--TODO-->

* **Testowanie aplikacji z obsługą zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune**: ten dokument zawiera szczegółowe instrukcje dotyczące testowania aplikacji systemu iOS lub Android z obsługą zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune. Ten dokument możesz znaleźć w repozytoriach usługi GitHub zestawów SDK.

* **Konto usługi Microsoft Intune**: do testowania aplikacji z obsługą zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune jest potrzebne konto usługi Microsoft Intune. 
    * Jeśli jesteś niezależnym dostawcą oprogramowania i włączasz obsługę zarządzania aplikacjami mobilnymi usługi Intune dla Twoich aplikacji systemu iOS lub Android ze sklepu, otrzymasz kod promocyjny po ukończeniu rejestracji w usłudze Microsoft Intune w sposób opisany w kroku rejestracji. Ten kod promocyjny pozwala zarejestrować się w celu korzystania z wersji próbnej usługi Microsoft Intune przez dodatkowy rok. 
    * Jeśli opracowujesz aplikację biznesową, która nie zostanie dostarczona do sklepu, dostęp do usługi Microsoft Intune możesz uzyskiwać za pośrednictwem swojej organizacji. Możesz też zarejestrować się w celu korzystania z miesięcznej bezpłatnej wersji próbnej usługi [Microsoft Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0).




<!--HONumber=Sep16_HO4-->


