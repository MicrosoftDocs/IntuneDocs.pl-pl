---
title: Samouczek — konfigurowanie usługi Slack do używania usługi Intune na potrzeby konfiguracji rozwiązania EMM i aplikacji
titleSuffix: Microsoft Intune
description: W tym samouczku skonfigurujesz usługę Slack do używania usługi Intune na potrzeby konfiguracji rozwiązania EMM i aplikacji.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: tutorial
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 55db37c5-0da7-4d9c-8027-525afb1c6349
Customer intent: As an Intune admin, I want to learn how to configure Slack to use Intune for EMM and app configuration..
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cd0a4b0c5e0b4cbaa7ef43ec40cddb3ab30d3070
ms.sourcegitcommit: 51591b862d97904291af7aa53a6eb341b11a761e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2020
ms.locfileid: "77415480"
---
# <a name="tutorial-configure-slack-to-use-intune-for-emm-and-app-configuration"></a>Samouczek: konfigurowanie usługi Slack do używania usługi Intune na potrzeby konfiguracji rozwiązania EMM i aplikacji

Slack to aplikacja do współpracy używana w usłudze Microsoft Intune.   

W tym samouczku wykonasz następujące czynności:
> [!div class="checklist"]
> - Ustawianie usługi Intune jako dostawcy usługi Enterprise Mobility Management (EMM) w rozwiązaniu Slack Enterprise Grid. Będzie można ograniczyć dostęp do obszarów roboczych planu rozwiązania Grid na urządzeniach zarządzanych przez usługę Intune.
> - Tworzenie zasad konfiguracji aplikacji w celu zarządzania aplikacją Slack for EMM w systemie iOS i aplikacją Slack dla urządzeń z profilem służbowym systemu Android.
> - Tworzenie zasad zgodności urządzeń w usłudze Intune w celu ustawienia warunków, które urządzenia z systemem Android i iOS muszą spełniać, aby zostały uznane za zgodne.

Jeśli nie masz subskrypcji usługi Intune, [utwórz konto bezpłatnej wersji próbnej](../fundamentals/free-trial-sign-up.md).

