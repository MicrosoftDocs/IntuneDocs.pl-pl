---
title: Konfigurowanie rejestracji dla urządzeń z systemem macOS
titlesuffix: Microsoft Intune
description: Informacje dotyczące rejestrowania urządzeń z systemem macOS w usłudze Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c1fb846dc65ee14315edf7b9ba15e0e24998a3a2
ms.sourcegitcommit: 21db583d6a9d3c15a8a8ee5579309dff1cfe1f8b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/16/2018
---
# <a name="set-up-enrollment-for-macos-devices-in-intune"></a>Konfigurowanie rejestracji dla urządzeń z systemem macOS w usłudze Intune

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

## <a name="user-owned-ios-devices-byod"></a>Urządzenia z systemem iOS należące do użytkownika (BYOD)

Możesz umożliwić użytkownikom rejestrowanie swoich urządzeń osobistych na potrzeby zarządzania w usłudze Intune — rozwiązanie to nazywa się „bring your own device”, czyli BYOD. Gdy ukończysz wymagania wstępne i przypiszesz użytkownikom licencje, użytkownicy muszą pobrać aplikację Portal firmy dla systemu macOS ze sklepu App Store i postępować zgodnie z instrukcjami w aplikacji dotyczącymi rejestrowania.

## <a name="company-owned-ios-devices"></a>Urządzenia z systemem iOS należące do firmy
W przypadku organizacji, które kupują urządzenia dla swoich użytkowników, usługa Intune obsługuje rejestrację urządzeń z systemem macOS należących do firmy przy użyciu konta [menedżera rejestracji urządzeń](device-enrollment-manager-enroll.md).

## <a name="set-up-macos-enrollment"></a>Konfigurowanie rejestracji urządzeń z systemem macOS

Domyślnie usługa Intune zezwala na rejestrację urządzeń z systemem macOS.

Aby zablokować rejestrowanie urządzeń z systemem macOS, zobacz [Ustawianie ograniczeń typu urządzeń](enrollment-restrictions-set.md).

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Poinformuj użytkowników, jak mogą zarejestrować swoje urządzenia w celu uzyskania dostępu do zasobów firmy

Poinformuj użytkowników końcowych, aby przeszli do [witryny Portalu firmy](https://portal.manage.microsoft.com) i wykonali instrukcje dotyczące rejestracji urządzeń. Możesz także wysłać im link do kroków rejestracji online: [Rejestrowanie urządzenia z systemem macOS w usłudze Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos).

Aby uzyskać informacje o innych zadaniach użytkownika końcowego, zobacz następujące artykuły:

- [Zasoby dotyczące środowiska użytkownika końcowego w usłudze Microsoft Intune](end-user-educate.md)
- [Korzystanie z urządzenia z systemem macOS w usłudze Intune](/intune-user-help/using-your-macos-device-with-intune)

## <a name="enroll-virtual-macos-machines-for-testing"></a>Rejestrowanie maszyn wirtualnych z systemem macOS na potrzeby testowania

> [!NOTE]
> Maszyny wirtualne z systemem macOS są obsługiwane tylko na potrzeby testowania. Nie należy używać maszyn wirtualnych z systemem macOS jako urządzeń produkcyjnych dla użytkowników końcowych. 

Maszyny wirtualne z systemem macOS można zarejestrować na potrzeby testowania przy użyciu oprogramowania Parallels Desktop lub VMware Fusion. 

W przypadku oprogramowania Parallels Desktop należy ustawić typ sprzętu i numer seryjny dla maszyn wirtualnych, aby usługa Intune mogła je rozpoznać. Postępuj zgodnie z instrukcjami firmy Parallels dotyczącymi [ustawiania typu sprzętu](http://kb.parallels.com/123594) i [numeru seryjnego](http://kb.parallels.com/123455), aby skonfigurować wymagane ustawienia na potrzeby testowania. Zaleca się dopasowanie typu sprzętu urządzenia, na którym są uruchomione maszyny wirtualne, do typu sprzętu tworzonych maszyn wirtualnych. Ten typ sprzętu można znaleźć, wybierając kolejno **menu Apple** > **Informacje o tym Macu** > **Raport systemowy** > **Identyfikator modelu**. 

W przypadku oprogramowania VMware Fusion należy [edytować plik vmx](https://kb.vmware.com/s/article/1014782), aby ustawić model sprzętu i numer seryjny maszyny wirtualnej. Zaleca się dopasowanie typu sprzętu urządzenia, na którym są uruchomione maszyny wirtualne, do typu sprzętu tworzonych maszyn wirtualnych. Ten typ sprzętu można znaleźć, wybierając kolejno **menu Apple** > **Informacje o tym Macu** > **Raport systemowy** > **Identyfikator modelu**. 
