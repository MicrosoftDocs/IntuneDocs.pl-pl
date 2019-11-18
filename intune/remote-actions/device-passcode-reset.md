---
title: Resetowanie kodów dostępu urządzenia za pomocą usługi Microsoft Intune — Azure | Microsoft Docs
description: Usuń lub zresetuj kod dostępu przy użyciu akcji Usuń kod dostępu na urządzeniach zarządzanych lub monitorowanych przy użyciu usługi Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/18/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: be6a254360d8e8e9ef1396515d261b6ff9077b87
ms.sourcegitcommit: 28622c5455adfbce25a404de4d0437fa2b5370be
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/07/2019
ms.locfileid: "73713123"
---
# <a name="reset-or-remove-a-device-passcode-in-intune"></a>Resetowanie lub usuwanie kodu dostępu urządzenia w usłudze Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

W tym dokumencie omówiono zarówno resetowanie kodu dostępu na poziomie urządzenia, jak i resetowanie kodu dostępu profilu służbowego na urządzeniach z rozwiązaniem Android Enterprise (wcześniej nazywanym Android for Work lub AfW). Należy pamiętać o tym rozróżnieniu, ponieważ wymagania dotyczące poszczególnych operacji mogą się różnić. Zresetowanie kodu dostępu na poziomie urządzenia powoduje zresetowanie kodu dostępu dla całego urządzenia. Zresetowanie kodu dostępu profilu służbowego powoduje zresetowanie kodu dostępu tylko dla profilu służbowego użytkownika na urządzeniach z rozwiązaniem Android enterprise.

## <a name="supported-platforms-for-device-level-passcode-reset"></a>Platformy, na których jest obsługiwane resetowanie kodu dostępu na poziomie urządzenia

| Platforma | Obsługiwane? |
| ---- | ---- |
| Urządzenia z systemem Android w wersji 6.x lub starszej | Tak |
| Urządzenia z rozwiązaniem Android enterprise w trybie kiosku | Tak |
| Urządzenia z systemem iOS | Tak |
| Urządzenia z systemem iOS zarejestrowane w usłudze rejestracji użytkowników | Nie |
| Zarejestrowane urządzenia z systemem Android z profilem służbowym | Nie |
| Urządzenia z systemem Android w wersji 7.0 lub nowszej | Nie |
| macOS | Nie |
| Windows | Nie |

Dla urządzeń z systemem Android oznacza to, że resetowanie kodu dostępu na poziomie urządzenia jest obsługiwane tylko na urządzeniach z systemem w wersji 6.x lub starszej oraz na urządzeniach z rozwiązaniem Android Enterprise działających w trybie kiosku. Jest to spowodowane tym, że firma Google usunęła obsługę resetowania hasła/kodu dostępu urządzeń z systemem Android 7 z poziomu aplikacji, której udzielono uprawnień administratora urządzenia, i dotyczy to wszystkich dostawców zarządzania urządzeniami przenośnymi (MDM).

## <a name="supported-platforms-for-android-enterprise-work-profile-passcode-reset"></a>Platformy, na których jest obsługiwane resetowanie kodu dostępu profilu służbowego rozwiązania Android enterprise

| Platforma | Obsługiwane? |
| ---- | ---- |
| Zarejestrowane urządzenia z rozwiązaniem Android enterprise z profilem służbowym, wersja 8.0 lub nowsza | Tak |
| Zarejestrowane urządzenia z rozwiązaniem Android enterprise z profilem służbowym, wersja 7.x lub starsza | Nie |
| Urządzenia z systemem Android, wersja 7.x lub starsza | Nie |

Aby utworzyć nowy kod dostępu profilu służbowego, użyj akcji resetowania kodu dostępu. Ta akcja powoduje wyświetlenie monitu o zresetowanie kodu dostępu i utworzenie nowego, tymczasowego kodu dostępu tylko dla profilu służbowego. 

## <a name="reset-a-passcode"></a>Resetowanie kodu dostępu


1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) przy użyciu dowolnej spośród następujących ról: administrator globalny usługi Azure Active Directory, administrator usługi Intune w usłudze Azure Active Directory, operator pomocy technicznej lub administrator roli.
2. Wybierz pozycję **Urządzenia**, a następnie wybierz pozycję **Wszystkie urządzenia**.
3. Z listy zarządzanych urządzeń wybierz urządzenie, a następnie wybierz pozycję **...więcej**. Następnie wybierz zdalną akcję urządzenia **Usuń kod dostępu**.

## <a name="reset-android-work-profile-passcodes"></a>Resetowanie kodów dostępu profilu służbowego systemu Android

Obsługiwane urządzenia z rozwiązaniem Android Enterprise i profilem służbowym otrzymują nowe hasło do odblokowywania profilu zarządzanego lub test profilu zarządzanego dla użytkownika końcowego.

Na urządzeniach z rozwiązaniem Android Enterprise z systemem 8.x lub nowszym i zarejestrowanych za pomocą profilu służbowego użytkownicy końcowi otrzymują powiadomienie dotyczące konieczności aktywowania kodu dostępu resetowania natychmiast po zakończeniu rejestracji. Powiadomienie jest wyświetlane, jeśli hasło profilu służbowego jest wymagane i ustawione. Po wprowadzeniu kodu dostępu powiadomienie jest odrzucane.


## <a name="remove-ios-passcodes"></a>Usuwanie kodów dostępu systemu iOS

W przypadku urządzeń z systemem iOS kodów dostępu się nie resetuje — usuwa się je. Jeśli zostały ustawione zasady zgodności kodu dostępu, urządzenie wyświetla użytkownikowi monit o ustawienie nowego kodu dostępu w ustawieniach.

## <a name="next-steps"></a>Następne kroki

Aby wyświetlić stan właśnie wykonanej akcji, w obszarze **Urządzenia** wybierz pozycję **Akcje urządzenia**.
