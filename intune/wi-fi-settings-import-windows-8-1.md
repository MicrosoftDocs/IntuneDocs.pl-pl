---
title: Importowanie ustawień sieci Wi-Fi dla urządzeń z systemem Windows w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Możliwe jest wyeksportowanie ustawień sieci Wi-Fi z urządzenia z systemem Windows jako plik XML przy użyciu narzędzia netsh wlan. Następnie można zaimportować ten plik w usłudze Intune, aby utworzyć profil sieci Wi-Fi dla urządzeń z systemem Windows 8.1, Windows 10 i Windows Holographic for Business.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 07/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6ce5cdd9509ed3407491714ccfa853613eb43973
ms.sourcegitcommit: e8e8164586508f94704a09c2e27950fe6ff184c3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2018
ms.locfileid: "39321139"
---
# <a name="import-wi-fi-settings-for-windows-devices-in-intune"></a>Importowanie ustawień sieci Wi-Fi dla urządzeń z systemem Windows w usłudze Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

W przypadku urządzeń z systemem Windows można zaimportować profil konfiguracji sieci Wi-Fi, który został wcześniej wyeksportowany do pliku. **Dla urządzeń z systemem Windows 10 lub nowszym można [utworzyć profil sieci Wi-Fi](wi-fi-settings-windows.md) bezpośrednio w usłudze Intune**.

Dotyczy:  
- Windows 8.1 i nowsze
- System Windows 10 lub nowszy
- Windows 10 Desktop lub Mobile
- Windows Holographic for Business

## <a name="export-wi-fi-settings-from-a-windows-device"></a>Eksportowanie ustawień sieci Wi-Fi z urządzenia z systemem Windows

W systemie Windows można użyć narzędzia **netsh wlan**, aby wyeksportować istniejący profil sieci Wi-Fi do pliku XML, który może zostać odczytany przez usługę Intune. Klucz musi być wyeksportowany jako zwykły tekst, aby można było pomyślnie użyć profilu.

Na komputerze z systemem Windows, na którym jest już zainstalowany wymagany profil sieci Wi-Fi, wykonaj następujące kroki:

1. Utwórz folder lokalny dla wyeksportowanych profilów sieci Wi-Fi, np. **c:\WiFi**.
2. Otwórz wiersz polecenia jako administrator.
3. Uruchom polecenie `netsh wlan show profiles` i określ nazwę profilu, który chcesz wyeksportować. W tym przykładzie nazwa profilu brzmi **WiFiName**.
4. Uruchom polecenie `netsh wlan export profile name="ProfileName" folder=c:\Wifi`. Spowoduje to utworzenie pliku profilu sieci Wi-Fi o nazwie **Wi-Fi-WiFiName.xml** w folderze docelowym.

## <a name="import-the-wi-fi-settings-into-intune"></a>Importowanie ustawień sieci Wi-Fi w usłudze Intune

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz opcję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz pozycję **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
4. Podaj **nazwę** i **opis** profilu ograniczenia urządzenia.

    > [!IMPORTANT]
    > - Nazwa **musi** być taka sama jak w atrybucie nazwy w pliku XML profilu sieci Wi-Fi. W przeciwnym razie działanie nie powiedzie się.
    > - Jeśli eksportujesz profil sieci Wi-Fi, który zawiera klucz wstępny, **musisz** dodać parametr `key=clear` do polecenia. Na przykład podaj polecenie `netsh wlan export profile name="ProfileName" key=clear folder=c:\Wifi`
    > - Użycie klucza wstępnego w systemie Windows 10 powoduje wystąpienie błędu korygowania w usłudze Intune. W takim przypadku profil sieci Wi-Fi zostanie prawidłowo przypisany do urządzenia i będzie działać zgodnie z oczekiwaniami.
    > - Jeśli eksportujesz profil sieci Wi-Fi, który zawiera klucz wstępny, upewnij się, że plik jest chroniony. Klucz ma postać zwykłego tekstu, więc odpowiedzialność za jego ochronę spoczywa na Tobie.

5. W polu **Platforma** wybierz pozycję **Windows 8.1 i nowsze**.
6. W polu **Typ profilu** wybierz pozycję **Importowanie sieci Wi-Fi**.
7. Skonfiguruj następujące ustawienia:
  - **Nazwa połączenia**: podaj nazwę połączenia sieci Wi-Fi. Ta nazwa jest wyświetlana użytkownikom końcowym podczas przeglądania dostępnych sieci Wi-Fi.
  - **Plik XML profilu**: wybierz przycisk Przeglądaj, aby wybrać plik XML zawierający ustawienia profilu sieci Wi-Fi, który chcesz zaimportować do usługi Intune.
  - **Zawartość pliku**: umożliwia wyświetlenie kodu XML wybranego profilu konfiguracji.
8. Gdy wszystko będzie gotowe, wybierz pozycję **OK**, a następnie **Utwórz**, aby utworzyć profil.

Profil zostanie utworzony i wyświetlony na liście profilów.
