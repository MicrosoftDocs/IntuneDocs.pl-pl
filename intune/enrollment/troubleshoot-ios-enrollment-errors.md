---
title: Rozwiązywanie problemów dotyczących rejestrowania urządzeń z systemem iOS w usłudze Microsoft Intune
titleSuffix: Microsoft Intune
description: Sugestie dotyczące rozwiązywania niektórych typowych problemów dotyczących rejestrowania urządzeń z systemem iOS w usłudze Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/18/2019
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
ms.openlocfilehash: e71ae2d2bcee22040c256ea711edd22b1d1fc80a
ms.sourcegitcommit: 01fb3d844958a0e66c7b87623160982868e675b0
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2019
ms.locfileid: "74199268"
---
# <a name="troubleshoot-ios-device-enrollment-problems-in-microsoft-intune"></a>Rozwiązywanie problemów dotyczących rejestrowania urządzeń z systemem iOS w usłudze Microsoft Intune

Ten artykuł ułatwia administratorom usługi Intune zrozumienie i rozwiązywanie problemów podczas rejestrowania urządzeń z systemem iOS w usłudze Intune.

## <a name="prerequisites"></a>Wymagania wstępne

Przed rozpoczęciem rozwiązywania problemów należy zebrać podstawowe informacje. Te informacje mogą pomóc w lepszym zrozumieniu problemu i skrócić czas, aby znaleźć rozwiązanie.

Zbierz następujące informacje o problemie:

- Jaki jest dokładny komunikat o błędzie?
- Gdzie zobaczysz komunikat o błędzie?
- Kiedy problem zaczął występować? Czy rejestracja została kiedykolwiek zadziałała?
- Na jakiej platformie (Android, iOS, Windows) występuje problem?
- Ilu użytkowników dotyczy błąd? Czy wszyscy użytkownicy mają te same lub tylko niektóre?
- Ile urządzeń ma wpływ? Czy dotyczy to wszystkich urządzeń?
- Co to jest urząd MDM? Jeśli jest System Center Configuration Manager, jakiej wersji Configuration Manager są używane?
- Jak odbywa się rejestracja? Czy jest to "Dobierz własne urządzenie" (BYOD), czy Apple Device Enrollment Program (DEP) z profilami rejestracji?

## <a name="error-messages"></a>Komunikaty o błędach

### <a name="profile-installation-failed-a-network-error-has-occurred"></a>Instalacja profilu nie powiodła się. Wystąpił błąd sieciowy.

**Przyczyna:** Wystąpił nieokreślony problem z systemem iOS na urządzeniu.

#### <a name="resolution"></a>Rozwiązanie

