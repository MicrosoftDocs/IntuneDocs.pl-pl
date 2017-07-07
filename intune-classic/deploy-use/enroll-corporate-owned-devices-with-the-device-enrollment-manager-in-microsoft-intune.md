---
title: "Rejestrowanie przy użyciu menedżera rejestracji urządzeń"
description: "Za pomocą konta menedżera rejestracji urządzeń można zarządzać dużą liczbą współdzielonych firmowych urządzeń przenośnych za pomocą jednego konta użytkownika."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 01/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a23abc61-69ed-44f1-9b71-b86aefc6ba03
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 095b89d1428d6b8f06143043d8bb6ed37fd8fa5b
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2017
---
# <a name="enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune"></a>Rejestrowanie urządzeń należących do firmy przy użyciu menedżera rejestracji urządzeń w usłudze Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Organizacje mogą używać usługi Intune do zarządzania dużą liczbą urządzeń przenośnych za pomocą jednego konta użytkownika. Konto *menedżera rejestracji urządzeń* (DEM, ang. Device Enrollment Manager) jest specjalnym kontem użytkownika umożliwiającym rejestrację do 1000 urządzeń. Istniejących użytkowników dodaje się do konta menedżera rejestracji urządzeń w celu nadania im szczególnych możliwości związanych z tym kontem. Każde zarejestrowane urządzenie używa jednej licencji. Zalecamy używanie urządzeń zarejestrowanych przy użyciu tego konta jako urządzeń udostępnionych (czyli bez koligacji użytkownika), a nie jako urządzeń osobistych („BYOD”).  

Aby było możliwe dodanie użytkowników jako menedżerów rejestracji urządzeń, muszą oni istnieć w witrynie Azure Portal. Aby możliwe było zapewnienie optymalnego poziomu bezpieczeństwa, użytkownik DEM nie powinien być jednocześnie administratorem usługi Intune.

>[!NOTE]
>Metoda rejestracji za pomocą menedżera rejestracji urządzeń nie może być używana razem z [metodą rejestracji za pośrednictwem asystenta ustawień programu Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md) bądź [metodą rejestracji bezpośredniej](ios-direct-enrollment-in-microsoft-intune.md) ani z [metodą rejestracji za pomocą programu Device Enrollment Program](ios-device-enrollment-program-in-microsoft-intune.md).

## <a name="example-of-a-device-enrollment-manager-scenario"></a>Przykład scenariusza menedżera rejestracji urządzeń

Restauracja potrzebuje 50 tabletów do punktów sprzedaży dla swoich kelnerów oraz monitorów zamówień dla personelu w kuchni. Pracownicy nigdy nie muszą uzyskiwać dostępu do danych firmowych ani logować się jako użytkownicy. Administrator usługi Intune tworzy konto menedżera rejestracji urządzeń i dodaje do niego kierownika restauracji, dając tym samym kierownikowi restauracji możliwości konta DEM. Kierownik może teraz zarejestrować 50 tabletów przy użyciu poświadczeń DEM.

Menedżerami rejestracji urządzeń mogą być tylko użytkownicy w konsoli usługi Intune. Użytkownik konta menedżera rejestracji urządzeń nie może być administratorem usługi Intune.

Użytkownik DEM ma następujące uprawnienia:

-   Rejestrowanie do 1000 urządzeń w usłudze Intune
-   Uzyskiwanie aplikacji firmowych przy użyciu aplikacji Portal firmy
-   Konfigurowanie dostępu do danych firmy przez wdrożenie na tabletach aplikacji powiązanych z funkcjami pełnionymi przez ich użytkowników

## <a name="limitations-of-devices-that-are-enrolled-with-a-dem-account"></a>Ograniczenia urządzeń zarejestrowanych przy użyciu konta DEM

Urządzenia zarejestrowane przy użyciu konta menedżera rejestracji urządzeń mają następujące ograniczenia:

  - Nie ma konkretnego „użytkownika” urządzenia. Powyższe uwarunkowanie skutkuje brakiem dostępu do wiadomości e-mail i danych firmy. Można jednak skorzystać na przykład z sieci VPN, dzięki czemu aplikacje urządzenia otrzymają dostęp do danych.

  - Brak możliwości dostępu warunkowego, przewidzianego w scenariuszach dla poszczególnych użytkowników.

  - Użytkownik DEM nie może wyrejestrować zarejestrowanych z użyciem konta DEM urządzeń z poziomu samych urządzeń, korzystając z Portalu firmy. Tę możliwość ma administrator usługi Intune, nie ma jej jednak użytkownik DEM.

  - W aplikacji lub witrynie internetowej Portal firmy widoczne jest tylko urządzenie lokalne.

  - Użytkownicy nie mogą używać aplikacji z programu zakupów zbiorczych VPP (ang. Volume Purchase Program) firmy Apple ze względu na wymagania dotyczące identyfikatora Apple ID dla poszczególnych użytkowników na potrzeby zarządzania aplikacjami.

  - (Dotyczy tylko systemu iOS) Jeśli do celów rejestrowania urządzeń z systemem iOS zostanie użyty menedżer rejestracji urządzeń, nie będzie można użyć do rejestrowania urządzeń programu Apple Configurator ani programu Device Enrollment Program (DEP) firmy Apple.

