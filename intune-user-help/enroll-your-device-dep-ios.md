---
title: Rejestrowanie udostępnionego przez organizację urządzenia z systemem iOS na potrzeby zarządzania | Microsoft Docs
description: Opis sposobu rejestrowania w usłudze Intune urządzenia z systemem iOS, które zostało zakupione i udostępnione przez Twoją organizację
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f4e7d87e-56d1-43e4-8e88-2f62cf0999e2
searchScope:
- User help
ROBOTS: ''
ms.reviewer: japoehlm
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: b93f02011b0900b1a64ae6cb10a84a52cd40187a
ms.sourcegitcommit: 11cad61c565c474a8d653181675cc1109d562626
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/29/2018
ms.locfileid: "43241800"
---
# <a name="enroll-your-organization-provided-ios-device-in-management"></a>Rejestrowanie udostępnionego przez organizację urządzenia z systemem iOS na potrzeby zarządzania

Dowiedz się, jak umożliwić zarządzanie nowym urządzeniem z systemem iOS w usłudze Intune.  

Urządzenia z systemem iOS, które są dostarczane przez pracodawcę lub szkołę, często są wstępnie skonfigurowane przed ich odebraniem. Twoja organizacja będzie wysyłać te wstępnie skonfigurowane ustawienia do urządzenia, gdy włączysz je i zalogujesz się po raz pierwszy. Po ukończeniu konfiguracji urządzenia otrzymasz dostęp do zasobów służbowych.  

Aby rozpocząć konfigurowanie, włącz zasilanie urządzenia i zaloguj się przy użyciu poświadczeń służbowych. W pozostałej części tego artykułu opisano kroki i ekrany, które zobaczysz w miarę poruszania się po Asystencie ustawień. 

## <a name="what-is-apple-dep"></a>Co to jest program Apple DEP?
Twoja organizacja mogła zakupić urządzenia za pośrednictwem programu zwanego *Apple Device Enrollment Program* (DEP). Program Apple DEP umożliwia organizacjom kupowanie wielu urządzeń z systemem iOS lub macOS. Organizacje mogą następnie konfigurować te urządzenia i zarządzać nimi przy użyciu preferowanego dostawcy zarządzania urządzeniami przenośnymi, takimi jak usługa Intune. Jeśli jesteś administratorem i chcesz dowiedzieć się więcej o programie Apple DEP, zobacz [Automatyczne rejestrowanie urządzeń z systemem iOS w ramach programu Device Enrollment Program firmy Apple](https://docs.microsoft.com/intune/device-enrollment-program-enroll-ios).  

## <a name="set-up-your-ios-device"></a>Konfigurowanie urządzenia z systemem iOS  
Jeśli używasz własnego urządzenia z systemem iOS, a nie urządzenia dostarczonego przez organizację, wykonaj kroki dotyczące [urządzeń osobistych i przyniesionych przez siebie](enroll-your-device-in-intune-ios.md).  

1. Włącz urządzenie z systemem iOS. 
2. Po wybraniu **języka** podłącz urządzenie do sieci Wi-Fi.
3. Na ekranie **Konfiguruj urządzenie z systemem iOS** wybierz opcję, z której chcesz skorzystać: 
 
   - **Konfiguruj jako nowe urządzenie**
   - **Przywróć z kopii zapasowej w usłudze iCloud**
   - **Przywróć z kopii zapasowej w usłudze iTunes**

4. Po podłączeniu do sieci Wi-Fi zostanie wyświetlony ekran **Konfiguracja**. Na ekranie zostanie wyświetlona informacja **[Twoja firma] automatycznie skonfiguruje Twoje urządzenie.**

   **Konfiguracja umożliwia [Twojej firmie] zarządzanie tym urządzeniem bez udziału użytkownika. Administrator może pomóc Ci w konfigurowaniu kont poczty e-mail i kont sieciowych, instalowaniu i konfigurowaniu aplikacji oraz zdalnym zarządzaniu ustawieniami. Administrator może wyłączać funkcje, instalować i usuwać aplikacje, monitorować i ograniczać ruch internetowy oraz zdalnie wymazać to urządzenie.**
 
   **Konfiguracja jest dostarczana przez: zespół ds. iOS [Twoja firma] [Adres]**

5. Zaloguj się przy użyciu swojego identyfikatora Apple ID. Zalogowanie umożliwia zainstalowanie aplikacji Portal firmy i zainstalowanie profilu zarządzania, który umożliwi uzyskanie dostępu do zasobów firmy, takich jak poczta e-mail i aplikacje. 
6. Zaakceptuj **warunki i postanowienia**, a następnie zdecyduj, czy chcesz wysłać firmie Apple informacje diagnostyczne.
7. Po zakończeniu rejestracji urządzenie może wyświetlać monity o podjęcie dalszych działań. Niektóre z tych kroków mogą wymagać wprowadzenia hasła dostępu do poczty e-mail lub skonfigurowania kodu dostępu.

Nadal potrzebujesz pomocy? Skontaktuj się z pomocą techniczną Twojej firmy. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).
