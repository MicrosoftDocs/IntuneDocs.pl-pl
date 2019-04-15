---
title: Zasady zgodności urządzeń dla urządzeń Jamf
titleSuffix: Microsoft Intune
description: Stosuj zasady zgodności usługi Microsoft Intune z dostępem warunkowym usługi Azure Active Directory, aby pomóc zabezpieczać urządzenia zarządzane przez narzędzie Jamf.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/02/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c87fd2bd-7f53-4f1b-b985-c34f2d85a7bc
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a2fc212d370e6835428e7b0ae837e3882a38e37e
ms.sourcegitcommit: 364a7dbc7eaa414c7a9c39cf53eb4250e1ad3151
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/09/2019
ms.locfileid: "59569522"
---
# <a name="enforce-compliance-on-macs-managed-with-jamf-pro"></a>Wymuszanie zgodności na urządzeniach Mac zarządzanych za pomocą narzędzia Jamf Pro

Dotyczy: Usługa Intune w witrynie Azure Portal

W celu zapewnienia, że użytkownicy końcowi spełniają wymagania obowiązujące w organizacji, można wykorzystać usługę Azure Active Directory i zasady dostępu warunkowego usługi Microsoft Intune. Te zasady można stosować na komputerach Mac, które są [zarządzane za pomocą narzędzia Jamf Pro](conditional-access-integrate-jamf.md). Wymaga to dostępu do konsol usługi Intune i narzędzia Jamf Pro.

## <a name="set-up-device-compliance-policies-in-intune"></a>Konfigurowanie zasad zgodności urządzeń w usłudze Intune

1. Otwórz program Microsoft Azure, a następnie przejdź do opcji **Intune** > **Zgodność urządzenia** > **Zasady**. Możesz utworzyć zasady dla systemu macOS, w tym wybór serii działań (np. wysłanie wiadomości e-mail z ostrzeżeniem) podejmowanych wobec niezgodnych użytkowników i grup.
2. Wyszukaj żądane grupy, a następnie zastosuj do nich zasady.

> [!Note]
> Aby zachować zgodność z przepisami, usługa Intune wymaga pełnego szyfrowania dysku.

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
> Przed przejściem do dalszych kroków musisz [wdrożyć aplikację Portal firmy](conditional-access-assign-jamf.md#deploy-the-company-portal-app-for-macos-in-jamf-pro) dla systemu macOS.  

Użytkownicy końcowi muszą za pośrednictwem usługi Jamf Self Service uruchomić aplikację Portal firmy, aby zarejestrować urządzenie w usłudze Azure Active Directory jako urządzenie zarządzane za pomocą narzędzia Jamf Pro. Wymaga to podjęcia działania przez użytkowników końcowych. Zalecamy [kontakt z użytkownikiem końcowym](end-user-educate.md) za pośrednictwem poczty e-mail, powiadomień Jamf Pro lub innych metod powiadamiania użytkowników końcowych, aby poinformować ich o potrzebie kliknięcia przycisku w usłudze Jamf Self Service.

> [!WARNING]
> Aby rozpocząć rejestrację urządzenia, aplikację Portal firmy należy uruchomić z poziomu usługi Jamf Self Service. <br><br>Uruchomienie aplikacji Portal firmy ręcznie (np. z poziomu folderów Aplikacje lub Pobrane pliki) nie spowoduje zarejestrowania urządzenia. Jeśli użytkownik końcowy uruchomi aplikację Portal firmy ręcznie, zobaczy ostrzeżenie „AccountNotOnboarded”.

1. W programie Jamf Pro przejdź do opcji **Komputery** > **Zasady** i utwórz nowe zasady na potrzeby rejestracji urządzenia.
2. Skonfiguruj ładunek **Integracja z usługą Intune**, łącznie z określeniem wyzwalacza i częstotliwości wykonywania.
3. Kliknij kartę **Zakres** i ustaw zakres zasad dla wszystkich urządzeń docelowych.
4. Kliknij kartę **Samoobsługa**, aby udostępnić zasady w usłudze Jamf Self Service. Dołącz zasady do kategorii **Zgodność urządzeń**. Kliknij polecenie **Zapisz**.

## <a name="removing-a-jamf-managed-device-from-intune"></a>Usuwanie urządzenia zarządzanego za pomocą narzędzia Jamf z usługi Intune

Urządzenie zarządzane za pomocą narzędzia Jamf można usunąć z konsoli usługi Intune, wybierając pozycję **Usuń** w widoku **Wszystkie urządzenia**. Zbiorcze usuwanie urządzeń można włączyć, zaznaczając wiele urządzeń i klikając pozycję **Usuń**.

Zapoznaj się z informacjami na temat [usuwania urządzenia zarządzanego za pomocą narzędzia Jamf w dokumentacji programu Jamf Pro](https://www.jamf.com/jamf-nation/articles/80/unmanaging-computers-while-preserving-their-inventory-information). Możesz również wypełnić bilet pomocy technicznej dla [obsługi Jamf](https://www.jamf.com/support/) w celu uzyskania dodatkowej pomocy. 

## <a name="next-steps"></a>Następne kroki

- [Dostęp warunkowy w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)
- [Wprowadzenie do dostępu warunkowego w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)
