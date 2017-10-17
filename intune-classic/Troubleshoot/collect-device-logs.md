---
title: "Zbieranie dzienników urządzeń"
description: "Dowiedz się, jak zbierać dzienniki z urządzeń zarządzanych."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 02/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d97fb610-9d88-40e5-bb06-447eec533630
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f54e0d40e0a8f723e04d4c2b936dee37bc611858
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2017
---
# <a name="device-logs"></a>Dzienniki urządzeń

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Podczas rozwiązywania problemów może być przydatne zebranie dzienników z urządzeń użytkowników. W tym temacie podano instrukcje dotyczące zbierania tych dzienników. W celu uzyskania tych dzienników zazwyczaj konieczny jest dostęp do urządzenia. Można też poprosić użytkownika o ich zebranie i przysłanie.

### <a name="android-logs"></a>Dzienniki systemu Android
Dzienniki systemu Android znajdują się w folderze *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files*.

Czasami pliki nie są wyświetlane, zwłaszcza na nowszych urządzeniach z systemem Android. W takim przypadku użytkownicy powinni otworzyć aplikację Portal firmy dla systemu Android. Następnie powinni wybrać polecenie **Ustawienia**>**Kopiuj dzienniki** i ponownie uruchomić urządzenie.

Aby uzyskać więcej informacji na temat sposobu, w jaki użytkownicy mogą przesyłać do Ciebie dzienniki danych, zobacz następujące artykuły:

- [Używanie pełnego rejestrowania ułatwiającego administratorowi IT rozwiązywanie problemów z urządzeniami](/intune-user-help/use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android) — opis sposobu, w jaki użytkownicy mogą włączyć pełne rejestrowanie, aby automatycznie przesyłać do Ciebie wszystkie dzienniki danych użytkowników. Domyślnie pełne rejestrowanie jest włączone.

- [Wysyłanie dzienników danych diagnostycznych systemu Android do administratora IT pocztą e-mail](/intune-user-help/send-logs-to-your-it-admin-by-email-android)

- [Wysyłanie dzienników danych diagnostycznych do administratora IT za pomocą kabla USB](/intune-user-help/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)

### <a name="ios-logs"></a>Dzienniki systemu iOS

Użytkownicy mogą wysłać do Ciebie błędy rejestracji w sposób opisany w temacie [Wysyłanie błędów rejestracji systemu iOS do administratora IT](/intune-user-help/send-errors-to-your-it-admin-ios).

Użytkownicy mogą wysyłać dzienniki urządzeń zgodnie z opisem w artykule [Send iOS Device Logs](/intune-user-help/send-logs-to-microsoft-ios) (Wysyłanie dzienników urządzeń z systemem iOS).

### <a name="mac-os-x-logs"></a>Dzienniki systemu Mac OS X

1. Otwórz aplikację **Konsola**.
2. W obszarze **PLIKI** wybierz pozycję **system.log**.
3. Na pasku menu u góry wybierz kolejno pozycje **Plik** > **Zapisz kopię jako**. Następnie zapisz plik.

### <a name="windows-phone"></a>Windows Phone

W aplikacji Portal firmy dla systemu Windows Phone do uzyskania dostępu do menu służy wielokropek (**...**). Następnie należy wybrać pozycję **Wyślij dzienniki**. Ta opcja jest dostępna zarówno przed, jak i po zalogowaniu się do aplikacji Portal firmy.

### <a name="windows"></a>Windows

W przypadku aplikacji Portal firmy dla systemu Windows dzienniki znajdują się w folderze *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState*.
