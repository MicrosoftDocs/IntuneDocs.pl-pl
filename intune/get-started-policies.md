---
title: Wprowadzenie do zasad
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1ac74ba5-7441-44ac-98b5-9d8bb8899747
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 232ec25c34df5e71f70737ca5f0f8a2ef12a05f0
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/03/2017
---
# <a name="getting-started-with-policies"></a>Wprowadzenie do zasad

Jednym z głównych celów rozpoczynania pracy z usługą Intune jest rejestrowanie urządzeń w celu zapewnienia, że są one zgodne z zasadami firmy. Zasady zgodności nie tylko ułatwiają zarządzanie specjalnymi typami urządzeń, takimi jak kioski należące do firmy, ale także urządzeniami osobistymi (BYOD), takimi jak tablety, oraz urządzeniami nienależącymi do żadnego użytkownika.

![Pulpit nawigacyjny zgodności z bardzo małą ilością danych](/intune/media/generic-compliance-dashboard.png)

Zasady zgodności zapewniają następujące możliwości zarządzania dla urządzeń przenośnych:

* Określanie liczby urządzeń, które może zarejestrować każdy użytkownik
* Zarządzanie ustawieniami urządzeń (na przykład szyfrowaniem na poziomie urządzenia, długością hasła czy użyciem aparatu fotograficznego)
* Dostarczanie aplikacji, profilów poczty e-mail, profilów sieci VPN itp.
* Ocenianie na poziomie urządzenia kryteriów dotyczących zasad zgodności z zabezpieczeniami

Zasady zgodności są tworzone osobno dla każdej platformy. Na potrzeby tego ćwiczenia używany będzie system iOS. Dla urządzeń z systemem iOS dostępne są następujące zasady:

* Konfiguracja kodu PIN lub hasła
* Szyfrowanie urządzenia
* Urządzenie ze zdjętymi zabezpieczeniami systemu
* Profil e-mail
* Minimalna wersja systemu operacyjnego
* Maksymalna wersja systemu operacyjnego

__Jak utworzyć zasady?__

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. W polu **Wyszukaj zasoby** wyszukaj usługę **Intune**.
3. Wybierz pozycję **Zgodność urządzenia**.
4. W bloku **Zgodność urządzenia** wybierz pozycję **Zasady**.
5. Wybierz pozycję **Utwórz zasady**, a następnie wprowadź szczegółowe informacje, takie jak **Nazwa** i **Opis**. Wybierz pozycję **iOS** na liście **Platforma**.
6. W obszarze **Ustawienia** wybierz pozycję **Zabezpieczenia systemu**, a następnie przełącz opcję **Wymagaj hasła do odblokowania urządzeń przenośnych** na wartość **Wymagaj**. Możesz również ustawić inne reguły, takie jak **Minimalna długość hasła**, **Wymagany typ hasła** i **Liczba znaków innych niż alfanumeryczne w haśle**. Po zakończeniu konfigurowania zasad wybierz przycisk **OK**.
7. Wróć do obszaru **Tworzenie zasad**, a następnie wybierz pozycję **Utwórz**.
8. Po utworzeniu zasad wybierz pozycję **Przypisania**, aby przypisać je do grupy testowej. Wybierz grupę testową (powinien do niej należeć użytkownik testowy), a następnie przypisz zasady do tej grupy, klikając pozycję **Zapisz**.
9. Poczekaj kilka minut, po których na zarejestrowanym urządzeniu powinien zostać wyświetlony monit z informacją, że wymagane jest zaktualizowanie hasła, aby utrzymać zgodność z zasadami firmowymi. Można to również sprawdzić ręcznie w **aplikacji Portal firmy dla systemu iOS**, naciskając nazwę urządzenia, a następnie przycisk **Synchronizuj**.
