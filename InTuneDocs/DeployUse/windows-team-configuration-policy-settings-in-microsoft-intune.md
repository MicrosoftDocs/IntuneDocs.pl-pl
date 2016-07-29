---
title: Ustawienia zasad konfiguracji systemu Windows Team | Microsoft Intune
description: "**Ogólne zasady konfiguracji systemu Windows 10 Team dla usługi Microsoft Intune** umożliwiają konfigurowanie ustawień zarejestrowanych urządzeń z systemem Windows 10 Team, takich jak Microsoft Surface Hub."
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38194ef3-e26e-4682-958d-14b395fccba1
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a409d36c1c5fcfd3d81ce0cbdf1f69af4747157a
ms.openlocfilehash: b70c935fb5c4525fddf7e36e8421ba14e3c15026


---

# Ustawienia zasad konfiguracji systemu Windows Team w usłudze Microsoft Intune
**Ogólne zasady konfiguracji systemu Windows 10 Team** dla usługi Microsoft Intune umożliwiają konfigurowanie ustawień zarejestrowanych urządzeń z systemem Windows 10 Team, takich jak Microsoft Surface Hub.

|Nazwa ustawienia|Szczegóły|
|----------------|-----------|
|**Zezwalaj na automatyczne obudzenie ekranu, gdy ktoś jest w pokoju**|Umożliwia automatyczne wznowienie działania urządzenia, gdy czujnik wykryje czyjąś obecność w pomieszczeniu.|
|**Wymagaj numeru PIN dla projekcji bezprzewodowej**|Określa, czy do korzystania z funkcji projekcji bezprzewodowej na urządzeniu jest wymagane wprowadzenie numeru PIN.|
|**Konfiguruj okno obsługi aktualizacji urządzenia**|Konfiguruje czas, w którym można przeprowadzać aktualizacje na urządzeniu. Możesz skonfigurować czas rozpoczęcia i czas trwania tego okresu (od 1 do 5 godzin).|
|**Włączanie usługi Azure Operational Insights**|Usługa Azure Operational Insights, część pakietu programu Microsoft Operations Manager, umożliwia zbieranie, przechowywanie i analizowanie danych pliku dziennika z urządzeń z systemem Windows 10 Team.<br /><br />Aby połączyć z usługą Azure Operational Insights, należy określić **identyfikator obszaru roboczego** i **klucz obszaru roboczego**.|
|**Włączanie bezprzewodowej projekcji Miracast**|Włącz tę opcję, jeśli chcesz zezwolić urządzeniu z systemem Windows 10 Team na korzystanie w projekcie z urządzeń z włączoną technologią Miracast.<br /><br />Po włączeniu tej opcji z listy **Wybierz kanał Miracast** wybierz kanał Miracast używany dla zawartości projektu.|
|**Wybieranie informacji o spotkaniach wyświetlanych na ekranie powitalnym**|Jeśli ta opcja zostanie włączona, będzie można wybrać informacje do wyświetlenia na kafelku **Spotkania** na ekranie **powitalnym**. Można:<br /><br />-   **— pokazać tylko organizatora i czas**<br />-   **— pokazać organizatora, czas i temat (w przypadku spotkań prywatnych temat jest ukryty)**|
|**Adres URL obrazu tła blokady ekranu**|Włącz to ustawienie, aby na ekranie **powitalnym** urządzenia z systemem Windows 10 Team wyświetlić niestandardowe tło z wybranego adresu URL.<br /><br />Obraz musi być w formacie PNG, a adres URL musi rozpoczynać się od **https://**.|


### Zobacz także
[Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)




<!--HONumber=Jul16_HO3-->


