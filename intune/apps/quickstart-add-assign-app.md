---
title: Szybki start — dodawanie i przypisywanie aplikacji klienckiej
titleSuffix: Microsoft Intune
description: W tym przewodniku Szybki start utworzysz i przypiszesz za pomocą usługi Microsoft Intune aplikację kliencką.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/24/2019
ms.topic: quickstart
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: dab6f5c8-1ebb-42c4-a7a7-7af001f94e15
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8ed8df1f7a9edb62b5c9c8a9050031aedea7397a
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72497658"
---
# <a name="quickstart-add-and-assign-a-client-app"></a>Szybki start: Dodawanie i przypisywanie aplikacji klienckiej

W tym przewodniku Szybki start za pomocą usługi Intune utworzysz i przypiszesz pracownikom aplikację kliencką. Jednym z priorytetów administratora jest zapewnienie, że użytkownicy końcowi mają dostęp do aplikacji, których potrzebują do pracy. 

Jeśli nie masz subskrypcji usługi Intune, [utwórz konto bezpłatnej wersji próbnej](../fundamentals/free-trial-sign-up.md).

## <a name="prerequisites"></a>Wymagania wstępne

- Aby ukończyć ten przewodnik Szybki start, musisz [utworzyć użytkownika](../fundamentals/quickstart-create-user.md), [utworzyć grupę](../fundamentals/quickstart-create-group.md) i [zarejestrować urządzenie](../quickstart-setup-auto-enrollment.md).

## <a name="sign-in-to-intune"></a>Logowanie się do usługi Intune

