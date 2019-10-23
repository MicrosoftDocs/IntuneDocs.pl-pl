---
title: Resetowanie urządzeń z systemem Windows 10 za pomocą usługi Microsoft Intune — Azure | Microsoft Docs
description: Usuń lub odinstaluj aplikacje na komputerach z systemem Windows 10 przy użyciu funkcji Rozpoczęcie od nowa usługi Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/09/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ff1dc2565ef52f81619abe8f14e78c58da0fce7d
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72508620"
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Użycie funkcji Rozpoczęcie od nowa do resetowania urządzeń z systemem Windows 10 przy użyciu usługi Intune


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Akcja **Rozpoczęcie od nowa** urządzenia usuwa wszystkie aplikacje zainstalowane na komputerze z systemem Windows 10 w wersji 1703 lub nowszej. Akcja Rozpoczęcie od nowa ułatwia usunięcie wstępnie zainstalowanych aplikacji (OEM), które zwykle są zainstalowane na nowym komputerze. 

1. Zaloguj się w witrynie [Azure Portal](https://portal.azure.com) i przejdź do obszaru > **Microsoft Intune** > **Urządzenia** > **Wszystkie urządzenia**.
2. Z listy urządzeń zarządzanych wybierz urządzenie z systemem Windows 10 Desktop.
3. Kliknij pozycję **Rozpoczęcie od nowa**. 
4. Wybierz opcję **Zachowaj dane użytkownika na tym urządzeniu**, aby:
   * urządzenie pozostało dołączone do usługi Azure AD,
   * urządzenie zostało ponownie zarejestrowane w usługach zarządzania urządzeniami mobilnymi, gdy zaloguje się do niego użytkownik z włączoną obsługą usługi Azure Active Directory,
   * zachować zawartość folderu macierzystego urządzenia użytkownika i usunąć aplikacje i ustawienia.

  > [!IMPORTANT]
 > Jeśli dane użytkownika nie zostaną zachowane, urządzenie zostanie przywrócone do domyślnego stanu OOBE (out-of-box experience), zachowując wbudowane konto administratora.
 > Urządzenie BYOD zostanie wyrejestrowane z usługi Azure AD i z usługi zarządzania urządzeniami przenośnymi.
 > Urządzenie dołączone do hybrydowej usługi Azure AD zostanie ponownie zarejestrowane w usługach zarządzania urządzeniami przenośnymi, gdy zaloguje się do niego użytkownik z włączoną obsługą usługi Azure Active Directory.
 
5. Kliknij przycisk **OK**.   
6. Aby wyświetlić stan tej akcji, wróć do obszaru **Urządzenia** i kliknij przycisk **Akcje urządzenia**.  
7. Na urządzeniu zostanie przywrócony początkowy ekran logowania.
