---
title: "Ustawienia usługi Intune dotyczące funkcji AirPrint dla urządzeń z systemami iOS i macOS"
titlesuffix: Azure portal
description: "Informacje na temat korzystania z usługi Intune w celu umożliwienia automatycznego nawiązywania połączenia między urządzeniami z systemem iOS i macOS oraz zgodnymi drukarkami z funkcją AirPrint."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f0a0fde27f39873874669c2ea0b435f47ad763d5
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/09/2017
---
# <a name="airprint-settings-for-ios-and-macos-devices"></a>Ustawienia funkcji AirPrint dla urządzeń z systemami iOS i macOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Te ustawienia umożliwiają konfigurowanie urządzeń z systemem iOS lub macOS do automatycznego nawiązywania połączenia z drukarkami w sieci zgodnymi z funkcją AirPrint. Aby kontynuować, konieczna jest znajomość adresów IP i ścieżek zasobu drukarek.

## <a name="find-airprint-printer-information"></a>Znajdowanie informacji o drukarkach AirPrint

Wykonaj tę procedurę, aby dodać informacje o drukarkach AirPrint do ładunku AirPrint, dzięki czemu użytkownicy urządzeń z systemem iOS będą mieć możliwość drukowania z użyciem znanych drukarek AirPrint.

1. Na komputerze Mac podłączonym do tej samej sieci lokalnej (podsieci) co drukarki AirPrint otwórz Terminal (**/Programy/Narzędzia**)
2. W Terminalu wpisz polecenie **ippfind**, a następnie naciśnij klawisz Enter.
3. Zapisz wszystkie informacje o drukarkach wyświetlone w wynikach, np.: **ipp://myprinter.local.:631/ipp/port1**. Pierwszy fragment to nazwa drukarki. Drugi fragment to ścieżka zasobu.
4. W Terminalu wpisz polecenie **ping myprinter.local**, a następnie naciśnij klawisz Enter.
5. Zapisz informacje o adresie IP wyświetlone po wykonaniu polecenia, na przykład **PING myprinter.local (10.50.25.21)**.
6. Na koniec użyj adresu IP i ścieżki zasobu w ustawieniach ładunku AirPrint. Przykładowy adres IP to **10.50.25.21**, a przykładowa ścieżka zasobu to **/ipp/port1**.

## <a name="configure-an-airprint-profile"></a>Konfigurowanie profilu AirPrint

1. W bloku **Funkcje urządzenia** wybierz pozycję **AirPrint**.
2. Aby dodać miejsce docelowe funkcji AirPrint, wpisz w bloku **AirPrint** jego **adres IP** i **ścieżkę zasobu**, a następnie kliknij przycisk **Dodaj**.
3. W miarę potrzeby dodaj kolejne miejsca docelowe. Gdy skończysz, wybierz przycisk **OK**.

Możesz również zaimportować listę drukarek z pliku wartości rozdzielanych przecinkami (csv) lub wyeksportować listę.


## <a name="next-steps"></a>Następne kroki

Teraz można przypisać profil urządzenia do wybranych grup. Aby uzyskać szczegółowe informacje, zobacz [Przypisywanie profilów urządzeń](device-profile-assign.md).