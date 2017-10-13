---
title: "Co to jest rejestrowanie urządzenia w usłudze Microsoft Intune"
titlesuffix: Azure portal
description: "Dowiedz się więcej o rejestrowaniu urządzeń z systemem iOS, Android i Windows."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 10/03/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bef73c81d285a6d320cd92b055ff2b5592a55af4
ms.sourcegitcommit: 001577b700f634da2fec0b44af2a378150d1f7ac
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/04/2017
---
# <a name="what-is-device-enrollment"></a>Co to jest rejestrowanie urządzenia?
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

W tym temacie opisano rejestrację oraz różne sposoby rejestrowania urządzeń przenośnych w celu zarządzania nimi w usłudze Intune.

Zarejestrowanie urządzeń w usłudze Intune umożliwia zarządzanie nimi. W dokumentacji usługi Intune funkcja ta jest określana mianem zarządzania urządzeniami przenośnymi (MDM, mobile device management). Gdy urządzenia są rejestrowane w usłudze Intune, wystawiane są dla nich certyfikaty MDM, używane następnie przez urządzenia do komunikowania się z usługą Intune.

Sposób rejestrowania urządzeń zależy od rodzaju urządzenia, własności i wymaganego poziomu zarządzania. Metoda rejestracji „Przynieś własne urządzenie” (BYOD) umożliwia użytkownikom rejestrowanie swoich osobistych telefonów, tabletów lub komputerów. Rejestracja urządzeń należących do firmy umożliwia korzystanie ze scenariuszy zarządzania, takich jak automatyczne rejestrowanie, urządzenia udostępnione lub wstępnie autoryzowane wymagania dotyczące rejestracji.

Organizacje korzystające z programu Exchange ActiveSync (lokalnie lub w chmurze) mogą używać prostszych metod zarządzania w usłudze Intune, w których nie jest wymagana rejestracja urządzeń (wkrótce zostanie udostępnionych więcej informacji na ten temat). Komputerami z systemem Windows można zarządzać jak urządzeniami przenośnymi. Tę zalecaną metodę opisano poniżej.


## <a name="overview-of-device-enrollment-methods"></a>Przegląd metod rejestracji urządzeń

Tabela zawiera przegląd metod rejestracji w usłudze Intune, a poniżej opisano ich możliwości i wymagania.

**Legenda**

- **Wymagane zresetowanie** — urządzenia są resetowane do ustawień fabrycznych podczas rejestracji.
- **Koligacja użytkownika** — kojarzy urządzenia z użytkownikami. Aby uzyskać więcej informacji, zobacz [Koligacja użytkownika](device-enrollment-program-enroll-ios.md).
- **Zablokowane** — uniemożliwia użytkownikom wyrejestrowanie urządzeń.

**Metody rejestracji urządzeń z systemem iOS**

