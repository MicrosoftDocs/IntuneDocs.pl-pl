---
title: "Rejestrowanie przy użyciu menedżera rejestracji urządzeń | Microsoft Intune"
description: "Za pomocą konta menedżera rejestracji urządzeń usługi Microsoft Intune można zarządzać dużą liczbą firmowych, współdzielonych urządzeń przenośnych za pomocą jednego konta użytkownika."
keywords: 
author: NathBarn
manager: arob98
ms.date: 07/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a23abc61-69ed-44f1-9b71-b86aefc6ba03
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1e0d05a4f229e2a8e72d1d60021b159f12dfa0d1
ms.openlocfilehash: 5c7eecf5b7801eca3d23dd0eee954203e9c9cb06


---


# Rejestrowanie urządzeń należących do firmy przy użyciu menedżera rejestracji urządzeń w usłudze Microsoft Intune
Organizacje mogą używać usługi Intune do zarządzania dużą liczbą urządzeń przenośnych za pomocą jednego konta użytkownika. Konto *menedżera rejestracji urządzeń* jest specjalnym kontem usługi Intune z uprawnieniem do rejestracji maksymalnie 1000 urządzeń. Urządzenia zarejestrowane przy użyciu konta menedżera rejestracji urządzeń powinny być używane jako urządzenia udostępnione, a nie urządzenia osobiste („BYOD”). Użytkownicy nie będą mogli na przykład korzystać z natywnych aplikacji poczty e-mail. Możesz przypisać menedżera lub kierownika magazynu, na przykład konto użytkownika menedżera rejestracji urządzeń, aby umożliwić wykonywanie następujących czynności:

-   Rejestrowanie urządzeń w usłudze Intune

-   Logowanie się do portalu firmy w celu pobrania aplikacji firmowych

-   Instalowanie i odinstalowywanie oprogramowania

-   Konfigurowanie dostępu do danych firmowych


**Przykłady scenariusza menedżera rejestracji urządzeń:** restauracja potrzebuje tabletów do punktów sprzedaży dla kelnerów oraz monitorów zamówień dla personelu w kuchni. Pracownicy w ogóle nie potrzebują dostępu do danych firmowych ani nie muszą logować się jako użytkownicy. Administrator usługi Intune tworzy konto menedżera rejestracji urządzeń i rejestruje urządzenia należące do firmy za pomocą tego konta. Administrator może również przyznać poświadczenia menedżera rejestracji urządzeń menedżerowi restauracji, umożliwiając mu tym samym rejestrowanie urządzeń i zarządzanie nimi.

Administrator lub menedżer może wdrożyć aplikacje specyficzne dla ról na urządzeniach w restauracji. Administrator może również wybrać urządzenie w konsoli programu Intune i wycofać je z zarządzania urządzeniami przenośnymi za pomocą konsoli administracyjnej.

Urządzenia zarejestrowane przy użyciu konta menedżera rejestracji urządzeń mają następujące ograniczenia:
  - Nie ma określonego użytkownika, a więc wszystkie urządzenia są urządzeniami „bez użytkownika”, w związku z tym nie ma dostępu do poczty e-mail czy danych firmowych, choć na przykład sieć VPN może nadal zapewniać aplikacjom urządzenia dostęp do danych
  - Nie ma warunkowego dostępu, ponieważ są to scenariusze dla poszczególnych użytkowników
  - Nie można resetować urządzeń z poziomu Portalu firmy
  - Tylko urządzenie lokalne pojawia się w aplikacji lub witrynie internetowej Portal firmy
  - Brak aplikacji z programu zakupów zbiorczych VPP (ang. Volume Purchase Program) firmy Apple ze względu na wymagania dotyczące identyfikatora Apple ID dla poszczególnych użytkowników na potrzeby zarządzania aplikacjami
  - Brak możliwości zarejestrowania przy użyciu narzędzia Apple Configurator lub w ramach programu rejestracji urządzeń firmy Apple (dotyczy urządzeń z systemem iOS)

> [!NOTE]
> Aby wdrożyć firmowe aplikacje na urządzeniach zarządzanych przy użyciu menedżera rejestracji urządzeń, wdróż aplikację portalu firmy jako **wymaganą instalację** na koncie użytkownika menedżera rejestracji urządzeń.
> Aby zwiększyć wydajność, podczas wyświetlania aplikacji Portal firmy na urządzeniu menedżera rejestracji urządzeń pokazywane jest tylko urządzenie lokalne. Zdalne zarządzanie innymi urządzeniami menedżera rejestracji urządzeń jest możliwe wyłącznie za pomocą konsoli administracyjnej usługi Intune.

