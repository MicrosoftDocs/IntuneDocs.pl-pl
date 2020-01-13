---
title: Rejestracja administratora urządzeń z systemem Android w usłudze Microsoft Intune
titleSuffix: ''
description: Zarejestruj urządzenia z systemem Android w usłudze Intune przy użyciu rejestracji administratora urządzeń.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/23/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 309860fb5ddf6fa9488ecaf395534bf869234176
ms.sourcegitcommit: a82d25d98fdf0ba766f8f074871d4f13725e23f9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/31/2019
ms.locfileid: "75547856"
---
# <a name="android-device-administrator-enrollment"></a>Rejestracja administratora urządzeń z systemem Android

Administrator urządzeń z systemem Android (czasami określany jako „starszy sposób” zarządzania systemem Android, opublikowany z systemem Android 2.2) to metoda zarządzania urządzeniami z systemem Android. Jednak obecnie jest dostępna ulepszona funkcja zarządzania w systemie [Android Enterprise](https://www.android.com/enterprise/management/) (wydanie z systemem Android 5.0). Dążąc do przejścia do nowoczesnego, bardziej zaawansowanego i bezpieczniejszego zarządzania urządzeniami, firma Google ogranicza wsparcie administratora urządzeń w nowych wersjach systemu Android.

W związku z tym, aby uniknąć takiej ograniczonej funkcjonalności, zalecamy, by nie rejestrować nowych urządzeń przy użyciu procesu administratora urządzeń opisanego poniżej.

Z tych samych powodów zaleca się również migrowanie urządzeń poza zarządzanie przez administratora urządzeń, jeśli urządzenia mają zostać zaktualizowane do systemu Android 10. 

Aby uzyskać więcej informacji na temat obsługi usługi Intune na potrzeby obsługi administratora urządzeń z systemem Android, zobacz [sekcję Powiadomienia](../fundamentals/whats-new.md#decreasing-support-for-android-device-administrator).

Jeśli mimo to decydujesz, aby użytkownicy rejestrowali swoje urządzenia z systemem Android za pomocą zarządzania przez administratora urządzeń, przejdź do następnej sekcji.  


> [!Note]  
> System Android 10 i jego nowsze wersje nie będą obsługiwane w ramach hybrydowego zarządzania urządzeniami przenośnymi (hybrydowe rozwiązanie MDM; usługa Intune zarządzana za pomocą konsoli Configuration Manager), ponieważ hybrydowe rozwiązanie MDM zostanie wycofane 1 września 2019 r. Jeśli nadal używasz hybrydowego rozwiązania MDM, musisz jak najszybciej przeprowadzić migrację do autonomicznej usługi Intune. Skontaktuj się z pomocą techniczną, jeśli potrzebujesz pomocy w zakresie migracji. Aby uzyskać więcej informacji, zobacz [Move from Hybrid Mobile Device Management to Intune on Azure](https://aka.ms/hybrid_notification) (Przechodzenie z hybrydowego zarządzania urządzeniami przenośnymi do usługi Intune na platformie Azure).

Aby uzyskać więcej informacji na temat funkcji systemu Android Enterprise firmy Google, zobacz następujące materiały:
- [Wskazówki firmy Google dotyczące migracji z zarzadzania przez administratora urządzeń do systemu Android Enterprise](http://static.googleusercontent.com/media/android.com/en/enterprise/static/2016/pdfs/enterprise/Android-Enterprise-Migration-Bluebook_2019.pdf)
- [Dokumentacja firmy Google dotycząca planu wycofania interfejsu API administratora urządzeń](https://developers.google.com/android/work/device-admin-deprecation)


## <a name="set-up-device-administrator-enrollment"></a>Konfiguracja rejestracji administratora urządzeń

1. Aby przygotować się do zarządzania urządzeniami przenośnymi, należy ustawić urząd zarządzania urządzeniami przenośnymi (MDM) na wartość **Microsoft Intune**. Instrukcje znajdują się w artykule [Ustawianie urzędu MDM](../fundamentals/mdm-authority-set.md). Element ten ustawia się tylko raz podczas pierwszej konfiguracji usługi Intune do zarządzania urządzeniami przenośnymi.
2. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) i wybierz kolejno pozycje **Urządzenia** > **Android** > **Rejestracja systemu Android** > **Urządzenia prywatne i należące do firmy z uprawnieniami do administrowania urządzeniami** > **Zarządzaj urządzeniami za pomocą administratora urządzeń**.
3. [Poinformuj użytkowników, jak mogą zarejestrować swoje urządzenia](/intune-user-help/enroll-your-device-in-intune-android).  

Po wykonaniu rejestracji przez użytkownika można zacząć zarządzać jego urządzeniami w usłudze Intune, w tym [przypisywać zasady zgodności](../protect/compliance-policy-create-android.md), [zarządzać aplikacjami](../apps/app-management.md) i nie tylko.

Aby uzyskać informacje o innych zadaniach użytkowników, zobacz następujące artykuły:
- [Zasoby dotyczące środowiska użytkownika końcowego w usłudze Microsoft Intune](../fundamentals/end-user-educate.md)
- [Korzystanie z urządzenia z systemem Android i usługi Intune](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)


## <a name="block-device-administrator-enrollment"></a>Blokowanie rejestracji administratora urządzeń
Aby zablokować rejestrowanie urządzeń administratora urządzeń z systemem Android lub tylko urządzeń administratora urządzeń z systemem Android będących własnością użytkowników, zobacz temat [Ustawianie ograniczeń typu urządzeń](enrollment-restrictions-set.md).



## <a name="next-steps"></a>Następne kroki
- [Przypisywanie zasad zgodności](../protect/compliance-policy-create-android.md)
- [Zarządzanie aplikacjami](../apps/app-management.md)
