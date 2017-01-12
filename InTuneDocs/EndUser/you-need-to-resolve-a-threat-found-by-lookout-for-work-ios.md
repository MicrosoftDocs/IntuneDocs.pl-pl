---
title: "Należy rozwiązać problem związany z zagrożeniem wykrytym przez aplikację Lookout for Work na urządzeniu z systemem iOS | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/17/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dd6aec3a-4063-4054-8d0f-d2f2034f0d3d
ROBOTS: NOINDEX,NOFOLLOW
translationtype: Human Translation
ms.sourcegitcommit: db5714009d4d0bcdd77be23314e4f2ff4db44b6e
ms.openlocfilehash: 9e958dc7421ac9373d80268db654c87c61ab3729


---

# <a name="you-need-to-resolve-a-threat-found-by-lookout-for-work"></a>Należy rozwiązać problem związany z zagrożeniem wykrytym przez aplikację Lookout for Work

Aplikacja Lookout for Work wykryła potencjalne zagrożenie na urządzeniu i należy rozwiązać ten problem, aby odzyskać dostęp do poczty e-mail, aplikacji i plików służbowych. Wyświetlony komunikat może wyglądać tak: 

![Komunikat o braku zgodności z aplikacji Lookout for Work](./media/ios-lfw-noncompliant-in-ssp.png)

Aby rozwiązać ten problem, otwórz aplikację Lookout for Work i wykonaj instrukcje wyświetlane w aplikacji.

## <a name="what-you-might-see-if-your-enrolled-device-is-blocked-from-accessing-email-or-files"></a>Ekran wyświetlany w przypadku zablokowania dostępu do wiadomości e-mail lub plików w zarejestrowanym urządzeniu

W przypadku próby uzyskania dostępu do firmowej poczty e-mail lub plików w sytuacji, gdy na zarejestrowanym urządzeniu znajduje się wirus lub występuje inne zagrożenie bezpieczeństwa, może zostać wyświetlony komunikat podobny do poniższego:

![Komunikat o błędzie aplikacji Lookout for Work z linkiem do witryny internetowej Portal firmy](./media/lookout-go-to-device-management-portal-android.png)

Wybierz link **portal zarządzania urządzeniami**, aby przejść do [witryny internetowej Portal firmy](http://portal.manage.microsoft.com), gdzie zostaną wyświetlone instrukcje dotyczące sposobu rozwiązania problemu.

## <a name="example-of-an-app-that-lookout-for-work-sees-as-a-threat"></a>Przykład aplikacji uznawanej za zagrożenie przez aplikację Lookout for Work

W przypadku zainstalowania aplikacji, którą aplikacja Lookout for Work uzna za zagrożenie, zostanie wyświetlony ekran podobny do następującego:

![Przykład alertu aplikacji Lookout for Work dotyczącego wykrycia wirusa](./media/ios-lfw-threat-example.png)

Jeśli widzisz podobny ekran, naciśnij nazwę aplikacji wyświetlaną u góry ekranu, a następnie wykonaj instrukcje, aby usunąć zagrożenie.

Po odinstalowaniu aplikacji można natychmiast ponownie uzyskać dostęp do służbowej poczty e-mail i danych. Jeśli zignorujesz żądanie dotyczące odinstalowania aplikacji, utracisz dostęp do firmowej poczty e-mail i danych do czasu odinstalowania aplikacji.

Nadal potrzebujesz pomocy? Skontaktuj się z administratorem IT. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](http://portal.manage.microsoft.com).





<!--HONumber=Dec16_HO3-->


