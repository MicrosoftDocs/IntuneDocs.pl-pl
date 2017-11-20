---
title: "Ustawianie ograniczeń rejestracji w usłudze Intune"
titlesuffix: Azure portal
description: "Ograniczanie rejestrowania według platformy i ustawianie limitu rejestracji urządzeń w usłudze Intune. \""
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 11/6/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 463278e4dc9ad677f654754d4710b110b376cc2d
ms.sourcegitcommit: 5279a0bb8c5aef79aa57aa247ad95888ffe5a12b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/08/2017
---
# <a name="set-enrollment-restrictions"></a>Ustawianie ograniczeń rejestracji

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Jako administrator usługi Intune możesz określić, które urządzenia mogą być rejestrowane w celu zarządzania za pomocą usługi Intune. Użyj witryny Azure Portal, aby ustawić następujące ograniczenia dotyczące rejestrowania urządzeń:

- Maksymalna liczba zarejestrowanych urządzeń
- Platformy urządzeń, które można zarejestrować:
  - Android
  - iOS
  - macOS
  - Windows
- Wersja systemu operacyjnego platformy dla systemu iOS, Android i Windows (mogą być używane tylko wersje systemu Windows 10, pozostaw to pole puste, jeśli dozwolony jest system Windows 8.1)
  - Minimalna wersja
  - Maksymalna wersja
- Ograniczenia urządzeń prywatnych (tylko z systemem iOS, Android i macOS)

>[!NOTE]
>Ograniczenia rejestrowania nie są funkcjami zabezpieczeń. Urządzenia, na których złamano zabezpieczenia, mogą błędnie podawać swój charakter. Te ograniczenia stanowią optymalną barierę dla niezłośliwych użytkowników.

## <a name="set-device-type-restrictions"></a>Ustawianie ograniczeń typu urządzeń
Domyślnie ograniczenia rejestrowania mają zastosowanie do wszystkich użytkowników i rejestracji bez użytkowników.
1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. Wybierz kolejno opcje **Rejestrowanie urządzenia** > **Ograniczenia rejestracji**.
4. W obszarze **Ograniczenia rejestracji** > **Ograniczenia typów urządzeń** wybierz pozycję **Domyślne**.
5. W obszarze **Wszyscy użytkownicy** wybierz pozycję **Platformy**. Wybierz pozycję **Zezwalaj** lub **Blokuj** dla każdej platformy:
  - **Android**
  - **iOS**
  - **macOS**
  - **Windows**

  Kliknij polecenie **Zapisz**.
6. W obszarze **Wszyscy użytkownicy** wybierz pozycję **Konfiguracje platformy** i wybierz następujące konfiguracje. Dla każdej dozwolonej platformy możesz skonfigurować następujące opcje:
  - **Wersje** — określ **minimalną** i **maksymalną** wersję systemu operacyjnego platformy dla urządzeń z systemem Android, iOS lub Windows. System Android obsługuje wersję major.minor.rev.build. System iOS obsługuje wersję major.minor.rev. System Windows obsługuje tylko major.minor.rev.build dla systemu Windows 10. Wersje systemu operacyjnego nie mają zastosowania do urządzeń firmy Apple rejestrowanych przy użyciu programu Device Enrollment Program, Apple School Manager lub aplikacji Apple Configurator. 
  - **Własność użytkownika** — określ, czy **zezwalać**, czy **blokować** urządzenia z systemami Android, iOS i macOS.
  ![Zrzut ekranu przedstawiający obszar roboczy ograniczania urządzeń z domyślnymi konfiguracjami platformy urządzeń i widocznymi skonfigurowanymi ustawieniami urządzeń będących własnością użytkownika.](media/device-restrictions-platform-configurations.png)
  Kliknij polecenie **Zapisz**.

>[!NOTE]
>Jeśli zablokujesz rejestrację prywatnych urządzeń z systemem Android, urządzenia z programem Android for Work nadal będą mogły być rejestrowane.

## <a name="set-device-limit-restrictions"></a>Ustawianie ograniczeń limitu urządzeń
Domyślnie ograniczenia rejestrowania mają zastosowanie do wszystkich użytkowników.
1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. Wybierz kolejno opcje **Rejestrowanie urządzenia** > **Ograniczenia rejestracji**.
4. W witrynie Azure Portal wybierz pozycję **Rejestrowanie urządzenia**, a następnie pozycję **Ograniczenia rejestracji**.
5. Wybierz pozycję **Ograniczenia rejestracji** > **Ograniczenia limitu urządzeń**.
6. W obszarze **Wszyscy użytkownicy** wybierz pozycję **Limit urządzeń**. Określ maksymalną liczbę zarejestrowanych urządzeń na użytkownika.  
![Zrzut ekranu przedstawiający blok ograniczeń dotyczących limitu liczby urządzeń z ograniczeniami limitu liczby urządzeń.](./media/device-restrictions-limit.png)

  Kliknij polecenie **Zapisz**.
