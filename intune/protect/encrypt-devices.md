---
title: Szyfrowanie urządzeń za pomocą metody szyfrowania obsługiwanej przez platformy
titleSuffix: Microsoft Intune
description: Szyfruj urządzenia za pomocą wbudowanych metod szyfrowania, takich jak BitLocker lub FileVault, oraz zarządzaj kluczami odzyskiwania dla tych szyfrowanych urządzeń z poziomu portalu usługi Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: annovich
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 5209ce7fba30a156de055503751104f9090d49d7
ms.sourcegitcommit: e7052114324b80d0503b107c934bb90b8eb29704
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/08/2020
ms.locfileid: "75756000"
---
# <a name="use-device-encryption-with-intune"></a>Szyfrowanie urządzeń w usłudze Intune

Zarządzaj szyfrowaniem wbudowanych dysków lub napędów urządzeń za pomocą usługi Intune w celu ochrony danych na tych urządzeniach.

Skonfiguruj szyfrowanie dysków jako część profilu konfiguracji urządzenia na potrzeby ochrony punktu końcowego. Usługa Intune obsługuje następujące platformy i technologie szyfrowania:

- macOS: FileVault
- Windows 10 lub nowszy: Funkcja BitLocker

Usługa Intune udostępnia również wbudowany [raport szyfrowania](encryption-monitor.md), który przedstawia szczegółowe informacje o stanie szyfrowania urządzeń na wszystkich urządzeniach zarządzanych.

## <a name="filevault-encryption-for-macos"></a>Szyfrowanie za pomocą programu FileVault w systemie macOS

Za pomocą usługi Intune można skonfigurować szyfrowanie dysków za pomocą programu FileVault na urządzeniach z systemem macOS. Następnie, korzystając z raportu szyfrowania usługi Intune, można wyświetlić szczegóły szyfrowania dla tych urządzeń i zarządzać kluczami odzyskiwania dla urządzeń zaszyfrowanych za pomocą programu FileVault.

Pamiętaj, że rejestracja urządzeń zatwierdzonych przez użytkownika jest wymagana, aby program FileVault działał w urządzeniu. Użytkownik musi ręcznie zatwierdzić profil zarządzania z preferencji systemu, aby rejestracja została uznana za zatwierdzoną przez użytkownika. 

FileVault to program do szyfrowania całych dysków, który jest dołączony do systemu macOS. Za pomocą usługi Intune można skonfigurować program FileVault na urządzeniach z systemem **macOS 10.13 lub nowszym**.

Aby skonfigurować narzędzie FileVault, utwórz [profil konfiguracji urządzenia](../configuration/device-profile-create.md) na potrzeby ochrony punktu końcowego na platformie macOS. Ustawienia programu FileVault są jedną z dostępnych kategorii ustawień ochrony punktu końcowego w systemie macOS.

Po utworzeniu zasad służących do szyfrowania urządzeń za pomocą programu FileVault te zasady są stosowane do urządzeń w dwóch etapach. Najpierw urządzenie jest przygotowywane, aby umożliwić usłudze Intune pobranie klucza odzyskiwania i utworzenie jego kopii zapasowej. Jest to nazywane deponowaniem. Po zdeponowaniu klucza można uruchomić szyfrowanie dysku.

![Ustawienia programu FileVault](./media/encrypt-devices/filevault-settings.png)

