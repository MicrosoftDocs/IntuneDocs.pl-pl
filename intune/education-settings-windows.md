---
title: Ustawienia usług edukacyjnych systemu Windows 10 w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zapoznaj się z listą wszystkich ustawień usług edukacyjnych dla urządzeń z systemem Windows 10. Używaj tych ustawień w profilu konfiguracji urządzenia z aplikacją Take a Test, wybieraj sposób logowania użytkowników lub uczniów, monitoruj ekran podczas testu i wykonuj inne czynności w usłudze Intune.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 01/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 32c15037bad21ca90f81ed239ac24a9bac8d7499
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/02/2019
ms.locfileid: "57228327"
---
# <a name="configure-the-take-a-test-app-on-windows-10-devices-using-intune"></a>Konfigurowanie aplikacji Take a Test na urządzeniach z systemem Windows 10 przy użyciu usługi Intune

W tym artykule opisano wszystkie ustawienia edukacyjnej aplikacji Take a Test, które można skonfigurować w usłudze Microsoft Intune na urządzeniach z systemem Windows 10 lub nowszym. Korzystając z tej aplikacji, uczniowie mogą logować się do urządzenia i brać udział w teście.

Te ustawienia są dodawane do profilu konfiguracji urządzenia, a następnie przypisywane do urządzeń lub wdrażane na nich przy użyciu usługi Microsoft Intune.

Artykuł [Aplikacja Take a Test w usłudze Intune](education-settings-configure.md) zawiera więcej informacji na temat tej funkcji.

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji urządzenia](education-settings-configure.md#create-a-device-profile).

## <a name="take-a-test-settings"></a>Ustawienia aplikacji Take a Test

- **Typ konta**: wybierz sposób logowania użytkowników do testu. Dostępne opcje:
  - Konto usługi Azure AD
  - Konto domeny
  - Konto lokalne
- **Nazwa użytkownika konta**: wprowadź nazwę użytkownika konta używanego z aplikacją Take a Test. Konta można wprowadzić w następującym formacie:
  - `user@contoso.com`
  - `domain\username`
  - `user@contoso.com`
  - `computerName\username`
- **Adres URL oceny**: wprowadź adres URL testu, który mają wykonać użytkownicy. Więcej informacji na temat uzyskiwania adresu URL znajduje się w [dokumentacji aplikacji Take a Test](https://docs.microsoft.com/education/windows/take-tests-in-windows-10).
- **Monitorowanie ekranu**: wybierz pozycję **Zezwalaj**, aby monitorować działania ekranu podczas wykonywania testu przez użytkowników. Pozycja **Nieskonfigurowane** uniemożliwia monitorowanie ekranu podczas testu.
- **Sugestia tekstowa**: wybierz pozycję **Zezwalaj**, aby uczestnicy testu mogą zobaczyć sugestie tekstowe. Pozycja **Nieskonfigurowane** powoduje blokowanie sugestii tekstowych podczas wykonywania testu przez użytkowników.

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale może jeszcze nie wykonywać żadnych czynności. Pamiętaj, aby [przypisać profil](device-profile-assign.md) i [monitorować jego stan](device-profile-monitor.md).
