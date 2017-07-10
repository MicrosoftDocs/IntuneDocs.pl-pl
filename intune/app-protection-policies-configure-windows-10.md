---
title: Przygotowywanie do konfigurowania zasad ochrony aplikacji dla systemu Windows 10
titleSuffix: Intune on Azure
description: "Konfigurowanie dostawcy zarządzania aplikacjami mobilnymi (MAM) w usłudze Azure AD"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 949fddec-5318-4c9a-957e-ea260e6e05be
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bf56d3a80f0d167baa95e9dfdb20d08e02590984
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2017
---
# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a>Przygotowywanie do konfigurowania zasad ochrony aplikacji dla systemu Windows 10

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Przed utworzeniem zasad ochrony aplikacji systemu Windows 10 trzeba włączyć zarządzanie aplikacjami mobilnymi (MAM) dla systemu Windows 10 poprzez skonfigurowanie dostawcy MAM w usłudze Azure AD. Konfiguracja ta umożliwia definiowanie stanu rejestracji podczas tworzenia nowych zasad funkcji Windows Information Protection (WIP) za pomocą usługi Intune.

> [!NOTE]
> Stanem rejestracji może być albo MAM, albo zarządzanie urządzeniami przenośnymi (MDM).

## <a name="to-configure-the-mam-provider"></a>Aby skonfigurować dostawcę MAM

1.  Przejdź do witryny [Azure Portal](https://portal.azure.com/) i zaloguj się przy użyciu swoich poświadczeń usługi Intune.

2.  W menu po lewej stronie wybierz pozycję **Azure Active Directory**.

    ![Konfiguracja dostawcy MAM](./media/mam-provider-sc-1.png)

3.  Po otwarciu bloku **Azure AD** wybierz pozycję **Mobilność (zarządzanie urządzeniami przenośnymi i aplikacjami mobilnymi)**, a następnie kliknij pozycję **Microsoft Intune**.

    ![Mobilność (zarządzanie urządzeniami przenośnymi i aplikacjami mobilnymi)](./media/mam-provider-sc-1.png)

4.  Kiedy zostanie otwarty blok konfigurowania, najpierw wybierz pozycję **Przywróć domyślne adresy URL funkcji zarządzania aplikacjami przenośnymi**, a następnie skonfiguruj następujące opcje:

    a.  Zakres użytkownika funkcji zarządzania aplikacjami mobilnymi: funkcji MAM można użyć do ochrony danych firmowych dla określonej grupy użytkowników, którzy korzystają z urządzeń z systemem Windows 10, lub dla wszystkich użytkowników.

    b.  Adres URL warunków użytkowania usługi zarządzania aplikacjami mobilnymi: adres URL punktu końcowego warunków użytkowania usługi MAM. Służy do wyświetlania warunków użytkowania usługi MAM dla użytkowników końcowych.

    c.  Adres URL odnajdywania usługi zarządzania aplikacjami mobilnymi: ten adres URL jest wyszukiwany przez urządzenia, gdy muszą one zastosować zasady ochrony aplikacji.

    d.  Adres URL informacji o zgodności usługi zarządzania aplikacjami mobilnymi:

5.  Po skonfigurowaniu tych ustawień wybierz przycisk **Zapisz**.

## <a name="next-steps"></a>Następne kroki

[Tworzenie zasad ochrony aplikacji w funkcji WIP](windows-information-protection-policy-create.md)
