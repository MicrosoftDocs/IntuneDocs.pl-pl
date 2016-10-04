---
title: "Rejestrowanie urządzeń | Microsoft Intune"
description: "Usługa zarządzania urządzeniami przenośnymi (MDM) używa funkcji rejestracji urządzeń, która umożliwia zarządzanie urządzeniami i zapewnia dostęp do zasobów."
keywords: 
author: NathBarn
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
ms.sourcegitcommit: c880bd9dfb998355a18e78af898a96d4cee393f7
ms.openlocfilehash: 145d373edd65d7ba01c696c3b851692a13831dad


---

# Rejestrowanie urządzeń do zarządzania w usłudze Intune
Rejestrowanie urządzeń, w tym komputerów z systemem Windows, pozwala na zarządzanie urządzeniami przenośnymi (MDM) w usłudze Microsoft Intune. W tym temacie opisano różne sposoby rejestrowania urządzeń przenośnych do zarządzania w usłudze Intune. Sposób rejestrowania urządzeń zależy od rodzaju urządzenia, własności i wymaganego poziomu zarządzania. Metoda rejestracji „Przynieś własne urządzenie” (BYOD) umożliwia użytkownikom rejestrowanie swoich osobistych telefonów, tabletów lub komputerów. Rejestrowanie urządzenia należącego do firmy (COD) umożliwia korzystanie ze scenariuszy zarządzania, takich jak zdalne czyszczenie danych, urządzenia współużytkowane, koligacja użytkownika w ramach urządzenia.

