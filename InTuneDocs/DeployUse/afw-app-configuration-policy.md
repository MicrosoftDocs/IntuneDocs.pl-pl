---
title: "Użycie zasad konfiguracji aplikacji mobilnych programu Android for Work | Microsoft Intune"
description: "Zasady konfiguracji aplikacji mobilnych w usłudze Intune umożliwiają określanie wartości ustawień, które mogą być wymagane, jeśli użytkownicy uruchamiają aplikację programu Android for Work."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/3/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fc6b645a-e837-4b2a-a10f-144065cbd8dd
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 32bded5047b1a08738418e3e36382eeae1a5f3b4
ms.openlocfilehash: a986e859e38e0936f53c57a75872dc86de3ee181


---

# <a name="configure-android-for-work-apps-with-mobile-app-configuration-policies-in-microsoft-intune"></a>Konfigurowanie aplikacji programu Android for Work przy użyciu zasad konfiguracji aplikacji mobilnych w usłudze Microsoft Intune

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

Zasady konfiguracji aplikacji mobilnych w usłudze Microsoft Intune umożliwiają określanie wartości ustawień, które mogą być wymagane, jeśli użytkownicy uruchamiają aplikację. Aplikacja może na przykład wymagać, aby użytkownicy określili:

-   Niestandardowy numer portu

-   Ustawienia języka

-   Ustawienia oznaczeń marki, takich jak logo firmy

Nieprawidłowe określenie tych ustawień przez użytkowników może zwiększyć obciążenie działu pomocy technicznej i spowolnić wdrażanie technologii nowych aplikacji.

Zasady konfiguracji aplikacji mobilnych mogą pomóc wyeliminować te problemy, umożliwiając wdrażanie tych ustawień do użytkowników, zanim uruchomią oni aplikację. Ustawienia są następnie określane automatycznie, a użytkownicy nie muszą podejmować żadnej akcji.

Aby korzystać z zasad konfiguracji aplikacji, podczas tworzenia aplikacji deweloper musi udostępnić konfiguracje aplikacji dla przedsiębiorstw. Na przykład przeglądarka Google Chrome udostępnia ustawienia, które umożliwiają ustawienie domyślnych zakładek, dozwolonych i niedozwolonych witryn i innych opcji. Skontaktuj się z deweloperem aplikacji, aby sprawdzić, czy te ustawienia są obsługiwane i jak określić je w zasadach.

Zasady konfiguracji aplikacji są wdrażane do tych samych użytkowników, do których wdrożono aplikację, którą chcesz skonfigurować. Ustawienia zasad będą używane przy każdym uruchomieniu aplikacji.

## <a name="configure-a-mobile-app-configuration-policy"></a>Konfigurowanie zasad konfiguracji aplikacji mobilnych

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) wybierz pozycję **Zasady** &gt; **Przegląd** &gt; **Dodaj zasady**.

2.  Na liście zasad rozwiń węzeł **Android for Work**, wybierz pozycję **Zasady konfiguracji aplikacji mobilnych (Android for Work)**, a następnie wybierz pozycję **Utwórz zasady**.

    > [!TIP]
    > W przypadku tego typu zasad możesz skonfigurować tylko ustawienia niestandardowe. Zalecane ustawienia są niedostępne.

3.  W części **Ogólne** strony **Tworzenie zasad** podaj nazwę i opcjonalny opis zasad konfiguracji aplikacji mobilnej.

4. W sekcji **Zasady konfiguracji aplikacji mobilnych** na tej stronie określ następujące informacje:
    - **Identyfikator pakietu dla aplikacji, której dotyczy ta konfiguracja** — identyfikator pakietu znajduje się w sekcji „id=” adresu URL aplikacji na jej stronie w Sklepie Google Play. Na przykład identyfikator pakietu aplikacji Microsoft Excel to **com.microsoft.office.excel**.
    - W polu tekstowym wprowadź dane ustawień aplikacji, którą chcesz skonfigurować. Te ustawienia można uzyskać od dostawcy aplikacji. Nie wszystkie aplikacje obsługują te ustawienia.
5.  Kliknij pozycję **Weryfikuj**, aby się upewnić, że wprowadzone dane mają prawidłowy format listy właściwości.

    > [!IMPORTANT]
    > Po kliknięciu pozycji **Weryfikuj** usługa Intune sprawdza, czy wprowadzone dane konfiguracji mają prawidłowy format. Nie sprawdza ona, czy dane będą współdziałać z aplikacją, z którą zostały skojarzone.

6.  Następnie kliknij przycisk **Zapisz zasady**.

Nowe zasady zostaną wyświetlone w węźle **Zasady konfiguracji** .


## <a name="deploy-the-app-configuration-policy"></a>Wdrażanie zasad konfiguracji aplikacji
Po utworzeniu zasad konfiguracji aplikacji mobilnej należy wdrożyć je do tych samych użytkowników, do których została wdrożona aplikacja, której będą dotyczyć ustawienia.

Aby uzyskać informacje na temat sposobu wdrażania zasad, zobacz [Wdrażanie zasad konfiguracji](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#deploy-a-configuration-policy).

Aby uzyskać informacje na temat sposobu wdrażania aplikacji do urządzeń z programem Android for Work, zobacz [Jak wdrażać aplikacje programu Android for Work za pomocą usługi Intune](android-for-work-apps.md).

Po uruchomieniu wdrożonej aplikacji na urządzeniu zostaną uruchomione ustawienia skonfigurowane w zasadach konfiguracji aplikacji mobilnej.

> [!TIP]
> Dla każdej aplikacji należy wdrożyć tylko jedną zasadę konfiguracji do użytkownika.



<!--HONumber=Oct16_HO2-->


