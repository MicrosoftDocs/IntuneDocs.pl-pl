---
title: Korzystanie z aplikacji zarządzanych na urządzeniu z systemem Android | Microsoft Docs
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/24/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ed10a62c-b026-4ad3-ac41-641933522df2
searchScope:
- User help
ROBOTS: ''
ms.reviewer: maxles
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: ebb79bc3405e9ea0dd38c24b86a4c9020760c895
ms.sourcegitcommit: 2773f388f50654366197a95a6838306f70fc18b8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/18/2018
---
# <a name="use-managed-apps-on-your-android-device"></a>Korzystanie z aplikacji zarządzanych na urządzeniu z systemem Android

Aplikacje zarządzane to aplikacje, które dział pomocy technicznej Twojej firmy może skonfigurować w celu wspomagania ochrony danych firmowych dostępnych w tych aplikacjach. Gdy uzyskujesz dostęp do danych firmowych w aplikacji zarządzanej na urządzeniu z systemem Android, możesz zauważyć, że aplikacja działa w sposób nieco inny od spodziewanego. Na przykład może okazać się niemożliwe kopiowanie i wklejanie chronionych danych firmowych lub zapisywanie tych danych w określonych lokalizacjach.

Różne aplikacje zarządzane mogą również współpracować ze sobą na urządzeniu, aby umożliwić wykonywanie codziennych zadań z zachowaniem ochrony danych firmowych. Na przykład jeśli otwierasz plik firmowy w jednej aplikacji zarządzanej, a do wyświetlenia tego pliku jest wymagana inna aplikacja zarządzana, automatycznie otwiera się aplikacja zarządzana, która umożliwia wyświetlenie pliku. Jeśli wymagana aplikacja jest niedostępna, pewne akcje, takie jak otwieranie dokumentu lub uzyskiwanie dostępu do linku sieci Web z dokumentu zarządzanego, mogą być niedostępne.

Gdy uzyskujesz dostęp do danych firmowych w aplikacji zarządzanej, jest wyświetlany komunikat podobny do poniższego, który informuje o tym, że otwierana aplikacja jest zarządzana.

![Komunikat dotyczący otwierania zarządzanej aplikacji](./media/managed-apps-message.png)

## <a name="how-do-i-get-managed-apps"></a>Jak uzyskać aplikacje zarządzane?
Aplikacje zarządzane można uzyskać na kilka sposobów:

-   Gdy urządzenie jest zarejestrowane w usłudze Microsoft Intune, zainstaluj aplikację z aplikacji Portal firmy lub witryny internetowej Portal firmy. Aplikację może również zainstalować na Twoim urządzeniu dział pomocy technicznej Twojej firmy. Aby uzyskać informacje na temat rejestrowania, zobacz [Rejestrowanie urządzenia w usłudze Intune](enroll-your-device-in-Intune-android.md).

-   Zainstaluj aplikację ze Sklepu Play, a następnie zaloguj się przy użyciu firmowego konta użytkownika, które jest zarządzane przez usługę Intune.

## <a name="what-can-my-company-support-manage-in-an-app"></a>Czym dział pomocy technicznej mojej firmy może zarządzać w aplikacji?
Oto kilka przykładowych opcji, którymi dział pomocy technicznej Twojej firmy może zarządzać w aplikacji i które mogą wpływać na interakcję z danymi firmowymi na urządzeniu:

-   Dostęp do określonych witryn sieci Web

-   Transfery danych między aplikacjami

-   Zapisywanie plików

-   Operacje kopiowania i wklejania

-   Wymagania dotyczące uzyskiwania dostępu za pomocą numeru PIN

-   Logowanie przy użyciu poświadczeń firmowych

-   Możliwość tworzenia kopii zapasowej w chmurze

-   Możliwość tworzenia zrzutów ekranu

-   Wymagania dotyczące szyfrowania danych

Do typowych aplikacji, którymi może zarządzać dział IT, należą między innymi:

-   Intune Managed Browser

-   Przeglądarka usługi Microsoft Azure Information Protection

-   Microsoft Word, Excel i PowerPoint

Aby uzyskać więcej informacji o aplikacjach zarządzanych na Twoim urządzeniu, skontaktuj się z działem pomocy technicznej Twojej firmy. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://portal.manage.microsoft.com#HelpDeskDialog).
