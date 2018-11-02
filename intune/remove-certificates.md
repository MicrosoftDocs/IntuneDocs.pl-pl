---
title: Tworzenie certyfikatów SECP lub PKCS w usłudze Microsoft Intune — Azure | Microsoft Docs
titleSuffix: ''
description: Administratorzy mogą użyć akcji czyszczenia lub wycofywania, aby usunąć certyfikaty z usługi Microsoft Intune. W pewnych scenariuszach, takich jak anulowanie rejestracji urządzenia lub usuwanie zasad zgodności, certyfikaty są automatycznie usuwane. W innych scenariuszach, takich jak utrata lub usunięcie licencji usługi Intune, certyfikaty automatycznie pozostają w urządzeniu. Zapoznaj się z różnymi sytuacjami dotyczącymi urządzeń z systemem Android, Android Enterprise, iOS, macOS i Windows.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d4287322fd494c97cf24feb8cc16435a4405f2af
ms.sourcegitcommit: 7a649a5995600fb91817643e20a5565caedbb8f2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/26/2018
ms.locfileid: "50150111"
---
# <a name="remove-scep-and-pkcs-certificates-in-microsoft-intune"></a>Usuwanie certyfikatów SCEP i PKCS w usłudze Microsoft Intune

W usłudze Microsoft Intune możesz dodawać certyfikaty SCEP i PKCS do urządzeń. Te certyfikaty mogą być również usuwane podczas [czyszczenia](devices-wipe.md#wipe) lub [wycofywania](devices-wipe.md#retire) urządzenia. Istnieje określone scenariusze, w których certyfikaty są automatycznie usuwane, i scenariusze, w których certyfikaty pozostają w urządzeniu.

W tym artykule opisano niektóre typowe scenariusze oraz ich wpływ na certyfikaty PKCS i SCEP.

> [!NOTE]
> Aby usunąć i odwołać certyfikaty dla użytkownika usuwanego z usługi Active Directory (AD) lub Azure AD, wykonaj poniższe kroki w następującej kolejności:
>
>    1. Wyczyszczenie lub wycofanie urządzenia użytkownika
>    2. Usunięcie użytkownika z usługi AD lub Azure AD

## <a name="windows-devices"></a>Urządzenia z systemem Windows

#### <a name="scep-certificates"></a>Certyfikaty SCEP

- Certyfikat SCEP jest odwoływany *oraz* usuwany, gdy:

  - Użytkownik końcowy wyrejestrowuje się
  - Administrator uruchamia akcję [czyszczenia](devices-wipe.md#wipe)
  - Administrator uruchamia akcję [wycofywania](devices-wipe.md#retire)
  - Urządzenie jest usuwane z grupy usługi Azure Active Directory (AD)
  - Zasady zgodności są usuwane z przypisania grupy
  - Profil konfiguracji jest usuwany z przypisania grupy

- Certyfikat SCEP jest odwoływany. gdy:
  - Administrator zmienia lub uaktualnia profil certyfikatu SCEP

- Certyfikat główny jest usuwany, gdy:
  - Użytkownik końcowy wyrejestrowuje się
  - Administrator uruchamia akcję [czyszczenia](devices-wipe.md#wipe)
  - Administrator uruchamia akcję [wycofywania](devices-wipe.md#retire)
  - Zasady zgodności są usuwane z przypisania grupy

- Certyfikaty SCEP **pozostają** w urządzeniu (certyfikaty nie są odwoływane ani usuwane), gdy:
  - Użytkownik końcowy traci licencję usługi Intune
  - Administrator wycofuje licencję usługi Intune
  - Administrator usuwa użytkownika lub grupę z usługi Azure AD

#### <a name="pkcs-certificates"></a>Certyfikaty PKCS

- Certyfikat PKCS jest odwoływany *oraz* usuwany, gdy:

  - Użytkownik końcowy wyrejestrowuje się
  - Administrator uruchamia akcję [czyszczenia](devices-wipe.md#wipe)
  - Administrator uruchamia akcję [wycofywania](devices-wipe.md#retire)

- Certyfikat główny jest usuwany, gdy:
  - Użytkownik końcowy wyrejestrowuje się
  - Administrator uruchamia akcję [czyszczenia](devices-wipe.md#wipe)
  - Administrator uruchamia akcję [wycofywania](devices-wipe.md#retire)

- Certyfikaty PKCS **pozostają** w urządzeniu (certyfikaty nie są odwoływane ani usuwane), gdy:
  - Użytkownik końcowy traci licencję usługi Intune
  - Administrator wycofuje licencję usługi Intune
  - Administrator usuwa użytkownika lub grupę z usługi Azure AD
  - Administrator zmienia lub uaktualnia profil certyfikatu SCEP
  - Profil konfiguracji jest usuwany z przypisania grupy
  - Zasady zgodności są usuwane z przypisania grupy 


## <a name="ios-devices"></a>Urządzenia z systemem iOS

#### <a name="scep-certificates"></a>Certyfikaty SCEP

- Certyfikat SCEP jest odwoływany *oraz* usuwany, gdy:

  - Użytkownik końcowy wyrejestrowuje się
  - Administrator uruchamia akcję [czyszczenia](devices-wipe.md#wipe)
  - Administrator uruchamia akcję [wycofywania](devices-wipe.md#retire)
  - Urządzenie jest usuwane z grupy usługi Azure Active Directory (AD)
  - Zasady zgodności są usuwane z przypisania grupy
  - Profil konfiguracji jest usuwany z przypisania grupy

- Certyfikat SCEP jest odwoływany. gdy:
  - Administrator zmienia lub uaktualnia profil certyfikatu SCEP

- Certyfikat główny jest usuwany, gdy:
  - Użytkownik końcowy wyrejestrowuje się
  - Administrator uruchamia akcję [czyszczenia](devices-wipe.md#wipe)
  - Administrator uruchamia akcję [wycofywania](devices-wipe.md#retire)
  - Zasady zgodności są usuwane z przypisania grupy

- Certyfikaty SCEP **pozostają** w urządzeniu (certyfikaty nie są odwoływane ani usuwane), gdy:
  - Użytkownik końcowy traci licencję usługi Intune
  - Administrator wycofuje licencję usługi Intune
  - Administrator usuwa użytkownika lub grupę z usługi Azure AD

#### <a name="pkcs-certificates"></a>Certyfikaty PKCS

- Certyfikat PKCS jest odwoływany *oraz* usuwany, gdy:

  - Użytkownik końcowy wyrejestrowuje się
  - Administrator uruchamia akcję [czyszczenia](devices-wipe.md#wipe)
  - Administrator uruchamia akcję [wycofywania](devices-wipe.md#retire)

- Certyfikat PKCS jest usuwany, gdy:
  - Zasady zgodności są usuwane z przypisania grupy
  - Profil konfiguracji jest usuwany z przypisania grupy
  
- Certyfikat główny jest usuwany, gdy:
  - Użytkownik końcowy wyrejestrowuje się
  - Administrator uruchamia akcję [czyszczenia](devices-wipe.md#wipe)
  - Administrator uruchamia akcję [wycofywania](devices-wipe.md#retire)

- Certyfikaty PKCS **pozostają** w urządzeniu (certyfikaty nie są odwoływane ani usuwane), gdy:
  - Użytkownik końcowy traci licencję usługi Intune
  - Administrator wycofuje licencję usługi Intune
  - Administrator usuwa użytkownika lub grupę z usługi Azure AD
  - Administrator zmienia lub uaktualnia profil certyfikatu SCEP

## <a name="android--android-enterprise-devices"></a>Urządzenia z systemem Android i rozwiązaniem Android Enterprise

#### <a name="scep-certificates"></a>Certyfikaty SCEP

- Certyfikat SCEP jest odwoływany *oraz* usuwany, gdy:
  - Użytkownik końcowy wyrejestrowuje się
  - Administrator uruchamia akcję [czyszczenia](devices-wipe.md#wipe)

- Certyfikat SCEP jest odwoływany. gdy:
  - Administrator uruchamia akcję [wycofywania](devices-wipe.md#retire)
  - Urządzenie jest usuwane z grupy usługi Azure Active Directory (AD)
  - Zasady zgodności są usuwane z przypisania grupy
  - Profil konfiguracji jest usuwany z przypisania grupy
  - Administrator usuwa użytkownika lub grupę z usługi Azure Active Directory (AD)
  - Administrator zmienia lub uaktualnia profil certyfikatu SCEP

- Certyfikat główny jest usuwany, gdy:
  - Użytkownik końcowy wyrejestrowuje się
  - Administrator uruchamia akcję [czyszczenia](devices-wipe.md#wipe)
  - Administrator uruchamia akcję [wycofywania](devices-wipe.md#retire)

- Certyfikaty SCEP **pozostają** w urządzeniu (certyfikaty nie są odwoływane ani usuwane), gdy:
  - Użytkownik końcowy traci licencję usługi Intune
  - Administrator wycofuje licencję usługi Intune
  - Administrator usuwa użytkownika lub grupę z usługi Azure AD

#### <a name="pkcs-certificates"></a>Certyfikaty PKCS

- Certyfikat PKCS jest odwoływany *oraz* usuwany, gdy:

  - Użytkownik końcowy wyrejestrowuje się
  - Administrator uruchamia akcję [czyszczenia](devices-wipe.md#wipe)
  - Administrator uruchamia akcję [wycofywania](devices-wipe.md#retire)

- Certyfikat główny jest usuwany, gdy:
  - Użytkownik końcowy wyrejestrowuje się
  - Administrator uruchamia akcję [czyszczenia](devices-wipe.md#wipe)
  - Administrator uruchamia akcję [wycofywania](devices-wipe.md#retire)

- Certyfikaty PKCS **pozostają** w urządzeniu (certyfikaty nie są odwoływane ani usuwane), gdy:
  - Użytkownik końcowy traci licencję usługi Intune
  - Administrator wycofuje licencję usługi Intune
  - Administrator usuwa użytkownika lub grupę z usługi Azure AD
  - Administrator zmienia lub uaktualnia profil certyfikatu SCEP
  - Profil konfiguracji jest usuwany z przypisania grupy
  - Zasady zgodności są usuwane z przypisania grupy 

## <a name="macos-certificates"></a>Certyfikaty systemu macOS

#### <a name="scep-certificates"></a>Certyfikaty SCEP

- Certyfikat SCEP jest odwoływany *oraz* usuwany, gdy:
  - Użytkownik końcowy wyrejestrowuje się
  - Administrator uruchamia akcję [wycofywania](devices-wipe.md#retire)
  - Urządzenie jest usuwane z grupy usługi Azure Active Directory (AD)
  - Zasady zgodności są usuwane z przypisania grupy
  - Profil konfiguracji jest usuwany z przypisania grupy

- Certyfikat SCEP jest odwoływany. gdy:
  - Administrator zmienia lub uaktualnia profil certyfikatu SCEP

- Certyfikaty SCEP **pozostają** w urządzeniu (certyfikaty nie są odwoływane ani usuwane), gdy:
  - Użytkownik końcowy traci licencję usługi Intune
  - Administrator wycofuje licencję usługi Intune
  - Administrator usuwa użytkownika lub grupę z usługi Azure AD

> [!NOTE]
> Używanie akcji [czyszczenia](devices-wipe.md#wipe) do resetowania urządzeń z systemem macOS do ustawień fabrycznych nie jest obsługiwane.

#### <a name="pkcs-certificates"></a>Certyfikaty PKCS

Certyfikaty PKCS nie są obsługiwane w systemie macOS.

