---
title: Rozwiązywanie problemów z akcjami urządzenia w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Pomoc dotycząca rozwiązywania problemów z akcjami urządzenia.
keywords: ''
author: erikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/02/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ROBOTS: ''
ms.reviewer: coferro
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 545f287e8b7ee82e2008f239171b22e01714b8c7
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514748"
---
# <a name="troubleshoot-device-actions-in-intune"></a>Rozwiązywanie problemów z akcjami urządzenia w usłudze Intune

Usługa Microsoft Intune oferuje wiele akcji, które ułatwiają zarządzanie urządzeniami. Ten artykuł zawiera odpowiedzi na kilka często zadawanych pytań, które mogą pomóc w rozwiązywaniu problemów z akcjami urządzenia.

## <a name="disable-activation-lock-action"></a>Akcja Wyłącz blokadę aktywacji

### <a name="i-clicked-the-disable-activation-lock-action-in-the-portal-but-nothing-happened-on-the-device"></a>Po kliknięciu akcji „Wyłącz blokadę aktywacji” w portalu na urządzeniu nic się nie dzieje.
Jest to oczekiwane zachowanie. Po uruchomieniu akcji Wyłącz blokadę aktywacji w usłudze Intune należy podać zaktualizowany kod od firmy Apple. Kod należy wprowadzić ręcznie w polu kodu dostępu, gdy na urządzeniu zostanie wyświetlony ekran Blokada aktywacji. Ten kod jest ważny tylko przez 15 dni, dlatego należy pamiętać, aby kliknąć tę akcję i skopiować kod przed uruchomieniem czyszczenia.

### <a name="why-dont-i-see-the-disable-activation-lock-code-in-the-hardware-overview-blade-of-my-iosipados-device"></a>Dlaczego nie widzę kodu akcji Wyłącz blokadę aktywacji w bloku przeglądu sprzętu mojego urządzenia z systemem iOS/iPadOS?
Najbardziej prawdopodobne przyczyny mogą być następujące:
- Kod wygasł i został wyczyszczony z usługi.
- Urządzenie nie jest nadzorowane przy użyciu zasad ograniczeń urządzenia, aby można było zezwolić na blokadę aktywacji.

Kod możesz sprawdzić w eksploratorze programu Graph za pomocą następującego zapytania:

```GET - https://graph.microsoft.com/beta/deviceManagement/manageddevices('deviceId')?$select=activationLockBypassCode.```

### <a name="why-is-the-disable-activation-lock-action-greyed-out-for-my-iosipados-device"></a>Dlaczego akcja Wyłącz blokadę aktywacji jest wyszarzona dla mojego urządzenia z systemem iOS/iPadOS?
Najbardziej prawdopodobne przyczyny mogą być następujące: 
- Kod wygasł i został wyczyszczony z usługi.
- Urządzenie nie jest nadzorowane przy użyciu zasad ograniczeń urządzenia, aby można było zezwolić na blokadę aktywacji.

### <a name="is-the-disable-activation-lock-code-case-sensitive"></a>Czy w kodzie akcji Wyłącz blokadę aktywacji jest rozróżniana wielkość liter?
Nie. Nie trzeba także wprowadzać kresek.

## <a name="remove-devices-action"></a>Akcja Usuń urządzenia

### <a name="how-do-i-tell-who-started-a-retirewipe"></a>Jak mogę sprawdzić, kto rozpoczął akcję Wycofaj/wyczyść?
W [Centrum administracyjnym usługi Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) przejdź do ekranu **Administracja dzierżawą** > **Dzienniki inspekcji** i sprawdź kolumnę **Zainicjowane przez**.
Jeśli nie widzisz żadnego wpisu, akcję najprawdopodobniej zainicjował użytkownik urządzenia. W tym celu skorzystał prawdopodobnie z aplikacji Portal firmy lub z witryny portal.manage.microsoft.com.

### <a name="why-wasnt-my-application-uninstalled-after-using-retire"></a>Dlaczego moja aplikacja nie została odinstalowana po użyciu akcji Wycofaj?
Ponieważ nie była uważana za aplikację zarządzaną. W tym kontekście aplikacja zarządzana to taka, która została zainstalowana za pomocą usługi Intune. Obejmuje to następujące działania:
- Aplikacja została wdrożona jako wymagana
- Aplikacja została wdrożona jako dostępna, a następnie zainstalowana przez użytkownika końcowego z poziomu aplikacji Portal firmy.

### <a name="why-is-wipe-grayed-out-for-android-enterprise-work-profile-devices"></a>Dlaczego dla urządzeń z profilami służbowymi w rozwiązaniu Android Enterprise akcja Wyczyść jest wyszarzona?
Jest to oczekiwane zachowanie. Firma Google nie pozwala na resetowanie do ustawień fabrycznych urządzeń z profilami służbowymi od dostawcy MDM.

### <a name="why-can-i-sign-back-into-my-office-apps-after-my-device-was-retired"></a>Dlaczego mogę ponownie zalogować się do aplikacji pakietu Office po wycofaniu mojego urządzenia?
Ponieważ wycofanie urządzenia nie powoduje odwołania tokenów dostępu. Aby wyeliminować ten warunek, można użyć zasad dostępu warunkowego.

### <a name="how-can-i-monitor-a-retirewipe-action-after-it-was-issued"></a>Jak mogę monitorować akcję Wycofaj/wyczyść po jej uruchomieniu?
W [Centrum administracyjnym usługi Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) przejdź do ekranu **Administracja dzierżawą** > **Dzienniki inspekcji**.