Aby uzyskać szczegółowe informacje na temat ustawień programu FileVault, którymi można zarządzać za pomocą usługi Intune, zobacz sekcję [FileVault](endpoint-protection-macos.md#filevault) w artykule dotyczącym ustawień ochrony punktu końcowego w usłudze Intune w systemie macOS.

### <a name="how-to-configure-macos-filevault"></a>Jak skonfigurować program FileVault w systemie macOS

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Wybierz pozycję **Urządzenia** > **Profile konfiguracji** > **Utwórz profil**.

3. Ustaw następujące opcje:

   - Platforma: macOS
   - Typ profilu: Program Endpoint Protection

4. Wybierz pozycję **Ustawienia** > **FileVault**.

5. Dla pozycji *FileVault* wybierz opcję **Włącz**.

6. Jako *Typ klucza odzyskiwania* obsługiwany jest tylko **Klucz prywatny**.

   Rozważ dodanie komunikatu, aby ułatwić użytkownikom końcowym pobieranie klucza odzyskiwania dla swojego urządzenia. Te informacje mogą być przydatne dla użytkowników końcowych, jeśli korzystasz z ustawienia „Wymiana osobistego klucza odzyskiwania” umożliwiającego automatyczne okresowe generowanie nowego klucza odzyskiwania dla urządzenia.

   Przykład: Aby pobrać zgubiony lub ostatnio obrócony klucz odzyskiwania, zaloguj się do witryny internetowej Intune — Portal firmy z dowolnego urządzenia. W portalu przejdź do pozycji *Urządzenia* i wybierz urządzenie z włączonym programem FileVault, a następnie wybierz pozycję *Pobierz klucz odzyskiwania*. Zostanie wyświetlony bieżący klucz odzyskiwania.

7. Skonfiguruj pozostałe [ustawienia programu FileVault](endpoint-protection-macos.md#filevault), aby spełniały Twoje potrzeby biznesowe, a następnie wybierz przycisk **OK**.

  8. Ukończ konfigurację dodatkowych ustawień, a następnie zapisz profil.  

### <a name="manage-filevault"></a>Zarządzanie programem FileVault

Po zaszyfrowaniu przez usługę Intune urządzenia z systemem macOS za pomocą programu FileVault można wyświetlać klucze odzyskiwania programu FileVault i zarządzać nimi z poziomu [raportu szyfrowania](encryption-monitor.md) usługi Intune.

Gdy usługa Intune zaszyfruje urządzenie z systemem macOS za pomocą programu FileVault, możesz wyświetlić osobisty klucz odzyskiwania tego urządzenia w internetowej aplikacji Portal firmy na dowolnym urządzeniu. W aplikacji internetowej Portal firmy wybierz zaszyfrowane urządzenie z systemem macOS, a następnie wybierz pozycję „Pobierz klucz odzyskiwania” jako akcję urządzenia zdalnego.

### <a name="retrieve-personal-recovery-key-from-mem-encrypted-macos-devices"></a>Pobieranie osobistego klucza odzyskiwania z urządzeń z systemem macOS zaszyfrowanych przy użyciu programu MEM

Użytkownicy końcowi będą mogli pobrać osobisty klucz odzyskiwania (klucz FileVault) przy użyciu aplikacji Portal firmy dla systemu iOS. Urządzenie, które ma osobisty klucz odzyskiwania, musi zostać zarejestrowane w usłudze Intune i zaszyfrowane za pomocą usługi FileVault w usłudze Intune. Korzystając z aplikacji Portal firmy dla systemu iOS, użytkownik końcowy może otworzyć stronę internetową zawierającą osobisty klucz odzyskiwania usługi FileVault. Możesz również pobrać klucz odzyskiwania z usługi Intune, wybierając pozycję **Urządzenia** > *zaszyfrowane i zarejestrowane urządzenie z systemem macOS* > **Pobierz klucz odzyskiwania**. 

## <a name="bitlocker-encryption-for-windows-10"></a>Szyfrowanie funkcją BitLocker dla systemu Windows 10

Za pomocą usługi Intune można skonfigurować szyfrowanie dysków funkcją BitLocker na urządzeniach z systemem Windows 10. Następnie, korzystając z raportu szyfrowania usługi Intune, można wyświetlić szczegóły szyfrowania dla tych urządzeń. Można również uzyskać dostęp do ważnych informacji dotyczących funkcji BitLocker z urządzeń, które korzystają z usługi Azure Active Directory (Azure AD).

Funkcja BitLocker jest dostępna na urządzeniach z systemem **Windows 10 lub nowszym**.

Funkcję BitLocker należy skonfigurować podczas tworzenia [profilu konfiguracji urządzenia](../configuration/device-profile-create.md) na potrzeby ochrony punktu końcowego na platformie Windows 10 lub nowszej. Ustawienia funkcji BitLocker znajdują się w kategorii ustawień szyfrowania systemu Windows dla ochrony punktu końcowego w systemie Windows 10.

![Ustawienia funkcji BitLocker](./media/encrypt-devices/bitlocker-settings.png)

### <a name="how-to-configure-windows-10-bitlocker"></a>Jak skonfigurować funkcję BitLocker w systemie Windows 10

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Wybierz pozycję **Urządzenia** > **Profile konfiguracji** > **Utwórz profil**.

3. Ustaw następujące opcje:

   - Platforma: Windows 10 lub nowszym
   - Typ profilu: Program Endpoint Protection

4. Wybierz pozycję **Ustawienia** > **Szyfrowanie systemu Windows**.

5. Skonfiguruj ustawienia funkcji BitLocker, aby spełniały Twoje potrzeby biznesowe, a następnie wybierz przycisk **OK**.

6. Ukończ konfigurację dodatkowych ustawień, a następnie zapisz profil.

### <a name="manage-bitlocker"></a>Zarządzanie funkcją BitLocker

Po zaszyfrowaniu przez usługę Intune urządzenia z systemem Windows 10 za pomocą funkcji BitLocker można wyświetlać klucze odzyskiwania funkcji BitLocker i zarządzać nimi z poziomu [raportu szyfrowania](encryption-monitor.md) usługi Intune.

### <a name="rotate-bitlocker-recovery-keys"></a>Rotacja kluczy odzyskiwania funkcji BitLocker

Za pomocą akcji urządzenia usługi Intune można zdalnie dokonać rotacji klucza odzyskiwania funkcji BitLocker urządzenia z systemem Windows 10 w wersji 1909 lub nowszej.

#### <a name="prerequisites"></a>Wymagania wstępne

Aby obsłużyć rotację klucza odzyskiwania funkcji BitLocker, urządzenia muszą spełniać następujące wymagania wstępne:

- Na urządzeniach musi działać system Windows 10 w wersji 1909 lub nowszej.

- Urządzenia przyłączone do usługi Azure AD i dołączone hybrydowo muszą mieć włączoną obsługę rotacji kluczy:

  - **Inicjowana przez klienta rotacja hasła odzyskiwania**

  To ustawienie znajduje się w obszarze *Szyfrowanie systemu Windows* w ramach zasad konfiguracji urządzenia dla ochrony punktu końcowego w systemie Windows 10.
  
#### <a name="to-rotate-the-bitlocker-recovery-key"></a>Aby dokonać rotacji klucza odzyskiwania funkcji BitLocker

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Wybierz pozycję **Urządzenia** > **Wszystkie urządzenia**.

3. Z listy zarządzanych urządzeń wybierz urządzenie, wybierz pozycję **Więcej**, a następnie wybierz akcję zdalną urządzenia **Rotacja klucza odzyskiwania funkcji BitLocker**.

## <a name="next-steps"></a>Następne kroki

Utwórz zasady [zgodności urządzenia](compliance-policy-create-windows.md).

Raport szyfrowanie umożliwia zarządzanie następującymi elementami:

- [Klucze odzyskiwania funkcji BitLocker](encryption-monitor.md#bitlocker-recovery-keys)
- [Klucze odzyskiwania programu FileVault](encryption-monitor.md#filevault-recovery-keys)

Zapoznaj się z ustawieniami szyfrowania, które można skonfigurować za pomocą usługi Intune dla funkcji:

- [BitLocker](endpoint-protection-windows-10.md#windows-encryption)
- [FileVault](endpoint-protection-macos.md#filevault)
