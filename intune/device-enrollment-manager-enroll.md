---
title: "Rejestrowanie urządzeń przy użyciu menedżera rejestracji urządzeń"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: korzystanie z konta menedżera rejestracji urządzeń w celu rejestrowania urządzeń w usłudze Intune. "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7196b33e-d303-4415-ad0b-2ecdb14230fd
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: aded0826c2628e4dc72859387fbe4a76d683db9e
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017

---

# <a name="enroll-devices-using-device-enrollment-manager"></a>Rejestrowanie urządzeń przy użyciu menedżera rejestracji urządzeń

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Organizacje mogą używać usługi Intune do zarządzania dużą liczbą urządzeń przenośnych za pomocą jednego konta użytkownika. Konto *menedżera rejestracji urządzeń* (DEM, ang. Device Enrollment Manager) jest specjalnym kontem użytkownika umożliwiającym rejestrację do 1000 urządzeń. Istniejących użytkowników dodaje się do konta menedżera rejestracji urządzeń w celu nadania im szczególnych możliwości związanych z tym kontem. Każde zarejestrowane urządzenie używa jednej licencji. Zalecamy używanie urządzeń zarejestrowanych przy użyciu tego konta jako urządzeń udostępnionych, a nie urządzeń osobistych („BYOD”).  

Aby było możliwe dodanie użytkowników jako menedżerów rejestracji urządzeń, muszą oni istnieć w witrynie Azure Portal. Aby możliwe było zapewnienie optymalnego poziomu bezpieczeństwa, użytkownik DEM nie powinien być jednocześnie administratorem usługi Intune.

>[!NOTE]
>Nie można używać metody rejestracji DEM w połączeniu z następującymi innymi metodami rejestracji: [program Apple Configurator z Asystentem ustawień](apple-configurator-setup-assistant-enroll-ios.md), [program Apple Configurator z bezpośrednią rejestracją](apple-configurator-direct-enroll-ios.md) i [program rejestracji urządzeń](device-enrollment-program-enroll-ios.md). 

## <a name="example-of-a-device-enrollment-manager-scenario"></a>Przykład scenariusza menedżera rejestracji urządzeń

Restauracja potrzebuje 50 tabletów do punktów sprzedaży dla swoich kelnerów oraz monitorów zamówień dla personelu w kuchni. Pracownicy nigdy nie muszą uzyskiwać dostępu do danych firmowych ani logować się jako użytkownicy. Administrator usługi Intune tworzy konto menedżera rejestracji urządzeń i dodaje do niego kierownika restauracji, dając tym samym kierownikowi restauracji możliwości konta DEM. Kierownik może teraz zarejestrować 50 tabletów przy użyciu poświadczeń DEM.

Menedżerami rejestracji urządzeń mogą być tylko użytkownicy w konsoli usługi Intune. Użytkownik konta menedżera rejestracji urządzeń nie może być administratorem usługi Intune.

Użytkownik DEM ma następujące uprawnienia:

-   Rejestrowanie do 1000 urządzeń w usłudze Intune.
-   Logowanie się w Portalu firmy w celu pobierania aplikacji firmowych.
-   Konfigurowanie dostępu do danych firmy poprzez wdrażanie na tabletach aplikacji powiązanych z funkcjami pełnionymi przez ich użytkowników.

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

1.  W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.

2.  W bloku Intune wybierz pozycję **Zarejestruj urządzenia**, a następnie wybierz pozycję **Menedżerowie rejestracji urządzeń**.

3.  Wybierz pozycję **Dodaj**.

4.  W bloku **Dodaj użytkownika** wprowadź główną nazwę użytkownika dla użytkownika DEM i wybierz pozycję **Dodaj**. Użytkownik DEM zostanie dodany do listy użytkowników DEM.

## <a name="remove-a-device-enrollment-manager"></a>Usuwanie menedżera rejestracji urządzeń

Usunięcie menedżera rejestracji urządzeń nie ma wpływu na zarejestrowane urządzenia. Gdy menedżer rejestracji urządzeń zostanie usunięty:

-   Usunięcie użytkownika z listy użytkowników DEM nie ma wpływu na zarejestrowane urządzenia — będą one nadal w pełni zarządzane.

-   Poświadczenia konta usuniętego menedżera rejestracji urządzeń zachowają ważność.

-   Używając usuniętego menedżera rejestracji urządzeń, nie można jednak czyścić ani wycofywać urządzeń.

-   Usunięty menedżer rejestracji urządzeń nie umożliwia rejestrowania dodatkowych urządzeń, dopóki nie zostanie osiągnięty limit na urządzenie skonfigurowany przez administratora usługi Intune.

**Usuwanie menedżera rejestracji urządzeń**

1. W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.

2. W bloku Intune wybierz pozycję **Zarejestruj urządzenia**, a następnie wybierz pozycję **Menedżerowie rejestracji urządzeń**.

3. W bloku **Menedżerowie rejestracji urządzeń** kliknij prawym przyciskiem myszy użytkownika DEM, a następnie wybierz pozycję **Usuń**.

## <a name="view-the-properties-of-a-device-enrollment-manager"></a>Wyświetlanie właściwości menedżera rejestracji urządzeń

1. W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.

2. W bloku Intune wybierz pozycję **Zarejestruj urządzenia**, a następnie wybierz pozycję **Menedżerowie rejestracji urządzeń**.

3. W bloku **Menedżerowie rejestracji urządzeń** kliknij prawym przyciskiem myszy użytkownika DEM, a następnie wybierz pozycję **Właściwości**.

