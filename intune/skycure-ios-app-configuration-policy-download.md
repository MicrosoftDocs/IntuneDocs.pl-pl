---
title: Pobieranie zasad konfiguracji aplikacji Skycure dla systemu iOS
titlesuffix: Azure portal
description: "Pobierz zasady konfiguracji aplikacji Skycure dla systemu iOS do użycia w usłudze Intune."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1bdc2ecf-32d0-4b6a-80b4-dbcdb9909010
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cbf26b44725f1fa08fbc6766f0560fe91d63d6ca
ms.sourcegitcommit: a3a744ea55f38a360ca9f788c77a5b3018d1add5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/30/2017
---
# <a name="download-skycure-ios-app-configuration-policy"></a>Pobieranie zasad konfiguracji aplikacji Skycure dla systemu iOS

## <a name="before-you-begin"></a>Przed rozpoczęciem

Aby wykonać kolejne kroki, musisz zalogować się do konsoli zarządzania Skycure.

> [!TIP] 
> Jeśli używasz przeglądarki Microsoft Internet Explorer 11 lub Edge, może być konieczne otwarcie konsoli zarządzania Skycure w trybie In-Private.

## <a name="to-download-the-ios-app-configuration-policy"></a>Aby pobrać zasady konfiguracji aplikacji dla systemu iOS

1.  Przejdź do [konsoli zarządzania Skycure](https://aad.skycure.com).

2.  Wprowadź swoje **poświadczenia administratora programu Skycure**, a następnie kliknij przycisk **Kontynuuj**.

    ![Logowanie do Konsoli zarządzania Skycure](./media/skycure-ios-app-1.png)

    > [!IMPORTANT] 
    > W przypadku administratora programu Skycure nazwą użytkownika jest konto e-mail, które musi należeć do prawidłowego użytkownika w usłudze Azure Active Directory. W przeciwnym razie logowanie zakończy się niepowodzeniem. Program Skycure używa usługi Azure Active Directory do uwierzytelniania nazwy użytkownika swojego administratora za pomocą funkcji logowania jednokrotnego (SSO, Single Sign On).

3.  Przejdź do opcji **Ustawienia** &gt; **Integracje zarządzania urządzeniami** &gt; **Wybór integracji EMM**, wybierz opcję **Microsoft Intune**, a następnie zapisz wybór.

4.  Kliknij link **Pliki instalacyjne integracji** i zapisz wygenerowany \*plik ZIP. Plik ZIP zawiera plik **skycure\_configuration.plist**, który będzie używany do tworzenia zasad konfiguracji aplikacji systemu iOS w portalu klasycznym usługi Intune.

![Pliki instalacyjne usługi Skycure Integration](./media/skycure-ios-app-2.png)

## <a name="next-steps"></a>Następne kroki

[Dodawanie i przypisywanie aplikacji Skycure, aplikacji Microsoft Authenticator i zasad konfiguracji systemu iOS](mtd-apps-ios-app-configuration-policy-add-assign.md)
