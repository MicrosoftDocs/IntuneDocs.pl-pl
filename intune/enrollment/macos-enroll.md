---
title: Konfigurowanie rejestracji dla urządzeń z systemem macOS
titleSuffix: Microsoft Intune
description: Informacje dotyczące rejestrowania urządzeń z systemem macOS w usłudze Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/14/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 684e9602e66842e26a7f8e233a8cee6db73f132d
ms.sourcegitcommit: 76ae5aea5deee7a590e24c3b2bb52f88125943e5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2019
ms.locfileid: "74098204"
---
# <a name="set-up-enrollment-for-macos-devices-in-intune"></a>Konfigurowanie rejestracji dla urządzeń z systemem macOS w usłudze Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Usługa Intune pozwala na zarządzanie urządzeniami z systemem macOS, aby zapewnić użytkownikom dostęp do aplikacji i poczty e-mail firmy.

Jako administrator usługi Intune możesz skonfigurować rejestrowanie dla urządzeń z systemem macOS należących do firmy oraz dla urządzeń osobistych z systemem macOS (przynieś swoje własne urządzenie — „bring your own device” czyli BYOD). 

## <a name="prerequisites"></a>Wymagania wstępne

Przed rozpoczęciem konfigurowania rejestracji urządzeń z systemem macOS należy spełnić następujące wymagania wstępne:

- [Upewnij się, że urządzenie kwalifikuje się programu Device Enrollment Program firmy Apple](https://support.apple.com/en-us/HT204142#eligibility).
- [Konfigurowanie domen](../fundamentals/custom-domain-name-configure.md)
- [Ustawienie urzędu zarządzania urządzeniami przenośnymi](../fundamentals/mdm-authority-set.md)
- [Tworzenie grup](../fundamentals/groups-add.md)
- [Skonfigurowanie aplikacji Portal firmy](../apps/company-portal-app.md)
- Przypisanie licencji użytkowników w [Centrum administracyjnym platformy Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Uzyskiwanie certyfikatu wypychania MDM firmy Apple](../enrollment/apple-mdm-push-certificate-get.md)

## <a name="user-owned-macos-devices-byod"></a>Urządzenia z systemem macOS należące do użytkownika (BYOD)

Możesz zezwolić użytkownikom na rejestrowanie własnych urządzeń osobistych w funkcji zarządzania usługi Intune. Ta strategia jest znana jako „bring your own device” (przynieś własne urządzenie) lub BYOD. Gdy wymagania wstępne zostaną spełnione, a licencje użytkowników przypisane, użytkownicy mogą zarejestrować swoje urządzenia przez:
- przejście do [witryny Portal firmy](https://portal.manage.microsoft.com) lub
- pobranie aplikacji Portal firmy dla komputerów Mac na stronie [aka.ms/EnrollMyMac](https://aka.ms/EnrollMyMac).

Możesz także wysłać im użytkownikom link do opisu kroków rejestracji online: [Rejestrowanie urządzenia z systemem macOS w usłudze Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos).

Aby uzyskać informacje o innych zadaniach użytkownika końcowego, zobacz następujące artykuły:

- [Zasoby dotyczące środowiska użytkownika końcowego w usłudze Microsoft Intune](../fundamentals/end-user-educate.md)
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

W przypadku oprogramowania Parallels Desktop należy ustawić typ sprzętu i numer seryjny dla maszyn wirtualnych, aby usługa Intune mogła je rozpoznać. Postępuj zgodnie z instrukcjami firmy Parallels dotyczącymi ustawiania typu sprzętu i [numeru seryjnego](http://kb.parallels.com/123455), aby skonfigurować wymagane ustawienia na potrzeby testowania. Zaleca się dopasowanie typu sprzętu urządzenia, na którym są uruchomione maszyny wirtualne, do typu sprzętu tworzonych maszyn wirtualnych. Ten typ sprzętu można znaleźć, wybierając kolejno **menu Apple** > **Informacje o tym Macu** > **Raport systemowy** > **Identyfikator modelu**. 

W przypadku oprogramowania VMware Fusion należy [edytować plik vmx](https://kb.vmware.com/s/article/1014782), aby ustawić model sprzętu i numer seryjny maszyny wirtualnej. Zaleca się dopasowanie typu sprzętu urządzenia, na którym są uruchomione maszyny wirtualne, do typu sprzętu tworzonych maszyn wirtualnych. Ten typ sprzętu można znaleźć, wybierając kolejno **menu Apple** > **Informacje o tym Macu** > **Raport systemowy** > **Identyfikator modelu**. 

## <a name="user-approved-enrollment"></a>Rejestracja zatwierdzona przez użytkownika
Rejestracja MDM zatwierdzona przez użytkownika to typ rejestracji w systemie macOS, którego można używać do zarządzania niektórymi ustawieniami istotnymi dla bezpieczeństwa. Aby uzyskać więcej informacji, zobacz [dokumentację pomocy technicznej firmy Apple](https://support.apple.com/HT208019).

Od listopada 2019 r. wszystkie nowe rejestracje urządzeń z systemem macOS należących do użytkownika będą zatwierdzane przez użytkowników, ponieważ użytkownik musi ręcznie zainstalować profil zarządzania w celu pomyślnego zarejestrowania. Podczas [procesu rejestracji](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos-cp) użytkownik zainstaluje profil zarządzania firmy Apple w obszarze **Preferencje systemowe** > **Profile**.  Instrukcje dotyczące instalacji profilu zarządzania są dostępne w aplikacji Portal firmy dla systemu macOS.

Urządzenia zarejestrowane przed listopadem 2019 r. mogą nie być zatwierdzane przez użytkownika, jeśli użytkownik nie zatwierdził ręcznie profilu zarządzania. Użytkownicy mogą jednak wrócić i zatwierdzić profil zarządzania, przechodząc do pozycji **Preferencje systemowe** > **Profile** i wybierając **profil zarządzania** > **Zatwierdź**.

### <a name="find-out-if-a-device-is-user-approved"></a>Sprawdzanie, czy urządzenie zostało zatwierdzone przez użytkownika
1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenie > **Sprzęt**.
3. Sprawdź pole **Rejestrowanie zatwierdzone przez użytkownika**.


## <a name="next-steps"></a>Następne kroki

Po zarejestrowaniu urządzeń z systemem macOS można [utworzyć ustawienia niestandardowe dla tych urządzeń](../configuration/custom-settings-macos.md).
