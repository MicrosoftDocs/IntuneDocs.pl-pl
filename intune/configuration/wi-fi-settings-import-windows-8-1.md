---
title: Importowanie ustawień sieci Wi-Fi dla urządzeń z systemem Windows w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Możliwe jest wyeksportowanie ustawień sieci Wi-Fi z urządzenia z systemem Windows jako plik XML przy użyciu narzędzia netsh wlan. Następnie można zaimportować ten plik w usłudze Intune, aby utworzyć profil sieci Wi-Fi dla urządzeń z systemem Windows 8.1, Windows 10 i Windows Holographic for Business.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/18/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f79ccdc71ddbfa3f25daef629515fb612de01852
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2019
ms.locfileid: "75207013"
---
# <a name="import-wi-fi-settings-for-windows-devices-in-intune"></a>Importowanie ustawień sieci Wi-Fi dla urządzeń z systemem Windows w usłudze Intune

W przypadku urządzeń z systemem Windows można zaimportować profil konfiguracji sieci Wi-Fi, który został wcześniej wyeksportowany do pliku. **Dla urządzeń z systemem Windows 10 lub nowszym można również [utworzyć profil sieci Wi-Fi](wi-fi-settings-windows.md) bezpośrednio w usłudze Intune**.

Dotyczy:  
- Windows 8.1 i nowsze
- Windows 10 lub nowszym
- Windows 10 Desktop lub Mobile
- Windows Holographic for Business

## <a name="export-wi-fi-settings-from-a-windows-device"></a>Eksportowanie ustawień sieci Wi-Fi z urządzenia z systemem Windows

W systemie Windows można użyć narzędzia `netsh wlan`, aby wyeksportować istniejący profil sieci Wi-Fi do pliku XML, który może zostać odczytany przez usługę Intune. Klucz musi być wyeksportowany jako zwykły tekst, aby można było pomyślnie użyć profilu.

Na komputerze z systemem Windows, na którym jest już zainstalowany wymagany profil sieci Wi-Fi, wykonaj następujące kroki:

1. Utwórz folder lokalny dla wyeksportowanych profilów sieci Wi-Fi, np. **c:\WiFi**.
2. Otwórz wiersz polecenia jako administrator.
3. Uruchom polecenie `netsh wlan show profiles`. Uruchom polecenie  i określ nazwę profilu, który chcesz wyeksportować. W tym przykładzie nazwa profilu brzmi **WiFiName**.
4. Uruchom polecenie `netsh wlan export profile name="ProfileName" folder=c:\Wifi`. To polecenie spowoduje utworzenie pliku profilu sieci Wi-Fi o nazwie **Wi-Fi-WiFiName.xml** w folderze docelowym.

## <a name="import-the-wi-fi-settings-into-intune"></a>Importowanie ustawień sieci Wi-Fi w usłudze Intune

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Urządzenia** > **Profile konfiguracji** > **Utwórz profil**.
3. Podaj następujące ustawienia:

    - **Nazwa**: Wprowadź opisową nazwę profilu. Nazwa **musi** być taka sama jak w atrybucie nazwy w pliku XML profilu sieci Wi-Fi. W przeciwnym razie działanie nie powiedzie się.
    - **Opis**: Wprowadź opis ułatwiający identyfikację ustawienia oraz zawierający inne ważne szczegóły.
    - **Platforma**: Wybierz pozycję **Windows 8.1 i nowsze**.
    - **Typ profilu**: Wybierz pozycję **Importowanie sieci Wi-Fi**.

    > [!IMPORTANT]
    > - Jeśli eksportujesz profil sieci Wi-Fi, który zawiera klucz wstępny, **musisz** dodać parametr `key=clear` do polecenia. Na przykład podaj polecenie `netsh wlan export profile name="ProfileName" key=clear folder=c:\Wifi`
    > - Użycie klucza wstępnego w systemie Windows 10 powoduje wyświetlenie błędu korygowania w usłudze Intune. W takim przypadku profil sieci Wi-Fi zostanie prawidłowo przypisany do urządzenia i będzie działać zgodnie z oczekiwaniami.
    > - Jeśli eksportujesz profil sieci Wi-Fi, który zawiera klucz wstępny, upewnij się, że plik jest chroniony. Klucz ma postać zwykłego tekstu, więc odpowiedzialność za jego ochronę spoczywa na Tobie.

4. Podaj następujące ustawienia:

    - **Nazwa połączenia**: wprowadź nazwę połączenia sieci Wi-Fi. Ta nazwa jest wyświetlana użytkownikom końcowym podczas przeglądania dostępnych sieci Wi-Fi.
    - **Plik XML profilu**: Wybierz przycisk przeglądania, a następnie plik XML zawierający ustawienia profilu sieci Wi-Fi, który chcesz zaimportować.
    - **Zawartość pliku**: Wyświetla kod XML wybranego profilu konfiguracji.

5. Wybierz przycisk **OK**, aby zapisać zmiany.
6. Po zakończeniu wybierz pozycję **OK** > **Utwórz**, aby utworzyć profil usługi Intune. Po utworzeniu profil będzie widoczny na liście **Urządzenia — profile konfiguracji**.

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje żadnych czynności. W dalszej części [przypiszesz profil](../device-profile-assign.md) i będziesz [monitorować jego stan](device-profile-monitor.md).

Zobacz [Omówienie ustawień sieci Wi-Fi](wi-fi-settings-configure.md), w tym informacje na temat innych dostępnych platform.
