---
title: Konfigurowanie programu Google Chrome dla urządzeń z systemem Android przy użyciu usługi Microsoft Intune
titleSuffix: Microsoft Intune
description: Używanie zasad konfiguracji usługi Intune z programem Google Chrome dla urządzeń z systemem Android.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/07/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2f667940cc238fe243b05c7ab6f1459f63f18faa
ms.sourcegitcommit: 2c8a41ee95a3fde150667a377770e51b621ead65
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2019
ms.locfileid: "73635489"
---
# <a name="configure-google-chrome-for-android-devices-using-intune"></a>Konfigurowanie programu Google Chrome dla urządzeń z systemem Android przy użyciu usługi Microsoft Intune 

Używanie zasad konfiguracji usługi Intune w celu skonfigurowania programu Google Chrome dla urządzeń z systemem Android. Ustawienia aplikacji mogą być stosowane automatycznie. Można na przykład ustawić zakładki i adresy URL, które mają być blokowane lub dozwolone.

## <a name="prerequisites"></a>Wymagania wstępne

- Urządzenie użytkownika z systemem Android Enterprise musi być zarejestrowane w usłudze Intune. Aby uzyskać więcej informacji, zobacz [Konfigurowanie rejestracji urządzeń z profilem służbowym systemu Android Enterprise](~/enrollment/android-work-profile-enroll.md).
- Przeglądarka Google Chrome jest dodawana jako zarządzana aplikacja Google Play. Aby uzyskać więcej informacji o zarządzanym sklepie Google Play, zobacz [Łączenie konta usługi Intune z kontem zarządzanego sklepu Google Play](~/enrollment/connect-intune-android-enterprise.md).

## <a name="add-the-google-chrome-app-to-intune"></a>Dodawanie aplikacji Google Chrome do usługi Intune

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. W okienku **Intune**  wybierz kolejno pozycje **Aplikacje klienckie** > **Aplikacje** > **Dodaj**, a następnie dodaj aplikację **Zarządzany sklep Google Play**.
3. Przejdź do zarządzanego sklepu Google Play, wyszukaj aplikację **Google Chrome**  i zatwierdź ją.

    ![Wyszukiwanie i zatwierdzanie aplikacji Google Chrome](~/apps/media/apps-configure-chrome-android/search.png)

4. Przypisz aplikację Google Chrome do grupy użytkowników jako wymagany typ aplikacji. Aplikacja Google Chrome zostanie wdrożona automatycznie po zarejestrowaniu urządzenia w usłudze Intune.

