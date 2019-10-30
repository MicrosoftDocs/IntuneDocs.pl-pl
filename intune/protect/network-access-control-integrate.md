---
title: Integracja kontroli dostępu do sieci z usługą Microsoft Intune — Azure | Microsoft Docs
description: Rozwiązania z zakresu kontroli dostępu do sieci (NAC, network access control) sprawdzają rejestrację i zgodność urządzeń w usłudze Intune. Rozwiązanie NAC obejmuje niektóre zachowania i współpracuje z dostępem warunkowym. Zobacz kroki umożliwiające rejestrację i uzyskaj listę rozwiązań partnerskich.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/25/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: aa7ecff7-8579-4009-8fd6-e17074df67de
ms.reviewer: tycast
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7b2083a493fd723c649bdfe2b709dbaa4c0ec663
ms.sourcegitcommit: 3ace4cba6e2f6fefa9120be3807387a49b200c9b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2019
ms.locfileid: "72810282"
---
# <a name="network-access-control-nac-integration-with-intune"></a>Integracja kontroli dostępu do sieci (NAC) z usługą Intune

Usługa Intune integruje się z partnerami kontroli dostępu do sieci (NAC, network access control), aby pomóc organizacjom w zabezpieczaniu danych firmowych, gdy urządzenia próbują uzyskać dostęp do zasobów lokalnych.

## <a name="how-do-intune-and-nac-solutions-help-protect-your-organization-resources"></a>Jak usługa Intune i rozwiązania NAC pomagają chronić zasoby organizacji?

Rozwiązania NAC sprawdzają stan rejestracji i zgodności urządzeń w usłudze Intune w celu podejmowania decyzji dotyczących kontroli dostępu. Jeśli urządzenie nie zostało zarejestrowane lub zostało zarejestrowane, ale nie jest zgodne z zasadami zgodności urządzeń usługi Intune, to urządzenie powinno zostać przekierowane do usługi Intune w celu rejestracji lub sprawdzenia zgodności urządzenia.

### <a name="example"></a>Przykład

Jeśli urządzenie zostało zarejestrowane i jest zgodne z usługą Intune, rozwiązanie NAC powinno zezwolić na dostęp urządzenia do zasobów firmy. Użytkownikom można na przykład zezwolić lub nie zezwolić na dostęp do zasobów firmowej sieci Wi-Fi lub VPN.

## <a name="feature-behaviors"></a>Zachowania funkcji

Urządzenia objęte aktywną synchronizacją z usługą Intune nie mogą przechodzić ze stanów **Zgodne** / **Niezgodne** na **Niezsynchronizowane** (lub **Nieznane**). Stan **Nieznane** jest zarezerwowany dla nowo zarejestrowanych urządzeń, które nie zostały jeszcze ocenione pod kątem zgodności.

