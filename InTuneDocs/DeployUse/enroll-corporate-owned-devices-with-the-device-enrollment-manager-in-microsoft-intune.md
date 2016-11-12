---
title: "Rejestrowanie przy użyciu menedżera rejestracji urządzeń | Microsoft Intune"
description: "Za pomocą konta menedżera rejestracji urządzeń można zarządzać dużą liczbą współdzielonych firmowych urządzeń przenośnych za pomocą jednego konta użytkownika."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 07/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a23abc61-69ed-44f1-9b71-b86aefc6ba03
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 289e6019aa1a17deb91b38ed32f0432af0902a9d
ms.openlocfilehash: 51e5f248c5e8759d5992918a99e1f114e2614142


---


# <a name="enroll-corporateowned-devices-with-the-device-enrollment-manager-in-microsoft-intune"></a>Rejestrowanie urządzeń należących do firmy przy użyciu menedżera rejestracji urządzeń w usłudze Microsoft Intune
Organizacje mogą używać usługi Intune do zarządzania dużą liczbą urządzeń przenośnych za pomocą jednego konta użytkownika. Konto *menedżera rejestracji urządzeń* jest specjalnym kontem usługi Intune umożliwiającym rejestrację do 1000 urządzeń. Zalecamy używanie urządzeń zarejestrowanych przy użyciu tego konta jako urządzeń udostępnionych, a nie urządzeń osobistych („BYOD”). Użytkownicy nie będą mogli na przykład korzystać z natywnych aplikacji poczty e-mail.

Konto użytkownika menedżera rejestracji urządzeń można na przykład przypisać menedżerowi lub kierownikowi magazynu, aby umożliwić mu wykonywanie następujących czynności:

-   Rejestrowanie urządzeń w usłudze Intune.

-   Logowanie się w Portalu firmy w celu pobierania aplikacji firmowych.

-   Instalowanie i odinstalowywanie oprogramowania.

-   Konfigurowanie dostępu do danych firmowych.


**Scenariusz menedżera rejestracji urządzeń:** restauracja potrzebuje tabletów dla kelnerów w punktach sprzedaży oraz monitorów zamówień dla personelu kuchni. Pracownicy nigdy nie muszą uzyskiwać dostępu do danych firmowych ani logować się jako użytkownicy. Administrator usługi Intune tworzy konto menedżera rejestracji urządzeń i rejestruje za jego pomocą urządzenia należące do firmy. Administrator może również przyznać menedżerowi restauracji poświadczenia menedżera rejestracji urządzeń, umożliwiając mu tym samym rejestrowanie urządzeń i zarządzanie nimi.

Administrator lub menedżer może wdrożyć aplikacje specyficzne dla ról na urządzeniach w restauracji. Administrator może również wybrać urządzenie w konsoli programu Intune i wycofać je z zarządzania urządzeniami przenośnymi za pomocą konsoli administracyjnej.

Urządzenia zarejestrowane przy użyciu konta menedżera rejestracji urządzeń mają następujące ograniczenia:
  - Brak konkretnego „użytkownika” skutkuje brakiem dostępu do wiadomości e-mail i danych firmy. Można jednak skorzystać na przykład z sieci VPN, dzięki czemu aplikacje urządzenia otrzymają dostęp do danych.
  - Brak możliwości dostępu warunkowego, przewidzianego w scenariuszach dla poszczególnych użytkowników.
  - Nie można resetować urządzeń z poziomu Portalu firmy.
  - W aplikacji lub witrynie internetowej Portal firmy widoczne jest tylko urządzenie lokalne.
  - Nie można używać aplikacji z programu zakupów zbiorczych VPP (ang. Volume Purchase Program) firmy Apple ze względu na wymagania dotyczące identyfikatora Apple ID dla poszczególnych użytkowników na potrzeby zarządzania aplikacjami.
  - (iOS) Nie można ich rejestrować za pomocą programu Apple Configurator ani Apple Device Enrollment Program (DEP), ale urządzenia zarządzane w ramach programu DEP lub Apple Configurator mogą być rejestrowane bez koligacji użytkownika.

> [!NOTE]
> Aby wdrożyć firmowe aplikacje na urządzeniach zarządzanych przy użyciu menedżera rejestracji urządzeń, wdróż aplikację Portal firmy jako **wymaganą instalację** na koncie użytkownika menedżera rejestracji urządzeń.
> Aby zwiększyć wydajność, podczas wyświetlania aplikacji Portal firmy na urządzeniu menedżera rejestracji urządzeń pokazywane jest tylko urządzenie lokalne. Zdalne zarządzanie innymi urządzeniami menedżera rejestracji urządzeń jest możliwe wyłącznie za pomocą konsoli administracyjnej usługi Intune.

