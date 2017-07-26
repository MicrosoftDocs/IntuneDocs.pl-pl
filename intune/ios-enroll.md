---
title: "Wybieranie sposobu rejestrowania urządzeń z systemem Windows w usłudze Intune"
titleSuffix: Intune on Azure
description: "Dowiedz się, jak skonfigurować rejestrację urządzeń z systemem Windows w usłudze Microsoft Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 439c33a6-e80c-4da9-ba09-a51fc36f62ad
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 61bdbc7ca68995e23295cf099ce73dfdcaeba37c
ms.sourcegitcommit: 5eb209ae48173ddfdbbab131f12f3ac3498dcd87
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/18/2017
---
# <a name="enroll-ios-devices-in-intune"></a>Rejestrowanie urządzeń z systemem iOS w usłudze Intune

Usługa Intune umożliwia zarządzanie urządzeniami przenośnymi typu iPad i iPhone, a także zapewnia użytkownikom dostęp do poczty e-mail oraz aplikacji firmy.

Jako administrator usługi Intune możesz włączyć rejestrowanie dla urządzeń z systemem iOS. Użytkownikom można zezwolić na rejestrację prywatnych urządzeń nazywaną rejestracją typu „Przynieś własne urządzenie” (BYOD, bring your own device). Można również włączyć rejestrację urządzeń należących do firmy.

## <a name="prerequisites-for-ios-enrollment"></a>Wymagania wstępne dotyczące rejestracji urządzeń z systemem iOS
Aby możliwa była rejestracja urządzeń z systemem iOS, wykonaj następujące czynności:
- [Skonfiguruj usługę Intune](setup-steps.md) — te kroki umożliwiają skonfigurowanie infrastruktury usługi Intune. W szczególności rejestracja urządzeń wymaga [ustawienia urzędu zarządzania urządzeniami przenośnymi](mdm-authority-set.md).
- [Uzyskiwanie certyfikatu wypychania MDM firmy Apple](apple-mdm-push-certificate-get.md) — firma Apple wymaga certyfikatu, aby możliwe było zarządzania urządzeniami z systemami iOS i macOS.

Po spełnieniu tych wymagań wstępnych użytkownicy mogą zainstalować aplikację Portal firmy, aby zarejestrować swoje urządzenia z systemem iOS, lub administrator może skonfigurować zarządzanie urządzeniami z systemem iOS należącymi do firmy. Administratorzy mogą również przypisać [menedżerów rejestracji urządzeń](device-enrollment-manager-enroll.md), którzy mogą zarejestrować wiele urządzeń przy użyciu jednego konta zarządzania. Usługa Intune obsługuje następujące metody rejestracji urządzeń z systemem iOS należących do firmy:

## <a name="device-enrollment-program"></a>Program Device Enrollment Program
Organizacje mogą zakupić urządzenia z systemem iOS za pośrednictwem programu Device Enrollment Program firmy Apple. Program Device Enrollment Program umożliwia wdrożenie „na odległość” profilu rejestracji w celu zarządzania urządzeniami. Dowiedz się więcej o programie [Device Enrollment Program](device-enrollment-program-enroll-ios.md).

## <a name="apple-school-manager"></a>Apple School Manager
Apple School Manager to program zakupu rejestracji urządzeń dla szkół. Podobnie jak w przypadku programu Device Enrollment Program możliwe jest wdrożenie profilu, aby zarejestrować urządzenia w usłudze zarządzania. Dowiedz się więcej o programie [Apple School Manager](apple-school-manager-set-up-ios.md).

## <a name="apple-configurator"></a>Program Apple Configurator
Możliwe jest rejestrowanie urządzeń z systemem iOS przy użyciu programu Apple Configurator uruchomionego na komputerze Mac. Aby przygotować urządzenia, należy podłączyć je za pomocą portu USB i zainstalować profil rejestracji. Za pomocą programu Apple Configurator można rejestrować urządzenia na dwa sposoby:
- Rejestracja z użyciem Asystenta ustawień — przywraca ustawienia fabryczne urządzenia i przygotowuje je do uruchomienia Asystenta ustawień, a także instaluje zasady firmy dla nowego użytkownika urządzenia.
- Rejestracja bezpośrednia — nie powoduje przywrócenia ustawień fabrycznych urządzenia i umożliwia zarejestrowanie urządzenia przy użyciu wstępnie zdefiniowanych zasad. Ta metoda służy do rejestrowania urządzeń bez koligacji użytkownika.

Dowiedz się więcej na temat [rejestrowanie programu Apple Configurator](apple-configurator-setup-assistant-enroll-ios.md).
