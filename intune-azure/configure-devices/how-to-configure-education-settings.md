---
title: "Konfigurowanie ustawień edukacyjnych usługi Intune dla systemu Windows 10"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: informacje dotyczące konfigurowania ustawień edukacyjnych systemu Windows 10 na zarządzanych urządzeniach przy użyciu usługi Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: d3fdf8884a0b7c035cde89da930ef74172b76873
ms.lasthandoff: 04/19/2017


---

# <a name="how-to-configure-windows-10-education-settings-in-microsoft-intune"></a>Jak skonfigurować ustawienia edukacyjne systemu Windows 10 w usłudze Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Profile edukacji umożliwiają określenie szczegółowych informacji wymaganych do skonfigurowania aplikacji Take a Test systemu Windows, w tym szczegółów konta, oraz przetestowanie adresu URL. Po skonfigurowaniu zostanie otwarta aplikacja Take a Test z określonym przez Ciebie testem i do czasu ukończenia testu żadna inna aplikacja nie będzie mogła zostać uruchomiona na urządzeniu.

Skorzystaj z informacji zawartych w tym temacie, aby uzyskać podstawową wiedzę z zakresu konfigurowania profilów ograniczeń dotyczących urządzeń, a następnie zapoznaj się z tematami dotyczącymi poszczególnych platform, aby dowiedzieć się więcej o charakterystyce urządzeń.

## <a name="create-a-device-profile-containing-education-profile-settings"></a>Tworzenie profilu urządzenia zawierającego ustawienia profilu edukacji

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno pozycje **Więcej usług** > **Inne** > **Intune**.
3. W bloku **Intune** wybierz opcję **Konfiguracja urządzeń**.
2. W bloku **Konfiguracja urządzeń** wybierz kolejno pozycje **Zarządzaj** > **Profile**.
3. W bloku profilów wybierz pozycję **Utwórz profil**.
4. W bloku **Utwórz profil** uzupełnij pola **Nazwa** i **Opis** odnoszące się do profilu ograniczeń urządzenia.
5. Z listy rozwijanej **Platforma** wybierz pozycję **Windows 10 lub nowszy**.
6. Z listy rozwijanej **Typ profilu** wybierz pozycję **Profil edukacji**. 
7. Wybierz opcję Ustawienia > Konfiguruj, a następnie w bloku **Take a Test** skonfiguruj następujące opcje:
    - **Nazwa użytkownika konta** — wprowadź nazwę użytkownika konta używanego z aplikacją Take a Test. Może to być konto domeny, konto usługi Azure Active Directory (AAD) lub lokalne konto na komputerze.
    - **Adres URL oceny** — podaj adres URL testu, który mają wykonać użytkownicy. Więcej informacji znajduje się w dokumentacji aplikacji Take a Test.
    - **Monitorowanie ekranu** — określ, czy chcesz mieć możliwość monitorowania działania ekranu podczas wykonywania testu przez użytkowników.
    - **Podpowiedzi tekstowe** — włącz lub zablokuj podpowiedzi tekstowe podczas wykonywania testu przez użytkowników.
8. Gdy skończysz, wróć do bloku **Utwórz profil** i wybierz pozycję **Utwórz**.

Profil zostanie utworzony i wyświetlony w bloku listy profilów.
Wskazówki umożliwiające przypisanie tego profilu do grup znajdują się w artykule [How to assign device profiles](how-to-assign-device-profiles.md) (Sposoby przypisywania profilów urządzeń).




