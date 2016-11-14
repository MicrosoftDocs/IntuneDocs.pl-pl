---
title: "Rejestrowanie urządzeń | Microsoft Intune"
description: "Usługa zarządzania urządzeniami przenośnymi (MDM) używa funkcji rejestracji urządzeń, która umożliwia zarządzanie urządzeniami i zapewnia dostęp do zasobów."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 09/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8fc415f7-0053-4aa5-8d2b-03202eca4b87
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 92e40930c0ccbeb3d98bef43b115fd92f24beaef
ms.openlocfilehash: 136f91e26a367ab107a80673930e735c85008ac7


---

# Rejestrowanie urządzeń do zarządzania w usłudze Intune
Rejestrowanie urządzeń, w tym komputerów z systemem Windows, pozwala na zarządzanie urządzeniami przenośnymi (MDM) w usłudze Microsoft Intune. W tym temacie opisano różne sposoby rejestrowania urządzeń przenośnych do zarządzania w usłudze Intune. Sposób rejestrowania urządzeń zależy od rodzaju urządzenia, własności i wymaganego poziomu zarządzania. Metoda rejestracji „Przynieś własne urządzenie” (BYOD) umożliwia użytkownikom rejestrowanie swoich osobistych telefonów, tabletów lub komputerów. Rejestrowanie urządzenia należącego do firmy (COD) umożliwia korzystanie ze scenariuszy zarządzania, takich jak zdalne czyszczenie danych, urządzenia współużytkowane, koligacja użytkownika w ramach urządzenia.

