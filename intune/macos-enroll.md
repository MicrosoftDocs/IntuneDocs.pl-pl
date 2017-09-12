---
title: "Rejestrowanie urządzeń z systemem macOS w usłudze Intune"
titlesuffix: Azure portal
description: "Informacje o rejestrowaniu urządzeń z systemem macOS w usłudze Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bdf29fdc9c7098572ca9f06a65dc23320f7a08fb
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/09/2017
---
# <a name="enroll-macos-devices-in-intune"></a>Rejestrowanie urządzeń z systemem macOS w usłudze Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Usługa Intune umożliwia zarządzanie urządzeniami z systemem macOS. Aby włączyć zarządzanie urządzeniami, użytkownicy muszą zarejestrować swoje urządzenia, przechodząc do [witryny internetowej Portal firmy](http://portal.manage.microsoft.com) i postępując zgodnie z wyświetlanymi instrukcjami. Po dodaniu urządzeń z systemem macOS do zarządzania można [utworzyć ustawienia niestandardowe dla tych urządzeń](custom-settings-macos.md). Wkrótce będzie dostępnych więcej możliwości.

## <a name="prerequisites"></a>Wymagania wstępne

Przed rozpoczęciem konfigurowania rejestracji urządzeń z systemem macOS należy spełnić następujące wymagania wstępne:

- [Skonfigurowanie domen](custom-domain-name-configure.md)
- [Ustawienie urzędu zarządzania urządzeniami przenośnymi](mdm-authority-set.md)
- [Tworzenie grup](https://docs.microsoft.com/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [Skonfigurowanie aplikacji Portal firmy](company-portal-app.md)
- Przypisanie licencji użytkowników w [portalu usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Uzyskiwanie certyfikatu wypychania MDM firmy Apple](apple-mdm-push-certificate-get.md)

## <a name="set-up-macos-enrollment"></a>Konfigurowanie rejestracji urządzeń z systemem macOS

Domyślnie usługa Intune zezwala na rejestrację urządzeń z systemem macOS.

Aby zablokować rejestrowanie urządzeń z systemem macOS, zobacz [Ustawianie ograniczeń typu urządzeń](enrollment-restrictions-set.md).

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Poinformuj użytkowników, jak mogą zarejestrować swoje urządzenia w celu uzyskania dostępu do zasobów firmy

Musisz poinformować użytkowników końcowych, aby przeszli do [witryny internetowej Portalu firmy](http://portal.manage.microsoft.com) i postępowali zgodnie z instrukcjami, aby zarejestrować swoje urządzenia. Możesz także wysłać im link do kroków rejestracji online: [Rejestrowanie urządzenia z systemem macOS w usłudze Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos).

Aby uzyskać informacje o innych zadaniach użytkownika końcowego, zobacz następujące artykuły:

- [Zasoby dotyczące środowiska użytkownika końcowego w usłudze Microsoft Intune](end-user-educate.md)
- [Korzystanie z urządzenia z systemem iOS lub macOS i usługi Intune](https://docs.microsoft.com/intune-user-help/using-your-ios-or-mac-os-x-device-with-intune)
