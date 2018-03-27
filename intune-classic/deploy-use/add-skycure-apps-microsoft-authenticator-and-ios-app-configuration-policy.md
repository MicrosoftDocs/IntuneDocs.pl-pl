---
title: Dodawanie aplikacji Skycure, aplikacji Microsoft Authenticator i zasad konfiguracji systemu iOS
description: Dodawanie aplikacji Skycure, aplikacji Microsoft Authenticator i zasad konfiguracji systemu iOS w portalu klasycznym usługi Intune.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 03/16/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 018d26f4-4a75-4e27-bb04-54f54106cb2f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 45412855db4afd9dd03b2139a3720d1619d293e2
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/22/2018
---
# <a name="add-skycure-apps-microsoft-authenticator-app-and-ios-configuration-policy"></a>Dodawanie aplikacji Skycure, aplikacji Microsoft Authenticator i zasad konfiguracji systemu iOS

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Do dodawania i wdrażania aplikacji należy używać usługi Intune, aby użytkownicy końcowi mogli otrzymywać powiadomienia w chwili zidentyfikowania zagrożenia w ich urządzeniach przenośnych oraz wskazówki dotyczące usuwania zagrożeń.

Ponadto wymagana jest aplikacja [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) do sprawdzania tożsamości użytkowników przez usługę Azure AD; zasady konfiguracji aplikacji systemu iOS, które sygnalizują aplikacji Skycure dla systemu iOS użycie funkcji logowania jednokrotnego (SSO) usługi Azure AD; usługa Intune, aby użytkownicy nie musieli wpisywać nazwy użytkownika i hasła przy każdym logowaniu do aplikacji Skycure.

## <a name="before-you-begin"></a>Przed rozpoczęciem

