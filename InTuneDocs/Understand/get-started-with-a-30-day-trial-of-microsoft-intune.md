---
title: "Przewodnik dotyczący ewaluacji usługi Intune | Microsoft Intune"
description: "Wprowadzenie i wymagania wstępne dotyczące sposobu konfigurowania bezpłatnej, 30-dniowej wersji ewaluacyjnej usługi Intune"
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 619a1d11-3d22-4635-8f70-770eba3e1712
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 60ee39a7eeeb9068a7350ec87f60e7148ccb7826
ms.openlocfilehash: f64fc7c8758e87aeb4866c21c46e0db7349713c5


---

# Przewodnik dotyczący oceny usługi Intune
Skonfigurowanie bezpłatnej 30-dniowej wersji ewaluacyjnej usługi Intune przeznaczonej do zarządzania Twoimi urządzeniami przenośnymi i komputerami jest szybkie i łatwe. Wykonanie kilku prostych kroków w wersji ewaluacyjnej umożliwia dodanie maksymalnie 100 użytkowników i urządzeń, skonfigurowanie grup, skonfigurowanie zasad zgodności oraz zarejestrowanie urządzeń przenośnych i komputerów, a następnie zarządzanie nimi.

W tym temacie nauczysz się podstaw uruchamiania i konfigurowania usługi Intune w wersji ewaluacyjnej. W ten sposób poznasz ogólnie usługę, dzięki czemu będziesz w stanie ocenić funkcje i możliwości usługi Intune.

