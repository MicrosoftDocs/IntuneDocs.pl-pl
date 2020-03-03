---
title: Tworzenie certyfikatów SECP lub PKCS w usłudze Microsoft Intune — Azure | Microsoft Docs
titleSuffix: ''
description: Administratorzy mogą użyć akcji czyszczenia lub wycofywania, aby usunąć certyfikaty z usługi Microsoft Intune. W pewnych scenariuszach, takich jak anulowanie rejestracji urządzenia lub usuwanie zasad zgodności, certyfikaty są automatycznie usuwane. W innych scenariuszach, takich jak utrata lub usunięcie licencji usługi Intune, certyfikaty automatycznie pozostają w urządzeniu. Zapoznaj się z różnymi sytuacjami dotyczącymi urządzeń z systemem Android, Android Enterprise, iOS/iPadOS, macOS i Windows.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.reviewer: lacranda
ms.openlocfilehash: a77780c05b0f637a4ee5100f8c7a1a729c3ec674
ms.sourcegitcommit: 47c9af81c385c7e893fe5a85eb79cf08e69e6831
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/25/2020
ms.locfileid: "77576248"
---
# <a name="remove-scep-and-pkcs-certificates-in-microsoft-intune"></a>Usuwanie certyfikatów SCEP i PKCS w usłudze Microsoft Intune

Usługa Microsoft Intune umożliwia dodawanie certyfikatów do urządzeń przy użyciu profilu prostego protokołu rejestrowania certyfikatów (SCEP) i profilu certyfikatów PKCS (Public Key Cryptography Standards).

