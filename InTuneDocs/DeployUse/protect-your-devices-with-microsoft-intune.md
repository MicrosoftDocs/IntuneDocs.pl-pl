---
# required metadata

title: Ochrona urządzeń za pomocą usługi Microsoft Intune | Microsoft Intune
description:
keywords:
author: Robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 71e0cbf3-2bfb-412e-8a12-8503df08b4cf

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Ochrona danych za pomocą usługi Microsoft Intune
Jeśli urządzenia są zarządzane przez usługę Intune, należy upewnić się, że są one chronione przed nieautoryzowanym dostępem i innymi zagrożeniami. Poniżej przedstawiono niektóre możliwości usługi Intune, które pomagają osiągnąć powyższe cele.

> [!TIP]
> W tym temacie nie opisano wszystkich sposobów, zabezpieczania urządzeń przy użyciu usługi Intune. Na przykład można użyć zasad usługi Intune w celu skonfigurowania wielu ustawień zabezpieczeń urządzeń, takich jak konfigurowanie hasła, ustawienia szyfrowania i funkcje sprzętu, takie jak Bluetooth i aparat urządzenia. Aby uzyskać dalsze informacje na temat tych ustawień, zobacz [Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

## Resetowanie kodów dostępu użytkowników z zablokowanym dostępem do urządzeń
Ponieważ pierwszym środkiem ochrony danych firmy na urządzeniach przenośnych jest wymaganie stosowania kodów dostępu do urządzenia, czasami trzeba [zresetować kod dostępu](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) lub umożliwić to pracownikowi przez usunięcie kodu dostępu albo zdalne ustawienie tymczasowego kodu dostępu. Możesz również [zdalnie zablokować urządzenie](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) w przypadku jego utraty lub kradzieży.

## Dodawanie dodatkowej warstwy ochrony do urządzeń z systemem Windows
[Usługa Multi-Factor Authentication (MFA)](protect-windows-devices-with-multi-factor-authentication.md) to bezpieczniejsza metoda uwierzytelniania użytkowników urządzeń z systemem Windows lub Windows Phone w sieci.  Uwierzytelnianie wieloskładnikowe wymaga potwierdzenia tożsamości użytkownika nie tylko przy użyciu nazwy użytkownika i hasła, ale też za pośrednictwem połączenia telefonicznego lub wiadomości SMS.

## Sterowanie ustawieniami usługi Microsoft Passport na urządzeniach z systemem Windows
Usługa Intune [umożliwia integrację z usługą Microsoft Passport dla miejsca pracy](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md), czyli alternatywną metodą logowania dla systemu Windows 10 i nowszych korzystającą z usługi Active Directory lub konta usługi Azure Active Directory w celu zastąpienia hasła, karty inteligentnej lub wirtualnej karty inteligentnej.

## Ochrona komputerów z systemem Windows zarządzanych za pomocą klienta usługi Intune
Usługa Intune w dalszym ciągu obsługuje zasady zabezpieczeń na komputerach z systemem Windows, które nie są rejestrowane, ale zarządzane przy użyciu oprogramowania klienckiego komputera z usługą Intune. Aby dowiedzieć się, jak przy użyciu tych zasad można zabezpieczyć komputery z systemem Windows, zobacz [Ochrona komputerów z systemem Windows z uruchomionym oprogramowaniem klienckim usługi Intune przy użyciu zasad](policies-to-protect-windows-pcs-in-microsoft-intune.md)..


<!--HONumber=May16_HO1-->


