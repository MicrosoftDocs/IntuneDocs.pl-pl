---
title: "Rejestrowanie urządzeń | Microsoft Intune"
description: "Usługa zarządzania urządzeniami przenośnymi (MDM) używa funkcji rejestracji urządzeń, która umożliwia zarządzanie urządzeniami i zapewnia dostęp do zasobów."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8fc415f7-0053-4aa5-8d2b-03202eca4b87
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d8e524b267622f91ed0c2ed854f931299f316312
ms.openlocfilehash: 15f4af1f870d619f4fd51e88d1aef91b0b45e66d


---

# Rejestrowanie urządzeń do zarządzania w usłudze Intune
Usługa zarządzania urządzeniami przenośnymi Microsoft Intune (MDM) używa rejestracji urządzeń, która umożliwia zarządzanie urządzeniami i zapewnia dostęp do zasobów. Sposób rejestrowania urządzeń zależy od rodzaju urządzenia, własności i wymaganego poziomu zarządzania. W scenariuszach opartych na strategii „przynieś własne urządzenie” (BYOD) i urządzeniach należących do firmy (COD) wymaga się procesu rejestracji urządzeń. Organizacje korzystające z programu Exchange ActiveSync (lokalnie lub w chmurze) mogą używać lżejszych metod zarządzania, w których nie wymaga się rejestracji urządzeń. Za pomocą oprogramowania klienckiego usługi Intune można również zarządzać komputerami z systemem Windows.

###  Obsługiwane platformy urządzeń

Usługa Intune umożliwia zarządzanie następującymi platformami urządzeń:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

## Przegląd metod rejestracji urządzeń

W poniższej tabeli przedstawiono metody rejestracji urządzeń firmowych oraz ich zalety.

**Metody rejestracji urządzeń z systemem iOS**

