---
title: Rejestrowanie urządzeń przy użyciu konta menedżera rejestracji urządzeń
titleSuffix: Microsoft Intune
description: Użycie konta menedżera rejestracji urządzeń w celu zarejestrowania urządzeń w usłudze Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 7196b33e-d303-4415-ad0b-2ecdb14230fd
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: cbfe0e30794ddfe5b2f089d50456f9cbdd031e6d
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71723323"
---
# <a name="enroll-devices-in-intune-by-using-a-device-enrollment-manager-account"></a>Rejestrowanie urządzeń w usłudze Intune przy użyciu konta menedżera rejestracji urządzeń

Przy użyciu jednego konta usługi Azure Active Directory możesz zarejestrować do 1000 urządzeń przenośnych, korzystając z konta menedżera rejestracji urządzeń (DEM, Device Enrollment Manager). Menedżer DEM to uprawnienie usługi Intune, które można zastosować do konta użytkownika usługi AAD i które umożliwia użytkownikowi zarejestrowanie do 1000 urządzeń. Konto DEM jest przydatne w scenariuszach, w których urządzenia są rejestrowane i przygotowywane przed przekazaniem ich użytkownikom. Zgodnie z projektem w usłudze Microsoft Intune obowiązuje limit 25 kont menedżera rejestracji urządzeń (DEM).

## <a name="limitations-of-devices-that-are-enrolled-with-a-dem-account"></a>Ograniczenia urządzeń zarejestrowanych przy użyciu konta DEM

Konta użytkowników DEM i urządzenia zarejestrowane przy użyciu konta użytkownika DEM mają następujące ograniczenia:

- Do użytkownika konta DEM musi być przypisana licencja usługi Intune.
- Nie można wykonać czyszczenia z poziomu Portalu firmy. Urządzenie zarejestrowane przy użyciu konta użytkownika DEM można wyczyścić z poziomu usługi Intune w witrynie Azure Portal.
- W aplikacji lub witrynie internetowej Portal firmy widoczne jest tylko urządzenie lokalne.
- Konta użytkowników DEM nie mogą używać aplikacji z programu Apple Volume Purchase Program (VPP) z licencjami użytkowników programu VPP ze względu na wymagania dotyczące identyfikatora Apple ID dla poszczególnych użytkowników na potrzeby zarządzania aplikacjami.
- Urządzenia mogą instalować aplikacje VPP, jeśli mają licencje urządzeń programu VPP.
- Dostęp warunkowy w urządzeniach został zablokowany, z wyjątkiem systemu Windows 10 1803+.
- Wszystkie urządzenia zarejestrowane przy użyciu konta DEM muszą mieć odpowiednie licencje, aby można było nimi zarządzać za pomocą usługi Intune. Licencja może być licencją użytkownika usługi Intune lub licencją urządzenia usługi Intune.
- W przypadku [rejestrowania urządzeń z profilami służbowymi systemu Android Enterprise](android-work-profile-enroll.md) za pomocą konta DEM na jednym koncie można zarejestrować maksymalnie 10 urządzeń.


## <a name="add-a-device-enrollment-manager"></a>Dodawanie menedżera rejestracji urządzeń

1. W usłudze [Intune w witrynie Azure Portal](https://aka.ms/intuneportal) wybierz pozycję **Rejestrowanie urządzenia** > **Menedżerowie rejestracji urządzeń**.

2. Wybierz pozycję **Dodaj**.

3. W bloku **Dodaj użytkownika** wprowadź główną nazwę użytkownika dla użytkownika DEM i wybierz pozycję **Dodaj**. Użytkownik DEM zostanie dodany do listy użytkowników DEM.

## <a name="permissions-for-dem"></a>Uprawnienia dla użytkownika DEM

Rola globalnego administratora lub administratora usługi Intune w usłudze Azure AD jest wymagana do:
- przypisania uprawnienia DEM do konta użytkownika usługi Azure AD,
- wyświetlenia wszystkich użytkowników DEM.

Jeśli użytkownik nie ma przypisanej roli administratora globalnego lub administratora usługi Intune, ale ma uprawnienia do odczytu włączone dla przypisanej do siebie roli menedżerów rejestracji urządzeń, może zobaczyć tylko użytkowników DEM utworzonych przez siebie.


## <a name="remove-device-enrollment-manager-permissions"></a>Usuwanie uprawnień menedżera rejestracji urządzeń

Usunięcie menedżera rejestracji urządzeń nie ma wpływu na zarejestrowane urządzenia.

**Usuwanie menedżera rejestracji urządzeń**

1. W usłudze [Intune w witrynie Azure Portal](https://aka.ms/intuneportal) wybierz pozycję **Rejestrowanie urządzenia**, a następnie pozycję **Menedżerowie rejestracji urządzeń**.
2. W bloku **Menedżerowie rejestracji urządzeń** wybierz użytkownika DEM, a następnie wybierz pozycję **Usuń**.

