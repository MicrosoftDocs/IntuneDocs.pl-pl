---
title: "Co to jest rejestrowanie urządzenia w usłudze Microsoft Intune"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: dowiedz się więcej o rejestrowaniu urządzeń z systemem iOS, Android i Windows."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 57bad4be991b61fe5212d340ab8d89cb6af3b0f7
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---

# <a name="what-is-device-enrollment"></a>Co to jest rejestrowanie urządzenia?
[!INCLUDE[azure_preview](./includes/azure_preview.md)]

W tym temacie opisano rejestrację oraz różne sposoby rejestrowania urządzeń przenośnych w celu zarządzania nimi w usłudze Intune.

Zarejestrowanie urządzeń w usłudze Intune umożliwia zarządzanie nimi. W dokumentacji usługi Intune funkcja ta jest określana mianem zarządzania urządzeniami przenośnymi (MDM, mobile device management). Gdy urządzenia są rejestrowane w usłudze Intune, wystawiane są dla nich certyfikaty MDM, używane następnie przez urządzenia do komunikowania się z usługą Intune.

Sposób rejestrowania urządzeń zależy od rodzaju urządzenia, własności i wymaganego poziomu zarządzania. Metoda rejestracji „Przynieś własne urządzenie” (BYOD) umożliwia użytkownikom rejestrowanie swoich osobistych telefonów, tabletów lub komputerów. Rejestracja urządzeń należących do firmy umożliwia korzystanie ze scenariuszy zarządzania, takich jak automatyczne rejestrowanie, urządzenia udostępnione lub wstępnie autoryzowane wymagania dotyczące rejestracji.

Organizacje korzystające z programu Exchange ActiveSync (lokalnie lub w chmurze) mogą używać prostszych metod zarządzania w usłudze Intune, w których nie jest wymagana rejestracja urządzeń (wkrótce zostanie udostępnionych więcej informacji na ten temat). Komputerami z systemem Windows można zarządzać jak urządzeniami przenośnymi. Tę zalecaną metodę opisano poniżej.


## <a name="overview-of-device-enrollment-methods"></a>Przegląd metod rejestracji urządzeń

W poniższej tabeli przedstawiono metody rejestracji usługi Intune oraz wymagania i obsługiwane możliwości każdej metody. Te wymagania i możliwości zostały opisane poniżej. W tabeli używane są następujące terminy:

- **Czyszczenie** — określa, czy urządzenie musi zostać wyczyszczone, zanim użytkownicy będą mogli je zarejestrować. Termin „czyszczenie” oznacza zresetowanie urządzenia do ustawień fabrycznych, co powoduje usunięcie wszystkich danych. Aby uzyskać więcej informacji, zobacz artykuł [Use full or selective wipe on devices](devices-wipe.md) (Użycie pełnego lub selektywnego czyszczenia danych na urządzeniach).
- **Koligacja** — kojarzy urządzenia z użytkownikami. Wymagane w celu zarządzania aplikacjami mobilnymi (MAM) i uzyskiwania warunkowego dostępu do danych firmowych. Aby uzyskać więcej informacji, zobacz [Koligacja użytkownika](device-enrollment-program-enroll-ios.md).
- **Blokada** — wskazuje, czy użytkownicy mają zablokowaną możliwość wyrejestrowywania swoich urządzeń z zarządzania. Użytkownicy mogą wyrejestrowywać swoje urządzenia na wszystkich platformach przy użyciu aplikacji Portal firmy. Do wyrejestrowania nie można używać natywnych menu systemu operacyjnego.


**Metody rejestracji urządzeń z systemem iOS**