W przypadku urządzeń z zablokowanym dostępem do zasobów usługa blokowania powinna przekierować wszystkich użytkowników do [portalu zarządzania](https://portal.manage.microsoft.com), aby ustalić, dlaczego urządzenie zostało zablokowane.  Gdy użytkownicy odwiedzą tę stronę, ich urządzenia zostaną synchronicznie ponownie ocenione pod kątem zgodności.

## <a name="nac-and-conditional-access"></a>Kontrola dostępu do sieci i dostęp warunkowy

Rozwiązanie NAC współpracuje z funkcją dostępu warunkowego w celu umożliwienia podejmowania decyzji dotyczących kontroli dostępu. Aby uzyskać więcej informacji, zobacz temat [Typowe sposoby korzystania z dostępu warunkowego przy użyciu usługi Intune](conditional-access-intune-common-ways-use.md).

## <a name="how-the-nac-integration-works"></a>Jak działa integracja NAC

Poniższa lista stanowi omówienie działania integracji kontroli dostępu do sieci w przypadku integracji z usługą Intune. W pierwszych trzech krokach (1–3) wyjaśniono proces dołączania. Po zintegrowaniu rozwiązania NAC z usługą Intune kroki 4–9 opisują bieżące działanie.

![Koncepcyjny obraz przedstawiający sposób współpracy rozwiązania NAC z usługą Intune](./media/network-access-control-integrate/ca-intune-common-ways-2.png)

1. Zarejestruj rozwiązanie partnerskie NAC za pomocą usługi Azure Active Directory (AAD) i przydziel uprawnienia delegowane do interfejsu API NAC usługi Intune.
2. Skonfiguruj rozwiązanie partnerskie NAC za pomocą odpowiednich ustawień z uwzględnieniem adresu URL odnajdowania usługi Intune.
3. Skonfiguruj rozwiązanie partnerskie NAC w celu uwierzytelnienia certyfikatu.
4. Użytkownik łączy się z punktem dostępu firmowej sieci Wi-Fi lub wysyła żądanie połączenia z siecią VPN.
5. Rozwiązanie partnerskie NAC przekazuje informacje o urządzeniu do usługi Intune i pyta usługę Intune o stan rejestracji i zgodności urządzenia.
6. Jeśli urządzenie nie jest zgodne lub nie zostało zarejestrowane, rozwiązanie partnerskie NAC instruuje użytkownika, aby zarejestrował urządzenie lub rozwiązał problem z jego zgodnością.
7. Urządzenie próbuje ponownie zweryfikować stan zgodności i rejestracji, gdy jest to konieczne.
8. Gdy urządzenie zostanie zarejestrowane i będzie zgodne, rozwiązanie partnerskie NAC pobiera ten stan z usługi Intune.
9. Połączenie jest pomyślnie ustanawiane, co umożliwia urządzeniu dostęp do zasobów firmy.

## <a name="use-nac-for-vpn-on-your-ios-devices"></a>Używanie kontroli dostępu do sieci VPN w urządzeniach z systemem iOS  

- Kontrola dostępu do sieci jest dostępna w następujących sieciach VPN bez włączania kontroli dostępu do sieci w profilu sieci VPN:

  - Kontrola dostępu do sieci dla starszej wersji programu Cisco AnyConnect
  - Starsza wersja programu F5 Access
  - Citrix VPN

- Kontrola dostępu do sieci jest również dostępna dla aplikacji Citrix SSO i F5 Access. Aby włączyć kontrolę dostępu do sieci dla aplikacji Citrix SSO:

  - Użyj rozwiązania Citrix Gateway 12.0.59 lub nowszego.  
  - Użytkownicy muszą mieć zainstalowaną aplikację Citrix SSO 1.1.6 lub nowszą.
  - [Zintegruj program NetScaler z usługą Intune na potrzeby rozwiązania NAC](https://docs.citrix.com/en-us/netscaler-gateway/12/microsoft-intune-integration/configuring-network-access-control-device-check-for-netscaler-gateway-virtual-server-for-single-factor-authentication-deployment.html) zgodnie z opisem w dokumentacji produktów firmy Citrix.
  - W profilu sieci VPN wybierz pozycję **Podstawowe ustawienia** > **Włącz kontrolę dostępu do sieci (NAC)** > wybierz pozycję **Zgadzam się**.

  Połączenie sieci VPN jest rozłączane co 24 godziny ze względów bezpieczeństwa. Połączenie z siecią VPN można od razu nawiązać ponownie.

- Aby włączyć kontrolę dostępu do sieci dla programu F5 Access:

  - Użyj systemu F5 BIG-IP 13.1.1.5. System BIG-IP 14 nie jest obsługiwany.
  - Zintegruj system BIG-IP z usługą Intune, aby móc korzystać z kontroli dostępu do sieci. Listę kroków można znaleźć w przewodniku firmy F5 [Overview: Configuring APM for device posture checks with endpoint management systems](https://support.f5.com/kb/en-us/products/big-ip_apm/manuals/product/apm-client-configuration-7-1-6/6.html#guid-0bd12e12-8107-40ec-979d-c44779a8cc89) (Omówienie: Konfigurowania programu APM pod kątem kontroli stanu urządzenia za pomocą systemów zarządzania punktem końcowym).
  - W profilu sieci VPN wybierz pozycję **Podstawowe ustawienia** > **Włącz kontrolę dostępu do sieci (NAC)** > wybierz pozycję **Zgadzam się**.

  Połączenie sieci VPN jest rozłączane co 24 godziny ze względów bezpieczeństwa. Połączenie z siecią VPN można od razu nawiązać ponownie.

- Kontrola dostępu do sieci nie jest obsługiwana dla następującego klienta sieci VPN w systemie iOS:
  - Cisco AnyConnect

Współpracujemy z naszymi partnerami, aby udostępnić rozwiązanie NAC dla nowszych klientów. Gdy rozwiązania będą gotowe, zaktualizujemy ten artykuł o dodatkowe informacje.

## <a name="next-steps"></a>Następne kroki

- [Integracja platformy Cisco ISE z usługą Intune](https://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html)
- [Integracja modułu Citrix NetScaler z usługą Intune](https://docs.citrix.com/en-us/netscaler-gateway/12/microsoft-intune-integration/configuring-network-access-control-device-check-for-netscaler-gateway-virtual-server-for-single-factor-authentication-deployment.html)
- [Integracja programu F5 BIG-IP Access Policy Manager z usługą Intune](https://support.f5.com/kb/en-us/products/big-ip_apm/manuals/product/apm-client-configuration-13-0-0/6.html)
- [Integracja rozwiązania HP Aruba ClearPass z usługą Intune](https://support.arubanetworks.com/Documentation/tabid/77/DMXModule/512/Command/Core_Download/Default.aspx?EntryId=31271)
- [Integracja rozwiązania Squadra security Removable Media Manager (secRMM) z usługą Intune](http://www.squadratechnologies.com/StaticContent/ProductDownload/secRMM/9.9.0.0/secRMMIntuneAccessControlSetupGuide.pdf)