## Tworzenie kont menedżerów rejestracji urządzeń
Konta menedżerów rejestracji urządzeń to konta użytkowników z uprawnieniem do rejestrowania dużej liczby urządzeń należących do firmy. Menedżerami rejestracji urządzeń mogą być tylko użytkownicy w konsoli usługi Intune.

#### Dodawanie menedżera rejestracji urządzeń do usługi Intune

1.  Przejdź do [portalu konta usługi Microsoft Intune](http://go.microsoft.com/fwlink/?LinkId=698854) i zaloguj się na swoim koncie administratora.

2.  Wybierz pozycję **Dodaj użytkownika**.

3.  Upewnij się, że konto użytkownika, który będzie menedżerem rejestracji urządzeń, jest wyświetlane na liście. Jeśli nie, dodaj użytkownika, wybierając pozycję **Nowy** i wykonując procedurę Dodawanie użytkownika. Każdy użytkownik, który uzyskuje dostęp do usługi, musi mieć licencję subskrypcyjną, a *menedżer rejestracji urządzeń* nie może być administratorem usługi Intune. Przed użyciem tej funkcji określ, czy potrzebujesz dodać więcej licencji.

4.  Zaloguj się do [konsoli administracyjnej usługi Microsoft Intune](http://manage.microsoft.com) przy użyciu swojego konta administratora.

5.  W okienku nawigacji wybierz pozycję **Administrator**, a następnie przejdź do sekcji **Zarządzanie administratorami** i wybierz pozycję **Menedżer rejestracji urządzeń**. Zostanie otwarta strona menedżerów rejestracji urządzeń.

6.  Wybierz pozycję **Dodaj**. Zostanie otwarte okno dialogowe **Dodawanie menedżera rejestracji urządzeń** .

7.  Wprowadź **identyfikator użytkownika** konta usługi Intune, a następnie wybierz pozycję **OK**. Użytkownik konta menedżera rejestracji urządzeń nie może być administratorem usługi Intune.

8.  Menedżer rejestracji urządzeń może teraz rejestrować urządzenia przenośne za pomocą tej samej procedury, której używa użytkownik końcowy w ramach scenariusza „Przynieś własne urządzenie” (BYOD, Bring Your Own Device) w portalu firmy.

## Usuwanie menedżera rejestracji urządzeń z usługi Intune

1.  Zaloguj się do [portalu administracyjnego usługi Microsoft Intune](http://manage.microsoft.com) przy użyciu swojego konta administratora.

2.  W okienku nawigacji wybierz pozycję **Administrator**, a następnie przejdź do sekcji **Zarządzanie administratorami** i wybierz pozycję **Menedżer rejestracji urządzeń**. Zostanie otwarta strona menedżerów rejestracji urządzeń.

3.  Wybierz **Użytkownika**, którego menedżer rejestracji urządzeń ma zostać usunięty, a następnie wybierz pozycję **Usuń**. Ten użytkownik nie zostanie usunięty z usługi Intune, a zarządzane przez niego urządzenia pozostaną zarejestrowane w usłudze Intune. Usunięcie menedżera rejestracji urządzeń uniemożliwi temu użytkownikowi rejestrację kolejnych urządzeń w usłudze Intune.

4.  Wybierz pozycję **Tak**, aby potwierdzić chęć usunięcia menedżera rejestracji urządzeń.

Usunięcie menedżera rejestracji urządzeń nie ma wpływu na zarejestrowane urządzenia. Gdy menedżer rejestracji urządzeń zostanie usunięty:

-   Nie będzie to mieć wpływu na zarejestrowane urządzenia

-   Zarejestrowane urządzenia będą nadal w pełni zarządzane

-   Poświadczenia konta usuniętego menedżera rejestracji urządzeń zachowają ważność i będzie można ich nadal używać do logowania się do portalu firmy w celu uzyskiwania dostępu do aplikacji

-   Używając poświadczeń konta usuniętego menedżera rejestracji urządzeń, nadal nie będzie można czyścić ani wycofywać urządzeń

-   Relacje usuniętego konta menedżera rejestracji urządzeń z zarejestrowanymi urządzeniami zostaną zachowane, ale nie będzie można zarejestrować żadnych dodatkowych urządzeń



<!--HONumber=Jul16_HO3-->


