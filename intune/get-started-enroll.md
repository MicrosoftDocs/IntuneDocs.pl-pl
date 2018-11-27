---
title: Informacje na temat środowiska rejestracji urządzenia z systemem iOS
titlesuffix: Microsoft Intune
description: Poznaj środowisko rejestracji, przeprowadzając pełną rejestrację urządzenia z systemem iOS.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: b595848d-c451-43ab-812d-b22e0170fb7a
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: bdd8267701b20600d67e6927c8b55d7f9c11a34f
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52186770"
---
# <a name="understand-the-users-experience-enrolling-an-ios-device"></a>Informacje na temat środowiska użytkownika służącego do rejestracji urządzenia z systemem iOS

Usługa Microsoft Intune ułatwia pracę pracowników mających urządzenia przenośne, chroniąc dane firmowe. Ponieważ użytkownicy końcowi będą wchodzić w interakcję z usługą Intune na swoich urządzeniach, a nie w konsoli administracyjnej, istotna jest dobra znajomość środowiska rejestracji. W ten sposób można połączyć dobrze przygotowane zasady zgodności i doświadczenie, aby okazać zrozumienie dla użytkowników. Jest to szczególnie ważne, ponieważ użytkownicy będą w pełni świadomi, jakie informacje są widoczne dla administratora:

| Czego nie widzi dział IT | Co widzi dział IT |
|---|---|
| Historia połączeń i przeglądania sieci Web | Model |
| Lokalizacja | Numer seryjny |
| Osobisty adres e-mail | Wersja systemu operacyjnego |
| Wiadomości SMS | Nazwy aplikacji |
| Kontakty | Właściciel |
| Hasła do kont osobistych | Nazwa urządzenia |
| Zdarzenia kalendarza | Producent (dla urządzeń, które nie zostały wyprodukowane przez firmę Apple) |
| Obrazy, w tym dane z aparatu i aplikacji Zdjęcia | Numer telefonu (dla urządzeń służbowych: cały numer; dla urządzeń osobistych: cztery ostatnie cyfry) |

## <a name="how-do-i-enroll-a-device"></a>Jak zarejestrować urządzenie?

Rejestrowanie urządzenia stanowi pierwsze doświadczenie użytkowników końcowych podczas dostępu do zasobów firmy. [Zrozumienie tego procesu](end-user-educate.md) może obrócić potencjalnie trudną sytuację w pozytywne doświadczenie.

1. Otwórz stronę sklepu **App Store** i wyszukaj aplikację **Portal firmy usługi Intune**.
2. Pobierz aplikację **Portal firmy w usłudze Microsoft Intune**.
3. Otwórz aplikację **Portal firmy**, podaj adres e-mail i hasło użytkownika testowego, a następnie naciśnij pozycję **Zaloguj**.
4. Zaktualizuj hasło tymczasowe na nowe.
5. Na stronie **Konfiguracja dostępu do zasobów firmy** naciśnij pozycję **Rejestrowanie urządzenia**.
6. Na stronie **Dlaczego warto zarejestrować urządzenie?** przeczytaj, co możesz zrobić po zarejestrowaniu urządzenia, a następnie naciśnij pozycję **Kontynuuj**.
7. Przejrzyj listę zasobów, do których użytkownik uzyskuje dostęp po rejestracji, a następnie naciśnij pozycję **Kontynuuj**.
8. Przejrzyj, co administrator IT może zobaczyć na Twoim urządzeniu, a czego nie, a następnie naciśnij pozycję **Kontynuuj**.
9. Na stronie **Co teraz** przeczytaj, jak będzie przebiegała rejestracja, a następnie naciśnij przycisk **Zarejestruj**.
10. Na stronie **Instalacja profilu** naciśnij pozycję **Zainstaluj**, a następnie wprowadź kod dostępu urządzenia, jeśli zostanie wyświetlony monit.
11. Naciśnij przycisk **Zainstaluj**.
12. Ponownie naciśnij pozycję **Zainstaluj**, aby potwierdzić, że ostrzeżenie zostało przeczytane.
13. W oknie podręcznym **Ostrzeżenie** naciśnij pozycję **Ufaj**.
14. Gdy ekran zmieni się, aby pokazać, że instalacja profilu została zakończona, naciśnij pozycję **Gotowe**.
15. Na ekranie zostanie wyświetlony komunikat „Rejestrowanie urządzenia” z informacją, że urządzenie zostało pomyślnie zarejestrowane. Zostanie wyświetlone okno podręczne z prośbą do użytkownika o otwarcie strony w Portalu firmy. Naciśnij pozycję **Otwórz**.
16. Nastąpi powrót na ekran **Konfiguracja dostępu do zasobów firmy**. Jeśli nie zostały skonfigurowane żadne zasady testowe, to urządzenie powinno być widoczne jako zgodne. Jeśli istnieją jakiekolwiek zasady testowe, naciśnięcie pozycji **Zgodność urządzenia** spowoduje wyświetlenie informacji, że istnieją działania, które należy wykonać, aby zabezpieczyć urządzenie.

## <a name="next-steps"></a>Następne kroki

[Wprowadzenie do dodawania aplikacji](get-started-apps.md) — znajduj i dodawaj aplikacje do urządzeń, aby umożliwić pracownikom wykonywanie zadań.

## <a name="learn-more"></a>Dowiedz się więcej

* [Opcje rejestracji dla usługi Intune](enrollment-options.md)
* [Enable bring your own device with Intune (Włączanie funkcji Przynieś własne urządzenie w usłudze Intune)](byod-enable.md)
* [Educating your end users about enrollment and device management (Szkolenie użytkowników końcowych w zakresie rejestracji i zarządzania urządzeniami)](end-user-educate.md)