### <a name="why-do-wipes-sometimes-show-as-pending-indefinitely"></a>Dlaczego akcje czyszczenia czasami są pokazywane jako oczekujące przez czas nieokreślony?
Urządzenia nie zawsze raportują swój stan z powrotem do usługi Intune przed rozpoczęciem resetowania. Dlatego stan akcji jest wyświetlany jako oczekujący. Po potwierdzeniu, że akcja zakończyła się pomyślnie, usuń urządzenie z usługi.

### <a name="what-happens-if-i-start-a-retirewipe-on-an-offline-device-or-a-device-that-hasnt-communicated-with-the-service-in-a-while"></a>Co się stanie, jeśli rozpocznę akcję wycofywania/czyszczenia na urządzeniu w trybie offline lub na urządzeniu, które od jakiegoś czasu nie komunikowało się z usługą?
Urządzenie pozostanie w stanie **oczekującym na wycofanie/wyczyszczenie** do momentu wygaśnięcia certyfikatu MDM. Certyfikat MDM jest ważny przez rok od rejestracji i co rok jest odnawiany automatycznie. Jeśli urządzenie zostanie zaewidencjonowane przed wygaśnięciem certyfikatu MDM, zostanie wycofane/wyczyszczone. Jeśli urządzenie nie zostanie zaewidencjonowane przed wygaśnięciem certyfikatu MDM, nie będzie można zaewidencjonować go w usłudze. 180 dni po wygaśnięciu certyfikatu MDM urządzenie zostanie automatycznie usunięte z witryny Azure Portal.


## <a name="reset-passcode-action"></a>Akcja Resetuj kod dostępu

### <a name="why-is-the-reset-passcode-action-greyed-out-on-my-android-device-admin-enrolled-device"></a>Dlaczego akcja Resetuj kod dostępu jest wyszarzona na moim urządzeniu z systemem Android zarejestrowanym przez administratora urządzenia?
Aby zwalczać oprogramowanie wymuszającego okup, firma Google usunęła funkcję resetowania kodu dostępu z interfejsu API administratora urządzenia (dotyczy to urządzeń z systemem Android 7.0 lub nowszym).

### <a name="why-do-i-get-a-not-supported-message-when-i-issue-a-passcode-reset-to-my-android-80-or-later-work-profile-enrolled-device"></a>Dlaczego otrzymuję komunikat „Nieobsługiwane” po uruchomieniu resetowania kodu dostępu na moim zarejestrowanym urządzeniu z profilem służbowym w systemie Android 8.0 lub nowszym?
Ponieważ na urządzeniu nie aktywowano tokenu resetowania. Aby aktywować token resetowania, należy spełnić następujące warunki:
1. W zasadach konfiguracji musi być wymagany kod dostępu profilu służbowego.
2. Użytkownik końcowy musi ustawić odpowiedni kod dostępu profilu służbowego.
3. Użytkownik końcowy musi zaakceptować monit pomocniczy, aby umożliwić resetowanie kodu dostępu.
Po wykonaniu tych kroków taka odpowiedź nie powinna być już wyświetlana.

### <a name="why-am-i-prompted-to-set-a-new-passcode-on-my-iosipados-device-when-i-issue-the-remove-passcode-action"></a>Dlaczego otrzymuję monit o ustawienie nowego kodu dostępu na urządzeniu z systemem iOS/iPadOS, gdy uruchamiam akcję Usuń kod dostępu?
Ponieważ jedna z zasad zgodności wymaga kodu dostępu.


## <a name="wipe-action"></a>Akcja Wyczyść

### <a name="i-cant-restart-a-windows-10-device-after-using-the-wipe-action"></a>Nie można ponownie uruchomić urządzenia z systemem Windows 10 po użyciu akcji czyszczenia
Może być to spowodowane tym, że używasz opcji **Wyczyść urządzenie i kontynuujesz czyszczenie nawet wtedy, gdy urządzenie utraci zasilanie. W przypadku wybrania tej opcji pamiętaj, że może ona uniemożliwić ponowne uruchomienie niektórych urządzeń z systemem Windows 10.** na urządzeniu z systemem Windows 10.

Może to być spowodowane tym, że instalacja systemu Windows ma poważne uszkodzenie uniemożliwiające ponowne zainstalowanie systemu operacyjnego. W takim przypadku proces kończy się niepowodzeniem i pozostawia system w [środowisku odzyskiwania systemu Windows]( https://docs.microsoft.com/windows-hardware/manufacture/desktop/windows-recovery-environment--windows-re--technical-reference).

### <a name="i-cant-restart-a-bitlocker-encrypted-device-after-using-the-wipe-action"></a>Nie można ponownie uruchomić urządzenia szyfrowanego funkcją BitLocker po użyciu akcji czyszczenia
Może być to spowodowane tym, że używasz opcji **Wyczyść urządzenie i kontynuujesz czyszczenie nawet wtedy, gdy urządzenie utraci zasilanie. W przypadku wybrania tej opcji pamiętaj, że może ona uniemożliwić ponowne uruchomienie niektórych urządzeń z systemem Windows 10.** na urządzeniu szyfrowanym funkcją BitLocker.

Aby rozwiązać ten problem, użyj nośnika rozruchowego w celu ponownego zainstalowania systemu Windows 10 na urządzeniu.


## <a name="next-steps"></a>Następne kroki

Uzyskaj [pomoc techniczną od firmy Microsoft](../fundamentals/get-support.md) lub skorzystaj z [forum społeczności](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).
