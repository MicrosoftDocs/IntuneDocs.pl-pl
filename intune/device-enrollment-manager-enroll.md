---
title: Rejestrowanie urządzeń przy użyciu konta menedżera rejestracji urządzeń
titlesuffix: Microsoft Intune
description: Użycie konta menedżera rejestracji urządzeń w celu zarejestrowania urządzeń w usłudze Intune. "
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 7196b33e-d303-4415-ad0b-2ecdb14230fd
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 870d61cce47132b19b4c3d8b7357f84a21a443e4
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="enroll-devices-by-using-a-device-enrollment-manager-account"></a>Rejestrowanie urządzeń przy użyciu konta menedżera rejestracji urządzeń

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Organizacje mogą używać usługi Intune do zarządzania dużą liczbą urządzeń przenośnych za pomocą jednego konta użytkownika. Konto *menedżera rejestracji urządzeń* (DEM, ang. Device Enrollment Manager) jest specjalnym kontem użytkownika umożliwiającym rejestrację do 1000 urządzeń. Istniejących użytkowników dodaje się do konta menedżera rejestracji urządzeń w celu nadania im szczególnych możliwości związanych z tym kontem. Każde zarejestrowane urządzenie używa jednej licencji. Zalecamy używanie urządzeń zarejestrowanych przy użyciu tego konta jako urządzeń udostępnionych, a nie urządzeń osobistych („BYOD”).  

