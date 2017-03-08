---
title: "Brak wymaganego certyfikatu urządzenia | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 01/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213
searchScope:
- User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
translationtype: Human Translation
ms.sourcegitcommit: 207297601634f390051a6345b96bf09e1d031747
ms.openlocfilehash: 6b37cede797f965b82c067b274517277d8597939
ms.lasthandoff: 01/12/2017

---


# <a name="your-device-is-missing-a-required-certificate"></a>Brak wymaganego certyfikatu urządzenia

## <a name="whats-a-certificate"></a>Co to jest certyfikat?

[Kryptografia](https://technet.microsoft.com/en-us/library/cc962030.aspx) to dziedzina nauki zajmująca się zapewnianiem bezpieczeństwa informacji. Kryptografia służyła kiedyś do przekazywania kodowanych wiadomości w celu [zagwarantowania, że komunikacja ma charakter tajny](https://technet.microsoft.com/en-us/library/cc962019.aspx). W swej najprostszej postaci kryptografia zakłada zamianę lub podstawianie liter w celu przekształcenia wiadomości kodowanej w wiadomość niemożliwą do odczytania, zaszyfrowaną lub ukrytą. Tylko osoba posiadająca klucz dekodujący lub _certyfikat_ może dokonać konwersji kodowanego komunikatu do jego pierwotnej postaci umożliwiającej odczyt. Urządzenie z systemem Android wykorzystuje certyfikaty usługi Intune w celu zagwarantowania, że komunikacja między urządzeniem i zasobami organizacji, taka jak wiadomości e-mail i dokumenty, jest bezpieczna zarówno po stronie urządzenia, jak i zasobów, a także podczas przesyłu danych w toku komunikacji.

## <a name="fixing-certificate-issues"></a>Rozwiązywanie problemów z certyfikatami

Jeśli urządzenie z systemem Android nie zostało zarejestrowane w usłudze Intune i nie ma certyfikatu wymaganego przez administratora IT, nie można zalogować się do aplikacji Portal firmy. Przy próbie zalogowania się zostanie wyświetlony następujący komunikat:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

Pierwszym krokiem, jaki należy wykonać, jest sprawdzenie, czy w urządzeniu [brakuje certyfikatu, który zwykle jest na nim wstępnie zainstalowany](your-device-is-missing-a-preinstalled-certificate-android.md).

Jeśli wykonanie tej czynności nie rozwiąże problemu, administrator IT może [narzucić wymóg zainstalowania drugiego certyfikatu w celu zapewnienia dodatkowego bezpieczeństwa](your-device-is-missing-an-IT-required-certificate-android.md).

Nadal potrzebujesz pomocy? Skontaktuj się z administratorem IT. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](http://portal.manage.microsoft.com).

