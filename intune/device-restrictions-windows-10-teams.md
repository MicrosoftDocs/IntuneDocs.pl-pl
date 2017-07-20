---
title: "Ograniczenia urządzenia z systemem Windows 10 Team w usłudze Intune"
titleSuffix: Intune on Azure
description: "Informacje na temat ograniczeń urządzenia dotyczących urządzeń z systemem Windows 10 Team."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 677c41a2-5344-4c52-85f0-809dce3a5d5b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6e7e6e5093b09d7a221083cd36a8d3e5ecbbb8c2
ms.sourcegitcommit: f100c943a635f5a08254ba7cf30f1aaebb7e810e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/13/2017
---
# <a name="windows-10-team-device-restriction-settings-in-microsoft-intune"></a>Ustawienia ograniczeń urządzenia z systemem Windows 10 Team w usłudze Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

- **Włącz ekran, gdy ktoś jest w pokoju** — umożliwia automatyczne wyjście urządzenia z trybu uśpienia, gdy czujnik wykryje czyjąś obecność w pomieszczeniu.
- **Numer PIN projekcji bezprzewodowej** — określa, czy przed korzystaniem z funkcji projekcji bezprzewodowej na urządzeniu jest wymagane wprowadzenie numeru PIN.
- **Projekcja bezprzewodowa Miracast** — jeśli chcesz zezwolić urządzeniu z systemem Windows 10 Team na korzystanie z projekcji przy użyciu urządzeń z funkcją Miracast, wybierz tę opcję.
- **Informacje o spotkaniu wyświetlane na ekranie powitalnym** — włącz tę opcję, aby wybrać informacje wyświetlane na kafelku Spotkania na ekranie powitalnym. Można:
    - wybrać opcję **Pokaż tylko organizatora i czas**;
    - wybrać opcję **Pokaż organizatora, czas i temat (temat jest ukryty w przypadku spotkań prywatnych)**.
- **Adres URL obrazu tła ekranu powitalnego** — włącz to ustawienie, aby na ekranie **Witamy** urządzeń z systemem Windows 10 Team wyświetlić niestandardowe tło z określonego adresu URL.<br>Obraz musi być w formacie PNG, a adres URL musi rozpoczynać się od **https://**.
- **Okno konserwacji dla aktualizacji** — konfiguruje okno czasowe, w którym można przeprowadzać aktualizacje na urządzeniu. Możesz skonfigurować czas rozpoczęcia i czas trwania tego okresu (od 1 do 5 godzin).
- **Azure Operational Insights** — usługa Azure Operational Insights, która wchodzi w skład pakietu Microsoft Operations Manager, umożliwia zbieranie, przechowywanie i analizowanie danych pliku dziennika z urządzeń z systemem Windows 10 Team.<br>Aby połączyć z usługą Azure Operational Insights, należy określić **identyfikator obszaru roboczego** i **klucz obszaru roboczego**.

## <a name="next-steps"></a>Następne kroki

Skorzystaj z informacji w artykule [Jak skonfigurować ustawienia ograniczeń urządzeń](device-restrictions-configure.md), aby zapisać i przypisać profil do użytkowników i urządzeń.
