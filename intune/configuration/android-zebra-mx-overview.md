---
title: Używanie funkcji Zebra Mobility Extensions na urządzeniach z systemem Android w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Usługa Microsoft Intune umożliwia zarządzanie urządzeniami Zebra z systemem Android i używanie ich za pomocą funkcji Zebra Mobility Extensions (MX). Zobacz wszystkie czynności, w tym instalowanie aplikacji Portal firmy, ładowanie bezpośrednie aplikacji, przypisywanie roli administratora urządzenia, tworzenie profilu StageNow i nie tylko.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: ''
ms.technology: ''
ms.assetid: ''
ms.reviewer: jieyan
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 829d8f6b2691f91c14029e4f29e2ef11b070e596
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "74059618"
---
# <a name="use-and-manage-zebra-devices-with-zebra-mobility-extensions-in-microsoft-intune"></a>Używanie urządzeń Zebra i zarządzanie nimi za pomocą funkcji Zebra Mobility Extensions w usłudze Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Usługa Intune obejmuje bogaty zestaw funkcji, takich jak zarządzanie aplikacjami i konfigurowanie ustawień urządzenia. Za pomocą tych wbudowanych funkcji i ustawień można zarządzać urządzeniami z systemem Android wyprodukowanymi przez firmę Zebra Technologies, zwanymi także urządzeniami Zebra.

Na urządzeniach z systemem Android profile funkcji **Mobility Extensions (MX)** firmy Zebra umożliwiają dostosowywanie lub dodawanie ustawień specyficznych dla urządzeń Zebra.

W tym artykule przedstawiono sposób używania funkcji Zebra Mobility Extensions (MX) w urządzeniach Zebra w usłudze Microsoft Intune.

Ta funkcja ma zastosowanie do:

- Android

Twoja firma może używać urządzeń Zebra na potrzeby handlu detalicznego, na etapie produkcji i nie tylko. Na przykład jesteś sprzedawcą detalicznym i Twoje środowisko zawiera tysiące urządzeń przenośnych Zebra używanych przez przedstawicieli handlowych. Usługa Intune ułatwia zarządzanie tymi urządzeniami w ramach swojego rozwiązania do zarządzania urządzeniami mobilnymi (MDM).

Przy użyciu usługi Intune można zarejestrować urządzenia Zebra, aby wdrożyć aplikacje biznesowe w urządzeniach. Profile konfiguracji urządzenia umożliwiają tworzenie profilów funkcji MX do zarządzania ustawieniami specyficznymi dla urządzeń Zebra.

