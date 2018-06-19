---
title: Rejestrowanie urządzeń
description: Usługa zarządzania urządzeniami przenośnymi (MDM) używa funkcji rejestracji urządzeń, która umożliwia zarządzanie urządzeniami i zapewnia dostęp do zasobów.
keywords: ''
author: nathbarn
ms.author: nathbarn
manager: dougeby
ms.date: 09/22/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8fc415f7-0053-4aa5-8d2b-03202eca4b87
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 3cae9bc1b76dba3b896957f60ca08cca53423267
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
ms.locfileid: "31026985"
---
# <a name="enroll-devices-for-management-in-intune"></a>Rejestrowanie urządzeń do zarządzania w usłudze Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Rejestrowanie urządzeń, w tym komputerów z systemem Windows, pozwala na zarządzanie urządzeniami przenośnymi (MDM) w usłudze Microsoft Intune. W tym temacie opisano różne sposoby rejestrowania urządzeń przenośnych do zarządzania w usłudze Intune. Sposób rejestrowania urządzeń zależy od rodzaju urządzenia, własności i wymaganego poziomu zarządzania. Metoda rejestracji „Przynieś własne urządzenie” (BYOD) umożliwia użytkownikom rejestrowanie swoich osobistych telefonów, tabletów lub komputerów. Rejestracja urządzeń należących do firmy umożliwia korzystanie ze scenariuszy zarządzania, takich jak automatyczne rejestrowanie, urządzenia udostępnione lub wstępnie autoryzowane wymagania dotyczące rejestracji.

