---
title: Używanie rozszerzeń mobilności zebry na urządzeniach z systemem Android w programie Microsoft Intune — Azure | Dokumentacja firmy Microsoft
description: Microsoft Intune umożliwia zarządzanie zasobami oraz używanie zebry urządzeń z systemem Android za pomocą rozszerzenia mobilności zebry (MX). Zobacz wszystkie czynności, w tym zainstalować aplikację Portal firmy, ładować bezpośrednio aplikację, Przypisz rolę administratora urządzenia, Utwórz profil StageNow i nie tylko.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/26/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: ''
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: aa2734247569245794bce7fe1de68c8b20c6091f
ms.sourcegitcommit: 44095bbd1502b02201a01604531f4105401fbb92
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 03/27/2019
ms.locfileid: "58490608"
---
# <a name="use-and-manage-zebra-devices-with-zebra-mobility-extensions-in-microsoft-intune"></a>Użyj urządzenia i zarządzać nimi zebry zebry mobilności rozszerzenia w Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Usługa Intune obejmuje bogaty zestaw funkcji, takich jak zarządzanie aplikacjami i konfigurowanie ustawień urządzenia. Te wbudowane funkcje i ustawienia są używane do zarządzania wytwarzane przez zebry technologii, znany także jako "zebry urządzenia" urządzenia z systemem Android.

Jeśli chcesz dostosować lub Dodaj więcej ustawień specyficznych dla zebry umożliwia także zebry **mobilności rozszerzenia (MX)** na tych urządzeniach. 

Ta funkcja ma zastosowanie do:

- Android

Twoja firma może używać urządzenia zebry dla handlu detalicznego na etapie produkcji i nie tylko. Na przykład jesteś sprzedaży detalicznej i środowisko zawiera tysiące zebry urządzeniach mobilnych używanych przez kojarzy sprzedaży. Usługa Intune może pomóc zarządzać tymi urządzeniami w ramach rozwiązania do zarządzania (urządzeniami przenośnymi MDM) urządzenia przenośnego.

Przy użyciu usługi Intune, można zarejestrować urządzenia zebry wdrożenia aplikacji line-of-business na urządzeniach. "Urządzenie" Profile umożliwiają tworzenie MX profilów, aby zarządzać ustawieniami zebry specyficznych.

W tym artykule przedstawiono sposób używania rozszerzeń mobilności zebry (MX) na urządzeniach zebry w Microsoft Intune.

## <a name="before-you-begin"></a>Przed rozpoczęciem

