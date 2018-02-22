---
title: "Rejestrowanie urządzeń z systemem macOS w usłudze Intune"
titlesuffix: Azure portal
description: "Informacje o rejestrowaniu urządzeń z systemem macOS w usłudze Intune."
keywords: 
author: ErikjeMS
ms.author: erikje
nmanager: dougeby
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f896ebd51f989c0e441043d320247946cdb8997b
ms.sourcegitcommit: 9bd6278d129fa29f184b2d850138f8f65f3674ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/09/2018
---
# <a name="enroll-macos-devices-in-intune"></a>Rejestrowanie urządzeń z systemem macOS w usłudze Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Usługa Intune umożliwia zarządzanie urządzeniami z systemem macOS. Aby włączyć zarządzanie urządzeniami, użytkownicy muszą zarejestrować swoje urządzenia, przechodząc do [witryny internetowej Portal firmy](http://portal.manage.microsoft.com) i postępując zgodnie z wyświetlanymi instrukcjami. Po dodaniu urządzeń z systemem macOS do zarządzania można [utworzyć ustawienia niestandardowe dla tych urządzeń](custom-settings-macos.md). Wkrótce będzie dostępnych więcej możliwości.

## <a name="prerequisites"></a>Wymagania wstępne

Przed rozpoczęciem konfigurowania rejestracji urządzeń z systemem macOS należy spełnić następujące wymagania wstępne:

- [Konfigurowanie domen](custom-domain-name-configure.md)
- [Ustawienie urzędu zarządzania urządzeniami przenośnymi](mdm-authority-set.md)
- [Tworzenie grup](https://docs.microsoft.com/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [Skonfigurowanie aplikacji Portal firmy](company-portal-app.md)
- Przypisanie licencji użytkowników w [portalu usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Uzyskiwanie certyfikatu wypychania MDM firmy Apple](apple-mdm-push-certificate-get.md)

## <a name="set-up-macos-enrollment"></a>Konfigurowanie rejestracji urządzeń z systemem macOS

Domyślnie usługa Intune zezwala na rejestrację urządzeń z systemem macOS.

Aby zablokować rejestrowanie urządzeń z systemem macOS, zobacz [Ustawianie ograniczeń typu urządzeń](enrollment-restrictions-set.md).

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Poinformuj użytkowników, jak mogą zarejestrować swoje urządzenia w celu uzyskania dostępu do zasobów firmy

Poinformuj użytkowników końcowych, aby przeszli do [witryny Portalu firmy](http://portal.manage.microsoft.com) i wykonali instrukcje dotyczące rejestracji urządzeń. Możesz także wysłać im link do kroków rejestracji online: [Rejestrowanie urządzenia z systemem macOS w usłudze Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos).

Aby uzyskać informacje o innych zadaniach użytkownika końcowego, zobacz następujące artykuły:

- [Zasoby dotyczące środowiska użytkownika końcowego w usłudze Microsoft Intune](end-user-educate.md)
- [Korzystanie z urządzenia z systemem macOS w usłudze Intune](/intune-user-help/using-your-macos-device-with-intune)
