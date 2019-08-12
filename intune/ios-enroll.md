---
title: Rejestrowanie urządzeń z systemem iOS w usłudze Intune
titleSuffix: Microsoft Intune
description: Konfigurowanie rejestrowania urządzeń z systemem iOS w usłudze Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 439c33a6-e80c-4da9-ba09-a51fc36f62ad
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2254c1e83764e9b29ab6fb99c016edef75aad43e
ms.sourcegitcommit: bc3450fc7f19006b500edf5b395c01559b483ea4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/02/2019
ms.locfileid: "68738280"
---
# <a name="enroll-ios-devices-in-intune"></a>Rejestrowanie urządzeń z systemem iOS w usłudze Intune

Usługa Intune umożliwia zarządzanie urządzeniami przenośnymi typu iPad i iPhone, a także zapewnia użytkownikom dostęp do poczty e-mail oraz aplikacji firmy.

Jako administrator usługi Intune możesz włączyć rejestrowanie dla urządzeń z systemem iOS. Użytkownikom można zezwolić na rejestrację prywatnych urządzeń nazywaną rejestracją typu „Przynieś własne urządzenie” (BYOD, bring your own device). Można również włączyć rejestrację urządzeń należących do firmy.

## <a name="prerequisites-for-ios-enrollment"></a>Wymagania wstępne dotyczące rejestracji urządzeń z systemem iOS
Aby możliwa była rejestracja urządzeń z systemem iOS, wykonaj następujące czynności:
- [Upewnij się, że urządzenie kwalifikuje się programu Device Enrollment Program firmy Apple](https://support.apple.com/en-us/HT204142#eligibility).
- [Skonfiguruj usługę Intune](setup-steps.md) — te kroki umożliwiają skonfigurowanie infrastruktury usługi Intune. W szczególności rejestracja urządzeń wymaga [ustawienia urzędu zarządzania urządzeniami przenośnymi](mdm-authority-set.md).
- [Uzyskiwanie certyfikatu wypychania MDM firmy Apple](apple-mdm-push-certificate-get.md) — firma Apple wymaga certyfikatu, aby możliwe było zarządzania urządzeniami z systemami iOS i macOS.


## <a name="user-owned-ios-devices-byod"></a>Urządzenia z systemem iOS należące do użytkownika (BYOD)

Możesz umożliwić użytkownikom rejestrowanie swoich urządzeń osobistych na potrzeby zarządzania w usłudze Intune — rozwiązanie to nazywa się „bring your own device”, czyli BYOD. Gdy ukończysz wymagania wstępne i przypiszesz użytkownikom licencje, użytkownicy muszą pobrać aplikację Intune — Portal firmy ze sklepu App Store i postępować zgodnie z instrukcjami w aplikacji dotyczącymi rejestrowania.

## <a name="company-owned-ios-devices"></a>Urządzenia z systemem iOS należące do firmy
W przypadku organizacji, które kupują urządzenia dla swoich użytkowników, usługa Intune obsługuje następujące metody rejestracji urządzeń z systemem iOS należących do firmy:

- Program Device Enrollment Program (DEP) firmy Apple
- Apple School Manager
- Rejestracja za pośrednictwem asystenta ustawień programu Apple Configurator
- Rejestracja bezpośrednia w narzędziu Apple Configurator

Urządzenia z systemem iOS należące do firmy możesz także zarejestrować przy użyciu konta [menedżera rejestracji urządzeń](device-enrollment-manager-enroll.md).

## <a name="device-enrollment-program"></a>Program Device Enrollment Program
Organizacje mogą zakupić urządzenia z systemem iOS za pośrednictwem programu Device Enrollment Program firmy Apple. Program Device Enrollment Program umożliwia wdrożenie „na odległość” profilu rejestracji w celu zarządzania urządzeniami. Dowiedz się więcej o programie [Device Enrollment Program](device-enrollment-program-enroll-ios.md).

## <a name="apple-school-manager"></a>Apple School Manager
Apple School Manager to program zakupu rejestracji urządzeń dla szkół. Podobnie jak w przypadku programu Device Enrollment Program możliwe jest wdrożenie profilu, aby zarejestrować urządzenia w usłudze zarządzania. Dowiedz się więcej o programie [Apple School Manager](apple-school-manager-set-up-ios.md).

## <a name="apple-configurator"></a>Program Apple Configurator
Możliwe jest rejestrowanie urządzeń z systemem iOS przy użyciu programu Apple Configurator uruchomionego na komputerze Mac. Aby przygotować urządzenia, należy podłączyć je za pomocą portu USB i zainstalować profil rejestracji. Za pomocą programu Apple Configurator można rejestrować urządzenia na dwa sposoby:
- Rejestracja z użyciem Asystenta ustawień — czyści dane urządzenia i przygotowuje je do uruchomienia Asystenta ustawień, a także instaluje zasady firmy dla nowego użytkownika urządzenia.
- Rejestracja bezpośrednia — nie powoduje wyczyszczenia urządzenia i umożliwia zarejestrowanie urządzenia przy użyciu wstępnie zdefiniowanych zasad. Ta metoda służy do rejestrowania urządzeń bez koligacji użytkownika.

Dowiedz się więcej na temat [rejestrowanie programu Apple Configurator](apple-configurator-setup-assistant-enroll-ios.md).

## <a name="use-the-company-portal-on-dep-enrolled-or-apple-configurator-enrolled-devices"></a>Korzystanie z Portalu firmy na urządzeniach zarejestrowanych w programie DEP lub przy użyciu narzędzia Apple Configurator

Urządzenia skonfigurowane z koligacją użytkownika mogą instalować i uruchamiać aplikację Portal firmy w celu pobierania aplikacji i zarządzania urządzeniami. Po otrzymaniu urządzeń użytkownicy muszą wykonać kilka dodatkowych czynności w celu ukończenia działania Asystenta ustawień i zainstalowania aplikacji Portal firmy.

Koligacja użytkownika jest wymagana do obsługi:
- Aplikacji do zarządzania aplikacjami mobilnymi
- Dostępu warunkowego do poczty e-mail i danych firmowych
- Aplikacji Portal firmy

**Jak użytkownicy rejestrują urządzenia firmowe z systemem iOS z koligacją użytkownika**
1. Po włączeniu urządzenia użytkownicy są monitowani o ukończenie działania Asystenta ustawień. 
2. Po ukończeniu instalacji użytkownicy są monitowani o podanie identyfikatora Apple ID. Muszą podać identyfikator Apple ID, aby umożliwić zainstalowanie aplikacji Portal firmy na urządzeniu. 
3. Na urządzeniu z systemem iOS jest automatycznie instalowana aplikacja Portal firmy ze sklepu App Store.
4. Użytkownicy muszą uruchamiać aplikację Portal firmy i logować się przy użyciu poświadczeń (na przykład unikatowego imienia i nazwiska lub nazwy UPN) skojarzonych z ich subskrypcją w usłudze Intune. 
5. Rejestracja zostanie ukończona po zalogowaniu się. Użytkownicy mogą teraz używać tego urządzenia z pełnym zestawem funkcji.

### <a name="about-corporate-owned-managed-devices-with-no-user-affinity"></a>Informacje dotyczące zarządzanych urządzeń należących do firmy bez koligacji użytkownika

Urządzenia skonfigurowane bez koligacji użytkownika nie obsługują Portalu firmy i nie powinny mieć zainstalowanej tej aplikacji. Portal firmy jest przeznaczony dla użytkowników, którzy mają poświadczenia firmowe i wymagają dostępu do spersonalizowanych zasobów firmowych (np. poczta e-mail). Urządzenia zarejestrowane bez koligacji użytkownika nie są przeznaczone do logowania określonego użytkownika. Urządzenia rejestrowane bez koligacji użytkownika są zazwyczaj stosowane w kioskach lub punktach sprzedaży (POS) albo jako narzędzia udostępnione.

Jeśli koligacja użytkownika jest wymagana, przed zarejestrowaniem urządzenia należy sprawdzić, czy w profilu rejestracji urządzenia wybrano opcję **Koligacja użytkownika**. Aby zmienić stan koligacji urządzenia, należy wycofać urządzenie i zarejestrować je ponownie.

## <a name="see-also"></a>Zobacz także

[Troubleshooting iOS device enrollment problems in Microsoft Intune](https://support.microsoft.com/help/4039809) (Rozwiązywanie problemów dotyczących rejestrowania urządzeń z systemem iOS w usłudze Microsoft Intune)