## <a name="prerequisites"></a>Wymagania wstępne
W tym samouczku będziesz potrzebować dzierżawy testowej z następującymi subskrypcjami:
- Azure Active Directory Premium ([bezpłatna wersja próbna](https://azure.microsoft.com/free/?WT.mc_id=A261C142F))
- Subskrypcja usługi Intune ([bezpłatna wersja próbna](../fundamentals/free-trial-sign-up.md))

Będziesz również potrzebować planu [Slack Enterprise Grid](https://get.slack.help/hc/articles/360004150931-What-is-Slack-Enterprise-Grid-).

## <a name="configure-your-slack-enterprise-grid-plan"></a>Konfigurowanie planu Slack Enterprise Grid
Włącz rozwiązanie EMM w planie Slack Enterprise Grid, postępując zgodnie z [instrukcjami dotyczącymi aplikacji Slack](https://get.slack.help/hc/articles/115002579426-Enable-Enterprise-Mobility-Management-for-your-org#step-2:-turn-on-emm), i [połącz usługę Azure Active Directory](https://docs.microsoft.com/azure/active-directory/saas-apps/slack-tutorial) jako dostawcę tożsamości planu Grid.

## <a name="sign-in-to-intune"></a>Logowanie się do usługi Intune
Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) jako administrator globalny lub administrator usługi Intune. Jeśli utworzono subskrypcję wersji próbnej usługi Intune, konto, którego użyto do utworzenia subskrypcji, jest administratorem globalnym.

## <a name="set-up-slack-for-emm-on-ios-devices"></a>Konfigurowanie aplikacji Slack for EMM na urządzeniach z systemem iOS
Dodaj aplikację Slack for EMM dla systemu iOS do dzierżawy usługi Intune, a następnie utwórz zasady konfiguracji aplikacji, aby umożliwić użytkownikom systemu iOS w organizacjach uzyskiwanie dostępu do aplikacji Slack przy użyciu usługi Intune jako dostawcy usługi EMM.

### <a name="add-slack-for-emm-to-intune"></a>Dodawanie aplikacji Slack for EMM do usługi Intune
Dodaj aplikację Slack for EMM jako zarządzaną aplikację systemu iOS w usłudze Intune i przypisz do niej użytkowników usługi Slack. Aplikacje są specyficzne dla platformy, dlatego musisz dodać osobną aplikację usługi Intune dla użytkowników usługi Slack na urządzeniach z systemem Android.
1. W centrum administracyjnym wybierz pozycję **Aplikacje** > **Wszystkie aplikacje** > **Dodaj**.
2. W obszarze **Typ aplikacji** wybierz aplikację ze sklepu dla systemu **iOS**.
3. Wybierz opcję **Wyszukaj w sklepie App Store**. Wprowadź termin wyszukiwany „Slack for EMM”, a następnie wybierz aplikację. Kliknij pozycję **Wybierz** w okienku **Wyszukaj w sklepie App Store**.
4. Wybierz pozycję **Informacje o aplikacji** i skonfiguruj odpowiednio wymagane zmiany. Wybierz przycisk **OK**, aby ustawić informacje o aplikacji.
5. Kliknij pozycję **Dodaj**.
6. Wybierz pozycję **Przypisania**.
7. Kliknij pozycję **Dodawanie grupy**. W zależności od tego, na kogo ma wpływać włączenie rozwiązania EMM dla usługi Slack, w obszarze **Typ przypisania** możesz wybrać pozycję:
    - **Dostępne dla zarejestrowanych urządzeń** w przypadku wybrania opcji „Wszyscy członkowie (w tym goście)” LUB
    - **Dostępne z rejestracją lub bez nie** w przypadku wybrania opcji „Wszyscy członkowie (z wyjątkiem gości)" lub „Opcjonalnie”.
8. Wybierz pozycję **Objęte grupy** i w obszarze **Udostępnij tę aplikację wszystkim użytkownikom** wybierz pozycję **Tak**.
9. Kliknij przycisk **OK**, a następnie kliknij ponownie przycisk **OK**, aby dodać grupę.
10. Kliknij przycisk **Zapisz**.

### <a name="add-an-app-configuration-policy-for-slack-for-emm"></a>Dodawanie zasad konfiguracji aplikacji Slack for EMM
Dodaj zasady konfiguracji aplikacji Slack for EMM dla systemu iOS/iPadOS. Zasady konfiguracji aplikacji dla urządzeń zarządzanych są specyficzne dla platformy, dlatego trzeba dodać osobne zasady dla użytkowników usługi Slack na urządzeniach z systemem Android.
1. W centrum administracyjnym wybierz pozycję **Aplikacje** > **Zasady konfiguracji aplikacji** > **Dodaj** > **Urządzenia zarządzane**.
2. W polu Nazwa wprowadź frazę „Test zasad konfiguracji aplikacji Slack”.
3. W obszarze Typ rejestracji urządzenia sprawdź, czy ustawiono pozycję **Urządzenia zarządzane**.
4. W polu Platforma wybierz pozycję **iOS**.
5. Wybierz pozycję **Skojarzona aplikacja**.
6. Na pasku wyszukiwania wprowadź frazę „Slack for EMM” i wybierz aplikację.
7. Kliknij przycisk **OK**, a następnie wybierz pozycję **Ustawienia konfiguracji**. 
8. Wybierz przycisk **OK**, a następnie pozycję **Dodaj**.
9. Na pasku wyszukiwania wprowadź frazę „Test zasad konfiguracji aplikacji Slack”, a następnie wybierz właśnie dodane zasady.
10. Z obszaru zarządzania wybierz pozycję **Przypisania**.
11. W obszarze Przypisz do wybierz pozycję **Wszyscy użytkownicy i wszystkie urządzenia**.
12. Kliknij przycisk **Zapisz**.

### <a name="optional-create-an-ios-device-compliance-policy"></a>(Opcjonalnie) Tworzenie zasad zgodności urządzeń z systemem iOS
Skonfiguruj zasady zgodności urządzeń z systemem iOS w usłudze Intune w celu ustawienia warunków, które urządzenie musi spełniać, aby zostało uznane za zgodne. W tym samouczku utworzymy zasady zgodności urządzeń z systemem iOS. Zasady zgodności są specyficzne dla platformy, dlatego trzeba dodać osobne zasady dla użytkowników usługi Slack na urządzeniach z systemem Android.
1. W centrum administracyjnym wybierz pozycję **Zgodność urządzeń** > **Zasady** > **Utwórz zasady**.
2. W obszarze Nazwa wprowadź frazę „Test zasad zgodności dla systemu iOS”.
3. W obszarze Opis wprowadź frazę „Test zasad zgodności dla systemu iOS”.
4. W polu Platforma wybierz pozycję **iOS**.
5. Wybierz pozycję **Kondycja urządzenia**. Obok pozycji Urządzenia ze zdjętymi zabezpieczeniami systemu wybierz pozycję **Blokuj**, a następnie wybierz przycisk **OK**.
6. Wybierz pozycję **Zabezpieczenia systemu** i wprowadź ustawienia w obszarze Hasło. Na potrzeby tego samouczka wybierz następujące zalecane ustawienia:
    - W obszarze Wymagaj hasła do odblokowania urządzeń przenośnych wybierz pozycję **Wymagaj**.
    - W obszarze Proste hasła wybierz pozycję **Blokuj**.
    - W obszarze Minimalna długość hasła wprowadź wartość 4.
    - W obszarze Wymagany typ hasła wybierz pozycję **Alfanumeryczne**.
    - W obszarze Maksymalna liczba minut po zablokowaniu ekranu, po których jest wymagane wprowadzenie hasła wybierz pozycję **Natychmiast**.
    - W obszarze Wygaśnięcie hasła (dni) wprowadź wartość 41.
    - W obszarze Liczba poprzednich haseł, których nie można użyć ponownie wprowadź wartość 5.
7. Kliknij przycisk **OK**, a następnie ponownie wybierz przycisk **OK**.
8. Kliknij przycisk **Utwórz**.

## <a name="set-up-slack-on-android-work-profile-devices"></a>Konfigurowanie usługi Slack na urządzeniach z profilem służbowym systemu Android
Dodaj aplikację Slack z zarządzanego sklepu Google Play do dzierżawy usługi Intune, a następnie utwórz zasady konfiguracji aplikacji, aby umożliwić użytkownikom systemu Android w organizacjach uzyskiwanie dostępu do aplikacji Slack przy użyciu usługi Intune jako dostawcy usługi EMM.

### <a name="add-slack-to-intune"></a>Dodawanie aplikacji Slack do usługi Intune
Dodaj aplikację Slack jako aplikację z zarządzanego sklepu Google Play w usłudze Intune i przypisz do niej użytkowników usługi Slack. Aplikacje są specyficzne dla platformy, dlatego musisz dodać osobną aplikację usługi Intune dla użytkowników usługi Slack na urządzeniach z systemem iOS.
1. W usłudze Intune wybierz kolejno pozycje **Aplikacje** > **Wszystkie aplikacje** > **Dodaj**.
2. W obszarze Typ aplikacji wybierz pozycję **Aplikacja ze sklepu — zarządzany sklep Google Play**.
3. Wybierz pozycję **Zarządzany sklep Google Play — zatwierdzanie**. Wprowadź termin wyszukiwany „Slack for EMM”, a następnie wybierz aplikację.
4. Wybierz pozycję **Zatwierdź**.
5. Na pasku wyszukiwania wprowadź wyraz „Slack”, a następnie wybierz właśnie dodaną aplikację.
6. Z obszaru zarządzania wybierz pozycję **Przypisania**.
7. Wybierz pozycję **Dodaj grupę**. W zależności od tego, na kogo ma wpływać włączenie rozwiązania EMM dla usługi Slack, w obszarze **Typ przypisania** możesz wybrać pozycję:
    - **Dostępne dla zarejestrowanych urządzeń** w przypadku wybrania opcji „Wszyscy członkowie (w tym goście)” LUB
    - **Dostępne z rejestracją lub bez nie** w przypadku wybrania opcji „Wszyscy członkowie (z wyjątkiem gości)" lub „Opcjonalnie”.
8. Wybierz pozycję Objęte grupy i w obszarze Udostępnij tę aplikację wszystkim użytkownikom wybierz pozycję **Tak**.
9. Kliknij przycisk **OK**, a następnie kliknij ponownie przycisk **OK**.
10. Kliknij przycisk **Zapisz**.

### <a name="add-an-app-configuration-policy-for-slack"></a>Dodawanie zasad konfigurowania aplikacji dla aplikacji Slack
Dodaj zasady konfiguracji aplikacji dla aplikacji Slack. Zasady konfiguracji aplikacji dla urządzeń zarządzanych są specyficzne dla platformy, dlatego trzeba dodać osobne zasady dla użytkowników usługi Slack na urządzeniach z systemem iOS.
1. W usłudze Intune wybierz kolejno pozycje **Aplikacje** > **Zasady konfiguracji aplikacji** > **Dodaj**.
2. W polu Nazwa wprowadź frazę Test zasad konfiguracji aplikacji Slack.
3. W obszarze Typ rejestracji urządzenia wybierz pozycję **Urządzenia zarządzane**.
4. W polu Platforma wybierz pozycję **Android**.
5. Wybierz pozycję **Skojarzona aplikacja**.
6. Na pasku wyszukiwania wprowadź wyraz „Slack” i wybierz aplikację.
7. Wybierz przycisk **OK**, a następnie wybierz pozycję **Ustawienia konfiguracji**.
    - Aby uzyskać informacje na temat kluczy konfiguracji i ich wartości, zapoznaj się z dokumentacją na karcie „Technical” (Informacje techniczne) [strony internetowej AppConfig usługi Slack](https://www.appconfig.org/company/slack/).
8. Kliknij przycisk **OK**, a następnie wybierz pozycję **Dodaj**.
9. Na pasku wyszukiwania wprowadź frazę „Test zasad konfiguracji aplikacji Slack”, a następnie wybierz właśnie dodane zasady.
10. Z obszaru zarządzania wybierz pozycję **Przypisania**.
11. W obszarze Przypisz do wybierz pozycję **Wszyscy użytkownicy i wszystkie urządzenia**.
12. Kliknij przycisk **Zapisz**.

### <a name="optional-create-an-android-device-compliance-policy"></a>(Opcjonalnie) Tworzenie zasad zgodności urządzeń z systemem Android
Skonfiguruj zasady zgodności urządzeń z systemem iOS w usłudze Intune w celu ustawienia warunków, które urządzenie musi spełniać, aby zostało uznane za zgodne. W tym samouczku utworzymy zasady zgodności urządzeń z systemem Android. Zasady zgodności są specyficzne dla platformy, dlatego trzeba dodać osobne zasady dla użytkowników usługi Slack na urządzeniach z systemem iOS.
1. W usłudze Intune wybierz pozycję **Zgodność urządzeń** > **Zasady** > **Utwórz zasady**.
2. W obszarze Nazwa wprowadź frazę „Test zasad zgodności dla systemu Android”.
3. W obszarze Opis wprowadź frazę „Test zasad zgodności dla systemu Android”.
4. W obszarze Platforma wybierz pozycję **Android Enterprise**.
5. W obszarze Typ profilu wybierz pozycję **Profil służbowy**.
6. Wybierz pozycję **Kondycja urządzenia**. Obok pozycji Urządzenia z odblokowanym dostępem wybierz pozycję **Blokuj**, a następnie wybierz przycisk **OK**.
7. Wybierz pozycję **Zabezpieczenia systemu** i wprowadź **ustawienia w obszarze Hasło**. Na potrzeby tego samouczka wybierz następujące zalecane ustawienia:
    - W obszarze Wymagaj hasła do odblokowania urządzeń przenośnych wybierz pozycję **Wymagaj**.
    - W obszarze Wymagany typ hasła wybierz pozycję **Co najmniej numeryczne**.
    - W obszarze Minimalna długość hasła wprowadź wartość 4.
    - W obszarze Maksymalna liczba minut po zablokowaniu ekranu, po których jest wymagane wprowadzenie hasła wybierz pozycję **15 minut**.
    - W obszarze Wygaśnięcie hasła (dni) wprowadź wartość 41.
    - W obszarze Liczba poprzednich haseł, których nie można użyć ponownie wprowadź wartość 5.
8. Kliknij przycisk **OK**, a następnie kliknij ponownie przycisk **OK**.
9. Kliknij przycisk **Utwórz**.

## <a name="launch-slack"></a>Uruchamianie aplikacji Slack

Właśnie utworzone zasady sprawiają, że wszystkie urządzenia z profilem służbowym systemu iOS lub Android, które podejmują próbę zalogowania do jednego z Twoich obszarów roboczych, muszą zostać zarejestrowane w usłudze Intune. Aby przetestować ten scenariusz, spróbuj uruchomić aplikację Slack for EMM na zarejestrowanym w usłudze Intune urządzeniu z systemem iOS lub uruchomić aplikację Slack na zarejestrowanym w usłudze Intune urządzeniu z profilem służbowym systemu Android. 

## <a name="next-steps"></a>Następne kroki

W tym samouczku:
- Ustawiono usługę Intune jako dostawcę rozwiązania EMM (Enterprise Mobility Management) w rozwiązaniu Slack Enterprise Grid. 
- Utworzono zasady konfiguracji aplikacji w celu zarządzania aplikacją Slack for EMM w systemie iOS i aplikacją Slack na urządzeniach z profilem służbowym systemu Android.
- Utworzono zasady zgodności urządzeń w usłudze Intune w celu ustawienia warunków, które urządzenia z systemem Android i iOS muszą spełniać, aby zostały uznane za zgodne.

Aby dowiedzieć się więcej na temat zasad konfiguracji aplikacji, zobacz artykuł [Zasady konfiguracji aplikacji usługi Microsoft Intune](app-configuration-policies-overview.md). Aby dowiedzieć się więcej na temat zasad zgodności urządzenia, zobacz artykuł [Ustawianie zasad na urządzeniach w celu umożliwienia dostępu do zasobów w organizacji za pomocą usługi Intune](../protect/device-compliance-get-started.md).
