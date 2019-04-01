---
title: Przewodnik testowania dla deweloperów po zestawie SDK aplikacji usługi Microsoft Intune dla systemu Android
description: Microsoft Intune App SDK dla systemu Android przewodnik testowania pomaga testować swoją aplikację dla systemu Android zarządzane przez usługę Intune.
keywords: SDK
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/14/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 4ef8f421-9610-4d34-a464-cc02eb1578a9
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4203f424c395399cb0ed1e7472b006602aa0b210
ms.sourcegitcommit: db7a6b8fc9e82dae4f2111ca0b2d3c14e33658f9
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2019
ms.locfileid: "58072474"
---
# <a name="microsoft-intune-app-sdk-for-android-developers-testing-guide"></a>Przewodnik testowania dla deweloperów po zestawie SDK aplikacji usługi Microsoft Intune dla systemu Android

Microsoft Intune App SDK dla systemu Android przewodnik testowania zaprojektowano ułatwia testowanie aplikacji systemu Android zarządzane przez usługę Intune.  

## <a name="prerequisite-test-accounts"></a>Konta testowania wymagań wstępnych
Można tworzyć nowych kont z lub bez wstępnie wygenerowane dane. Aby utworzyć nowe konto:
1. Przejdź do [Demos Microsoft](https://demos.microsoft.com/environments/create/tenant) lokacji. 
2. [Konfigurowanie usługi Intune](https://docs.microsoft.com/intune/setup-steps) umożliwiające zarządzanie urządzeniami przenośnymi (MDM).
3. [Tworzenie użytkowników](https://docs.microsoft.com/intune/users-add).
4. [Tworzenie grup](https://docs.microsoft.com/intune/groups-add).
5. [Przypisywanie licencji](https://docs.microsoft.com/intune/licenses-assign) odpowiednio na potrzeby testów.


## <a name="azure-portal-policy-configuration"></a>Konfiguracja zasad portalu Azure
[Tworzenie i przypisywanie zasad ochrony aplikacji](https://docs.microsoft.com/intune/app-protection-policies) w [bloku Intune witryny Azure portal](https://portal.azure.com/?feature.customportal=false#blade/Microsoft_Intune_Apps/MainMenu/14/selectedMenuItem/Overview). Twoje [zasady konfiguracji aplikacji](https://docs.microsoft.com/intune/app-configuration-policies-overview) również można tworzyć i przypisana w bloku usługi Intune.

> [!NOTE]
> Jeśli aplikacja nie znajduje się w witrynie Azure portal, możesz wybrać docelową go za pomocą zasad, wybierając **większej liczby aplikacji** opcja i podając nazwę pakietu, w polu tekstowym.

> [!IMPORTANT]
> Zasad konfiguracji aplikacji zastosować, rejestrowanie użytkowników musi być objęta [zasad ochrony aplikacji usługi Intune](https://docs.microsoft.com/intune/app-protection-policy).

## <a name="test-cases"></a>Przypadki testowe

Następujące przypadki testowe zawierają opis etapów konfiguracji i potwierdzenia. Skorzystać z poniższych wskazówek, aby ułatwić rozwiązywanie problemów z aplikacjami dla systemu Android zarządzane przez usługę Intune.

### <a name="required-pin-and-corporate-credentials"></a>Wymagaj numeru PIN i poświadczeń firmowych

Może wymagać numeru pin umożliwiającego dostęp do zasobów firmy. Ponadto można wymusić uwierzytelnianie firmy, zanim użytkownicy mogą korzystać z aplikacji zarządzanych. Aby ustawić te wymagania, wykonaj następujące kroki:

1. Konfigurowanie **Wymagaj numeru PIN, aby uzyskać dostęp do** i **Wymagaj poświadczeń firmowych w celu udzielenia dostępu** do **tak**. Aby uzyskać więcej informacji, zobacz [Ustawienia zasad ochrony aplikacji systemu Android w usłudze Microsoft Intune](app-protection-policy-settings-android.md#access-requirements).
2. Potwierdź następujące warunki:
    - Uruchamianie aplikacji powinni przedstawić potwierdzenie odpowiedniego monit o podanie numeru PIN, dane wejściowe/Konfiguracja i/lub produkcji użytkownika, którego użyto podczas rejestracji w portalu firmy.
    - Nie można przedstawić prawidłowy monit logowania może być spowodowany niepoprawnie skonfigurowany manifest systemu android, w szczególności wartości integracji usługi ADAL (element SkipBroker, identyfikatora klienta i uprawnienia).
    - Niewysłanie dowolnego wiersza może wynikać z niepoprawnie zintegrowane `MAMActivity` wartość. Aby uzyskać więcej informacji na temat `MAMActivity`, zobacz [Microsoft Intune App SDK for przewodnik dewelopera systemu Android](app-sdk-android.md).

> [!NOTE] 
> Jeśli powyższe testu nie działa, poniższe testy prawdopodobnie zakończy się niepowodzeniem także. Przegląd [SDK](app-sdk-android.md##sdk-integration) i [ADAL](app-sdk-android.md#configure-azure-active-directory-authentication-library-adal) integracji.

### <a name="restrict-transferring-and-receiving-data-with-other-apps"></a>Ograniczanie transferu i odbierania danych z innych aplikacji
Można kontrolować transfer danych między firmowych zarządzanych aplikacji w następujący sposób:

1. Ustaw **Zezwalaj aplikacji na przesyłanie danych do innych aplikacji** do **aplikacje zarządzane przez zasady**.
2. Dla pozycji **Zezwalaj aplikacji na odbieranie danych z innych aplikacji** ustaw opcję **Wszystkie aplikacje**. Użycie intencje i dostawców zawartości będzie mieć wpływ tych zasad.
3. Potwierdź następujące warunki:
    - Otwieranie z niezarządzanych aplikacji do aplikacji funkcji poprawnie.
    - Udostępnianie zawartości między aplikacjami zarządzanymi jest dozwolone.
    - Udostępnianie danych z aplikacji zarządzanych do niezarządzanych aplikacji (na przykład przeglądarka Chrome) jest zablokowany.

### <a name="restrict-cut-copy-and-paste"></a>Ogranicz wycinanie, kopiowanie i wklejanie
Schowek systemu można ograniczyć do aplikacji zarządzanych, w następujący sposób:

1. Ustaw **Ogranicz wycinanie, kopiowanie i wklejanie w innych aplikacjach** do **zarządzane przez zasady z funkcją wklejania**.
2. Potwierdź następujące warunki:
    - Kopiowanie tekstu z aplikacją do zarządzanej niezarządzanej aplikacji (na przykład wiadomości) jest zablokowany.

### <a name="prevent-save-as"></a>Nie zezwalaj na używanie polecenia **Zapisz jako**
Możesz kontrolować **Zapisz jako** funkcji w następujący sposób:

1. Jeśli aplikacja wymaga [zintegrowane kontrolki "Zapisz jako"](app-sdk-android.md#example-determine-if-saving-to-device-or-cloud-storage-is-permitted)ustaw **Zapobiegaj "Zapisz jako"** do **tak**.
2. Potwierdź następujące warunki:
    - Zapisz jest ograniczony do odpowiednich zarządzanych lokalizacji.

### <a name="file-encryption"></a>Szyfrowanie plików
Można zaszyfrować dane na urządzeniu w następujący sposób:

1. Ustaw **Szyfruj dane aplikacji** do **tak**.
2. Potwierdź następujące warunki:
    - Nie ma wpływu na zachowanie normalne aplikacji.

### <a name="prevent-android-backups"></a>Blokuj kopie zapasowe systemu Android
Kopia zapasowa aplikacji można kontrolować w następujący sposób:

1. Jeśli ustawiono [zintegrowane ograniczenia tworzenia kopii zapasowej](app-sdk-android.md#protecting-backup-data), skonfiguruj **kopie zapasowe zapobiec systemu Android** do **tak**.
2. Potwierdź następujące warunki:
    - Kopie zapasowe są ograniczone.

### <a name="unenrollment"></a>Wyrejestrowanie
Zdalnie czyścić zarządzane aplikacje z zawierającego firmowej poczty e-mail i dokumenty i dane osobowe zostaną odszyfrowane, gdy jest podawana nie jest już w następujący sposób:

1. W witrynie Azure portal [czyszczenie danych](https://docs.microsoft.com/intune/apps-selective-wipe).
2. Jeśli aplikacja nie zarejestrować do obsługi dowolnej czyszczenia Potwierdź następujące warunki:
    - Występuje, pełnego czyszczenia danych aplikacji.
3. Jeśli aplikacja została zarejestrowana dla `WIPE_USER_DATA` lub `WIPE_USER_AUXILARY_DATA`, potwierdź następujące warunki:
    - Zawartości zarządzanej zostanie usunięty z aplikacji. Aby uzyskać więcej informacji, zobacz [Intune App SDK for przewodnik dewelopera systemu Android — selektywne czyszczenie](app-sdk-android.md#selective-wipe).

### <a name="multi-identity"></a>Wiele tożsamości
Integrowanie [obsługą wielu tożsamości](app-sdk-android.md#multi-identity-optional) zmiany o wysokim ryzyku, który musi być sprawdzone. Najczęściej spotykanych problemów będzie ze względu na niepoprawne ustawienia tożsamości (context, a poziom zagrożenia) i również śledzenia plików (`MAMFileProtectionManager`).

Co najmniej następujące scenariusze związane z obsługą wielu tożsamości powinien być sprawdzony ponownie:

- **Zapisz jako** zasada działa prawidłowo dla zarządzanych tożsamości.
- Kopiowanie, wklejanie, który ograniczenia są prawidłowo wymuszane z kodu zarządzanego do osobistych.
- Tylko dane należące do tożsamości zarządzanej są szyfrowane i pliki osobiste nie są modyfikowane.
- Selektywne czyszczenie danych podczas wyrejestrowywania tylko usunięcie danych zarządzanych tożsamości.
- Użytkownik jest monitowany o warunkowego uruchamiania, podczas zmiany z niezarządzanego konta zarządzanego (tylko pierwszy raz).

### <a name="app-configuration-optional"></a>Konfiguracja aplikacji (opcjonalnie)
Działanie aplikacji zarządzanej można skonfigurować w następujący sposób:

1. Jeśli aplikacja wykorzystuje wszystkie ustawienia konfiguracji aplikacji, należy sprawdzić, że aplikacja poprawnie obsługuje wszystkie wartości, które (jako administrator) można ustawić. [Zasady konfiguracji aplikacji](https://docs.microsoft.com/intune/app-configuration-policies-overview) utworzone i przypisane przy użyciu usługi Intune.

## <a name="next-steps"></a>Następne kroki

- [Dodawanie aplikacji biznesowych dla systemu Android do usługi Microsoft Intune](lob-apps-android.md).
