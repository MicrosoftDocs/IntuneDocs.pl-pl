---
title: Brak wymaganego certyfikatu urządzenia | Microsoft Docs
titlesuffix: Microsoft Intune
description: Twoje urządzenie nie ma certyfikatu wymaganego przez dział pomocy technicznej Twojej firmy.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 12/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser; seodec18
ms.openlocfilehash: e40ac2fd81375b84084dd229f4cb5a6ab3e9915f
ms.sourcegitcommit: fff179f59bd542677cbd4bf3bacc24bb880e2cb6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/07/2018
ms.locfileid: "53032218"
---
# <a name="your-device-is-missing-a-required-certificate"></a>Brak wymaganego certyfikatu urządzenia

## <a name="whats-a-certificate"></a>Co to jest certyfikat?

[Kryptografia](https://technet.microsoft.com/library/cc962030.aspx) to dziedzina nauki zajmująca się zapewnianiem bezpieczeństwa informacji. Kryptografia służyła kiedyś do przekazywania kodowanych wiadomości w celu [zagwarantowania, że komunikacja ma charakter tajny](https://technet.microsoft.com/library/cc962019.aspx). W swej najprostszej postaci kryptografia zakłada zamianę lub podstawianie liter w celu przekształcenia kodowanej wiadomości w wiadomość niemożliwą do odczytania, zaszyfrowaną lub ukrytą. Tylko osoba posiadająca klucz dekodujący lub _certyfikat_ może dokonać konwersji kodowanego komunikatu do jego pierwotnej postaci umożliwiającej odczyt. Urządzenie z systemem Android wykorzystuje certyfikaty usługi Intune w celu zagwarantowania, że komunikacja między urządzeniem i zasobami organizacji, taka jak wiadomości e-mail i dokumenty, jest bezpieczna zarówno po stronie urządzenia, jak i zasobów, a także podczas przesyłu danych w toku komunikacji.

## <a name="fixing-certificate-issues"></a>Rozwiązywanie problemów z certyfikatami

Jeśli urządzenie z systemem Android nie zostało zarejestrowane w usłudze Intune i nie ma certyfikatu wymaganego przez dział pomocy technicznej Twojej firmy, nie można zalogować się do aplikacji Portal firmy. Przy próbie zalogowania się zostanie wyświetlony następujący komunikat:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

Pierwszym krokiem, jaki należy wykonać, jest sprawdzenie, czy w urządzeniu [brakuje certyfikatu, który zwykle jest na nim wstępnie zainstalowany](your-device-is-missing-a-preinstalled-certificate-android.md).

Jeśli nie udaje się rozwiązać problemów z certyfikatem, dział pomocy technicznej Twojej firmy może [narzucić wymóg zainstalowania drugiego certyfikatu w celu zapewnienia wyższego poziomu bezpieczeństwa](your-device-is-missing-an-IT-required-certificate-android.md).

Nadal potrzebujesz pomocy? Skontaktuj się z pomocą techniczną Twojej firmy. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).
