---
title: Przewodnik dotyczący testowania zestawu SDK aplikacji usługi Microsoft Intune dla systemu Android
description: Przewodnik testowania po zestawie SDK aplikacji usługi Microsoft Intune dla systemu Android ułatwia przetestowanie zarządzanej przez usługę Intune aplikacji dla systemu Android.
keywords: SDK
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 4ef8f421-9610-4d34-a464-cc02eb1578a9
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9eada01f2b1e876d6d3b47140c671e3ff7eeab02
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72503510"
---
# <a name="microsoft-intune-app-sdk-for-android-testing-guide"></a>Przewodnik dotyczący testowania zestawu SDK aplikacji usługi Microsoft Intune dla systemu Android

Ten przewodnik ułatwia deweloperom testowanie aplikacji systemu Android zarządzanych przez usługę Intune.  

## <a name="prerequisite-test-accounts"></a>Wymagane wstępnie konta do testowania
Można tworzyć nowe konta z lub bez wstępnie wygenerowanych danych. Aby utworzyć nowe konto:
1. Przejdź do witryny [Microsoft Demos](https://demos.microsoft.com/environments/create/tenant). 
2. [Skonfiguruj usługę Intune](../fundamentals/setup-steps.md), aby włączyć zarządzanie urządzeniami mobilnymi (MDM, Mobile Device Management).
3. [Utwórz użytkowników](../fundamentals/users-add.md).
4. [Tworzenie grup](../fundamentals/groups-add.md).
5. Odpowiednio [przypisz licencje](../fundamentals/licenses-assign.md) na potrzeby testów.


## <a name="azure-portal-policy-configuration"></a>Konfiguracja zasad w witrynie Azure Portal
[Utwórz i przypisz zasady ochrony aplikacji](../apps/app-protection-policies.md) w [bloku usługi Intune w witrynie Azure Portal](https://portal.azure.com/?feature.customportal=false#blade/Microsoft_Intune_Apps/MainMenu/14/selectedMenuItem/Overview). Możesz również utworzyć i przypisać [zasady konfiguracji aplikacji](../apps/app-configuration-policies-overview.md) w bloku Intune.

> [!NOTE]
> Jeśli aplikacji nie ma na liście w witrynie Azure Portal, możesz wybrać ją jako docelową dla zasad, wybierając opcję **więcej aplikacji** i podając nazwę pakietu w polu tekstowym.

## <a name="test-cases"></a>Przypadki testowe

W następujących przypadkach testowych przedstawiono kroki konfiguracji i potwierdzania. Wskazówki te ułatwią Ci rozwiązywanie problemów z zarządzanymi przez usługę Intune aplikacjami dla systemu Android.

### <a name="required-pin-and-corporate-credentials"></a>Wymaganie PIN-u i poświadczeń firmowych

Możesz wymagać podania numeru PIN przed uzyskaniem dostępu do zasobów firmy. Możesz też wymuszać uwierzytelnianie firmowe, zanim użytkownicy będą mogli korzystać z aplikacji zarządzanych. Oto jak:

1. W polach **Wymagaj numeru PIN w celu uzyskania dostępu** i **Wymagaj poświadczeń firmowych w celu udzielenia dostępu** ustaw wartość **Tak**. Aby uzyskać więcej informacji, zobacz [Ustawienia zasad ochrony aplikacji systemu Android w usłudze Microsoft Intune](../apps/app-protection-policy-settings-android.md#access-requirements).
2. Potwierdź następujące warunki:
    - Podczas uruchamiania aplikacji powinien pojawiać się monit o podanie numeru PIN lub konto użytkownika produkcyjnego, za pomocą którego dokonano rejestracji w aplikacji Portal firmy.
    - Niepowodzenie zaprezentowania prawidłowego monitu logowania może być spowodowane niepoprawnie skonfigurowanym manifestem systemu Android, w odniesieniu do wartości integracji biblioteki uwierzytelniania Azure Active Directory (ADAL) (element skipbroker, ClientID i urząd).
    - Jeśli nie pojawia się żaden monit, może to być spowodowane niepoprawnie zintegrowaną wartością `MAMActivity`. Aby uzyskać więcej informacji na temat klasy `MAMActivity`, zobacz [Przewodnik dewelopera po zestawie SDK aplikacji usługi Microsoft Intune dla systemu Android](app-sdk-android.md).

> [!NOTE] 
> Jeśli poprzedni test nie działa, następujące testy prawdopodobnie zakończą się niepowodzeniem. Zapoznaj się z informacjami o zestawie [SDK](app-sdk-android.md##sdk-integration) i integracji [ADAL](app-sdk-android.md#configure-azure-active-directory-authentication-library-adal).

### <a name="restrict-transferring-and-receiving-data-with-other-apps"></a>Ograniczanie przesyłania i odbierania danych z innych aplikacji
Przesyłaniem danych między zarządzanymi przez firmę aplikacjami możesz sterować w następujący sposób:

1. Dla ustawienia **Zezwalaj aplikacji na przesyłanie danych do innych aplikacji** skonfiguruj wartość **Aplikacje zarządzane przez zasady**.
2. Dla pozycji **Zezwalaj aplikacji na odbieranie danych z innych aplikacji** ustaw opcję **Wszystkie aplikacje**. Te zasady mają wpływ na korzystanie z intencji i dostawców zawartości.
3. Potwierdź następujące warunki:
    - Otwieranie z poziomu aplikacji niezarządzanej do funkcji aplikacji działa poprawnie.
    - Udostępnianie zawartości między aplikacjami zarządzanymi jest dozwolone.
    - Udostępnianie z aplikacji zarządzanych do aplikacji niezarządzanych (na przykład do przeglądarki Chrome) jest zablokowane.

### <a name="restrict-cut-copy-and-paste"></a>Ogranicz wycinanie, kopiowanie i wklejanie
Schowek systemu możesz ograniczyć do aplikacji zarządzanych w następujący sposób:

1. Dla ustawienia **Ogranicz wycinanie, kopiowanie i wklejanie w innych aplikacjach** skonfiguruj wartość **Aplikacje zarządzane przez zasady z funkcją wklejania**.
2. Potwierdź następujące warunki:
    - Kopiowanie tekstu z Twojej aplikacji do aplikacji niezarządzanej (na przykład do aplikacji Wiadomości) jest zablokowane.

### <a name="prevent-save"></a>Zapobieganie zapisywaniu
Działaniem polecenia **Zapisz jako** możesz sterować w następujący sposób:

1. Jeśli aplikacja wymaga [zintegrowanych kontrolek polecenia „Zapisz jako”](app-sdk-android.md#example-determine-if-saving-to-device-or-cloud-storage-is-permitted), dla ustawienia **Nie zezwalaj na używanie polecenia „Zapisz jako”** skonfiguruj wartość **Tak**.
2. Potwierdź następujące warunki:
    - Zapisywanie jest ograniczone do odpowiednich lokalizacji zarządzanych.

### <a name="file-encryption"></a>Szyfrowanie plików
Dane na urządzeniu możesz szyfrować w następujący sposób:

1. Dla ustawienia **Szyfruj dane aplikacji** skonfiguruj wartość **Tak**.
2. Potwierdź następujące warunki:
    - Normalne zachowanie aplikacji nie ma zastosowania.

### <a name="prevent-android-backups"></a>Blokuj kopie zapasowe systemu Android
Kopiami zapasowymi aplikacji możesz sterować w następujący sposób:

1. Jeśli zostały ustawione [zintegrowane ograniczenia dotyczące kopii zapasowej](app-sdk-android.md#protecting-backup-data), dla ustawienia **Nie zezwalaj na kopie zapasowe systemu Android** skonfiguruj wartość **Tak**.
2. Potwierdź następujące warunki:
    - Kopie zapasowe są ograniczone.

### <a name="unenrollment"></a>Wyrejestrowywanie
Możesz zdalnie wyczyścić w aplikacjach zarządzanych firmowe wiadomości e-mail i dokumenty, a wyłączenie administrowania spowoduje odszyfrowanie danych osobistych. Oto jak:

1. W witrynie Azure Portal [wydaj polecenie wyczyszczenia danych](../apps/apps-selective-wipe.md).
2. Jeśli dla aplikacji nie zarejestrowano żadnych procedur obsługi czyszczenia, potwierdź następujące warunki:
    - Przeprowadzane jest pełne czyszczenie aplikacji.
3. Jeśli dla aplikacji nie zarejestrowano procedury `WIPE_USER_DATA` ani `WIPE_USER_AUXILARY_DATA`, potwierdź następujące warunki:
    - Zawartość zarządzana zostaje usunięta z aplikacji. Aby uzyskać więcej informacji, zobacz [Przewodnik dewelopera po zestawie SDK aplikacji usługi Microsoft Intune dla systemu Android — selektywne czyszczenie](app-sdk-android.md#selective-wipe).

### <a name="multi-identity-support"></a>Obsługa wielu tożsamości
Integracja [obsługi wielu tożsamości](app-sdk-android.md#multi-identity-optional) to zmiana, z którą wiąże się istotne ryzyko, należy więc ją dokładnie przetestować. Najczęstsze problemy występują z powodu nieprawidłowego ustawienia tożsamości (poziomu kontekstu i zagrożenia) oraz śledzenia plików (`MAMFileProtectionManager`).

Upewnij się, że:

- Zasady polecenia **Zapisz jako** działają poprawnie dla tożsamości zarządzanych.
- Ograniczenia dotyczące kopiowania i wklejania są poprawnie wymuszane ze środowisk zarządzanych do osobistych.
- Tylko dane należące do tożsamości zarządzanej są szyfrowane, a pliki osobiste nie są modyfikowane.
- Selektywne czyszczenie podczas wyrejestrowywania powoduje usunięcie tylko danych tożsamości zarządzanych.
- Użytkownik jest monitowany o uruchomienie warunkowe podczas przełączania z konta niezarządzanego na zarządzane (tylko za pierwszym razem).

### <a name="app-configuration-optional"></a>Konfiguracja aplikacji (opcjonalna)
Możesz skonfigurować działanie aplikacji zarządzanych. Jeśli aplikacja używa jakichkolwiek ustawień konfiguracji aplikacji, należy sprawdzić, czy poprawnie obsługuje ona wszystkie wartości, które (jako administrator) możesz ustawić. Można tworzyć i przypisywać [zasady konfiguracji aplikacji](../apps/app-configuration-policies-overview.md) w usłudze Intune.

## <a name="next-steps"></a>Następne kroki

- [Dodawanie aplikacji biznesowych dla systemu Android do usługi Microsoft Intune](../apps/lob-apps-android.md)
