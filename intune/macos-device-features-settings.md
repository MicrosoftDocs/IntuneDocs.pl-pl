---
title: Ustawienia funkcji urządzeń z systemem macOS w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zobacz wszystkie ustawienia służące do konfigurowania urządzeń z systemem macOS na potrzeby funkcji AirPrint w usłudze Microsoft Intune. Zapoznaj się również z krokami wymaganymi do pobrania ustawień adresu IP, ścieżki i portu serwera funkcji AirPrint w sieci. Te ustawienia zastosowane w profilu konfiguracji urządzenia umożliwiają skonfigurowanie urządzeń z systemem macOS do korzystania z serwerów funkcji AirPrint w sieci.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: ''
ms.custom: intune-azure
ms.openlocfilehash: cdc5f5fe2c94dee2349cab777c7671c2673f52b2
ms.sourcegitcommit: e08a26558174be3ea8f3d20646e577f1493ea21a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54832605"
---
# <a name="macos-device-feature-settings-in-intune"></a>Ustawienia funkcji urządzenia z systemem macOS w usłudze Intune

Usługa Intune oferuje wbudowane ustawienia, które umożliwiają użytkownikom systemu macOS drukowanie na drukarkach AirPrint w sieci. Ten artykuł zawiera listę tych ustawień i opisy zadań poszczególnych ustawień. Przedstawiono w nim również listę czynności wymaganych do uzyskania adresu IP, ścieżki i portu drukarek AirPrint przy użyciu aplikacji Terminal (emulatora).

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji urządzenia sieci macOS](device-features-configure.md).

## <a name="airprint-settings"></a>Ustawienia funkcji AirPrint

1. W obszarze **Ustawienia** wybierz pozycję **AirPrint**. Wprowadź następujące właściwości serwera funkcji AirPrint:

    - **Adres IP**: wprowadź adres IPv4 lub IPv6 drukarki. Jeśli do identyfikowania drukarek używasz nazw hostów, możesz uzyskać adres IP, wysyłając polecenie ping do drukarki w aplikacji Terminal. Dalsze szczegółowe informacje można znaleźć w sekcji [Uzyskiwanie adresu IP i ścieżki](#get-the-ip-address-and-path) (w tym artykule).
    - **Ścieżka**: wprowadź ścieżkę drukarki. W przypadku drukarek w sieci ścieżka to zazwyczaj `ipp/print`. Dalsze szczegółowe informacje można znaleźć w sekcji [Uzyskiwanie adresu IP i ścieżki](#get-the-ip-address-and-path) (w tym artykule).
    - **Port**: wprowadź port nasłuchiwania miejsca docelowego funkcji AirPrint. Jeśli ta właściwość pozostanie pusta, funkcja AirPrint będzie używać portu domyślnego. Ustawienie dostępne w systemie iOS 11.0 i jego nowszych wersjach.
    - **TLS**: wybierz pozycję **Włącz**, aby zabezpieczyć połączenia funkcji AirPrint przy użyciu protokołu Transport Layer Security (TLS). Ustawienie dostępne w systemie iOS 11.0 i jego nowszych wersjach.

2. Wybierz pozycję **Dodaj**. Serwer funkcji AirPrint został dodany do listy. Można dodać wiele serwerów z funkcją AirPrint.

    Można również **zaimportować** plik rozdzielany przecinkami (CSV) zawierający listę drukarek z funkcją AirPrint. Po dodaniu drukarek z funkcją AirPrint w usłudze Intune można również **wyeksportować** tę listę.

3. Po zakończeniu wybierz przycisk **OK**, aby zapisać listę.

## <a name="get-the-ip-address-and-path"></a>Uzyskiwanie adresu IP i ścieżki

Aby dodać serwery funkcji AirPrinter, potrzebujesz adresu IP drukarki, ścieżki zasobu i portu. Poniższe kroki przedstawiają sposób uzyskiwania tych informacji.

1. Na komputerze Mac podłączonym do tej samej sieci lokalnej (podsieci) co drukarki AirPrint otwórz **Terminal** (z folderu **/Applications/Utilities**).
2. W aplikacji Terminal wpisz `ippfind`, a następnie wybierz klawisz Enter.

    Zanotuj informacje o drukarce. Zwrócone informacje mogą wyglądać podobnie do następujących: `ipp://myprinter.local.:631/ipp/port1`. Pierwsza część to nazwa drukarki. Ostatnia część (`ipp/port1`) to ścieżka zasobu.

3. W terminalu wpisz `ping myprinter.local`, a następnie wybierz klawisz Enter.

   Zanotuj adres IP. Zwrócone informacje mogą wyglądać podobnie do następujących: `PING myprinter.local (10.50.25.21)`.

4. Użyj wartości adresu IP i ścieżki zasobu. W tym przykładzie adres IP to `10.50.25.21`, a ścieżka zasobu to `/ipp/port1`.

## <a name="next-steps"></a>Następne kroki

- Wyświetl wszystkie ustawienia urządzeń z systemem [iOS](ios-device-features-settings.md).
- Przypisz ten profil do grup; zobacz temat dotyczący [przypisywania profilów urządzeń](device-profile-assign.md).