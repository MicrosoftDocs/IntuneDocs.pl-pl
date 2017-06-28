---
title: Ustawienia zasad konfiguracji systemu Windows Team
description: "**Ogólne zasady konfiguracji systemu Windows 10 Team dla usługi Microsoft Intune** umożliwiają konfigurowanie ustawień zarejestrowanych urządzeń z systemem Windows 10 Team, takich jak Microsoft Surface Hub."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38194ef3-e26e-4682-958d-14b395fccba1
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 6e0f0ea969ed78f2daf482438b056c8b4eb1a316
ms.contentlocale: pl-pl
ms.lasthandoff: 06/08/2017


---

# <a name="windows-team-configuration-policy-settings-in-microsoft-intune"></a>Ustawienia zasad konfiguracji systemu Windows Team w usłudze Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

**Ogólne zasady konfiguracji systemu Windows 10 Team** dla usługi Microsoft Intune umożliwiają konfigurowanie ustawień zarejestrowanych urządzeń z systemem Windows 10 Team, takich jak Microsoft Surface Hub.

|Nazwa ustawienia|Szczegóły|
|----------------|-----------|
|**Zezwalaj na automatyczne obudzenie ekranu, gdy ktoś jest w pokoju**|Umożliwia automatyczne wznowienie działania urządzenia, gdy czujnik wykryje czyjąś obecność w pomieszczeniu.|
|**Wymagaj numeru PIN dla projekcji bezprzewodowej**|Określa, czy do korzystania z funkcji projekcji bezprzewodowej na urządzeniu jest wymagane wprowadzenie numeru PIN.|
|**Konfiguruj okno obsługi aktualizacji urządzenia**|Konfiguruje czas, w którym można przeprowadzać aktualizacje na urządzeniu. Możesz skonfigurować czas rozpoczęcia i czas trwania tego okresu (od 1 do 5 godzin).|
|**Włączanie usługi Azure Operational Insights**|Usługa Azure Operational Insights, część pakietu programu Microsoft Operations Manager, umożliwia zbieranie, przechowywanie i analizowanie danych pliku dziennika z urządzeń z systemem Windows 10 Team.<br /><br />Aby połączyć z usługą Azure Operational Insights, należy określić **identyfikator obszaru roboczego** i **klucz obszaru roboczego**.|
|**Włączanie bezprzewodowej projekcji Miracast**|Włącz tę opcję, jeśli chcesz zezwolić urządzeniu z systemem Windows 10 Team na korzystanie w projekcie z urządzeń z włączoną technologią Miracast.<br /><br />Po włączeniu tej opcji z listy **Wybierz kanał Miracast** wybierz kanał Miracast używany dla zawartości projektu.|
|**Wybieranie informacji o spotkaniach wyświetlanych na ekranie powitalnym**|Jeśli ta opcja zostanie włączona, będzie można wybrać informacje do wyświetlenia na kafelku **Spotkania** na ekranie **powitalnym**. Można:<br /><br />-   **Pokaż tylko organizatora i czas**<br />-   **Pokaż organizatora, czas i temat (temat jest ukryty w przypadku spotkań prywatnych)**|
|**Adres URL obrazu tła blokady ekranu**|Włącz to ustawienie, aby na ekranie **powitalnym** urządzenia z systemem Windows 10 Team wyświetlić niestandardowe tło z wybranego adresu URL.<br /><br />Obraz musi być w formacie PNG, a adres URL musi rozpoczynać się od **https://**.|


### <a name="see-also"></a>Zobacz także
[Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)


