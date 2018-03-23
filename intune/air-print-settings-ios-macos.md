---
title: Ustawienia usługi Intune dotyczące funkcji AirPrint dla urządzeń z systemami iOS i macOS
titlesuffix: Microsoft Intune
description: Informacje na temat korzystania z usługi Microsoft Intune w celu umożliwienia automatycznego nawiązywania połączenia między urządzeniami z systemem iOS i macOS oraz zgodnymi drukarkami z funkcją AirPrint.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 02/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8402ff3631e18ec6169bc96ef1bb7669bdcfbdd8
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/17/2018
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

1. Z obszaru [Usługa Intune w witrynie Azure Portal](https://portal.azure.com) przejdź do obszaru [**Funkcje urządzenia** w obszarze konfiguracji urządzenia](device-features-configure.md). 
1. W okienku **Funkcje urządzenia** wybierz pozycję **AirPrint**.
2. Aby dodać miejsce docelowe funkcji AirPrint, w okienku **AirPrint** wpisz jej **adres IP** i **ścieżkę zasobu**, a następnie kliknij pozycję **Dodaj**.
3. W miarę potrzeby dodaj kolejne miejsca docelowe. Gdy skończysz, wybierz przycisk **OK**.

Możesz również zaimportować listę drukarek z pliku wartości rozdzielanych przecinkami (csv) lub wyeksportować listę.


## <a name="next-steps"></a>Następne kroki

Teraz można przypisać profil urządzenia do wybranych grup. Aby uzyskać szczegółowe informacje, zobacz [Przypisywanie profilów urządzeń](device-profile-assign.md).