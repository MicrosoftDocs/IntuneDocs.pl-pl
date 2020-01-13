---
title: Używanie numeru PIN do logowania się do urządzeń z systemem Windows 10 za pomocą usługi Microsoft Intune — Azure | Microsoft Docs
description: Użyj funkcji Windows Hello dla firm, aby zezwolić użytkownikom na logowanie do urządzeń przy użyciu numeru PIN, odcisku palca i innych opcji. Utwórz profil konfiguracji ochrony tożsamości w usłudze Intune dla urządzeń z systemem Windows 10 urządzenia przy użyciu tych ustawień i przypisz profil do grup użytkowników i grup urządzeń.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/18/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a4f5d3a232cab25c60189132732a0ea3f347c74a
ms.sourcegitcommit: 107fef144013b01ed768ca8973373f9cb3f0f7dc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/06/2020
ms.locfileid: "75683803"
---
# <a name="use-windows-hello-for-business-on-windows-10-devices-with-microsoft-intune"></a>Korzystanie z funkcji Windows Hello dla firm na urządzeniach z systemem Windows 10 z usługą Microsoft Intune

Funkcja Windows Hello dla firm to metoda logowania do urządzeń z systemem Windows przez zastępowanie haseł, kart inteligentnych i wirtualnych kart inteligentnych. Usługa Intune oferuje wbudowane ustawienia, dzięki którym administratorzy mogą konfigurować funkcję Windows Hello dla firm i jej używać. Tych ustawień można na przykład używać w celu:

- Włączania funkcji Windows Hello dla firm dla urządzeń i użytkowników
- Ustawiania wymagań dotyczących numeru PIN urządzenia, w tym minimalnej i maksymalnej długości numeru PIN
- Zezwalania na gesty, takie jak odcisk palca, których użytkownicy mogą (lub nie mogą) używać do logowania się na urządzeniach

Ta funkcja ma zastosowanie do urządzenia z systemem:

- Windows 10 lub nowszym
- Windows 10 Mobile
- Windows Holographic for Business

„Profile konfiguracji” są używane w usłudze Intune do tworzenia i dostosowywania tych ustawień na potrzeby organizacji. Po dodaniu tych funkcji w profilu należy wypchnąć lub wdrożyć te ustawienia do grup użytkowników i urządzeń w organizacji.

W tym artykule przedstawiono sposób tworzenia profilu konfiguracji urządzenia. Listę wszystkich ustawień i ich zadań można znaleźć w temacie [Windows 10 device settings to enable Windows Hello for Business](identity-protection-windows-settings.md) (Ustawienia urządzeń z systemem Windows 10 służące do włączania funkcji Windows Hello dla firm).

## <a name="create-the-device-profile"></a>Tworzenie profilu urządzenia

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Wybierz pozycję **Urządzenia** > **Profile konfiguracji** > **Utwórz profil**.

3. Wprowadź następujące właściwości:

   - **Nazwa**: Wprowadź opisową nazwę nowego profilu.
   - **Opis**: Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
   - **Platforma**: Wybierz pozycję **Windows 10 i nowsze**. Usługa Windows Hello dla firm jest obsługiwana tylko na urządzeniach z systemem Windows 10 lub nowszym.
   - **Typ profilu**: wybierz pozycję **Identity protection**.

4. W okienku *Windows Hello dla firm* skonfiguruj następujące opcje:

   - **Skonfiguruj usługę Windows Hello dla firm**: wybierz sposób konfigurowania usługi Windows Hello dla firm:

     - **Nieskonfigurowane** (wartość domyślna): [aprowizuje usługę Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-how-it-works-provisioning) na urządzeniu. Podczas przypisywania profilów ochrony tożsamości tylko do użytkowników wartością domyślną kontekstu urządzenia jest **Nieskonfigurowane**.

     - **Wyłączone**: wybierz tę opcję, jeśli nie chcesz używać usługi Windows Hello dla firm. Ta opcja powoduje wyłączenie usługi Windows Hello dla firm dla wszystkich użytkowników.

     - **Włączone**: wybierz tę opcję, aby przeprowadzać [aprowizowanie](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-how-it-works-provisioning), i skonfiguruj ustawienia usługi Windows Hello dla firm w usłudze Intune. wprowadź ustawienia, które chcesz skonfigurować. Listę wszystkich ustawień i ich zadań można znaleźć w temacie [Windows 10 device settings to enable Windows Hello for Business](identity-protection-windows-settings.md) (Ustawienia urządzeń z systemem Windows 10 służące do włączania funkcji Windows Hello dla firm).

   - **Użyj kluczy zabezpieczeń do logowania się**: włącz klucz zabezpieczeń funkcji Windows Hello jako poświadczenie logowania dla wszystkich komputerów w dzierżawie.

     - **Włączenie**
     - **Nie skonfigurowano** (wartość domyślna)

5. Po zakończeniu wybierz kolejno pozycje **OK** > **Utwórz**, aby zapisać zmiany.

Profil został utworzony i wyświetlony na liście profilów. Następnie [przypisz](../configuration/device-profile-assign.md) ten profil do grup użytkowników i urządzeń stosownie do potrzeb.

> [!IMPORTANT]
> Aby umożliwić aprowizowanie wielu użytkowników na urządzeniu, należy określić, że zasady usługi Windows Hello dla firm mają być stosowane do urządzeń. Jeśli zasady są stosowane tylko do użytkowników, na urządzeniu można aprowizować tylko jednego użytkownika.

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/identity-protection-configure/disable-android-camera.png)

-->

## <a name="next-steps"></a>Następne kroki

- Zapoznaj się z listą wszystkich [ustawień i ich zadaniami](identity-protection-windows-settings.md).
- [Przypisywanie profilu](../configuration/device-profile-assign.md) i [monitorowanie jego stanu](../configuration/device-profile-monitor.md).