- Upewnij się, że masz najnowszą wersję aplikacji klasycznej StageNow z zebry technologii.
- Należy koniecznie sprawdzić [zebry firmy pełną macierz funkcji MX](http://techdocs.zebra.com/mx/compatibility) (otwiera witrynę sieci web firmy zebry) aby upewnić się, profile, tworzysz są zgodne z modelu, wersji systemu operacyjnego i wersji MX urządzenia.
- Niektóre urządzenia, takich jak urządzenia TC20/25 nie obsługują wszystkie funkcje dostępne MX w StageNow. Należy koniecznie sprawdzić [tabela funkcji firmy zebry](http://techdocs.zebra.com/mx/tc2x/) (otwiera witrynę sieci web firmy zebry) dla informacji o pomocy technicznej zaktualizowane.

## <a name="step-1-install-the-latest-company-portal-app"></a>Krok 1: Zainstaluj najnowszą wersję aplikacji Portal firmy

Na urządzeniu przejdź do sklepu Google Play i pobrać i zainstalować aplikację Portal firmy usługi Intune przez firmę Microsoft. Po zainstalowaniu ze sklepu Google Play aplikację Portal firmy pobiera aktualizacje i poprawki automatycznie.

Jeśli sklepu Google Play nie jest dostępna, Pobierz [Portal firmy usługi Microsoft Intune dla systemu Android](https://www.microsoft.com/download/details.aspx?id=49140) (otwiera innej witrynie internetowej firmy Microsoft), i [sideload go](#sideload-the-company-portal-app) (w tym artykule). Podczas instalacji w ten sposób aplikacja nie otrzymywać aktualizacje lub rozwiązuje się automatycznie. Należy regularnie aktualizacji i poprawek aplikacji ręcznie.

### <a name="sideload-the-company-portal-app"></a>Ładowanie bezpośrednie aplikacji Portal firmy

"Ładowaniem bezpośrednim" jest, gdy nie używasz, aby zainstalować aplikację sklepu Google Play. Aby ładować bezpośrednio aplikację Portal firmy należy użyć StageNow. 

W poniższych krokach przedstawiono omówienie. Aby uzyskać szczegółowe informacje można znaleźć w temacie zebry w dokumentacji. [Rejestrowanie w usłudze MDM za pomocą StageNow](http://techdocs.zebra.com/stagenow/3-1/Profiles/enrollmdm/) (otwiera witrynę sieci web firmy zebry) może być dobry zasobem.

1. W StageNow, Utwórz profil dla **rejestracja w usłudze MDM**.
2. W **wdrożenia**, wybierz opcję pobrania pliku agenta zarządzania urządzeniami Przenośnymi.
3. Ustaw **aplikacji obsługi** i **pobrać konfiguracji** kroki, aby **nie**.
4. W **Pobierz MDM**, wybierz opcję **przenoszenia/kopiowania pliku**. Dodaj do źródłowej i docelowej pakiet Portal firmy dla systemu Android (APK).
5. W **uruchamiania zarządzania urządzeniami Przenośnymi**, pozostaw wartości domyślne jak-to. Dodaj następujące szczegóły:

    - **Nazwa pakietu**: `com.microsoft.windowsintune.companyportal`
    - **Nazwa klasy**: `com.microsoft.windowsintune.companyportal.views.SplashActivity`

W dalszym ciągu profil publikowania i używanie go z aplikacją StageNow na urządzeniu. Aplikacja Portal firmy jest zainstalowana i otworzyć na urządzeniu.

> [!TIP]
> Aby uzyskać więcej informacji na temat StageNow i przeznaczenie, zobacz [przemieszczania urządzenia StageNow Android](https://www.zebra.com/us/en/products/software/mobile-computers/mobile-app-utilities/stagenow.html) (otwiera witrynę sieci web firmy zebry).

## <a name="step-2-confirm-the-company-portal-app-has-device-administrator-role"></a>Krok 2: Upewnij się, że aplikacja Portal firmy ma rolę administratora urządzenia

Aplikacja Portal firmy wymaga administratora urządzenia do zarządzania urządzeniami z systemem Android. Aby aktywować rolę Administrator urządzenia, niektóre urządzenia zebry obejmują interfejs użytkownika (UI) na urządzeniu. Jeśli urządzenie obsługuje interfejs użytkownika, aplikację Portal firmy monituje użytkownika końcowego, aby udzielić Administrator urządzenia podczas [rejestracji](#step-3-enroll-the-device-in-to-intune) (w tym artykule).

Jeśli interfejs użytkownika jest niedostępna, użyj **Menedżera DevAdmin** w StageNow, aby utworzyć profil ręcznie przyznająca administratora urządzenia do aplikacji Portal firmy.

W poniższych krokach przedstawiono omówienie. Aby uzyskać szczegółowe informacje można znaleźć w temacie zebry w dokumentacji. 
[Ustaw baterii wymiany tryb jako administrator urządzenia](https://zebratechnologies.force.com/s/article/Set-Battery-Swap-Mode-as-Device-Administrator-using-StageNow-Tool) (otwiera witrynę sieci Web firmy zebry) może być dobry zasobem.

1. W StageNow, Utwórz profil i wybierz **tryb Xpert**.
2. Dodaj **Menedżera DevAdmin** do profilu.
3. Ustaw **akcji administracyjnej urządzenia** do **włączyć jako Administrator urządzenia**.
4. Ustaw **nazwa pakietu administracyjnego urządzenia** do `com.microsoft.windowsintune.companyportal`.
5. Ustaw **Nazwa klasy administratora urządzenia** do `com.microsoft.omadm.client.PolicyManagerReceiver`.

W dalszym ciągu profil publikowania i używanie go z aplikacją StageNow na urządzeniu. Aplikacja Portal firmy jest udzielany rolę administratora urządzenia.

## <a name="step-3-enroll-the-device-in-to-intune"></a>Krok 3: Rejestrowanie urządzenia w usłudze Intune

Po wykonaniu dwóch pierwszych kroków aplikacji Portal firmy jest zainstalowany na urządzeniu. Urządzenie jest gotowe do rejestracji w usłudze Intune.

[Rejestrowanie urządzeń z systemem Android](android-enroll.md) zawiera listę czynności. Jeśli masz wiele urządzeń zebry, warto użyć [konta Menedżera rejestracji urządzeń](device-enrollment-manager-enroll.md).

## <a name="step-4-create-a-device-management-profile-in-stagenow"></a>Krok 4: Tworzenie profilu zarządzania urządzeniami w StageNow

Użyj StageNow, aby utworzyć profil, który konfiguruje ustawienia, które mają być zarządzane na urządzeniu. Aby uzyskać szczegółowe informacje można znaleźć w temacie zebry w dokumentacji. [Profile](http://techdocs.zebra.com/stagenow/3-2/stagingprofiles/) (otwiera witrynę sieci Web firmy zebry) może być dobry zasobem.

Po utworzeniu profilu w StageNow, w ostatnim kroku wybierz **wyeksportować do zarządzania urządzeniami Przenośnymi**. Spowoduje to wygenerowanie pliku XML. Zapisz ten plik. Będą potrzebne w kolejnym kroku.

> [!TIP]
> Zaleca się testowanie profil, który można wdrożyć na urządzeniach w organizacji. Aby przetestować w ostatnim kroku podczas tworzenia profilów za pomocą StageNow na komputerze, użyj **Test** opcje. Następnie należy korzystać z wygenerowanych StageNow pliku za pomocą aplikacji StageNow na urządzeniu. 
> 
> Aplikacja StageNow na urządzeniu zawiera dzienniki generowane, gdy można przetestować profilu. [Użyj StageNow loguje zebry urządzeń z systemem Android w usłudze Intune](android-zebra-mx-logs-troubleshoot.md) zawiera informacje na temat korzystania z dzienników StageNow do zrozumienia błędy.

> [!NOTE]
> Jeśli odwoływać się do aplikacji, pakietów aktualizacji lub zaktualizować inne pliki w swoim profilu StageNow chcesz się urządzenie, aby uzyskać te aktualizacje. Aby pobrać aktualizacje, urządzenie musi połączyć się na serwerze wdrażania StageNow po zastosowaniu profilu. 
> 
> Alternatywnie można użyć wbudowanych funkcji w usłudze Intune, można pobrać te zmiany, w tym: 
> - Funkcje zarządzania aplikacjami [Dodaj](apps-add.md), [wdrażanie](apps-deploy.md), zaktualizować, i [monitor](apps-monitor.md) aplikacji.
> - Zarządzanie [aktualizacje systemu i aplikacji](device-restrictions-android-for-work.md#device-owner-only) na urządzeniu z systemem Android Enterprise

Po przetestowaniu pliku, następnym krokiem jest na wdrożenie profilu do urządzeń przy użyciu usługi Intune.

> [!NOTE]
> Do każdego urządzenia, należy wdrożyć jeden profil. Jeśli istnieje wiele profili StageNow, które mają zostać wdrożone na urządzeniach, eksportowanie profilów StageNow i łączyć ustawienia w pojedynczym pliku XML, przed dodaniem go do usługi Intune. 
> 
> Nie mają dwa ustawienia, które skonfiguruj tę samą właściwość tego samego pliku XML. Celem jest, aby zapobiec konfliktom między ustawień na urządzeniu.

## <a name="step-5-create-a-profile-in-intune"></a>Krok 5: Tworzenie profilu w usłudze Intune

W usłudze Intune utwórz profil konfiguracji urządzenia:

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi**, wpisz nazwę usługi **Intune** w filtrze, a następnie wybierz pozycję **Intune**.
2. Wybierz kolejno pozycje **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Wprowadź następujące właściwości:

    - **Nazwa**: wprowadź opisową nazwę nowego profilu.
    - **Opis:** wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
    - **Platforma**: wybierz pozycję **Android**.
    - **Typ profilu**: Wybierz **MX profilu (tylko zebry)**.

4. W **MX profilu w formacie XML**, Dodaj plik XML profilu [wyeksportowane z StageNow](#step-4-create-a-device-management-profile-in-stagenow) (w tym artykule).
5. Wybierz kolejno pozycje **OK** > **Utwórz**, aby zapisać zmiany. Zasada jest tworzone i wyświetlane na liście.

Profil został utworzony, ale nie wykonuje jeszcze żadnych czynności. W dalszej części [przypiszesz profil](device-profile-assign.md) i będziesz [monitorować jego stan](device-profile-monitor.md).

Przy następnym urządzenie sprawdza dostępność aktualizacji konfiguracji profilu MX jest wdrożony na urządzeniu. Synchronizowanie urządzeń przy użyciu usługi Intune, podczas rejestracji urządzeń, a następnie co 8 godzin. Możesz również [wymusić synchronizację w usłudze Intune](device-sync.md). Na urządzeniu, należy otworzyć **aplikacji Portal firmy** > **ustawienia** > **synchronizacji**. 

> [!TIP]
> - Ze względów bezpieczeństwa nie będziesz widzieć profilu tekstu XML, po jego zapisaniu. Tekst jest szyfrowany i wyświetlać tylko gwiazdki (`****`). Do której można się odwołać zaleca się zapisywania kopii profile MX przed dodaniem ich do usługi Intune.
> 
> - Aby zaktualizować profil po przypisaniu do urządzeń zebry, Utwórz plik StageNow XML zaktualizowane, edytować istniejący profil usługi Intune i Dodaj nowy plik StageNow XML. Ten nowy plik zastąpi poprzednich zasad StageNow w profilu.

## <a name="next-steps"></a>Następne kroki

[Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).

[Użyj dzienników StageNow, aby rozwiązywać problemy dotyczące urządzeń zebry](android-zebra-mx-logs-troubleshoot.md).
