---
title: Ustawienia kiosku dla urządzeń z systemem Windows i Holographic w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Skonfiguruj urządzenia z systemem Windows 10 (i nowszym) oraz Windows Holographic for Business jako kioski z pojedynczą aplikacją oraz z wieloma aplikacjami, dostosuj menu Start, dodaj aplikacje i pasek zadań oraz skonfiguruj przeglądarkę internetową usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.openlocfilehash: beb1c63e672c08963ba822e6cee2bf8a69456dac
ms.sourcegitcommit: e08a26558174be3ea8f3d20646e577f1493ea21a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54831347"
---
# <a name="windows-10-and-windows-holographic-for-business-device-settings-to-run-as-a-dedicated-kiosk-using-intune"></a>Ustawienia urządzenia z systemem Windows 10 i Windows Holographic for Business, które ma działać jako dedykowany kiosk przy użyciu usługi Intune

Na urządzeniach z systemem Windows 10 możesz użyć usługi Intune, aby uruchamiać urządzenia jako kiosk — czasami jest to nazywane urządzeniem dedykowanym. Urządzenie w trybie kiosku może uruchamiać jedną aplikację lub wiele aplikacji. Możesz wyświetlić i dostosować menu Start, dodać różne aplikacje, w tym aplikacje Win32, dodać określoną stronę główną do przeglądarki internetowej i wykonywać inne czynności. 

Ta funkcja ma zastosowanie do urządzeń z systemem:

- System Windows 10 lub nowszy
- Windows Holographic for Business

Usługa Intune obsługuje jeden profil kiosku na urządzenie. Jeśli potrzebujesz wielu profilów kiosku w jednym urządzeniu, możesz użyć [niestandardowego identyfikatora OMA-URI](custom-settings-windows-10.md).

„Profile konfiguracji” są używane w usłudze Intune do tworzenia i dostosowywania tych ustawień na potrzeby organizacji. Po dodaniu tych funkcji w profilu należy wypchnąć lub wdrożyć te ustawienia do grup w organizacji.

W tym artykule przedstawiono sposób tworzenia profilu konfiguracji urządzenia. Aby uzyskać listę wszystkich ustawień i ich zadań, zobacz tematy [Windows 10 kiosk settings](kiosk-settings-windows.md) (Ustawienia kiosku systemu Windows 10) i [Windows Holographic for Business kiosk settings](kiosk-settings-holographic.md) (Ustawienia kiosku systemu Windows Holographic for Business).

## <a name="create-the-profile"></a>Tworzenie profilu

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi** > wpisz nazwę usługi **Intune** w filtrze > wybierz pozycję **Microsoft Intune**.
2. Wybierz kolejno pozycje **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Wprowadź następujące właściwości:

   - **Nazwa**: Wprowadź opisową nazwę nowego profilu.
   - **Opis**: Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
   - **Platforma**: Wybierz pozycję **Windows 10 i nowsze**
   - **Typ profilu**: Wybierz pozycję **Kiosk**

4. W obszarze **Ustawienia** wybierz **tryb kiosku**. **Tryb kiosku** wskazuje typ trybu kiosku obsługiwany przez zasady. Dostępne opcje:

    - **Nieskonfigurowane** (wartość domyślna): Te zasady nie umożliwiają korzystania z trybu kiosku.
    - **Kiosk z pojedynczą aplikacją w trybie pełnoekranowym**: Urządzenie działa jako jedno konto użytkownika i blokuje je do pojedynczej aplikacji ze Sklepu. Gdy użytkownik zaloguje się, jest uruchamiana konkretna aplikacja. Ten tryb uniemożliwia także użytkownikowi otwieranie nowych aplikacji oraz zmianę uruchomionej aplikacji.
    - **Kiosk z wieloma aplikacjami**: W urządzeniu działa wiele aplikacji ze Sklepu, aplikacji Win32 lub aplikacji skrzynki odbiorczej systemu Windows dzięki użyciu identyfikatora modelu użytkownika aplikacji (AUMID). Tylko dodane aplikacje są dostępne w urządzeniu.

        Korzyści z kiosku z wieloma aplikacjami (czyli urządzenia o stałym przeznaczeniu) polegają na udostępnieniu użytkownikom łatwego do poznania środowiska, w którym są dostępne tylko potrzebne im aplikacje. Aplikacje, których użytkownicy nie potrzebują, są usuwane z widoku.

    Listę wszystkich ustawień i ich zadań można znaleźć w temacie:
      - [Windows 10 kiosk settings](kiosk-settings-windows.md) (Ustawienia kiosku systemu Windows 10)
      - [Windows Holographic for Business kiosk settings](kiosk-settings-holographic.md) (Ustawienia kiosku systemu Windows Holographic for Business)

5. Po zakończeniu wybierz kolejno pozycje **OK** > **Utwórz**, aby zapisać zmiany. 

Profil zostanie utworzony i wyświetlony na liście profilów. Teraz należy [przypisać](device-profile-assign.md) profil.

## <a name="next-steps"></a>Następne kroki

[Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).

Profile kiosku można tworzyć dla urządzeń, na których działają następujące platformy:
- [Android](device-restrictions-android.md#kiosk)
- [Android Enterprise](device-restrictions-android-for-work.md#kiosk-settings)
- [Windows 10 lub nowszy](kiosk-settings-windows.md)
- [Windows Holographic for Business](kiosk-settings-holographic.md)
