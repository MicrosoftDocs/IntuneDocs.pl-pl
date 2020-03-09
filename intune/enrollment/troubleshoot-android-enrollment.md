---
title: Rozwiązywanie problemów z urządzeniami z systemem Android Enterprise w usłudze Microsoft Intune
description: Sugestie dotyczące rozwiązywania niektórych typowych problemów występujących podczas rejestrowania urządzeń z systemem Android w usłudze Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/25/2020
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 04c726c1dc6af7e92b75335d105de605ef00e712
ms.sourcegitcommit: 8b716db3c0fdbb7dff62497ec283902a5069a343
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/27/2020
ms.locfileid: "77652372"
---
# <a name="troubleshoot-android-enterprise-device-problems-in-microsoft-intune"></a>Rozwiązywanie problemów z urządzeniami z systemem Android Enterprise w usłudze Microsoft Intune

Ten artykuł ułatwia administratorom usługi Intune zrozumienie i rozwiązywanie problemów podczas rejestrowania urządzeń z systemem Android Enterprise w usłudze Intune.

## <a name="apps-on-android-enterprise-devices"></a>Aplikacje na urządzeniach z systemem Android Enterprise

### <a name="managed-google-play-apps-that-arent-deployed-through-intune-are-displayed-in-the-work-profile"></a>Aplikacje zarządzane ze sklepu Google Play, które nie zostały wdrożone za pomocą usługi Intune, są wyświetlane w profilu służbowym
Aplikacje systemowe mogą zostać włączone w profilu służbowym przez producenta OEM urządzenia w momencie tworzenia profilu służbowego. Dostawca zarządzania urządzeniami przenośnymi (MDM) tego nie kontroluje.

