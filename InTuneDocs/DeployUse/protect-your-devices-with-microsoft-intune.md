---
title: "Ochrona urządzeń | Microsoft Intune"
description: "Poznaj sposoby, za pomocą których usługa Intune chroni urządzenia przed nieautoryzowanym dostępem i innymi zagrożeniami."
keywords: 
author: Robstackmsft
manager: angrobe
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71e0cbf3-2bfb-412e-8a12-8503df08b4cf
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6716a3d1fb53dc3de0189f637d5664d0a2023d05
ms.openlocfilehash: 2b33330f8ec8b46e3b4c6886463e8d3588410ab7


---

# Ochrona danych za pomocą usługi Microsoft Intune
Jeśli urządzenia są zarządzane przez usługę Intune, należy upewnić się, że są one chronione przed nieautoryzowanym dostępem i innymi zagrożeniami. Poniżej przedstawiono niektóre możliwości usługi Intune, które pomagają osiągnąć powyższe cele.

> [!TIP]
> W tym temacie nie opisano wszystkich sposobów zabezpieczania urządzeń przy użyciu usługi Intune. Na przykład można użyć zasad usługi Intune w celu skonfigurowania wielu ustawień zabezpieczeń urządzeń, takich jak dotyczące hasła, szyfrowania i funkcji sprzętu, takich jak połączenia Bluetooth i aparat urządzenia. Aby uzyskać dalsze informacje na temat tych ustawień, zobacz [Manage settings and features on your devices with Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) (Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu usługi Microsoft Intune).

## Resetowanie kodów dostępu użytkowników z zablokowanym dostępem do urządzeń
Ponieważ pierwszym środkiem ochrony danych firmy na urządzeniach przenośnych jest wymaganie stosowania kodów dostępu do urządzenia, czasami trzeba [zresetować kod dostępu](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) lub umożliwić to pracownikowi przez usunięcie kodu dostępu albo zdalne ustawienie tymczasowego kodu dostępu. Możesz również [zdalnie zablokować urządzenie](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) w przypadku jego utraty lub kradzieży.

## Dodawanie kolejnej warstwy ochrony dla urządzeń z systemem Windows
[Uwierzytelnianie wieloskładnikowe](protect-windows-devices-with-multi-factor-authentication.md) to bezpieczniejsza metoda uwierzytelniania użytkowników urządzeń z systemem Windows lub Windows Phone w sieci.  Uwierzytelnianie wieloskładnikowe wymaga potwierdzenia tożsamości użytkownika nie tylko przy użyciu nazwy użytkownika i hasła, ale też za pośrednictwem połączenia telefonicznego lub wiadomości SMS.

## Sterowanie ustawieniami usługi Microsoft Passport na urządzeniach z systemem Windows
Usługa Intune umożliwia integrację z usługą [Microsoft Passport for Work](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md), czyli alternatywną metodę logowania dla systemu Windows 10 i nowszych korzystającą z usługi Active Directory lub konta usługi Azure Active Directory w celu zastąpienia hasła, karty inteligentnej lub wirtualnej karty inteligentnej.

## Obchodzenie blokady aktywacji na urządzeniach z systemem iOS
Blokada aktywacji to funkcja, która ułatwia ochronę urządzeń użytkowników. Wymaga podania identyfikatora firmy Apple i hasła przed wymazaniem lub ponownym aktywowaniem urządzenia. Jednak może to prowadzić do problemów, na przykład jeśli użytkownik opuści firmę bez usunięcia blokady. [Funkcja pominięcia blokady aktywacji systemu iOS](help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune.md) umożliwia usunięcie blokady z nadzorowanych urządzeń z systemem iOS, pozwalając na ich ponowne przydzielenie lub skasowanie.

## Ochrona komputerów z systemem Windows zarządzanych za pomocą klienta usługi Intune
Usługa Intune w dalszym ciągu obsługuje zasady zabezpieczeń na komputerach z systemem Windows, które nie są rejestrowane, ale zarządzane przy użyciu oprogramowania klienckiego komputera z usługą Intune. Aby dowiedzieć się, jak przy użyciu tych zasad można zabezpieczyć komputery z systemem Windows, zobacz [Use policies to help protect Windows PCs that run the Intune client software](policies-to-protect-windows-pcs-in-microsoft-intune.md) (Ochrona komputerów z systemem Windows z uruchomionym oprogramowaniem klienckim usługi Intune przy użyciu zasad).



<!--HONumber=Jul16_HO4-->


