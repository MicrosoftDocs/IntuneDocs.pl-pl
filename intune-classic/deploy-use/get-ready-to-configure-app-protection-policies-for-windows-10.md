---
title: Przygotowywanie do konfigurowania zasad ochrony aplikacji dla systemu Windows 10 | Dokumentacja firmy Microsoft
description: "Konfigurowanie dostawcy zarządzania aplikacjami mobilnymi (MAM) w usłudze Azure AD"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 04/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ebc7cfc8-40b9-47c2-8357-d392ebbb27c8
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: c48f9181e8fd740ab080a8620f3873909d0fd0f1
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---

# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a>Przygotowywanie do konfigurowania zasad ochrony aplikacji dla systemu Windows 10

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Przed utworzeniem zasad ochrony aplikacji systemu Windows 10 trzeba włączyć zarządzanie aplikacjami mobilnymi (MAM) dla systemu Windows 10 poprzez skonfigurowanie dostawcy MAM w usłudze Azure AD. Konfiguracja ta umożliwia definiowanie stanu rejestracji podczas tworzenia nowych zasad funkcji Windows Information Protection (WIP) za pomocą usługi Intune.

> [!NOTE]
> Stanem rejestracji może być albo MAM, albo zarządzanie urządzeniami przenośnymi (MDM).

## <a name="to-configure-the-mam-provider"></a>Aby skonfigurować dostawcę MAM

1.  Przejdź do witryny [Azure Portal](https://portal.azure.com/) i zaloguj się przy użyciu swoich poświadczeń usługi Intune.

2.  W menu po lewej stronie wybierz pozycję **Azure Active Directory**.

    ![Konfiguracja dostawcy MAM](../media/AppManagement/mam-provider-sc-1.png)

3.  Po otwarciu bloku **Azure AD** wybierz pozycję **Mobilność (zarządzanie urządzeniami przenośnymi i aplikacjami mobilnymi)**, a następnie kliknij pozycję **Microsoft Intune**.

    ![Mobilność (zarządzanie urządzeniami przenośnymi i aplikacjami mobilnymi)](../media/AppManagement/mam-provider-sc-2.png)

4.  Kiedy zostanie otwarty blok konfigurowania, najpierw wybierz pozycję **Przywróć domyślne adresy URL funkcji zarządzania aplikacjami przenośnymi**, a następnie skonfiguruj następujące opcje:

    a.  Zakres użytkownika funkcji zarządzania aplikacjami mobilnymi: funkcji MAM można użyć do ochrony danych firmowych dla określonej grupy użytkowników, którzy korzystają z urządzeń z systemem Windows 10, lub dla wszystkich użytkowników.

    b.  Adres URL warunków użytkowania usługi zarządzania aplikacjami mobilnymi: adres URL punktu końcowego warunków użytkowania usługi MAM. Służy do wyświetlania warunków użytkowania usługi MAM dla użytkowników końcowych.

    c.  Adres URL odnajdywania usługi zarządzania aplikacjami mobilnymi: ten adres URL jest wyszukiwany przez urządzenia, gdy muszą one zastosować zasady ochrony aplikacji.

    d.  Adres URL informacji o zgodności usługi zarządzania aplikacjami mobilnymi:

5.  Po skonfigurowaniu tych ustawień wybierz przycisk **Zapisz**.

## <a name="next-steps"></a>Następne kroki

[Tworzenie zasad ochrony aplikacji w funkcji WIP](/intune-classic/deploy-use/create-windows-information-protection-policy-with-intune)