Organizacje korzystające z programu [Exchange ActiveSync](#mobile-device-management-with-exchange-activesync-and-intune) (lokalnie lub w chmurze) mogą używać prostszych metod zarządzania usługi Intune, w których nie jest wymagana rejestracja urządzeń. Za pomocą [oprogramowania klienckiego usługi Intune](#manage-windows-pcs-with-intune) można również zarządzać komputerami z systemem Windows.

## Przegląd metod rejestracji urządzeń

W poniższej tabeli przedstawiono metody rejestracji w usłudze Intune wraz z funkcjami przez nie obsługiwanymi. Te funkcje obejmują:
- **Czyszczenie danych** — powoduje zresetowanie urządzenia do ustawień fabrycznych i usunięcie wszystkich danych. [Wycofywanie urządzeń](retire-devices-from-microsoft-intune-management.md)
- **Koligacja** — kojarzy urządzenia z użytkownikami. Wymagane w celu zarządzania aplikacjami mobilnymi (MAM) i uzyskiwania warunkowego dostępu do danych firmowych. [Koligacja użytkownika](enroll-corporate-owned-ios-devices-in-microsoft-intune.md#using-company-portal-on-dep-or-apple-configurator-enrolled-devices)
- **Zablokuj** Uniemożliwia użytkownikom usunięcie urządzenia z zarządzania. Urządzenia z systemem iOS wymagają trybu nadzorcy w celu dokonania blokady. [Zdalne blokowanie](retire-devices-from-microsoft-intune-management.md#block-access-a-device)

**Metody rejestracji urządzeń z systemem iOS**

| **Metoda** |  **Czyszczenie danych** |  **Koligacja**    |   **Zablokuj** | **Szczegóły** |
|:---:|:---:|:---:|:---:|:---:|
|**[„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)](#byod)** | Nie|    Tak |   Nie | [więcej](prerequisites-for-enrollment.md#set-up-device-management)|
|**[Menedżer rejestracji urządzeń](#dem)**|   Nie |Nie |Nie  | [więcej](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|
|**[Program Device Enrollment Program](#dep)**|   Tak |   Opcjonalne |  Opcjonalne|[więcej](ios-device-enrollment-program-in-microsoft-intune.md)|
|**[USB-SA](#usb-sa)**| Tak |   Opcjonalne |  Nie| [więcej](ios-setup-assistant-enrollment-in-microsoft-intune.md)|
|**[USB-Direct](#usb-direct)**| Nie |    Nie  | Nie|[więcej](ios-direct-enrollment-in-microsoft-intune.md)|

**Metody rejestracji systemu Windows**

| **Metoda** |  **Czyszczenie danych** |  **Koligacja**    |   **Zablokuj** | **Szczegóły**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)](#byod)** | Tak|   Tak |   Nie | [więcej](prerequisites-for-enrollment.md#set-up-device-management)|
|**[Menedżer rejestracji urządzeń](#dem)**|   Nie |Nie |Nie  |[więcej](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

**Metody rejestracji systemu Android**

| **Metoda** |  **Czyszczenie danych** |  **Koligacja**    |   **Zablokuj** | **Szczegóły**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)](#byod)** | Nie|    Tak |   Nie | [więcej](prerequisites-for-enrollment.md#set-up-device-management)|
|**[Menedżer rejestracji urządzeń](#dem)**|   Nie |Nie |Nie  |[więcej](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

W dobraniu odpowiedniej metody rejestrowania pomogą pytania znajdujące się w temacie [Wybieranie metody rejestrowania urządzeń](/intune/get-started/choose-how-to-enroll-devices1).

## „Przynieś własne urządzenie” (BYOD, Bring Your Own Device)
Użytkownicy korzystający z metody „Przynieś własne urządzenie” instalują aplikację Portal firmy i rejestrują swoje urządzenie. Może to umożliwić użytkownikom nawiązanie połączenia z siecią firmową, dołączenie do domeny lub usługi Azure Active Directory. Włączenie rejestracji typu „Przynieś własne urządzenie” (BYOD) jest wymagane przez większość platform w wielu scenariuszach dotyczących urządzeń należących do firmy (COD). Zobacz temat [Prerequisites for device enrollment](prerequisites-for-enrollment.md) (Wymagania wstępne dotyczące rejestracji urządzeń). ([Powrót do tabeli](#overview-of-device-enrollment-methods))

## Urządzenia należące do firmy
Urządzeniami należącymi do firmy (COD) można zarządzać za pomocą konsoli usługi Intune. Urządzenia z systemem iOS można zarejestrować bezpośrednio za pomocą narzędzi dostarczonych przez firmę Apple. Wszystkie typy urządzeń mogą być rejestrowane przez administratora lub menedżera za pomocą menedżera rejestracji urządzeń. Urządzenia z numerem IMEI można również zidentyfikować i oznaczyć jako należące do firmy, umożliwiając korzystanie ze scenariuszy COD.

[Rejestrowanie urządzeń należących do firmy](manage-corporate-owned-devices.md)

### Menedżer rejestracji urządzeń
Menedżer rejestracji urządzeń to specjalne konto usługi Intune używane do rejestrowania i zarządzania wieloma urządzeniami należącymi do firmy. Menedżerowie mogą zainstalować Portal firmy i zarejestrować wiele urządzeń bez użytkowników. Dowiedz się więcej na temat [menedżera rejestracji urządzeń](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md). ([Powrót do tabeli](#overview-of-device-enrollment-methods))

### Program Device Enrollment Program
Zarządzanie w programie Device Enrollment Program (DEP) firmy Apple pozwala na tworzenie i wdrażanie zasad „bez udziału użytkownika” w urządzeniach z systemem iOS kupionych i zarządzanych przy użyciu programu DEP. Urządzenie jest rejestrowane, gdy użytkownik włącza je po raz pierwszy i uruchamia asystenta ustawień systemu iOS. Ta metoda obsługuje tryb **nadzorcy systemu iOS**, który z kolei umożliwia:
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

## Zarządzanie urządzeniami przenośnymi za pomocą programu Exchange ActiveSync i usługi Intune
Urządzeniami przenośnymi, które nie są zarejestrowane, ale są połączone z programem Exchange ActiveSync (EAS), można zarządzać za pomocą usługi Intune, korzystając z zasad EAS MDM. Usługa Intune używa łącznika Exchange Connector do komunikowania się z programem EAS (lokalnym lub hostowanym w chmurze).

[Zarządzanie urządzeniami przenośnymi za pomocą programu Exchange ActiveSync i usługi Intune](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md)


## Zarządzanie komputerami z systemem Windows przy użyciu usługi Intune  
Usługa Microsoft Intune umożliwia również zarządzanie komputerami z systemem Windows za pomocą oprogramowania klienckiego usługi Intune. Komputery z systemem Windows zarządzane za pomocą klienta usługi Intune mogą:

 - Zgłaszać spisy sprzętu i oprogramowania.
 - Instalować aplikacje komputerowe (np. pliki .exe i .msi).
 - Ustawienia zapory

Komputery zarządzane przy użyciu oprogramowania klienckiego usługi Intune nie mogą być wyczyszczone i nie mogą korzystać z wielu funkcji zarządzania w usłudze Intune, takich jak dostęp warunkowy, ustawienia sieci VPN i Wi-Fi, wdrażanie certyfikatów i konfiguracja poczty e-mail.

[Zarządzanie komputerami z systemem Windows przy użyciu usługi Intune](manage-windows-pcs-with-microsoft-intune.md)

##  Obsługiwane platformy urządzeń

Usługa Intune umożliwia zarządzanie następującymi platformami urządzeń:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

## Następne kroki
- [Wymagania wstępne dotyczące rejestracji urządzeń](prerequisites-for-enrollment.md)
- [Zarządzanie urządzeniami należącymi do firmy](manage-corporate-owned-devices.md)
- [Obsługiwane urządzenia przenośne i komputery](../get-started/supported-mobile-devices-and-computers.md)



<!--HONumber=Sep16_HO4-->


