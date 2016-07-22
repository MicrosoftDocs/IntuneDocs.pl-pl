---
# required metadata

title: Zapewnianie dostępu do zasobów firmy | Usługa Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3dd8dd4e-e165-4d0c-97b7-b3e86ebab909

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Zapewnianie dostępu do zasobów firmy przy użyciu usługi Microsoft Intune
Profile sieci Wi-Fi, sieci VPN i poczty e-mail w usłudze Microsoft Intune działają razem, ułatwiając użytkownikom uzyskiwanie dostępu do plików i zasobów potrzebnych im do skutecznej pracy, niezależnie od miejsca, w którym się znajdują. Profile certyfikatów ułatwiają zabezpieczanie dostępu.

## [Profile sieci Wi-Fi](wi-fi-connections-in-microsoft-intune.md) i obsługiwane platformy

Wdrażaj ustawienia sieci bezprzewodowej dla użytkowników. Wdrażając te ustawienia, można zminimalizować działania użytkowników końcowych wymagane w celu połączenia z siecią firmową.
#### Obsługiwane platformy

|Windows 8.1 i nowsze|System Windows Phone 8.1 lub nowszy|iOS|Android|Samsung KNOX|
|---------------------|---------------------------|---|-------|------------|
|Tak (można zaimportować profil Wi-Fi systemu Windows)|Tak (można skonfigurować identyfikator OMA-URI) |Tak|Tak|Tak|

## [Profile sieci VPN](vpn-connections-in-microsoft-intune.md) i obsługiwane platformy
Wdrażanie ustawień wirtualnej sieci prywatnej (VPN) dla użytkowników. Przez wdrożenie tych ustawień można zminimalizować nakład pracy użytkowników końcowych wymagany do nawiązywania połączeń z zasobami w sieci firmowej.

|Windows 8.1 i nowsze|System Windows Phone 8.1 lub nowszy|iOS|Android|Samsung KNOX|
|---------------------|---------------------------|---|-------|------------|
|Tak|Tak|Tak|Tak|Tak|

## [Profile poczty e-mail](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md) i obsługiwane platformy
Tworzenie, wdrażanie i monitorowanie ustawień natywnego klienta poczty e-mail na urządzeniach w organizacji.

|Windows 8.1 i nowsze|System Windows Phone 8.1 lub nowszy|iOS|Android|Samsung KNOX|
|---------------------|---------------------------|---|-------|------------|
|Nie|Tak|Tak|Nie|Tak|
> [!NOTE]
> [Ten wpis w blogu zespołu usługi Intune](http://blogs.technet.com/b/microsoftintune/archive/2015/02/23/using-oma-uri-to-create-custom-wi-fi-profiles-for-windows-phone-8-1.aspx) zawiera informacje dotyczące sposobu konfigurowania profilu sieci Wi-Fi systemu Windows Phone 8.1 przy użyciu identyfikatora OMA-URI.

## [Profile certyfikatów](secure-resource-access-with-certificate-profiles.md) i obsługiwane platformy
Ułatwienie bezpiecznego dostępu do zasobów firmowych z uwzględnieniem połączeń sieci bezprzewodowych i sieci VPN.

|Windows 8.1 i nowsze|System Windows Phone 8.1 lub nowszy|iOS|Android|Samsung KNOX|
|---------------------|---------------------------|---|-------|------------|
|Tak|Tak|Tak|Tak|Tak|


<!--HONumber=May16_HO1-->