| **Metoda** |    **Wymagane wyczyszczenie?** |    **Koligacja**    |    **Blokada** | **Szczegóły** |
|:---:|:---:|:---:|:---:|:---:|
|**[„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)](#byod)** | Nie|    Tak |    Nie | Wkrótce zostanie udostępnionych więcej informacji na ten temat|
|**[Menedżer rejestracji urządzeń](#dem)**|    Nie |Nie |Nie    | [Więcej informacji](device-enrollment-program-enroll-ios.md)|
|**[Device Enrollment Program](#dep)**|    Tak |    Opcjonalne |    Opcjonalne|[Więcej informacji](device-enrollment-program-enroll-ios.md)|
|**[USB-SA](#usb-sa)**|    Tak |    Opcjonalne |    Nie| [Więcej informacji](apple-configurator-setup-assistant-enroll-ios.md)|
|**[USB-Direct](#usb-direct)**|    Nie |    Nie    | Nie|[Więcej informacji](apple-configurator-direct-enroll-ios.md)|

**Metody rejestracji urządzeń z systemem Windows**

| **Metoda** |    **Wymagane wyczyszczenie?** |    **Koligacja**    |    **Blokada** | **Szczegóły**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)](#byod)** | Nie |    Tak |    Nie | [Więcej informacji](windows-enroll.md)|
|**[Menedżer rejestracji urządzeń](#dem)**|    Nie |Nie |Nie    |[Więcej informacji](device-enrollment-manager-enroll.md)|

**Metody rejestracji urządzeń z systemem Android**

| **Metoda** |    **Wymagane wyczyszczenie?** |    **Koligacja**    |    **Blokada** | **Szczegóły**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)](#byod)** | Nie|    Tak |    Nie | [Więcej informacji](android-enroll.md)|
|**[Menedżer rejestracji urządzeń](#dem)**|    Nie |Nie |Nie    |[Więcej informacji](device-enrollment-program-enroll-ios.md)|
|**Android for Work**| Nie | Tak | Nie| [Więcej informacji](android-enroll.md) |


## <a name="byod"></a>„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)
Użytkownicy korzystający z metody „Przynieś własne urządzenie” instalują aplikację Portal firmy i rejestrują swoje urządzenie. Umożliwia to użytkownikom nawiązanie połączenia z siecią firmową i dołączenie do domeny lub usługi Azure Active Directory. W przypadku większości platform należy włączyć rejestrowanie w trybie „Przynieś własne urządzenie” (BYOD, bring your own device) w wielu scenariuszach dotyczących urządzeń należących do firmy (COD, company-owned device). Możesz zablokować możliwość rejestrowania urządzeń z systemem iOS i Android będących własnością użytkowników. Instrukcje zawiera temat [Ustawianie ograniczeń typu urządzeń](enrollment-restrictions-set.md#set-device-type-restrictions).

## <a name="corporate-owned-devices"></a>Urządzenia należące do firmy
Urządzeniami należącymi do firmy można zarządzać za pomocą portalu Azure. Urządzenia z systemem iOS można zarejestrować bezpośrednio za pomocą narzędzi dostarczonych przez firmę Apple. Wszystkie typy urządzeń mogą być rejestrowane przez administratora lub menedżera za pomocą menedżera rejestracji urządzeń. Urządzenia z numerem IMEI można również zidentyfikować i oznaczyć jako należące do firmy, umożliwiając korzystanie ze scenariuszy COD.

### <a name="dem"></a>Menedżer rejestracji urządzeń
Menedżer rejestracji urządzeń (DEM) to specjalne konto użytkownika używane do rejestrowania wielu urządzeń należących do firmy i zarządzania nimi. Menedżerowie mogą zainstalować Portal firmy i zarejestrować wiele urządzeń bez użytkowników. Dowiedz się więcej na temat [menedżera rejestracji urządzeń](device-enrollment-manager-enroll.md). ([Powrót do tabeli](#overview-of-device-enrollment-methods))

### <a name="dep"></a>Program Device Enrollment Program
Zarządzanie w programie Device Enrollment Program (DEP) firmy Apple pozwala na tworzenie i bezprzewodowe wdrażanie zasad na urządzeniach z systemem iOS kupionych i zarządzanych przy użyciu programu DEP. Urządzenie jest rejestrowane, gdy użytkownik włącza je po raz pierwszy i uruchamia asystenta ustawień systemu iOS. Ta metoda obsługuje tryb **nadzorcy systemu iOS**, który z kolei umożliwia:

  -    Rejestrację zablokowaną
  -    Tryb kiosku i inne zaawansowane konfiguracje oraz ograniczenia

Aby dowiedzieć się więcej o rejestracji urządzeń z systemem iOS, zobacz:

- [Wybieranie sposobu rejestrowania urządzeń z systemem iOS](enrollment-method-choose-ios.md)
- [Rejestrowanie urządzeń z systemem iOS przy użyciu programu Device Enrollment Program](device-enrollment-program-enroll-ios.md)
- [Powrót do tabeli powyżej](#overview-of-device-enrollment-methods)

### <a name="usb-sa"></a>USB-SA
Korzystając z programu Apple Configurator za pośrednictwem połączenia USB, administratorzy IT mogą ręcznie przygotować każde urządzenie firmowe do rejestracji przy użyciu Asystenta ustawień. Administrator IT tworzy profil rejestracji i eksportuje go do programu Apple Configurator. Gdy użytkownicy otrzymują swoje urządzenia, są następnie proszeni o uruchomienie Asystenta ustawień w zarejestrowania swojego urządzenia. Ta metoda obsługuje tryb **nadzorcy systemu iOS**, który z kolei umożliwia:
  -    Rejestrację zablokowaną
  -    Tryb kiosku i inne zaawansowane konfiguracje oraz ograniczenia

Aby dowiedzieć się więcej o rejestracji urządzeń z systemem iOS, zobacz:

- [Wybieranie sposobu rejestrowania urządzeń z systemem iOS](enrollment-method-choose-ios.md)
- [Rejestrowanie urządzeń z systemem iOS przy użyciu programu Configurator i Asystenta ustawień](apple-configurator-setup-assistant-enroll-ios.md)

### <a name="usb-direct"></a>USB-Direct
W celu przeprowadzenia rejestracji bezpośredniej administrator musi ręcznie zarejestrować każde urządzenie, tworząc zasady rejestracji i eksportując je do programu Apple Configurator. Urządzenia USB należące do firmy są rejestrowane bezpośrednio, bez konieczności resetowania do ustawień fabrycznych. Urządzenia są zarządzane jako urządzenia bez użytkowników. Nie są zablokowane ani nadzorowane i nie obsługują dostępu warunkowego, wykrywania zdjęcia zabezpieczeń systemu ani zarządzania aplikacjami mobilnymi.

Aby dowiedzieć się więcej o rejestracji urządzeń z systemem iOS, zobacz:

- [Wybieranie sposobu rejestrowania urządzeń z systemem iOS](enrollment-method-choose-ios.md)
- [Rejestracja urządzeń z systemem iOS przy użyciu narzędzia Configurator i rejestracji bezpośredniej](apple-configurator-direct-enroll-ios.md)

## <a name="mobile-device-management-with-exchange-activesync-and-intune"></a>Zarządzanie urządzeniami przenośnymi za pomocą programu Exchange ActiveSync i usługi Intune
Urządzeniami przenośnymi, które nie są zarejestrowane, ale są połączone z programem Exchange ActiveSync (EAS), można zarządzać za pomocą usługi Intune, korzystając z zasad EAS MDM. Usługa Intune używa łącznika Exchange Connector do komunikowania się z programem EAS (lokalnym lub hostowanym w chmurze). Wkrótce zostanie udostępnionych więcej informacji na ten temat.

## <a name="supported-device-platforms-and-browsers"></a>Obsługiwane platformy urządzeń i przeglądarki

Zobacz artykuł [Supported devices and browsers for Intune](https://docs.microsoft.com/intune-classic/get-started/supported-mobile-devices-and-computers) (Obsługiwane urządzenia i przeglądarki dla usługi Intune)

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Czyszczenie urządzenia przenośnego po wygaśnięciu certyfikatu MDM

Certyfikat MDM jest odnawiany automatycznie, gdy urządzenia przenośne komunikują się z usługą Intune. W przypadku wyczyszczenia urządzeń przenośnych lub jeśli przez pewien czas nie komunikują się one z usługą Intune, certyfikat MDM nie zostanie odnowiony. Urządzenie zostanie usunięte z portalu Azure 180 dni po wygaśnięciu certyfikatu MDM.