Te certyfikaty mogą być usuwane podczas [czyszczenia](../remote-actions/devices-wipe.md#wipe) lub [wycofywania](../remote-actions/devices-wipe.md#retire) urządzenia. Istnieje również scenariusze, w których certyfikaty są automatycznie usuwane, i scenariusze, w których certyfikaty pozostają na urządzeniu. W tym artykule opisano niektóre typowe scenariusze oraz ich wpływ na certyfikaty PKCS i SCEP.

> [!NOTE]
> Aby usunąć i odwołać certyfikaty dla użytkownika usuwanego z lokalnej usługi Active Directory lub Azure Active Directory (Azure AD), wykonaj poniższe kroki w następującej kolejności:
>
> 1. Wyczyszczenie lub wycofanie urządzenia użytkownika.
> 2. Usunięcie użytkownika z lokalnej usługi Active Directory lub Azure AD.

## <a name="manually-deleted-certificates"></a>Certyfikaty usuwane ręcznie

Ręczne usuwanie certyfikatu to scenariusz, który ma zastosowanie na różnych platformach i do certyfikatów aprowizowanych za pomocą profilów certyfikatów SCEP i PKCS. Na przykład użytkownik może usunąć certyfikat z urządzenia, gdy na urządzaniu nadal obowiązuje zasada certyfikatu.

W tym scenariuszu po usunięciu certyfikatu, gdy urządzenie następnym razem będzie sprawdzać zasady usługi Intune, zostanie określone jako niezgodne, ponieważ nie będzie zawierać oczekiwanego certyfikatu. Usługa Intune wystawi nowy certyfikat, aby przywrócić zgodność urządzenia. Aby przywrócić certyfikat, nie jest wymagana żadna dodatkowa akcja.

## <a name="windows-devices"></a>Urządzenia z systemem Windows

### <a name="scep-certificates"></a>Certyfikaty SCEP

Certyfikat SCEP jest odwoływany *oraz* usuwany, gdy:

- Użytkownik wyrejestrowuje się.
- Administrator uruchamia akcję [czyszczenia](../remote-actions/devices-wipe.md#wipe).
- Administrator uruchamia akcję [wycofywania](../remote-actions/devices-wipe.md#retire).
- Urządzenie jest usuwane z grupy usługi Azure AD.
- Profil certyfikatu jest usuwany z przypisania grupy.

Certyfikat SCEP jest odwoływany. gdy:

- Administrator zmienia lub uaktualnia profil certyfikatu SCEP.

Certyfikat główny jest usuwany, gdy:

- Użytkownik wyrejestrowuje się.
- Administrator uruchamia akcję [czyszczenia](../remote-actions/devices-wipe.md#wipe).
- Administrator uruchamia akcję [wycofywania](../remote-actions/devices-wipe.md#retire).

Certyfikaty SCEP *pozostają* w urządzeniu (certyfikaty nie są odwoływane ani usuwane), gdy:

- Użytkownik traci licencję usługi Intune.
- Administrator wycofuje licencję usługi Intune.
- Administrator usuwa użytkownika lub grupę z usługi Azure AD.

### <a name="pkcs-certificates"></a>Certyfikaty PKCS

Certyfikat PKCS jest odwoływany *oraz* usuwany, gdy:

- Użytkownik wyrejestrowuje się.
- Administrator uruchamia akcję [czyszczenia](../remote-actions/devices-wipe.md#wipe).
- Administrator uruchamia akcję [wycofywania](../remote-actions/devices-wipe.md#retire).

Certyfikat główny jest usuwany, gdy:

- Użytkownik wyrejestrowuje się.
- Administrator uruchamia akcję [czyszczenia](../remote-actions/devices-wipe.md#wipe).
- Administrator uruchamia akcję [wycofywania](../remote-actions/devices-wipe.md#retire).

Certyfikaty PKCS *pozostają* w urządzeniu (certyfikaty nie są odwoływane ani usuwane), gdy:

- Użytkownik traci licencję usługi Intune.
- Administrator wycofuje licencję usługi Intune.
- Administrator usuwa użytkownika lub grupę z usługi Azure AD.
- Administrator zmienia lub aktualizuje profil certyfikatu SCEP.
- Profil certyfikatu jest usuwany z przypisania grupy.


## <a name="ios-devices"></a>Urządzenia z systemem iOS

### <a name="scep-certificates"></a>Certyfikaty SCEP

Certyfikat SCEP jest odwoływany *oraz* usuwany, gdy:

- Użytkownik wyrejestrowuje się.
- Administrator uruchamia akcję [czyszczenia](../remote-actions/devices-wipe.md#wipe).
- Administrator uruchamia akcję [wycofywania](../remote-actions/devices-wipe.md#retire).
- Urządzenie jest usuwane z grupy usługi Azure AD.
- Profil certyfikatu jest usuwany z przypisania grupy.

Certyfikat SCEP jest odwoływany. gdy:

- Administrator zmienia lub uaktualnia profil certyfikatu SCEP.

Certyfikat główny jest usuwany, gdy:

- Użytkownik wyrejestrowuje się.
- Administrator uruchamia akcję [czyszczenia](../remote-actions/devices-wipe.md#wipe).
- Administrator uruchamia akcję [wycofywania](../remote-actions/devices-wipe.md#retire).

Certyfikaty SCEP *pozostają* w urządzeniu (certyfikaty nie są odwoływane ani usuwane), gdy:

- Użytkownik traci licencję usługi Intune.
- Administrator wycofuje licencję usługi Intune.
- Administrator usuwa użytkownika lub grupę z usługi Azure AD.

### <a name="pkcs-certificates"></a>Certyfikaty PKCS

Certyfikat PKCS jest odwoływany *oraz* usuwany, gdy:

- Użytkownik wyrejestrowuje się.
- Administrator uruchamia akcję [czyszczenia](../remote-actions/devices-wipe.md#wipe).
- Administrator uruchamia akcję [wycofywania](../remote-actions/devices-wipe.md#retire).

Certyfikat PKCS jest usuwany, gdy:

- Profil certyfikatu jest usuwany z przypisania grupy.

Certyfikat główny jest usuwany, gdy:

- Użytkownik wyrejestrowuje się.
- Administrator uruchamia akcję [czyszczenia](../remote-actions/devices-wipe.md#wipe).
- Administrator uruchamia akcję [wycofywania](../remote-actions/devices-wipe.md#retire).

Certyfikaty PKCS *pozostają* w urządzeniu (certyfikaty nie są odwoływane ani usuwane), gdy:

- Użytkownik traci licencję usługi Intune.
- Administrator wycofuje licencję usługi Intune.
- Administrator usuwa użytkownika lub grupę z usługi Azure AD.
- Administrator zmienia lub aktualizuje profil certyfikatu SCEP.

## <a name="android-knox-devices"></a>Urządzenia z rozwiązaniem Android KNOX

### <a name="scep-certificates"></a>Certyfikaty SCEP

Certyfikat SCEP jest odwoływany *oraz* usuwany, gdy:

- Użytkownik wyrejestrowuje się.
- Administrator uruchamia akcję [czyszczenia](../remote-actions/devices-wipe.md#wipe).

Certyfikat SCEP jest odwoływany. gdy:

- Administrator uruchamia akcję [wycofywania](../remote-actions/devices-wipe.md#retire).
- Urządzenie jest usuwane z grupy usługi Azure AD.
- Profil certyfikatu jest usuwany z przypisania grupy.
- Administrator usuwa użytkownika lub grupę z usługi Azure AD.
- Administrator zmienia lub uaktualnia profil certyfikatu SCEP.

Certyfikat główny jest usuwany, gdy:

- Użytkownik wyrejestrowuje się.
- Administrator uruchamia akcję [czyszczenia](../remote-actions/devices-wipe.md#wipe).
- Administrator uruchamia akcję [wycofywania](../remote-actions/devices-wipe.md#retire).

Certyfikaty SCEP *pozostają* w urządzeniu (certyfikaty nie są odwoływane ani usuwane), gdy:

- Użytkownik traci licencję usługi Intune.
- Administrator wycofuje licencję usługi Intune.
- Administrator usuwa użytkownika lub grupę z usługi Azure AD.

### <a name="pkcs-certificates"></a>Certyfikaty PKCS

Certyfikat PKCS jest odwoływany *oraz* usuwany, gdy:

- Użytkownik wyrejestrowuje się.
- Administrator uruchamia akcję [czyszczenia](../remote-actions/devices-wipe.md#wipe).
- Administrator uruchamia akcję [wycofywania](../remote-actions/devices-wipe.md#retire).

Certyfikat główny jest usuwany, gdy:

- Użytkownik wyrejestrowuje się.
- Administrator uruchamia akcję [czyszczenia](../remote-actions/devices-wipe.md#wipe).
- Administrator uruchamia akcję [wycofywania](../remote-actions/devices-wipe.md#retire).

Certyfikaty PKCS *pozostają* w urządzeniu (certyfikaty nie są odwoływane ani usuwane), gdy:
- Użytkownik traci licencję usługi Intune.

- Administrator wycofuje licencję usługi Intune.
- Administrator usuwa użytkownika lub grupę z usługi Azure AD.
- Administrator zmienia lub aktualizuje profil certyfikatu SCEP.
- Profil certyfikatu jest usuwany z przypisania grupy.


> [!NOTE]
> Urządzenia z programem Android for Work nie są weryfikowane pod kątem powyższych scenariuszy.
> Na starszych urządzeniach z systemem Android (każdym urządzeniu firmy innej niż Samsung bez profilu służbowego) nie można usuwać certyfikatów.

## <a name="macos-certificates"></a>Certyfikaty systemu macOS

### <a name="scep-certificates"></a>Certyfikaty SCEP

Certyfikat SCEP jest odwoływany *oraz* usuwany, gdy:

- Użytkownik wyrejestrowuje się.
- Administrator uruchamia akcję [wycofywania](../remote-actions/devices-wipe.md#retire).
- Urządzenie jest usuwane z grupy usługi Azure AD.
- Profil certyfikatu jest usuwany z przypisania grupy.

Certyfikat SCEP jest odwoływany. gdy:

- Administrator zmienia lub uaktualnia profil certyfikatu SCEP.

Certyfikaty SCEP *pozostają* w urządzeniu (certyfikaty nie są odwoływane ani usuwane), gdy:

- Użytkownik traci licencję usługi Intune.
- Administrator wycofuje licencję usługi Intune.
- Administrator usuwa użytkownika lub grupę z usługi Azure AD.

> [!NOTE]
> Używanie akcji [czyszczenia](../remote-actions/devices-wipe.md#wipe) do resetowania urządzeń z systemem macOS do ustawień fabrycznych nie jest obsługiwane.

### <a name="pkcs-certificates"></a>Certyfikaty PKCS

Certyfikaty PKCS nie są obsługiwane w systemie macOS.

## <a name="next-steps"></a>Następne kroki

[Używanie certyfikatów do uwierzytelniania](certificates-configure.md)