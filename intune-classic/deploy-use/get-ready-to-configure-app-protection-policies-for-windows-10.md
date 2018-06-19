---
title: Przygotowywanie do konfigurowania zasad ochrony aplikacji dla systemu Windows 10
description: Konfigurowanie dostawcy zarządzania aplikacjami mobilnymi (MAM) w usłudze Azure AD
keywords: ''
author: mattbriggs
ms.author: mabrigg
manager: dougeby
ms.date: 04/18/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ebc7cfc8-40b9-47c2-8357-d392ebbb27c8
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9b91d3740ead5815974d7ffee67c15b7769b0210
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
ms.locfileid: "31025556"
---
# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a>Przygotowywanie do konfigurowania zasad ochrony aplikacji dla systemu Windows 10

[!INCLUDE [note for both-portals](../includes/note-for-both-portals.md)]

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
