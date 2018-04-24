---
title: Importowanie ustawień sieci Wi-Fi dla systemu Windows 8.1 lub nowszego
titleSuffix: Microsoft Intune
description: Jak importować ustawienia sieci Wi-Fi z systemu Windows do profilu sieci Wi-Fi usługi Intune.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 033b60fded23f5a1dac5c8ff93716dac77c56fe2
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="import-wi-fi-settings-for-windows-81-and-later-devices-in-microsoft-intune"></a>Importowanie ustawień sieci Wi-Fi dla urządzeń z systemem Windows 8.1 lub nowszym w usłudze Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

W przypadku urządzeń z systemami operacyjnymi Windows 8.1, Windows 10 (na komputery i urządzenia mobilne) oraz Windows Holographic for Business można zaimportować profil konfiguracji sieci Wi-Fi, który został wcześniej wyeksportowany do pliku.

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
