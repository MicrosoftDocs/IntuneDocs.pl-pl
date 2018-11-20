---
title: Rejestrowanie urządzeń z profilem służbowym systemu Android w usłudze Intune
titlesuffix: Microsoft Intune
description: Dowiedz się, jak rejestrować urządzenia z profilem służbowym systemu Android w usłudze Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 6/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a38c5db1e608cb5d9a047dc72ee9109e840096e0
ms.sourcegitcommit: 4d5e811d451aeb6307e0f64818e182e471ae1ed4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2018
ms.locfileid: "51618994"
---
# <a name="set-up-enrollment-of-android-work-profile-devices"></a>Konfigurowanie rejestracji urządzeń z profilem służbowym systemu Android

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Usługa Intune ułatwia wdrażanie aplikacji i ustawień na urządzeniach z profilem służbowym systemu Android, co zapewnia oddzielenie informacji osobistych od służbowych. Aby uzyskać szczegółowe informacje na temat rozwiązania Android enterprise, zobacz [wymagania dotyczące rozwiązania Android enterprise](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

Aby skonfigurować zarządzanie profilami służbowymi systemu Android, wykonaj następujące kroki:

1. [Połącz swoje konto dzierżawy usługi Intune z kontem rozwiązania Android enterprise](connect-intune-android-enterprise.md).
2. Określ ustawienia rejestracji profilu służbowego systemu Android. Profile służbowe systemu Android są [obsługiwane tylko na niektórych urządzeniach z systemem Android](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012%20style=%22target=new_window%22). Każde urządzenie, które obsługuje profile służbowe systemu Android, obsługuje także konwencjonalne zarządzanie systemem Android. Usługa Intune pozwala określić, jak w ramach [ograniczeń rejestracji](enrollment-restrictions-set.md) powinny być zarządzane urządzenia, które obsługują profile służbowe systemu Android.
    - **Blokuj (ustawienie domyślne)**: wszystkie urządzenia z systemem Android, w tym urządzenia, które obsługują profile służbowe systemu Android, są rejestrowane jako konwencjonalne urządzenia z systemem Android.
    - **Zezwalaj**: wszystkie urządzenia, które obsługują profile służbowe systemu Android, są rejestrowane jako urządzenia z profilami służbowymi systemu Android. Każde urządzenie z systemem Android, które nie obsługuje profilów służbowych systemu Android, zostanie zarejestrowane jako konwencjonalne urządzenie z systemem Android.
3. [Poinformuj użytkowników, jak mogą zarejestrować swoje urządzenia](/intune-user-help/enroll-your-device-in-intune-android).


Jeśli chcesz zarejestrować urządzenia w ramach profilów służbowych systemu Android, ale zostały one już zarejestrowane jako zwykłe urządzenia z systemem Android, należy najpierw wyrejestrować te urządzenia, a następnie ponownie je zarejestrować.

W przypadku rejestrowania urządzeń z profilami służbowymi systemu Android za pomocą konta [menedżera rejestracji urządzeń](device-enrollment-manager-enroll.md) na jednym koncie można zarejestrować maksymalnie 10 urządzeń.

Aby uzyskać więcej informacji, zobacz artykuł [Data Intune sends to Google (Dane wysyłane przez usługę Intune do firmy Google)](data-intune-sends-to-google.md).

## <a name="approve-the-company-portal-app-in-the-managed-google-play-store"></a>Zatwierdzanie aplikacji Portal firmy w zarządzanym sklepie Google Play

Aby zapewnić, że użytkownicy zawsze będą mieć dostęp do najnowszych wersji aplikacji Portal firmy, należy zatwierdzić aplikację Portal firmy dla systemu Android w zarządzanym sklepie Google Play. Dzięki temu każdy użytkownik będzie otrzymywać aktualizacje automatyczne. Jeśli ta aplikacja nie zostanie zatwierdzona, aplikacja Portal firmy po pewnym czasie stanie się nieaktualna i może nie otrzymywać ważnych poprawek błędów i nowych funkcji wydawanych przez firmę Microsoft.

Wykonaj następujące kroki, aby zatwierdzić aplikację Portal firmy usługi Intune:

1.  Przejdź do aplikacji Portal firmy w [zarządzanym sklepie Google Play](https://play.google.com/work/apps/details?id=com.microsoft.windowsintune.companyportal).
2.  Zaloguj się do zarządzanego sklepu Google Play za pomocą tego samego konta, którego użyto do skonfigurowania powiązania na potrzeby rozwiązania Android enterprise.
3.  Kliknij pozycję **Zatwierdź**, co spowoduje otwarcie nowego okna dialogowego.
4.  Przejrzyj uprawnienia w tym oknie dialogowym, a następnie kliknij przycisk **Zatwierdź**. Jest to konieczne, aby zezwolić na te uprawnienia w celu umożliwienia aplikacji Portal firmy zarządzanie profilem służbowym na urządzeniu.
5.  Wybierz pozycję **Utrzymuj zatwierdzenie, gdy aplikacja żąda nowych uprawnień**, a następnie kliknij przycisk **Zapisz**.

## <a name="next-steps-for-android-work-profiles"></a>Kolejne kroki dotyczące profilów służbowych systemu Android
- [Wdrażanie aplikacji profilu służbowego systemu Android](apps-add-android-for-work.md)
- [Dodawanie zasad konfiguracji profilu służbowego systemu Android](device-profiles.md)
