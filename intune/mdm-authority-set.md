---
title: Ustawianie źródła zarządzania urządzeniem przenośnym
titlesuffix: Microsoft Intune
description: Konfigurowanie urzędu zarządzania urządzeniami przenośnymi w usłudze Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f903e9dfe5fb30f45806aac5694171814492f2e
ms.sourcegitcommit: 0f1a5d6e577915d2d748d681840ca04a0a2604dd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2018
---
# <a name="set-the-mobile-device-management-authority"></a>Ustawianie źródła zarządzania urządzeniem przenośnym

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ustawienie urzędu zarządzania urządzeniami przenośnymi (MDM) określa metodę zarządzania urządzeniami. Jako administrator systemów informatycznych, musisz ustawić urząd MDM, aby użytkownicy mogli zarejestrować urządzenia do zarządzania.

Możliwe są następujące konfiguracje:

- **Autonomiczna usługa Intune** — zarządzanie tylko w chmurze konfigurowane przy użyciu witryny Azure Portal. Ta konfiguracja zawiera pełny zestaw funkcji oferowanych przez usługę Intune. [Ustaw urząd MDM w konsoli usługi Intune](#set-mdm-authority-to-intune).

- **Hybrydowa usługa Intune** — integracja rozwiązania usługi Intune w chmurze z programem System Center Configuration Manager. Konfigurowanie usługi Intune odbywa się przy użyciu konsoli programu Configuration Manager. [Ustaw urząd MDM w programie Configuration Manager](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-intune-subscription).

- **Zarządzanie urządzeniami przenośnymi w usłudze Office 365** — integracja usługi Office 365 z rozwiązaniem usługi Intune w chmurze. Konfigurowanie usługi Intune odbywa się przy użyciu centrum administracyjnego usługi Office 365. Ta konfiguracja zawiera podzbiór możliwości dostępnych w ramach autonomicznej usługi Intune. Ustaw urząd MDM przy użyciu centrum administracyjnego usługi Office 365.

> [!IMPORTANT]
> W programie Configuration Manager w wersji 1610 lub nowszej i w usłudze Microsoft Intune w wersji 1705 można zmienić urząd certyfikacji MDM bez konieczności kontaktowania się Pomocą techniczną firmy Microsoft oraz wyrejestrowywania i ponownego rejestrowania istniejących urządzeń zarządzanych. Szczegółowe informacje można znaleźć w sekcji [Co należy zrobić, jeśli wybrano błędne ustawienie urzędu MDM](/intune-classic/deploy-use/prerequisites-for-enrollment#what-to-do-if-you-choose-the-wrong-mdm-authority-setting).

## <a name="set-mdm-authority-to-intune"></a>Ustawianie urzędu MDM na usługę Intune

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. Wybierz pomarańczowy transparent, aby otworzyć ustawienie **Urząd zarządzania urządzeniami przenośnymi**.
4. W obszarze **Urząd zarządzania urządzeniami przenośnymi** wybierz swój urząd MDM spośród następujących opcji:
   - **Urząd MDM w usłudze Intune**
   - **Urząd MDM w programie Configuration Manager**
   - **Brak**

   ![Zrzut ekranu usługi Intune przeznaczonego do ustawiania urzędu zarządzania urządzeniami przenośnymi](media/set-mdm-auth.png)

   Zostanie wyświetlony komunikat z potwierdzeniem pomyślnego ustawienia urzędu certyfikacji MDM na usługę Intune.

## <a name="enable-device-enrollment"></a>Włączanie rejestracji urządzeń

W przypadku ustawienia usługi Intune jako urzędu MDM użytkownicy mogą rejestrować urządzenia osobiste i uzyskiwać dostęp do zasobów, takich jak poczta e-mail, w opisany poniżej sposób, instalując aplikację Portal firmy (iOS, macOS i Android), dodając poświadczenia służbowe (Windows) lub uzyskując dostęp do witryny internetowej Portal firmy (iOS, Android, macOS).

Różne platformy mają następujące wymagania dotyczące włączania lub upraszczania rejestracji:
- **iOS** — (wymagane) [Uzyskaj certyfikat wypychania MDM firmy Apple](apple-mdm-push-certificate-get.md), a następnie [włącz rejestrowanie urządzeń z systemem iOS należących do firmy](ios-enroll.md) (opcjonalnie).
- **Android** — (opcjonalne) [Włącz profile służbowe w systemie Android](android-enroll.md)
- **Windows** — (opcjonalnie) Włącz [rejestrowanie automatyczne](windows-enroll.md) lub [rejestrowanie zbiorcze](windows-bulk-enroll.md)
- **macOS** — (wymagane) [Uzyskaj certyfikat wypychania MDM firmy Apple](apple-mdm-push-certificate-get.md).

### <a name="workflow-of-intune-administration-ui"></a>Przepływ pracy interfejsu użytkownika administrowania usługą Intune
Gdy zarządzanie urządzeniami firmy Apple i urządzeniami z systemem Android jest włączone, usługa Intune wysyła informacje o urządzeniu i użytkowniku w celu integracji z usługami innych firm i zarządzania urządzeniami.

Dodanie zgody na udostępnianie danych ma miejsce:
- Podczas włączania programu Android for Work.
- Podczas włączania i przekazywania certyfikatów wypychania MDM firmy Apple.
- Podczas włączania dowolnych usługi firmy Apple takich jak Device Enrollment Program, School Manager czy Volume Purchasing Program (program zakupów zbiorczych).

W każdym przypadku zgoda ściśle dotyczy uruchamiania usługi zarządzania urządzeniami przenośnymi. Może to być na przykład potwierdzenie, że administrator IT zezwolił na rejestrację urządzeń firmy Google lub Apple. Dokumentacja opisująca, jakie informacje są udostępniane po wprowadzeniu nowych przepływów pracy, jest dostępna w następujących lokalizacjach:
- [Dane wysyłane przez usługę Intune do firmy Google](https://aka.ms/Data-intune-sends-to-google)
- [Dane wysyłane przez usługę Intune do firmy Apple](https://aka.ms/data-intune-sends-to-apple)

Aby uzyskać więcej informacji na temat zgodności z RODO w produktach firmy Microsoft, zobacz [Trust Center — Assess your GDPR compliance (Centrum zaufania — ocena zgodności z RODO)](https://aka.ms/trust_center_info).

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Czyszczenie urządzenia przenośnego po wygaśnięciu certyfikatu MDM

Certyfikat MDM jest odnawiany automatycznie, gdy urządzenia przenośne komunikują się z usługą Intune. W przypadku wyczyszczenia urządzeń przenośnych lub jeśli przez pewien czas nie komunikują się one z usługą Intune, certyfikat MDM nie zostanie odnowiony. Urządzenie zostanie usunięte z portalu Azure 180 dni po wygaśnięciu certyfikatu MDM.
