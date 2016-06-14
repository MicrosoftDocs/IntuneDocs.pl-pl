---
# required metadata

title: Przygotowanie do rejestracji urządzeń w usłudze Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 44fd4af0-f9b0-493a-b590-7825139d9d40

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Przygotowanie do rejestracji urządzeń w usłudze Microsoft Intune
Aby umożliwić pracownikom zarejestrowanie urządzeń przenośnych w usłudze Intune (w tym urządzeń z systemami Android, iOS i Windows Phone oraz komputerów z systemem Windows), należy włączyć rejestrowanie urządzeń. Aby zezwolić na rejestrowanie, należy ustawić urząd zarządzania urządzeniami przenośnymi, skonfigurować Portal firmy usługi Intune, przypisać licencje i włączyć rejestrowanie dla platformy urządzeń.

## <a name="BKMK_Set_MDM_Authority"></a>Ustawianie urzędu zarządzania urządzeniami przenośnymi
Urząd zarządzania urządzeniami przenośnymi definiuje usługę zarządzania z uprawnieniami do zarządzania zestawem urządzeń. Opcje przeznaczone dla urzędu zarządzania urządzeniami przenośnymi obejmują samą usługę Intune oraz program Configuration Manager z usługą Intune. Jeśli program Configuration Manager zostanie ustawiony jako urząd zarządzania, do zarządzania urządzeniami przenośnymi nie można używać żadnej innej usługi.

>[!IMPORTANT]
> Starannie rozważ, czy chcesz zarządzać urządzeniami przenośnymi za pomocą samej usługi Intune (usługa online) czy przy użyciu programu System Center Configuration Manager z usługą Intune (rozwiązanie oprogramowania lokalnego w połączeniu z usługą online). Po ustawieniu urzędu zarządzania urządzeniami przenośnymi tego urzędu nie będzie można zmienić.



1.  W [konsoli administracyjnej usługi Microsoft Intune](http://manage.microsoft.com) kliknij pozycje **Administrator** &gt; **Zarządzanie urządzeniami przenośnymi**.

2.  Na liście **Zadania** kliknij pozycję **Ustaw urząd zarządzania urządzeniami przenośnymi**. Zostanie otwarte okno dialogowe **Ustawianie urzędu zarządzania urządzeniami przenośnymi** .

    ![Okno dialogowe Ustaw urząd MDM](../media/intune-mdm-authority.png)

3.  Usługa Intune zażąda potwierdzenia zamiaru ustawienia usługi Intune jako urzędu zarządzania urządzeniami przenośnymi. Zaznacz pole wyboru, a następnie kliknij przycisk **Tak** , aby zarządzać urządzeniami przenośnymi przy użyciu usługi Microsoft Intune.

## Konfigurowanie Portalu firmy usługi Intune i przypisywanie licencji
Portal firmy usługi Intune ułatwia użytkownikom dostęp do zasobów firmy, takich jak aplikacje, znajdowanie informacji pomocy technicznej, a także rejestrowanie i wyrejestrowywanie urządzeń. Przed rozpoczęciem rejestrowania urządzeń należy [skonfigurować Portal firmy](/intune/get-started/get-started-with-a-paid-subscription-to-microsoft-intune-step-7). Należy również [przypisać licencje użytkownikom](/intune/get-started/get-started-with-a-paid-subscription-to-microsoft-intune-step-4), aby zezwolić na dostęp do usługi Intune.

## Konfigurowanie zarządzania urządzeniami
Po skonfigurowaniu urzędu zarządzania urządzeniami przenośnymi należy skonfigurować zarządzanie urządzeniami dla systemów operacyjnych, które chce obsługiwać organizacja. Kroki wymagane do skonfigurowania zarządzania urządzeniami różnią się zależnie od systemu operacyjnego. Na przykład system operacyjny Android nie wymaga wykonywania żadnych czynności w konsoli administracyjnej usługi Intune. Jednak systemy Windows i iOS wymagają relacji zaufania między urządzeniami a usługą Intune, ponieważ tylko wówczas możliwe jest zarządzanie.

> [!div class="op_single_selector"]
- [Konfigurowanie zarządzania systemem Android przy użyciu usługi Microsoft Intune](set-up-android-management-with-microsoft-intune.md)
- [Set up iOS and Mac management with Microsoft Intune](set-up-ios-and-mac-management-with-microsoft-intune.md)
- [Konfigurowanie zarządzania systemem Windows Phone przy użyciu usługi Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md)
- [Konfigurowanie zarządzania urządzeniami z systemem Windows przy użyciu usługi Microsoft Intune](set-up-windows-device-management-with-microsoft-intune.md)

Możliwe jest również:
 - Używanie [konta menedżera rejestracji urządzeń](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) w celu rejestrowania wielu urządzeń
 - [Określanie urządzeń firmowych według numerów IMEI](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) w celu sprawniejszego rejestrowania urządzeń i zasad docelowych


<!--HONumber=May16_HO1-->


