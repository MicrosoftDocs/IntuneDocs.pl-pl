---
title: "Importowanie ustawień sieci Wi-Fi dla systemu Windows 8.1 lub nowszego"
titleSuffix: Microsoft Intune
description: "Jak importować ustawienia sieci Wi-Fi z systemu Windows do profilu sieci Wi-Fi usługi Intune."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/2/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0113703cbdc58172edc9552146c7634aa1058e3b
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/05/2018
---
# <a name="import-wi-fi-settings-for-windows-81-and-later-devices-in-microsoft-intune"></a>Importowanie ustawień sieci Wi-Fi dla urządzeń z systemem Windows 8.1 lub nowszym w usłudze Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

W przypadku urządzeń z systemami operacyjnymi Windows 8.1, Windows 10 (na komputery i urządzenia mobilne) oraz Windows Holographic for Business można zaimportować profil konfiguracji sieci Wi-Fi, który został wcześniej wyeksportowany do pliku.

## <a name="export-wi-fi-settings-from-a-windows-device"></a>Eksportowanie ustawień sieci Wi-Fi z urządzenia z systemem Windows

W systemie Windows można użyć narzędzia **netsh wlan**, aby wyeksportować istniejący profil sieci Wi-Fi do pliku XML, który może zostać odczytany przez usługę Intune. Na komputerze z systemem Windows, na którym jest już zainstalowany wymagany profil sieci Wi-Fi, wykonaj następującą procedurę.
1. Utwórz folder lokalny dla wyeksportowanych profilów sieci Wi-Fi, np. **c:\WiFi**.
1. Otwórz wiersz polecenia jako administrator.
1. Uruchom polecenie **netsh wlan show profiles** i określ nazwę profilu, który chcesz wyeksportować. W tym przykładzie nazwa profilu brzmi **WiFiName**.
1. Uruchom polecenie **netsh wlan export profile name="ProfileName" folder=c:\Wifi**. Spowoduje to utworzenie pliku profilu sieci Wi-Fi o nazwie **Wi-Fi-WiFiName.xml** w folderze docelowym.

## <a name="import-the-wi-fi-settings-into-intune"></a>Importowanie ustawień sieci Wi-Fi w usłudze Intune

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. Na stronie **Intune** wybierz opcję **Konfiguracja urządzeń**.
2. Na stronie **Konfiguracja urządzeń** wybierz pozycję **Zarządzaj** > **Profile**.
3. Na stronie profilów kliknij pozycję **Utwórz profil**.
4. Na stronie **Utwórz profil** wprowadź wartości pól **Nazwa** i **Opis** odnoszące się do profilu ograniczeń urządzenia.

   > [!WARNING]
   > Nazwa **musi** być taka sama jak w atrybucie nazwy w pliku XML profilu sieci Wi-Fi. W przeciwnym razie działanie nie powiedzie się.

5. Z listy rozwijanej **Platforma** wybierz pozycję **System Windows 8.1 lub nowszy**.
6. Z listy rozwijanej **Typ profilu** wybierz pozycję **Importowanie konfiguracji sieci Wi-Fi**.
7. Na stronie **Podstawowa sieć Wi-Fi** skonfiguruj następujące ustawienia:
    - **Nazwa połączenia** — wprowadź nazwę połączenia sieci Wi-Fi. Ta nazwa jest wyświetlana użytkownikom końcowym podczas przeglądania dostępnych sieci Wi-Fi.
    - **Plik XML profilu** — kliknij przycisk Przeglądaj, aby wybrać plik XML zawierający ustawienia profilu sieci Wi-Fi, który chcesz zaimportować do usługi Intune.
    - **Zawartość pliku** — wyświetla kod XML wybranego profilu konfiguracji.
8. Gdy skończysz, wróć na stronę **Tworzenie profilu** i wybierz pozycję **Utwórz**.

Profil zostanie utworzony i wyświetlony na stronie listy profilów.
