---
title: Korzystanie z ustawień sieci VPN dla urządzeń z systemem Android w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zobacz wszystkie ustawienia potrzebne do utworzenia połączeń sieci VPN na urządzeniach z systemem Android w usłudze Microsoft Intune. Wprowadź nazwę połączenia, adres IP lub nazwę FQDN serwera sieci VPN, wybierz sposób uwierzytelniania użytkowników, a następnie wybierz typ połączenia Citrix, SonicWall, Check Point Capsule lub Pulse Secure.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/18/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3f82cc74aa2e351ee63ffba2629e9ddddb57fc76
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77512521"
---
# <a name="android-device-settings-to-configure-vpn-in-intune"></a>Ustawienia urządzenia z systemem Android potrzebne do skonfigurowania sieci VPN w usłudze Intune

W tym artykule wyszczególniono i opisano różne ustawienia połączenia VPN, którymi można zarządzać na urządzeniach z systemem Android. W ramach oprogramowania do zarządzania urządzeniami przenośnymi (MDM) użyj tych ustawień, aby utworzyć połączenie sieci VPN, wybrać sposób uwierzytelniania sieci VPN, wybrać typ serwera sieci VPN i wykonać inne czynności.

Jako administrator usługi Intune możesz tworzyć ustawienia sieci VPN i przypisywać je do urządzeń z systemem Android. 

Aby dowiedzieć się więcej o profilach sieci VPN w usłudze Intune, zobacz [Profile sieci VPN](vpn-settings-configure.md).

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji urządzenia](vpn-settings-configure.md#create-a-device-profile) i wybierz pozycję **Android**.

## <a name="base-vpn"></a>Podstawowa sieć VPN

- **Nazwa połączenia**: Wprowadź nazwę dla połączenia. Użytkownicy końcowi widzą tę nazwę, przeglądając w urządzeniu listę dostępnych połączeń sieci VPN. Na przykład wprowadź `Contoso VPN`.
- **Adres IP lub nazwa FQDN**: wprowadź adres IP lub w pełni kwalifikowaną nazwę domeny (FQDN) serwera sieci VPN, z którym urządzenia nawiązują połączenie. Na przykład podaj adres **192.168.1.1** lub **vpn.contoso.com**.

  - **Metoda uwierzytelniania**: wybierz sposób uwierzytelniania urządzeń na serwerze sieci VPN. Dostępne opcje:

    - **Certyfikaty**: wybierz istniejący profil certyfikatu SCEP lub PKCS na potrzeby uwierzytelniania połączenia. [Konfigurowanie certyfikatów](../protect/certificates-configure.md): zawiera procedurę tworzenia profilu certyfikatu.
    - **Nazwa użytkownika i hasło**: podczas logowania się do serwera sieci VPN użytkownicy są proszeni o wprowadzenie nazwy użytkownika i hasła.

- **Typ połączenia**: wybierz typ połączenia sieci VPN. Dostępne opcje:

  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5 Access**
  - **Pulse Secure**
  - **Citrix SSO**

- **Odcisk palca** (tylko funkcja Check Point Capsule VPN): wprowadź ciąg znaków, na przykład **Kod odcisku palca firmy Contoso**, aby sprawdzić, czy serwer sieci VPN jest zaufany. Odcisk palca jest wysyłany do klienta, dzięki czemu klient wie, że może ufać każdemu serwerowi z tym samym odciskiem palca. Jeśli urządzenie nie ma żadnego odcisku palca, wyświetli użytkownikowi monit dotyczący zaufania serwerowi sieci VPN zawierający odcisk palca serwera. Użytkownik ręcznie weryfikuje odcisk palca i wybiera pozycję Zaufane w celu nawiązania połączenia.
- **Wprowadź pary kluczy i wartości dla atrybutów sieci VPN Citrix** (tylko Citrix): wprowadź pary kluczy i wartości udostępnione przez firmę Citrix. Te wartości służą do konfigurowania właściwości połączenia sieci VPN. 

  Można również **zaimportować** plik z wartościami rozdzielanymi przecinkami (CSV) za pomocą par kluczy i wartości. Pamiętaj, aby sprawdzić właściwości **Moje dane mają nagłówki** i **Klucz**.

  Po dodaniu par kluczy i wartości użyj pozycji **Eksportuj**, aby utworzyć kopię zapasową danych w pliku CSV.

## <a name="next-steps"></a>Następne kroki

[Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).

Można również tworzyć profile sieci VPN dla urządzeń z systemem [Android Enterprise](vpn-settings-android-enterprise.md), [iOS/iPadOS](vpn-settings-ios.md), [macOS](vpn-settings-macos.md), [Windows 10 lub nowszym](vpn-settings-windows-10.md), [Windows 8.1](vpn-settings-windows-8-1.md) i [Windows Phone 8.1](vpn-settings-windows-phone-8-1.md).
