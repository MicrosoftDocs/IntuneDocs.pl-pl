---
title: "Zbieranie dzienników urządzeń | Microsoft Intune"
description: 
keywords: 
author: Nbigman
manager: jeffgilb
ms.date: 06/01/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d97fb610-9d88-40e5-bb06-447eec533630
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ac5c66f57194a84580aa495a58e5281683aa1cca
ms.openlocfilehash: 4fc08fcea6cea897b9ddc3d0c00f2d83069f639d


---

# Dzienniki urządzeń

Podczas rozwiązywania problemów może być konieczne zebranie dzienników z urządzeń użytkowników. W tym temacie podano instrukcje dotyczące zbierania tych dzienników. Zazwyczaj trzeba uzyskać dostęp do urządzenia lub poprosić użytkownika o zebranie dzienników i wysłanie ich do Ciebie. 

### Lokalizacja dzienników systemu Android
Dzienniki systemu Android znajdują się w folderze *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files*. Użytkownik może również wysłać pliki dzienników do Ciebie w wiadomości e-mail zgodnie z opisem w temacie [Wysyłanie dzienników danych diagnostycznych systemu Android do administratora IT za pomocą poczty e-mail](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android).

### Dzienniki systemu iOS

Użytkownik może wysłać do Ciebie błędy rejestracji w sposób opisany w temacie [Wysyłanie błędów rejestracji systemu iOS do administratora IT](/intune/enduser/send-errors-to-your-it-admin-ios).

### Urządzenia z systemem Mac OS X

1. Otwórz aplikację **Konsola**.
2. W obszarze **PLIKI** wybierz pozycję **system.log**.
3. Na pasku menu u góry wybierz pozycję **Plik** > **Zapisz kopię jako** i zapisz plik.

### System Windows Phone

W aplikacji **Portal firmy dla systemu Windows Phone** użytkownik musi wybrać pozycję **…**, aby uzyskać dostęp do menu, a następnie wybrać pozycję **Wyślij dzienniki**. Ta opcja jest dostępna zarówno przed, jak i po zalogowaniu się do portalu.

### Windows

W przypadku aplikacji Portal firmy dla systemu Windows dzienniki znajdują się w folderze *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState*.



<!--HONumber=Jun16_HO4-->


