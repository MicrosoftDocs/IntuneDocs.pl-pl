---
title: "Zbieranie dzienników urządzeń | Microsoft Intune"
description: "Dowiedz się, jak zbierać dzienniki z urządzeń zarządzanych."
keywords: 
author: staciebarker
ms.author: staciebarker
manager: angrobe
ms.date: 10/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d97fb610-9d88-40e5-bb06-447eec533630
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3a081109cd499d3bdda75cb6c8a4dab9d9d28fab
ms.openlocfilehash: ec7d522e8dcff66d1b84fed3c4c0cc708e555e67


---

# <a name="device-logs"></a>Dzienniki urządzeń

Podczas rozwiązywania problemów może być konieczne zebranie dzienników z urządzeń użytkowników. W tym temacie podano instrukcje dotyczące zbierania tych dzienników. Zazwyczaj trzeba uzyskać dostęp do urządzenia lub poprosić użytkownika o zebranie dzienników i wysłanie ich do Ciebie.

### <a name="android-log-location"></a>Lokalizacja dzienników systemu Android
Dzienniki systemu Android znajdują się w folderze *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files*. Użytkownik może również wysłać pliki dzienników do Ciebie w wiadomości e-mail zgodnie z opisem w temacie [Wysyłanie dzienników danych diagnostycznych systemu Android do administratora IT za pomocą poczty e-mail](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android).

### <a name="ios-logs"></a>Dzienniki systemu iOS

Użytkownik może wysłać do Ciebie błędy rejestracji w sposób opisany w temacie [Wysyłanie błędów rejestracji systemu iOS do administratora IT](/intune/enduser/send-errors-to-your-it-admin-ios).

### <a name="mac-os-x-devices"></a>Urządzenia z systemem Mac OS X

1. Otwórz aplikację **Konsola**.
2. W obszarze **PLIKI** wybierz pozycję **system.log**.
3. Na pasku menu u góry wybierz pozycję **Plik** > **Zapisz kopię jako** i zapisz plik.

### <a name="windows-phone"></a>System Windows Phone

W aplikacji **Portal firmy dla systemu Windows Phone** użytkownik musi wybrać pozycję **…**, aby uzyskać dostęp do menu, a następnie wybrać pozycję **Wyślij dzienniki**. Ta opcja jest dostępna zarówno przed, jak i po zalogowaniu się do portalu.

### <a name="windows"></a>Windows

W przypadku aplikacji Portal firmy dla systemu Windows dzienniki znajdują się w folderze *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState*.



<!--HONumber=Oct16_HO3-->


