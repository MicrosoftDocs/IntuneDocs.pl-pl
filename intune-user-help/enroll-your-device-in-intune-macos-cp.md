---
title: "Rejestrowanie urządzenia z systemem macOS w usłudze Intune za pomocą aplikacji Portal firmy | Microsoft Docs"
description: "Opis sposobu rejestrowania urządzenia z systemem macOS w usłudze Intune za pomocą aplikacji Portal firmy"
keywords: Mac OS X, macOS, OS X
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 09/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3bb659cc-9b57-4d19-8631-2c26749fa71c
searchScope: User help
ROBOTS: 
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: b40801633a130ac79b0ae5b4e1669320c70909e2
ms.sourcegitcommit: db7a7bbead3a3fa78c4d643607f709a2909eb608
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/28/2017
---
# <a name="enroll-your-macos-device-in-intune-with-the-company-portal-app"></a>Rejestrowanie urządzenia z systemem macOS w usłudze Intune przy użyciu aplikacji Portal firmy

[!INCLUDE[macos-preview-1708](./includes/macos-preview-1708.md)]

Uzyskiwanie dostępu do aplikacji, danych i zasobów organizacji ułatwia wykonywanie pracy. Twoja organizacja używa usługi Intune do [zarządzania dostępem do tych zasobów](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-ios.md), co wymaga pobrania aplikacji Portal firmy dla systemu macOS. Te instrukcje będą działać w przypadku urządzeń z systemem macOS w wersji OS X El Capitan 10.11 i nowszych.

  > [!NOTE]
  > Jeśli chcesz zarejestrować urządzenie z systemem iOS, takie jak iPhone lub iPad, [zamiast tego spróbuj wykonać te instrukcje](enroll-your-device-in-intune-ios.md).

1.  W __Docku__ wyszukaj pozycję __Safari__ i przejdź na stronę [aka.ms/macoscompanyportal](https://aka.ms/macoscompanyportal). 

2. Pobierz aplikację. Komputer Mac sprawdzi, czy pobrany plik **CompanyPortal.dmg** można bezpiecznie otworzyć. Po otwarciu go z folderu **Pobrane rzeczy** przeciągnij aplikację **CompanyPortal** na folder **Aplikacje**.

3. Otwórz folder **Aplikacje** lub **Launchpad**, a następnie otwórz aplikację **Portal firmy**.

4. Komputer Mac wyświetli komunikat **„CompanyPortal” to aplikacja pobrana z Internetu. Czy na pewno chcesz ją otworzyć?** Kliknij pozycję **Otwórz**.

  > [!NOTE]
  > Usługa Intune musi mieć dostęp do komputera, aby sprawdzić, czy urządzenie jest wystarczająco bezpieczne, aby mogło uzyskiwać dostęp do zasobów organizacji. Jeśli Twój komputer odmawia otwarcia aplikacji Portal firmy, spróbuj [wyłączyć funkcję Gatekeeper](https://support.apple.com/HT202491) i wtedy otworzyć aplikację.

6. Pierwszy ekran wyświetlony w aplikacji Portal firmy poprosi Cię o **zalogowanie się** za pomocą tego samego konta służbowego, które zostało użyte do zalogowania się do witryny internetowej Portal firmy.

7. Portal firmy potwierdzi informacje o Twoim koncie, a następnie wyświetli stan **rejestracji urządzenia** i **zgodności urządzenia**. Żółte trójkąty będą informować o akcjach, które trzeba wykonać, aby zagwarantować, że komputera Mac można bezpiecznie używać do pracy. Kliknij przycisk **Rozpocznij**, aby zacząć [rejestrowanie urządzenia w systemie zarządzania](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md).

8. Komputer Mac zacznie rejestrację w systemie zarządzania. Może wtedy zostać wyświetlony monit o podanie informacji logowania na komputerze. Rejestracja może zająć kilka minut. W tym czasie można robić inne rzeczy na komputerze. Gdy konfigurowanie dostępu do zasobów firmy zostanie zakończone, pojawi się odpowiedni komunikat.

Nadal potrzebujesz pomocy? Skontaktuj się z działem pomocy technicznej Twojej firmy. Odpowiednie informacje kontaktowe możesz znaleźć w [witrynie aplikacji Portal firmy](https://portal.manage.microsoft.com).
