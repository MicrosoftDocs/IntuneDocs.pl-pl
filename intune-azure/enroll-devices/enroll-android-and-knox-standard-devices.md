---
title: "Rejestrowanie urządzeń z systemem Android w usłudze Intune | Wersja zapoznawcza usługi Intune Azure | Dokumentacja firmy Microsoft"
description: "Wersja zapoznawcza usługi Intune Azure: informacje dotyczące rejestrowania urządzeń z systemem Android w wersji zapoznawczej usługi Intune Azure."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 12/16/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: edd6303f3bb05dfff758cbb7d4bd08e21f083998


---

# <a name="enroll-android-devices"></a>Rejestrowanie urządzeń z systemem Android

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Będąc administratorem usługi Intune, możesz włączyć zarządzanie urządzeniami z systemem Android, w tym urządzeniami Samsung Knox Standard, w Portalu firmy. Użytkownicy będą mogli wtedy rejestrować swoje urządzenia przy użyciu aplikacji Portal firmy dostępnej w sklepie Google Play.

## <a name="prerequisite"></a>Wymaganie wstępne

Należy ustawić urząd MDM na wartość **Microsoft Intune**, aby przygotować się do zarządzania urządzeniami przenośnymi. Instrukcje znajdują się w artykule [Set the MDM authority](set-mdm-authority.md) (Ustawianie urzędu MDM). Element ten ustawia się tylko raz podczas pierwszej konfiguracji usługi Intune do zarządzania urządzeniami przenośnymi, więc być może jest on już ustawiony. 

## <a name="set-up-android-enrollment"></a>Konfiguracja rejestrowania urządzeń z systemem Android

Domyślnie usługa Intune jest konfigurowana do zezwalania na rejestrację urządzeń z systemem Android i programem Samsung Knox Standard. 

Aby wyświetlić ustawienie zezwalające na rejestrację urządzeń z systemem Android lub ją blokujące, przejdź do bloku Usługa Intune w witrynie Azure Portal, a następnie wybierz kolejno pozycje **Rejestracja** > **Ograniczenia rejestracji**. 

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Poinformuj użytkowników, jak mogą zarejestrować swoje urządzenia w celu uzyskania dostępu do zasobów firmy

Instrukcje dotyczące rejestrowania przez użytkownika końcowego można znaleźć w temacie [Rejestrowanie urządzenia z systemem Android w usłudze Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-android). W trakcie procesu rejestracji użytkownicy są informowani, czego mogą oczekiwać, a także co administratorzy IT mogą i czego nie mogą wyświetlać na swoich urządzeniach.

Aby uzyskać informacje o innych zadaniach użytkownika końcowego, zobacz następujące artykuły:

- [Zasoby dotyczące środowiska użytkownika końcowego w usłudze Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)
- [Korzystanie z urządzenia z systemem Android i usługi Intune](https://docs.microsoft.com/intune/enduser/using-your-android-device-with-intune)


<!--HONumber=Feb17_HO1-->


