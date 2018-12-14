---
title: Konfigurowanie rejestracji dla urządzeń z systemem macOS
titlesuffix: Microsoft Intune
description: Informacje dotyczące rejestrowania urządzeń z systemem macOS w usłudze Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/13/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 7a54a72afb6052ed11566c2d2ada596ebde2159b
ms.sourcegitcommit: 5058dbfb0e224207dd4e7ca49712c6ad3434c83c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2018
ms.locfileid: "53112412"
---
# <a name="set-up-enrollment-for-macos-devices-in-intune"></a>Konfigurowanie rejestracji dla urządzeń z systemem macOS w usłudze Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Usługa Intune pozwala na zarządzanie urządzeniami z systemem macOS, aby zapewnić użytkownikom dostęp do aplikacji i poczty e-mail firmy.

Jako administrator usługi Intune możesz skonfigurować rejestrowanie dla urządzeń z systemem macOS należących do firmy oraz dla urządzeń osobistych z systemem macOS (przynieś swoje własne urządzenie — „bring your own device” czyli BYOD). 

## <a name="prerequisites"></a>Wymagania wstępne

Przed rozpoczęciem konfigurowania rejestracji urządzeń z systemem macOS należy spełnić następujące wymagania wstępne:

- [Konfigurowanie domen](custom-domain-name-configure.md)
- [Ustawienie urzędu zarządzania urządzeniami przenośnymi](mdm-authority-set.md)
- [Tworzenie grup](groups-add.md)
- [Skonfigurowanie aplikacji Portal firmy](company-portal-app.md)
- Przypisanie licencji użytkowników w [portalu usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Uzyskiwanie certyfikatu wypychania MDM firmy Apple](apple-mdm-push-certificate-get.md)

## <a name="user-owned-macos-devices-byod"></a>Urządzenia z systemem macOS należące do użytkownika (BYOD)

Możesz umożliwić użytkownikom rejestrowanie swoich urządzeń osobistych na potrzeby zarządzania w usłudze Intune — rozwiązanie to nazywa się „bring your own device”, czyli BYOD. Gdy wymagania wstępne zostaną spełnione, a licencje użytkowników przypisane, użytkownicy mogą zarejestrować swoje urządzenia przez:
- przejście do [witryny Portal firmy](https://portal.manage.microsoft.com) lub
- pobranie aplikacji Portal firmy.
Możesz także wysłać im link do opisu kroków rejestracji online: [Rejestrowanie urządzenia z systemem macOS w usłudze Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos).

Aby uzyskać informacje o innych zadaniach użytkownika końcowego, zobacz następujące artykuły:

- [Zasoby dotyczące środowiska użytkownika końcowego w usłudze Microsoft Intune](end-user-educate.md)
- [Korzystanie z urządzenia z systemem macOS w usłudze Intune](/intune-user-help/using-your-macos-device-with-intune)

## <a name="company-owned-macos-devices"></a>Urządzenia z systemem macOS należące do firmy
W przypadku organizacji, które kupują urządzenia dla swoich użytkowników, usługa Intune obsługuje następujące metody rejestracji urządzeń z systemem macOS należących do firmy:
- [Program Device Enrollment Program (DEP) firmy Apple](device-enrollment-program-enroll-macos.md): organizacje mogą zakupić urządzenia z systemem macOS za pośrednictwem programu Device Enrollment Program (DEP) firmy Apple. Program Device Enrollment Program umożliwia wdrożenie „na odległość” profilu rejestracji w celu zarządzania urządzeniami.
- [Menedżer rejestracji urządzeń (DEM, Device enrollment manager)](device-enrollment-manager-enroll.md): konto menedżera rejestracji urządzeń (DEM) umożliwia rejestrację do 1000 urządzeń.

## <a name="block-macos-enrollment"></a>Blokowanie rejestracji urządzeń z systemem macOS
Domyślnie usługa Intune zezwala na rejestrowanie urządzeń z systemem macOS. Aby zablokować rejestrowanie urządzeń z systemem macOS, zobacz [Ustawianie ograniczeń typu urządzeń](enrollment-restrictions-set.md).

## <a name="enroll-virtual-macos-machines-for-testing"></a>Rejestrowanie maszyn wirtualnych z systemem macOS na potrzeby testowania

> [!NOTE]
> Maszyny wirtualne z systemem macOS są obsługiwane tylko na potrzeby testowania. Nie należy używać maszyn wirtualnych z systemem macOS jako urządzeń produkcyjnych dla użytkowników końcowych. 

Maszyny wirtualne z systemem macOS można zarejestrować na potrzeby testowania przy użyciu oprogramowania Parallels Desktop lub VMware Fusion. 

W przypadku oprogramowania Parallels Desktop należy ustawić typ sprzętu i numer seryjny dla maszyn wirtualnych, aby usługa Intune mogła je rozpoznać. Postępuj zgodnie z instrukcjami firmy Parallels dotyczącymi [ustawiania typu sprzętu](http://kb.parallels.com/123594) i [numeru seryjnego](http://kb.parallels.com/123455), aby skonfigurować wymagane ustawienia na potrzeby testowania. Zaleca się dopasowanie typu sprzętu urządzenia, na którym są uruchomione maszyny wirtualne, do typu sprzętu tworzonych maszyn wirtualnych. Ten typ sprzętu można znaleźć, wybierając kolejno **menu Apple** > **Informacje o tym Macu** > **Raport systemowy** > **Identyfikator modelu**. 

W przypadku oprogramowania VMware Fusion należy [edytować plik vmx](https://kb.vmware.com/s/article/1014782), aby ustawić model sprzętu i numer seryjny maszyny wirtualnej. Zaleca się dopasowanie typu sprzętu urządzenia, na którym są uruchomione maszyny wirtualne, do typu sprzętu tworzonych maszyn wirtualnych. Ten typ sprzętu można znaleźć, wybierając kolejno **menu Apple** > **Informacje o tym Macu** > **Raport systemowy** > **Identyfikator modelu**. 

## <a name="user-approved-enrollment"></a>Rejestracja zatwierdzona przez użytkownika

Rejestracja MDM zatwierdzona przez użytkownika to typ rejestracji w systemie macOS, którego można używać do zarządzania niektórymi ustawieniami istotnymi dla bezpieczeństwa. Aby uzyskać więcej informacji, zobacz [dokumentację pomocy technicznej firmy Apple](https://support.apple.com/HT208019).

W celu uzyskania zatwierdzenia użytkownika użytkownik końcowy musi — po zarejestrowaniu przy użyciu Portalu firmy dla systemu macOS — ręcznie przeprowadzić zatwierdzanie przy użyciu preferencji systemowych. Instrukcje dotyczące wykonywania tej czynności są dostępne w aplikacji Portal firmy dla systemu macOS dla użytkowników systemu macOS w wersji 10.13.2 i nowszych.

Aby sprawdzić, czy urządzenie zostało zatwierdzone przez użytkownika, przejdź do portalu usługi Intune, a następnie wybierz kolejno pozycje **Urządzenia** > **Wszystkie urządzenia**> wybierz urządzenie > **Sprzęt**. Zaznacz pole **Zatwierdzone przez użytkownika**.

## <a name="next-steps"></a>Następne kroki

Po zarejestrowaniu urządzeń z systemem macOS można [utworzyć ustawienia niestandardowe dla tych urządzeń](custom-settings-macos.md).
