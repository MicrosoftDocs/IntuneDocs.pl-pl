---
title: Co to jest rejestrowanie urządzenia w usłudze Microsoft Intune
titleSuffix: Microsoft Intune
description: Dowiedz się więcej o rejestrowaniu urządzeń z systemem iOS, Android i Windows.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 4/24/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 304e869460a5396a486b6de0cd5c2f549c192b70
ms.sourcegitcommit: 60ed93682a21860e9d99ba1592ede120477f2b4d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72379863"
---
# <a name="what-is-device-enrollment"></a>Co to jest rejestrowanie urządzenia?
[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Usługa Intune umożliwia zarządzanie urządzeniami i aplikacjami pracowników oraz sposobem uzyskiwania przez nich dostępu do danych firmy. Aby można było użyć tego rozwiązania do zarządzania urządzeniami przenośnymi (MDM, mobile device management), urządzenia muszą być zarejestrowane w usłudze Intune. Dla zarejestrowanego urządzenia jest wystawiany certyfikat MDM. Ten certyfikat jest używany do komunikacji z usługą Intune.

Jak pokazano w poniższych tabelach, istnieje kilka metod rejestracji urządzeń pracowników. Każda metoda zależy od własności urządzenia (osobiste lub firmowe), typu urządzenia (system iOS, Windows lub Android) i wymagań dotyczących zarządzania (resetowanie, koligacja i blokowanie).

Domyślnie w usłudze Intune mogą być rejestrowane urządzenia dla dowolnej platformy. Można jednak [ograniczyć urządzenia według platformy](enrollment-restrictions-set.md#create-a-device-type-restriction).

## <a name="ios-enrollment-methods"></a>Metody rejestracji urządzeń z systemem iOS

| **Metoda** | **Wymagane zresetowanie** | [**Koligacja użytkownika**](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile) | **Zablokowane** | **Szczegóły** |
|:---:|:---:|:---:|:---:|:---:|
| | Podczas rejestracji urządzenia są czyszczone. | Kojarzy każde urządzenie z użytkownikiem.| Jeśli tak jest, użytkownicy nie mogą wyrejestrowywać urządzeń. | |
|**[„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)](#bring-your-own-device)** | Nie| Tak | Nie | [Więcej informacji](apple-mdm-push-certificate-get.md)|
|**[Menedżer rejestracji urządzeń](#device-enrollment-manager)**| Nie |Nie |Nie | [Więcej informacji](device-enrollment-program-enroll-ios.md)|
|**[Device Enrollment Program](#apple-device-enrollment-program)**| Tak | Opcjonalne | Opcjonalne|[Więcej informacji](device-enrollment-program-enroll-ios.md)|
|**[USB-SA](#usb-sa)**| Tak | Opcjonalne | Nie| [Więcej informacji](apple-configurator-enroll-ios.md)|
|**[USB-Direct](#usb-direct)**| Nie | Nie | Nie|[Więcej informacji](apple-configurator-enroll-ios.md)|

## <a name="macos-enrollment-methods"></a>Metody rejestracji urządzeń z systemem macOS
| **Metoda** |  **Wymagane zresetowanie** |  **Koligacja użytkownika** | **Zablokowane** | **Szczegóły**|
|:---:|:---:|:---:|:---:|:---:|
|**[„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)](#bring-your-own-device)** | Nie| Tak | Nie | [Więcej informacji](macos-enroll.md)|
|**[Menedżer rejestracji urządzeń](#device-enrollment-manager)**| Nie |Nie |Nie  | [Więcej informacji](device-enrollment-manager-enroll.md)|
|**[Device Enrollment Program](#apple-device-enrollment-program)**| Tak | Opcjonalne | Opcjonalne|[Więcej informacji](device-enrollment-program-enroll-macos.md)|

## <a name="windows-enrollment-methods"></a>Metody rejestracji systemu Windows

| **Metoda** | **Wymagane zresetowanie** | **Koligacja użytkownika** | **Zablokowane** | **Szczegóły**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)](#bring-your-own-device)** | Nie | Tak | Nie | [Więcej informacji](windows-enroll.md)|
|**[Menedżer rejestracji urządzeń](#device-enrollment-manager)**| Nie |Nie |Nie |[Więcej informacji](device-enrollment-manager-enroll.md)|
|**Automatyczne rejestrowanie** | Nie |Tak |Nie | [Więcej informacji](windows-enroll.md#enable-windows-10-automatic-enrollment)|
|**Rozwiązanie Autopilot** |Tak |Tak |Nie | [Więcej informacji](enrollment-autopilot.md)
|**Rejestrowanie zbiorcze** |Nie |Nie |Nie | [Więcej informacji](windows-bulk-enroll.md) |
|**Współzarządzanie** |Nie |Tak |Nie | [Więcej informacji](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview)
|**Obiekt zasad grupy** |Nie |Tak |Nie | [Więcej informacji](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)

## <a name="android-enrollment-methods"></a>Metody rejestracji systemu Android

| **Osobiste** | **Metody rejestracji** | **Wymagane zresetowanie** | **Koligacja użytkownika** | **Zablokowane** | **Szczegóły**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**Administrator urządzenia z systemem Android**|**Inicjowane przez użytkownika za pośrednictwem Portalu firmy** | Nie | Tak | Nie | [Więcej informacji](https://docs.microsoft.com/intune-user-help/enroll-device-android-company-portal)|
|**Android Enterprise — profil służbowy**|**Inicjowane przez użytkownika za pośrednictwem Portalu firmy**| Nie | Tak | Nie | [Więcej informacji](android-work-profile-enroll.md)|


| **Firmowe** | **Metody rejestracji** | **Wymagane zresetowanie** | **Koligacja użytkownika** | **Zablokowane** | **Szczegóły**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**Administrator urządzenia z systemem Android**|**Inicjowane przez [menedżera rejestracji urządzeń](#device-enrollment-manager) za pośrednictwem Portalu firmy**| Nie | Nie | Nie |[Więcej informacji](device-enrollment-manager-enroll.md)|
|**Administrator urządzenia z systemem Android**|**(Zadeklarowany wstępnie numer IMEI lub SN) Inicjowane przez użytkownika za pośrednictwem Portalu firmy**| Nie | Tak | Nie | [Więcej informacji](./../corporate-identifiers-add.md)|
|**Administrator urządzenia z systemem Android przy użyciu rozszerzeń mobilności Zebra**|**Inicjowane przez użytkownika lub [menedżera rejestracji urządzeń](#device-enrollment-manager) za pośrednictwem Portalu firmy**| Nie | Tak, jeśli inicjowana przez użytkownika, nie, jeśli inicjowana przez [menedżera rejestracji urządzeń](#device-enrollment-manager) | Nie | [Więcej informacji](../configuration/android-zebra-mx-overview.md)|
|**Android Enterprise (dedykowane)**|**NFC, token, kod QR, Zero Touch**| Tak | Nie | Można konfigurować za pomocą zasad | [Więcej informacji](android-kiosk-enroll.md)|
|**W pełni zarządzane urządzenia z rozwiązaniem Android Enterprise**|**NFC, token, kod QR, Zero Touch**| Tak | Tak | Można konfigurować za pomocą zasad | [Więcej informacji](android-dedicated-devices-fully-managed-enroll.md)|


## <a name="bring-your-own-device"></a>Korzystanie z własnych urządzeń
Model „Przynieś własne urządzenie” (BYOD) obejmuje telefony, tablety i komputery stanowiące własność użytkownika. W celu zarejestrowania urządzeń BYOD użytkownicy instalują i uruchamiają aplikację Portal firmy. Ten program umożliwia użytkownikom dostęp do zasobów firmowych, takich jak wiadomości e-mail.

## <a name="corporate-owned-device"></a>Urządzenie należące do firmy
[Urządzenia należące do firmy (COD)](corporate-identifiers-add.md) obejmują telefony, tablety oraz komputery należące do organizacji i dostarczane pracownikom. Rejestracja urządzeń COD obsługuje takie scenariusze jak automatyczne rejestrowanie, urządzenia udostępnione lub wstępnie autoryzowane wymagania dotyczące rejestracji. Często stosowaną metodą rejestracji urządzeń COD jest użycie menedżera rejestracji urządzeń (DEM) przez administratora lub kierownika. Urządzenia z systemem iOS można zarejestrować bezpośrednio za pomocą narzędzi programu Device Enrollment Program (DEP) dostarczonych przez firmę Apple. Urządzenia z numerem IMEI można również zidentyfikować i oznaczyć jako należące do firmy.

### <a name="device-enrollment-manager"></a>Menedżer rejestracji urządzeń
Menedżer rejestracji urządzeń (DEM) to specjalne konto użytkownika używane do rejestrowania wielu urządzeń należących do firmy i zarządzania nimi. Menedżerowie mogą zainstalować Portal firmy i zarejestrować wiele urządzeń bez użytkowników. Tego rodzaju urządzenia nadają się do wykorzystania w punktach sprzedaży lub na potrzeby użycia aplikacji narzędziowych, ale są złym rozwiązaniem dla użytkowników, którzy potrzebują dostępu do poczty e-mail lub zasobów firmowych. Dowiedz się więcej na temat [menedżera rejestracji urządzeń](device-enrollment-manager-enroll.md).

### <a name="apple-device-enrollment-program"></a>Program Device Enrollment Program firmy Apple
Zarządzanie w programie Device Enrollment Program (DEP) firmy Apple pozwala na tworzenie i bezprzewodowe wdrażanie zasad na urządzeniach z systemem iOS oraz macOS kupionych i zarządzanych przy użyciu programu DEP. Urządzenie jest rejestrowane, gdy użytkownik włącza je po raz pierwszy i uruchamia asystenta ustawień. Ta metoda obsługuje tryb nadzorowany systemu iOS, który umożliwia skonfigurowanie określonej funkcji na urządzeniu.

Więcej informacji o rejestracji DEP urządzeń z systemem iOS:

- [Wybieranie sposobu rejestrowania urządzeń z systemem iOS](ios-enroll.md)
- [Rejestrowanie urządzeń z systemem iOS przy użyciu programu Device Enrollment Program](device-enrollment-program-enroll-ios.md)

### <a name="usb-sa"></a>USB-SA
Korzystając z programu Apple Configurator za pośrednictwem połączenia USB, administratorzy IT mogą ręcznie przygotować każde urządzenie firmowe do rejestracji przy użyciu Asystenta ustawień. Administrator IT tworzy profil rejestracji i eksportuje go do programu Apple Configurator. Gdy użytkownicy otrzymują swoje urządzenia, są następnie proszeni o uruchomienie Asystenta ustawień w celu zarejestrowania swojego urządzenia. Ta metoda obsługuje tryb **nadzorowany systemu iOS**, który z kolei udostępnia następujące funkcje:
- Rejestrację zablokowaną
- Tryb kiosku i inne zaawansowane konfiguracje oraz ograniczenia

Więcej informacji o rejestracji urządzeń z systemem iOS przy użyciu programu Configurator firmy Apple oraz Asystenta ustawień:

- [Wybieranie sposobu rejestrowania urządzeń z systemem iOS](ios-enroll.md)
- [Rejestrowanie urządzeń z systemem iOS przy użyciu programu Configurator i Asystenta ustawień](apple-configurator-enroll-ios.md)

### <a name="usb-direct"></a>USB-Direct
W celu przeprowadzenia rejestracji bezpośredniej administrator musi ręcznie zarejestrować każde urządzenie, tworząc zasady rejestracji i eksportując je do programu Apple Configurator. Urządzenia USB należące do firmy są rejestrowane bezpośrednio, bez konieczności czyszczenia urządzenia. Urządzenia są zarządzane jako urządzenia bez użytkowników. Nie są zablokowane ani nadzorowane i nie obsługują dostępu warunkowego, wykrywania zdjęcia zabezpieczeń systemu ani zarządzania aplikacjami mobilnymi.

Aby dowiedzieć się więcej o rejestracji urządzeń z systemem iOS, zobacz:

- [Wybieranie sposobu rejestrowania urządzeń z systemem iOS](ios-enroll.md)
- [Rejestracja urządzeń z systemem iOS przy użyciu narzędzia Configurator i rejestracji bezpośredniej](apple-configurator-enroll-ios.md)

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Czyszczenie urządzenia przenośnego po wygaśnięciu certyfikatu MDM

Certyfikat MDM jest odnawiany automatycznie, gdy urządzenia przenośne komunikują się z usługą Intune. W przypadku wyczyszczenia urządzeń przenośnych lub jeśli przez pewien czas nie komunikują się one z usługą Intune, certyfikat MDM nie zostanie odnowiony. Urządzenie zostanie usunięte z portalu Azure 180 dni po wygaśnięciu certyfikatu MDM.