Aby było możliwe dodanie użytkowników jako menedżerów rejestracji urządzeń, muszą oni istnieć w witrynie [Azure Portal](https://portal.azure.com). Aby możliwe było zapewnienie optymalnego poziomu bezpieczeństwa, użytkownik DEM nie powinien być jednocześnie administratorem usługi Intune.

>[!NOTE]
>Metody rejestracji przez użytkownika DEM nie można używać w połączeniu z następującymi innymi metodami rejestracji: [program Apple Configurator z Asystentem ustawień](apple-configurator-setup-assistant-enroll-ios.md), [program Apple Configurator z bezpośrednią rejestracją](apple-configurator-direct-enroll-ios.md), [program Apple School Manager (ASM)](apple-school-manager-set-up-ios.md) i [Device Enrollment Program (DEP)](device-enrollment-program-enroll-ios.md).

## <a name="example-of-a-device-enrollment-manager-scenario"></a>Przykład scenariusza menedżera rejestracji urządzeń

Restauracja potrzebuje 50 tabletów do punktów sprzedaży dla swoich kelnerów oraz monitorów zamówień dla personelu w kuchni. Pracownicy nigdy nie muszą uzyskiwać dostępu do danych firmowych ani logować się jako użytkownicy. Administrator usługi Intune tworzy konto menedżera rejestracji urządzeń i dodaje do niego kierownika restauracji. W efekcie kierownik ma teraz możliwości konta DEM. Kierownik może teraz zarejestrować 50 tabletów przy użyciu poświadczeń DEM.

Menedżerami rejestracji urządzeń mogą być tylko użytkownicy w witrynie [Azure Portal](https://portal.azure.com). Użytkownik konta menedżera rejestracji urządzeń nie może być administratorem usługi Intune.

Użytkownik DEM ma następujące uprawnienia:

-   Rejestrowanie do 1000 urządzeń w usłudze Intune
-   Logowanie się w Portalu firmy w celu pobierania aplikacji firmowych
-   Konfigurowanie dostępu do danych firmy przez wdrożenie na tabletach aplikacji powiązanych z funkcjami pełnionymi przez ich użytkowników

## <a name="limitations-of-devices-that-are-enrolled-with-a-dem-account"></a>Ograniczenia urządzeń zarejestrowanych przy użyciu konta DEM

Urządzenia zarejestrowane przy użyciu konta menedżera rejestracji urządzeń mają następujące ograniczenia:

  - Brak dostępu do poszczególnych użytkowników. Ponieważ urządzenia nie mają przypisanych użytkowników, urządzenie nie ma dostępu do poczty e-mail ani danych firmowych. Można jednak skorzystać na przykład z konfiguracji sieci VPN, dzięki czemu aplikacje urządzenia otrzymają dostęp do danych.
  - Użytkownik DEM nie może wyrejestrować zarejestrowanych z użyciem konta DEM urządzeń z poziomu samych urządzeń, korzystając z Portalu firmy. Administrator usługi Intune może wykonać wyrejestrowanie.
  - W aplikacji lub witrynie internetowej Portal firmy widoczne jest tylko urządzenie lokalne.
  - Użytkownicy nie mogą używać aplikacji z programu Apple Volume Purchase Program (VPP) z licencjami użytkowników ze względu na wymagania dotyczące identyfikatora Apple ID dla poszczególnych użytkowników na potrzeby zarządzania aplikacjami.
  - (Dotyczy tylko systemu iOS) Jeśli do celów rejestrowania urządzeń z systemem iOS zostanie użyta metoda DEM, nie będzie można użyć do rejestrowania urządzeń programu Apple Configurator, programu Device Enrollment Program (DEP) firmy Apple ani programu Apple School Manager (ASM).
  - (Tylko system Android) Istnieje ograniczenie dotyczące liczby urządzeń z programem Android for Work, które mogą być rejestrowane za pomocą jednego konta menedżera rejestracji urządzeń. Na jednym koncie menedżera rejestracji urządzeń może być zarejestrowane maksymalnie 10 urządzeń z systemem Android z profilem służbowym. To ograniczenie nie dotyczy starszych rejestracji systemu Android.
  - Urządzenia mogą instalować aplikacje VPP, jeśli mają licencje urządzeń.
  - Każde urządzenie wymaga licencji urządzenia. Dowiedz się więcej o [licencjach użytkowników i urządzeń](licenses-assign.md#how-user-and-device-licenses-affect-access-to-services).


> [!NOTE]
> Aplikacje firmy można wdrażać na urządzeniach, które są zarządzane przez menedżera rejestracji urządzeń. Wdróż aplikację Portal firmy jako **wymaganą instalację** na koncie użytkownika menedżera rejestracji urządzeń.
> Aby zwiększyć wydajność, podczas wyświetlania aplikacji Portal firmy na urządzeniu DEM pokazywane jest tylko urządzenie lokalne. Zdalne zarządzanie innymi urządzeniami menedżera rejestracji urządzeń jest możliwe wyłącznie za pomocą konsoli administracyjnej usługi Intune.


## <a name="add-a-device-enrollment-manager"></a>Dodawanie menedżera rejestracji urządzeń

1.  W usłudze [Intune w witrynie Azure Portal](https://aka.ms/intuneportal) wybierz pozycję **Rejestrowanie urządzenia** > **Menedżerowie rejestracji urządzeń**.

2.  Wybierz pozycję **Dodaj**.

3.  W bloku **Dodaj użytkownika** wprowadź główną nazwę użytkownika dla użytkownika DEM i wybierz pozycję **Dodaj**. Użytkownik DEM zostanie dodany do listy użytkowników DEM.

## <a name="permissions-for-dem"></a>Uprawnienia dla użytkownika DEM

Do wykonywania zadań rejestracji menedżera rejestracji urządzeń wymagana jest rola globalnego administratora lub administratora usługi Intune w usłudze Azure AD. Role te są również wymagane, aby wyświetlić wszystkich użytkowników DEM, niezależnie od uprawnień RBAC wymienionych i dostępnych w ramach niestandardowej roli użytkownika. Użytkownik bez przypisanej roli administratora globalnego lub administratora usługi Intune, który ma uprawnienia do odczytu dla roli menedżerów rejestracji urządzeń, może zobaczyć tylko użytkowników DEM utworzonych przez siebie. Obsługa kontroli dostępu na podstawie ról w odniesieniu do tych funkcji zostanie ogłoszona w przyszłości.

Jeśli użytkownik nie ma przypisanej roli administratora globalnego lub administratora usługi Intune, ale ma uprawnienia do odczytu włączone dla przypisanej do siebie roli menedżerów rejestracji urządzeń, może zobaczyć tylko użytkowników DEM utworzonych przez siebie.

## <a name="remove-a-device-enrollment-manager"></a>Usuwanie menedżera rejestracji urządzeń

Usunięcie menedżera rejestracji urządzeń nie ma wpływu na zarejestrowane urządzenia. Gdy menedżer rejestracji urządzeń zostanie usunięty:

-   Nie ma to wpływu na zarejestrowane urządzenia, które będą nadal w pełni zarządzane.
-   Poświadczenia konta usuniętego menedżera rejestracji urządzeń zachowają ważność.
-   Używając usuniętego menedżera rejestracji urządzeń, nie można jednak czyścić ani wycofywać urządzeń.
-   Usunięty menedżer rejestracji urządzeń może zarejestrować tylko taką liczbę urządzeń, która nie przekracza limitu na użytkownika skonfigurowanego przez administratora usługi Intune.

**Usuwanie menedżera rejestracji urządzeń**

1. W usłudze [Intune w witrynie Azure Portal](https://aka.ms/intuneportal) wybierz pozycję **Rejestrowanie urządzenia**, a następnie pozycję **Menedżerowie rejestracji urządzeń**.
2. W bloku **Menedżerowie rejestracji urządzeń** wybierz użytkownika DEM, a następnie wybierz pozycję **Usuń**.

## <a name="view-the-properties-of-a-device-enrollment-manager"></a>Wyświetlanie właściwości menedżera rejestracji urządzeń

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Rejestrowanie urządzenia**, a następnie pozycję **Menedżerowie rejestracji urządzeń**.
2. W bloku **Menedżerowie rejestracji urządzeń** kliknij prawym przyciskiem myszy użytkownika DEM, a następnie wybierz pozycję **Właściwości**.
