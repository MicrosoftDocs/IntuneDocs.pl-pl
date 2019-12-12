---
title: Rozwiązywanie problemów z akcjami urządzenia w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Uzyskaj pomoc w rozwiązywaniu problemów z akcjami urządzeń.
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
ms.openlocfilehash: 239dd8630eb361da8609e3a34eb2c9346a64dab0
ms.sourcegitcommit: ec69e7ccc6e6183862a48c1b03ca6a3bf573f354
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 12/07/2019
ms.locfileid: "74907189"
---
# <a name="troubleshoot-device-actions-in-intune"></a>Rozwiązywanie problemów z akcjami urządzenia w usłudze Intune

Microsoft Intune ma wiele akcji, które ułatwiają zarządzanie urządzeniami. Ten artykuł zawiera odpowiedzi na niektóre często zadawane pytania, które mogą pomóc w rozwiązywaniu problemów z akcjami urządzeń.

## <a name="bypass-activation-lock-action"></a>Akcja obejścia blokady aktywacji

### <a name="i-clicked-the-bypass-activation-lock-action-in-the-portal-but-nothing-happened-on-the-device"></a>W portalu została kliknięta akcja "Obejście Blokada aktywacji", ale nic się nie stało na urządzeniu.
Jest to oczekiwane. Po uruchomieniu akcji obejście Blokada aktywacji usługa Intune zażąda zaktualizowanego kodu od firmy Apple. Kod w polu kod dostępu należy wprowadzić ręcznie, gdy urządzenie zostanie wyświetlone na Blokada aktywacji ekranie. Ten kod jest prawidłowy tylko przez 15 dni, dlatego kliknij akcję i skopiuj kod przed wygenerowaniem czyszczenia.

### <a name="why-dont-i-see-the-bypass-activation-lock-code-in-the-hardware-overview-blade-of-my-ios-device"></a>Dlaczego nie widzę kodu obejścia Blokada aktywacji w bloku przegląd sprzętu mojego urządzenia z systemem iOS?
Najbardziej prawdopodobną przyczyną są:
- Kod wygasł i został wyczyszczony z usługi.
- Urządzenie nie jest nadzorowane przy użyciu zasad ograniczeń urządzenia, aby zezwolić na Blokada aktywacji.

Możesz zaewidencjonować kod w Eksploratorze grafu przy użyciu następującego zapytania:

```GET - https://graph.microsoft.com/beta/deviceManagement/manageddevices('deviceId')?$select=activationLockBypassCode.```

### <a name="why-is-the-bypass-activation-lock-action-greyed-out-for-my-ios-device"></a>Dlaczego akcja obejścia Blokada aktywacji jest wyszarzona dla urządzenia z systemem iOS?
Najbardziej prawdopodobną przyczyną są: 
- Kod wygasł i został wyczyszczony z usługi.
- Urządzenie nie jest nadzorowane przy użyciu zasad ograniczeń urządzenia, aby zezwolić na Blokada aktywacji.

### <a name="is-the-bypass-activation-lock-code-case-sensitive"></a>Czy w przypadku obejścia Blokada aktywacji rozróżniana jest wielkość liter?
Nie. Nie musisz wprowadzać kresek.

## <a name="remove-devices-action"></a>Akcja usuwania urządzeń

### <a name="how-do-i-tell-who-started-a-retirewipe"></a>Jak mogę powiedzieć, kto rozpoczął wycofanie/wymazanie?
W [centrum administracyjnym programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)przejdź do pozycji **administracja dzierżawy** > **dzienniki inspekcji** > Sprawdź **zainicjowane przez** kolumnę.
Jeśli nie widzisz wpisu, najprawdopodobniej osoba, która zainicjuje akcję, jest użytkownikiem urządzenia. Prawdopodobnie używają aplikacji Portal firmy lub portal.manage.microsoft.com.

### <a name="why-wasnt-my-application-uninstalled-after-using-retire"></a>Dlaczego moja aplikacja nie została odinstalowana po użyciu wycofania?
Ponieważ nie był traktowany jako aplikacja zarządzana. W tym kontekście zarządzana aplikacja jest aplikacją, która została zainstalowana za pomocą usługi Intune. Obejmuje to następujące działania:
- Aplikacja została wdrożona zgodnie z wymaganiami
- Aplikacja została wdrożona jako dostępna, a następnie zainstalowana przez użytkownika końcowego z poziomu aplikacji Portal firmy.

