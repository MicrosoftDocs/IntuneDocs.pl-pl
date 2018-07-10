---
title: Wprowadzenie do zasad w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Utwórz zasady, aby chronić dane firmowe i zarządzać urządzeniami używanymi przez użytkowników końcowych w celu uzyskiwania dostępu do zasobów firmy. Następnie przypisz te zasady do grup.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1ac74ba5-7441-44ac-98b5-9d8bb8899747
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d7fa1b596a1800971919cfc0ab3e94d2d16ec328
ms.sourcegitcommit: afda8a0fc0f615e976b18ddddf81d56d7ae3566e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/20/2018
ms.locfileid: "36271528"
---
# <a name="get-started-with-creating-policies"></a>Wprowadzenie do tworzenia zasad

Zasady usługi Intune to bardzo dobry sposób na rejestrowanie urządzeń i upewnienie się, że są one zgodne z zasadami firmowymi. Zasady zgodności ułatwiają zarządzanie specjalnymi typami urządzeń, takimi jak kioski należące do firmy, oraz urządzeniami osobistymi (BYOD), tabletami i urządzeniami nienależącymi do żadnego użytkownika.

![Pulpit nawigacyjny zgodności z małą ilością danych](/intune/media/generic-compliance-dashboard.png)

Urządzeniami przenośnymi można zarządzać za pomocą zasad zgodności, które obejmują między innymi:

* Regulowanie liczby urządzeń, które użytkownik może zarejestrować w usłudze Intune
* Zarządzanie ustawieniami urządzeń, takimi jak szyfrowanie na poziomie urządzenia, długość hasła i użycie aparatu
* Dostarczanie aplikacji, profilów poczty e-mail, profilów sieci VPN i nie tylko
* Ocenianie na poziomie urządzenia kryteriów dotyczących zasad zgodności z zabezpieczeniami

Zasady zgodności są tworzone dla poszczególnych platform, takich jak systemy iOS, Android, Windows i inne. W tym ćwiczeniu użyjemy systemu iOS. Dla urządzeń z systemem iOS dostępne są następujące zasady:

* Konfiguracja kodu PIN lub hasła
* Szyfrowanie urządzenia
* Urządzenie ze zdjętymi zabezpieczeniami systemu
* Profil e-mail
* Minimalna wersja systemu operacyjnego
* Maksymalna wersja systemu operacyjnego

## <a name="create-a-policy"></a>Tworzenie zasad

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz opcję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz pozycję **Zgodność urządzeń** > **Zasady** > **Utwórz zasady**.
4. Wprowadź **nazwę** i **opis** zasady. 
5. W polu **Platforma** wybierz pozycję **iOS**.
6. W obszarze **Ustawienia** wybierz pozycję **Zabezpieczenia systemu**, a następnie dla opcji **Wymagaj hasła do odblokowania urządzeń przenośnych** ustaw wartość **Wymagaj**. 

    Możesz również ustawić inne zasady, takie jak: 
    - **Minimalna długość hasła**
    - **Wymagany typ hasła**
    - **Liczba znaków innych niż alfanumeryczne w haśle**
    
    Po zakończeniu konfigurowania zasad wybierz przycisk **OK**.
  
7. Wróć do pozycji **Utwórz zasady** i wybierz pozycję **Utwórz**. Ta czynność powoduje utworzenie zasad i wymienienie ich w obszarze **Zgodność urządzeń** > **Zasady**.
8. Wybierz swoje nowe zasady i wybierz pozycję **Przypisania**. Możesz włączyć lub wyłączyć grupy zabezpieczeń usługi Azure Active Directory (AD).
Wybierz pozycję Wybrane grupy, aby wyświetlić istniejące grupy zabezpieczeń usługi Azure AD. Wybierz grupy użytkowników, których mają dotyczyć te zasady, a następnie opcję **Zapisz**, aby je wdrożyć.

Aby zachować zgodność z nowymi zasadami firmy, po upływie kilku minut na zarejestrowanym urządzeniu zostanie wyświetlony monit dotyczący zaktualizowanego hasła. Możesz ręcznie sprawdzić aktualizację w **aplikacji Portal firmy dla systemu iOS**. Otwórz aplikację Portal firmy, wybierz nazwę urządzenia, a następnie wybierz pozycję **Synchronizuj**.

> [!NOTE]
> Zastosowanie nowych zasad stosowanych do grupy dynamicznej na wszystkich urządzeniach w grupie może potrwać do ośmiu godzin.

## <a name="next-steps"></a>Następne kroki

[Wprowadzenie do rejestrowania urządzeń](get-started-enroll.md) — poznaj środowisko rejestracji, przeprowadzając pełną rejestrację urządzenia z systemem iOS.

## <a name="learn-more"></a>Dowiedz się więcej

* [Monitorowanie zasad zgodności urządzeń Intune](compliance-policy-monitor.md)
* [Typowe sposoby korzystania z zasad dostępu warunkowego przy użyciu usługi Intune](conditional-access-intune-common-ways-use.md)
