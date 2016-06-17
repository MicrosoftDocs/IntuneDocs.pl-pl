---
# required metadata

title: Zarządzanie firmowymi urządzeniami | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Rejestrowanie firmowych urządzeń w usłudze Microsoft Intune
Urządzenia należące do organizacji lub firmy (COD) mogą być wprowadzane do systemu zarządzania w usłudze Intune na wiele sposobów, w zależności od urządzenia, sposobu jego zakupu i potrzeb organizacji.

## Firmowe urządzenia z systemem iOS
Te metody rejestracji są odpowiednie w scenariuszach „Wybierz własne urządzenie” (CYOD), w których organizacja kupuje urządzenia dla użytkowników, ale chce zachować możliwość zarządzania urządzeniem. Jeśli dana organizacja nabyła urządzenia z systemem iOS, można wstępnie zorganizować rejestrację w taki sposób, że urządzenie zostanie dołączone do systemu zarządzania, gdy użytkownik włączy je pierwszy raz. Usługa Intune obsługuje rejestrowanie urządzeń w ramach programu [Device Enrollment Program (DEP) firmy Apple](ios-device-enrollment-program-in-microsoft-intune.md) lub przy użyciu programu Apple Configurator działającego na komputerze Mac, który umożliwia rejestrację [bezpośrednią](ios-direct-enrollment-in-microsoft-intune.md) lub z wykorzystaniem [asystenta ustawień](ios-setup-assistant-enrollment-in-microsoft-intune.md).

[Rejestrowanie firmowych urządzeń z systemem iOS](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)

## Menedżer rejestracji urządzeń
Organizacje mogą używać usługi Intune do zarządzania dużą liczbą urządzeń przenośnych za pomocą jednego konta użytkownika, zwanego kontem menedżera rejestracji urządzeń. Po utworzeniu konta menedżera rejestracji urządzeń menedżer może użyć tego konta do zarejestrowania większej liczby urządzeń. Domyślnie normalni użytkownicy mogą rejestrować do pięciu urządzeń. Rejestrowanie urządzeń za pomocą menedżera rejestrowania urządzeń działa tylko wobec urządzeń, które nie są wykorzystywane przez konkretnego użytkownika. Takie urządzenia nadają się do wykorzystania w punktach sprzedaży lub na potrzeby użycia aplikacji narzędziowych, ale są złym rozwiązaniem dla użytkowników, którzy potrzebują dostępu do poczty e-mail lub zasobów firmowych.

[Rejestrowanie urządzeń należących do firmy przy użyciu menedżera rejestracji urządzeń](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)

## Unikatowe międzynarodowe numery identyfikujące urządzenia przenośne (IMEI)
Unikatowe międzynarodowe numery identyfikujące urządzenia przenośne (IMEI) są często stosowanymi przez producentów oznaczeniami urządzeń przenośnych. Administratorzy usługi Intune mogą importować numery IMEI dla urządzeń, których właścicielem jest firma. Gdy urządzenie jest zarządzane przez usługę Intune, można oznakować je jako urządzenie należące do firmy i zastosować wobec niego odpowiednie zasady.

