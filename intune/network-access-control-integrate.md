---
title: "Integracja kontroli dostępu do sieci z usługą Microsoft Intune"
titlesuffix: 
description: "Integracja kontroli dostępu do sieci (NAC) z usługą Intune"
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aa7ecff7-8579-4009-8fd6-e17074df67de
ms.reviewer: davidra
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6f54f04bc5a63c8a431eddaf4210fcb290942cc3
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/05/2018
---
# <a name="network-access-control-nac-integration-with-intune"></a>Integracja kontroli dostępu do sieci (NAC) z usługą Intune

Usługa Intune integruje się z partnerami kontroli dostępu do sieci (NAC, network access control), aby pomóc organizacjom w zabezpieczaniu danych firmowych, gdy urządzenia próbują uzyskać dostęp do zasobów lokalnych.

## <a name="how-do-intune-and-nac-solutions-help-protect-your-organization-resources"></a>Jak usługa Intune i rozwiązania NAC pomagają chronić zasoby organizacji?

Rozwiązania NAC są odpowiedzialne za sprawdzanie stanu rejestracji i zgodności urządzeń w usłudze Intune w celu podejmowania decyzji dotyczących kontroli dostępu. Jeśli urządzenie nie zostało zarejestrowane lub zostało zarejestrowane, ale nie jest zgodne z zasadami zgodności urządzeń usługi Intune, to urządzenie powinno zostać przekierowane do usługi Intune w celu rejestracji i/lub sprawdzenia zgodności urządzenia.

### <a name="example"></a>Przykład

Jeśli urządzenie zostało zarejestrowane i jest zgodne z usługą Intune, rozwiązanie NAC powinno zezwolić na dostęp urządzenia do zasobów firmy. Użytkownikom można na przykład zezwolić lub nie zezwolić na dostęp do zasobów firmowej sieci Wi-Fi lub VPN.

## <a name="feature-behaviors"></a>Zachowania funkcji

Urządzenia objęte aktywną synchronizacją z usługą Intune nie mogą przechodzić ze stanów **Zgodne** / **Niezgodne** na **Niezsynchronizowane** (lub **Nieznane**). Stan **Nieznane** jest zarezerwowany dla nowo zarejestrowanych urządzeń, które nie zostały jeszcze ocenione pod kątem zgodności.

W przypadku urządzeń z zablokowanym dostępem do zasobów usługa blokowania powinna przekierować wszystkich użytkowników do [portalu zarządzania](https://portal.manage.microsoft.com), aby ustalić, dlaczego urządzenie zostało zablokowane.  Gdy użytkownicy odwiedzą tę stronę, ich urządzenia zostaną synchronicznie ponownie ocenione pod kątem zgodności.

## <a name="nac-and-conditional-access"></a>Kontrola dostępu do sieci i dostęp warunkowy

Rozwiązanie NAC współpracuje z funkcją dostępu warunkowego w celu umożliwienia podejmowania decyzji dotyczących kontroli dostępu. Aby uzyskać więcej szczegółów, zobacz temat [Typowe sposoby korzystania z dostępu warunkowego przy użyciu usługi Intune](conditional-access-intune-common-ways-use.md).

## <a name="how-the-nac-integration-works"></a>Jak działa integracja NAC

Poniżej przedstawiono omówienie działania integracji kontroli dostępu do sieci w przypadku integracji z usługą Intune. W pierwszych trzech krokach (1–3) wyjaśniono proces dołączania. Po zintegrowaniu rozwiązania NAC z usługą Intune kroki 4–9 opisują bieżące działanie.

![Jak rozwiązanie NAC współpracuje z usługą Intune](./media/ca-intune-common-ways-2.png)

1. Zarejestruj rozwiązanie partnerskie NAC za pomocą usługi Azure Active Directory (AAD) i przydziel uprawnienia delegowane do interfejsu API NAC usługi Intune.
2. Skonfiguruj rozwiązanie partnerskie NAC za pomocą odpowiednich ustawień z uwzględnieniem adresu URL odnajdowania usługi Intune.
3. Skonfiguruj rozwiązanie partnerskie NAC w celu uwierzytelnienia certyfikatu.
4. Użytkownik łączy się z punktem dostępu firmowej sieci Wi-Fi lub wysyła żądanie połączenia z siecią VPN.
5. Rozwiązanie partnerskie NAC przekazuje informacje o urządzeniu do usługi Intune i pyta usługę Intune o stan rejestracji i zgodności urządzenia.
6. Jeśli urządzenie nie jest zgodne lub nie zostało zarejestrowane, rozwiązanie partnerskie NAC instruuje użytkownika, aby zarejestrował urządzenie lub rozwiązał problem z jego zgodnością.
7. Urządzenie próbuje ponownie zweryfikować stan zgodności i/lub rejestracji.
8. Gdy urządzenie zostanie zarejestrowane i będzie zgodne, rozwiązanie partnerskie NAC pobiera ten stan z usługi Intune.
9. Połączenie jest pomyślnie ustanawiane, co umożliwia urządzeniu dostęp do zasobów firmy.

## <a name="next-steps"></a>Następne kroki

- [Integracja platformy Cisco ISE z usługą Intune](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html)
- [Integracja modułu Citrix NetScaler z usługą Intune](http://docs.citrix.com/en-us/netscaler-gateway/12/microsoft-intune-integration/configuring-network-access-control-device-check-for-netscaler-gateway-virtual-server-for-single-factor-authentication-deployment.html)
- [Integracja rozwiązania HP Aruba Clear Pass z usługą Intune](https://support.arubanetworks.com/Documentation/tabid/77/DMXModule/512/Command/Core_Download/Default.aspx?EntryId=23757)
