---
title: Wprowadzenie do zasad w usłudze Microsoft Intune
titlesuffix: ''
description: Utwórz zasady, aby chronić dane firmowe i zarządzać urządzeniami używanymi przez użytkowników końcowych w celu uzyskiwania dostępu do zasobów firmy.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1ac74ba5-7441-44ac-98b5-9d8bb8899747
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 661ef25085892e299e45156f27b3d9db959577d4
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="get-started-with-creating-policies"></a>Wprowadzenie do tworzenia zasad

Jednym z głównych celów rozpoczynania pracy z usługą Intune jest rejestrowanie urządzeń w celu zapewnienia, że są one zgodne z zasadami firmy. Zasady zgodności nie tylko ułatwiają zarządzanie specjalnymi typami urządzeń, takimi jak kioski należące do firmy, ale także urządzeniami osobistymi (BYOD), takimi jak tablety, oraz urządzeniami nienależącymi do żadnego użytkownika.

![Pulpit nawigacyjny zgodności z małą ilością danych](/intune/media/generic-compliance-dashboard.png)

Zarządzaj urządzeniami przenośnymi w następujących obszarach za pomocą zasad zgodności:

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

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. Wybierz pozycję **Zgodność urządzenia**.
4. W okienku **Zgodność urządzeń** wybierz pozycję **Zasady**.
5. Wybierz pozycję **Utwórz zasady**, a następnie wprowadź szczegółowe informacje, takie jak **Nazwa** i **Opis**. 
6. Wybierz pozycję **iOS** na liście **Platforma**.
6. W obszarze **Ustawienia** wybierz pozycję **Zabezpieczenia systemu**, a następnie przełącz opcję **Wymagaj hasła do odblokowania urządzeń przenośnych** na wartość **Wymagaj**. Możesz również ustawić inne reguły, takie jak **Minimalna długość hasła**, **Wymagany typ hasła** i **Liczba znaków innych niż alfanumeryczne w haśle**. Po zakończeniu konfigurowania zasad wybierz przycisk **OK**.
7. Wróć do okienka **Tworzenie zasad**, a następnie wybierz pozycję **Utwórz**.
8. Po utworzeniu zasad wybierz pozycję **Przypisania**, aby przypisać je do grupy testowej. Wybierz grupę testową (powinien do niej należeć użytkownik testowy), a następnie przypisz zasady do tej grupy, klikając pozycję **Zapisz**.
9. Poczekaj kilka minut, po których na zarejestrowanym urządzeniu powinien zostać wyświetlony monit z informacją, że wymagane jest zaktualizowanie hasła, aby utrzymać zgodność z zasadami firmowymi. Można to również sprawdzić ręcznie w **aplikacji Portal firmy dla systemu iOS**, naciskając nazwę urządzenia, a następnie przycisk **Synchronizuj**.

## <a name="next-steps"></a>Następne kroki

[Wprowadzenie do rejestrowania urządzeń](get-started-enroll.md) — poznaj środowisko rejestracji, przeprowadzając pełną rejestrację urządzenia z systemem iOS.

## <a name="learn-more"></a>Dowiedz się więcej

* [Monitorowanie zasad zgodności urządzeń Intune](compliance-policy-monitor.md)
* [Typowe sposoby korzystania z zasad dostępu warunkowego przy użyciu usługi Intune](conditional-access-intune-common-ways-use.md)
