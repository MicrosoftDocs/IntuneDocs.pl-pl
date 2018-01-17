---
title: "Wymuszanie zasad zgodności na urządzeniach zarządzanych za pomocą narzędzia Jamf"
titlesuffix: Azure portal
description: "Wykorzystaj zgodność w celu ułatwienia zabezpieczania urządzeń zarządzanych za pomocą narzędzia Jamf."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c87fd2bd-7f53-4f1b-b985-c34f2d85a7bc
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c72de87b87775155672994163140e342b7ba99b4
ms.sourcegitcommit: 000684953cbb3ceae0e2bcaa51186c9221f7aa86
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/15/2017
---
# <a name="enforce-compliance-on-macs-managed-with-jamf-pro"></a>Wymuszanie zgodności na urządzeniach Mac zarządzanych za pomocą narzędzia Jamf Pro

|Dotyczy: usługa Intune w witrynie Azure Portal |
|--|
|Szukasz dokumentacji dotyczącej usługi Intune w portalu klasycznym? [Przejdź tutaj](/intune/introduction-intune?toc=/intune-classic/toc.json).|
| |

W celu zapewnienia, że użytkownicy końcowi spełniają wymagania obowiązujące w organizacji, można wykorzystać usługę Azure Active Directory i zasady dostępu warunkowego usługi Microsoft Intune. Te zasady można stosować na komputerach Mac, które są [zarządzane za pomocą narzędzia Jamf Pro](conditional-access-integrate-jamf.md). Wymaga to dostępu do konsol usługi Intune i narzędzia Jamf Pro.

## <a name="set-up-device-compliance-policies-in-intune"></a>Konfigurowanie zasad zgodności urządzeń w usłudze Intune

1. Otwórz program Microsoft Azure, a następnie przejdź do opcji **Intune** > **Zgodność urządzenia** > **Zasady**. Możesz utworzyć zasady dla systemu macOS, w tym wybór serii działań (np. wysłanie wiadomości e-mail z ostrzeżeniem) podejmowanych wobec niezgodnych użytkowników i grup.
2. Wyszukaj żądane grupy, a następnie zastosuj do nich zasady.

## <a name="deploy-the-company-portal-app-for-macos-in-jamf-pro"></a>Wdrażanie aplikacji Portal firmy dla systemu macOS w narzędziu Jamf Pro

Aplikację Portal firmy dla systemu macOS w narzędziu Jamf Pro należy wdrożyć w formie instalacji w tle, wykonując poniższą procedurę:

1. Na urządzeniu z systemem macOS pobierz bieżącą wersję [aplikacji Portal firmy dla systemu macOS](https://go.microsoft.com/fwlink/?linkid=862280). Nie instaluj tej aplikacji — należy przekazać jej kopię do narzędzia Jamf Pro.
2. Otwórz program Jamf Pro, a następnie przejdź do opcji **Zarządzanie komputerem** > **Pakiety**.
3. Utwórz nowy pakiet z aplikacją Portal firmy dla systemu macOS, a następnie kliknij przycisk **Zapisz**.
4. Otwórz opcję **Komputery** > **Zasady**, a następnie wybierz pozycję **Nowy**.
5. Użyj ładunku **Ogólne**, aby skonfigurować ustawienia zasad. Te ustawienia powinny być następujące:
   - Wyzwalacz: wybierz opcję **Ukończenie rejestracji** i **Cykliczne zaewidencjonowanie**
   - Częstotliwość wykonywania: wybierz opcję **Raz na komputerze**
6. Wybierz ładunek **Pakiety** i kliknij przycisk **Konfiguruj**.
7. Aby wybrać pakiet z aplikacją Portal firmy, kliknij przycisk **Dodaj**.
8. Wybierz opcję **Zainstaluj** z menu podręcznego **Akcje**.
9. Skonfiguruj ustawienia pakietu.
10. Kliknij kartę **Zakres**, aby określić, na których komputerach należy zainstalować aplikację Portal firmy. Kliknij polecenie **Zapisz**. W urządzeniach objętych zakresem zasady zostaną uruchomione przy następnym wystąpieniu na komputerze wybranego wyzwalacza spełniającego kryteria ładunku **Ogólne**.

## <a name="create-a-policy-in-jamf-pro-to-have-users-register-their-devices-with-azure-active-directory"></a>Tworzenie zasad narzędzia Jamf Pro, które umożliwią użytkownikom rejestrowanie swoich urządzeń w usłudze Azure Active Directory

> [!NOTE]
> Przed przejściem do dalszych kroków musisz [wdrożyć aplikację Portal firmy](conditional-access-assign-jamf.md#require-the-company-portal-app-for-macos) dla systemu macOS.  

Użytkownicy końcowi muszą za pośrednictwem usługi Jamf Self Service uruchomić aplikację Portal firmy, aby zarejestrować urządzenie w usłudze Azure Active Directory jako urządzenie zarządzane za pomocą narzędzia Jamf Pro. Wymaga to podjęcia działania przez użytkowników końcowych. Zalecamy [kontakt z użytkownikiem końcowym](end-user-educate.md) za pośrednictwem poczty e-mail, powiadomień Jamf Pro lub innych metod powiadamiania użytkowników końcowych, aby poinformować ich o potrzebie kliknięcia przycisku w usłudze Jamf Self Service.

> [!WARNING]
> Aby rozpocząć rejestrację urządzenia, aplikację Portal firmy należy uruchomić z poziomu usługi Jamf Self Service. <br><br>Uruchomienie aplikacji Portal firmy ręcznie (np. z poziomu folderów Aplikacje lub Pobrane pliki) nie spowoduje zarejestrowania urządzenia. Jeśli użytkownik końcowy uruchomi aplikację Portal firmy ręcznie, zobaczy ostrzeżenie „AccountNotOnboarded”.

1. W programie Jamf Pro przejdź do opcji **Komputery** > **Zasady** i utwórz nowe zasady na potrzeby rejestracji urządzenia.
2. Skonfiguruj ładunek **Integracja z usługą Intune**, łącznie z określeniem wyzwalacza i częstotliwości wykonywania.
3. Kliknij kartę **Zakres** i ustaw zakres zasad dla wszystkich urządzeń docelowych.
4. Kliknij kartę **Samoobsługa**, aby udostępnić zasady w usłudze Jamf Self Service. Dołącz zasady do kategorii **Zgodność urządzeń**. Kliknij polecenie **Zapisz**.

## <a name="next-steps"></a>Następne kroki

- [Dostęp warunkowy w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)
- [Wprowadzenie do dostępu warunkowego w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)
