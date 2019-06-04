---
title: dołączanie pliku
description: dołączanie pliku
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: 1073a38da8a5b2467b1ff8c97b32b93f92e34e4c
ms.sourcegitcommit: f90cba0b2c2672ea733052269bcc372a80772945
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/31/2019
ms.locfileid: "66454129"
---
Te powiadomienia zawierają ważne informacje, które mogą ułatwić przygotowanie się na nadchodzące zmiany i nowe funkcje w usłudze Intune. 

### <a name="update-your-android-company-portal-app-to-the-latest-version---4536963--"></a>Aktualizacja aplikacji Portal firmy dla systemu Android do najnowszej wersji <!--4536963-->
W ramach usługi Intune okresowo wydawane są aktualizacje aplikacji Portal firmy dla systemu Android. W listopadzie 2018 roku opublikowaliśmy aktualizację portalu firmy, która uwzględnia przełącznik zaplecza, aby przygotować się do zmiany wprowadzonej przez firmę Google, która przechodzi ze swojej dotychczasowej platformy powiadomień do usługi Google Firebase Cloud Messaging (FCM). Po wycofaniu przez Google obecnej platformy powiadomień i przejściu do usługi FCM użytkownicy końcowi będą musieli zaktualizować swoją aplikację portalu firmy do wersji z listopada 2018 r. lub nowszej, aby zachować możliwość komunikowania się ze sklepem Google Play.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Nasza telemetria wskazuje, że masz urządzenia z aplikacją Portal firmy w wersji wcześniejszej niż 5.0.4269.0. Jeśli ta lub nowsza wersja aplikacji portalu firmy nie zostanie zainstalowana, akcje inicjowane na urządzeniu przez specjalistę IT, takie jak czyszczenie, resetowanie hasła, instalowanie dostępnych i wymaganych aplikacji oraz rejestrowanie certyfikatów mogą nie działać zgodnie z oczekiwaniami. Jeśli Twoje urządzenia są zarejestrowane w usłudze Intune za pomocą rozwiązania MDM, wersje aplikacji portalu firmy oraz użytkowników możesz wyświetlić, przechodząc do obszaru Aplikacje klienckie — Odnalezione aplikacje. Wybierając wcześniejsze wersje aplikacji Portal firmy, będzie można zobaczyć, którzy użytkownicy końcowi mają urządzenia z niezaktualizowaną wersją portalu firmy.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?
Poproś użytkowników końcowych urządzeń z systemem Android, które nie zostały zaktualizowane, aby zaktualizowali portal firmy za pośrednictwem sklepu Google Play. Powiadom dział pomocy technicznej w przypadku, gdy użytkownik nie ma wybranej opcji automatycznego aktualizowania aplikacji portalu firmy. Skorzystaj z linku w sekcji Dodatkowe informacje, aby dowiedzieć się więcej na temat platformy FCM i zmiany wprowadzanej przez firmę Google.

#### <a name="additional-information"></a>Dodatkowe informacje
https://firebase.google.com/docs/cloud-messaging/


### <a name="new-fullscreen-experience-coming-to-intune---4593669--"></a>Nowe funkcje obsługi pełnego ekranu w usłudze Intune <!--4593669-->
Usługa Intune w witrynie Azure Portal zyska zaktualizowany interfejs użytkownika funkcji tworzenia i edytowania danych. Nowy interfejs uprości istniejące przepływy pracy dzięki zastosowaniu formatu kreatorów w obrębie jednego bloku. Zmiana ta pozwoli pozbyć się natłoku widocznych jednocześnie bloków, a także wyeliminować konieczność przechodzenia do szczegółów bloków podczas zadań związanych z tworzeniem i edytowaniem informacji. Przepływy pracy dotyczące tworzenia zostaną ponadto zaktualizowane o funkcję przypisań (z wyjątkiem przypisywania aplikacji).

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Obsługa pełnego ekranu w usłudze Intune zostanie wprowadzona zarówno w witrynie portal.azure.com, jak i devicemanagement.microsoft.com w ciągu najbliższych kilku miesięcy. Aktualizacja interfejsu użytkownika nie będzie miała wpływu na działanie istniejących zasad i profilów, ale przepływ pracy ulegnie drobnym zmianom. Na przykład podczas tworzenia nowych zasad będzie można już na tym etapie ustawić niektóre przypisania, zamiast robić to później, już po utworzeniu zasad. Dodatkowe informacje o tym, jak te nowe funkcje będą wyglądać w konsoli (wraz ze zrzutami ekranu), znaleźć można we wpisie na blogu.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Co zrobić, aby przygotować się do tej zmiany?
Nie trzeba podejmować żadnych działań, ale w razie potrzeby można rozważyć zaktualizowanie wskazówek dla specjalistów IT. Naszą dokumentację będziemy aktualizować w miarę wdrażania nowych funkcji w kolejnych blokach usługi Intune w witrynie Azure Portal.

#### <a name="additional-information"></a>Dodatkowe informacje 
https://aka.ms/intune_fullscreen
