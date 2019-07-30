---
title: Rozwiązywanie problemów z instalacją aplikacji
titleSuffix: Microsoft Intune
description: Użyj okienka rozwiązywania problemów w usłudze Microsoft Intune do rozwiązywania problemów z instalacją aplikacji.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/25/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: b613f364-0150-401f-b9b8-2b09470b34f4
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b93fc8bc1bddbae8b1b0bde4f8b8815e8052fb51
ms.sourcegitcommit: 2fa20338bd0236884e1f3fde624cf70da89fd254
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 07/26/2019
ms.locfileid: "68507689"
---
# <a name="troubleshoot-app-installation-issues"></a>Rozwiązywanie problemów z instalacją aplikacji

Na urządzeniach zarządzanych przez oprogramowanie MDM w usłudze Microsoft Intune czasami operacje instalacji aplikacji mogą zakończyć się niepowodzeniem. W takich sytuacjach zrozumienie przyczyny niepowodzenia lub rozwiązanie problemu może okazać się wyzwaniem. Usługa Microsoft Intune udostępnia szczegóły niepowodzeń instalacji aplikacji, które ułatwiają operatorom pomocy technicznej i administratorom usługi Intune wyświetlanie informacji o aplikacji pomocnych podczas obsługi żądań użytkowników dotyczących pomocy. Okienko rozwiązywania problemów w usłudze Intune zawiera szczegóły niepowodzenia, w tym szczegółowe informacje o aplikacjach zarządzanych na urządzeniu użytkownika. W obszarze każdego urządzenia w okienku **Aplikacje zarządzane** są dostępne kompleksowe szczegóły cyklu eksploatacji. Można zapoznać się z problemami dotyczącymi instalacji, takimi jak występujące podczas tworzenia, modyfikowania i wybierania aplikacji oraz dostarczania jej na urządzenie. 

## <a name="app-troubleshooting-details"></a>Szczegóły dotyczące rozwiązywania problemów z aplikacją

Usługa Intune dostarcza szczegółowe informacje na temat rozwiązywania problemów z aplikacją w oparciu o aplikacje zainstalowane na urządzeniu określonego użytkownika.

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. W okienku **Intune** wybierz pozycję **Rozwiązywanie problemów**.
4. Kliknij pozycję **Wybierz użytkownika**, aby wybrać użytkownika na potrzeby rozwiązywania problemów. Zostanie wyświetlone okienko **Wybieranie użytkowników**.
5. Wybierz użytkownika przez wpisanie jego nazwy lub adresu e-mail. Kliknij pozycję **Wybierz** w dolnej części okienka. Informacje dotyczące rozwiązywania problemów użytkownika zostaną wyświetlone w okienku **Rozwiązywanie problemów**. 
6. Wybierz urządzenie, którego problemy chcesz rozwiązać, z listy **Urządzenia**.
    ![Okienku Rozwiązywanie problemów w usłudze Intune.](media/troubleshoot-app-install-01.png)
7. Wybierz pozycję **Aplikacje zarządzane** w okienku wybranego urządzenia. Zostanie wyświetlona lista aplikacji zarządzanych.
    ![Szczegółowe informacje dotyczące określonego urządzenia zarządzanego przez usługę Intune.](media/troubleshoot-app-install-02.png)
