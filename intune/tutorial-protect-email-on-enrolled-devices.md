---
title: Samouczek — chronienie poczty e-mail usługi Exchange Online na urządzeniach zarządzanych przez usługę Intune
titleSuffix: Microsoft Intune
description: Dowiedz się, jak zabezpieczać usługę Exchange Online przy użyciu zasad zgodności usługi Intune dla systemu iOS oraz dostępu warunkowego usługi Azure AD w celu wymagania zarządzanych urządzeń i aplikacji Outlook.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/26/2019
ms.topic: tutorial
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 91c2ab71cb393bdf885c947c8f3cd93a5bb196c3
ms.sourcegitcommit: bccfbf1e3bdc31382189fc4489d337d1a554e6a1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/03/2019
ms.locfileid: "67548040"
---
# <a name="tutorial-protect-exchange-online-email-on-managed-devices"></a>Samouczek: Chronienie poczty e-mail usługi Exchange Online na urządzeniach zarządzanych
Dowiedz się więcej na temat używania zasad zgodności urządzeń z dostępem warunkowym w celu zagwarantowania, że urządzenia z systemem iOS będą mogły uzyskiwać dostęp do poczty e-mail usługi Exchange Online tylko wtedy, gdy będą zarządzane przez usługę Intune i będą korzystać z zatwierdzonej aplikacji poczty e-mail. 

Z tego samouczka dowiesz się, jak wykonywać następujące czynności: 
> [!div class="checklist"]
> * Tworzenie zasad zgodności urządzeń z systemem iOS w usłudze Intune w celu ustawienia warunków, które urządzenie musi spełniać, aby zostało uznane za zgodne.
> * Tworzenie zasad dostępu warunkowego usługi Azure Active Directory (Azure AD), które wymagają, aby urządzenia z systemem iOS były rejestrowane w usłudze Intune i zgodne z zasadami usługi Intune oraz korzystały z zatwierdzonej aplikacji mobilnej Outlook w celu uzyskiwania dostępu do poczty e-mail usługi Exchange Online.

Jeśli nie masz subskrypcji usługi Intune, [utwórz konto bezpłatnej wersji próbnej](free-trial-sign-up.md).

