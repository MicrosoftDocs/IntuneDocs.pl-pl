---
title: "Stosowanie zasad zgodności do urządzeń zarządzanych za pomocą narzędzia Jamf"
titlesuffix: Azure portal
description: "Wykorzystaj zgodność w celu ułatwienia zabezpieczania urządzeń zarządzanych za pomocą narzędzia Jamf."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c87fd2bd-7f53-4f1b-b985-c34f2d85a7bc
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dd84812a7e7dcf83f01c8d4d2b613706f7700775
ms.sourcegitcommit: b2a6678a0e9617f94ee8c65e7981211483b30ee7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/22/2017
---
# <a name="enforce-compliance-on-macs-managed-with-jamf-pro"></a>Wymuszanie zgodności na urządzeniach Mac zarządzanych za pomocą narzędzia Jamf Pro

|Dotyczy: usługa Intune w witrynie Azure Portal |
|--|
|Szukasz dokumentacji dotyczącej usługi Intune w portalu klasycznym? [Przejdź tutaj](/intune/introduction-intune?toc=/intune-classic/toc.json).|
| |

|Aktualnie w prywatnej wersji zapoznawczej|
|--|
|Funkcje opisane w tym temacie są aktualnie dostępne jedynie dla klientów prywatnej wersji zapoznawczej. Ten komunikat zostanie usunięty po udostępnieniu funkcji wszystkim klientom.|
| |

W celu zapewnienia, że użytkownicy końcowi spełniają wymagania obowiązujące w organizacji, można wykorzystać usługę Azure Active Directory i zasady dostępu warunkowego usługi Microsoft Intune. Te zasady można stosować na komputerach Mac, które są [zarządzane za pomocą narzędzia Jamf Pro](conditional-access-integrate-jamf.md). Wymaga to dostępu do konsol usługi Intune i narzędzia Jamf Pro.

## <a name="set-up-device-compliance-policies-in-intune"></a>Konfigurowanie zasad zgodności urządzeń w usłudze Intune

1. Otwórz program Microsoft Azure, a następnie przejdź do opcji **Intune** > **Zgodność urządzenia** > **Zasady**. Możesz utworzyć zasady dla systemu macOS, w tym wybór serii działań (np. wysłanie wiadomości e-mail z ostrzeżeniem) podejmowanych wobec niezgodnych użytkowników i grup.
2. Wyszukaj żądane grupy, a następnie zastosuj do nich zasady.

## <a name="require-the-company-portal-app-for-macos"></a>Wymaganie aplikacji Portal firmy dla systemu macOS

1. Na urządzeniu z systemem macOS przejdź do witryny https://aka.ms/macoscompanyportal, aby pobrać bieżącą wersję aplikacji Portal firmy dla systemu macOS.
2. Otwórz program Jamf Pro, a następnie przejdź do opcji **Zarządzanie komputerem** > **Pakiety**.
3. Utwórz nowy pakiet z aplikacją Portal firmy dla systemu macOS, a następnie kliknij przycisk **Zapisz**.
4. Otwórz opcję **Komputery** > **Zasady**, a następnie wybierz pozycję **Nowy**.
5. Aby skonfigurować ustawienia zasad, włącznie z wyzwalaczem i częstotliwością wykonywania, użyj ładunku **Ogólne**.
6. Wybierz ładunek **Pakiety** i kliknij przycisk **Konfiguruj**.
7. Aby wybrać pakiet z aplikacją Portal firmy, kliknij przycisk **Dodaj**.
8. Wybierz opcję **Zainstaluj** z menu podręcznego **Akcje**.
9. Skonfiguruj ustawienia pakietu.
10. Kliknij kartę **Zakres**, aby określić, na których komputerach należy zainstalować aplikację Portal firmy. Kliknij polecenie **Zapisz**. W urządzeniach objętych zakresem zasady zostaną uruchomione przy następnym wystąpieniu na komputerze wybranego wyzwalacza spełniającego kryteria ładunku **Ogólne**.

## <a name="direct-your-users-to-register-jamf-pro-managed-devices-with-azure-active-directory"></a>Narzucenie wymogu rejestrowania przez użytkowników urządzeń zarządzanych za pomocą narzędzia Jamf Pro w usłudze Azure Active Directory

> [!NOTE]
> Przed przejściem do dalszych kroków musisz [wdrożyć aplikację Portal firmy](conditional-access-assign-jamf.md#require-the-company-portal-app-for-macos) dla systemu macOS.  

Użytkownicy końcowi muszą za pośrednictwem usługi Jamf Self Service uruchomić aplikację Portal firmy, aby zarejestrować urządzenie w usłudze Azure Active Directory jako urządzenie zarządzane za pomocą narzędzia Jamf Pro.

1. W programie Jamf Pro przejdź do opcji **Komputery** > **Zasady** i utwórz nowe zasady na potrzeby rejestracji urządzenia.
2. Skonfiguruj ładunek **Dostęp warunkowy**, łącznie z określeniem wyzwalacza i częstotliwości wykonywania. Ustaw priorytet na **Po**.
3. Kliknij kartę **Zakres** i ustaw zakres zasad dla wszystkich urządzeń docelowych.
4. Kliknij kartę **Samoobsługa**, aby udostępnić zasady w usłudze Jamf Self Service. Dołącz zasady do kategorii **Zgodność urządzeń**. Kliknij polecenie **Zapisz**.

## <a name="next-steps"></a>Następne kroki

- [Dostęp warunkowy w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)
- [Wprowadzenie do dostępu warunkowego w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)
