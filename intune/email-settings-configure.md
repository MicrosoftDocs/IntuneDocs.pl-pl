---
title: Jak skonfigurować ustawienia poczty e-mail w usłudze Microsoft Intune
titleSuffix: ''
description: Dowiedz się, jak skonfigurować usługę Microsoft Intune pod kątem tworzenia połączeń z firmowymi serwerami poczty e-mail na zarządzanych urządzeniach.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/1/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 15710f6115bb23dfe9ba899dfa01b38f315d00f0
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905312"
---
# <a name="how-to-configure-email-settings-in-microsoft-intune"></a>Jak skonfigurować ustawienia poczty e-mail w usłudze Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Profilów poczty e-mail można używać do konfigurowania zarządzanych urządzeń za pomocą ustawień niezbędnych do połączenia się z firmową pocztą e-mail i synchronizowania się z nią. Stanowi to gwarancję, że ustawienia są standardowe dla wszystkich urządzeń, a także pomaga zmniejszyć liczbę telefonów od użytkowników końcowych, którzy nie znają prawidłowych ustawień poczty e-mail.

Wbudowany klient poczty e-mail jest obsługiwany w przypadku większości platform. Większość aplikacji poczty e-mail innych firm nie jest obecnie obsługiwana.

Profile poczty e-mail mogą służyć do konfigurowania klienta natywnego poczty e-mail na następujących typach urządzeń:

- System Android Samsung Knox Standard 4.0 i nowsze wersje
- Urządzenia profilu służbowego systemu Android
- System iOS 8.0 i nowsze
- System Windows Phone 8.1 lub nowszy
- System Windows 10 Mobile Desktop i Windows 10 Mobile

Skorzystaj z informacji zawartych w tym artykule, aby uzyskać podstawową wiedzę z zakresu konfigurowania profilów poczty e-mail, a następnie zapoznaj się z tematami dotyczącymi poszczególnych platform, aby dowiedzieć się więcej o charakterystyce urządzeń.

## <a name="create-a-device-profile-containing-email-settings"></a>Tworzenie profilu urządzenia zawierającego ustawienia poczty e-mail

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Konfiguracja urządzeń**.
2. W okienku **Konfiguracja urządzeń** w sekcji **Zarządzanie** wybierz pozycję **Profile**.
3. W okienku profilów wybierz pozycję **Utwórz profil**.
4. W okienku **Utwórz profil** uzupełnij pola **Nazwa** i **Opis** odnoszące się do profilu poczty e-mail.
5. Z listy rozwijanej **Platforma** wybierz platformę urządzenia, do której chcesz zastosować ustawienia poczty e-mail. Obecnie dla ustawień poczty e-mail urządzenia można wybrać jedną z następujących platform:
    - **Android** (tylko system Samsung Android Knox Standard)
    - **Android enterprise**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 lub nowszy**
    - **Windows 10 lub nowszy**
6. Z listy rozwijanej **Typ profilu** wybierz pozycję **Poczta e-mail**.
7. Ustawienia, które można skonfigurować, różnią się w zależności od wybranej platformy. Szczegółowe informacje na temat ustawień każdej z platform podano w następujących tematach:
    - [Android work profile and Samsung Knox Standard settings (Ustawienia profilu służbowego w systemie Android i systemu Samsung Knox Standard)](email-settings-android.md)
    - [Ustawienia systemu iOS](email-settings-ios.md)
    - [Ustawienia systemu Windows Phone 8.1](email-settings-windows-phone-8-1.md)
    - [Windows 10 settings](email-settings-windows-10.md) (Ustawienia systemu Windows 10)
8. Gdy skończysz, wróć do okienka **Tworzenie profilu**, a następnie wybierz pozycję **Utwórz**.

Profil zostanie utworzony i wyświetlony w okienku z listą profilów.
Wskazówki umożliwiające przypisanie tego profilu do grup znajdują się w artykule [How to assign device profiles](device-profile-assign.md) (Sposoby przypisywania profilów urządzeń).

## <a name="further-information"></a>Dodatkowe informacje

### <a name="remove-an-email-profile"></a>Usuwanie profilu poczty e-mail

