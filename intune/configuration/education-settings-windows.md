---
title: Ustawienia usług edukacyjnych systemu Windows 10 w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zapoznaj się z listą wszystkich ustawień usług edukacyjnych dla urządzeń z systemem Windows 10. Używaj tych ustawień w profilu konfiguracji urządzenia z aplikacją Take a Test, wybieraj sposób logowania użytkowników lub uczniów, monitoruj ekran podczas testu i wykonuj inne czynności w usłudze Intune.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 07/03/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: kakyker
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7d89f512c06dcfbf6f6ddaba5e17ac9ca6f0becf
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72506805"
---
# <a name="configure-the-take-a-test-app-on-windows-10-devices-using-intune"></a>Konfigurowanie aplikacji Take a Test na urządzeniach z systemem Windows 10 przy użyciu usługi Intune

Aplikacja Wypełnij test pozwala bezpiecznie administrować testami online na urządzeniach z systemem Windows 10. Aby skonfigurować aplikację Wypełnij test, należy utworzyć profil konfiguracji urządzenia w usłudze Intune i skonfigurować ustawienia dotyczące bezpiecznej oceny. W tym artykule opisano ustawienia, które można znaleźć dla aplikacji Wypełnij test. 

Po skonfigurowaniu profilu przypisz go uczniom i Wdróż go. 

Artykuł [Aplikacja Take a Test w usłudze Intune](education-settings-configure.md) zawiera więcej informacji na temat tej funkcji.

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji urządzenia](education-settings-configure.md#create-a-device-profile).

## <a name="take-a-test-settings"></a>Ustawienia aplikacji Take a Test
Po utworzeniu profilu konfiguracji urządzenia przejdź do pozycji **Typ profilu** i wybierz pozycję **bezpieczna Ocena (edukacja)** . Możesz znaleźć następujące ustawienia aplikacji Wypełnij test. 


- **Typ konta**: wybierz sposób logowania użytkowników do testu. Dostępne opcje:
  - Konto usługi Azure AD
  - Konto domeny
  - Konto lokalne
  - Lokalne konto gościa: dostępne tylko na urządzeniach z systemem Windows 10 w wersji 1903 lub nowszej.    
- **Nazwa użytkownika konta**: wprowadź nazwę użytkownika konta używanego z aplikacją Take a Test. Konta można wprowadzić w następującym formacie:
  - `user@contoso.com`
  - `domain\username`
  - `user@contoso.com`
  - `computerName\username`
- **Nazwa konta**: Aby skonfigurować typ lokalnego konta gościa, wprowadź nazwę konta używanego z aplikacją Wypełnij aplikację testową. Nazwa konta zostanie wyświetlona jako kafelek na ekranie logowania. Studenci klikają kafelek, aby uruchomić test.  
- **Adres URL oceny**: wprowadź adres URL testu, który mają wykonać użytkownicy. Więcej informacji na temat uzyskiwania adresu URL znajduje się w [dokumentacji aplikacji Take a Test](https://docs.microsoft.com/education/windows/take-tests-in-windows-10).
- **Połączenie drukarki**: wybierz opcję **Wymagaj** , aby zezwolić na dostęp tylko do aplikacji Take a test z urządzeń, które są podłączone do drukarki. To ustawienie powoduje także udostępnienie przycisku drukowania aplikacji opcji test-uczestnikom. **Nieskonfigurowane** zezwala uczniom na dostęp do aplikacji z urządzeń, które nie są połączone z drukarką.  
- **Monitorowanie ekranu**: wybierz pozycję **Zezwalaj**, aby monitorować działania ekranu podczas wykonywania testu przez użytkowników. Pozycja **Nieskonfigurowane** uniemożliwia monitorowanie ekranu podczas testu.
- **Podpowiedzi tekstowe**: wybierz pozycję **Zezwalaj**, aby uczestnicy testu mogli zobaczyć podpowiedzi tekstowe. Pozycja **Nieskonfigurowane** powoduje blokowanie sugestii tekstowych podczas wykonywania testu przez użytkowników.

## <a name="next-steps"></a>Następne kroki

Pamiętaj, aby [przypisać profil](device-profile-assign.md) i [monitorować jego stan](device-profile-monitor.md).
