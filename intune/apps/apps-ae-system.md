---
title: Dodawanie aplikacji systemu Android Enterprise do usługi Microsoft Intune
titleSuffix: ''
description: Dowiedz się, jak dodawać aplikacje systemu Enterprise do usługi Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: priyar
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d45455a97f8016527dce49839b5493f16b173d43
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/27/2019
ms.locfileid: "74563654"
---
# <a name="add-android-enterprise-system-apps-to-microsoft-intune"></a>Dodawanie aplikacji systemu Android Enterprise do usługi Microsoft Intune

Przed przypisaniem aplikacji do urządzenia lub grupy użytkowników należy najpierw dodać aplikację do usługi Microsoft Intune. Aplikacje systemowe są obsługiwane na urządzeniach z systemem Android Enterprise. Możesz włączyć aplikację systemową na [dedykowanych urządzeniach z systemem Android Enterprise](../enrollment/android-kiosk-enroll.md) lub [w pełni zarządzanych urządzeniach](../enrollment/android-fully-managed-enroll.md).

## <a name="add-the-app"></a>Dodawanie aplikacji

Możesz dodawać aplikacje systemu Android Enterprise do usługi Intune w witrynie Azure Portal, wykonując następujące czynności:

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz kolejno pozycje **Aplikacje** > **Wszystkie aplikacje** > **Dodaj**.
3. W okienku **Dodaj aplikację** wybierz pozycję **aplikacja systemu Android Enterprise** w obszarze dostępnych typów **Inne**.
4. Aby skonfigurować informacje o aplikacji, wybierz pozycję **Konfiguruj**, a następnie podaj następujące informacje:
    - **Nazwa aplikacji**: Wprowadź nazwę aplikacji.
    - **Wydawca**: Wprowadź nazwę wydawcy aplikacji.  
    - **Nazwa pakietu**: Wprowadź nazwę pakietu. Usługa Intune sprawdzi, czy nazwa pakietu jest prawidłowa.
5. Wybierz przycisk **OK**.
6. Wybierz pozycję **Dodaj**.

> [!NOTE]
> Aby znaleźć nazwę pakietu aplikacji, którą chcesz włączyć/wyłączyć, skontaktuj się z producentem OEM urządzenia.

Utworzona aplikacja będzie wyświetlana na liście aplikacji, z której można ją przypisać do wybranych grup. 

Aplikacje systemu Android Enterprise będą włączać lub wyłączać aplikacje, które są już częścią platformy. Aby włączyć aplikację, przypisz aplikację systemową jako **Wymaganą**. Aby wyłączyć aplikację, przypisz aplikację systemową jako **Odinstaluj**. Aplikacje systemowe nie mogą być przypisywane jako dostępne dla użytkownika.


## <a name="next-steps"></a>Następne kroki

- [Przypisywanie aplikacji do grup](apps-deploy.md)