| **Metoda** |  **Wymagane zresetowanie** |    **Koligacja użytkownika**   |   **Zablokowane** | **Szczegóły** |
|:---:|:---:|:---:|:---:|:---:|
|**[„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)](#byod)** | Nie|    Tak |   Nie | [Więcej informacji](./apple-mdm-push-certificate-get.md)|
|**[Menedżer rejestracji urządzeń](#dem)**|   Nie |Nie |Nie  | [Więcej informacji](./device-enrollment-program-enroll-ios.md)|
|**[Device Enrollment Program](#dep)**|   Tak |   Opcjonalne |  Opcjonalne|[Więcej informacji](./device-enrollment-program-enroll-ios.md)|
|**[USB-SA](#usb-sa)**| Tak |   Opcjonalne |  Nie| [Więcej informacji](./apple-configurator-setup-assistant-enroll-ios.md)|
|**[USB-Direct](#usb-direct)**| Nie |    Nie  | Nie|[Więcej informacji](./apple-configurator-direct-enroll-ios.md)|

**Metody rejestracji urządzeń z systemem Windows**

| **Metoda** |  **Wymagane zresetowanie** |    **Koligacja użytkownika**   |   **Zablokowane** | **Szczegóły**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)](#byod)** | Nie |   Tak |   Nie | [Więcej informacji](windows-enroll.md)|
|**[Menedżer rejestracji urządzeń](#dem)**|   Nie |Nie |Nie  |[Więcej informacji](device-enrollment-manager-enroll.md)|
|**Automatyczne rejestrowanie** | Nie |Tak |Nie | [Więcej informacji](./windows-enroll.md#enable-windows-10-automatic-enrollment)|
|**Rejestrowanie zbiorcze** |Nie |Nie |Nie | [Więcej informacji](./windows-bulk-enroll.md) |

**Metody rejestracji urządzeń z systemem Android**

| **Metoda** |  **Wymagane zresetowanie** |    **Koligacja użytkownika**   |   **Zablokowane** | **Szczegóły**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)](#byod)** | Nie|    Tak |   Nie | [Więcej informacji](./android-enroll.md)|
|**[Menedżer rejestracji urządzeń](#dem)**|   Nie |Nie |Nie  |[Więcej informacji](./device-enrollment-program-enroll-ios.md)|
|**Android for Work**| Nie | Tak | Nie| [Więcej informacji](./android-enroll.md#enable-enrollment-of-android-for-work-devices) |


## <a name="byod"></a>„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)
Użytkownicy korzystający z metody „Przynieś własne urządzenie” w celu zarejestrowania swoich urządzeń instalują i uruchamiają aplikację Portal firmy. Ten program umożliwia użytkownikom dostęp do zasobów firmowych, takich jak wiadomości e-mail.

## <a name="corporate-owned-devices"></a>Urządzenia należące do firmy
Poniżej przedstawiono scenariusze rejestracji urządzeń należących do firmy (COD, Corporate-Owned Device). Urządzenia z systemem iOS można zarejestrować bezpośrednio za pomocą narzędzi dostarczonych przez firmę Apple. Wszystkie typy urządzeń mogą być rejestrowane przez administratora lub menedżera za pomocą menedżera rejestracji urządzeń. Urządzenia z numerem IMEI można również zidentyfikować i oznaczyć jako należące do firmy, umożliwiając korzystanie ze scenariuszy COD.

### <a name="dem"></a>Menedżer rejestracji urządzeń
Menedżer rejestracji urządzeń (DEM) to specjalne konto użytkownika używane do rejestrowania wielu urządzeń należących do firmy i zarządzania nimi. Menedżerowie mogą zainstalować Portal firmy i zarejestrować wiele urządzeń bez użytkowników. Dowiedz się więcej na temat [menedżera rejestracji urządzeń](./device-enrollment-manager-enroll.md).

### <a name="dep"></a>Program Device Enrollment Program
Zarządzanie w programie Device Enrollment Program (DEP) firmy Apple pozwala na tworzenie i bezprzewodowe wdrażanie zasad na urządzeniach z systemem iOS kupionych i zarządzanych przy użyciu programu DEP. Urządzenie jest rejestrowane, gdy użytkownik włącza je po raz pierwszy i uruchamia asystenta ustawień systemu iOS. Ta metoda obsługuje tryb nadzorowany systemu iOS, który umożliwia skonfigurowanie urządzenia z następującą funkcjonalnością:

- Blokada aplikacji (tryb jednej aplikacji) 
- Globalny serwer proxy HTTP 
- Obejście blokady aktywacji 
- Autonomiczny tryb jednej aplikacji 
- Filtr zawartości internetowej 
- Ustawianie tła i ekranu blokady 
- Dyskretne wypychanie aplikacji 
- Zawsze włączona sieć VPN 
- Zezwalanie wyłącznie na instalację zarządzanych aplikacji 
- iBookstore 
- iMessages 
- Centrum gier 
- AirDrop 
- AirPlay 
- Parowanie hostów 
- Synchronizacja z chmurą 
- Wyszukiwanie Spotlight 
- Handoff 
- Wymazywanie urządzenia 
- Interfejs użytkownika ograniczeń 
- Instalacja profilów konfiguracji przez interfejs użytkownika 
- News 
- Skróty klawiaturowe 
- Modyfikacje kodu dostępu 
- Zmiany nazwy urządzenia 
- Zmiany tapety 
- Automatyczne pobieranie aplikacji 
- Zmiany zaufania aplikacji przedsiębiorstwa 
- Apple Music 
- Mail Drop 
- Parowanie z zegarkiem Apple Watch 

> [!NOTE]
> Firma Apple potwierdza, że w 2018 r. niektóre ustawienia będą dostępne wyłącznie w trybie nadzorowanym. Zalecamy wzięcie tego pod uwagę podczas używania tych ustawień zamiast czekania, aż firma Apple przeprowadzi ich migrację do trybu nadzorowanego:
> - Instalacja aplikacji
> - Usuwanie aplikacji
> - FaceTime
> - Safari
> - iTunes
> - Zawartość dla dorosłych
> - Dokumenty i dane iCloud
> - Gry dla wielu graczy
> - Dodaj przyjaciół centrum gier

Więcej informacji o rejestracji DEP urządzeń z systemem iOS:

- [Wybieranie sposobu rejestrowania urządzeń z systemem iOS](ios-enroll.md)
- [Rejestrowanie urządzeń z systemem iOS przy użyciu programu Device Enrollment Program](device-enrollment-program-enroll-ios.md)

### <a name="usb-sa"></a>USB-SA
Korzystając z programu Apple Configurator za pośrednictwem połączenia USB, administratorzy IT mogą ręcznie przygotować każde urządzenie firmowe do rejestracji przy użyciu Asystenta ustawień. Administrator IT tworzy profil rejestracji i eksportuje go do programu Apple Configurator. Gdy użytkownicy otrzymują swoje urządzenia, są następnie proszeni o uruchomienie Asystenta ustawień w zarejestrowania swojego urządzenia. Ta metoda obsługuje tryb **nadzorowany systemu iOS**, który z kolei udostępnia następujące funkcje:
  - Rejestrację zablokowaną
  - Tryb kiosku i inne zaawansowane konfiguracje oraz ograniczenia

Więcej informacji o rejestracji urządzeń z systemem iOS przy użyciu programu Configurator firmy Apple oraz Asystenta ustawień:

- [Wybieranie sposobu rejestrowania urządzeń z systemem iOS](enrollment-method-choose-ios.md)
- [Rejestrowanie urządzeń z systemem iOS przy użyciu programu Configurator i Asystenta ustawień](apple-configurator-setup-assistant-enroll-ios.md)

### <a name="usb-direct"></a>USB-Direct
W celu przeprowadzenia rejestracji bezpośredniej administrator musi ręcznie zarejestrować każde urządzenie, tworząc zasady rejestracji i eksportując je do programu Apple Configurator. Urządzenia USB należące do firmy są rejestrowane bezpośrednio, bez konieczności resetowania do ustawień fabrycznych. Urządzenia są zarządzane jako urządzenia bez użytkowników. Nie są zablokowane ani nadzorowane i nie obsługują dostępu warunkowego, wykrywania zdjęcia zabezpieczeń systemu ani zarządzania aplikacjami mobilnymi.

Aby dowiedzieć się więcej o rejestracji urządzeń z systemem iOS, zobacz:

- [Wybieranie sposobu rejestrowania urządzeń z systemem iOS](enrollment-method-choose-ios.md)
- [Rejestracja urządzeń z systemem iOS przy użyciu narzędzia Configurator i rejestracji bezpośredniej](apple-configurator-direct-enroll-ios.md)

## <a name="mobile-device-management-with-exchange-activesync-and-intune"></a>Zarządzanie urządzeniami przenośnymi za pomocą programu Exchange ActiveSync i usługi Intune
Urządzeniami mobilnymi, które nie są zarejestrowane, ale są połączone z programem Exchange ActiveSync (EAS), można zarządzać za pomocą usługi Intune, korzystając z zasad MDM programu EAS. Usługa Intune używa łącznika Exchange Connector do komunikowania się z programem EAS (lokalnym lub hostowanym w chmurze). Wkrótce zostanie udostępnionych więcej informacji na ten temat.

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Czyszczenie urządzenia przenośnego po wygaśnięciu certyfikatu MDM

Certyfikat MDM jest odnawiany automatycznie, gdy urządzenia przenośne komunikują się z usługą Intune. W przypadku wyczyszczenia urządzeń przenośnych lub jeśli przez pewien czas nie komunikują się one z usługą Intune, certyfikat MDM nie zostanie odnowiony. Urządzenie zostanie usunięte z portalu Azure 180 dni po wygaśnięciu certyfikatu MDM.