[Określanie urządzeń należących do firmy z międzynarodowymi numerami identyfikującymi urządzenia przenośne (IMEI, International Mobile Equipment Identity)](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

## Przegląd metod rejestracji urządzeń firmowych

W poniższej tabeli przedstawiono metody rejestracji urządzeń firmowych oraz ich zalety.

**Metody rejestracji urządzeń z systemem iOS**

| **Metoda** |  **[Reset (Zresetuj)](#Reset)** |   **[Koligacja](#Affinity)**   |   **[Zablokowana](#Locked)** |
|:---:|:---:|:---:|:---:|
|**[„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)](#BYOD)** | Nie|    Tak |   Nie |
|**[Menedżer rejestracji urządzeń](#DEM)**|   Nie |Nie |Nie  |
|**[Program Device Enrollment Program](#DEP)**|   Tak |   Opt |   Opt|
|**[USB-SA](#USB-SA)**| Tak |   Opt |   Nie|
|**[USB-Direct](#USB-Direct)**| Nie |    Nie  | Nie|

**Metody rejestracji urządzeń z systemami Windows i Android**

| **Metoda** |  **[Czyszczenie danych](#Wipe)** | **[Użytkownik](#User)**   |   **[Zablokowana](#Locked)** |
|:---:|:---:|:---:|:---:|
|**[„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)](#BYOD)** | Nie|    Tak |   Nie |
|**[Menedżer rejestracji urządzeń](#DEM)**|   Nie |Nie |Nie  |

**Metody rejestracji firmowych urządzeń**

### „Przynieś własne urządzenie” (BYOD, Bring Your Own Device)
„Przynieś własne urządzenie”. Użytkownicy instalują aplikację Portal firmy i rejestrują swoje urządzenia. Zarejestrowanie urządzenia w portalu firmy spowoduje dołączenie urządzenia do miejsca pracy. Zarejestrowanie urządzeń z systemem iOS w portalu firmy wymaga identyfikatora firmy Apple. Urządzenia BYOD nie wymagają dodatkowej konfiguracji w przypadku urządzeń firmowych. Zobacz kroki [konfigurowania zarządzania urządzeniami](get-ready-to-enroll-devices-in-microsoft-intune#set-up-device-management.md). ([Z powrotem do tabeli](#overview-of corporate-owned-device-enrollment-methods))

### Menedżer rejestracji urządzeń
Menedżer rejestracji urządzeń. Administrator tworzy konta menedżera rejestracji urządzeń. Menedżerowie mogą wtedy zainstalować portal firmy i zarejestrować wiele urządzeń bez użytkowników. Dowiedz się więcej na temat [menedżera rejestracji urządzeń](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md). ([Z powrotem do tabeli](#overview-of corporate-owned-device-enrollment-methods))

### Program Device Enrollment Program
Program Device Enrollment Program firmy Apple. Administrator tworzy i wdraża zasady bezprzewodowo na urządzeniach z systemem iOS kupionych i zarządzanych w ramach programu DEP. Gdy użytkownik uruchomi asystenta ustawień systemu iOS, urządzenie zostanie zarejestrowane. Ta metoda obsługuje tryb **nadzorcy systemu iOS**, który z kolei umożliwia:
  - Rejestrację zablokowaną
  - Dostęp warunkowy
  - Wykrywanie zdjęcia zabezpieczeń systemu
  - Zarządzanie aplikacjami mobilnymi

Dowiedz się więcej na temat [programu DEP](ios-device-enrollment-program-in-microsoft-intune.md). ([Z powrotem do tabeli](#overview-of corporate-owned-device-enrollment-methods))

### USB-SA
Połączenie USB, rejestracja za pomocą asystenta ustawień. Administrator tworzy zasady usługi Intune i eksportuje je do programu Apple Configurator. Połączone urządzenia USB są przygotowywane za pomocą zasad usługi Intune. Administrator musi ręcznie zarejestrować każde urządzenie. Użytkownicy odbierają swoje urządzenia i uruchamiają asystenta ustawień, rejestrując urządzenia. Ta metoda obsługuje tryb **nadzorcy systemu iOS**, który z kolei umożliwia:
  - Dostęp warunkowy
  - Wykrywanie zdjęcia zabezpieczeń systemu
  - Zarządzanie aplikacjami mobilnymi

Dowiedz się więcej o [rejestracji za pomocą asystenta ustawień przy użyciu programu Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md). ([Z powrotem do tabeli](#overview-of corporate-owned-device-enrollment-methods))

### USB-Direct
Rejestracja bezpośrednia. Administrator tworzy zasady usługi Intune i eksportuje je do programu Apple Configurator. Połączone urządzenia USB są rejestrowane bezpośrednio, bez konieczności resetowania do ustawień fabrycznych. Administrator musi ręcznie zarejestrować każde urządzenie. Urządzenia są zarządzane jako urządzenia bez użytkowników. Nie są zablokowane ani nadzorowane i nie obsługują dostępu warunkowego, wykrywania zdjęcia zabezpieczeń systemu i zarządzania aplikacjami mobilnymi. Dowiedz się więcej o [rejestracji bezpośredniej przy użyciu programu Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md). ([Z powrotem do tabeli](#overview-of corporate-owned-device-enrollment-methods))

**Zachowanie dla firmowych urządzeń przenośnych**

### Reset (Zresetuj)
Określa, czy zarejestrowanie urządzenia wymaga zresetowania do ustawień fabrycznych, co oznacza usunięcie wszystkich danych z urządzenia i przywrócenie go do stanu pierwotnego.
([Z powrotem do tabeli](#overview-of corporate-owned-device-enrollment-methods))

### Koligacja
Określa, czy metoda rejestracji obsługuje koligację użytkownika, która łączy urządzenie z określonym użytkownikiem. Urządzenia typu „Opt” można zarejestrować z zastosowaniem koligacji lub bez niej. Koligacja użytkownika jest wymagana do obsługi:
  - Aplikacji do zarządzania aplikacjami mobilnymi
  - Warunkowego dostępu do poczty e-mail i danych firmowych
  - Aplikacji Portal firmy

([Z powrotem do tabeli](#overview-of corporate-owned-device-enrollment-methods))

### Zablokuj
Określa, czy urządzenie można zablokować, aby uniemożliwić użytkownikowi usunięcie zasad usługi Intune, co powoduje wykluczenie urządzenia z zarządzania. Dla urządzeń z systemem iOS zablokowanie urządzenia wymaga, aby było ono w trybie nadzorcy.
([Z powrotem do tabeli](#overview-of corporate-owned-device-enrollment-methods)) ([Z powrotem do tabeli](#overview-of corporate-owned-device-enrollment-methods))


<!--HONumber=Jun16_HO3-->