Aby uzyskać dodatkowe informacje na temat dodawania aplikacji zarządzanego sklepu Google Play do usługi Intune, zobacz [Aplikacje zarządzanego sklepu Google Play](~/apps/apps-add-android-for-work.md#managed-google-play-store-apps).

## <a name="add-app-configuration-for-managed-ae-devices"></a>Dodawanie konfiguracji aplikacji dla zarządzanych urządzeń AE

1. W okienku [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) wybierz pozycje **Zasady konfiguracji aplikacji** > **Dodaj**.
2. Dodaj nazwę zasad, wybierz pozycję **Urządzenia zarządzane** w obszarze Typ rejestracji urządzenia i **Android** w obszarze Platforma.

    ![Dodawanie zasad konfiguracji aplikacji Google Chrome](~/apps/media/apps-configure-chrome-android/add-policy.png)

3. Kliknij pozycję **Skojarzona aplikacja** i wybierz pozycję **Google Chrome** .

    ![Wybieranie pozycji Google Chrome w obszarze Skojarzona aplikacja](~/apps/media/apps-configure-chrome-android/associated-app.png)

4. Kliknij pozycję **Ustawienia konfiguracji**, wybierz opcję **Użyj projektanta konfiguracji**, a następnie kliknij przycisk **Dodaj**, aby wybrać klucze konfiguracji.

    ![Dodawanie opcji Użyj projektanta konfiguracji](~/apps/media/apps-configure-chrome-android/configuration.png)

    Poniżej przedstawiono przykład typowych ustawień:
    - **Blokuj dostęp do listy adresów URL** : `["*"]`
    - **Zezwalaj na dostęp do listy adresów URL** : `["baidu.com", "yahoo.com", "chrome://*"]`
    - **Zakładki zarządzane**: `[{"toplevel_name": "My managed bookmarks folder"  },  {"url": "baidu.com",   "name": "Baidu"},  {"url": "youtube.com", "name": "Youtube"},  {"name": "Chrome links",  "children": [{"url": "chromium.org", "name": "Chromium"},    {"url": "dev.chromium.org", "name": "Chromium Developers"}]}]`
    - **Dostępność trybu incognito**: `Incognito mode disabled`

    Po dodaniu ustawień konfiguracji za pomocą projektanta konfiguracji zostaną one wyświetlone w tabeli. 

    ![Typowe ustawienia](~/apps/media/apps-configure-chrome-android/common-settings.png)

    Powyższe ustawienia tworzą zakładki i zezwalają na dostęp do wszystkich witryn sieci Web z wyjątkiem `baidu.com`, `yahoo.com` i `chrome://`.

5. Kliknij **OK**  i **Dodaj**, aby dodać zasady konfiguracji do usługi Intune.
6. Przypisz te zasady konfiguracji do grupy użytkowników. Aby uzyskać więcej informacji, zobacz [Przypisywanie aplikacji do grup w usłudze Microsoft Intune](~/apps/apps-deploy.md). 

## <a name="verify-the-device-settings"></a>Weryfikowanie ustawień urządzenia

Gdy urządzenie z systemem Android zostanie zarejestrowane w systemie Android Enterprise, zarządzana aplikacja Google Chrome z ikoną portfolio zostanie wdrożona automatycznie.
 
   <img alt="Managed Google Chrome with the portfolio icon" src="~/apps/media/apps-configure-chrome-android/chrome-icon.png" width="350">

Uruchom program Google Chrome, a znajdziesz zastosowane ustawienia.

   Zakładki:<br>
   <img alt="Bookmarks" src="~/apps/media/apps-configure-chrome-android/bookmarks.png" width="350">

   Zablokowany adres URL:<br>
   <img alt="Blocked URL" src="~/apps/media/apps-configure-chrome-android/blocked-url.png" width="350">

   Dozwolony adres URL:<br>
   <img alt="Allow URL" src="~/apps/media/apps-configure-chrome-android/allowed-url.png" width="350">

   Karta incognito:<br>
   <img alt="Incognito tab" src="~/apps/media/apps-configure-chrome-android/incognito-tab.png" width="350">

## <a name="troubleshooting"></a>Rozwiązywanie problemów

1. Sprawdź portal usługi Intune, aby monitorować stan wdrożenia zasad.

    ![Monitorowanie stanu wdrożenia zasad](~/apps/media/apps-configure-chrome-android/monitor-status.png)

2. Uruchom aplikację Google Chrome i odwiedź stronę **chrome://policy**. Możemy potwierdzić, czy ustawienia zostały zastosowane pomyślnie.

    ![Sprawdzanie, czy ustawienia zostały zastosowane pomyślnie](~/apps/media/apps-configure-chrome-android/confirm.png)

## <a name="additional-information"></a>Dodatkowe informacje

- [Dodawanie zasad konfiguracji aplikacji dla zarządzanych urządzeń z systemem Android Enterprise](~/app-configuration-policies-use-android.md)
- [Lista zasad systemu Chrome Enterprise](https://cloud.google.com/docs/chrome-enterprise/policies/)

## <a name="next-steps"></a>Następne kroki

- Aby uzyskać więcej informacji o w pełni zarządzanych urządzeniach dla rozwiązania Android Enterprise, zobacz temat [Konfiguracja rejestracji w usłudze Intune dla w pełni zarządzanych urządzeń z systemem Android Enterprise (wersja zapoznawcza)](~/enrollment/android-fully-managed-enroll.md).
