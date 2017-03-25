---
title: "Rejestrowanie urządzeń z systemem Android w usłudze Intune"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: informacje dotyczące rejestrowania urządzeń z systemem Android w wersji zapoznawczej usługi Intune Azure."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e76d66768ac58df25313e102b7f60d2bc7bbc59b
ms.openlocfilehash: b664620f424f9ef612d17beb810564dbdd68ff79
ms.lasthandoff: 03/22/2017


---

# <a name="enroll-android-devices"></a>Rejestrowanie urządzeń z systemem Android

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Usługa Intune umożliwia zarządzanie urządzeniami z systemem Android, w tym urządzeniami z systemem Samsung Knox Standard. Aby włączyć zarządzanie urządzeniami, użytkownicy muszą zarejestrować urządzenia, pobierając aplikację Portal firmy usługi Intune, która jest dostępna w usłudze Google Play, a następnie otwierając aplikację i postępując zgodnie z instrukcjami w celu zarejestrowania. Po dodaniu urządzeń z systemem Android do zarządzania można [tworzyć zasady zgodności](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-android), [zarządzać aplikacjami](https://docs.microsoft.com/intune-azure/manage-apps/what-is-app-management) itd.

## <a name="prerequisite"></a>Wymaganie wstępne

Należy ustawić urząd MDM na wartość **Microsoft Intune**, aby przygotować się do zarządzania urządzeniami przenośnymi. Instrukcje znajdują się w artykule [Set the MDM authority](set-mdm-authority.md) (Ustawianie urzędu MDM). Element ten ustawia się tylko raz podczas pierwszej konfiguracji usługi Intune do zarządzania urządzeniami przenośnymi, więc być może jest on już ustawiony.

## <a name="set-up-android-enrollment"></a>Konfiguracja rejestrowania urządzeń z systemem Android

Domyślnie usługa Intune zezwala na rejestrację urządzeń z systemem Android i rozwiązaniem Samsung Knox Standard.

Aby zablokować rejestrowanie urządzeń z systemem Android lub tylko urządzeń z systemem Android będących własnością użytkowników, zobacz [Ustawianie ograniczeń typu urządzeń](https://docs.microsoft.com/intune-azure/enroll-devices/set-enrollment-restrictions#set-device-type-restrictions).

Aby ustawić maksymalną liczbę urządzeń, które użytkownik może zarejestrować, zobacz [Ustawianie ograniczeń limitu urządzeń](https://docs.microsoft.com/intune-azure/enroll-devices/set-enrollment-restrictions#set-device-limit-restrictions).

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Poinformuj użytkowników, jak mogą zarejestrować swoje urządzenia w celu uzyskania dostępu do zasobów firmy

Należy poinformować użytkowników, aby przeszli do usługi Google Play, aby pobrać aplikację Portal firmy usługi Intune, a następnie otworzyli aplikację i postępowali zgodnie z instrukcjami w celu zarejestrowania urządzenia. W trakcie procesu rejestracji użytkownicy są informowani, czego mogą oczekiwać, a także co administratorzy IT mogą i czego nie mogą wyświetlać na swoich urządzeniach.

Można także wysłać im link do kroków rejestracji online: [Rejestrowanie urządzenia z systemem Android w usłudze Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-android).

Aby uzyskać informacje o innych zadaniach użytkownika końcowego, zobacz następujące artykuły:

- [Zasoby dotyczące środowiska użytkownika końcowego w usłudze Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune)
- [Korzystanie z urządzenia z systemem Android i usługi Intune](https://docs.microsoft.com/intune/enduser/using-your-android-device-with-intune)

