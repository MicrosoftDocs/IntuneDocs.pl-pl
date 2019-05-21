---
title: dołączanie pliku
description: dołączanie pliku
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: ffcef5b4d78856709f8563ee1f667ec7e5d993b3
ms.sourcegitcommit: d2e04a38e024b0f5afb0ca202823227de9da3ad1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/09/2019
ms.locfileid: "65732603"
---
Te powiadomienia zawierają ważne informacje, które mogą ułatwić przygotowanie się na nadchodzące zmiany i nowe funkcje w usłudze Intune. 

### <a name="change-in-enrollment-workflow-with-intune-company-portal-on-corporate-ios-devices-authenticating-with-setup-assistant----1927359---"></a>Zmiana w przepływie pracy rejestracji w Portalu firmy usługi Intune na firmowych urządzeniach z systemem iOS uwierzytelniających się przy użyciu Asystenta ustawień <!-- 1927359 -->
Zbliża się zmiana w przepływie pracy rejestracji urządzeń z systemem iOS za pomocą jednej z metod rejestracji firmowych urządzeń Apple — programu Apple Configurator lub usług Apple Business Manager, Apple School Manager bądź Apple Device Enrollment Program (DEP), w sytuacji gdy do uwierzytelniania używany jest Asystent ustawień. Ta zmiana dotyczy tylko urządzeń zarejestrowanych za pomocą koligacji użytkownika.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Po wprowadzeniu tej zmiany profile rejestracji w usłudze Intune w witrynie Azure Portal zostaną zaktualizowane, tak aby określić sposób uwierzytelniania urządzeń oraz wskazać, czy otrzymują aplikację Portal firmy. Przepływ pracy dotyczący rejestracji urządzeń z systemem iOS za pomocą metod wymienionych powyżej zostanie usprawniony. 

- W przypadku rejestrowania nowych urządzeń i uwierzytelniania przy użyciu Asystenta ustawień będzie można wybrać, czy należy automatycznie wdrożyć aplikację Portal firmy. Użytkownicy końcowi nie zobaczą już ekranów „Identyfikowanie urządzenia” i „Potwierdzanie urządzenia” w procesie rejestracji.  
- Na urządzeniach, które są już zarejestrowane za pośrednictwem Asystenta ustawień za pomocą jednej z metod rejestracji urządzeń firmowych firmy Apple, w celu włączenia dostępu warunkowego należy podjąć odpowiednie działania. Trzeba [skonfigurować zasady konfiguracji aplikacji](https://aka.ms/enrollment_setup_assistant) za pomocą określonego pliku xml w celu wypychania aplikacji Portal firmy do tych urządzeń.  Jeśli zdecydujesz się na wypychanie aplikacji Portal firmy w taki sposób, użytkownicy końcowi nie zobaczą już ekranów „Identyfikowanie urządzenia” i „Potwierdzanie urządzenia” w procesie rejestracji. 
- Po wdrożeniu tej zmiany, jeśli Portal firmy nie zostanie wdrożony przy użyciu profilu konfiguracji aplikacji wymienionego powyżej, a użytkownicy końcowi pobiorą aplikację Portal firmy ze sklepu z aplikacjami, będą mogli się zalogować, ale zostanie wyświetlony komunikat o błędzie. Nie będą mogli korzystać z tej aplikacji na potrzeby dostępu warunkowego. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?
Jeśli planujesz używanie zmodyfikowanego przepływu pracy, należy zaktualizować wskazówki dla użytkowników końcowych, podając informacje, że:

- Użytkownicy końcowi nie będą już widzieli dwóch wspomnianych powyżej ekranów w procedurze rejestracji. 
- Będą musieli zalogować się do aplikacji Portal firmy, gdy zostanie wdrożona automatycznie, a nie pobierać ją ze sklepu z aplikacjami. 

Jeśli chcesz, możesz teraz utworzyć zasady konfiguracji aplikacji w ramach przygotowania do tej zmiany. Kiedy nowy przepływ pracy zostanie wdrożony, zobaczysz zaktualizowane profile rejestracji w konsoli. Firma Microsoft poinformuje również o tym wdrożeniu za pośrednictwem Centrum wiadomości. Wtedy trzeba będzie podjąć odpowiednie działania, dzięki czemu użytkownicy końcowi będą mogli rejestrować się za pomocą programu DEP z uwierzytelnianiem przy użyciu Asystenta ustawień, a aplikacji Portal firmy będzie można użyć na potrzeby dostępu warunkowego.

#### <a name="additional-information"></a>Dodatkowe informacje 
[https://aka.ms/enrollment_setup_assistant](https://aka.ms/enrollment_setup_assistant)


### <a name="update-your-android-company-portal-app-to-the-latest-version---4536963--"></a>Aktualizacja aplikacji Portal firmy dla systemu Android do najnowszej wersji <!--4536963-->
W ramach usługi Intune okresowo wydawane są aktualizacje aplikacji Portal firmy dla systemu Android. W listopadzie 2018 roku opublikowaliśmy aktualizację portalu firmy, która uwzględnia przełącznik zaplecza, aby przygotować się do zmiany wprowadzonej przez firmę Google, która przechodzi ze swojej dotychczasowej platformy powiadomień do usługi Google Firebase Cloud Messaging (FCM). Po wycofaniu przez Google obecnej platformy powiadomień i przejściu do usługi FCM użytkownicy końcowi będą musieli zaktualizować swoją aplikację portalu firmy do wersji z listopada 2018 r. lub nowszej, aby zachować możliwość komunikowania się ze sklepem Google Play.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Nasza telemetria wskazuje, że masz urządzenia z aplikacją Portal firmy w wersji wcześniejszej niż 5.0.4269.0. Jeśli ta lub nowsza wersja aplikacji portalu firmy nie zostanie zainstalowana, akcje inicjowane na urządzeniu przez specjalistę IT, takie jak czyszczenie, resetowanie hasła, instalowanie dostępnych i wymaganych aplikacji oraz rejestrowanie certyfikatów mogą nie działać zgodnie z oczekiwaniami. Jeśli Twoje urządzenia są zarejestrowane w usłudze Intune za pomocą rozwiązania MDM, wersje aplikacji portalu firmy oraz użytkowników możesz wyświetlić, przechodząc do obszaru Aplikacje klienckie — Odnalezione aplikacje. Wybierając wcześniejsze wersje aplikacji Portal firmy, będzie można zobaczyć, którzy użytkownicy końcowi mają urządzenia z niezaktualizowaną wersją portalu firmy.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?
Poproś użytkowników końcowych urządzeń z systemem Android, które nie zostały zaktualizowane, aby zaktualizowali portal firmy za pośrednictwem sklepu Google Play. Powiadom dział pomocy technicznej w przypadku, gdy użytkownik nie ma wybranej opcji automatycznego aktualizowania aplikacji portalu firmy. Skorzystaj z linku w sekcji Dodatkowe informacje, aby dowiedzieć się więcej na temat platformy FCM i zmiany wprowadzanej przez firmę Google.

#### <a name="additional-information"></a>Dodatkowe informacje
https://firebase.google.com/docs/cloud-messaging/