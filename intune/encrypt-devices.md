---
title: Szyfrowanie urządzeń w usłudze Microsoft Intune przy użyciu metod szyfrowania obsługiwanych przez platformy
titleSuffix: Microsoft Intune
description: Szyfruj urządzenia za pomocą wbudowanych metod szyfrowania, takich jak BitLocker lub FileVault, oraz zarządzaj kluczami odzyskiwania dla tych szyfrowanych urządzeń z poziomu portalu usługi Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 08/02/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: annovich
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: b7c76439b734837b5a4dd7e5fdbba5d21d0681d7
ms.sourcegitcommit: ec22a186a9cfa489a8490698e387624e480892d8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/13/2019
ms.locfileid: "68960424"
---
# <a name="use-device-encryption-with-intune"></a>Szyfrowanie urządzeń w usłudze Intune  

Zarządzaj szyfrowaniem wbudowanych dysków lub napędów urządzeń za pomocą usługi Intune w celu ochrony danych na tych urządzeniach.  

Skonfiguruj szyfrowanie dysków jako część profilu konfiguracji urządzenia na potrzeby ochrony punktu końcowego. Usługa Intune obsługuje następujące platformy i technologie szyfrowania:  
- macOS: FileVault   
- Windows 10 lub nowszy: Funkcja BitLocker  

Usługa Intune udostępnia również wbudowany [raport szyfrowania](encryption-monitor.md), który przedstawia szczegółowe informacje o stanie szyfrowania urządzeń na wszystkich urządzeniach zarządzanych.  

## <a name="filevault-encryption-for-macos"></a>Szyfrowanie za pomocą programu FileVault w systemie macOS  

Za pomocą usługi Intune można skonfigurować szyfrowanie dysków za pomocą programu FileVault na urządzeniach z systemem macOS. Następnie, korzystając z raportu szyfrowania usługi Intune, można wyświetlić szczegóły szyfrowania dla tych urządzeń i zarządzać kluczami odzyskiwania dla urządzeń zaszyfrowanych za pomocą programu FileVault.  

FileVault to program do szyfrowania całych dysków, który jest dołączony do systemu macOS. Za pomocą usługi Intune można skonfigurować program FileVault na urządzeniach z systemem **macOS 10.13 lub nowszym**.  

Aby skonfigurować narzędzie FileVault, utwórz [profil konfiguracji urządzenia](device-profile-create.md) na potrzeby ochrony punktu końcowego na platformie macOS. Ustawienia programu FileVault są jedną z dostępnych kategorii ustawień ochrony punktu końcowego w systemie macOS.  

Po utworzeniu zasad służących do szyfrowania urządzeń za pomocą programu FileVault te zasady są stosowane do urządzeń w dwóch etapach. Najpierw urządzenie jest przygotowywane, aby umożliwić usłudze Intune pobranie klucza odzyskiwania i utworzenie jego kopii zapasowej. Jest to nazywane deponowaniem. Po zdeponowaniu klucza można uruchomić szyfrowanie dysku.

![Ustawienia programu FileVault](./media/encrypt-devices/filevault-settings.png)

Aby uzyskać szczegółowe informacje na temat ustawień programu FileVault, którymi można zarządzać za pomocą usługi Intune, zobacz sekcję [FileVault](endpoint-protection-macos.md#filevault) w artykule dotyczącym ustawień ochrony punktu końcowego w usłudze Intune w systemie macOS.  

### <a name="how-to-configure-macos-filevault"></a>Jak skonfigurować program FileVault w systemie macOS 

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) i przejdź do pozycji **Konfiguracja urządzenia** > **Profile** > **Utwórz profil**.  

2. Ustaw następujące opcje:  

   - Platforma: macOS  
   - Typ profilu: Program Endpoint Protection  

3. Wybierz pozycję **Ustawienia** > **FileVault**.  

4. Dla pozycji *FileVault* wybierz opcję **Włącz**.  

5. Jako *Typ klucza odzyskiwania* obsługiwany jest tylko **Klucz prywatny**.  

   Rozważ dodanie komunikatu, aby ułatwić użytkownikom końcowym pobieranie klucza odzyskiwania dla swojego urządzenia. Te informacje mogą być przydatne dla użytkowników końcowych, jeśli korzystasz z ustawienia „Wymiana osobistego klucza odzyskiwania” umożliwiającego automatyczne okresowe generowanie nowego klucza odzyskiwania dla urządzenia.  

   Przykład: Aby pobrać zgubiony lub ostatnio obrócony klucz odzyskiwania, zaloguj się do witryny internetowej Intune — Portal firmy z dowolnego urządzenia. W portalu przejdź do pozycji *Urządzenia* i wybierz urządzenie z włączonym programem FileVault, a następnie wybierz pozycję *Pobierz klucz odzyskiwania*. Zostanie wyświetlony bieżący klucz odzyskiwania.  

