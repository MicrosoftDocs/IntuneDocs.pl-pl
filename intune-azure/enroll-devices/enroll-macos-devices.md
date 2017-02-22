---
title: "Rejestrowanie urządzeń z systemem macOS w usłudze Intune | Wersja zapoznawcza usługi Intune Azure | Dokumentacja firmy Microsoft"
description: "Wersja zapoznawcza usługi Intune Azure: informacje o sposobie rejestrowania urządzeń z systemem macOS w wersji zapoznawczej usługi Intune Azure."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 1/3/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ba2affcdbcdfcd690d671c7b20f9d1e14a74f764
ms.openlocfilehash: 171175689adca027181f3da4d05222117de97e13


---

# <a name="enroll-macos-devices-in-intune-azure-preview"></a>Rejestrowanie urządzeń z systemem macOS w wersji zapoznawczej usługi Intune Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Jako administrator usługi Intune możesz zarządzać urządzeniami z systemem macOS. Portal usługi Azure domyślnie umożliwia użytkownikom rejestrowanie ich urządzeń z systemem macOS. Wystarczy poinformować użytkowników o możliwości przejścia do [witryny sieci Web portalu firmy](http://portal.manage.microsoft.com) i zarejestrowania urządzeń z systemem macOS. 

## <a name="prerequisites"></a>Wymagania wstępne

Przed rozpoczęciem konfigurowania rejestracji urządzeń z systemem macOS należy spełnić następujące wymagania wstępne:

- [Skonfigurowanie domen](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [Ustawienie urzędu zarządzania urządzeniami przenośnymi](set-mdm-authority.md)
- [Tworzenie grup](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [Skonfigurowanie aplikacji Portal firmy](/intune-azure/manage-apps/company-portal-app.md)
- Przypisanie licencji użytkowników w [portalu usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Uzyskiwanie certyfikatu wypychania MDM firmy Apple](get-an-apple-mdm-push-certificate.md)

## <a name="set-up-macos-enrollment"></a>Konfigurowanie rejestracji urządzeń z systemem macOS

Usługa Intune jest domyślnie skonfigurowana w taki sposób, aby zezwalać na rejestrację urządzeń z systemem macOS. 

Aby wyświetlić ustawienia zezwalające na rejestrację urządzeń z systemem macOS lub blokujące możliwość ich rejestracji, przejdź do bloku Intune w portalu usługi Azure, a następnie wybierz kolejno pozycje **Rejestracja** > **Ograniczenia rejestracji**. 

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Poinformuj użytkowników, jak mogą zarejestrować swoje urządzenia w celu uzyskania dostępu do zasobów firmy

Instrukcje dotyczące rejestrowania przez użytkownika końcowego można znaleźć w artykule [Enroll your macOS device in Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-macos) (Rejestrowanie urządzenia z systemem macOS w usłudze Intune). W trakcie procesu rejestracji użytkownicy są informowani, czego mogą oczekiwać, a także co administratorzy IT mogą i czego nie mogą wyświetlać na swoich urządzeniach.

Aby uzyskać informacje o innych zadaniach użytkownika końcowego, zobacz następujące artykuły:

- [Zasoby dotyczące środowiska użytkownika końcowego w usłudze Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)
- [Korzystanie z urządzenia z systemem iOS lub macOS i usługi Intune](https://docs.microsoft.com/intune/enduser/using-your-ios-or-mac-os-x-device-with-intune)


<!--HONumber=Feb17_HO1-->