Obejrzyj następującą 5-minutową prezentację, aby dowiedzieć się, jak łatwo można rozpocząć pracę z bezpłatną wersją ewaluacyjną usługi Microsoft Intune i zarządzać urządzeniami. W pierwszej części klipu wideo jest wspomniany portal, który został „wycofany”, ale pomimo że będziesz używać innego portalu, kroki będą zasadniczo takie same. Więcej informacji na temat portalu można znaleźć [tutaj](https://docs.microsoft.com/intune/deploy-use/account-portal-merged-with-Office-365).

<iframe width="675" height="480" src="https://www.youtube.com/embed/ltcZvm4VOFU" frameborder="0" allowfullscreen></iframe>

## Przed rozpoczęciem
Przed rozpoczęciem pracy z usługą Intune potrzebujesz:

-   Urządzenia z przeglądarką sieci Web obsługującą program Silverlight, pozwalającą uzyskiwać dostęp do witryn sieci Web, w których zostaną utworzone konta użytkowników usługi Intune (**Centrum administracyjne usługi Office 365**) i które będą służyć do zarządzania urządzeniami, grupami i zasadami (**Konsola administracyjna Intune**).

-   Drugiego urządzenia z przeglądarką sieci Web, którego będziesz używać do testowania, w jaki sposób użytkownicy usługi Intune będą rejestrować swoje urządzenia i zarządzać nimi za pomocą Portalu firmy. Ponadto przetestujesz, w jaki sposób użytkownicy będą znajdować i instalować aplikacje oraz zwracać się o pomoc do Administratorów. Jeśli nie masz drugiego urządzenia z przeglądarką sieci Web, możesz użyć ustawienia „tryb prywatny” w tej samej przeglądarce, za pomocą której administrujesz usługą Intune (na przykład w przeglądarce Internet Explorer możesz kliknąć opcje **Narzędzia** &gt; **Przeglądanie InPrivate**).

-   Jeśli masz już konto usług Microsoft Online Services, potrzebne będą poświadczenia administratora dla tego konta. Jeśli nie masz takiego konta lub chcesz korzystać z tej dzierżawy usługi Intune wyłącznie do celów ewaluacyjnych, nie potrzebujesz poświadczeń administratora.

-   Jeśli przy użyciu usługi Intune w wersji ewaluacyjnej będziesz zarządzać urządzeniami z systemem iOS lub Windows Phone, potrzebujesz certyfikatów (lub kluczy) oraz kont umożliwiających pobranie tych certyfikatów (patrz poniższa tabela). Urządzenia z systemem Android nie wymagają żadnych dodatkowych certyfikatów.

    |Platforma|Wymagania dotyczące certyfikatów|Więcej informacji|
    |------------|----------------------------|--------------------|
    |Windows Phone 8.1 i Windows Phone 8 |Żaden certyfikat nie jest wymagany w przypadku użytkowników systemu Windows Phone 8.1, którzy instalują aplikację Portal firmy pobraną ze Sklepu. Certyfikat Symantec jest wymagany w przypadku systemu Windows Phone 8.0 oraz w przypadku wdrażania aplikacji Portal firmy za pośrednictwem usługi Intune na urządzeniach z systemem Windows Phone 8.1.|We wskazówkach tych założono, że użytkownicy pobierają aplikację Portal firmy ze Sklepu na urządzeniach z systemem Windows Phone 8.1 lub nowszym. Aby uzyskać informacje na temat obsługi systemu Windows Phone 8.0, zobacz [Konfigurowanie zarządzania systemem Windows Phone przy użyciu usługi Microsoft Intune](/Intune/Deploy-Use/set-up-windows-phone-management-with-microsoft-intune).|
    |Urządzenia z systemem Windows 10, Windows RT 8.1, Windows RT lub Windows 8.1|Żaden certyfikat nie jest wymagany w przypadku rejestracji urządzeń z systemem Windows RT i Windows.|[Instalowanie klienta komputera z systemem Windows przy użyciu usługi Microsoft Intune](/Intune/Deploy-Use/install-the-windows-pc-client-with-microsoft-intune).|
    |System iOS 7.1 lub nowszy|Pobierz certyfikat usługi Apple Push Notification.|Należy uzyskać certyfikat usługi Apple Push Notification Service od firmy Apple w sposób opisany w temacie: [Konfigurowanie zarządzania urządzeniami z systemem iOS i komputerami Mac przy użyciu usługi Microsoft Intune](/Intune/Deploy-Use/set-up-ios-and-mac-management-with-microsoft-intune).|

## Kroki w celu zakończenia 30-dniowej ewaluacji usługi Intune
- [Krok 1. Zarejestrowanie się lub zalogowanie na potrzeby uzyskania dostępu do 30-dniowej wersji ewaluacyjnej](get-started-with-a-30-day-trial-of-microsoft-intune-step-1.md). Przed zarejestrowaniem się w usłudze Intune lub zalogowaniem do niej należy rozważyć logowanie przy użyciu istniejącego konta albo utworzenie tymczasowego konta, które będzie używane tylko na potrzeby 30-dniowej ewaluacji usługi Microsoft Intune.
- [Krok 2. Dodawanie użytkowników](get-started-with-a-30-day-trial-of-microsoft-intune-step-2.md). Teraz, po skonfigurowaniu konta, możesz dodawać do usługi Intune indywidualne konta użytkowników lub możesz dodawać użytkowników zbiorczo (patrz instrukcje w tej sekcji). Jest ważne, aby przed rozpoczęciem pracy zrozumieć, w jaki sposób usługa Intune obsługuje konta administratorów.
- [Krok 3. Tworzenie grup w celu zorganizowania użytkowników i urządzeń](get-started-with-a-30-day-trial-of-microsoft-intune-step-3.md). Grupy w usłudze Intune zapewniają dużą elastyczność zarządzania urządzeniami i użytkownikami. Grupy można skonfigurować zgodnie z potrzebami organizacyjnymi (na przykład według lokalizacji geograficznej, działu lub charakterystyki sprzętu) i używać ich do różnych zadań administracyjnych w dowolnej skali, od ustawiania zasad dla zestawu użytkowników po wdrażanie aplikacji w grupach urządzeń.
- [Krok 4. Tworzenie zasad i publikowanie aplikacji](get-started-with-a-30-day-trial-of-microsoft-intune-step-4.md). Zasady usługi Intune udostępniają ustawienia, które ułatwiają sterowanie ustawieniami zabezpieczeń na urządzeniach przenośnych, obsługę ustawień Zapory systemu Windows i programu Endpoint Protection dla komputerów oraz wdrażanie aplikacji.
- [Krok 5. Rejestrowanie urządzeń przenośnych i instalowanie aplikacji](get-started-with-a-30-day-trial-of-microsoft-intune-step-5.md). Aby skonfigurować zarządzanie urządzeniami przenośnymi za pomocą usługi Intune, musisz najpierw ustawić urząd zarządzania urządzeniami przenośnymi, włączyć zarządzanie dla konkretnych platform sprzętowych i zarejestrować swoje urządzenia za pomocą aplikacji Portal firmy. Następnie możesz wdrożyć opublikowaną przez siebie aplikację Microsoft Skype.
- [Krok 6. Inne opcje i dodatki](get-started-with-a-30-day-trial-of-microsoft-intune-step-6.md). Wybierz sposób używania alertów, raportów i innych możliwości usługi Intune w celu spełnienia konkretnych potrzeb biznesowych.
- [Krok 7. Następne kroki](get-started-with-a-30-day-trial-of-microsoft-intune-step-7.md). Przygotuj się do przejścia do płatnej subskrypcji usługi Intune i skorzystaj z asysty centrum rozwiązania FastTrack dla usługi Intune


### Następne kroki
Nadszedł czas, aby zacząć korzystać z subskrypcji 30-dniowej wersji ewaluacyjnej!

>[!div class="step-by-step"]
[**Rejestracja w usłudze Intune** &rarr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-1.md)

### Zobacz także
[Przewodnik Szybki start dotyczący usługi Intune](/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune)



<!--HONumber=Jul16_HO4-->


