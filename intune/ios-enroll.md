---
title: "Wybieranie sposobu rejestrowania urządzeń z systemem iOS w usłudze Intune"
titlesuffix: Microsoft Intune
description: "Konfigurowanie rejestrowania urządzeń z systemem iOS w usłudze Microsoft Intune."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 439c33a6-e80c-4da9-ba09-a51fc36f62ad
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e79122c1bea970525faaf443f9bf4271d050abe2
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/08/2018
---
# <a name="enroll-ios-devices-in-intune"></a>Rejestrowanie urządzeń z systemem iOS w usłudze Intune

Usługa Intune umożliwia zarządzanie urządzeniami przenośnymi typu iPad i iPhone, a także zapewnia użytkownikom dostęp do poczty e-mail oraz aplikacji firmy.

Jako administrator usługi Intune możesz włączyć rejestrowanie dla urządzeń z systemem iOS. Użytkownikom można zezwolić na rejestrację prywatnych urządzeń nazywaną rejestracją typu „Przynieś własne urządzenie” (BYOD, bring your own device). Można również włączyć rejestrację urządzeń należących do firmy.

## <a name="prerequisites-for-ios-enrollment"></a>Wymagania wstępne dotyczące rejestracji urządzeń z systemem iOS
Aby możliwa była rejestracja urządzeń z systemem iOS, wykonaj następujące czynności:
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
- Rejestracja z użyciem Asystenta ustawień — przywraca ustawienia fabryczne urządzenia i przygotowuje je do uruchomienia Asystenta ustawień, a także instaluje zasady firmy dla nowego użytkownika urządzenia.
- Rejestracja bezpośrednia — nie powoduje przywrócenia ustawień fabrycznych urządzenia i umożliwia zarejestrowanie urządzenia przy użyciu wstępnie zdefiniowanych zasad. Ta metoda służy do rejestrowania urządzeń bez koligacji użytkownika.

Dowiedz się więcej na temat [rejestrowanie programu Apple Configurator](apple-configurator-setup-assistant-enroll-ios.md).

## <a name="use-the-company-portal-on-dep-enrolled-or-apple-configurator-enrolled-devices"></a>Korzystanie z Portalu firmy na urządzeniach zarejestrowanych w programie DEP lub przy użyciu narzędzia Apple Configurator

Na urządzeniach skonfigurowanych z koligacją użytkownika można zainstalować aplikację Portal firmy i używać jej do pobierania aplikacji i zarządzania urządzeniami. Po otrzymaniu urządzeń użytkownicy muszą wykonać kilka dodatkowych czynności w celu ukończenia działania Asystenta ustawień i zainstalowania aplikacji Portal firmy.

Koligacja użytkownika jest wymagana do obsługi:
  - Aplikacji do zarządzania aplikacjami mobilnymi
  - Warunkowego dostępu do poczty e-mail i danych firmowych
  - Aplikacji Portal firmy

**Jak użytkownicy rejestrują urządzenia firmowe z systemem iOS z koligacją użytkownika**
1. Po włączeniu urządzenia użytkownicy są monitowani o ukończenie działania Asystenta ustawień. Podczas instalacji użytkownicy są monitowani o podanie swoich poświadczeń. Muszą oni korzystać z poświadczeń (tj. unikatowej kombinacji imienia i nazwiska lub nazwy UPN) skojarzonych z ich subskrypcją w usłudze Intune.

2. Podczas instalacji użytkownicy są monitowani o podanie identyfikatora Apple ID. Muszą podać identyfikator Apple ID, aby umożliwić zainstalowanie aplikacji Portal firmy na urządzeniu. Mogą także podać identyfikator z menu ustawień systemu iOS po zakończeniu konfiguracji.

3. Po ukończeniu konfiguracji na urządzeniu iOS trzeba zainstalować aplikację Portal firmy ze sklepu App Store.

4. Użytkownik może się teraz zalogować do Portalu firmy przy użyciu nazwy UPN użytej podczas konfigurowania urządzenia.

5. Po zalogowaniu użytkownik jest monitowany o zarejestrowanie urządzenia. Pierwszym krokiem jest zidentyfikowanie urządzenia. Aplikacja wyświetla listę urządzeń z systemem iOS, które zostały już zarejestrowane przez firmę i przypisane do konta użytkownika w usłudze Intune. Użytkownicy powinni wybrać odpowiednie urządzenie.

  Jeśli to urządzenie nie zostało jeszcze zarejestrowane przez firmę, użytkownicy powinni wybrać pozycję **nowe urządzenie**, aby kontynuować standardową procedurę rejestracji.

6. Na następnym ekranie użytkownik musi potwierdzić numer seryjny nowego urządzenia. Użytkownik może nacisnąć link **Potwierdź numer seryjny**, aby otworzyć instrukcje korzystania z aplikacji Ustawienia w celu zweryfikowania numeru seryjnego. Użytkownik musi następnie wprowadzić cztery ostatnie znaki numeru seryjnego do aplikacji Portal firmy.

  Ten krok umożliwia zweryfikowanie, że urządzenie zostało zarejestrowane przez firmę w usłudze Intune. Jeśli numer seryjny urządzenia nie jest zgodny, oznacza to, że wybrano niewłaściwe urządzenie. Użytkownik powinien wrócić do poprzedniego ekranu i wybrać inne urządzenie.

7. Po zweryfikowaniu numeru seryjnego aplikacja Portal firmy wykonuje przekierowanie do witryny internetowej Portalu firmy w celu sfinalizowania rejestracji. Następnie w witrynie pojawia się monit o powrót użytkownika do aplikacji.

8. Rejestracja jest teraz ukończona. Użytkownik może teraz używać tego urządzenia z pełnym zestawem funkcji.

### <a name="about-corporate-owned-managed-devices-with-no-user-affinity"></a>Informacje dotyczące zarządzanych urządzeń należących do firmy bez koligacji użytkownika

Urządzenia skonfigurowane bez koligacji użytkownika nie obsługują Portalu firmy i nie powinny mieć zainstalowanej tej aplikacji. Portal firmy jest przeznaczony dla użytkowników, którzy mają poświadczenia firmowe i wymagają dostępu do spersonalizowanych zasobów firmowych (np. poczta e-mail). Urządzenia zarejestrowane bez koligacji użytkownika nie są przeznaczone do logowania określonego użytkownika. Urządzenia rejestrowane bez koligacji użytkownika są zazwyczaj stosowane w kioskach lub punktach sprzedaży (POS) albo jako narzędzia udostępnione.

Jeśli koligacja użytkownika jest wymagana, przed zarejestrowaniem urządzenia należy sprawdzić, czy w profilu rejestracji urządzenia wybrano opcję **Koligacja użytkownika**. Aby zmienić stan koligacji urządzenia, należy wycofać urządzenie i zarejestrować je ponownie.

