---
title: Konfigurowanie ustawień edukacyjnych usługi Intune dla systemu Windows 10
titleSuffix: Microsoft Intune
description: Informacje dotyczące konfigurowania ustawień edukacyjnych systemu Windows 10 na zarządzanych urządzeniach przy użyciu usługi Intune.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 02/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 120aca8dae457748fea322ce164aa663ffa7e748
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52187382"
---
# <a name="how-to-configure-windows-10-education-settings-in-microsoft-intune"></a>Jak skonfigurować ustawienia edukacyjne systemu Windows 10 w usłudze Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Profile edukacji umożliwiają określenie szczegółowych informacji wymaganych do skonfigurowania aplikacji Take a Test systemu Windows, w tym szczegółów konta, oraz przetestowanie adresu URL. Po skonfigurowaniu zostanie otwarta aplikacja Take a Test z określonym przez Ciebie testem i do czasu ukończenia testu żadna inna aplikacja nie będzie mogła zostać uruchomiona na urządzeniu.

Aby uzyskać więcej informacji o aplikacji Take a Test, zobacz [Wykonywanie testów w systemie Windows 10](https://docs.microsoft.com/education/windows/take-tests-in-windows-10).

## <a name="create-a-device-profile-containing-education-profile-settings"></a>Tworzenie profilu urządzenia zawierającego ustawienia profilu edukacji

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Konfiguracja urządzeń**.
2. W okienku **Konfiguracja urządzeń** w sekcji **Zarządzanie** wybierz pozycję **Profile**.
3. W okienku profilów wybierz pozycję **Utwórz profil**.
4. W okienku **Tworzenie profilu** wprowadź wartość w polach **Nazwa** i **Opis** dotyczących profilu ograniczeń urządzenia.
5. Z listy rozwijanej **Platforma** wybierz pozycję **Windows 10 lub nowszy**.
6. Z listy rozwijanej **Typ profilu** wybierz pozycję **Profil edukacji**. 
7. Wybierz opcję **Ustawienia > Konfiguruj**, a następnie w okienku **Take a Test** skonfiguruj następujące elementy:
    - **Typ konta** — wybierz typ konta z pola listy rozwijanej.
    - **Nazwa użytkownika konta** — wprowadź nazwę użytkownika konta używanego z aplikacją Take a Test. Może to być konto domeny, konto usługi Azure Active Directory (AAD) lub lokalne konto na komputerze.
    - **Adres URL oceny** — podaj adres URL testu, który mają wykonać użytkownicy. Więcej informacji znajduje się w dokumentacji aplikacji Take a Test.
    - **Monitorowanie ekranu** — określ, czy chcesz mieć możliwość monitorowania działania ekranu podczas wykonywania testu przez użytkowników.
    - **Podpowiedzi tekstowe** — włącz lub zablokuj podpowiedzi tekstowe podczas wykonywania testu przez użytkowników.
8. Gdy skończysz, wróć do okienka **Tworzenie profilu**, a następnie wybierz pozycję **Utwórz**.

Profil zostanie utworzony i wyświetlony w okienku z listą profilów.

## <a name="next-steps"></a>Następne kroki

Wskazówki umożliwiające przypisanie tego profilu do grup znajdują się w artykule [How to assign device profiles](device-profile-assign.md) (Sposoby przypisywania profilów urządzeń).



