---
title: Resetowanie kodów dostępu urządzenia za pomocą usługi Microsoft Intune — Azure | Microsoft Docs
description: Usuń lub zresetuj kod dostępu przy użyciu akcji Usuń kod dostępu na urządzeniach zarządzanych lub monitorowanych przy użyciu usługi Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dd743bdb0eaf2e00c50aab85c497dd00aac773ed
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905159"
---
# <a name="reset-or-remove-a-device-passcode-in-intune"></a>Resetowanie lub usuwanie kodu dostępu urządzenia w usłudze Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Aby utworzyć nowy kod dostępu urządzenia, użyj akcji **Resetuj kod dostępu**.

## <a name="supported-platforms"></a>Obsługiwane platformy

- Zarejestrowane urządzenia z systemem Android z profilem służbowym, wersja 8.0 lub nowsza
- Urządzenia z systemem Android w wersji 6.0 lub starszej
- Urządzenia kiosku w rozwiązaniu Android enterprise
- iOS 
     
## <a name="unsupported-platforms"></a>Nieobsługiwane platformy

- Zarejestrowane urządzenia z systemem Android z profilem służbowym, wersja 7.0 lub starsza
- Urządzenia z systemem Android w wersji 7.0 lub nowszej
- macOS
- Windows

## <a name="reset-a-passcode"></a>Resetowanie kodu dostępu

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz pozycję **Urządzenia**, a następnie wybierz pozycję **Wszystkie urządzenia**.
4. Z listy zarządzanych urządzeń wybierz urządzenie, a następnie wybierz pozycję **...więcej**. Następnie wybierz zdalną akcję urządzenia **Usuń kod dostępu**.

## <a name="resetting-android-work-profile-passcodes"></a>Resetowanie kodów dostępu profilu służbowego systemu Android

Obsługiwane urządzenia profilu służbowego systemu Android otrzymują nowe hasło do odblokowywania profilu zarządzanego lub test profilu zarządzanego dla użytkownika końcowego. Na urządzeniach profilu służbowego systemu Android 8.0 użytkownicy końcowi otrzymują powiadomienia dotyczące konieczności aktywowania kodu dostępu resetowania natychmiast po zakończeniu rejestracji. Powiadomienie jest wyświetlane, jeśli hasło profilu służbowego jest wymagane i ustawione. Po wprowadzeniu kodu dostępu powiadomienie jest odrzucane.

## <a name="resetting-ios-passcodes"></a>Resetowanie kodów dostępu w systemie iOS

Kody dostępu są usuwane z urządzeń z systemem iOS. Jeśli zostały ustawione zasady zgodności kodu dostępu, urządzenie wyświetla użytkownikowi monit o ustawienie nowego kodu dostępu w ustawieniach. 

## <a name="next-steps"></a>Następne kroki

Aby wyświetlić stan właśnie wykonanej akcji, w obszarze **Urządzenia** wybierz pozycję **Akcje urządzenia**.