6. Skonfiguruj pozostałe [ustawienia programu FileVault](endpoint-protection-macos.md#filevault), aby spełniały Twoje potrzeby biznesowe, a następnie wybierz przycisk **OK**.  

   > [!IMPORTANT]  
   > Istnieje znany problem, gdy dla ustawienia **Wyłącz monit przy wylogowywaniu** zostanie ustawiona wartość *Włączone*. Gdy zostanie ustawiona wartość *Włączone*, dla ustawienia **Liczba dozwolonych pominięć** należy ustawić wartość i nie może ona wynosić *Nieskonfigurowane*. Jeśli zostanie ustawiona wartość *Nieskonfigurowane*, profil nie będzie działać na urządzeniu. W tym scenariuszu urządzenie raportuje **Podsumowanie stanu profilu** jako **Błąd** bez dalszych szczegółów.
   > 
   > Gdy ustawienie **Wyłącz monit przy wylogowywaniu** ma wartość *Nieskonfigurowane*, dla ustawienia **Liczba dozwolonych pominięć** można ustawić opcję *Nieskonfigurowane* lub może ono mieć wartość.  
   > 
   > Ten problem zostanie rozwiązany w przyszłej aktualizacji. 

7. Ukończ konfigurację dodatkowych ustawień, a następnie zapisz profil.  

### <a name="manage-filevault"></a>Zarządzanie programem FileVault  

Po zaszyfrowaniu przez usługę Intune urządzenia z systemem macOS za pomocą programu FileVault można wyświetlać klucze odzyskiwania programu FileVault i zarządzać nimi z poziomu [raportu szyfrowania](encryption-monitor.md) usługi Intune.  

## <a name="bitlocker-encryption-for-windows-10"></a>Szyfrowanie funkcją BitLocker dla systemu Windows 10  

Za pomocą usługi Intune można skonfigurować szyfrowanie dysków funkcją BitLocker na urządzeniach z systemem Windows 10. Następnie, korzystając z raportu szyfrowania usługi Intune, można wyświetlić szczegóły szyfrowania dla tych urządzeń. Można również uzyskać dostęp do ważnych informacji dotyczących funkcji BitLocker z urządzeń, które korzystają z usługi Azure Active Directory (Azure AD).  

Funkcja BitLocker jest dostępna na urządzeniach z systemem **Windows 10 lub nowszym**.  

Funkcję BitLocker należy skonfigurować podczas tworzenia [profilu konfiguracji urządzenia](device-profile-create.md) na potrzeby ochrony punktu końcowego na platformie Windows 10 lub nowszej. Ustawienia funkcji BitLocker znajdują się w kategorii ustawień szyfrowania systemu Windows dla ochrony punktu końcowego w systemie Windows 10.    

![Ustawienia funkcji BitLocker](./media/encrypt-devices/bitlocker-settings.png) 

### <a name="how-to-configure-windows-10-bitlocker"></a>Jak skonfigurować funkcję BitLocker w systemie Windows 10  

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) i przejdź do pozycji Konfiguracja urządzenia > Profile > Utwórz profil.  

2. Ustaw następujące opcje:  
   - Platforma: System Windows 10 lub nowszy  
   - Typ profilu: Program Endpoint Protection  

3. Wybierz pozycję **Ustawienia** > **Szyfrowanie systemu Windows**.

4. Skonfiguruj ustawienia funkcji BitLocker, aby spełniały Twoje potrzeby biznesowe, a następnie wybierz przycisk **OK**.  

5. Ukończ konfigurację dodatkowych ustawień, a następnie zapisz profil.  

### <a name="manage-bitlocker"></a>Zarządzanie funkcją BitLocker  

Po zaszyfrowaniu przez usługę Intune urządzenia z systemem Windows 10 za pomocą funkcji BitLocker można wyświetlać klucze odzyskiwania funkcji BitLocker i zarządzać nimi z poziomu [raportu szyfrowania](encryption-monitor.md) usługi Intune.  

## <a name="next-steps"></a>Następne kroki  

Tworzenie zasad [zgodności urządzenia](compliance-policy-create-windows.md)  

Raport szyfrowanie umożliwia zarządzanie następującymi elementami:  
- [Klucze odzyskiwania funkcji BitLocker](encryption-monitor.md#bitlocker-recovery-keys)
- [Klucze odzyskiwania programu FileVault](encryption-monitor.md#filevault-recovery-keys)

Zapoznaj się z ustawieniami szyfrowania, które można skonfigurować za pomocą usługi Intune dla funkcji:  
- [BitLocker](endpoint-protection-windows-10.md#windows-encryption)  
- [FileVault](endpoint-protection-macos.md#filevault)  
 
 
