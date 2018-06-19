---
title: Konfigurowanie strony ze stanem rejestracji
titleSuffix: Microsoft Intune
description: Powitaj użytkowników, którzy rejestrują urządzenia z systemem Windows 10.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 5/17/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c6604c35cebdad4341f27a51db1a4c735f9a9818
ms.sourcegitcommit: 6bd5867c41fb5288fde114dbfcc127dd206f7148
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
ms.locfileid: "34235624"
---
# <a name="set-up-an-enrollment-status-page"></a>Konfigurowanie strony ze stanem rejestracji
 
[!INCLUDE [azure_portal](./includes/azure_portal.md)]
 
Podczas instalacji urządzenia na stronie ze stanem rejestracji są wyświetlane informacje o stanie instalacji na urządzeniu użytkownika końcowego. Niektóre aplikacje, profile i certyfikaty mogą nie być w pełni zainstalowane, zanim użytkownik nie zostanie zarejestrowany. Strona stanu może pomóc użytkownikom zinterpretować stan urządzenia w trakcie i po rejestracji. Możesz włączyć stronę stanu dla wszystkich Twoich użytkowników oraz uniemożliwić użytkownikom korzystanie z urządzenia do chwili zainstalowania wszystkich przypisanych aplikacji i profilów.
 
Aby włączyć stronę ze stanem rejestracji dla wszystkich Twoich użytkowników końcowych, wykonaj poniższe kroki.
 
1.  W usłudze [Intune](https://aka.ms/intuneportal) wybierz **Rejestracja urządzenia** > **Rejestracja systemu Windows** > **Strona ze stanem rejestracji (wersja zapoznawcza)**.
2.  W bloku **Strona ze stanem rejestracji** wybierz pozycje **Domyślne** > **Ustawienia**.
3.  Aby **wyświetlić postęp instalacji aplikacji i profilu**, wybierz pozycję **Tak**.
4.  Wybierz inne ustawienia, które chcesz włączyć, a następnie wybierz pozycję **Zapisz**.
 
## <a name="enrollment-status-page-tracking-information"></a>Informacje śledzenia strony ze stanem rejestracji

Strona stanu śledzi informacje o przygotowywaniu urządzenia, konfiguracji urządzenia i ustawieniach konta.

### <a name="device-preparation"></a>Przygotowywanie urządzenia

W przypadku przygotowywania urządzenia strona ze stanem rejestracji śledzi zaświadczenia klucza modułu Trusted Platform Module (TPM) (jeśli jest to wymagane), postęp dołączania do usługi Azure Active Directory i rejestracji w usłudze Intune.

### <a name="device-setup"></a>Konfiguracja urządzenia

W przypadku konfiguracji urządzenia strona ze stanem rejestracji śledzi następujące elementy, jeśli są one przypisane do wszystkich urządzeń:
- Zasady zabezpieczeń
    - Jeden dostawca usług konfiguracji (CSP) dla wszystkich rejestracji.
    - Faktyczni dostawcy usług konfiguracji skonfigurowani za pomocą usługi Intune nie są śledzeni w tym miejscu.
- Aplikacje
    - Biznesowe aplikacje MSI na maszynę.
    - Aplikacje magazynu biznesowego z kontekstem instalacji = urządzenie.
    - Aplikacje magazynu offline i biznesowego z kontekstem instalacji = urządzenie.
- Profile połączeń (sieci VPN i Wi-Fi) nie są jeszcze śledzone, więc zawsze będzie się pojawiała informacja „0 z 0”.
- Certyfikaty nie są jeszcze śledzone, więc zawsze będzie się pojawiała informacja „0 z 0”.

### <a name="account-setup"></a>Konfigurowanie kont
W przypadku konfigurowania konta strona ze stanem rejestracji śledzi następujące elementy:
- Zasady zabezpieczeń
    - Jeden dostawca usług konfiguracji dla wszystkich rejestracji.
    - Faktyczni dostawcy usług konfiguracji skonfigurowani za pomocą usługi Intune nie są śledzeni w tym miejscu.
- Aplikacje
    - Aplikacje biznesowe MSI na użytkownika, które są przypisane do wszystkich urządzeń, wszystkich użytkowników lub grupy użytkowników, której członkiem jest użytkownik rejestrujący urządzenie.
    - Aplikacje biznesowe MSI na maszynę, które są przypisane do wszystkich użytkowników lub grupy użytkowników, której członkiem jest użytkownik rejestrujący urządzenie.
    - Aplikacje magazynu biznesowego, które są przypisane do wszystkich urządzeń, wszystkich użytkowników lub grupy użytkowników, której członkiem jest użytkownik rejestrujący urządzenie z kontekstem instalacji = użytkownik.
    - Aplikacje magazynu online, które są przypisane do wszystkich urządzeń, wszystkich użytkowników lub grupy użytkowników, której członkiem jest użytkownik rejestrujący urządzenie z kontekstem instalacji = użytkownik.
    - Aplikacje magazynu offline, które są przypisane do wszystkich urządzeń, wszystkich użytkowników lub grupy użytkowników, której członkiem jest użytkownik rejestrujący urządzenie z kontekstem instalacji = użytkownik.
- Profile połączeń
    - Profile sieci VPN lub Wi-Fi, które są przypisane do wszystkich użytkowników lub grupy użytkowników, której członkiem jest użytkownik rejestrujący urządzenie.
- Certyfikaty
    - Profile certyfikatów, które są przypisane do wszystkich użytkowników lub grupy użytkowników, której członkiem jest użytkownik rejestrujący urządzenie.

## <a name="next-steps"></a>Następne kroki
Po skonfigurowaniu strony rejestracji w systemie Windows dowiedz się, jak zarządzać urządzeniami z systemem Windows. Aby uzyskać więcej informacji, zobacz artykuł [Co to jest zarządzanie urządzeniami w usłudze Microsoft Intune?](https://docs.microsoft.com/intune/device-management)