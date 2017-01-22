---
title: "Konfigurowanie zarządzania systemem Android | Microsoft Docs"
description: "Włącz zarządzanie urządzeniami przenośnymi (MDM) dla urządzeń z systemem Android i KNOX Standard w usłudze Microsoft Intune."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 01/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dbe5cad1-3e0d-41a9-966b-738156089700
ms.reviewer: lacranda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 26ddc03985ab8a4959a1d2c9a47e77f042ab9310
ms.openlocfilehash: 6b74c09c37970429d3eaa571db655854d592a2fe


---

# <a name="set-up-android-device-management"></a>Konfigurowanie zarządzania urządzeniami z systemem Android

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Będąc administratorem usługi Intune, możesz włączyć zarządzanie urządzeniami z systemem Android, w tym urządzeniami Samsung Knox Standard, w Portalu firmy. Użytkownicy będą mogli wtedy rejestrować swoje urządzenia przy użyciu aplikacji Portal firmy dostępnej w sklepie Google Play.

1.  **Skonfiguruj usługę**<br>
    Jeśli usługa ta nie została jeszcze skonfigurowana, przygotuj się do zarządzania urządzeniami przenośnymi, [ustawiając urząd zarządzania urządzeniami przenośnymi](prerequisites-for-enrollment.md#step-2-set-mdm-authority) na usługę **Microsoft Intune** i konfigurując zarządzanie urządzeniami przenośnymi.

2.  **Włączona rejestracja systemu Android**<br>
    Żadne dodatkowe konfiguracje w konsoli usługi Intune nie są wymagane do włączenia rejestracji urządzeń przenośnych z systemem Android.

3.  **Poinformuj użytkowników, jak mogą zarejestrować swoje urządzenia w celu uzyskania dostępu do zasobów firmy.**

    Instrukcje dotyczące rejestrowania przez użytkownika końcowego można znaleźć w temacie [Rejestrowanie urządzenia z systemem Android w usłudze Intune](../enduser/enroll-your-device-in-intune-android.md). W trakcie procesu rejestracji użytkownicy są informowani, czego mogą oczekiwać, a także co administratorzy IT mogą i czego nie mogą wyświetlać na swoich urządzeniach.

    Aby uzyskać informacje o innych zadaniach użytkownika końcowego, zobacz następujące artykuły:
  - [Zasoby dotyczące środowiska użytkownika końcowego w usłudze Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
  - [Wskazówki dla użytkowników końcowych korzystających z urządzeń z systemem Android](../enduser/using-your-android-device-with-intune.md)

Z powodu braku dostępności sklepu Google Play w Chinach aplikację Portal firmy dla urządzeń z systemem Android należy uzyskać z chińskich platform handlowych oferujących aplikacje. Aplikacja Portal firmy dla systemu Android będzie dostępna do pobrania w następujących sklepach:
* [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
* [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
* [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
* [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)
* [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)

Aplikacja Portal firmy dla systemu Android używa usług Google Play do komunikowania się z usługą Microsoft Intune. Ponieważ usługi Google Play nie są jeszcze dostępne w Chinach, wykonanie dowolnego z wymienionych poniżej zadań może potrwać do 8 godzin. 

|Konsola administracyjna usługi Intune| Aplikacja Portal firmy w usłudze Intune dla systemu Android |Witryna aplikacji Portal firmy w usłudze Intune|   
|---|---|---|
|Pełne czyszczenie danych| Usuwanie urządzenia zdalnego| Usuwanie urządzenia (lokalnego i zdalnego)|
|Selektywne czyszczenie danych| Resetowanie urządzenia| Resetowanie urządzenia|
|Wdrażanie nowych lub zaktualizowanych aplikacji| Instalowanie dostępnych aplikacji biznesowych| Resetowanie kodu dostępu urządzenia|
|Zdalne blokowanie|||
|Resetowanie kodu dostępu|||

### <a name="see-also"></a>Zobacz także
[Wymagania wstępne dotyczące rejestrowania urządzeń w usłudze Microsoft Intune](prerequisites-for-enrollment.md)



<!--HONumber=Jan17_HO1-->