Jeśli chcesz usunąć profil poczty e-mail z urządzenia, zmodyfikuj przypisanie i usuń wszystkie grupy, których urządzenie jest członkiem. Nie można usunąć profilu poczty e-mail w ten sposób, gdy jest to jedyny profil poczty e-mail na urządzeniu.

### <a name="securing-email-access"></a>Zabezpieczenie dostępu do poczty e-mail

Profile poczty e-mail mogą być chronione przy użyciu jednej z dwóch metod:

1. **Certyfikaty** — podczas tworzenia profilu poczty e-mail wybierasz profil certyfikatu utworzony wcześniej w usłudze Intune. Jest on znany jako certyfikat tożsamości i jest używany do uwierzytelniania względem profilu zaufanego certyfikatu (lub certyfikatu głównego) w celu określenia, czy urządzenie użytkownika może nawiązać połączenie. Zaufany certyfikat jest przypisywany do komputera, który uwierzytelnia połączenie poczty e-mail — zwykle jest to natywny serwer poczty.
Aby uzyskać więcej informacji o sposobie tworzenia i używania profilów certyfikatów w usłudze Intune, zobacz artykuł [How to configure certificates with Intune](certificates-configure.md) (Jak skonfigurować certyfikaty z użyciem usługi Intune).
2. **Nazwa użytkownika i hasło** — użytkownik jest uwierzytelniany na natywnym serwerze poczty e-mail przez podanie nazwy użytkownika i hasła.
Hasło nie znajduje się w profilu poczty e-mail, więc użytkownik musi je podać podczas łączenia z kontem e-mail.


### <a name="how-intune-handles-existing-email-accounts"></a>Obsługa istniejących kont poczty e-mail przez usługę Intune

Jeśli użytkownik skonfigurował już konto e-mail, wynik przypisania profilu poczty e-mail usługi Intune zależy od platformy urządzeń:

- **iOS**: istniejące zduplikowane profile poczty e-mail są wykrywane na podstawie nazwy hosta i adresu e-mail. Duplikat profilu poczty e-mail blokuje możliwość przypisywania profilu usługi Intune. W takim przypadku w witrynie Portal firmy zostanie wyświetlony komunikat dla użytkownika z informacją, że profil nie jest zgodny, oraz monitem o usunięcie ręcznie skonfigurowanego profilu. Aby uniknąć takich sytuacji, poleć użytkownikom, aby dokonali rejestracji przed zainstalowaniem profilu poczty e-mail — dzięki temu usługa Intune będzie mogła samodzielnie skonfigurować profil.
- **Windows**: istniejące zduplikowane profile poczty e-mail są wykrywane na podstawie nazwy hosta i adresu e-mail. Usługa Intune zastępuje istniejący profil poczty e-mail utworzony przez użytkownika.
- **Android Samsung Knox Standard**: istniejące zduplikowane profile poczty e-mail są wykrywane na podstawie adresu e-mail i zastępowane przez profil usługi Intune.
Ponieważ system Android nie używa nazwy hosta do identyfikowania profilu, nie zalecamy tworzenia wielu profilów poczty e-mail do użycia dla tego samego adresu e-mail na różnych hostach, ponieważ będą one się nawzajem zastępować.
- **Profile służbowe w systemie Android** Usługa Intune udostępnia dwa służbowe profile poczty e-mail systemu Android — jeden dla aplikacji poczty e-mail Gmail i drugi dla aplikacji Nine Work. Aplikacje te, dostępne w sklepie Google Play, są instalowane w profilu służbowym urządzenia, dlatego powstanie zduplikowanych profilów jest wykluczone. Obie aplikacje obsługują połączenia z programem Exchange. Aby włączyć łączność za pośrednictwem poczty e-mail, wdróż jedną z tych aplikacji na urządzeniach użytkowników, a następnie utwórz i wdróż odpowiedni profil poczty e-mail. Aplikacje poczty e-mail, takie jak Nine Work, mogą nie być bezpłatne. Sprawdź szczegóły licencji aplikacji lub skontaktuj się z producentem aplikacji, jeśli masz jakieś pytania.

### <a name="update-an-email-profile"></a>Aktualizowanie profilu poczty e-mail

W przypadku wprowadzenia zmian w zakresie przypisanego wcześniej profilu poczty e-mail użytkownicy końcowi mogą zobaczyć monit o zatwierdzenie nowej konfiguracji ich ustawień poczty e-mail.
