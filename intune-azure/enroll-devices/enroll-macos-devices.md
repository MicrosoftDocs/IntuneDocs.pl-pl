---
title: "Rejestrowanie urządzeń z systemem macOS w usłudze Intune"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: informacje o sposobie rejestrowania urządzeń z systemem macOS w wersji zapoznawczej usługi Intune Azure."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 63ac5ecf6fbe9ae66c879466c7785b051dfb7a61
ms.lasthandoff: 02/18/2017


---

# <a name="enroll-macos-devices-in-intune-azure-preview"></a>Rejestrowanie urządzeń z systemem macOS w wersji zapoznawczej usługi Intune Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Usługa Intune umożliwia zarządzanie urządzeniami z systemem macOS. Aby włączyć zarządzanie urządzeniami, użytkownicy muszą zarejestrować swoje urządzenia, przechodząc do [witryny internetowej Portal firmy](http://portal.manage.microsoft.com) i postępując zgodnie z wyświetlanymi instrukcjami. Po dodaniu urządzeń z systemem macOS do zarządzania można [utworzyć ustawienia niestandardowe dla tych urządzeń](https://docs.microsoft.com/intune-azure/configure-devices/custom-for-macos). Wkrótce będzie dostępnych więcej możliwości.

## <a name="prerequisites"></a>Wymagania wstępne

Przed rozpoczęciem konfigurowania rejestracji urządzeń z systemem macOS należy spełnić następujące wymagania wstępne:

- [Skonfigurowanie domen](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [Ustawienie urzędu zarządzania urządzeniami przenośnymi](set-mdm-authority.md)
- [Tworzenie grup](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [Skonfigurowanie aplikacji Portal firmy](/intune-azure/manage-apps/company-portal-app.md)
- Przypisanie licencji użytkowników w [portalu usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Uzyskiwanie certyfikatu wypychania MDM firmy Apple](get-an-apple-mdm-push-certificate.md)

## <a name="set-up-macos-enrollment"></a>Konfigurowanie rejestracji urządzeń z systemem macOS

Domyślnie usługa Intune zezwala na rejestrację urządzeń z systemem macOS. 

Aby zablokować rejestrowanie urządzeń z systemem macOS, zobacz [Ustawianie ograniczeń typu urządzeń](https://docs.microsoft.com/intune-azure/enroll-devices/set-enrollment-restrictions#set-device-type-restrictions). 

Aby ustawić maksymalną liczbę urządzeń, które użytkownik może zarejestrować, zobacz [Ustawianie ograniczeń limitu urządzeń](https://docs.microsoft.com/intune-azure/enroll-devices/set-enrollment-restrictions#set-device-limit-restrictions).

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Poinformuj użytkowników, jak mogą zarejestrować swoje urządzenia w celu uzyskania dostępu do zasobów firmy

Musisz poinformować użytkowników końcowych, aby przeszli do [witryny internetowej Portalu firmy](http://portal.manage.microsoft.com) i postępowali zgodnie z instrukcjami, aby zarejestrować swoje urządzenia. Możesz także wysłać im link do kroków rejestracji online: [Rejestrowanie urządzenia z systemem macOS w usłudze Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-macos). 

Aby uzyskać informacje o innych zadaniach użytkownika końcowego, zobacz następujące artykuły:

- [Zasoby dotyczące środowiska użytkownika końcowego w usłudze Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)
- [Korzystanie z urządzenia z systemem iOS lub macOS i usługi Intune](https://docs.microsoft.com/intune/enduser/using-your-ios-or-mac-os-x-device-with-intune)