> [!NOTE]
> Aby wdrożyć firmowe aplikacje na urządzeniach zarządzanych przy użyciu menedżera rejestracji urządzeń, wdróż aplikację Portal firmy jako **wymaganą instalację** na koncie użytkownika menedżera rejestracji urządzeń.
> Aby zwiększyć wydajność, podczas wyświetlania aplikacji Portal firmy na urządzeniu DEM pokazywane jest tylko urządzenie lokalne. Zdalne zarządzanie innymi urządzeniami menedżera rejestracji urządzeń jest możliwe wyłącznie za pomocą konsoli administracyjnej usługi Intune.


## <a name="add-a-device-enrollment-manager"></a>Dodawanie menedżera rejestracji urządzeń

1.  Upewnij się, że użytkownik, którego chcesz dodać do konta DEM, już istnieje. Aby dodać użytkownika, zaloguj się do [portalu usługi Office 365](https://go.microsoft.com/fwlink/p/?LinkId=698854) i wykonaj instrukcje zawarte w temacie [Pojedyncze lub zbiorcze dodawanie użytkowników do usługi Office 365](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).

2.  Zaloguj się do [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com), korzystając z poświadczeń administratora.

3.  W okienku nawigacji wybierz pozycję **Administrator**, a następnie przejdź do sekcji **Zarządzanie administratorami** i wybierz pozycję **Menedżer rejestracji urządzeń**. Zostanie otwarta strona **Menedżerowie rejestracji urządzeń**.

4.  Wybierz pozycję **Dodaj**. Zostanie otwarte okno dialogowe **Dodawanie menedżera rejestracji urządzeń** .

5.  Wprowadź **identyfikator użytkownika** konta usługi Intune, a następnie wybierz opcję **OK**.

    Użytkownik DEM może teraz rejestrować urządzenia przenośne za pomocą tej samej procedury, której używa użytkownik końcowy w ramach scenariusza „Przynieś własne urządzenie” (BYOD, Bring Your Own Device) w Portalu firmy. Użytkownik końcowy menedżera może zainstalować aplikację Portal firmy i zarejestrować urządzenie, używając jego poświadczeń menedżera rejestrowania urządzeń dla maksymalnie 1000 urządzeń. Instrukcje dotyczące rejestrowania przez użytkownika końcowego odnoszące się do poszczególnych platform znajdują się w tematach:

  - [Rejestrowanie urządzenia z systemem iOS w usłudze Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios)
  - [Rejestrowanie urządzenia z systemem macOS w usłudze Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos)
  - [Rejestrowanie urządzenia z systemem Android w usłudze Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android)
  - [Rejestrowanie urządzenia z systemem Windows w usłudze Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows)

## <a name="delete-a-device-enrollment-manager-from-intune"></a>Usuwanie menedżera rejestracji urządzeń z usługi Intune

1.  Zaloguj się do [portalu administracyjnego usługi Microsoft Intune](https://manage.microsoft.com), korzystając z poświadczeń administratora.

2.  W okienku nawigacji wybierz pozycję **Administrator**, a następnie przejdź do sekcji **Zarządzanie administratorami** i wybierz pozycję **Menedżer rejestracji urządzeń**. Zostanie otwarta strona **Menedżerowie rejestracji urządzeń**.

3.  Wybierz **Użytkownika**, którego menedżer rejestracji urządzeń ma zostać usunięty, a następnie wybierz pozycję **Usuń**. Ten użytkownik nie zostanie usunięty z usługi Intune, a zarządzane przez niego urządzenia pozostaną zarejestrowane w usłudze. Usunięcie menedżera rejestracji urządzeń uniemożliwi temu użytkownikowi rejestrację kolejnych urządzeń w usłudze Intune.

4.  Wybierz pozycję **Tak**, aby potwierdzić chęć usunięcia menedżera rejestracji urządzeń.

Usunięcie menedżera rejestracji urządzeń nie ma wpływu na zarejestrowane urządzenia. Gdy menedżer rejestracji urządzeń zostanie usunięty:

-   Nie ma to wpływu na zarejestrowane urządzenia.

-   Zarejestrowane urządzenia będą nadal w pełni zarządzane.

-   Poświadczenia konta usuniętego menedżera rejestracji urządzeń zachowują ważność i można ich nadal używać do logowania się do portalu firmy w celu uzyskiwania dostępu do aplikacji.

-   Używając poświadczeń konta usuniętego menedżera rejestracji urządzeń, nie można jednak czyścić ani wycofywać urządzeń.

-   Powiązanie usuniętego konta menedżera rejestracji urządzeń z zarejestrowanymi urządzeniami zostaje zachowane, ale nie można zarejestrować dodatkowych urządzeń.
