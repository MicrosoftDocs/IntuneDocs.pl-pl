---
title: Konfigurowanie strony ze stanem rejestracji
titleSuffix: Microsoft Intune
description: Powitaj użytkowników, którzy rejestrują urządzenia z systemem Windows 10.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
ms.reviewer: damionw
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: ada9fee575824d27a6bfdd8f14d4845d228467db
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52186089"
---
# <a name="set-up-an-enrollment-status-page"></a>Konfigurowanie strony ze stanem rejestracji
 
[!INCLUDE [azure_portal](./includes/azure_portal.md)]
 
Podczas konfigurowania urządzenia na stronie ze stanem rejestracji są wyświetlane informacje o instalacji na urządzeniu. Niektóre aplikacje, profile i certyfikaty mogą nie zostać zainstalowane do czasu ukończenia rejestracji przy pierwszym uruchomieniu i zalogowania się do urządzenia. Strona ze stanem rejestracji może pomóc użytkownikom zinterpretować stan urządzenia w trakcie konfigurowania. Możesz utworzyć wiele profilów strony ze stanem rejestracji i zastosować je do różnych grup. Profile możesz ustawiać w następujących celach:
- Wyświetlanie postępu instalacji.
- Blokowanie użycia do zakończenia instalacji.
- Określanie czynności, które użytkownik może wykonać, jeśli konfigurowanie urządzenia nie powiedzie się.

Ponadto możesz ustawić kolejność priorytetu dla każdego profilu w celu obsłużenia konfliktu przypisań profilu w przypadku tego samego użytkownika lub urządzenia.

 
## <a name="turn-on-default-enrollment-status-page-for-all-users"></a>Włączanie domyślnej strony stanu rejestracji dla wszystkich użytkowników

Aby włączyć stronę ze stanem rejestracji, wykonaj poniższe kroki.
 
1. W usłudze [Intune](https://aka.ms/intuneportal) wybierz **Rejestracja urządzenia** > **Rejestracja systemu Windows** > **Strona ze stanem rejestracji (wersja zapoznawcza)**.
2. W bloku **Strona ze stanem rejestracji** wybierz pozycje **Domyślne** > **Ustawienia**.
3. Aby **wyświetlić postęp instalacji aplikacji i profilu**, wybierz pozycję **Tak**.
4. Wybierz inne ustawienia, które chcesz włączyć, a następnie wybierz pozycję **Zapisz**.

## <a name="create-enrollment-status-page-profile-and-assign-to-a-group"></a>Tworzenie profilu strony ze stanem rejestracji i przypisywanie do grupy

1. W usłudze [Intune](https://aka.ms/intuneportal) wybierz pozycje **Rejestracja urządzenia** > **Rejestracja systemu Windows** > **Strona ze stanem rejestracji (wersja zapoznawcza)** > **Utwórz profil**.
2. Podaj **nazwę** i **opis**.
3. Wybierz pozycję **Utwórz**.
4. Wybierz nowy profil z listy **Strona ze stanem rejestracji**.
5. Wybierz pozycje **Przypisania** > **Wybierz grupy** > wybierz grupy, które mają być ujęte w tym profilu > **Wybierz** > **Zapisz**.
6. Wybierz pozycje **Ustawienia** > wybierz ustawienia, które chcesz zastosować do tego profilu > **Zapisz**.

## <a name="set-the-enrollment-status-page-priority"></a>Ustawianie priorytetu strony ze stanem rejestracji

Urządzenie lub użytkownik mogą należeć do wielu grup i mieć wiele profilów stron ze stanem rejestracji. Aby obsłużyć takie konflikty, możesz ustawić priorytety dla każdego profilu. Jeśli dana osoba ma więcej niż jeden profil strony ze stanem rejestracji, zostanie zastosowany tylko profil o najwyższym priorytecie.

1. W usłudze [Intune](https://aka.ms/intuneportal) wybierz **Rejestracja urządzenia** > **Rejestracja systemu Windows** > **Strona ze stanem rejestracji (wersja zapoznawcza)**.
2. Zatrzymaj wskaźnik myszy nad profilem na liście.
3. Używając trzech pionowych punktów, przeciągnij profil do żądanej pozycji na liście.


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
- Profile połączeń
    - Profile sieci VPN lub Wi-Fi przypisane do **wszystkich urządzeń** lub grupy urządzeń, do której należy rejestrowane urządzenie, ale tylko w przypadku urządzeń rozwiązania Autopilot
- Profile certyfikatów przypisane do **wszystkich urządzeń** lub grupy urządzeń, do której należy rejestrowane urządzenie, ale tylko w przypadku urządzeń rozwiązania Autopilot

### <a name="account-setup"></a>Konfigurowanie kont
W przypadku konfigurowania konta strona ze stanem rejestracji śledzi następujące elementy:
- Zasady zabezpieczeń
    - Jeden dostawca usług konfiguracji dla wszystkich rejestracji.
    - Faktyczni dostawcy usług konfiguracji skonfigurowani za pomocą usługi Intune nie są śledzeni w tym miejscu.
- Aplikacje
    - Aplikacje biznesowe MSI na użytkownika, które są przypisane do wszystkich urządzeń, wszystkich użytkowników lub grupy użytkowników, której członkiem jest użytkownik rejestrujący urządzenie.
    - Aplikacje biznesowe MSI na maszynę, które są przypisane do wszystkich użytkowników lub grupy użytkowników, której członkiem jest użytkownik rejestrujący urządzenie.
    - Aplikacje magazynu biznesowego, aplikacje magazynu online i aplikacje magazynu offline przypisane do dowolnego z następujących elementów:
        - Wszystkie urządzenia
        - Wszyscy użytkownicy
        - grupa użytkowników, w której użytkownik rejestrujący urządzenie jest członkiem z kontekstem instalacji ustawionym na wartość Użytkownik.
- Profile połączeń
    - Profile sieci VPN lub Wi-Fi, które są przypisane do wszystkich użytkowników lub grupy użytkowników, której członkiem jest użytkownik rejestrujący urządzenie.
- Certyfikaty
    - Profile certyfikatów, które są przypisane do wszystkich użytkowników lub grupy użytkowników, której członkiem jest użytkownik rejestrujący urządzenie.

## <a name="next-steps"></a>Następne kroki
Po skonfigurowaniu strony rejestracji w systemie Windows dowiedz się, jak zarządzać urządzeniami z systemem Windows. Aby uzyskać więcej informacji, zobacz artykuł [Co to jest zarządzanie urządzeniami w usłudze Microsoft Intune?](https://docs.microsoft.com/intune/device-management)