8. Z listy wybierz aplikację, dla której **Stan instalacji** wskazuje niepowodzenie.
    ![Wybrana aplikacja z wyświetlonymi szczegółami niepowodzenia instalacji.](media/troubleshoot-app-install-03.png)

    > [!Note]  
    > Tę samą aplikację można przypisać do wielu grup, ale z inną zamierzoną akcją (intencją) dla aplikacji. Na przykład rozpoznaną intencją aplikacji będzie wartość **wykluczona**, jeśli aplikacja została wykluczona w przypadku użytkownika podczas przypisywania aplikacji. Aby uzyskać więcej informacji, zobacz [Jak są rozwiązywane konflikty intencji aplikacji](apps-deploy.md#how-conflicts-between-app-intents-are-resolved).<br><br>
    > W przypadku wystąpienia błędu instalacji wymaganej aplikacji użytkownik lub dział pomocy technicznej będzie w stanie zsynchronizować urządzenie i ponowić próbę instalacji aplikacji.

Szczegóły błędu instalacji aplikacji będą wskazywać problem. Tych szczegółów można użyć, aby określić najlepszą akcję do podjęcia w celu rozwiązania problemu. Aby uzyskać więcej informacji na temat rozwiązywania problemów z instalacją aplikacji, zobacz sekcję [Błędy instalacji aplikacji](troubleshoot-app-install.md#app-installation-errors).

> [!Note]  
> Dostęp do okienka **Rozwiązywanie problemów** można też uzyskać przez przejście w przeglądarce do strony [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting).

## <a name="user-group-targeted-app-installation-does-not-reach-device"></a>Instalacja aplikacji dostosowanej do grupy użytkowników nie dociera do urządzenia
Jeśli masz problemy z instalowaniem aplikacji, należy wziąć pod uwagę następujące działania:
- Jeśli aplikacja nie jest wyświetlana w Portal firmy, upewnij się, że aplikacja jest wdrażana z zamiarą **dostępne** i że użytkownik uzyskuje dostęp do Portal firmy za pomocą typu urządzenia obsługiwanego przez aplikację.
- W przypadku urządzeń z systemem Windows BYOD użytkownik musi dodać do urządzenia konto służbowe.
- Sprawdź, czy użytkownik przekracza limit urządzeń usługi AAD:
  1. Przejdź do [Azure Active Directory ustawień urządzenia](https://portal.azure.com/#blade/Microsoft_AAD_IAM/DevicesMenuBlade/DeviceSettings/menuId).
  2. Zanotuj wartość ustawioną dla **Maksymalna liczba urządzeń na użytkownika**.
  3. Przejdź do [Azure Active Directory użytkowników](https://portal.azure.com/#blade/Microsoft_AAD_IAM/UsersManagementMenuBlade/AllUsers).
  4. Wybierz użytkownika, którego dotyczy ten użytkownik, a następnie kliknij pozycję **urządzenia**.
  5. Jeśli użytkownik ma ustawiony limit, Usuń wszystkie nieodświeżone rekordy, które nie są już potrzebne.
- W przypadku urządzeń programu DEP w systemie iOS upewnij się, że użytkownik jest wymieniony jako **zarejestrowany przez użytkownika** w bloku przegląd urządzeń w usłudze Intune. Jeśli jest wyświetlana wartość NA, należy wdrożyć zasady konfiguracji dla Intune — Portal firmy. Aby uzyskać więcej informacji, zobacz [Konfigurowanie aplikacji Portal firmy](https://docs.microsoft.com/intune/app-configuration-policies-use-ios#configure-the-company-portal-app-to-support-ios-dep-devices).

## <a name="win32-app-installation-troubleshooting"></a>Rozwiązywanie problemów z instalacją aplikacji Win32

Wybierz aplikację Win32 wdrożoną za pomocą rozszerzenia do zarządzania usługi Intune. Jeśli instalacja aplikacji Win32 kończy się niepowodzeniem, możesz zaznaczyć opcję **Zbieraj dzienniki**. 

> [!IMPORTANT]
> Opcja **Zbieraj dzienniki** nie będzie dostępna, jeśli aplikacja Win32 została pomyślnie zainstalowana na urządzeniu.<p>Aby móc zbierać informacje dzienników aplikacji Win32, na kliencie z systemem Windows musi być zainstalowane rozszerzenie do zarządzania usługi Intune. Rozszerzenie zarządzania usługi Intune jest instalowane, gdy skrypt programu PowerShell lub aplikacja Win32 jest wdrażana do grupy zabezpieczeń użytkowników lub urządzeń. Aby uzyskać więcej informacji, zobacz [Intune Management extension — Prerequisites (Rozszerzenie do zarządzania usługi Intune — wymagania wstępne)](intune-management-extension.md#prerequisites).

### <a name="collect-log-file"></a>Zbieranie plików dziennika

Aby zbierać dzienniki instalacji aplikacji Win32, najpierw wykonaj czynności przedstawione w sekcji [Szczegóły dotyczące rozwiązywania problemów z aplikacją](troubleshoot-app-install.md#app-troubleshooting-details). Następnie wykonaj następujące czynności:

1. Kliknij opcję **Zbieraj dzienniki** w bloku **Szczegóły instalacji**.

    <image alt="Win32 app installation details - Collect log option" src="media/troubleshoot-app-install-04.png" width="500" />

2. Podaj ścieżki do plików oraz nazwy plików dziennika, aby rozpocząć proces zbierania plików dziennika, a następnie kliknij przycisk **OK**.
    
    > [!NOTE]
    > Zbieranie dzienników potrwa mniej niż dwie godziny. Obsługiwane typy plików to *log, txt, dmp, cab, zip, xml, evtx i evtl*. Maksymalna liczba ścieżek do plików to 25.

3. Po zebraniu plików dziennika możesz je pobrać, wybierając link **dzienniki**.

    <image alt="Win32 app log details - Download logs" src="media/troubleshoot-app-install-05.png" width="500" />

    > [!NOTE]
    > Zostanie wyświetlone powiadomienie o powodzeniu zbierania dzienników aplikacji.

#### <a name="win32-log-collection-requirements"></a>Wymagania dotyczące zbierania dzienników Win32

Aby możliwe było zbieranie plików dziennika, muszą zostać spełnione określone wymagania:

- Należy podać pełną ścieżkę do pliku. 
- Można podać zmienne środowiskowe na potrzeby zbierania dzienników, na przykład:<br>
  *%PROGRAMFILES%, %PROGRAMDATA% %PUBLIC%, %WINDIR%, %TEMP%, %TMP%*
- Dozwolone są tylko dokładne rozszerzenia plików, na przykład:<br>
  *log, txt, dmp, cab, .zip, .xml*
- Maksymalnie można przekazać 60 MB danych lub 25 plików, w zależności od tego, który limit zostanie wyczerpany wcześniej. 
- Opcja zbierania dzienników instalacji aplikacji Win32 jest dostępna w przypadku aplikacji z intencją przypisywania aplikacji „wymagane”, „dostępne” oraz „odinstaluj”.
- Przechowywane dzienniki są szyfrowane, aby chronić wszelkie dane osobowe zawarte w dziennikach.
- Otwierając bilet pomocy technicznej dotyczący błędów aplikacji Win32, dołącz do niego odpowiednie dzienniki błędów, korzystając z powyższych instrukcji.

## <a name="app-installation-errors"></a>Błędy instalacji aplikacji

Następujące komunikaty o błędach oraz opisy zapewniają szczegółowe informacje o błędach instalacji w systemie Android i iOS. 

### <a name="android-errors"></a>Błędy systemu Android

|    Komunikat o błędzie/kod    |    Opis    |
|----------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Instalowanie aplikacji nie powiodło się. (0xC7D14FB5)    |    Ten komunikat o błędzie jest wyświetlany, gdy usługa Intune nie może ustalić głównej przyczyny błędu instalacji aplikacji dla systemu Android. Podczas awarii system Android nie dostarczył żadnych informacji.       Ten błąd jest zwracany, gdy pobieranie pakietu APK zakończyło się pomyślnie, ale instalacja aplikacji nie powiodła się. Jego najczęstszą przyczyną może być nieprawidłowy plik APK, którego nie można zainstalować na urządzeniu. Możliwą przyczyną może być też zablokowanie instalacji aplikacji przez funkcję Google Play Protect ze względów bezpieczeństwa. Inna możliwa przyczyna tego błędu może polegać na tym, że urządzenie nie obsługuje danej aplikacji. Na przykład jeśli aplikacja wymaga interfejsu API w wersji 21 lub nowszej, a urządzenia aktualnie ma interfejs API w wersji 19.         Usługa Intune zwraca ten błąd dla urządzeń DA i KNOX i chociaż może zostać wyświetlone powiadomienie, które można kliknąć, aby ponowić próbę, to jeśli występuje problem z pakietem APK, kontynuacja nigdy nie nastąpi ze względu na niepowodzenie. Jeśli aplikacja jest aplikacją dostępną, powiadomienie można odrzucić. Jeśli jednak dana aplikacja jest wymagana, nie można go odrzucić.        |
|    Anulowano instalowanie aplikacji, ponieważ plik instalacyjny (APK) został usunięty po pobraniu, ale przed instalacją. (0xC7D14FBA)    |    Pobieranie pakietu APK zakończyło się pomyślnie, ale przed zainstalowaniem aplikacji plik został usunięty z urządzenia. Może się to zdarzyć, jeśli między pobraniem a instalacją upłynęło sporo czasu. Na przykład użytkownik anulował pierwotną instalację, odczekał jakiś czas, a następnie kliknął powiadomienie, aby spróbować ponownie.         Ten komunikat o błędzie jest zwracany jedynie dla scenariuszy DA. Scenariusze KNOX mogą być realizowane w trybie cichym. Powiadomienie o ponownej próbie jest wyświetlane, aby użytkownik mógł zaakceptować, zamiast anulować. Jeśli aplikacja jest aplikacją dostępną, powiadomienie można odrzucić. Jeśli jednak dana aplikacja jest wymagana, nie można go odrzucić.    |
|    Anulowano instalowanie aplikacji, ponieważ proces został uruchomiony ponownie podczas instalacji. (0xC7D14FBB)    |    Urządzenie zostało uruchomione ponownie podczas procesu instalacji pliku APK, co spowodowało anulowanie instalacji.        Ten komunikat o błędzie jest zwracany dla urządzeń DA i KNOX. Usługa Intune wyświetla powiadomienie, które użytkownik może kliknąć, aby przeprowadzić ponowną próbę. Jeśli aplikacja jest aplikacją dostępną, powiadomienie można odrzucić. Jeśli jednak dana aplikacja jest wymagana, nie można go odrzucić.    |
|    Aplikacja nie została wykryta po pomyślnym ukończeniu instalacji. (0x87D1041C)    |    Użytkownik jawnie odinstalował aplikację. Ten błąd nie jest zwracany przez klienta. Jest od generowany wtedy, gdy aplikacja została w pewnym momencie zainstalowana, ale następnie użytkownik ją odinstalował. Ten błąd powinien być wyświetlany tylko w przypadku wymaganych aplikacji. Użytkownicy mogą odinstalowywać aplikacje, które nie są wymagane. Ten błąd może wystąpić tylko na urządzeniach DA. System KNOX blokuje dezinstalację aplikacji zarządzanych.       Przy następnej synchronizacji na urządzeniu zostanie ponownie opublikowane powiadomienie, aby użytkownik przeprowadził instalację.   Użytkownik może zignorować to powiadomienie. Błąd będzie stale zgłaszany, aż do momentu, gdy użytkownik zainstaluje aplikację.    |
|    Pobieranie nie powiodło się z powodu nieoczekiwanego błędu. (0xC7D14FB2)    |    Ten błąd występuje, gdy pobieranie nie powiedzie się. Ten błąd często występuje z powodu problemów z siecią Wi-Fi lub powolnego połączenia.       Ten błąd jest zwracany jedynie dla scenariuszy DA. W przypadku scenariuszy KNOX użytkownik nie otrzymuje monitu o instalację, ponieważ można ją przeprowadzić w trybie cichym. Usługa Intune wyświetla powiadomienie, które użytkownik może kliknąć, aby spróbować ponownie. Jeśli aplikacja jest aplikacją dostępną, powiadomienie można odrzucić. Jeśli jednak dana aplikacja jest wymagana, nie można go odrzucić.    |
|    Pobieranie nie powiodło się z powodu nieoczekiwanego błędu. Zasada zostanie ponowiona przy kolejnej synchronizacji urządzenia. (0xC7D15078)    |    Ten błąd występuje, gdy pobieranie nie powiedzie się. Ten błąd często występuje z powodu problemów z siecią Wi-Fi lub powolnego połączenia.       Ten błąd jest zwracany jedynie dla scenariuszy DA. W przypadku scenariuszy KNOX użytkownik nie otrzymuje monitu o instalację, ponieważ można ją przeprowadzić w trybie cichym.    |
|    Użytkownik końcowy anulował instalację aplikacji. (0xC7D14FB1)    |    Użytkownik jawnie odinstalował aplikację. Ten błąd jest zwracany, gdy użytkownik anuluje działanie instalacji systemu operacyjnego Android. Użytkownik kliknął przycisk anulowania po wyświetleniu monitu o instalacji systemu operacyjnego, lub kliknął poza monitem.        Ten błąd jest zwracany jedynie dla scenariuszy DA. W przypadku scenariuszy KNOX użytkownik nie otrzymuje monitu o instalację, ponieważ można ją przeprowadzić w trybie cichym. Usługa Intune wyświetla powiadomienie, które użytkownik może kliknąć, aby spróbować ponownie. Jeśli aplikacja jest aplikacją dostępną, powiadomienie można odrzucić. Jeśli jednak dana aplikacja jest wymagana, nie można go odrzucić.    |
|    Proces pobierania pliku został nieoczekiwanie zatrzymany. (0xC7D15015)    |    System operacyjny zatrzymał proces pobierania przed ukończeniem. Ten błąd może wystąpić, gdy poziom naładowania baterii urządzenia jest niski lub gdy pobieranie trwa zbyt długo.       Ten błąd jest zwracany jedynie dla scenariuszy DA. W przypadku scenariuszy KNOX użytkownik nie otrzymuje monitu o instalację, ponieważ można ją przeprowadzić w trybie cichym. Usługa Intune wyświetla powiadomienie, które użytkownik może kliknąć, aby spróbować ponownie. Jeśli aplikacja jest aplikacją dostępną, powiadomienie można odrzucić. Jeśli jednak dana aplikacja jest wymagana, nie można go odrzucić.    |
|    Usługa pobierania pliku została nieoczekiwanie zatrzymana. Zasada zostanie ponowiona przy kolejnej synchronizacji urządzenia. (0xC7D1507C)    |    System operacyjny zatrzymał proces pobierania przed ukończeniem. Ten błąd może wystąpić, gdy poziom naładowania baterii urządzenia jest niski lub gdy pobieranie trwa zbyt długo.       Ten błąd jest zwracany jedynie dla scenariuszy DA. W przypadku scenariuszy KNOX użytkownik nie otrzymuje monitu o instalację, ponieważ można ją przeprowadzić w trybie cichym.    |

### <a name="ios-errors"></a>Błędy systemu iOS

| Komunikat o błędzie/kod | Opis/wskazówki dotyczące rozwiązywania problemów |
|------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| (0x87D12906) | Agent MDM firmy Apple zwrócił informację, że polecenie instalacji nie powiodło się. |
| (0x87D1313C) | Utracono połączenie sieciowe, gdy zaktualizowany adres URL usługi pobierania został wysłany na urządzenie. W szczególności nie można odnaleźć serwera z określoną nazwą hosta. |
| Urządzenie z systemem iOS jest aktualnie zajęte. (0x87D11388) | Urządzenie z systemem iOS było zajęte, co spowodowało wystąpienie błędu. |
| Instalacja aplikacji nie powiodła się. (0x87D13B64) | Wystąpił błąd instalacji aplikacji. Do rozwiązania tego problemu są wymagane dzienniki programu XCODE. |
| Aplikacja jest zarządzana, ale wygasła lub została usunięta przez użytkownika. (0x87D13B66) | Użytkownik jawnie odinstalował aplikację. Może być też tak, że aplikacja wygasła, ale nie można jej pobrać, lub wykrywanie aplikacji jest niezgodne z odpowiedzią z urządzenia.   Ponadto ten błąd może wystąpić na podstawie usterki platformy iOS 9.2.2. |
| Zaplanowano zainstalowanie tej aplikacji, ale sfinalizowanie transakcji wymaga kodu realizacji. (0x87D13B60) | Ten błąd zazwyczaj występuje w przypadku aplikacji ze sklepu dla systemu iOS, które są płatne. |
| Aplikacja nie została wykryta po pomyślnym ukończeniu instalacji.   (0x87D1041C) | Proces wykrywania aplikacji jest niezgodny z odpowiedzią z urządzenia. |
| Użytkownik odrzucił ofertę zainstalowania aplikacji. (0x87D13B62) | Podczas początkowej instalacji aplikacji użytkownik kliknął przycisk Anuluj. |
| Użytkownik odrzucił ofertę zaktualizowania aplikacji. (0x87D13B63) | Użytkownik końcowy kliknął przycisk Anuluj podczas procesu aktualizacji. |
| Nieznany błąd (0x87D103E8) | Wystąpił nieznany błąd instalacji aplikacji. Jest to błąd wynikowy, gdy nie wystąpią inne błędy. |
| Aplikacje VPP można instalować tylko na udostępnionym urządzeniu iPad (-2016330861). | Aby móc zainstalować aplikacje na udostępnionym tablecie iPad, należy uzyskać je w ramach programu Apple Volume Purchase Program. |
| Nie można instalować aplikacji, gdy sklep App Store jest wyłączony (-2016330860).  | Aby użytkownik mógł zainstalować aplikację, musi być włączony sklep App Store. |
| Nie można znaleźć licencji VPP dla aplikacji (-2016330859).  | Spróbuj odwołać i ponownie przypisać licencję do aplikacji. |
| Nie można instalować aplikacji systemu przy użyciu dostawcy MDM (-2016330858). | Instalowanie aplikacji wstępnie zainstalowanych przez system operacyjny iOS nie jest obsługiwane. |
| Nie można instalować aplikacji, gdy urządzenie jest w trybie zgubienia (-2016330857). | W trybie zgubienia wszystkie sposoby korzystania z urządzenia są zablokowane.   Aby móc instalować aplikacje, wyłącz tryb zgubienia. |
| Nie można instalować aplikacji, gdy urządzenie jest w trybie kiosku (-2016330856). | Aby móc instalować aplikacje, spróbuj dodać to urządzenie do grupy wykluczonych w zasadach konfiguracji trybu kiosku. |
| Na tym urządzeniu nie można instalować 32-bitowych aplikacji (-2016330852). | Urządzenie nie obsługuje instalowania aplikacji 32-bitowych. Spróbuj wdrożyć 64-bitową wersję aplikacji. |
| Użytkownik musi się zalogować w sklepie App Store (-2016330855). | Aby móc zainstalować aplikację, użytkownik musi zalogować się w sklepie App Store. |
| Nieznany problem. Spróbuj ponownie (-2016330854). | Instalacja aplikacji nie powiodła się z nieznanej przyczyny.   Spróbuj ponownie później. |
| Instalacja aplikacji nie powiodła się. Usługa Intune ponowi próbę przy następnej synchronizacji urządzenia (-2016330853). | Podczas instalacji aplikacji wystąpił błąd urządzenia. Zsynchronizuj urządzenie, aby ponowić próbę instalacji aplikacji. |

### <a name="other-installation-errors"></a>Inne błędy instalacji

|    Komunikat o błędzie/kod    |    Opis    |
|-----------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    0x80073CFF, 0x80CF201C (błąd klienta)    |    Aby zainstalować tę aplikację, wymagany jest system z obsługą ładowania bezpośredniego. Upewnij się, że pakiet aplikacji został podpisany przy użyciu zaufanego podpisu i zainstalowany na urządzeniu przyłączonym do domeny, które ma włączone zasady **AllowAllTrustedApps**, lub na urządzeniu, które ma licencję ładowania bezpośredniego systemu Windows z włączonymi zasadami **AllowAllTrustedApps**. Aby uzyskać więcej informacji, zobacz temat [Troubleshooting packaging, deployment, and query of Windows Store apps](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting) (Rozwiązywanie problemów z pakowaniem, wdrażaniem i zapytaniami aplikacji ze sklepu Windows Store).     |
|    0x80073CF0    |    Nie można otworzyć pakietu. Możliwe przyczyny:<ul><li> Pakiet jest niepodpisany.</li><li> Nazwa wydawcy jest niezgodna z podmiotem certyfikatu podpisywania.</li></ul> Sprawdź dziennik zdarzeń **AppxPackagingOM**, aby uzyskać informacje. Aby uzyskać więcej informacji, zobacz temat [Troubleshooting packaging, deployment, and query of Windows Store apps](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting) (Rozwiązywanie problemów z pakowaniem, wdrażaniem i zapytaniami aplikacji ze sklepu Windows Store).    |
|    0x80073CF3    |    Niepowodzenie aktualizacji, błąd weryfikacji zależności lub konflikt pakietu. Możliwe przyczyny:<ul><li> Przychodzący pakiet powoduje konflikt z zainstalowanym pakietem.</li><li> Określona zależność pakietu nie została odnaleziona.</li><li> Pakiet nie obsługuje poprawnej architektury procesora.</li></ul> Sprawdź dziennik zdarzeń **AppXDeployment-Server**, aby uzyskać informacje. Aby uzyskać więcej informacji, zobacz temat [Troubleshooting packaging, deployment, and query of Windows Store apps](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting) (Rozwiązywanie problemów z pakowaniem, wdrażaniem i zapytaniami aplikacji ze sklepu Windows Store).    |
|    0x80073CFB    |    Dany pakiet jest już zainstalowany i jego ponowna instalacja została zablokowana. Ten błąd może pojawić się w przypadku instalowania pakietu, który nie jest identyczny z pakietem już zainstalowanym. Upewnij się , że podpis cyfrowy jest również częścią pakietu. Jeśli pakiet został ponownie skompilowany lub ponownie podpisany, nie jest już bitowo identyczny z wcześniej zainstalowanym pakietem. Dostępne są następujące dwie opcje naprawienia tego błędu:<ul><li> Zwiększenie numeru wersji aplikacji, a następnie ponowne skompilowanie i ponowne podpisanie pakietu.</li><li> Usunięcie starego pakietu dla każdego użytkownika w systemie przed zainstalowaniem nowego pakietu.</li></ul> Aby uzyskać więcej informacji, zobacz temat [Troubleshooting packaging, deployment, and query of Windows Store apps](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting) (Rozwiązywanie problemów z pakowaniem, wdrażaniem i zapytaniami aplikacji ze sklepu Windows Store).    |
|    0x87D1041C    |    Instalacja aplikacji zakończyła się pomyślnie, ale nie wykryto aplikacji. Aplikacja została pomyślnie wdrożona przez usługę Intune, a następnie odinstalowana. Możliwe przyczyny odinstalowania aplikacji:<ul><li> Użytkownik końcowy odinstalował aplikację.</li><li> Informacje o tożsamości w pakiecie są niezgodne z danymi zgłaszanymi przez urządzenie w przypadku nieprawidłowych aplikacji.</li><li>W przypadku samoaktualizujących się instalatorów MSI wersja produktu nie odpowiada informacjom o aplikacji po przeprowadzeniu aktualizacji poza usługą Intune.</li></ul> Poinstruuj użytkownika, aby ponownie zainstalował aplikację z portalu firmy. Pamiętaj, że wymagane aplikacje zostaną automatycznie zainstalowane ponownie po następnym zaewidencjonowaniu urządzenia.    |
|    0x8000FFFF    |    Podczas instalacji wystąpił nieoczekiwany błąd. Zapoznaj się z dziennikami instalacji, aby uzyskać dodatkowe informacje.    |

## <a name="troubleshooting-apps-from-the-microsoft-store"></a>Rozwiązywanie problemów z aplikacjami ze Sklepu Microsoft

Informacje zawarte w temacie [Troubleshooting packaging, deployment, and query of Microsoft Store apps (Tworzenie pakietów, wdrażanie i zapytania aplikacji ze Sklepu Microsoft)](https://msdn.microsoft.com/library/windows/desktop/hh973484.aspx) pomagają w rozwiązywaniu typowych problemów, które mogą wystąpić podczas instalowania aplikacji ze Sklepu Microsoft za pomocą usługi Intune lub w inny sposób.

## <a name="app-troubleshoooting-resources"></a>Zasoby troubleshoooting aplikacji
- [Wdrażanie programu Visio i projektu w ramach wdrożenia pakietu Office Pro Plus](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Deploying-Visio-and-Project-as-part-of-your-Office/ba-p/701795)
- [Podejmowanie działań w celu zapewnienia, że aplikacje MSfB wdrożone przy użyciu instalacji usługi Intune w systemie Windows 10 1903](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Take-Action-to-Ensure-MSfB-Apps-deployed-through/ba-p/658864)
- [Rozwiązywanie problemów z wdrożeniami aplikacji MSI w Microsoft Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Troubleshooting-MSI-App-deployments-in-Microsoft/ba-p/359125)
- [Najlepsze rozwiązania dotyczące dystrybucji oprogramowania do klasycznego komputera z systemem Windows w usłudze Intune](https://support.microsoft.com/en-us/help/2583929/best-practices-for-intune-software-distribution-to-windows-pc)

## <a name="next-steps"></a>Następne kroki

- Aby uzyskać dodatkowe informacje dotyczące rozwiązywania problemów z usługą Intune, zobacz [Korzystanie z portalu rozwiązywania problemów, aby pomóc użytkownikom w firmie](help-desk-operators.md). 
- Dowiedz się więcej o wszelkich znanych problemach w usłudze Microsoft Intune. Aby uzyskać więcej informacji, zobacz [powodzenie klienta usługi Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess).
- Potrzebujesz dodatkowej pomocy? Zobacz [Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](get-support.md).
