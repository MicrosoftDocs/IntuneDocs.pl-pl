---
title: Dodawanie aplikacji systemu Android Enterprise do usługi Microsoft Intune
titleSuffix: ''
description: Dowiedz się, jak dodawać aplikacje systemu Enterprise do usługi Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/23/2020
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
ms.openlocfilehash: 613369070d847265f371a7b228a2b6d81bf813fe
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2020
ms.locfileid: "76755259"
---
# <a name="add-android-enterprise-system-apps-to-microsoft-intune"></a>Dodawanie aplikacji systemu Android Enterprise do usługi Microsoft Intune

Przed przypisaniem aplikacji do urządzenia lub grupy użytkowników należy najpierw dodać aplikację do usługi Microsoft Intune. Aplikacje systemowe są obsługiwane na urządzeniach z systemem Android Enterprise. Możesz włączyć aplikację systemową na [dedykowanych urządzeniach z systemem Android Enterprise](../enrollment/android-kiosk-enroll.md) lub [w pełni zarządzanych urządzeniach](../enrollment/android-fully-managed-enroll.md).

## <a name="add-the-app"></a>Dodawanie aplikacji

Możesz dodawać aplikacje systemu Android Enterprise do usługi Intune w witrynie Azure Portal, wykonując następujące czynności:

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Aplikacje** > **Wszystkie aplikacje** > **Dodaj**.
3. W okienku **Wybierz typ aplikacji** wybierz pozycję **Aplikacja systemu Android Enterprise** w obszarze dostępnych typów **Inne**.
4. Kliknij pozycję **Wybierz**. Zostaną wyświetlone kroki **dodawania aplikacji**.
Na stronie **Informacje o aplikacji** dodaj szczegóły aplikacji:
    - **Nazwa aplikacji**: Wprowadź nazwę aplikacji.
    - **Wydawca**: Wprowadź nazwę wydawcy aplikacji.  
    - **Nazwa pakietu**: Wprowadź nazwę pakietu. Usługa Intune sprawdzi, czy nazwa pakietu jest prawidłowa.
5. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Tagi zakresu**.
8. Kliknij pozycję **Wybierz tagi zakresu**, aby opcjonalnie dodać tagi zakresu dla aplikacji. Aby uzyskać więcej informacji, zobacz temat [Używanie kontroli dostępu opartej na rolach i tagów zakresu w rozproszonej infrastrukturze informatycznej](~/fundamentals/scope-tags.md).
9. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Przypisania**.
10. Wybierz przypisania grupy dla aplikacji. Aby uzyskać więcej informacji, zobacz temat [Dodawanie grup w celu organizowania użytkowników i urządzeń](~/fundamentals/groups-add.md). 
11. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Recenzja i tworzenie**. Przejrzyj wartości i ustawienia wprowadzone dla aplikacji.
12. Gdy skończysz, kliknij pozycję **Utwórz**, aby dodać aplikację do usługi Intune.

Zostanie wyświetlony blok **Omówienie** dotyczący utworzonej aplikacji.

> [!NOTE]
> Aby znaleźć nazwę pakietu aplikacji, którą chcesz włączyć/wyłączyć, skontaktuj się z producentem OEM urządzenia.

Utworzona aplikacja będzie wyświetlana na liście aplikacji, z której można ją przypisać do wybranych grup. 

Aplikacje systemu Android Enterprise będą włączać lub wyłączać aplikacje, które są już częścią platformy. Aby włączyć aplikację, przypisz aplikację systemową jako **Wymaganą**. Aby wyłączyć aplikację, przypisz aplikację systemową jako **Odinstaluj**. Aplikacje systemowe nie mogą być przypisywane jako dostępne dla użytkownika.


## <a name="next-steps"></a>Następne kroki

- [Przypisywanie aplikacji do grup](apps-deploy.md)
