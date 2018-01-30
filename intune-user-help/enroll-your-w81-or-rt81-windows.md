---
title: "Jak zarejestrować urządzenie z systemem Windows 8.1 lub Windows RT 8.1 | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 28984f26-1070-4f7a-877c-669a59375c0c
searchScope:
- User help
ROBOTS: 
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 28b7d99e285762945b746295688fee5d53209b29
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-enroll-your-windows-81-or-windows-rt-81-device-in-intune"></a>Jak zarejestrować urządzenie z systemem Windows 8.1 lub Windows RT 8.1 w usłudze Intune

Jeśli firma lub szkoła używa usługi Microsoft Intune, możesz zarejestrować urządzenia, aby uzyskać dostęp do poczty e-mail, plików i innych zasobów firmy. Po zarejestrowaniu urządzeń organizacja może zapewnić bezpieczeństwo danych firmowych. Aby uzyskać więcej informacji o rejestracji, zobacz [Co się dzieje w przypadku zainstalowania aplikacji Portal firmy i zarejestrowania urządzenia w usłudze Intune?](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows.md) i [Lista rzeczy, jakie dział pomocy technicznej Twojej firmy może zobaczyć na Twoim urządzeniu i jakich nie może](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md).


Aby zarejestrować urządzenie z systemem Windows 8.1 lub Windows RT 8.1:

1.  Na urządzeniu naciśnij kolejno pozycje **Ustawienia** &gt; **Ustawienia komputera** &gt; **Sieć** &gt; **Miejsce pracy**.

    ![nav-to-workplace](./media/W81-1-workplacejoin.png)

2.  Wprowadź służbowy adres e-mail jako identyfikator użytkownika, jeśli jest wymagany, a następnie naciśnij pozycję **Dołącz**.

    Jeśli identyfikator użytkownika nie jest wymagany, używany jest adres e-mail wprowadzony podczas logowania na tym urządzeniu.

3.  Wprowadź hasło dla służbowego adresu e-mail.

    ![type-password](./media/W81-2-workplacesettings_signin.png)

4.  W obszarze **Włączanie zarządzania urządzeniami** naciśnij pozycję **Włącz**.

    ![turn-on-device-management](./media/W81-3-dev-mgt-turn-on.png)

5.  W oknie dialogowym **Zezwalanie na aplikacje i usługi od działu pomocy technicznej firmy** zaznacz pole wyboru **Zgadzam się**, a następnie naciśnij pozycję **Włącz**.

    ![turn-on-allow-apps-services](./media/W81-4-agree-allow-apps-services.png)

    Po pomyślnym zarejestrowaniu zobaczysz następujący ekran.

    ![enrollment-complete](./media/W81-5-enrolled-done.png)

Zalecane jest również zainstalowanie aplikacji Portal firmy, dzięki której możesz łatwo znaleźć i uzyskać aplikacje firmowe związane z Tobą i Twoim stanowiskiem. W zależności od tego, jak usługa Intune została skonfigurowana w firmie, aplikacja Portal firmy może zostać zainstalowana w ramach procesu rejestracji. Aby sprawdzić, czy masz tę aplikację, poszukaj nazwy **Portal firmy** na liście aplikacji. Jeśli lista nie zawiera aplikacji Portal firmy, wykonaj następujące kroki, aby ją zainstalować.

1.  Naciśnij kolejno pozycje **Start** &gt; **Sklep**.

2.  Naciśnij pozycję **Wyszukaj** i wpisz **portal firmy**.

3.  Na liście wyników naciśnij pozycję **Portal firmy**.

4.  Naciśnij pozycję **Zainstaluj** lub **Bezpłatne**. Wyświetlana opcja zależy od konfiguracji aplikacji w firmie.

Nadal potrzebujesz pomocy? Skontaktuj się z pomocą techniczną Twojej firmy. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://portal.manage.microsoft.com#HelpDeskDialog).
