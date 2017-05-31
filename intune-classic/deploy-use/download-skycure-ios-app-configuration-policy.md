---
title: Pobieranie zasad konfiguracji aplikacji Skycure dla systemu iOS| Dokumentacja firmy Microsoft
description: "Pobierz zasady konfiguracji aplikacji Skycure dla systemu iOS do wykorzystania z wdrożoną u użytkowników końcowych aplikacją Skycure dla systemu iOS."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d211b876-4d3a-473c-999f-843c0a16cd22
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: a8e46960a5d469093052148eb457140b3c235d3a
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---

# <a name="download-skycure-ios-app-configuration-policy"></a>Pobieranie zasad konfiguracji aplikacji Skycure dla systemu iOS

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

##<a name="before-you-begin"></a>Przed rozpoczęciem

Aby wykonać kolejne kroki, musisz zalogować się do konsoli zarządzania Skycure.

> [!TIP] 
> Jeśli używasz przeglądarki Microsoft Internet Explorer 11 lub Edge, może być konieczne otwarcie konsoli zarządzania Skycure w trybie In-Private.

## <a name="to-download-the-ios-app-configuration-policy"></a>Aby pobrać zasady konfiguracji aplikacji dla systemu iOS

1.  Przejdź do [konsoli zarządzania Skycure](https://aad.skycure.com).

2.  Wprowadź swoje **poświadczenia administratora programu Skycure**, a następnie kliknij przycisk **Kontynuuj**.

    ![Logowanie do Konsoli zarządzania Skycure](../media/mtp/skycure-ios-app-1.png)

    > [!IMPORTANT] 
    > W przypadku administratora programu Skycure nazwą użytkownika jest konto e-mail, które musi należeć do prawidłowego użytkownika w usłudze Azure Active Directory. W przeciwnym razie logowanie zakończy się niepowodzeniem. Program Skycure używa usługi Azure Active Directory do uwierzytelniania nazwy użytkownika swojego administratora za pomocą funkcji logowania jednokrotnego (SSO, Single Sign On).

3.  Przejdź do opcji **Ustawienia** &gt; **Integracje zarządzania urządzeniami** &gt; **Wybór integracji EMM**, wybierz opcję **Microsoft Intune**, a następnie zapisz wybór.

2.  Kliknij link **Pliki instalacyjne integracji** i zapisz wygenerowany \*plik ZIP. Plik ZIP zawiera plik **skycure\_configuration.plist**, który będzie używany do tworzenia zasad konfiguracji aplikacji systemu iOS w klasycznej konsoli usługi Intune.

![Pliki instalacyjne usługi Skycure Integration](../media/mtp/skycure-ios-app-2.png)

## <a name="next-steps"></a>Następne kroki

[Dodawanie aplikacji Skycure, aplikacji Microsoft Authenticator i zasad konfiguracji systemu iOS](/intune-classic/deploy-use/add-skycure-apps-microsoft-authenticator-and-ios-app-configuration-policy)

