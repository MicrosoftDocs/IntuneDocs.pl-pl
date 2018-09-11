---
title: Rejestrowanie udostępnionego przez organizację urządzenia z systemem macOS na potrzeby zarządzania | Microsoft Docs
description: Opis sposobu rejestrowania w usłudze Intune urządzenia z systemem macOS, które zostało zakupione i udostępnione przez Twoją organizację.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
searchScope:
- User help
ROBOTS: ''
ms.reviewer: japoehlm
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: a5808a0ac80390b76058827d2ca0870249b043b9
ms.sourcegitcommit: 11cad61c565c474a8d653181675cc1109d562626
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/29/2018
ms.locfileid: "43241834"
---
# <a name="enroll-your-organization-provided-macos-device-in-management"></a>Rejestrowanie udostępnionego przez organizację urządzenia z systemem macOS na potrzeby zarządzania

Dowiedz się, jak umożliwić zarządzanie nowym urządzeniem z systemem macOS w usłudze Intune.  

Urządzenia, które są dostarczane przez pracodawcę lub szkołę, często są wstępnie skonfigurowane przed ich odebraniem. Twoja organizacja będzie wysyłać te wstępnie skonfigurowane ustawienia do urządzenia, gdy włączysz je i zalogujesz się po raz pierwszy. Po ukończeniu konfiguracji urządzenia otrzymasz dostęp do zasobów służbowych. 

Aby rozpocząć konfigurowanie zarządzania, włącz zasilanie urządzenia i zaloguj się przy użyciu poświadczeń służbowych. W pozostałej części tego artykułu opisano kroki i ekrany, które zobaczysz w miarę poruszania się po Asystencie ustawień.   

## <a name="what-is-apple-dep"></a>Co to jest program Apple DEP?
Twoja organizacja mogła zakupić urządzenia za pośrednictwem programu zwanego *Apple Device Enrollment Program* (DEP). Program Apple DEP umożliwia organizacjom kupowanie wielu urządzeń z systemem iOS lub macOS. Organizacje mogą następnie konfigurować te urządzenia i zarządzać nimi przy użyciu preferowanego dostawcy zarządzania urządzeniami przenośnymi, takimi jak usługa Intune. Jeśli jesteś administratorem i chcesz dowiedzieć się więcej o programie Apple DEP, zobacz [Automatyczne rejestrowanie urządzeń z systemem macOS w ramach programu Device Enrollment Program firmy Apple](https://docs.microsoft.com/intune/device-enrollment-program-enroll-macos).  

## <a name="set-up-your-macos-device"></a>Konfigurowanie urządzenia z systemem macOS  
Wykonaj poniższe kroki, aby zarejestrować urządzenie z systemem macOS na potrzeby zarządzania. Jeśli używasz własnego urządzenia, a nie urządzenia dostarczonego przez organizację, wykonaj kroki dotyczące [urządzeń osobistych i przyniesionych przez siebie](enroll-your-device-in-intune-macos-cp.md).  

1. Włącz zasilanie urządzenia z systemem macOS. 
2. Wybierz **język** i kliknij pozycję **Kontynuuj**.  

   ![Zrzut ekranu przedstawiający ekran powitalny Asystenta konfiguracji urządzenia z systemem macOS z listą języków do wyboru.](./media/macos-dep-welcome-1808.png)   
3. Wybierz układ klawiatury. Lista zawiera co najmniej jedną opcję w oparciu o wybrany język. Aby wyświetlić wszystkie opcje układu, bez względu na wybrany język, kliknij pozycję **Pokaż wszystko**. Po zakończeniu kliknij przycisk **Kontynuuj**.  

   ![Zrzut ekranu Układ klawiatury Asystenta ustawień urządzenia z systemem macOS z listą języków klawiatury do wyboru, niezaznaczoną opcją Pokaż wszystkie oraz przyciskami Wstecz i Kontynuuj.](./media/macos-dep-keyboard-1808.png)  
4. Wybierz sieć Wi-Fi. Musisz mieć połączenie internetowe, aby kontynuować instalację. Jeśli nie widzisz swojej sieci lub jeśli musisz nawiązać połączenie za pośrednictwem sieci przewodowej, kliknij pozycję **Inne opcje sieciowe**. Po zakończeniu kliknij przycisk **Kontynuuj**.  

   ![Zrzut ekranu Wybieranie sieci Wi-Fi Asystenta ustawień urządzenia z systemem macOS z listą dostępnych sieci do wyboru. Przedstawia on również przycisk Inne opcje sieciowe, przycisk Wstecz i przycisk Kontynuuj.](./media/macos-dep-wifi-1808.png)  
5. Po połączeniu z siecią Wi-Fi zostanie wyświetlony ekran **Zarządzanie zdalne**. Zarządzanie zdalne umożliwia administratorowi organizacji zdalne konfigurowanie urządzenia przy użyciu wymaganych przez firmę kont, ustawień, aplikacji i sieci. Zanim przejdziesz dalej, zapoznaj się z dokumentacją, która pomoże Ci zrozumieć, jak Twoje urządzenie jest zarządzane. Następnie kliknij przycisk **Kontynuuj**.  

   ![Zrzut ekranu Zarządzanie zdalne Asystenta ustawień urządzenia z systemem macOS z tekstem objaśniającym zarządzanie zdalne i linkiem do dokumentacji zawierającej dalsze informacje. Przedstawia on również przycisk Wstecz i przycisk Kontynuuj.](./media/macos-dep-remote-management-1-1808.png)  
6. Po wyświetleniu monitu zaloguj się przy użyciu konta służbowego. Po uwierzytelnieniu użytkownika urządzenie zainstaluje profil zarządzania. Profil konfiguruje zasoby organizacji i umożliwia dostęp do nich.  
7. Zapoznaj się z informacjami wyświetlanymi po użyciu ikony danych i ochrony prywatności firmy Apple, aby później zidentyfikować moment zbierania danych osobowych. Następnie kliknij przycisk **Kontynuuj**.  

   ![Zrzut ekranu Dane i prywatność Asystenta ustawień urządzenia z systemem macOS z ilustracją przedstawiającą dwie osoby wymieniające uścisk dłoni oraz opisem sposobu używania danych osobowych przez firmę Apple. Przedstawia on również przyciski Wstecz i Kontynuuj.](./media/macos-dep-apple-data-privacy-1808.png)  
8. Po zarejestrowaniu urządzenia być może trzeba będzie wykonać dodatkowe kroki. Wyświetlone kroki zależą od tego, jak Twoja organizacja dostosowała środowisko konfiguracji. Konieczne może być:
    * Zalogowanie do konta Apple
    * Zaakceptowanie warunków i postanowień
    * Utworzenie konta komputera
    * Przeprowadzenie instalacji ekspresowej
    * Skonfigurowanie komputera Mac  
## <a name="get-the-company-portal-app"></a>Pobranie aplikacji Portal firmy      
Przejdź do sklepu App Store, aby pobrać aplikację Portal firmy usługi Intune na swoje urządzenie. Ta aplikacja umożliwia monitorowanie, synchronizowanie, dodawanie i usuwanie urządzenia z zarządzania oraz instalowanie aplikacji.

Nadal potrzebujesz pomocy? Skontaktuj się z pomocą techniczną Twojej firmy. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).