Organizacje korzystające z programu [Exchange ActiveSync](#mobile-device-management-with-exchange-activesync-and-intune) (lokalnie lub w chmurze) mogą używać prostszych metod zarządzania usługi Intune, w których nie jest wymagana rejestracja urządzeń. Za pomocą [oprogramowania klienckiego usługi Intune](#manage-windows-pcs-with-intune) można również zarządzać komputerami z systemem Windows.

## Przegląd metod rejestracji urządzeń

W poniższej tabeli przedstawiono metody rejestracji w usłudze Intune wraz z funkcjami przez nie obsługiwanymi. Te funkcje obejmują:
- **Czyszczenie danych** — powoduje zresetowanie urządzenia do ustawień fabrycznych i usunięcie wszystkich danych. Aby uzyskać więcej informacji, zobacz [Wycofywanie urządzeń](retire-devices-from-microsoft-intune-management.md).
- **Koligacja** — kojarzy urządzenia z użytkownikami. Wymagane w celu zarządzania aplikacjami mobilnymi (MAM) i uzyskiwania warunkowego dostępu do danych firmowych. Aby uzyskać więcej informacji, zobacz [Koligacja użytkownika](enroll-corporate-owned-ios-devices-in-microsoft-intune.md#using-company-portal-on-dep-or-apple-configurator-enrolled-devices).
- **Zablokuj** — uniemożliwia użytkownikom usunięcie urządzenia z zarządzania. Urządzenia z systemem iOS wymagają trybu nadzorcy w celu dokonania blokady. Aby uzyskać więcej informacji, zobacz [Zdalne blokowanie](retire-devices-from-microsoft-intune-management.md#block-access-a-device).

**Metody rejestracji urządzeń z systemem iOS**

| **Metoda** |  **Czyszczenie danych** |  **Koligacja**    |   **Zablokuj** | **Szczegóły** |
|:---:|:---:|:---:|:---:|:---:|
|**[„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)](#byod)** | Nie|    Tak |   Nie | [Więcej informacji](prerequisites-for-enrollment.md#set-up-device-management)|
|**[Menedżer rejestracji urządzeń](#dem)**|   Nie |Nie |Nie  | [Więcej informacji](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|
|**[Program Device Enrollment Program](#dep)**|   Tak |   Opcjonalne |  Opcjonalne|[Więcej informacji](ios-device-enrollment-program-in-microsoft-intune.md)|
|**[USB-SA](#usb-sa)**| Tak |   Opcjonalne |  Nie| [Więcej informacji](ios-setup-assistant-enrollment-in-microsoft-intune.md)|
|**[USB-Direct](#usb-direct)**| Nie |    Nie  | Nie|[Więcej informacji](ios-direct-enrollment-in-microsoft-intune.md)|

**Metody rejestracji systemu Windows**

| **Metoda** |  **Czyszczenie danych** |  **Koligacja**    |   **Zablokuj** | **Szczegóły**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)](#byod)** | Tak|   Tak |   Nie | [Więcej informacji](prerequisites-for-enrollment.md#set-up-device-management)|
|**[Menedżer rejestracji urządzeń](#dem)**|   Nie |Nie |Nie  |[Więcej informacji](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

**Metody rejestracji systemu Android**

| **Metoda** |  **Czyszczenie danych** |  **Koligacja**    |   **Zablokuj** | **Szczegóły**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)](#byod)** | Nie|    Tak |   Nie | [Więcej informacji](prerequisites-for-enrollment.md#set-up-device-management)|
|**[Menedżer rejestracji urządzeń](#dem)**|   Nie |Nie |Nie  |[Więcej informacji](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

W dobraniu odpowiedniej metody rejestrowania pomogą pytania znajdujące się w temacie [Wybieranie metody rejestrowania urządzeń](/intune/get-started/choose-how-to-enroll-devices1).

## „Przynieś własne urządzenie” (BYOD, Bring Your Own Device)
Użytkownicy korzystający z metody „Przynieś własne urządzenie” instalują aplikację Portal firmy i rejestrują swoje urządzenie. Umożliwia to użytkownikom nawiązanie połączenia z siecią firmową i dołączenie do domeny lub usługi Azure Active Directory. W przypadku większości platform należy włączyć rejestrowanie w trybie „Przynieś własne urządzenie” (BYOD, bring your own device) w wielu scenariuszach dotyczących urządzeń należących do firmy (COD, company-owned device). Aby uzyskać więcej informacji, zobacz [Wymagania wstępne dotyczące rejestracji urządzeń](prerequisites-for-enrollment.md). ([Powrót do tabeli](#overview-of-device-enrollment-methods))

## Urządzenia należące do firmy
Urządzeniami należącymi do firmy można zarządzać za pomocą konsoli usługi Intune. Urządzenia z systemem iOS można zarejestrować bezpośrednio za pomocą narzędzi dostarczonych przez firmę Apple. Wszystkie typy urządzeń mogą być rejestrowane przez administratora lub menedżera za pomocą menedżera rejestracji urządzeń. Urządzenia z numerem IMEI można również zidentyfikować i oznaczyć jako należące do firmy, umożliwiając korzystanie ze scenariuszy COD.

Aby uzyskać więcej informacji, zobacz [Rejestrowanie urządzeń należących do firmy](manage-corporate-owned-devices.md).

### Menedżer rejestracji urządzeń
Menedżer rejestracji urządzeń to specjalne konto usługi Intune używane do rejestrowania wielu urządzeń należących do firmy i zarządzania nimi. Menedżerowie mogą zainstalować Portal firmy i zarejestrować wiele urządzeń bez użytkowników. Dowiedz się więcej na temat [menedżera rejestracji urządzeń](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md). ([Powrót do tabeli](#overview-of-device-enrollment-methods))

### Program Device Enrollment Program
Zarządzanie w programie Device Enrollment Program (DEP) firmy Apple pozwala na tworzenie i bezprzewodowe wdrażanie zasad na urządzeniach z systemem iOS kupionych i zarządzanych przy użyciu programu DEP. Urządzenie jest rejestrowane, gdy użytkownik włącza je po raz pierwszy i uruchamia asystenta ustawień systemu iOS. Ta metoda obsługuje tryb **nadzorcy systemu iOS**, który z kolei umożliwia:
  - Rejestrację zablokowaną
  - Dostęp warunkowy
  - Wykrywanie zdjęcia zabezpieczeń systemu
  - Zarządzanie aplikacjami mobilnymi

Dowiedz się więcej na temat [programu DEP](ios-device-enrollment-program-in-microsoft-intune.md). ([Powrót do tabeli](#overview-of-device-enrollment-methods))

### USB-SA
Połączone urządzenia USB należące do firmy są przygotowywane za pomocą zasad usługi Intune. Na potrzeby rejestracji asystenta ustawień administrator tworzy zasady usługi Intune i eksportuje je do programu Apple Configurator. Administrator musi ręcznie zarejestrować każde urządzenie. Użytkownicy odbierają swoje urządzenia i uruchamiają asystenta ustawień, rejestrując urządzenia. Ta metoda obsługuje tryb **nadzorcy systemu iOS**, który z kolei umożliwia:
  - Dostęp warunkowy
  - Wykrywanie zdjęcia zabezpieczeń systemu
  - Zarządzanie aplikacjami mobilnymi

Dowiedz się więcej o [rejestracji za pomocą asystenta ustawień przy użyciu programu Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md). ([Powrót do tabeli](#overview-of-device-enrollment-methods))

### USB-Direct
W celu bezpośredniej rejestracji administrator tworzy zasady usługi Intune i eksportuje je do programu Apple Configurator. Urządzenia USB należące do firmy są rejestrowane bezpośrednio, bez konieczności resetowania do ustawień fabrycznych. Administrator musi ręcznie zarejestrować każde urządzenie. Urządzenia są zarządzane jako urządzenia bez użytkowników. Nie są zablokowane ani nadzorowane i nie obsługują dostępu warunkowego, wykrywania zdjęcia zabezpieczeń systemu ani zarządzania aplikacjami mobilnymi. Dowiedz się więcej o [rejestracji bezpośredniej przy użyciu programu Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md). ([Powrót do tabeli](#overview-of-device-enrollment-methods))

## Zarządzanie urządzeniami przenośnymi za pomocą programu Exchange ActiveSync i usługi Intune
Urządzeniami przenośnymi, które nie są zarejestrowane, ale są połączone z programem Exchange ActiveSync (EAS), można zarządzać za pomocą usługi Intune, korzystając z zasad EAS MDM. Usługa Intune używa łącznika Exchange Connector do komunikowania się z programem EAS (lokalnym lub hostowanym w chmurze).

Aby uzyskać więcej informacji, zobacz [Zarządzanie urządzeniami przenośnymi za pomocą programu Exchange ActiveSync i usługi Intune](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md).


## Zarządzanie komputerami z systemem Windows przy użyciu usługi Intune  
Usługa Microsoft Intune umożliwia również zarządzanie komputerami z systemem Windows za pomocą oprogramowania klienckiego usługi Intune. Komputery z systemem Windows zarządzane za pomocą klienta usługi Intune mogą:

 - Zgłaszać spisy sprzętu i oprogramowania.
 - Instalować aplikacje komputerowe (np. pliki .exe i .msi).
 - Ustawienia zapory

Komputery zarządzane przy użyciu oprogramowania klienckiego usługi Intune nie mogą zostać w pełni wyczyszczone, ale czyszczenie selektywne jest dostępne. Komputery zarządzane przy użyciu oprogramowania klienckiego usługi Intune nie mogą korzystać z wielu funkcji zarządzania w usłudze Intune, takich jak dostęp warunkowy, ustawienia sieci VPN i Wi-Fi, wdrażanie certyfikatów i konfiguracja poczty e-mail.

Aby uzyskać więcej informacji, zobacz [Zarządzanie komputerami z systemem Windows przy użyciu usługi Intune](manage-windows-pcs-with-microsoft-intune.md).

## Obsługiwane platformy urządzeń

Usługa Intune umożliwia zarządzanie następującymi platformami urządzeń:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

## Następne kroki
- [Wymagania wstępne dotyczące rejestracji urządzeń](prerequisites-for-enrollment.md)
- [Zarządzanie urządzeniami należącymi do firmy](manage-corporate-owned-devices.md)
- [Obsługiwane urządzenia przenośne i komputery](../get-started/supported-mobile-devices-and-computers.md)



<!--HONumber=Oct16_HO3-->