Aby rozwiązać problem, wykonaj następujące kroki:

  1. Zbierz dzienniki Portalu firmy.
  2. Zanotuj aplikacje, które nieoczekiwanie są wyświetlane w profilu służbowym.
  3. Wyrejestruj urządzenie z usługi Intune i odinstaluj aplikację Portal firmy.
  4. Zainstaluj na potrzeby testowania aplikację [Test DPC](https://play.google.com/store/apps/details?id=com.afwsamples.testdpc), która umożliwia utworzenie profilu służbowego bez usługi zarządzania mobilnością w przedsiębiorstwie (EMM).
  5. Postępuj zgodnie z instrukcjami w artykule [Test DPC](https://play.google.com/store/apps/details?id=com.afwsamples.testdpc), aby utworzyć profil służbowy na urządzeniu.
  6. Przejrzyj aplikacje wyświetlane w profilu służbowym. 
  7. Jeśli te same aplikacje są wyświetlane w aplikacji Test DPC, producent OEM spodziewa się, że będą one instalowane na tym urządzeniu.

### <a name="unapproved-managed-google-play-for-work-store-apps-arent-being-removed-from-the-client-apps-page-in-intune"></a>Niezatwierdzone aplikacje zarządzane ze sklepu Google Play for Work nie są usuwane ze strony Aplikacje klienckie w usłudze Intune
Jest to oczekiwane zachowanie.

### <a name="managed-google-play-apps-arent-being-reported-under-the-discovered-apps-blade-in-the-intune-portal"></a>Aplikacje zarządzane ze sklepu Google Play nie są zgłaszane w bloku Odnalezione aplikacje w portalu usługi Intune
Jest to oczekiwane zachowanie. W bloku Odnalezione aplikacje są umieszczane wyłącznie aplikacje systemowe zainstalowane w profilu służbowym. Aby wyświetlić zainstalowane aplikacje zarządzane ze sklepu Google Play, użyj bloku **Aplikacje zarządzane**.

### <a name="are-web-applications-supported-for-work-profile-enrolled-devices"></a>Czy w przypadku urządzeń zarejestrowanych w profilu służbowym są obsługiwane aplikacje internetowe?
Tak. Aby uzyskać więcej informacji, zobacz [Linki sieci Web z zarządzanego sklepu Google Play](../apps/apps-add-android-for-work.md#managed-google-play-web-links)

## <a name="device-management"></a>Zarządzanie urządzeniami

### <a name="file-path-internal-storageandroiddatacommicrosoftwindowsintunecompanyportalfiles-missing-on-work-profile-enrolled-devices"></a>Brak ścieżki pliku Internal storage/Android/Data.com.microsoft.windowsintune.companyportal/files na urządzeniach zarejestrowanych w profilu służbowym

  **Odpowiedź**: Jest to oczekiwane zachowanie. Ta ścieżka jest tworzona wyłącznie na potrzeby scenariusza administratora urządzenia (starsza rejestracja systemu Android).

  Aby zebrać dzienniki Portalu firmy, wykonaj następujące kroki:

  1. W aplikacji Portal firmy ze wskaźnikiem naciśnij pozycję **Menu** > **Pomoc** > **Obsługa poczty e-mail**, a następnie naciśnij pozycję **Wyślij wiadomość e-mail i przekaż dzienniki**. 
  2. Po wyświetleniu monitu **Wyślij żądanie pomocy za pomocą** wybierz jedną z aplikacji poczty e-mail.
  3. Zostanie wygenerowana wiadomość e-mail do administratora IT zawierająca identyfikator zdarzenia, który można dostarczyć do pomocy technicznej dla produktów firmy Microsoft.

### <a name="managed-google-play-last-sync-time--hasnt-been-updated-in-days"></a>Czas ostatniej synchronizacji usługi Zarządzany sklep Google Play nie był aktualizowany od kilku dni
Jest to oczekiwane zachowanie. Synchronizacja jest wyzwalana tylko w przypadku ręcznego wykonania tej czynności.

### <a name="encryption-is-required-when-a-device-is-enrolled-can-it-be-turned-off"></a>Podczas rejestrowania urządzenia jest wymagane szyfrowanie. Czy można je wyłączyć?
Nie, firma Google wymaga, aby urządzenie było szyfrowane w celu utworzenia profilu służbowego. 

### <a name="samsung-devices-are-blocking-the-use-of-third-party-keyboards-like-swiftkey"></a>Urządzenia firmy Samsung blokują korzystanie z klawiatur innych firm, takich jak SwiftKey
Firma Samsung zaczęła wymuszać to ograniczenie na urządzeniach z systemem Android 8.0 i nowszych. Obecnie firma Microsoft pracuje z firmą Samsung nad rozwiązaniem tego problemu, a nowe informacje zostaną opublikowane, gdy tylko będą dostępne.

## <a name="remote-actions"></a>Akcje zdalne

### <a name="wipe-factory-reset-option-isnt-available-for-work-profile-enrolled-device"></a>Na urządzeniu zarejestrowanym w profilu służbowym nie jest dostępna opcja czyszczenia (resetowania do ustawień fabrycznych)
Jest to oczekiwane zachowanie. W scenariuszu profilu służbowego dostawca MDM nie ma pełnej kontroli nad urządzeniem. Jedyną dostępną opcją jest wycofanie (usunięcie danych firmowych), która powoduje usunięcie całego profilu służbowego wraz z jego zawartością.

### <a name="is-device-passcode-reset-supported"></a>Czy jest obsługiwane resetowanie kodu dostępu urządzenia?
Na urządzeniach zarejestrowanych w profilu służbowym można zresetować kod dostępu profilu służbowego na urządzeniach z systemem Android 8.0 i nowszych jedynie w przypadku, gdy:
- kod dostępu profilu służbowego jest zarządzany
- użytkownik końcowy zezwolił na jego zresetowanie.

W przypadku urządzeń dedykowanych (COSU) i w pełni zarządzanych resetowanie kodu dostępu urządzenia jest obsługiwane.


## <a name="next-steps"></a>Następne kroki

- [Rozwiązywanie problemów dotyczących rejestrowania urządzeń w usłudze Intune](../troubleshoot-device-enrollment-in-intune.md)
- [Zadaj pytanie na forum usługi Intune](https://social.technet.microsoft.com/Forums/%7Blang-locale%7D/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)
- [Sprawdź blog zespołu pomocy technicznej usługi Microsoft Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess)
- [Sprawdź blog dotyczący pakietu Microsoft Enterprise Mobility and Security](https://techcommunity.microsoft.com/t5/Azure-Active-Directory-Identity/Announcing-the-public-preview-of-Azure-AD-group-based-license/ba-p/245210)