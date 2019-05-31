---
title: Rejestrowanie urządzenia z systemem Windows w aplikacji Portal firmy usługi Intune | Microsoft Docs
description: Wprowadzenie do rejestrowania urządzenia z systemem Windows w aplikacji Portal firmy
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 05/24/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 36250832-c6fd-4e8d-b681-de735023ebc3
searchScope:
- User help
ROBOTS: ''
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: d9f29e2d737dfd7bef709f239d6c8506c3bb746c
ms.sourcegitcommit: d258bcf6716c8a2589d3f8dada819905ee80f233
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 05/24/2019
ms.locfileid: "66196878"
---
# <a name="windows-device-enrollment-in-intune-company-portal"></a>Rejestrowanie urządzenia z systemem Windows w aplikacji Portal firmy usługi Intune  

Zarejestruj swoje urządzenie z systemem Windows w aplikacji Portal firmy usługi Intune, aby uzyskać bezpieczny dostęp do służbowych aplikacji, wiadomości e-mail i plików. Jeśli Twoja organizacja wymaga lub zaleca niektóre aplikacje, np. pakiet Office lub usługę OneDrive, otrzymasz je podczas rejestracji lub będą one dostępne w portalu firmy po rejestracji.  

Urządzenia z systemem Windows 10 możesz zarejestrować za pośrednictwem witryny internetowej Portal firmy *lub* aplikacji. Jeśli chcesz zarejestrować urządzenie z wcześniejszą wersją systemu Windows, musisz to zrobić za pośrednictwem witryny internetowej Portal firmy.  

## <a name="install-company-portal-app"></a>Instalowanie aplikacji Portal firmy  
Być może aplikacja Portal firmy jest już zainstalowana na urządzeniu. Sprawdź, czy ta aplikacja znajduje się na liście __Wszystkie aplikacje__.  Jeśli lista nie zawiera aplikacji Portal firmy, wykonaj następujące kroki, aby ją zainstalować.  

1. Otwórz sklep **Microsoft Store** na urządzeniu.

2. W polu **Wyszukaj** wpisz **Portal firmy**.

3. Na liście wyników wybierz kolejno pozycje **Portal firmy** > **Zainstaluj**.

4. Wybierz pozycję **Zainstaluj** lub **Bezpłatne**. Nie ma żadnej różnicy między tymi dwiema opcjami. Są one wyświetlane w zależności od sposobu skonfigurowania aplikacji w organizacji.  

## <a name="find-windows-10-version-number"></a>Znajdywanie numeru wersji systemu Windows 10  
Kroki rejestracji różnią się dla różnych wersji urządzeń z systemem Windows 10. W poniższych krokach opisano, jak znaleźć numer wersji w systemie Windows 10 na komputerze i urządzeniu przenośnym. Jeśli znasz swoją wersję, przejdź do zalecanych kroków rejestracji.  

### <a name="windows-10-desktop-devices"></a>Urządzenia z systemem Windows 10 Desktop  

1. Przejdź do pozycji **Start**.

2. Na pasku wyszukiwania wpisz „informacje o komputerze”. Z wyników wybierz pozycję __Informacje o komputerze__.  


   ![ustawienia wyszukiwania dla opcji informacje o komputerze](media/searching_for_about_your_pc.png)  

3. Przewiń w dół do sekcji **Specyfikacja systemu Windows**, w której można znaleźć **wersję** systemu Windows 10 zainstalowanego na Twoim komputerze.  


   ![Opcja Informacje o komputerze w systemie Windows 10 Desktop](media/settings_about_pc.png)  

4. Jeśli masz wersję  

    *  __1607 lub nowszą__: zarejestruj urządzenie, wybierając kolejno pozycje [**Ustawienia** > **Konto** > **Uzyskaj dostęp do miejsca pracy lub nauki**](enroll-windows-10-device.md#enroll-windows-10-version-1607-and-later-device).   
    * __1511 lub starszą__: zarejestruj urządzenie, wybierając kolejno pozycje [**Ustawienia** > **Konto** > **Twoje konta**](enroll-windows-10-device.md#enroll-windows-10-version-1511-and-earlier-device).  

### <a name="windows-10-mobile-devices"></a>Urządzenia z systemem Windows 10 Mobile       

1.  Przejdź do ekranu __Wszystkie aplikacje__ i wybierz aplikację __Ustawienia__.  
2.  Wybierz pozycje __System__ > __Informacje__.      
3.  W obszarze __Informacje o urządzeniu__ znajdź pozycję __Wersja__.  
4. Jeśli masz wersję  

    *  __1607 lub nowszą__: zarejestruj urządzenie, wybierając kolejno pozycje [**Ustawienia** > **Uzyskaj dostęp do miejsca pracy lub nauki**](enroll-windows-10-device.md#enroll-windows-10-version-1607-and-later-device).   
    * __1511 lub starszą__: zarejestruj urządzenie, wybierając kolejno pozycje [**Ustawienia** > **Konta**](enroll-windows-10-device.md#enroll-windows-10-version-1511-and-earlier-device).  

## <a name="enroll-non-windows-10-devices"></a>Rejestrowanie urządzeń z systemem innym niż Windows 10  
Informacje o rejestrowaniu innych obsługiwanych urządzeń z systemem Windows za pośrednictwem witryny internetowej Portal firmy można znaleźć w następujących artykułach:   
* [Urządzenie z systemem Windows 8.1 lub Windows RT 8.1](enroll-your-W81-or-rt81-windows.md)  
* [Urządzenie z systemem Windows Phone 8.1](enroll-your-wp81-windows.md)    

## <a name="it-administrator-support"></a>Pomoc techniczna dla administratora IT  
Jeśli jako administrator IT napotkasz problemy podczas rejestrowania urządzeń, zobacz [Troubleshooting Windows device enrollment problems in Microsoft Intune (Rozwiązywanie problemów z rejestrowaniem urządzeń z systemem Windows w usłudze Microsoft Intune)](https://support.microsoft.com/help/4469913). W tym artykule wymieniono typowe błędy, ich przyczyny i kroki prowadzące do ich usunięcia.  

## <a name="next-steps"></a>Następne kroki  
Teraz, gdy znasz obsługiwane urządzenia i numer wersji systemu Windows 10, przejdź do zalecanego artykułu dotyczącego rejestracji.  
 
Aby uzyskać więcej informacji na temat zarządzania urządzeniami i aplikacji Portal firmy, a także jak ich używać w szkołach i w pracy, zobacz następujące artykuły:  
* [Uzyskiwanie dostępu do zasobów służbowych przy użyciu urządzeń zarządzanych](use-managed-devices-to-get-work-done.md)  
* [Co się stanie po zarejestrowaniu urządzenia w usłudze Intune](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows.md)  
* [Jakie informacje może zobaczyć moja organizacja, gdy zarejestruję swoje urządzenie?](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md)  

Potrzebujesz pomocy? Skontaktuj się z pomocą techniczną Twojej firmy. [Przejdź do witryny internetowej Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980), gdzie możesz znaleźć informacje kontaktowe pomocy informatycznej w Twojej firmie.  