## <a name="create-device-enrollment-manager-accounts"></a>Tworzenie kont menedżerów rejestracji urządzeń
Konta menedżerów rejestracji urządzeń to konta użytkowników z uprawnieniem do rejestrowania dużej liczby urządzeń należących do firmy. Menedżerami rejestracji urządzeń mogą być tylko użytkownicy w konsoli usługi Intune.

#### <a name="add-a-device-enrollment-manager-to-intune"></a>Dodawanie menedżera rejestracji urządzeń do usługi Intune

1.  Przejdź do [portalu konta usługi Microsoft Intune](http://go.microsoft.com/fwlink/?LinkId=698854) i zaloguj się na swoim koncie administratora.

2.  Wybierz pozycję **Dodaj użytkownika**.

3.  Upewnij się, że konto użytkownika, który będzie menedżerem rejestracji urządzeń, jest wyświetlane na liście. Jeśli nie widać tego konta, dodaj użytkownika, wybierając pozycję **Nowy** i wykonując procedurę **Dodawanie użytkownika**. Dla każdego użytkownika uzyskującego dostęp do usługi wymagana jest licencja subskrypcji. Menedżer rejestracji urządzeń nie może być administratorem usługi Intune. Przed rozpoczęciem korzystania z tej funkcji dowiedz się, czy nie trzeba dodać kolejnych licencji.

4.  Zaloguj się do [konsoli administracyjnej usługi Microsoft Intune](http://manage.microsoft.com), korzystając z poświadczeń administratora.

5.  W okienku nawigacji wybierz pozycję **Administrator**, a następnie przejdź do sekcji **Zarządzanie administratorami** i wybierz pozycję **Menedżer rejestracji urządzeń**. Zostanie otwarta strona **Menedżerowie rejestracji urządzeń**.

6.  Wybierz pozycję **Dodaj**. Zostanie otwarte okno dialogowe **Dodawanie menedżera rejestracji urządzeń** .

7.  Wprowadź **identyfikator użytkownika** konta usługi Intune, a następnie wybierz opcję **OK**. Użytkownik konta menedżera rejestracji urządzeń nie może być administratorem usługi Intune.

8.  Menedżer rejestracji urządzeń może teraz rejestrować urządzenia przenośne za pomocą tej samej procedury, której używa użytkownik końcowy w ramach scenariusza „Przynieś własne urządzenie” (BYOD, Bring Your Own Device) w portalu firmy.

## <a name="delete-a-device-enrollment-manager-from-intune"></a>Usuwanie menedżera rejestracji urządzeń z usługi Intune

1.  Zaloguj się do [portalu administracyjnego usługi Microsoft Intune](http://manage.microsoft.com), korzystając z poświadczeń administratora.

2.  W okienku nawigacji wybierz pozycję **Administrator**, a następnie przejdź do sekcji **Zarządzanie administratorami** i wybierz pozycję **Menedżer rejestracji urządzeń**. Zostanie otwarta strona **Menedżerowie rejestracji urządzeń**.

3.  Wybierz **Użytkownika**, którego menedżer rejestracji urządzeń ma zostać usunięty, a następnie wybierz pozycję **Usuń**. Ten użytkownik nie zostanie usunięty z usługi Intune, a zarządzane przez niego urządzenia pozostaną zarejestrowane w usłudze. Usunięcie menedżera rejestracji urządzeń uniemożliwi temu użytkownikowi rejestrację kolejnych urządzeń w usłudze Intune.

4.  Wybierz pozycję **Tak**, aby potwierdzić chęć usunięcia menedżera rejestracji urządzeń.

Usunięcie menedżera rejestracji urządzeń nie ma wpływu na zarejestrowane urządzenia. Gdy menedżer rejestracji urządzeń zostanie usunięty:

-   Nie ma to wpływu na zarejestrowane urządzenia.

-   Zarejestrowane urządzenia będą nadal w pełni zarządzane.

-   Poświadczenia konta usuniętego menedżera rejestracji urządzeń zachowują ważność i można ich nadal używać do logowania się do portalu firmy w celu uzyskiwania dostępu do aplikacji.

-   Używając poświadczeń konta usuniętego menedżera rejestracji urządzeń, nie można jednak czyścić ani wycofywać urządzeń.

-   Powiązanie usuniętego konta menedżera rejestracji urządzeń z zarejestrowanymi urządzeniami zostaje zachowane, ale nie można zarejestrować dodatkowych urządzeń.



<!--HONumber=Nov16_HO1-->


