---
title: "Integracja kontroli dostępu do sieci z usługą Intune"
titleSuffix: Intune on Azure
description: "Integracja kontroli dostępu do sieci (NAC) z usługą Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aa7ecff7-8579-4009-8fd6-e17074df67de
ms.reviewer: davidra
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6037ec4638b487c0bae8fcecf2d9bd010e3bc59a
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/03/2017
---
# <a name="network-access-control-nac-integration-with-intune"></a>Integracja kontroli dostępu do sieci (NAC) z usługą Intune

Usługa Intune integruje się z partnerami kontroli dostępu do sieci (NAC, network access control), aby pomóc organizacjom w zabezpieczaniu danych firmowych, gdy urządzenia próbują uzyskać dostęp do zasobów lokalnych.

## <a name="how-do-intune-and-nac-solutions-help-protect-your-organization-resources"></a>Jak usługa Intune i rozwiązania NAC pomagają chronić zasoby organizacji?

Rozwiązania NAC są odpowiedzialne za sprawdzanie stanu rejestracji i zgodności urządzeń w usłudze Intune w celu podejmowania decyzji dotyczących kontroli dostępu. Jeśli urządzenie nie zostało zarejestrowane lub zostało zarejestrowane, ale nie jest zgodne z zasadami zgodności urządzeń usługi Intune, to urządzenie powinno zostać przekierowane do usługi Intune w celu rejestracji i/lub sprawdzenia zgodności urządzenia.

### <a name="example"></a>Przykład

Jeśli urządzenie zostało zarejestrowane i jest zgodne z usługą Intune, rozwiązanie NAC powinno zezwolić na dostęp urządzenia do zasobów firmy. Użytkownikom można na przykład zezwolić lub nie zezwolić na dostęp do zasobów firmowej sieci Wi-Fi lub VPN.

## <a name="nac-and-conditional-access"></a>Kontrola dostępu do sieci i dostęp warunkowy

Rozwiązania NAC współpracują z rozwiązaniami dostępu warunkowego w celu zapewnienia decyzji dotyczących kontroli dostępu.

- Zobacz [Typowe sposoby korzystania z dostępu warunkowego przy użyciu usługi Intune](conditional-access-intune-common-ways-use.md), aby uzyskać więcej szczegółów.

## <a name="how-the-nac-integration-works"></a>Jak działa integracja NAC

Poniżej przedstawiono omówienie działania integracji NAC z usługą Intune. Trzy pierwsze kroki objaśniają proces dołączania. Po zintegrowaniu rozwiązania NAC z usługą Intune kroki 4–9 opisują bieżące działanie.

![Jak rozwiązanie NAC współpracuje z usługą Intune](./media/ca-intune-common-ways-2.png)

1.  Zarejestruj rozwiązanie partnerskie NAC za pomocą usługi Azure Active Directory (AAD) i przydziel uprawnienia delegowane do interfejsu API NAC usługi Intune.

2.  Skonfiguruj rozwiązanie partnerskie NAC za pomocą odpowiednich ustawień z uwzględnieniem adresu URL odnajdowania usługi Intune.

3.  Skonfiguruj rozwiązanie partnerskie NAC w celu uwierzytelnienia certyfikatu.

4.  Użytkownik łączy się z punktem dostępu firmowej sieci Wi-Fi lub wysyła żądanie połączenia z siecią VPN.

5.  Rozwiązanie partnerskie NAC przekazuje informacje o urządzeniu do usługi Intune i pyta usługę Intune o stan rejestracji i zgodności urządzenia.

6.  Jeśli urządzenie nie jest zgodne lub nie zostało zarejestrowane, rozwiązanie partnerskie NAC instruuje użytkownika, aby zarejestrował urządzenie lub rozwiązał problem z jego zgodnością.

7.  Urządzenie próbuje ponownie zweryfikować swój stan zgodności i/lub rejestracji.

8.  Gdy urządzenie zostanie zarejestrowane i będzie zgodne, rozwiązanie partnerskie NAC pobiera ten stan z usługi Intune.

9.  Połączenie jest pomyślnie ustanawiane, co umożliwia urządzeniu dostęp do zasobów firmy.

## <a name="next-steps"></a>Następne kroki

-   [Integracja platformy Cisco ISE z usługą Intune](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html)

-   [Integracja modułu Citrix NetScaler z usługą Intune](https://docs.citrix.com/netscaler-gateway/11-1/microsoft-intune-integration/configuring-network-access-control-device-check-for-netscaler-gateway-virtual-server-for-single-factor-authentication-deployment.html)

-   [Integracja rozwiązania HP Aruba Clear Pass z usługą Intune](https://support.arubanetworks.com/Documentation/tabid/77/DMXModule/512/Command/Core_Download/Default.aspx?EntryId=23757)