1. Aby zapobiec utracie danych w następujących krokach (Przywracanie systemu iOS powoduje usunięcie wszystkich danych z urządzenia), należy pamiętać o wykonaniu kopii zapasowej danych.
2. Przełącz urządzenie w tryb odzyskiwania, a następnie Przywróć je. Upewnij się, że skonfigurowano ją jako nowe urządzenie. Więcej informacji o sposobie przywracania urządzeń z systemem iOS znajduje się w temacie [https://support.apple.com/HT201263](https://support.apple.com/HT201263).
3. Zarejestruj ponownie urządzenie.

### <a name="profile-installation-failed-connection-to-the-server-could-not-be-established"></a>Instalacja profilu nie powiodła się. Nie można nawiązać połączenia z serwerem.

**Przyczyna:** Dzierżawa usługi Intune jest skonfigurowana tak, aby zezwalać tylko na urządzenia należące do firmy. 

#### <a name="resolution"></a>Rozwiązanie
1. Zaloguj się do witryny Azure Portal.
2. Wybierz pozycję **Więcej usług**, wyszukaj usługę Intune, a następnie wybierz usługę **Intune**.
3. Wybierz pozycję **Rejestrowanie urządzenia** > **Ograniczenia rejestracji**.
4. W obszarze **ograniczenia typu urządzenia**wybierz ograniczenie, które chcesz ustawić > **Właściwości** > **Wybierz platformy** > wybierz pozycję **Zezwól** dla **systemu iOS**, a następnie kliknij przycisk **OK**.
5. Wybierz pozycję **Konfiguruj platformy**, wybierz pozycję **Zezwól** dla urządzeń z systemem iOS należących do użytkownika, a następnie kliknij przycisk **OK**.
6. Zarejestruj ponownie urządzenie.

**Przyczyna:** Niezbędne rekordy CNAME w systemie DNS nie istnieją.

#### <a name="resolution"></a>Rozwiązanie
Utwórz rekordy zasobów CNAME systemu DNS dla domeny Twojej firmy. Na przykład jeśli domena firmy to contoso.com, utwórz w systemie DNS rekord CNAME przekierowujący EnterpriseEnrollment.contoso.com do EnterpriseEnrollment-s.manage.microsoft.com.

Chociaż tworzenie wpisów DNS rekordów CNAME jest opcjonalne, rekordy CNAME ułatwiają użytkownikom rejestrację. Jeśli rekord CNAME nie zostanie znaleziony, użytkownicy są proszeni o ręczne wprowadzenie nazwy serwera MDM: enrollment.manage.microsoft.com.

Jeśli zweryfikowano więcej niż jedną domenę, należy utworzyć rekord CNAME dla każdej z nich. Rekordy zasobów CNAME muszą zawierać następujące informacje:

|TYPE|Nazwa hosta|Przekierowanie na|TTL|
|------|------|------|------|
|CNAME|EnterpriseEnrollment.domena_firmowa.com|EnterpriseEnrollment-s.manage.microsoft.com|1 godzina|
|CNAME|EnterpriseRegistration.domena_firmowa.com|EnterpriseRegistration.windows.net|1 godzina|

Jeśli firma używa wielu domen dla poświadczeń użytkowników, należy utworzyć rekordy CNAME dla każdej domeny.

> [!NOTE]
> Propagowanie zmian rekordów DNS może potrwać do 72 godzin. Nie można zweryfikować zmiany w systemie DNS w usłudze Intune, dopóki trwa propagowanie rekordu DNS.

**Przyczyna:** Należy zarejestrować urządzenie, które było wcześniej zarejestrowane przy użyciu innego konta użytkownika, a poprzedni użytkownik nie został odpowiednio usunięty z usługi Intune.

#### <a name="resolution"></a>Rozwiązanie
1. Anuluj wszystkie bieżące instalacje profilu.
2. Otwórz [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com) w przeglądarce Safari.
3. Zarejestruj ponownie urządzenie.

> [!NOTE]
> Jeśli rejestracja nadal kończy się niepowodzeniem, Usuń pliki cookie w przeglądarce Safari (nie blokuj plików cookie), a następnie zarejestruj ponownie urządzenie.

**Przyczyna:** Urządzenie zostało już zarejestrowane za pomocą innego dostawcy zarządzania urządzeniami przenośnymi.

#### <a name="resolution"></a>Rozwiązanie
1. Otwórz **Ustawienia** na urządzeniu z systemem iOS, przejdź do pozycji **Ogólne > Zarządzanie urządzeniami**.
2. Usuń istniejący profil zarządzania.
3. Zarejestruj ponownie urządzenie.

**Przyczyna:** Użytkownik próbujący zarejestrować urządzenie nie ma licencji Microsoft Intune.

#### <a name="resolution"></a>Rozwiązanie
1. Przejdź do [Centrum administracyjnego pakietu Office 365](https://portal.office.com/adminportal/home#/homepage), a następnie wybierz pozycję **Użytkownicy > aktywni użytkownicy**.
2. Wybierz konto użytkownika, do którego chcesz przypisać licencję użytkownika usługi Intune, po czym wybierz opcje **Licencje produktu > Edytuj**.
3. Przełącz przełącznik na pozycję **w** pozycji licencja, którą chcesz przypisać do tego użytkownika, a następnie wybierz pozycję **Zapisz**.
4. Zarejestruj ponownie urządzenie.

### <a name="this-service-is-not-supported-no-enrollment-policy"></a>Ta usługa nie jest obsługiwana. Brak zasad rejestracji.

**Przyczyna**: certyfikat wypychania MDM firmy Apple nie jest skonfigurowany w usłudze Intune lub certyfikat jest nieprawidłowy. 

#### <a name="resolution"></a>Rozwiązanie

- Jeśli certyfikat wypychania MDM nie jest skonfigurowany, wykonaj kroki opisane w sekcji [Pobieranie certyfikatu wypychania MDM firmy Apple](apple-mdm-push-certificate-get.md#steps-to-get-your-certificate).
- Jeśli certyfikat wypychania MDM jest nieprawidłowy, wykonaj czynności opisane w sekcji [odnów certyfikat wypychania Apple MDM](apple-mdm-push-certificate-get.md#renew-apple-mdm-push-certificate).

### <a name="company-portal-temporarily-unavailable-the-company-portal-app-encountered-a-problem-if-the-problem-persists-contact-your-system-administrator"></a>Portal firmy jest tymczasowo niedostępny. Aplikacja Portal firmy napotkała problem. Jeśli problem będzie nadal występować, skontaktuj się z administratorem systemu.

**Przyczyna:** Aplikacja Portal firmy jest nieaktualna lub uszkodzona.

#### <a name="resolution"></a>Rozwiązanie
1. Usuń aplikację Portal firmy z urządzenia.
2. Pobierz i zainstaluj aplikację **Microsoft Intune — Portal firmy** ze sklepu **App Store**.
3. Zarejestruj ponownie urządzenie.
 > [!NOTE]
    > Ten błąd może również wystąpić, jeśli użytkownik próbuje zarejestrować więcej urządzeń, niż jest skonfigurowana do zezwalania na rejestrację urządzenia. Postępuj zgodnie z krokami **poniżej,** Jeśli te kroki nie rozwiążą problemu.

### <a name="device-cap-reached"></a>Osiągnięto limit urządzeń

**Przyczyna:** Użytkownik próbuje zarejestrować więcej urządzeń, niż jest to limit rejestracji urządzeń.

#### <a name="resolution"></a>Rozwiązanie
1. Otwórz [Portal administracyjny usługi Intune](https://portal.azure.com/?Microsoft_Intune=1&Microsoft_Intune_DeviceSettings=true&Microsoft_Intune_Enrollment=true&Microsoft_Intune_Apps=true&Microsoft_Intune_Devices=true#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview) , > **urządzenia** > **wszystkie urządzenia**, i sprawdź liczbę urządzeń zarejestrowanych przez użytkownika.
    > [!NOTE]
    > Należy również mieć zalogowanego użytkownika w [portalu użytkowników usługi Intune](https://portal.manage.microsoft.com/) i sprawdzić zarejestrowane urządzenia. Mogą istnieć urządzenia, które są wyświetlane w [portalu użytkowników usługi Intune](https://portal.manage.microsoft.com/) , ale nie w [portalu administracyjnym usługi Intune](https://portal.azure.com/?Microsoft_Intune=1&Microsoft_Intune_DeviceSettings=true&Microsoft_Intune_Enrollment=true&Microsoft_Intune_Apps=true&Microsoft_Intune_Devices=true#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview), takie urządzenia również liczą się na limit rejestracji urządzeń.
2. Przejdź do pozycji **administracja** > **Zarządzanie urządzeniami przenośnymi** > **reguły rejestracji** > Sprawdź limit rejestracji urządzeń. Domyślnie limit wynosi 15. 
3. Jeśli liczba zarejestrowanych urządzeń osiągnie limit, Usuń niepotrzebne urządzenia lub Zwiększ limit rejestracji urządzeń. Ponieważ każde zarejestrowane urządzenie korzysta z licencji usługi Intune, zalecamy najpierw usunąć niepotrzebne urządzenia.
4. Zarejestruj ponownie urządzenie.

### <a name="workplace-join-failed"></a>Workplace Join nie powiodło się

**Przyczyna:** Aplikacja Portal firmy jest nieaktualna lub uszkodzona.  

#### <a name="resolution"></a>Rozwiązanie
1. Usuń aplikację Portal firmy z urządzenia.
2. Pobierz i zainstaluj aplikację **Microsoft Intune — Portal firmy** ze sklepu **App Store**.
3. Zarejestruj ponownie urządzenie.

### <a name="user-license-type-invalid"></a>Nieprawidłowy typ licencji użytkownika

**Przyczyna:** Użytkownik próbujący zarejestrować urządzenie nie ma prawidłowej licencji usługi Intune.

#### <a name="resolution"></a>Rozwiązanie
1. Przejdź do [Centrum administracyjnego Microsoft 365](https://portal.office.com/adminportal/home#/homepage), a następnie wybierz pozycję **Użytkownicy** > **aktywni użytkownicy**.
2. Wybierz konto użytkownika, którego to dotyczy, > **licencje produktu** > **Edytuj**.
3. Sprawdź, czy przypisano prawidłową licencję usługi Intune do tego użytkownika.
4. Zarejestruj ponownie urządzenie.

### <a name="user-name-not-recognized-this-user-account-is-not-authorized-to-use-microsoft-intune-contact-your-system-administrator-if-you-think-you-have-received-this-message-in-error"></a>Nie rozpoznano nazwy użytkownika. To konto użytkownika nie ma autoryzacji do użycia Microsoft Intune. Skontaktuj się z administratorem systemu, jeśli uważasz, że ten komunikat został wyświetlony z błędem.

**Przyczyna:** Użytkownik próbujący zarejestrować urządzenie nie ma prawidłowej licencji usługi Intune.

1. Przejdź do [Centrum administracyjnego Microsoft 365](https://portal.office.com/adminportal/home#/homepage), a następnie wybierz pozycję **Użytkownicy** > **aktywni użytkownicy**.
2. Wybierz konto użytkownika, którego to dotyczy, a następnie wybierz pozycję **licencje produktu** > **Edytuj**.
3. Sprawdź, czy przypisano prawidłową licencję usługi Intune do tego użytkownika.
4. Zarejestruj ponownie urządzenie.

### <a name="profile-installation-failed-the-new-mdm-payload-does-not-match-the-old-payload"></a>Instalacja profilu nie powiodła się. Nowy ładunek MDM nie jest zgodny ze starym ładunkiem.

**Przyczyna:** Profil zarządzania jest już zainstalowany na urządzeniu.

#### <a name="resolution"></a>Rozwiązanie

1. Otwórz **Ustawienia** na urządzeniu z systemem iOS, > **Ogólne** > **Zarządzanie urządzeniami**.
2. Naciśnij istniejący profil zarządzania i naciśnij pozycję **Usuń zarządzanie**.
3. Zarejestruj ponownie urządzenie.

### <a name="noenrollmentpolicy"></a>NoEnrollmentPolicy

**Przyczyna:** Brak certyfikatu Apple Push Notification Service (APNs), jest on nieprawidłowy lub wygasł.

#### <a name="resolution"></a>Rozwiązanie
Sprawdź, czy do usługi Intune został dodany prawidłowy certyfikat usługi APNs. Aby uzyskać więcej informacji, zobacz [Konfigurowanie zarządzania urządzeniami z systemem iOS i komputerami Mac](https://docs.microsoft.com/intune-classic/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune). 

### <a name="accountnotonboarded"></a>AccountNotOnboarded

**Przyczyna:** Wystąpił problem z certyfikatem usługi Apple Push Notification Service (APNs) skonfigurowanym w usłudze Intune.

#### <a name="resolution"></a>Rozwiązanie
Odnów certyfikat APNs, a następnie zarejestruj ponownie urządzenie.

> [!IMPORTANT]
> Upewnij się, że odnowisz certyfikat usługi APNs. Nie zamieniaj certyfikatu APNs. W przypadku zastąpienia certyfikatu należy ponownie zarejestrować wszystkie urządzenia z systemem iOS w usłudze Intune. 

- Aby odnowić certyfikat usługi APNs w autonomicznej usłudze Intune, zobacz [odnów certyfikat wypychania Apple MDM](apple-mdm-push-certificate-get.md#renew-apple-mdm-push-certificate).
- Aby odnowić certyfikat usługi APNs w hybrydowej usłudze Intune za pomocą Configuration Manager, zobacz [Konfigurowanie hybrydowego zarządzania urządzeniami z systemem iOS za pomocą System Center Configuration Manager i Microsoft Intune](https://docs.microsoft.com/sccm/mdm/deploy-use/enroll-hybrid-ios-mac).
- Aby odnowić certyfikat APNs w pakiecie Office 365, zobacz [Tworzenie certyfikatu APNs dla urządzeń z systemem iOS](https://support.office.com/article/Create-an-APNs-Certificate-for-iOS-devices-522b43f4-a2ff-46f6-962a-dd4f47e546a7).

### <a name="xpc_type_error-connection-invalid"></a>Nieprawidłowe połączenie XPC_TYPE_ERROR

Po włączeniu urządzenia zarządzanego przez program DEP, któremu przypisano profil rejestracji, rejestracja kończy się niepowodzeniem i wyświetlany jest następujący komunikat o błędzie:

```
asciidoc
mobileassetd[83] <Notice>: 0x1a49aebc0 Client connection: XPC_TYPE_ERROR Connection invalid <error: 0x1a49aebc0> { count = 1, transaction: 0, voucher = 0x0, contents = "XPCErrorDescription" => <string: 0x1a49aee18> { length = 18, contents = "Connection invalid" } }
iPhone mobileassetd[83] <Notice>: Client connection invalid (Connection invalid); terminating connection
iPhone com.apple.accessibility.AccessibilityUIServer(MobileAsset)[288] <Notice>: [MobileAssetError:29] Unable to copy asset information from https://mesu.apple.com/assets/ for asset type com.apple.MobileAsset.VoiceServices.CombinedVocalizerVoices
iPhone mobileassetd[83] <Notice>: 0x1a49aebc0 Client connection: XPC_TYPE_ERROR Connection invalid <error: 0x1a49aebc0> { count = 1, transaction: 0, voucher = 0x0, contents = "XPCErrorDescription" => <string: 0x1a49aee18> { length = 18, contents = "Connection invalid" }
```

**Przyczyna:** Wystąpił problem z połączeniem między urządzeniem a usługą DEP firmy Apple.

#### <a name="resolution"></a>Rozwiązanie
Rozwiąż problem z połączeniem lub użyj innego połączenia sieciowego do zarejestrowania urządzenia. Jeśli problem będzie się powtarzać, może być również konieczne skontaktowanie się z firmą Apple.


## <a name="other-issues"></a>Inne problemy

### <a name="dep-enrollment-doesnt-start"></a>Rejestracja w programie DEP nie jest uruchomiona
Po włączeniu urządzenia zarządzanego przez program DEP, któremu przypisano profil rejestracji, proces rejestracji w usłudze Intune nie zostanie zainicjowany.

**Przyczyna:** Profil rejestracji zostanie utworzony przed przekazaniem tokenu DEP do usługi Intune.

#### <a name="resolution"></a>Rozwiązanie

1. Edytuj profil rejestracji. Możesz wprowadzić zmiany w profilu. Celem jest aktualizacja czasu modyfikacji profilu.
2. Synchronizuj urządzenia zarządzane w programie DEP: Otwórz portal usługi Intune, > **administrator** > **Zarządzanie urządzeniami przenośnymi** > **iOS** > **Device Enrollment Program** > **zsynchronizuj teraz**. Żądanie synchronizacji zostanie wysłane do firmy Apple.

### <a name="dep-enrollment-stuck-at-user-login"></a>Rejestracja w programie DEP zablokowana przy logowaniu użytkownika
Po włączeniu urządzenia zarządzanego przez program DEP, któremu przypisano profil rejestracji, początkowa konfiguracja jest umieszczana po wprowadzeniu poświadczeń.

**Przyczyna:** Uwierzytelnianie wieloskładnikowe (MFA) jest włączone. Obecnie uwierzytelnianie wieloskładnikowe nie działa podczas rejestracji na urządzeniach DEP.

#### <a name="resolution"></a>Rozwiązanie
Wyłącz usługę MFA, a następnie ponownie Zarejestruj urządzenie.

## <a name="next-steps"></a>Następne kroki

- [Rozwiązywanie problemów dotyczących rejestrowania urządzeń w usłudze Intune](../troubleshoot-device-enrollment-in-intune.md)
- [Zadaj pytanie na forum usługi Intune](https://social.technet.microsoft.com/Forums/%7Blang-locale%7D/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)
- [Sprawdź Blog zespołu pomocy technicznej Microsoft Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess)
- [Zapoznaj się z blogiem dotyczącym pakietu Microsoft Enterprise Mobility and Security](https://techcommunity.microsoft.com/t5/Azure-Active-Directory-Identity/Announcing-the-public-preview-of-Azure-AD-group-based-license/ba-p/245210)
