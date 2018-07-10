---
title: Tworzenie powiązań urządzeń z systemem Android według lokalizacji sieciowej w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Tworzenie lub konfigurowanie lokalizacji sieciowych w usłudze Microsoft Intune dla urządzeń z systemem Android. Urządzenia można oznaczać jako niezgodne w oparciu o lokalizację sieciową urządzenia. Jeśli urządzenie jest przenoszone poza lokalizację sieciową, można zablokować dostęp do zasobów firmy.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ayesham
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 988407d6d736b669854ef8420b71a092765162b7
ms.sourcegitcommit: 445fcf9e2a185e5c987334cad398bce71383be03
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/07/2018
ms.locfileid: "34843127"
---
# <a name="use-locations-network-fence-in-intune"></a>Korzystanie z lokalizacji (ogrodzenia sieci) w usłudze Intune

Dostęp do sieci firmowej można zablokować, jeśli urządzenie opuści lokalizację. Tę możliwość oferuje funkcja **Lokalizacje** w usłudze Intune. 

Można utworzyć zasady zgodności oparte na lokalizacji sieciowej — to rozwiązane jest znane również jako ogrodzenie sieci. Zasady gwarantują, że w celu zachowania zgodności urządzenia muszą być połączone z siecią służbową. Te zasady mogą być używane razem z zasadami dostępu warunkowego, aby urządzenia miały dostęp do zasobów *tylko*, gdy urządzenie będzie połączone z siecią służbową. Jeśli urządzenie nie jest połączone z siecią służbową, staje się niezgodne i traci dostęp do zasobów służbowych.

Rozważmy następujący scenariusz:

W Twoim zakładzie produkcyjnym niektórzy pracownicy używają urządzeń z systemem Android. Pracownik zabiera urządzenie z systemem Android poza teren zakładu lub fabryki. Aby zapobiec nieautoryzowanemu dostępowi, można:

1. Utworzyć lokalizację z zakresem adresów IPv4 o nazwie **Dział produkcyjny**.
2. Utworzyć zasady zgodności, które wymagają połączenia tych urządzeń z siecią firmową, a następnie przypisać te zasady.
3. Jeśli urządzenie znajdzie się poza zakładem produkcyjnym, będzie uznawane za niezgodne i nie będzie mieć dostępu do zasobów firmy.

Ponadto można dodać [akcje w przypadku niezgodności](#configure-the-actions-for-noncompliance). Gdy urządzenie znajdzie się z powrotem w środowisku lokalnym i w zasięgu lokalizacji sieciowej, odzyska dostęp do zasobów firmy.

## <a name="prerequisites"></a>Wymagania wstępne

Aby utworzyć zasady zgodności na podstawie lokalizacji:

- Utwórz lokalizację sieciową w postaci zakresów sieci IPv4 dla serwera bramy, serwera DHCP i/lub serwera DNS, z którą łączą się urządzenia
- Utwórz zasady zgodności, które korzystają z tych lokalizacji i definiują akcję do podjęcia, gdy urządzenie nie jest już połączone z lokalizacją sieciową
- Urządzenia z systemem Android 6.0 lub nowszym ze zaktualizowaną aplikacją Portal firmy

## <a name="create-a-location"></a>Tworzenie lokalizacji

1. W usłudze Intune wybierz kolejno pozycje **Zgodność urządzenia** > **Lokalizacje** > **Utwórz**.

2. Wprowadź następujące właściwości:  

   - Element wymagany. Wprowadź **nazwę** lokalizacji, taką jak **Dział produkcyjny** lub **Budynek nr 44 — zabezpieczona**.
   - Opcjonalny. Wprowadź **zakres adresów IPv4** w notacji CIDR (Classless Interdomain Routing), taki jak `aaa.bbb.ccc.ddd/n`.
   - Opcjonalny. Wprowadź adres **bramy IPv4**, taki jak `aaa.bbb.ccc.ddd`.
   - Opcjonalny. Wprowadź adres **serwera DHCP IPv4**, taki jak `aaa.bbb.ccc.ddd`.
   - Opcjonalny. Wprowadź listę adresów **serwerów DNS IPv4**. To ustawienie używa **dopasowywania podzestawów**. Jeśli serwery DNS IPv4 na urządzeniu są podzestawami wartości zdefiniowanych, urządzenie jest uznawane za znajdujące się W OBRĘBIE ogrodzenia. Upewnij się, że wprowadzasz jeden adres w każdym wierszu, taki jak:  
     `aaa.bbb.ccc.ddd`  
     `aaa.bbb.ccc.ddd`
   - Opcjonalny. Wprowadź listę **sufiksów DNS**. To ustawienie używa **dopasowywania podzestawów**. Jeśli sufiksy DNS na urządzeniu są podzestawami wartości zdefiniowanych, urządzenie jest uznawane za znajdujące się W OBRĘBIE ogrodzenia. Upewnij się, że wprowadzasz jedną nazwę domeny w każdym wierszu, taką jak:  
     `contoso.com`  
     `contoso.org`

3. **Zapisz** zmiany.

## <a name="create-the-location-compliance-policy"></a>Tworzenie zasad zgodności lokalizacji

Podczas tworzenia zasad zgodności wybierz pozycję **Android** w polu **Platforma**. W obszarze **Lokalizacje** możesz wybrać co najmniej jedną z dodanych lokalizacji sieciowych. Lokalizacje te są częścią ogrodzenia sieci, które tworzysz dla urządzeń.

Wskazówki można znaleźć w temacie [Tworzenie zasad zgodności na podstawie lokalizacji sieciowej](compliance-policy-create-android.md#locations).

## <a name="configure-the-actions-for-noncompliance"></a>Konfigurowanie akcji w przypadku niezgodności

Po utworzeniu zasad zgodności na urządzeniu w przypadku niezgodności zostanie zastosowana akcja domyślna. Możesz dodać więcej akcji. Na przykład dodaj akcję, która wysyła wiadomość e-mail do użytkownika, gdy urządzenie nie jest już zgodne z lokalizacjami.

Wskazówki można znaleźć w temacie [Dodawanie akcji w przypadku niezgodności](actions-for-noncompliance.md).

## <a name="company-portal-app"></a>Aplikacji Portal firmy

Urządzenie połączone z lokalizacją jest wyświetlane jako zgodne w aplikacji Portal firmy. Urządzenie niepołączone z jedną z lokalizacji jest wyświetlane jako niezgodne.

## <a name="next-steps"></a>Następne kroki
[Monitorowanie zasad zgodności urządzeń](compliance-policy-monitor.md)  
[Wprowadzenie do zasad zgodności](device-compliance-get-started.md)