### <a name="why-is-wipe-grayed-out-for-android-enterprise-work-profile-devices"></a>Dlaczego czyszczenie jest wyszarzone dla urządzeń profilu służbowego systemu Android?
Jest to oczekiwane zachowanie. Firma Google nie pozwala na Resetowanie ustawień fabrycznych urządzeń profilu służbowego od dostawcy MDM.

### <a name="why-can-i-sign-back-into-my-office-apps-after-my-device-was-retired"></a>Dlaczego mogę ponownie zalogować się do aplikacji pakietu Office, gdy moje urządzenie zostało wycofane?
Ponieważ wycofanie urządzenia nie odwołuje tokenów dostępu. Aby wyeliminować ten warunek, można użyć zasad dostępu warunkowego.

### <a name="how-can-i-monitor-a-retirewipe-action-after-it-was-issued"></a>Jak mogę monitorować akcję wycofywania/czyszczenia po wydaniu?
W [centrum administracyjnym programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)przejdź do pozycji **administracja dzierżawy** > **dzienniki inspekcji**.

### <a name="why-do-wipes-sometimes-show-as-pending-indefinitely"></a>Dlaczego wymazywania są czasami wyświetlane jako oczekujące na czas nieokreślony?
Urządzenia nie zawsze raportują swój stan z powrotem do usługi Intune przed rozpoczęciem resetowania. Dlatego Akcja jest wyświetlana jako oczekująca. Po potwierdzeniu, że akcja zakończyła się pomyślnie, Usuń urządzenie z usługi.

### <a name="what-happens-if-i-start-a-retirewipe-on-an-offline-device-or-a-device-that-hasnt-communicated-with-the-service-in-a-while"></a>Co się stanie w przypadku rozpoczęcia wycofywania/wymazania na urządzeniu w trybie offline lub na urządzeniu, które nie komunikuje się z usługą w czasie?
Urządzenie pozostanie w stanie **oczekiwania na wycofanie/wymazanie** do momentu wygaśnięcia certyfikatu MDM. Certyfikat MDM jest ważny przez jeden rok od rejestracji i automatycznie odnawiany co roku. Jeśli urządzenie zostanie zaewidencjonowane przed wygaśnięciem certyfikatu MDM, zostanie wycofane lub wymazane. Jeśli urządzenie nie zostanie zaewidencjonowane przed wygaśnięciem certyfikatu MDM, nie będzie można zaewidencjonować go w usłudze. 180 dni po wygaśnięciu certyfikatu MDM urządzenie zostanie automatycznie usunięte z Azure Portal.


## <a name="reset-passcode-action"></a>Akcja resetowania kodu dostępu

### <a name="why-is-the-reset-passcode-action-greyed-out-on-my-android-device-admin-enrolled-device"></a>Dlaczego akcja resetowania kodu dostępu jest wyszarzona na zarejestrowanym urządzeniu z systemem Android?
Aby zwalczać oprogramowanie wymuszającego okup, firma Google usunęła funkcję resetowania kodu dostępu do interfejsu API administratora urządzenia (dotyczy to urządzeń z systemem Android w wersji 7,0 lub nowszej).

### <a name="why-do-i-get-a-not-supported-message-when-i-issue-a-passcode-reset-to-my-android-80-or-later-work-profile-enrolled-device"></a>Dlaczego otrzymuję komunikat "nieobsługiwany" po wydaniu resetowania kodu dostępu do mojego zarejestrowanego urządzenia z systemem Android 8,0 lub nowszym?
Ponieważ token reset nie został aktywowany na urządzeniu. Aby aktywować token resetowania:
1. W zasadach konfiguracji należy wymagać kodu dostępu do profilu służbowego.
2. Użytkownik końcowy musi ustawić odpowiedni kod dostępu profilu służbowego.
3. Użytkownik końcowy musi zaakceptować monit pomocniczy, aby umożliwić Resetowanie kodu dostępu.
Po wykonaniu tych kroków nie należy już otrzymywać odpowiedzi.

### <a name="why-am-i-prompted-to-set-a-new-passcode-on-my-ios-device-when-i-issue-the-remove-passcode-action"></a>Dlaczego otrzymuję monit o ustawienie nowego kodu dostępu na urządzeniu z systemem iOS, gdy wystawią akcję Usuń kod dostępu?
Ponieważ jedna z zasad zgodności wymaga kodu dostępu.

## <a name="next-steps"></a>Następne kroki

Uzyskaj [pomoc techniczną od firmy Microsoft](../fundamentals/get-support.md) lub skorzystaj z [forum społeczności](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).