Organizacje korzystające z programu [Exchange ActiveSync](#mobile-device-management-with-exchange-activesync-and-intune) (lokalnie lub w chmurze) mogą używać prostszych metod zarządzania usługi Intune, w których nie jest wymagana rejestracja urządzeń. Za pomocą [oprogramowania klienckiego usługi Intune](#windows-pc-management-with-intune) można również zarządzać komputerami z systemem Windows.

Domyślnie w usłudze Intune mogą być rejestrowane urządzenia dla dowolnej platformy. Aby zablokować możliwość rejestrowania urządzeń, zaloguj się do [portalu administracyjnego usługi Microsoft Intune](https://manage.microsoft.com), korzystając z poświadczeń administratora. Wybierz pozycję **Administracja** > **Zarządzanie urządzeniami przenośnymi** > **Reguły rejestracji**, a następnie wyczyść pola wyboru odpowiadające platformom, które chcesz zablokować.

## <a name="overview-of-device-enrollment-methods"></a>Przegląd metod rejestracji urządzeń

W poniższej tabeli przedstawiono metody rejestracji usługi Intune oraz wymagania i obsługiwane możliwości każdej metody. Te wymagania i możliwości zostały opisane poniżej.

- **Czyszczenie** — określa, czy urządzenie musi zostać wyczyszczone, zanim użytkownicy będą mogli je zarejestrować. Termin „czyszczenie” oznacza zresetowanie urządzenia do ustawień fabrycznych, co powoduje usunięcie wszystkich danych. Aby uzyskać więcej informacji, zobacz [Wycofywanie urządzeń](retire-devices-from-microsoft-intune-management.md).
- **Koligacja** — kojarzy urządzenia z użytkownikami. Wymagane w celu zarządzania aplikacjami mobilnymi (MAM) i uzyskiwania warunkowego dostępu do danych firmowych. Aby uzyskać więcej informacji, zobacz [Koligacja użytkownika](enroll-corporate-owned-ios-devices-in-microsoft-intune.md#use-the-company-portal-on-dep-enrolled-or-apple-configurator-enrolled-devices).
- **Blokada** — wskazuje, czy użytkownicy mają zablokowaną możliwość wyrejestrowywania swoich urządzeń przy użyciu natywnych menu systemu operacyjnego. Użytkownicy mogą wyrejestrowywać swoje urządzenia na wszystkich platformach przy użyciu aplikacji Portal firmy.

**Metody rejestracji urządzeń z systemem iOS**

| **Metoda** |  **Wymagane wyczyszczenie?** |    **Koligacja**    |   **Blokada** | **Szczegóły** |
|:---:|:---:|:---:|:---:|:---:|
|**[„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)](#byod)** | Nie|    Tak |   Nie | [Więcej informacji](prerequisites-for-enrollment.md)|
|**[Menedżer rejestracji urządzeń](#dem)**|   Nie |Nie |Nie  | [Więcej informacji](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|
|**[Device Enrollment Program](#dep)**|   Tak |   Opcjonalne |  Opcjonalne|[Więcej informacji](ios-device-enrollment-program-in-microsoft-intune.md)|
|**[USB-SA](#usb-sa)**| Tak |   Opcjonalne |  Nie| [Więcej informacji](ios-setup-assistant-enrollment-in-microsoft-intune.md)|
|**[USB-Direct](#usb-direct)**| Nie |    Nie  | Nie|[Więcej informacji](ios-direct-enrollment-in-microsoft-intune.md)|

**Metody rejestracji urządzeń z systemem Windows**

| **Metoda** |  **Wymagane wyczyszczenie?** |    **Koligacja**    |   **Blokada** | **Szczegóły**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)](#byod)** | Nie|    Tak |   Nie | [Więcej informacji](prerequisites-for-enrollment.md)|
|**[Menedżer rejestracji urządzeń](#dem)**|   Nie |Nie |Nie  |[Więcej informacji](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

**Metody rejestracji urządzeń z systemem Android**

| **Metoda** |  **Wymagane wyczyszczenie?** |    **Koligacja**    |   **Blokada** | **Szczegóły**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)](#byod)** | Nie|    Tak |   Nie | [Więcej informacji](prerequisites-for-enrollment.md)|
|**[Menedżer rejestracji urządzeń](#dem)**|   Nie |Nie |Nie  |[Więcej informacji](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

**Metody rejestracji programu Android for Work**

| **Metoda** |  **Wymagane wyczyszczenie?** |    **Koligacja**    |   **Blokada** | **Szczegóły**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)](#byod)** | Nie|    Tak |   Nie | [Więcej informacji](prerequisites-for-enrollment.md)|
|**[Menedżer rejestracji urządzeń](#dem)**|   Nie |Nie |Nie  |[Więcej informacji](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

**Metody rejestracji urządzeń z systemem macOS**

| **Metoda** |  **Wymagane wyczyszczenie?** |    **Koligacja**    |   **Blokada** | **Szczegóły**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)](#byod)** | Nie|    Tak |   Nie | [Więcej informacji](prerequisites-for-enrollment.md)|


W dobraniu odpowiedniej metody rejestrowania pomogą pytania znajdujące się w temacie [Wybieranie metody rejestrowania urządzeń](/intune-classic/get-started/choose-how-to-enroll-devices1).

## <a name="byod"></a>„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)
Użytkownicy korzystający z metody „Przynieś własne urządzenie” instalują aplikację Portal firmy i rejestrują swoje urządzenie. Umożliwia to użytkownikom nawiązanie połączenia z siecią firmową i dołączenie do domeny lub usługi Azure Active Directory. W przypadku większości platform należy włączyć rejestrowanie w trybie „Przynieś własne urządzenie” (BYOD, bring your own device) w wielu scenariuszach dotyczących urządzeń należących do firmy (COD, company-owned device). Aby uzyskać więcej informacji, zobacz [Wymagania wstępne dotyczące rejestracji urządzeń](prerequisites-for-enrollment.md). ([Powrót do tabeli](#overview-of-device-enrollment-methods))

## <a name="corporate-owned-devices"></a>Urządzenia należące do firmy
Urządzeniami należącymi do firmy można zarządzać za pomocą konsoli usługi Intune. Urządzenia z systemem iOS można zarejestrować bezpośrednio za pomocą narzędzi dostarczonych przez firmę Apple. Wszystkie typy urządzeń mogą być rejestrowane przez administratora lub menedżera za pomocą menedżera rejestracji urządzeń. Urządzenia z numerem IMEI można również zidentyfikować i oznaczyć jako należące do firmy, umożliwiając korzystanie ze scenariuszy COD.

Aby uzyskać więcej informacji, zobacz [Rejestrowanie urządzeń należących do firmy](manage-corporate-owned-devices.md).

### <a name="dem"></a>Menedżer rejestracji urządzeń
Menedżer rejestracji urządzeń to specjalne konto usługi Intune używane do rejestrowania wielu urządzeń należących do firmy i zarządzania nimi. Menedżerowie mogą zainstalować Portal firmy i zarejestrować wiele urządzeń bez użytkowników. Dowiedz się więcej na temat [menedżera rejestracji urządzeń](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md). ([Powrót do tabeli](#overview-of-device-enrollment-methods))

### <a name="dep"></a>Program Device Enrollment Program
Zarządzanie w programie Device Enrollment Program (DEP) firmy Apple pozwala na tworzenie i bezprzewodowe wdrażanie zasad na urządzeniach z systemem iOS kupionych i zarządzanych przy użyciu programu DEP. Urządzenie jest rejestrowane, gdy użytkownik włącza je po raz pierwszy i uruchamia asystenta ustawień systemu iOS. Ta metoda obsługuje tryb **nadzorcy systemu iOS**, który z kolei umożliwia:
  - Rejestrację zablokowaną
  - Tryb kiosku i inne zaawansowane konfiguracje oraz ograniczenia

Dowiedz się więcej na temat [programu DEP](ios-device-enrollment-program-in-microsoft-intune.md). ([Powrót do tabeli](#overview-of-device-enrollment-methods))

### <a name="usb-sa"></a>USB-SA
Korzystając z programu Apple Configurator za pośrednictwem połączenia USB, administratorzy IT mogą ręcznie przygotować każde urządzenie firmowe do rejestracji przy użyciu Asystenta ustawień. Administrator IT tworzy profil rejestracji i eksportuje go do programu Apple Configurator. Gdy użytkownicy otrzymują swoje urządzenia, są następnie proszeni o uruchomienie Asystenta ustawień w zarejestrowania swojego urządzenia. Ta metoda obsługuje tryb **nadzorcy systemu iOS**, który z kolei umożliwia:
  - Rejestrację zablokowaną
  - Tryb kiosku i inne zaawansowane konfiguracje oraz ograniczenia

Dowiedz się więcej o [rejestracji za pomocą asystenta ustawień przy użyciu programu Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md). ([Powrót do tabeli](#overview-of-device-enrollment-methods))

### <a name="usb-direct"></a>USB-Direct
W celu przeprowadzenia rejestracji bezpośredniej administrator musi ręcznie zarejestrować każde urządzenie, tworząc zasady rejestracji i eksportując je do programu Apple Configurator. Urządzenia USB należące do firmy są rejestrowane bezpośrednio, bez konieczności resetowania do ustawień fabrycznych. Urządzenia są zarządzane jako urządzenia bez użytkowników. Nie są zablokowane ani nadzorowane i nie obsługują dostępu warunkowego, wykrywania zdjęcia zabezpieczeń systemu ani zarządzania aplikacjami mobilnymi.  Dowiedz się więcej o [rejestracji bezpośredniej przy użyciu programu Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md). ([Powrót do tabeli](#overview-of-device-enrollment-methods))

## <a name="mobile-device-management-with-exchange-activesync-and-intune"></a>Zarządzanie urządzeniami przenośnymi za pomocą programu Exchange ActiveSync i usługi Intune
Urządzeniami przenośnymi, które nie są zarejestrowane, ale są połączone z programem Exchange ActiveSync (EAS), można zarządzać za pomocą usługi Intune, korzystając z zasad EAS MDM. Usługa Intune używa łącznika Exchange Connector do komunikowania się z programem EAS (lokalnym lub hostowanym w chmurze). Aby uzyskać więcej informacji, zobacz [Zarządzanie urządzeniami przenośnymi za pomocą programu Exchange ActiveSync i usługi Intune](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md).


## <a name="windows-pc-management-with-intune"></a>Zarządzanie komputerami z systemem Windows przy użyciu usługi Intune  
Usługa Microsoft Intune umożliwia również zarządzanie komputerami z systemem Windows za pomocą oprogramowania klienckiego usługi Intune. Komputery z systemem Windows zarządzane za pomocą klienta usługi Intune mogą:

 - Zgłaszać spisy sprzętu i oprogramowania.
 - Instalować aplikacje komputerowe (np. pliki .exe i .msi).
 - Zarządzaj ustawienia zapory

Komputery zarządzane przy użyciu oprogramowania klienckiego usługi Intune nie mogą zostać w pełni wyczyszczone, ale czyszczenie selektywne jest dostępne. Komputery zarządzane przy użyciu oprogramowania klienckiego usługi Intune nie mogą korzystać z wielu funkcji zarządzania w usłudze Intune, takich jak dostęp warunkowy, ustawienia sieci VPN i Wi-Fi, wdrażanie certyfikatów i konfiguracja poczty e-mail. Aby uzyskać więcej informacji, zobacz [Zarządzanie komputerami z systemem Windows przy użyciu usługi Intune](manage-windows-pcs-with-microsoft-intune.md).

## <a name="supported-device-platforms"></a>Obsługiwane platformy urządzeń

Usługa Intune umożliwia zarządzanie następującymi platformami urządzeń:

[!INCLUDE [mdm-supported-devices](../includes/mdm-supported-devices.md)]

## <a name="next-steps"></a>Następne kroki
- [Wymagania wstępne dotyczące rejestracji urządzeń](prerequisites-for-enrollment.md)
- [Zarządzanie urządzeniami należącymi do firmy](manage-corporate-owned-devices.md)
- [Obsługiwane urządzenia przenośne i komputery](/intune/supported-devices-browsers#intune-supported-devices)