| **Metoda** |  **[Czyszczenie danych](#Wipe)** | **[Koligacja](#Affinity)**   |   **[Zablokowana](#Lock)** |
|:---:|:---:|:---:|:---:|
|**[„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)](#BYOD)** | Nie|    Tak |   Nie |
|**[Menedżer rejestracji urządzeń](#DEM)**|   Nie |Nie |Nie  |
|**[Program Device Enrollment Program](#DEP)**|   Tak |   Opt |   Opt|
|**[USB-SA](#USB-SA)**| Tak |   Opt |   Nie|
|**[USB-Direct](#USB-Direct)**| Nie |    Nie  | Nie|

**Metody rejestracji urządzeń z systemami Windows i Android**

| **Metoda** |  **[Czyszczenie danych](#Wipe)** | **[Koligacja](#Affinity)**   |   **[Zablokowana](#Lock)** |
|:---:|:---:|:---:|:---:|
|**[„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)](#BYOD)** | Nie|    Tak |   Nie |
|**[Menedżer rejestracji urządzeń](#DEM)**|   Nie |Nie |Nie  |

**Metody rejestracji firmowych urządzeń**

### „Przynieś własne urządzenie” (BYOD, Bring Your Own Device)
„Przynieś własne urządzenie”. Użytkownicy instalują aplikację Portal firmy i rejestrują swoje urządzenia. Zarejestrowanie urządzenia w portalu firmy spowoduje dołączenie urządzenia do miejsca pracy. Zarejestrowanie urządzeń z systemem iOS w portalu firmy wymaga identyfikatora firmy Apple. Urządzenia BYOD nie wymagają dodatkowej konfiguracji w przypadku urządzeń firmowych. Zobacz kroki [konfigurowania zarządzania urządzeniami](get-ready-to-enroll-devices-in-microsoft-intune.md#set-up-device-management). ([Powrót do tabeli](#overview-of-device-enrollment-methods))

### Menedżer rejestracji urządzeń
Menedżer rejestracji urządzeń. Administrator tworzy konta menedżera rejestracji urządzeń w celu zarządzania urządzeniami należącymi do firmy. Menedżerowie mogą wtedy zainstalować portal firmy i zarejestrować wiele urządzeń bez użytkowników. Dowiedz się więcej na temat [menedżera rejestracji urządzeń](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md). ([Powrót do tabeli](#overview-of-device-enrollment-methods))

### Program Device Enrollment Program
Program Device Enrollment Program firmy Apple. Administrator tworzy i wdraża zasady bezprzewodowo na należących do firmy urządzeniach z systemem iOS zakupionych i zarządzanych w ramach programu DEP. Gdy użytkownik uruchomi asystenta ustawień systemu iOS, urządzenie zostanie zarejestrowane. Ta metoda obsługuje tryb **nadzorcy systemu iOS**, który z kolei umożliwia:
  - Rejestrację zablokowaną
  - Dostęp warunkowy
  - Wykrywanie zdjęcia zabezpieczeń systemu
  - Zarządzanie aplikacjami mobilnymi

Dowiedz się więcej na temat [programu DEP](ios-device-enrollment-program-in-microsoft-intune.md). ([Powrót do tabeli](#overview-of-device-enrollment-methods))

### USB-SA
Połączenie USB, rejestracja za pomocą asystenta ustawień. Administrator tworzy zasady usługi Intune i eksportuje je do programu Apple Configurator. Połączone urządzenia USB należące do firmy są przygotowywane za pomocą zasad usługi Intune. Administrator musi ręcznie zarejestrować każde urządzenie. Użytkownicy odbierają swoje urządzenia i uruchamiają asystenta ustawień, rejestrując urządzenia. Ta metoda obsługuje tryb **nadzorcy systemu iOS**, który z kolei umożliwia:
  - Dostęp warunkowy
  - Wykrywanie zdjęcia zabezpieczeń systemu
  - Zarządzanie aplikacjami mobilnymi

Dowiedz się więcej o [rejestracji za pomocą asystenta ustawień przy użyciu programu Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md). ([Powrót do tabeli](#overview-of-device-enrollment-methods))

### USB-Direct
Rejestracja bezpośrednia. Administrator tworzy zasady usługi Intune i eksportuje je do programu Apple Configurator. Połączone urządzenia USB należące do firmy są rejestrowane bezpośrednio, bez konieczności resetowania do ustawień fabrycznych. Administrator musi ręcznie zarejestrować każde urządzenie. Urządzenia są zarządzane jako urządzenia bez użytkowników. Nie są zablokowane ani nadzorowane i nie obsługują dostępu warunkowego, wykrywania zdjęcia zabezpieczeń systemu i zarządzania aplikacjami mobilnymi. Dowiedz się więcej o [rejestracji bezpośredniej przy użyciu programu Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md). ([Powrót do tabeli](#overview-of-device-enrollment-methods))

**Zachowanie dla firmowych urządzeń przenośnych**

### Czyszczenie danych
Określa, czy zarejestrowanie urządzenia wymaga zresetowania do ustawień fabrycznych, co oznacza usunięcie wszystkich danych z urządzenia i przywrócenie go do stanu pierwotnego.
[Wycofywanie urządzeń](retire-devices-from-microsoft-intune-management.md) ([Powrót do tabeli](#overview-of-device-enrollment-methods))

### Koligacja
Określa, czy metoda rejestracji obsługuje koligację użytkownika, która łączy urządzenie z określonym użytkownikiem. Urządzenia typu „Opt” można zarejestrować z zastosowaniem koligacji lub bez niej. Koligacja użytkownika jest wymagana do obsługi:
  - Aplikacji do zarządzania aplikacjami mobilnymi
  - Warunkowego dostępu do poczty e-mail i danych firmowych
  - Aplikacji Portal firmy

[Koligacja użytkownika](enroll-corporate-owned-ios-devices-in-microsoft-intune.md#using-company-portal-on-dep-or-apple-configurator-enrolled-devices) ([Powrót do tabeli](#overview-of-device-enrollment-methods))

### Zablokuj
Określa, czy urządzenie można zablokować, aby uniemożliwić użytkownikowi usunięcie zasad usługi Intune, co powoduje wykluczenie urządzenia z zarządzania. Dla urządzeń z systemem iOS zablokowanie urządzenia wymaga, aby było ono w trybie nadzorcy.
([Powrót do tabeli](#overview-of-device-enrollment-methods))

## Włączanie rejestracji urządzeń  
 Rejestracja umożliwia użytkownikom uzyskiwanie dostępu do zasobów firmowych na swoich urządzeniach osobistych. Dzięki niej administrator może upewnić się, że urządzenia są zgodne z zasadami chroniącymi zasoby firmowe. Jest to najlepszy sposób na skorzystanie ze strategii „przynieś własne urządzenie” z usługą Intune. Administrator musi włączyć rejestrację w konsoli usługi Intune. Może to wymagać utworzenia zaufanej relacji z urządzeniem i przypisania licencji do użytkowników. Następnie urządzenie jest rejestrowane, zazwyczaj przez użytkowników, którzy muszą wprowadzić poświadczenia służbowe. Urządzenie otrzymuje zasady z usługi Intune i uzyskuje dostęp do zasobów.

[Przygotowanie do rejestracji urządzeń w usłudze Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)

## Rejestrowanie urządzeń należących do firmy
Urządzeniami należącymi do firmy (COD) można zarządzać za pomocą konsoli usługi Intune. Urządzenia z systemem iOS można zarejestrować bezpośrednio za pomocą narzędzi dostarczonych przez firmę Apple. Wszystkie typy urządzeń mogą być rejestrowane przez administratora lub menedżera za pomocą menedżera rejestracji urządzeń. Urządzenia z numerem IMEI można również zidentyfikować i oznaczyć jako należące do firmy, umożliwiając korzystanie ze scenariuszy COD.

[Rejestrowanie urządzeń należących do firmy](manage-corporate-owned-devices.md)

## Zarządzanie urządzeniami przenośnymi za pomocą programu Exchange ActiveSync i usługi Intune
Urządzeniami przenośnymi, które nie są zarejestrowane, ale są połączone z programem Exchange ActiveSync (EAS), można zarządzać za pomocą usługi Intune, korzystając z zasad EAS MDM. Usługa Intune używa łącznika Exchange Connector do komunikowania się z programem EAS (lokalnym lub hostowanym w chmurze).

[Zarządzanie urządzeniami przenośnymi za pomocą programu Exchange ActiveSync i usługi Intune](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md)


## Zarządzanie komputerami z systemem Windows przy użyciu usługi Intune  
Usługa Microsoft Intune umożliwia również zarządzanie komputerami z system Windows za pomocą komputerowego oprogramowania klienckiego usługi Intune dla systemu Windows. Komputery z systemem Windows zarządzane za pomocą klienta usługi Intune mogą:

 - Zgłaszać spisy sprzętu i oprogramowania.
 - Instalować aplikacje komputerowe (np. pliki .exe i .msi).
 - Ustawienia zapory

Komputery zarządzane przy użyciu oprogramowania klienckiego usługi Intune nie mogą być wybiórczo wyczyszczone lub wycofane. Ponadto nie mogą korzystać z wielu funkcji zarządzania usługi Intune, np. dostępu warunkowego, ustawień połączenia VPN i Wi-Fi lub wdrażania certyfikatów i konfiguracji poczty e-mail.

[Zarządzanie komputerami z systemem Windows przy użyciu usługi Intune](manage-windows-pcs-with-microsoft-intune.md)



<!--HONumber=Aug16_HO1-->


