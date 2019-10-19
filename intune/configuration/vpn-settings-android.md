---
title: Korzystanie z ustawień sieci VPN dla urządzeń z systemem Android w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zobacz wszystkie ustawienia, aby utworzyć połączenia sieci VPN na urządzeniach z systemem Android w Microsoft Intune. Wprowadź nazwę połączenia, adres IP lub nazwę FQDN serwera sieci VPN, wybierz sposób uwierzytelniania użytkowników, a następnie wybierz Citrix, SonicWall, Check Point kapsułka i Pulse bezpieczne typy połączeń.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/06/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8d9fefc2413e2dafbf5d0ad67ea15f5f8406cc1c
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72506546"
---
# <a name="android-device-settings-to-configure-vpn-in-intune"></a>Ustawienia urządzenia z systemem Android w celu skonfigurowania sieci VPN w usłudze Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

W tym artykule wyszczególniono i opisano różne ustawienia połączenia VPN, którymi można zarządzać na urządzeniach z systemem Android. W ramach rozwiązania do zarządzania urządzeniami przenośnymi (MDM) Użyj tych ustawień, aby utworzyć połączenie sieci VPN, wybierz sposób uwierzytelniania sieci VPN, wybierz typ serwera sieci VPN i inne.

Jako administrator usługi Intune możesz tworzyć ustawienia sieci VPN i przypisywać je do urządzeń z systemem Android. 

Aby dowiedzieć się więcej o profilach sieci VPN w usłudze Intune, zobacz [Profile sieci VPN](vpn-settings-configure.md).

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji urządzenia](vpn-settings-configure.md#create-a-device-profile) i wybierz pozycję **Android**.

## <a name="base-vpn"></a>Podstawowa sieć VPN

- **Nazwa połączenia**: umożliwia wprowadzenie nazwy połączenia. Użytkownicy końcowi widzą tę nazwę, przeglądając w urządzeniu listę dostępnych połączeń sieci VPN. Na przykład wprowadź `Contoso VPN`.
- **Adres IP lub nazwa FQDN** — podaj adres IP lub w pełni kwalifikowaną nazwę domeny (FQDN) serwera sieci VPN, z którym urządzenia nawiązują połączenie. Na przykład podaj adres **192.168.1.1** lub **vpn.contoso.com**.

  - **Metoda uwierzytelniania**: umożliwia wybór sposobu uwierzytelniania urządzeń na serwerze sieci VPN. Dostępne opcje:

    - **Certyfikaty**: wybierz istniejący profil certyfikatu SCEP lub PKCS na potrzeby uwierzytelniania połączenia. [Konfigurowanie certyfikatów](../protect/certificates-configure.md): zawiera procedurę tworzenia profilu certyfikatu.
    - **Nazwa użytkownika i hasło**: podczas logowania na serwerze VPN użytkownicy końcowi są proszeni o podanie nazwy użytkownika i hasła.

- **Typ połączenia**: pozwala wybrać typ połączenia VPN. Dostępne opcje:

  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5 Access**
  - **Pulse Secure**
  - **Citrix SSO**

- **Odcisk palca** (tylko dla Check Point Capsule VPN) — wprowadź ciąg znaków, na przykład **Kod odcisku palca firmy Contoso**, aby sprawdzić, czy serwer sieci VPN jest zaufany. Odcisk palca jest wysyłany do klienta, aby Klient wiedział, aby ufać każdemu serwerowi, który ma ten sam odcisk palca. Jeśli urządzenie nie ma żadnego odcisku palca, wyświetli użytkownikowi monit dotyczący zaufania serwerowi sieci VPN zawierający odcisk palca serwera. Użytkownik ręcznie weryfikuje odcisk palca i wybiera pozycję Zaufane w celu nawiązania połączenia.
- **Podaj pary klucza i wartości dla atrybutów sieci VPN Citrix** (tylko dla dostawcy Citrix) — wprowadź pary klucza i wartości dostarczone przez dostawcę Citrix. Te wartości służą do konfigurowania właściwości połączenia sieci VPN. 

  Można również **zaimportować** plik z wartościami rozdzielanymi przecinkami (CSV) za pomocą par klucze i wartość. Pamiętaj, aby sprawdzić, czy **moje dane mają nagłówki** i właściwości **klucza** .

  Po dodaniu par kluczy i wartości Użyj opcji **Eksportuj** , aby utworzyć kopię zapasową danych w pliku CSV.

## <a name="next-steps"></a>Następne kroki

[Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).

Można również tworzyć profile sieci VPN dla urządzeń z [systemem Android Enterprise](vpn-settings-android-enterprise.md), [iOS](vpn-settings-ios.md), [macOS](vpn-settings-macos.md), [Windows 10 i nowszych](vpn-settings-windows-10.md), [Windows 8.1](vpn-settings-windows-8-1.md)i [Windows Phone 8,1](vpn-settings-windows-phone-8-1.md) .