## <a name="prerequisites"></a>Wymagania wstępne
  - W tym samouczku będziesz potrzebować dzierżawy testowej z następującymi subskrypcjami:
    - Azure Active Directory Premium ([bezpłatna wersja próbna](https://azure.microsoft.com/free/?WT.mc_id=A261C142F))
    - Subskrypcja Office 365 Business obejmująca program Exchange ([bezpłatna wersja próbna](https://go.microsoft.com/fwlink/p/?LinkID=510938))
  - Przed rozpoczęciem pracy utwórz profil testowy urządzenia dla urządzeń z systemem iOS, wykonując kroki opisane w przewodniku [Szybki start: Tworzenie profilu poczty e-mail urządzenia dla systemu iOS](quickstart-email-profile.md).

## <a name="sign-in-to-intune"></a>Logowanie się do usługi Intune

Zaloguj się w usłudze [Intune](https://aka.ms/intuneportal) jako administrator globalny lub administrator usługi Intune. Jeśli utworzono subskrypcję wersji próbnej usługi Intune, konto, którego użyto do utworzenia subskrypcji, jest administratorem globalnym.

## <a name="create-the-ios-device-compliance-policy"></a>Tworzenie zasad zgodności urządzenia z systemem iOS
Skonfiguruj zasady zgodności urządzeń z systemem iOS w usłudze Intune w celu ustawienia warunków, które urządzenie musi spełniać, aby zostało uznane za zgodne. W tym samouczku utworzymy zasady zgodności urządzeń z systemem iOS. Zasady zgodności są specyficzne dla platformy, dlatego potrzebujesz osobnych zasad zgodności dla każdej platformy urządzeń przeznaczonych do oceny.

1. W usłudze Intune wybierz pozycję **Zgodność urządzeń** > **Zasady** > **Utwórz zasady**.
2. W obszarze **Nazwa** wprowadź frazę **Test zasad zgodności dla systemu iOS**. 
3. W obszarze **Opis** wprowadź frazę **Test zasad zgodności dla systemu iOS**.
4. W polu **Platforma** wybierz pozycję **iOS**. 
5. Wybierz kolejno pozycje **Ustawienia** > **Poczta e-mail**. 
     
    1. Obok pozycji **Wymagaj, aby urządzenia przenośne miały zarządzany profil poczty e-mail** wybierz pozycję **Wymagaj**.
    2. Wybierz przycisk **OK**.

    ![Ustawianie zasad zgodności poczty e-mail do wymagania zarządzanego profilu poczty e-mail](media/tutorial-protect-email-on-enrolled-devices/ios-compliance-policy-email.png)
    
6. Wybierz pozycję **Kondycja urządzenia**. Obok pozycji **Urządzenia ze zdjętymi zabezpieczeniami systemu** wybierz pozycję **Zablokuj**, a następnie wybierz przycisk **OK**.
7. Wybierz pozycję **Zabezpieczenia systemu** i wprowadź ustawienia w obszarze **Hasło**. Na potrzeby tego samouczka wybierz następujące zalecane ustawienia:
     
    - W obszarze **Wymagaj hasła do odblokowania urządzeń przenośnych** wybierz pozycję **Wymagaj**.
    - W obszarze **Proste hasła** wybierz pozycję **Zablokuj**.
    - W obszarze **Minimalna długość hasła** wprowadź wartość **4**.
    - W obszarze **Wymagany typ hasła** wybierz **Alfanumeryczne**.
    - W obszarze **Maksymalna liczba minut po zablokowaniu ekranu, zanim będzie wymagane hasło** wybierz pozycję **Natychmiast**.
    - W obszarze **Wygaśnięcie hasła (dni)** wprowadź wartość **41**.
    - W obszarze **Liczba poprzednich haseł, których nie można użyć ponownie** wprowadź wartość **5**.
 
    ![Konfigurowanie ustawień hasła dla zasad zgodności poczty e-mail](media/tutorial-protect-email-on-enrolled-devices/ios-compliance-policy-system-security.png)

8. Wybierz przycisk **OK**, a następnie ponownie wybierz przycisk **OK**.
9. Wybierz przycisk **Utwórz**.

## <a name="create-the-conditional-access-policy"></a>Tworzenie zasad dostępu warunkowego
Teraz utworzymy zasady dostępu warunkowego, które wymagają zarejestrowania wszystkich platform urządzeń w Intune oraz ich zgodności z naszymi zasadami zgodności usługi Intune przed uzyskaniem dostępu do usługi Exchange Online. Będziemy również wymagać aplikacji Outlook na potrzeby dostępu do poczty e-mail. Zasady dostępu warunkowego można konfigurować w portalu usługi Azure AD lub w portalu usługi Intune. Ponieważ pracujemy już w portalu usługi Intune zasady także utworzymy w tym miejscu.
1. W usłudze Intune wybierz kolejno pozycje **Dostęp warunkowy** > **Zasady** > **Nowe zasady**.
1. W polu **Nazwa** wprowadź frazę **Testowe zasady do obsługi poczty e-mail usługi Office 365**. 
3. W obszarze **Przypisania** wybierz pozycję **Użytkownicy i grupy**. Na karcie **Dołączanie** wybierz pozycję **Wszyscy użytkownicy**, a następnie wybierz pozycję **Gotowe**.

4. W obszarze **Przypisania** wybierz pozycję **Aplikacje w chmurze**. Ponieważ chcemy chronić pocztę e-mail usługi Office 365 Exchange Online, wybierzemy ją, wykonując następujące kroki:
     
    1. Na karcie **Dołączanie** wybierz pozycję **Wybierz aplikacje**.
    2. Wybierz pozycję **Wybierz**. 
    3. Na liście aplikacji wybierz pozycję **Office 365 Exchange Online**, a następnie wybierz pozycję **Wybierz**. 
    4. Wybierz pozycję **Gotowe**.
  
    ![Wybieranie aplikacji Office 365 Exchange Online](media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-cloud-apps.png)

5. W obszarze **Przypisania** wybierz kolejno pozycje **Warunki** > **Platformy urządzeń**.
     
    1. W obszarze **Konfiguruj** wybierz pozycję **Tak**.
    2. Na karcie **Dołączanie** wybierz pozycję **Dowolne urządzenie**, a następnie wybierz pozycję **Gotowe**. 
    3. Ponownie wybierz pozycję **Gotowe**.
   
    ![Wybieranie aplikacji Office 365 Exchange Online](media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-cloud-device-platforms.png)

6. W obszarze **Przypisania** wybierz pozycję **Warunki** > **Aplikacje klienckie**.
     
    1. W obszarze **Konfiguruj** wybierz pozycję **Tak**.
    2. Na potrzeby tego samouczka wybierz pozycje **Aplikacje mobilne i klienci stacjonarni** i **Klienci nowoczesnego uwierzytelniania** (które odnoszą się do aplikacji, takich jak program Outlook dla systemu iOS i Outlook dla systemu Android). Usuń zaznaczenia wszystkich pozostałych pól wyboru.
    3. Wybierz pozycję **Gotowe**, a następnie ponownie wybierz pozycję **Gotowe**.
    
    ![Wybieranie aplikacji Office 365 Exchange Online](media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-client-apps.png)

7. W obszarze **Kontrole dostępu** wybierz pozycję **Udziel**. 
     
    1. W okienku **Udzielanie** wybierz pozycję **Udziel dostępu**.
    2. Wybierz pozycję **Wymagaj, aby urządzenie było oznaczone jako zgodne**. 
    3. Wybierz pozycję **Wymagaj zatwierdzonej aplikacji klienckiej**.
    4. W obszarze **W przypadku wielu kontrolek** wybierz pozycję **Wymagaj wszystkich wybranych kontrolek**. To ustawienie zapewnia, że obydwa wybrane wymagania są wymuszane, gdy urządzenie próbuje uzyskać dostęp do poczty e-mail.
    5. Wybierz pozycję **Wybierz**.
     
    ![Wybieranie aplikacji Office 365 Exchange Online](media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-grant-access.png)

8. W obszarze **Włącz zasady** wybierz pozycję **na**.
     
    ![Wybieranie aplikacji Office 365 Exchange Online](media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-enable-policy.png)

9. Wybierz przycisk **Utwórz**.

## <a name="try-it-out"></a>Wypróbowywanie działania
Dzięki utworzonym zasadom dowolne urządzenie z systemem iOS, które próbuje zalogować się do poczty e-mail usługi Office 365, musi zostać zarejestrowanie w usłudze Intune i musi używać aplikacji mobilnej Outlook dla systemu iOS. Aby przetestować ten scenariusz w urządzeniu z systemem iOS, zaloguj się do usługi Exchange Online przy użyciu poświadczeń dla użytkownika w dzierżawie testowej. Zostanie wyświetlony monit o zarejestrowanie urządzenia i zainstalowanie aplikacji mobilnej Outlook.
1. Aby przetestować na telefonie iPhone, przejdź do pozycji **Ustawienia** > **Hasła i konta** > **Dodaj konto** > **Exchange**.
2. Wprowadź adres e-mail użytkownika w dzierżawie testowej, a następnie wybierz pozycję **Dalej**.
3. Wybierz pozycję **Zaloguj się**.
4. Wprowadź hasło użytkownika testowego i wybierz pozycję **Zaloguj się**.
5. Zostanie wyświetlony komunikat informujący o tym, że urządzenie musi być zarządzane, aby uzyskiwać dostęp do zasobu, wraz z opcją rejestrowania. 

## <a name="clean-up-resources"></a>Oczyszczanie zasobów
Gdy zasady testowe nie są już potrzebne, można je usunąć.
1. Zaloguj się w usłudze [Intune](https://aka.ms/intuneportal) jako administrator globalny lub administrator usługi Intune.
2. Wybierz kolejno pozycje **Zgodność urządzenia** > **Zasady**.
3. Z listy **Nazwa zasad** wybierz menu kontekstowe ( **...** ) dla zasad testowych, a następnie wybierz pozycję **Usuń**. Wybierz przycisk **OK**, aby potwierdzić.
4. Wybierz kolejno pozycje **Dostęp warunkowy** > **Zasady**.
5. Z listy **Nazwa zasad** wybierz menu kontekstowe ( **...** ) dla zasad testowych, a następnie wybierz pozycję **Usuń**. Kliknij przycisk **Tak**, aby potwierdzić.

## <a name="next-steps"></a>Następne kroki 
W tym samouczku utworzono zasady wymagające zarejestrowania urządzeń z systemem iOS w usłudze Intune oraz użycia aplikacji Outlook w celu uzyskania dostępu do poczty e-mail usługi Exchange Online. Aby dowiedzieć się więcej na temat ochrony innych aplikacji i usług, takich jak klienci programu Exchange ActiveSync dla usługi Office 365 Exchange Online, za pomocą usługi Intune z dostępem warunkowym, zobacz artykuł [Konfigurowanie dostępu warunkowego](conditional-access.md).
