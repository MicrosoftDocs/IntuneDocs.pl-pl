---
# required metadata

title: Rejestrowanie urządzeń należących do firmy przy użyciu menedżera rejestracji urządzeń w usłudze Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a23abc61-69ed-44f1-9b71-b86aefc6ba03

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Rejestrowanie urządzeń należących do firmy przy użyciu menedżera rejestracji urządzeń w usłudze Microsoft Intune
Organizacje mogą używać usługi Intune do zarządzania dużą liczbą urządzeń przenośnych za pomocą jednego konta użytkownika. Konto *menedżera rejestracji urządzeń* jest specjalnym kontem usługi Intune z uprawnieniem do rejestracji więcej niż 5 urządzeń. Możesz przypisać menedżera lub kierownika magazynu, na przykład konto użytkownika menedżera rejestracji urządzeń, aby umożliwić wykonywanie następujących czynności:

-   Rejestrowanie urządzeń w usłudze Intune

-   Logowanie się do portalu firmy w celu pobrania aplikacji firmowych

-   Instalowanie i odinstalowywanie oprogramowania

-   Konfigurowanie dostępu do danych firmowych

Używaj konta menedżera urządzeń tylko wobec urządzeń, które nie otrzymają wiadomości e-mail lub loginu dla konkretnego użytkownika. Urządzeń zarządzanych za pomocą konta menedżera urządzeń nie można konfigurować przy użyciu dostępu warunkowego, ponieważ jest on również częścią scenariuszy opartych na poszczególnych użytkownikach. Menedżer magazynu nie może resetować urządzenia z portalu firmy.

**Przykład scenariusza menedżera rejestracji urządzeń:**
Restauracja potrzebuje tabletów do punktów sprzedaży dla swoich kelnerów oraz monitorów zamówień dla personelu w kuchni. Pracownicy w ogóle nie potrzebują dostępu do danych firmowych ani nie muszą logować się jako użytkownicy. Administrator usługi Intune tworzy konto menedżera rejestracji urządzeń i rejestruje urządzenia należące do firmy za pomocą tego konta. Administrator może również przyznać poświadczenia menedżera rejestracji urządzeń menedżerowi restauracji, umożliwiając mu tym samym rejestrowanie urządzeń i zarządzanie nimi.

Administrator lub menedżer może wdrożyć aplikacje specyficzne dla ról na urządzeniach w restauracji. Administrator może również wybrać urządzenie w konsoli programu Intune i wycofać je z zarządzania urządzeniami przenośnymi za pomocą konsoli administracyjnej.

> [!NOTE]
> Konta użytkownika menedżera rejestracji urządzeń z ponad 20 zarejestrowanymi urządzeniami mogą powodować problemy podczas korzystania z aplikacji portalu firmy. Aby wdrożyć firmowe aplikacje na urządzeniach zarządzanych przy użyciu menedżera rejestracji urządzeń, wdróż aplikację portalu firmy jako **wymaganą instalację** na koncie użytkownika menedżera rejestracji urządzeń.

## Tworzenie kont menedżerów rejestracji urządzeń
Konta menedżerów rejestracji urządzeń to konta użytkowników z uprawnieniem do rejestrowania dużej liczby urządzeń należących do firmy. Menedżerami rejestracji urządzeń mogą być tylko użytkownicy w konsoli usługi Intune.

#### Dodawanie menedżera rejestracji urządzeń do usługi Intune

1.  Przejdź do [portalu konta usługi Microsoft Intune](http://go.microsoft.com/fwlink/?LinkId=698854) i zaloguj się na swoim koncie administratora.

2.  Kliknij pozycję **Dodaj użytkownika**.

3.  Upewnij się, że konto użytkownika, który będzie menedżerem rejestracji urządzeń, jest wyświetlane na liście. Jeśli nie, dodaj użytkownika, klikając pozycję **Nowy** i wykonując procedurę Dodawanie użytkownika. Każdy użytkownik, który uzyskuje dostęp do usługi, musi mieć licencję subskrypcyjną, a *menedżer rejestracji urządzeń* nie może być administratorem usługi Intune. Przed użyciem tej funkcji określ, czy potrzebujesz dodać więcej licencji.

4.  Zaloguj się do [konsoli administracyjnej usługi Microsoft Intune](http://manage.microsoft.com) przy użyciu swojego konta administratora.

5.  W okienku nawigacji kliknij pozycję **Administrator**, następnie przejdź do sekcji **Zarządzanie Administratorami** i wybierz pozycję **Menedżer rejestracji urządzeń**. Zostanie otwarta strona menedżerów rejestracji urządzeń.

6.  Kliknij przycisk **Dodaj...**. Zostanie otwarte okno dialogowe **Dodawanie menedżera rejestracji urządzeń** .

7.  Wprowadź **Identyfikator użytkownika** konta usługi Intune, a następnie kliknij przycisk **OK**. Użytkownik konta menedżera rejestracji urządzeń nie może być administratorem usługi Intune.

8.  Menedżer rejestracji urządzeń może teraz rejestrować urządzenia przenośne za pomocą tej samej procedury, której używa użytkownik końcowy w ramach scenariusza „Przynieś własne urządzenie” (BYOD, Bring Your Own Device) w portalu firmy.

## Usuwanie menedżera rejestracji urządzeń z usługi Intune

1.  Zaloguj się do [portalu administracyjnego usługi Microsoft Intune](http://manage.microsoft.com) przy użyciu swojego konta administratora.

2.  W okienku nawigacji kliknij pozycję **Administrator** , następnie przejdź do sekcji **Zarządzanie Administratorami** i wybierz pozycję **Menedżer rejestracji urządzeń**. Zostanie otwarta strona menedżerów rejestracji urządzeń.

3.  Na stronie menedżerów rejestracji urządzeń określ, który **Użytkownik** ma zostać usunięty, a następnie kliknij przycisk **Usuń**. Ten użytkownik nie zostanie usunięty z usługi Intune, a zarządzane przez niego urządzenia pozostaną zarejestrowane w usłudze Intune. Usunięcie menedżera rejestracji urządzeń uniemożliwi temu użytkownikowi rejestrację kolejnych urządzeń w usłudze Intune.

4.  Kliknij przycisk **Tak** , aby potwierdzić chęć usunięcia menedżera rejestracji urządzeń.

Usunięcie menedżera rejestracji urządzeń nie ma wpływu na zarejestrowane urządzenia. Gdy menedżer rejestracji urządzeń zostanie usunięty:

-   Nie będzie to mieć wpływu na zarejestrowane urządzenia

-   Zarejestrowane urządzenia będą nadal w pełni zarządzane

-   Poświadczenia konta usuniętego menedżera rejestracji urządzeń zachowają ważność i będzie można ich nadal używać do logowania się do portalu firmy w celu uzyskiwania dostępu do aplikacji

-   Używając poświadczeń konta usuniętego menedżera rejestracji urządzeń, nadal nie będzie można czyścić ani wycofywać urządzeń

-   Relacje usuniętego konta menedżera rejestracji urządzeń z zarejestrowanymi urządzeniami zostaną zachowane, ale nie będzie można zarejestrować żadnych dodatkowych urządzeń


<!--HONumber=May16_HO1-->


