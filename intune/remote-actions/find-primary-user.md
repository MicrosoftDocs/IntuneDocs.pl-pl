---
title: Znajdowanie użytkownika podstawowego urządzenia usługi Microsoft Intune.
titleSuffix: ''
description: Znajdź użytkownika podstawowego (lub koligację urządzenia użytkownika) urządzenia usługi Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d6f594e20abf1a507d1d4e00641a4821fe1ba9b0
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72509330"
---
# <a name="find-the-primary-user-of-an-intune-device"></a>Znajdowanie użytkownika podstawowego urządzenia usługi Intune

Użytkownik podstawowy, określany również jako koligacja urządzenia użytkownika, to właściwość każdego urządzenia usługi Intune. Urządzenie usługi Intune może nie mieć przypisanego użytkownika podstawowego lub mieć przypisanego jednego użytkownika podstawowego. Jeśli nie przypisano użytkownika podstawowego, urządzenie jest określane jako „Urządzenie udostępnione”.

## <a name="how-to-find-a-devices-primary-user"></a>Jak znaleźć użytkownika podstawowego urządzenia

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz pozycję **Urządzenia** > wybierz urządzenie.
3. Na stronie **Omówienie** wybierz pozycję **Zobacz więcej**. Zostanie wyświetlony użytkownik podstawowy.

## <a name="what-is-the-primary-user"></a>Kto to jest użytkownik podstawowy?
Właściwość użytkownika podstawowego jest używana do mapowania licencjonowanego użytkownika usługi Intune na urządzeniach w:
- Aplikacji Portal firmy
- Witrynie internetowej użytkownika końcowego
- Profesjonalnych środowiskach IT, takich jak strony rozwiązywania problemów w witrynie Azure Portal. Te strony mapują konta użytkowników na urządzenia przy użyciu użytkownika podstawowego.    

### <a name="company-portal-app"></a>Aplikacji Portal firmy
Aplikacja Portal firmy oczekuje, że konto użytkownika zalogowanego do Portalu firmy jest użytkownikiem podstawowym danego urządzenia. Jeśli inny użytkownik został przypisany jako użytkownik podstawowy, aplikacja Portal firmy wyświetla ostrzeżenie:

„To urządzenie zostało już przypisane do kogoś w Twojej organizacji. Skontaktuj się z działem pomocy technicznej firmy w sprawie przypisania jako użytkownik podstawowy urządzenia. Możesz nadal używać aplikacji Portal firmy, ale funkcjonalność będzie ograniczona”.

Jeśli urządzenie usługi Intune nie ma przypisanego użytkownika podstawowego, aplikacja Portal firmy wykrywa je jako urządzenie udostępnione. Urządzenia udostępnione można wizualnie identyfikować dzięki etykiecie „udostępnione” wyświetlanej na kafelku urządzenia. W tym trybie aplikacji Portal firmy można nadal używać do żądania i instalowania dostępnych aplikacji. Jednak akcje samoobsługi (resetowanie/zmienianie nazwy/wycofywanie) są niedostępne.  

Aby dostępne aplikacje były wyświetlane w Portalu firmy na urządzeniach udostępnionych, muszą zostać przypisane do grupy użytkowników. Zostaną one zainstalowane w kontekście systemowym lub w kontekście użytkownika, w zależności od tego, jak aplikacja została skonfigurowana przez administratora IT. Aby uzyskać więcej informacji na temat kontekstu aplikacji, zobacz sekcję [Instalowanie aplikacji na urządzeniach z systemem Windows 10](../apps/apps-windows-10-app-deploy.md). Do korzystania z tej funkcji jest wymagana aplikacja Portal firmy w wersji 10.3.4651.0 lub nowszej.


## <a name="who-is-assigned-as-the-primary-user"></a>Kto jest przydzielany jako użytkownik podstawowy?
Usługa Intune automatycznie dodaje użytkownika podstawowego na urządzeniach podczas rejestracji lub wkrótce po niej. Metoda rejestracji określa, kiedy użytkownik podstawowy jest dodawany do urządzenia.

| Platforma | Metoda rejestracji | Przypisany użytkownik podstawowy | Użytkownik podstawowy jest przypisywany |
| ---- | ---- | ---- | ---- |
| Windows | Dodawanie miejsca pracy lub szkoły (sterowane przez użytkownika) | Użytkownik rejestrujący | Podczas rejestracji |   
| Windows | Logowanie do nowoczesnych aplikacji (sterowane przez użytkownika) | Użytkownik rejestrujący | Podczas rejestracji | 
| Windows | Rejestrowanie tylko w oprogramowaniu MDM (sterowane przez użytkownika) | Użytkownik rejestrujący | Podczas rejestracji | 
| Windows | Przyłączanie do usługi Azure AD (gotowe środowisko) | Użytkownik rejestrujący | Podczas rejestracji | 
| Windows | Przyłączanie do usługi Azure AD (gotowe środowisko rozwiązania Autopilot) | Użytkownik rejestrujący | Podczas rejestracji | 
| Windows | Rejestrowanie tylko w oprogramowaniu MDM | Użytkownik rejestrujący | Podczas rejestracji | 
| Windows | Hybrydowa funkcja AADJ i obiekt zasad grupy automatycznej rejestracji | Pierwszy użytkownik zalogowany w systemie Windows | Kiedy pierwszy użytkownik zaloguje się w systemie Windows| 
| Windows | Współzarządzanie | Pierwszy użytkownik zalogowany w systemie Windows | Kiedy pierwszy użytkownik zaloguje się w systemie Windows | 
| Windows | Przyłączanie do usługi Azure AD (token rejestracji zbiorczej) | Brak | Nie dotyczy | 
| Windows | Przyłączanie do usługi Azure AD (tryb samowdrażania rozwiązania Autopilot) | Brak | Nie dotyczy | 
| Wiele platform | Rejestracja sterowana przez użytkownika za pomocą aplikacji Portal firmy | Użytkownik rejestrujący | Podczas rejestracji |
| Wiele platform | Menedżer rejestracji urządzeń (DEM, Device Enrollment Manager) | Rejestrujący użytkownik DEM | Podczas rejestracji |
| iOS, macOS | Zautomatyzowane rejestrowanie urządzeń firmy Apple (program DEP z koligacją użytkownika) | Użytkownik rejestrujący | Podczas rejestracji |
| iOS, macOS | Zautomatyzowane rejestrowanie urządzeń firmy Apple (program DEP bez koligacji użytkownika) | Brak | Nie dotyczy |
| Android | Należące do firmy, dedykowane urządzenia z systemem Android | Brak | Nie dotyczy |

## <a name="primary-user-and-azure-ad-device-owner"></a>Użytkownik podstawowy i właściciel urządzenia w usłudze Azure AD
W niektórych przypadkach użytkownik podstawowy usługi Intune może różnić się od właściwości **Właściciel** urządzenia usługi Azure AD (widocznej w obszarze **Urządzenia** > **Urządzenia usługi Azure AD**). Właściciel urządzenia usługi Azure AD jest dodawany podczas rejestracji urządzenia w usłudze Azure Active Directory.

## <a name="next-steps"></a>Następne kroki
[Zarządzanie urządzeniami usługi Intune.](device-management.md)