-   Poniższe kroki należy wykonać w [portalu klasycznym usługi Intune](https://manage.microsoft.com/).

-   Użyj tego samego konta usługi Azure AD, które zostało wcześniej skonfigurowane w konsoli zarządzania aplikacji Skycure. Powinno to być konto używane podczas logowania się do portalu klasycznego usługi Intune.

-   Plik integracji Skycure musi być gotowy do użycia. Jest to pobrany wcześniej z konsoli zarządzania Skycure plik ZIP, który zawiera plik **skycure\_configuration.plist** z parametrami zasad konfiguracji aplikacji systemu iOS.

-   Upewnij się, że znasz następujące procesy:

    -   [Dodawanie aplikacji w usłudze Intune](/intune-classic/deploy-use/add-apps).

    -   [Dodawanie zasad konfiguracji aplikacji systemu iOS w usłudze Intune](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

## <a name="to-add-the-skycure-app-for-android"></a>Aby dodać aplikację Skycure dla systemu Android

1.  W portalu klasycznym usługi Intune wybierz opcję **Aplikacje** &gt; **Dodaj aplikacje**, aby uruchomić narzędzie Wydawca oprogramowania usługi Intune, a następnie kliknij przycisk **Dalej**.

2.  Na stronie **Instalator oprogramowania** wybierz opcję **Odnośnik zewnętrzny**, a następnie w polu **Określ adres URL** wklej [adres URL aplikacji Skycure dla systemu Android](https://play.google.com/store/apps/details?id=com.skycure.skycure).

    ![Podaj adres URL w narzędziu Wydawca oprogramowania usługi Intune](../media/mtp/skycure-add-apps-1.png)

3.  Na stronie **Opis oprogramowania** wprowadź wartości pól **Wydawca**, **Nazwa** i **Opis**, wybierz opcję **Wyświetlaj jako polecaną aplikację i wyróżnij w Portalu firmy**, a następnie kliknij przycisk **Dalej**.

    ![Opis oprogramowania w narzędziu Wydawca oprogramowania usługi Intune](../media/mtp/skycure-add-apps-2.png)

4.  Kliknij przycisk **Przekaż**, a następnie przycisk **Zamknij**.

## <a name="to-add-the-skycure-app-for-ios"></a>Aby dodać aplikację Skycure dla systemu iOS

1.  W portalu klasycznym usługi Intune wybierz opcję **Aplikacje** &gt; **Dodaj aplikacje**, aby uruchomić narzędzie Wydawca oprogramowania usługi Intune, a następnie kliknij przycisk **Dalej**.

2.  Na stronie **Instalator oprogramowania** wybierz opcję **Zarządzana aplikacja systemu iOS ze sklepu App Store**, a następnie w polu **Określ adres URL** wklej [adres URL aplikacji Skycure dla systemu iOS](https://itunes.apple.com/us/app/skycure/id695620821?mt=8).

    ![Zarządzana aplikacja systemu iOS w narzędziu Wydawca oprogramowania usługi Intune](../media/mtp/skycure-add-apps-3.png)

3.  Na stronie **Opis oprogramowania** wprowadź wartości pól **Wydawca**, **Nazwa** i **Opis**, wybierz opcję **Wyświetlaj jako polecaną aplikację i wyróżnij w Portalu firmy**, a następnie kliknij przycisk **Dalej**.

    ![Opcje aplikacji w narzędziu Wydawca oprogramowania usługi Intune](../media/mtp/skycure-add-apps-4.png)

4.  Na stronie **Wymagania** w polu **Typ urządzenia przenośnego** zaznacz opcję **Dowolne**, następnie kliknij przycisk **Dalej**.

5.  Kliknij przycisk **Przekaż**, a następnie przycisk **Zamknij**.

## <a name="to-add-the-microsoft-authenticator-app-for-ios"></a>Aby dodać aplikację Microsoft Authenticator dla systemu iOS

1.  W portalu klasycznym usługi Intune wybierz opcję **Aplikacje** &gt; **Dodaj aplikacje**, aby uruchomić narzędzie Wydawca oprogramowania usługi Intune, a następnie kliknij przycisk **Dalej**.

2.  Na stronie **Instalator oprogramowania** wybierz opcję **Zarządzana aplikacja systemu iOS ze sklepu App Store**, a następnie w polu **Określ adres URL** wklej [adres URL aplikacji Microsoft Administrator dla systemu iOS](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8).

    ![Zarządzana aplikacja systemu iOS w narzędziu Wydawca oprogramowania usługi Intune — 2](../media/mtp/skycure-add-apps-5.png)

3.  Na stronie **Opis oprogramowania** wprowadź wartości pól **Wydawca**, **Nazwa** i **Opis**, wybierz opcję **Wyświetlaj jako polecaną aplikację i wyróżnij w Portalu firmy**, a następnie kliknij przycisk **Dalej**.

    ![Zarządzana aplikacja systemu iOS w narzędziu Wydawca oprogramowania usługi Intune — 3](../media/mtp/skycure-add-apps-6.png)

4.  Na stronie **Wymagania** w polu **Typ urządzenia przenośnego** zaznacz opcję **Dowolne**, następnie kliknij przycisk **Dalej**.

5.  Kliknij przycisk **Przekaż**, a następnie przycisk **Zamknij**.

## <a name="to-add-the-skycure-ios-app-configuration-policy"></a>Aby dodać zasady konfiguracji aplikacji Skycure dla systemu iOS

1.  W portalu klasycznym usługi Intune wybierz opcję **Zasady** &gt; **Przegląd &gt; Dodaj zasady**.

2.  Na liście zasad rozwiń węzeł **iOS**, wybierz pozycję **Zasady konfiguracji aplikacji mobilnej (iOS 8.0 i nowsze)**, a następnie wybierz pozycję **Utwórz zasady**.

    ![Zasady konfiguracji aplikacji systemu iOS](../media/mtp/skycure-add-apps-7.png)

3.  W sekcji **Ogólne** strony **Utwórz zasady** podaj nazwę i opcjonalny opis zasad konfiguracji aplikacji mobilnej dla systemu iOS.

    a.  Otwórz plik **skycure\_configuration.plist** za pomocą edytora tekstów, takiego jak Notatnik, skopiuj jego zawartość i wklej ją w treści pola **Zasady konfiguracji aplikacji mobilnej**, wybierz polecenie **Sprawdź poprawność**, a następnie wybierz opcję **Zapisz zasady**.

       ![Zasady konfiguracji aplikacji systemu iOS — 2](../media/mtp/skycure-add-apps-8.png)

## <a name="next-steps"></a>Następne kroki

[Wdrażanie aplikacji Skycure, aplikacji Microsoft Authenticator i zasad konfiguracji systemu iOS](/intune-classic/deploy-use/deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy)