> [!NOTE]
> Domyślnie interfejsy API zebry MX nie są blokowane na urządzeniach. Zanim urządzenie zostanie zarejestrowane w usłudze Intune, możliwe jest złośliwe bezpieczeństwo urządzenia. Jeśli urządzenie jest w stanie czystym, sugerujemy zablokowanie interfejsów API MX przy użyciu programu Access Manager (AccessMgr). Możesz na przykład wybrać, że tylko Portal firmy aplikacji i aplikacji, którym ufasz, są dozwolone wywołania interfejsów API MX.
>
> Aby uzyskać więcej informacji, zobacz [blokowanie urządzenia](https://developer.zebra.com/community/home/blog/2017/04/11/locking-down-your-device) w witrynie sieci Web zebry.

## <a name="before-you-begin"></a>Przed rozpoczęciem

- Upewnij się, że masz najnowszą wersję aplikacji klasycznej StageNow firmy Zebra Technologies.
- Sprawdź [pełną tabelę funkcji MX firmy Zebra](http://techdocs.zebra.com/mx/compatibility) (powoduje otwarcie witryny firmy Zebra), aby upewnić się, że tworzone przez Ciebie profile są zgodne z modelem, wersją systemu operacyjnego i wersją funkcji MX urządzenia.
- Niektóre urządzenia, takie jak TC20/25, nie obsługują wszystkich dostępnych funkcji MX w rozwiązaniu StageNow. Sprawdź [tabelę funkcji firmy Zebra](http://techdocs.zebra.com/mx/tc2x/) (powoduje otwarcie witryny firmy Zebra), aby uzyskać zaktualizowane informacje o obsłudze.

## <a name="step-1-install-the-latest-company-portal-app"></a>Krok 1. Instalowanie najnowszej wersji aplikacji Portal firmy

Na urządzeniu otwórz magazyn Google Play. Pobierz i zainstaluj aplikację Portal firmy usługi Intune z firmy Microsoft. Po zainstalowaniu ze sklepu Google Play aplikacja Portal firmy automatycznie pobiera aktualizacje i poprawki.

Jeśli sklep Google Play jest niedostępny, pobierz aplikację [Portal firmy usługi Microsoft Intune dla systemu Android](https://www.microsoft.com/download/details.aspx?id=49140) (powoduje otwarcie innej witryny firmy Microsoft) i [załaduj ją bezpośrednio](#sideload-the-company-portal-app) (w tym artykule). W przypadku tej metody instalacji aplikacja nie otrzymuje automatycznie aktualizacji i poprawek. Należy regularnie aktualizować aplikację i ręcznie stosować do niej poprawki.

### <a name="sideload-the-company-portal-app"></a>Ładowanie bezpośrednie aplikacji Portal firmy

Ładowanie bezpośrednie występuje, gdy nie instalujesz aplikacji za pomocą sklepu Google Play. Aby załadować bezpośrednio aplikację Portal firmy, użyj rozwiązania StageNow. 

Poniżej przedstawiono omówienie. Szczegółowe informacje można znaleźć w dokumentacji firmy Zebra. Pomocny może być zasób [Rejestrowanie w usłudze MDM za pomocą rozwiązania StageNow](http://techdocs.zebra.com/stagenow/3-1/Profiles/enrollmdm/) (powoduje otwarcie witryny firmy Zebra).

1. W rozwiązaniu StageNow utwórz profil **Rejestracja w usłudze MDM**.
2. W obszarze **Wdrożenie** wybierz opcję pobrania pliku agenta usługi MDM.
3. Dla kroków **Obsługa aplikacji** i **Pobieranie konfiguracji** ustaw wartość **Nie**.
4. W obszarze **Pobieranie usługi MDM**, wybierz pozycję **Przenieś/kopiuj plik**. Dodaj źródło i cel pakietu Portalu firmy dla systemu Android (APK).
5. W obszarze **Uruchamianie usługi MDM** pozostaw wartości domyślne. Dodaj następujące szczegóły:

    - **Nazwa pakietu**: `com.microsoft.windowsintune.companyportal`
    - **Nazwa klasy**: `com.microsoft.windowsintune.companyportal.views.SplashActivity`

Kontynuuj, aby opublikować profil, i użyj go z aplikacją StageNow w urządzeniu. Aplikacja Portal firmy jest zainstalowana i otwarta w urządzeniu.

> [!TIP]
> Aby uzyskać więcej informacji na temat rozwiązania StageNow i jego przeznaczenia, zobacz [Przemieszczanie urządzeń z systemem Android dla rozwiązania StageNow](https://www.zebra.com/us/en/products/software/mobile-computers/mobile-app-utilities/stagenow.html) (powoduje otwarcie witryny firmy Zebra).

## <a name="step-2-confirm-the-company-portal-app-has-device-administrator-role"></a>Krok 2. Potwierdzanie, że aplikacja Portal firmy ma rolę administratora urządzenia

Aplikacja Portal firmy wymaga uprawnień administratora urządzenia do zarządzania urządzeniami z systemem Android. Aby można było uaktywnić rolę administratora urządzenia, niektóre urządzenia Zebra zawierają interfejs użytkownika. Jeśli urządzenie zawiera interfejs użytkownika, w aplikacji Portal firmy jest wyświetlany monit dla użytkownika końcowego o udzielenie uprawnień administratora urządzenia podczas [rejestracji](#step-3-enroll-the-device-in-to-intune) (w tym artykule).

Jeśli interfejs użytkownika jest niedostępny, użyj **Menedżera DevAdmin** w rozwiązaniu StageNow, aby utworzyć profil, który ręcznie udziela uprawnień administratora urządzenia do aplikacji Portal firmy.

Poniżej przedstawiono omówienie. Szczegółowe informacje można znaleźć w dokumentacji firmy Zebra. 
Pomocny może być zasób [Ustawianie tryby wymiany baterii jako administrator urządzenia](https://zebratechnologies.force.com/s/article/Set-Battery-Swap-Mode-as-Device-Administrator-using-StageNow-Tool) (powoduje otwarcie witryny firmy Zebra).

1. W rozwiązaniu StageNow utwórz profil i wybierz pozycję **Tryb Xpert**.
2. Dodaj **menedżera DevAdmin** do profilu.
3. W polu **Akcja administracyjna urządzenia** ustaw wartość **Włącz jako administrator urządzenia**.
4. W polu **Nazwa pakietu administracyjnego urządzenia** ustaw wartość `com.microsoft.windowsintune.companyportal`.
5. W polu **Nazwa klasy administracyjnej urządzenia** ustaw wartość `com.microsoft.omadm.client.PolicyManagerReceiver`.

Kontynuuj, aby opublikować profil, i użyj go z aplikacją StageNow w urządzeniu. Aplikacji Portal firmy udzielono uprawnienia roli administratora urządzenia.

## <a name="step-3-enroll-the-device-in-to-intune"></a>Krok 3. Rejestrowanie urządzenia w usłudze Intune

Po wykonaniu dwóch pierwszych kroków aplikacja Portal firmy jest zainstalowana w urządzeniu. Urządzenie jest gotowe do rejestracji w usłudze Intune.

Instrukcje można znaleźć na stronie [Rejestrowanie urządzeń z systemem Android](../enrollment/android-enroll.md). Jeśli masz wiele urządzeń Zebra, warto użyć [konta menedżera rejestracji urządzeń](../enrollment/device-enrollment-manager-enroll.md). Użycie konta menedżera rejestracji urządzeń spowoduje też wyrejestrowanie się z aplikacji Portal firmy, aby użytkownicy nie mogli wyrejestrowywać urządzenia tak łatwo.

## <a name="step-4-create-a-device-management-profile-in-stagenow"></a>Krok 4. Tworzenie profilu zarządzania urządzeniami w rozwiązaniu StageNow

Rozwiązanie StageNow pozwala utworzyć profil konfiguracji ustawień, którymi chcesz zarządzać w urządzeniu. Szczegółowe informacje można znaleźć w dokumentacji firmy Zebra. Pomocny może być zasób [Profile](http://techdocs.zebra.com/stagenow/3-2/stagingprofiles/) (powoduje otwarcie witryny firmy Zebra).

Po utworzeniu profilu w rozwiązaniu StageNow w ostatnim kroku wybierz pozycję **Eksportuj do usługi MDM**. Ten krok powoduje wygenerowanie pliku XML. Zapisz ten plik. Będzie on potrzebny w dalszym kroku.

- Zaleca się przetestowanie profilu przed wdrożeniem go w urządzeniach w organizacji. Aby przeprowadzić test, w ostatnim kroku podczas tworzenia profili za pomocą rozwiązania StageNow na komputerze użyj opcji **Test**. Następnie użyj pliku wygenerowanego przez rozwiązanie StageNow za pomocą aplikacji StageNow w urządzeniu.

  Aplikacja StageNow w urządzeniu zawiera dzienniki wygenerowane podczas testu profilu. Aby uzyskać informacje na temat używania dzienników rozwiązania StageNow na potrzeby analizy błędów, zobacz [Używanie dzienników rozwiązania StageNow w urządzeniach Zebra z systemem Android w usłudze Intune](android-zebra-mx-logs-troubleshoot.md).

- Jeśli odwołujesz się do aplikacji albo aktualizujesz pakiety lub inne pliki w swoim profilu rozwiązania StageNow, urządzenie powinno uzyskiwać te aktualizacje. Aby można było pobrać aktualizacje, urządzenie musi połączyć się z serwerem wdrażania rozwiązania StageNow po zastosowaniu profilu. 

  Alternatywnie można użyć wbudowanych funkcji usługi Intune, aby pobrać te zmiany, w tym:

  - Funkcje zarządzania aplikacjami na potrzeby [dodawania](../apps/apps-add.md), [wdrażania](../apps/apps-deploy.md), aktualizowania i [monitorowania](../apps/apps-monitor.md) aplikacji.
  - Zarządzanie [aktualizacjami systemu i aplikacji](device-restrictions-android-for-work.md#device-owner-only) w urządzeniach z systemem Android Enterprise

Po przetestowaniu pliku następnym krokiem jest wdrożenie profilu w urządzeniach przy użyciu usługi Intune.

- Do urządzenia można wdrożyć jeden lub wiele profilów MX.
- Możesz również wyeksportować wiele profilów StageNow i połączyć ustawienia w jeden plik XML. Następnie Przekaż plik XML do usługi Intune, aby wdrożyć go na urządzeniach.

  > [!WARNING]
  > Jeśli wiele profilów MX jest przeznaczonych dla tej samej grupy i skonfigurowania tej samej właściwości, na urządzeniu będą występować konflikty.
  >
  > Jeśli ta sama właściwość jest konfigurowana wiele razy w jednym profilu MX, Ostatnia konfiguracja usługi WINS.

## <a name="step-5-create-a-profile-in-intune"></a>Krok 5. Tworzenie profilu w usłudze Intune

W usłudze Intune utwórz profil konfiguracji urządzenia:

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Urządzenia** > **Profile konfiguracji** > **Utwórz profil**.
3. Wprowadź następujące właściwości:

    - **Nazwa**: wprowadź opisową nazwę nowego profilu.
    - **Opis:** wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
    - **Platforma**: wybierz pozycję **Android**.
    - **Typ profilu**: wybierz pozycję **Profil MX (tylko urządzenia Zebra)** .

4. W obszarze **Profil MX w formacie xml** dodaj plik profilu XML [wyeksportowany z rozwiązania StageNow](#step-4-create-a-device-management-profile-in-stagenow) (w tym artykule).
5. Wybierz kolejno pozycje **OK** > **Utwórz**, aby zapisać zmiany. Zasady zostaną utworzone i wyświetlone na liście.

    > [!TIP]
    > Ze względów bezpieczeństwa nie zobaczysz tekstu profilu XML po jego zapisaniu. Tekst jest szyfrowany i wyświetlane są tylko gwiazdki (`****`). Zaleca się zapisanie kopii profili MX przed dodaniem ich do usługi Intune.

Profil został utworzony, ale nie wykonuje jeszcze żadnych czynności. W dalszej części [przypiszesz profil](device-profile-assign.md) i będziesz [monitorować jego stan](device-profile-monitor.md).

Następnym razem, gdy urządzenie sprawdzi dostępność aktualizacji, w urządzeniu zostanie wdrożony profil MX. Urządzenia są synchronizowane z usługą Intune podczas rejestracji urządzeń, a następnie co ok. 8 godzin. Możesz też [wymusić synchronizację w usłudze Intune](../remote-actions/device-sync.md). Alternatywnie w urządzeniu otwórz **aplikację Portal firmy**  >  **Ustawienia**  >  **Synchronizacja**. 

## <a name="update-a-zebra-mx-configuration-after-its-assigned"></a>Aktualizowanie konfiguracji zebry MX po jej przypisaniu

Aby zaktualizować konfigurację specyficzną dla platformy MX dla urządzenia zebry, możesz: 

- Utwórz zaktualizowany plik XML StageNow, Edytuj istniejący profil usługi Intune MX i przekaż nowy plik XML StageNow. Ten nowy plik zastępuje poprzednie zasady w profilu i zastąpi poprzednią konfigurację.
- Utwórz nowy plik XML StageNow, który konfiguruje różne ustawienia, Utwórz nowy profil usługi Intune MX, Przekaż nowy plik XML StageNow i przypisz go do tej samej grupy. Wdrożono wiele profilów. Jeśli nowy profil konfiguruje ustawienia, które już istnieją w istniejących profilach, będą występować konflikty.

## <a name="next-steps"></a>Następne kroki

- [Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).
- [Używanie dzienników rozwiązania StageNow na potrzeby rozwiązywania problemów z urządzeniami Zebra](android-zebra-mx-logs-troubleshoot.md).
