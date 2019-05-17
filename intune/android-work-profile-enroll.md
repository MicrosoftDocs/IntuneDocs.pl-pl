---
title: Rejestrowanie urządzeń z profilem służbowym systemu Android Enterprise w usłudze Intune
titleSuffix: Microsoft Intune
description: Dowiedz się, jak rejestrować urządzenia z profilem służbowym systemu Android Enterprise w usłudze Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 6/21/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 66574fe66f90b73d8ebf5835c5b16e93276579e4
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2019
ms.locfileid: "59568222"
---
# <a name="set-up-enrollment-of-android-enterprise-work-profile-devices"></a>Konfigurowanie rejestracji urządzeń z profilem służbowym systemu Android Enterprise

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Usługa Intune ułatwia wdrażanie aplikacji i ustawień na urządzeniach z profilem służbowym systemu Android Enterprise, co zapewnia oddzielenie informacji osobistych od służbowych. Aby uzyskać szczegółowe informacje na temat rozwiązania Android Enterprise, zobacz [wymagania dotyczące rozwiązania Android Enterprise](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

Aby skonfigurować zarządzanie profilami służbowymi systemu Android Enterprise, wykonaj następujące kroki:

1. [Połącz swoje konto dzierżawy usługi Intune z kontem rozwiązania Android Enterprise](connect-intune-android-enterprise.md).
2. Określ ustawienia rejestracji profilu służbowego systemu Android Enterprise. Profile służbowe systemu Android Enterprise są [obsługiwane tylko na niektórych urządzeniach z systemem Android](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012%20style=%22target=new_window%22). Każde urządzenie, które obsługuje profile służbowe systemu Android Enterprise, obsługuje także konwencjonalne zarządzanie systemem Android. Usługa Intune pozwala określić, jak w ramach [ograniczeń rejestracji](enrollment-restrictions-set.md) powinny być zarządzane urządzenia, które obsługują profile służbowe systemu Android Enterprise.
    - **Blokuj (ustawienie domyślne)**:  wszystkie urządzenia z systemem Android Enterprise, w tym urządzenia, które obsługują profile służbowe systemu Android, są rejestrowane jako konwencjonalne urządzenia z systemem Android.
    - **Zezwalaj**: wszystkie urządzenia, które obsługują profile służbowe systemu Android Enterprise, są rejestrowane jako urządzenia z profilami służbowymi systemu Android Enterprise. Każde urządzenie z systemem Android, które nie obsługuje profilów służbowych systemu Android Enterprise, zostanie zarejestrowane jako konwencjonalne urządzenie z systemem Android.
3. [Poinformuj użytkowników, jak mogą zarejestrować swoje urządzenia](/intune-user-help/enroll-your-device-in-intune-android).


Jeśli chcesz zarejestrować urządzenia przy użyciu profilów służbowych systemu Android Enterprise, ale zostały one już zarejestrowane jako zwykłe urządzenia z systemem Android, należy najpierw wyrejestrować te urządzenia, a następnie ponownie je zarejestrować.

W przypadku rejestrowania urządzeń z profilami służbowymi systemu Android Enterprise za pomocą konta [menedżera rejestracji urządzeń](device-enrollment-manager-enroll.md) na jednym koncie można zarejestrować maksymalnie 10 urządzeń.

Aby uzyskać więcej informacji, zobacz artykuł [Data Intune sends to Google (Dane wysyłane przez usługę Intune do firmy Google)](data-intune-sends-to-google.md).

## <a name="approve-the-company-portal-app-in-the-managed-google-play-store"></a>Zatwierdzanie aplikacji Portal firmy w zarządzanym sklepie Google Play

Aby zapewnić, że użytkownicy zawsze będą mieć dostęp do najnowszych wersji aplikacji Portal firmy, należy zatwierdzić aplikację Portal firmy dla systemu Android w zarządzanym sklepie Google Play. Dzięki temu każdy użytkownik będzie otrzymywać aktualizacje automatyczne. Jeśli ta aplikacja nie zostanie zatwierdzona, aplikacja Portal firmy po pewnym czasie stanie się nieaktualna i może nie otrzymywać ważnych poprawek błędów i nowych funkcji wydawanych przez firmę Microsoft.

Wykonaj następujące kroki, aby zatwierdzić aplikację Portal firmy usługi Intune:

1.  Przejdź do aplikacji Portal firmy w [zarządzanym sklepie Google Play](https://play.google.com/work/apps/details?id=com.microsoft.windowsintune.companyportal).
2.  Zaloguj się do zarządzanego sklepu Google Play za pomocą tego samego konta, którego użyto do skonfigurowania powiązania na potrzeby systemu Android Enterprise.
3.  Kliknij pozycję **Zatwierdź**, co spowoduje otwarcie nowego okna dialogowego.
4.  Przejrzyj uprawnienia w tym oknie dialogowym, a następnie kliknij przycisk **Zatwierdź**. Jest to konieczne, aby zezwolić na te uprawnienia w celu umożliwienia aplikacji Portal firmy zarządzanie profilem służbowym na urządzeniu.
5.  Wybierz pozycję **Utrzymuj zatwierdzenie, gdy aplikacja żąda nowych uprawnień**, a następnie kliknij przycisk **Zapisz**.

## <a name="next-steps-for-android-enterprise-work-profiles"></a>Kolejne kroki dotyczące profilów służbowych systemu Android Enterprise
- [Deploy Android Enterprise work profile apps](apps-add-android-for-work.md) (Wdrażanie aplikacji z profilami służbowymi systemu Android Enterprise)
- [Add Android Enterprise work profile configuration policies](device-profiles.md) (Dodawanie zasad konfiguracji profilów służbowych systemu Android Enterprise)