Zaloguj się w usłudze [Intune](https://aka.ms/intuneportal) jako [administrator globalny lub administrator usługi Intune](../fundamentals/users-add.md#types-of-administrators). Jeśli utworzono subskrypcję wersji próbnej usługi Intune, konto, którego użyto do utworzenia subskrypcji, jest administratorem globalnym.

## <a name="add-the-client-app-to-intune"></a>Dodawanie aplikacji klienckiej do usługi Intune

Po dodaniu aplikacji usługa Intune może zarządzać jej aspektami. 

Aby dodać aplikację do usługi Intune, wykonaj następujące czynności:
1. W usłudze [Intune](https://aka.ms/intuneportal) wybierz pozycję **Aplikacje klienckie** > **Aplikacje** > **Dodaj**. 
2. Wybierz pozycję **Windows 10** w sekcji **Pakiet Office 365** na liście rozwijanej **Typ aplikacji**.
3. Wybierz pozycję **Skonfiguruj pakiet aplikacji** w celu wybrania aplikacji pakietu Office, który zostaną przypisane do użytkownika usługi Intune.
4. Kliknij przycisk **OK**, aby zaakceptować domyślnie wybrane aplikacje.
5. Wybierz pozycję **Informacje o pakiecie aplikacji**.
6. Wprowadź tekst **Pakiet aplikacji usługi Microsoft Office 365** w polu **Nazwa pakietu**.
7. Wprowadź **Pakiet aplikacji usługi Microsoft Office 365** jako **Opis pakietu**.
8. Kliknij przycisk **Tak** obok pozycji **Wyświetl jako polecaną aplikację w Portalu firmy**.
9. Kliknij przycisk **OK**.

    ![Zrzut ekranu przedstawiający dodawanie informacji o aplikacji](./media/quickstart-add-assign-app/quickstart-add-assign-app-01.png)

10. Wybierz pozycję **Ustawienia pakietu aplikacji**.
11. Z listy rozwijanej **Kanał aktualizacji** wybierz pozycję **Co miesiąc**.
12. Kliknij przycisk **OK** > **Dodaj**.

## <a name="assign-the-app-to-a-group"></a>Przypisywanie aplikacji do grupy

Po dodaniu aplikacji do usługi Microsoft Intune należy ją przypisać do grup użytkowników i urządzeń.

> [!NOTE]
> Ten przewodnik Szybki start bazuje na poprzednich przewodnikach Szybki start z tej serii. Aby uzyskać szczegółowe informacje, zobacz [wymagania wstępne](quickstart-add-assign-app.md#prerequisites) w tym przewodniku Szybki Start.

Aby przypisać aplikację do grupy, wykonaj następujące czynności:
1. W usłudze [Intune](https://aka.ms/intuneportal) wybierz pozycję **Aplikacje klienckie** > **Aplikacje**. 
2. Wybierz aplikację, którą chcesz przypisać do grupy.
3. Kliknij pozycję **Przypisania** > **Dodaj grupę** w celu wyświetlenia bloku **Dodawanie grupy**.
4. Wybierz pozycję **Dostępne dla zarejestrowanych urządzeń** z listy rozwijanej **Typ przypisania**. 
5. Wybierz pozycję **Objęte grupy** > **Wybierz grupy do uwzględnienia** > **Contoso Testers** (Testerzy Contoso).
6. Kliknij pozycję **Wybierz** > **OK** > **OK** > **Zapisz** w celu przypisania grupy.

Aplikacja została przypisana do grupy **Contoso Testers** (Testerzy Contoso).

## <a name="install-the-app-on-the-enrolled-device"></a>Instalowanie aplikacji na zarejestrowanym urządzeniu

W celu zainstalowania aplikacji **To-Do firmy Contoso** udostępnionej przez usługę Intune należy zainstalować aplikację Portal firmy i skorzystać z niej. Wykonaj następujące czynności, aby upewnić się, że aplikacja jest dostępna dla użytkownika zarejestrowanego urządzenia.

1. Zaloguj się na zarejestrowanym urządzeniu z systemem Windows 10 Desktop.

    > [!IMPORTANT]
    > Urządzenie musi być [zarejestrowane w usłudze Intune](../quickstart-enroll-windows-device.md). Ponadto musisz zalogować się na urządzeniu przy użyciu konta należącego do grupy przypisanej do aplikacji.

2. Z menu **Start** otwórz aplikację **Microsoft Store**. Następnie znajdź aplikację **Portal firmy** i zainstaluj ją.
3. Uruchom aplikację **Portal firmy**.
4. Kliknij aplikację dodaną przy użyciu usługi Intune. W tym przewodniku Szybki start dodano aplikację **Pakiet aplikacji usługi Microsoft Office 365**.

    > [!NOTE]
    > Jeśli nie udało Ci się pomyślnie przypisać żadnych aplikacji do użytkownika usługi Intune, zostanie wyświetlony następujący komunikat: *Administrator IT nie udostępnił Ci żadnych aplikacji.*

5. Kliknij przycisk **Zainstaluj**.

Jeśli jednak w Twojej organizacji wymagane jest przypisanie aplikacji Portal firmy do pracowników, aplikację Portal firmy dla systemu Windows 10 można przypisać ręcznie bezpośrednio z poziomu usługi Intune. Aby uzyskać więcej informacji, zobacz [Ręczne dodawanie aplikacji Portal firmy dla systemu Windows 10 przy użyciu usługi Microsoft Intune](../company-portal-app.md).

## <a name="next-steps"></a>Następne kroki

W tym przewodniku Szybki start dodano aplikacje do usługi Intune, przypisano je do grupy oraz zainstalowano je na zarejestrowanym urządzeniu z systemem Windows 10 Desktop. Aby uzyskać więcej informacji o zarządzaniu aplikacjami w usłudze Intune, zobacz: [Co to jest zarządzanie aplikacjami w usłudze Microsoft Intune?](app-management.md)

Aby zapoznać się kolejnymi przewodnikami Szybki start dotyczącymi usługi Intune, przejdź do kolejnego przewodnika Szybki start.

> [!div class="nextstepaction"]
> [Szybki start: Tworzenie i przypisywanie zasad ochrony aplikacji](quickstart-create-assign-app-policy.md)
