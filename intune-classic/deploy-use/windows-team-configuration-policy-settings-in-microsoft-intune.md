---
title: Ustawienia zasad konfiguracji systemu Windows Team
description: '**Ogólne zasady konfiguracji systemu Windows 10 Team** dla usługi Microsoft Intune umożliwiają konfigurowanie ustawień zarejestrowanych urządzeń z systemem Windows 10 Team, takich jak Microsoft Surface Hub.'
keywords: ''
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 38194ef3-e26e-4682-958d-14b395fccba1
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 70b1091cd58439b7d42eab1a612b0b63ca39103d
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="windows-team-configuration-policy-settings-in-microsoft-intune"></a>Ustawienia zasad konfiguracji systemu Windows Team w usłudze Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

**Ogólne zasady konfiguracji systemu Windows 10 Team** dla usługi Microsoft Intune umożliwiają konfigurowanie ustawień zarejestrowanych urządzeń z systemem Windows 10 Team, takich jak Microsoft Surface Hub.


|                                  Nazwa ustawienia                                   |                                                                                                                                                                Szczegóły                                                                                                                                                                |
|---------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <strong>Zezwalaj na automatyczne obudzenie ekranu, gdy ktoś jest w pokoju</strong>   |                                                                                                                         Umożliwia automatyczne wznowienie działania urządzenia, gdy czujnik wykryje czyjąś obecność w pomieszczeniu.                                                                                                                          |
|              <strong>Wymagaj numeru PIN dla projekcji bezprzewodowej</strong>               |                                                                                                             Określa, czy do korzystania z funkcji projekcji bezprzewodowej na urządzeniu jest wymagane wprowadzenie numeru PIN.                                                                                                             |
|          <strong>Konfiguruj okno obsługi aktualizacji urządzenia</strong>           |                                                                                          Konfiguruje czas, w którym można przeprowadzać aktualizacje na urządzeniu. Możesz skonfigurować czas rozpoczęcia i czas trwania tego okresu (od 1 do 5 godzin).                                                                                           |
|               <strong>Włączanie usługi Azure Operational Insights</strong>                |                  Usługa Azure Operational Insights, część pakietu programu Microsoft Operations Manager, umożliwia zbieranie, przechowywanie i analizowanie danych pliku dziennika z urządzeń z systemem Windows 10 Team.<br /><br />Aby połączyć z usługą Azure Operational Insights, należy określić <strong>identyfikator obszaru roboczego</strong> i <strong>klucz obszaru roboczego</strong>.                   |
|              <strong>Włączanie bezprzewodowej projekcji Miracast</strong>               |                                          Włącz tę opcję, jeśli chcesz zezwolić urządzeniu z systemem Windows 10 Team na korzystanie w projekcie z urządzeń z włączoną technologią Miracast.<br /><br />Po włączeniu tej opcji z listy <strong>Wybierz kanał Miracast</strong> wybierz kanał Miracast używany dla zawartości projektu.                                           |
| <strong>Wybieranie informacji o spotkaniach wyświetlanych na ekranie powitalnym</strong> | Jeśli ta opcja zostanie włączona, będzie można wybrać informacje do wyświetlenia na kafelku <strong>Spotkania</strong> na ekranie <strong>powitalnym</strong>. Można:<br /><br />-   <strong>Pokaż tylko organizatora i czas</strong><br />-   <strong>Pokaż organizatora, czas i temat (temat jest ukryty w przypadku spotkań prywatnych)</strong> |
|                <strong>Adres URL obrazu tła blokady ekranu</strong>                 |                                           Włącz to ustawienie, aby na ekranie <strong>powitalnym</strong> urządzenia z systemem Windows 10 Team wyświetlić niestandardowe tło z wybranego adresu URL.<br /><br />Obraz musi być w formacie PNG, a adres URL musi rozpoczynać się od <strong>https://</strong>.                                            |

### <a name="see-also"></a>Zobacz też
[Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

