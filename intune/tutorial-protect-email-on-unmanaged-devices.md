---
title: Samouczek — chronienie poczty e-mail usługi Exchange Online na urządzeniach niezarządzanych
titlesuffix: Microsoft Intune
description: Dowiedz się, jak zabezpieczyć usługę Office 365 Exchange Online za pomocą zasad ochrony aplikacji usługi Intune i dostępu warunkowego usługi Azure AD.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/11/2018
ms.topic: tutorial
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4692e19d657e19efe18a91273ce585eb59c6cb65
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57528279"
---
# <a name="tutorial-protect-exchange-online-email-on-unmanaged-devices"></a>Samouczek: chronienie poczty e-mail usługi Exchange Online na urządzeniach niezarządzanych

Dowiedz się więcej na temat używania zasad ochrony aplikacji z dostępem warunkowym w celu chronienia usługi Exchange Online, nawet gdy urządzenia nie zostały zarejestrowane w rozwiązaniu do zarządzania urządzeniami, takim jak usługa Intune. Z tego samouczka dowiesz się, jak wykonywać następujące czynności: 

> [!div class="checklist"]
> * Tworzenie zasad ochrony aplikacji usługi Intune na potrzeby aplikacji Outlook. Ograniczysz czynności, które użytkownik może wykonywać w stosunku do danych aplikacji, uniemożliwiając korzystanie z polecenia „Zapisz jako”, a także ograniczysz akcje wycinania, kopiowania i wklejania. 
> * Tworzenie zasad dostępu warunkowego usługi Azure Active Directory (Azure AD) zezwalających tylko aplikacji Outlook na uzyskiwanie dostępu do firmowej poczty e-mail w usłudze Exchange Online. Będziesz również wymagać uwierzytelniania wieloskładnikowego (MFA) w przypadku klientów z nowoczesnym uwierzytelnianiem, takich jak program Outlook dla systemów iOS i Android.

## <a name="prerequisites"></a>Wymagania wstępne
  - W tym samouczku będziesz potrzebować dzierżawy testowej z następującymi subskrypcjami:
    - Azure Active Directory Premium ([bezpłatna wersja próbna](https://azure.microsoft.com/free/?WT.mc_id=A261C142F))
    - Subskrypcja usługi Intune ([bezpłatna wersja próbna](free-trial-sign-up.md))
    - Subskrypcja Office 365 Business obejmująca program Exchange ([bezpłatna wersja próbna](https://go.microsoft.com/fwlink/p/?LinkID=510938))

## <a name="sign-in-to-intune"></a>Logowanie się do usługi Intune

Zaloguj się w usłudze [Intune](https://aka.ms/intuneportal) jako administrator globalny lub administrator usługi Intune. Dostęp do usługi Intune można uzyskać w witrynie Azure Portal, wybierając pozycję **Wszystkie usługi** > **Intune**.

## <a name="create-the-app-protection-policy"></a>Tworzenie zasad ochrony aplikacji
W tym samouczku skonfigurujemy zasady ochrony aplikacji usługi Intune dla aplikacji Outlook w celu zastosowania zabezpieczeń na poziomie aplikacji. Do otwarcia aplikacji w kontekście służbowym będziemy wymagać kodu PIN. Ograniczymy również udostępnianie danych między aplikacjami i uniemożliwimy zapisywanie danych firmowych w lokalizacji prywatnej.

1.  W usłudze Intune wybierz kolejno pozycje **Aplikacje klienckie** > **Zasady ochrony aplikacji** > **Dodaj zasady**.
2.  W polu **Nazwa** wprowadź wartość **Test zasad aplikacji Outlook**.
3.  W polu **Opis** wprowadź wartość **Test zasad aplikacji Outlook**.
4.  Wybierz pozycję **Aplikacje**. Na liście aplikacji wybierz pozycję **Outlook**, a następnie wybierz pozycję **Wybierz**.
5.  Wybierz pozycję **Ustawienia**. 
6.  W obszarze **Relokacja danych** wybierz następujące ustawienia na potrzeby tego samouczka:

    - W obszarze **Zezwalaj aplikacji na transfer danych do innych aplikacji** wybierz pozycję **Brak**.
    - W obszarze **Zezwalaj aplikacji na odbieranie danych z innych aplikacji** wybierz pozycję **Brak**.
    - W obszarze **Nie zezwalaj na używanie polecenia „Zapisz jako”** wybierz pozycję **Tak**.
    - W obszarze **Ogranicz wycinanie, kopiowanie i wklejanie w innych aplikacjach** wybierz pozycję **Zablokowane**.
   
     ![Wybieranie ustawień relokacji danych zasad ochrony aplikacji Outlook](media/tutorial-protect-email-on-unmanaged-devices/outlook-app-data-relocation.png)
    
7.  W obszarze **Akcje dostępu** wybierz następujące ustawienia na potrzeby tego samouczka:

    - W obszarze **Wymagaj numeru PIN w celu udzielenia dostępu** wybierz pozycję **Tak**.
    - W obszarze **Wymagaj poświadczeń firmowych w celu udzielenia dostępu** wybierz pozycję **Tak**.
    - W przypadku innych ustawień pozostaw ich wartości domyślne.
 
     ![Wybieranie akcji dostępu zasad ochrony aplikacji Outlook](media/tutorial-protect-email-on-unmanaged-devices/outlook-app-access-actions.png)

9.  Wybierz przycisk **OK**.
10. Wybierz przycisk **Utwórz**.

Zostały utworzone zasady ochrony aplikacji dla programu Outlook. Teraz możesz skonfigurować dostęp warunkowy, aby urządzenia musiały korzystać z aplikacji Outlook.

## <a name="create-conditional-access-policies"></a>Tworzenie zasad dostępu warunkowego
Teraz utworzymy dwie zasady dostępu warunkowego, aby uwzględnić wszystkie platformy urządzeń. Pierwsze zasady będą wymagać od klientów z nowoczesnym uwierzytelnianiem, takich jak program Outlook dla systemu iOS i program Outlook dla systemu Android, korzystania z zatwierdzonej aplikacji Outlook i usługi MFA. Drugie zasady będą wymagać od klientów programu Exchange ActiveSync używania zatwierdzonej aplikacji Outlook. (Obecnie program Exchange Active Sync nie obsługuje warunków innych niż platforma urządzenia). Zasady dostępu warunkowego można konfigurować w portalu usługi Azure AD lub w portalu usługi Intune. Ponieważ pracujemy już w portalu usługi Intune zasady także utworzymy w tym miejscu.
### <a name="create-an-mfa-policy-for-modern-authentication-clients"></a>Tworzenie zasad usługi MFA dla klientów z nowoczesnym uwierzytelnianiem
1.  W usłudze Intune wybierz kolejno pozycje **Dostęp warunkowy** > **Zasady** > **Nowe zasady**.
1.  W polu **Nazwa** wprowadź frazę **Testowe zasady dla klientów z nowoczesnym uwierzytelnianiem**. 
3.  W obszarze **Przypisania** wybierz pozycję **Użytkownicy i grupy**. Na karcie **Dołączanie** wybierz pozycję **Wszyscy użytkownicy**, a następnie wybierz pozycję **Gotowe**.

4.  W obszarze **Przypisania** wybierz pozycję **Aplikacje w chmurze**. Ponieważ chcemy chronić pocztę e-mail usługi Office 365 Exchange Online, wybierzemy ją, wykonując następujące kroki:
     
    1. Na karcie **Dołączanie** wybierz pozycję **Wybierz aplikacje**.
    2. Wybierz pozycję **Wybierz**. 
    3. Na liście aplikacji wybierz pozycję **Office 365 Exchange Online**, a następnie wybierz pozycję **Wybierz**. 
    4. Wybierz pozycję **Gotowe**.
  
    ![Wybieranie aplikacji Office 365 Exchange Online](media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-cloud-apps.png)

5.  W obszarze **Przypisania** wybierz kolejno pozycje **Warunki** > **Platformy urządzeń**.
     
    1. W obszarze **Konfiguruj** wybierz pozycję **Tak**.
    2. Na karcie **Dołączanie** wybierz pozycję **Wszystkie platformy (w tym nieobsługiwane)**. 
    3. Wybierz pozycję **Gotowe**.
   
6.  W okienku **Warunki** wybierz pozycję **Aplikacje klienckie**.
     
    1. W obszarze **Konfiguruj** wybierz pozycję **Tak**.
    2. Wybierz pozycje **Aplikacje mobilne i klienci stacjonarni** oraz **Nowocześni klienci uwierzytelniania**.
    3. Usuń zaznaczenia pozostałych pól wyboru.
    4. Wybierz pozycję **Gotowe**, a następnie ponownie wybierz pozycję **Gotowe**.
    
    ![Wybieranie aplikacji Office 365 Exchange Online](media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-client-apps.png)

7.  W obszarze **Kontrole dostępu** wybierz pozycję **Udziel**. 
     
    1. W okienku **Udzielanie** wybierz pozycję **Udziel dostępu**.
    2. Wybierz pozycję **Wymagaj uwierzytelniania wieloskładnikowego**.
    4. Wybierz pozycję **Wymagaj zatwierdzonej aplikacji klienckiej**.
    5. W obszarze **W przypadku wielu kontrolek** wybierz pozycję **Wymagaj wszystkich wybranych kontrolek**. To ustawienie zapewnia, że obydwa wybrane wymagania są wymuszane, gdy urządzenie próbuje uzyskać dostęp do poczty e-mail.
    6. Wybierz pozycję **Wybierz**.
     
    ![Wybieranie aplikacji Office 365 Exchange Online](media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-mfa.png)

8.  W obszarze **Włącz zasady** wybierz pozycję **na**.
     
    ![Wybieranie aplikacji Office 365 Exchange Online](media/tutorial-protect-email-on-unmanaged-devices/enable-policy.png)

9.  Wybierz przycisk **Utwórz**.

Zostały utworzone zasady dostępu warunkowego dla klientów z nowoczesnym uwierzytelnianiem. Teraz możesz utworzyć zasady dla klientów programu Exchange Active Sync.

### <a name="create-a-policy-for-exchange-active-sync-clients"></a>Tworzenie zasad dla klientów programu Exchange Active Sync
1.  W usłudze Intune wybierz kolejno pozycje **Dostęp warunkowy** > **Zasady** > **Nowe zasady**.
2.  W polu **Nazwa** wprowadź frazę **Testowe zasady do obsługi klientów programu EAS**. 
3.  W obszarze **Przypisania** wybierz pozycję **Użytkownicy i grupy**. Na karcie **Dołączanie** wybierz pozycję **Wszyscy użytkownicy**, a następnie wybierz pozycję **Gotowe**.

4.  W obszarze **Przypisania** wybierz pozycję **Aplikacje w chmurze**. Wybierz pocztę e-mail usługi Office 365 Exchange Online, wykonując następujące kroki:
     
    1. Na karcie **Dołączanie** wybierz pozycję **Wybierz aplikacje**.
    2. Wybierz pozycję **Wybierz**. 
    3. Na liście aplikacji wybierz pozycję **Office 365 Exchange Online**, a następnie wybierz pozycję **Wybierz**. 
    4. Wybierz pozycję **Gotowe**.

5.  W obszarze **Przypisania** wybierz kolejno pozycje **Warunki** > **Platformy urządzeń**.
     
    1. W obszarze **Konfiguruj** wybierz pozycję **Tak**.
    2. Na karcie **Dołączanie** wybierz pozycję **wszystkich platform (w tym nieobsługiwane)**, a następnie wybierz pozycję **Gotowe**. 
    3. Ponownie wybierz pozycję **Gotowe**.

6.  W okienku **Warunki** wybierz pozycję **Aplikacje klienckie**.
     
    1. W obszarze **Konfiguruj** wybierz pozycję **Tak**.
    2. Wybierz pozycję **Aplikacje mobilne i klienci stacjonarni**.
    3. Wybierz pozycje **Klienci programu Exchange ActiveSync** i **Zastosuj zasady tylko do obsługiwanych platform**. 
    4. Usuń zaznaczenia wszystkich pozostałych pól wyboru.
    5. Wybierz pozycję **Gotowe**, a następnie ponownie wybierz pozycję **Gotowe**.
    
    ![Wybieranie aplikacji Office 365 Exchange Online](media/tutorial-protect-email-on-unmanaged-devices/eas-client-apps.png)

7.  W obszarze **Kontrole dostępu** wybierz pozycję **Udziel**. 
     
    1. W okienku **Udzielanie** wybierz pozycję **Udziel dostępu**.
    4. Wybierz pozycję **Wymagaj zatwierdzonej aplikacji klienckiej**. Usuń zaznaczenia wszystkich pozostałych pól wyboru.
    6. Wybierz pozycję **Wybierz**.
     
    ![Wybieranie aplikacji Office 365 Exchange Online](media/tutorial-protect-email-on-unmanaged-devices/eas-grant-access.png)

8.  W obszarze **Włącz zasady** wybierz pozycję **na**.

9.  Wybierz przycisk **Utwórz**.

Zasady ochrony aplikacji i dostępu warunkowego zostały teraz utworzone i są gotowe do testowania. 

## <a name="try-it-out"></a>Wypróbowywanie działania
Dzięki utworzonym zasadom urządzenia będą musiały zostać zarejestrowane w usłudze Intune i będą musiały używać aplikacji mobilnej Outlook w celu uzyskiwania dostępu do poczty e-mail usługi Office 365. Aby przetestować ten scenariusz w urządzeniu z systemem iOS, zaloguj się do usługi Exchange Online przy użyciu poświadczeń dla użytkownika w dzierżawie testowej.
1. Aby przetestować na telefonie iPhone, przejdź do pozycji **Ustawienia** > **Hasła i konta** > **Dodaj konto** > **Exchange**.
2. Wprowadź adres e-mail użytkownika w dzierżawie testowej, a następnie wybierz pozycję **Dalej**.
3. Wybierz pozycję **Zaloguj się**.
4. Wprowadź hasło użytkownika testowego i wybierz pozycję **Zaloguj się**.
5. Zostanie wyświetlony komunikat **Wymagane dalsze informacje** oznaczający, że należy skonfigurować usługę MFA. Skonfiguruj dodatkową metodę weryfikacji.
6. Następnie zobaczysz komunikat informujący, że próbujesz otworzyć ten zasób przy użyciu aplikacji, która nie została zatwierdzona przez dział IT. Oznacza to, że możliwość korzystania z natywnej aplikacji poczty jest blokowana. Anuluj logowanie.
7.  Otwórz aplikację Outlook i wybierz pozycję **Ustawienia** > **Dodaj konto** > **Dodaj konto e-mail**.
8. Wprowadź adres e-mail użytkownika w dzierżawie testowej, a następnie wybierz pozycję **Dalej**.
9. Naciśnij pozycję **Zaloguj się przy użyciu usługi Office 365**. Zostanie wyświetlony monit o dodatkowe uwierzytelnienie i rejestrację. Po zalogowaniu można przetestować akcje, takie jak wycinanie, kopiowanie, wklejanie i używanie polecenia „Zapisz jako”.

## <a name="clean-up-resources"></a>Oczyszczanie zasobów
Gdy zasady testowe nie są już potrzebne, można je usunąć.
1. Zaloguj się w usłudze [Intune](https://aka.ms/intuneportal) jako administrator globalny lub administrator usługi Intune.
2. Wybierz kolejno pozycje **Zgodność urządzenia** > **Zasady**.
3. Z listy **Nazwa zasad** wybierz menu kontekstowe (**...**) dla zasad testowych, a następnie wybierz pozycję **Usuń**. Wybierz przycisk **OK**, aby potwierdzić.
4. Wybierz kolejno pozycje **Dostęp warunkowy** > **Zasady**.
5. Z listy **Nazwa zasad** wybierz menu kontekstowe (**...**) dla każdej z zasad testowych, a następnie wybierz pozycję **Usuń**. Kliknij przycisk **Tak**, aby potwierdzić.

 ## <a name="next-steps"></a>Następne kroki 
W tym samouczku utworzono zasady ochrony aplikacji, aby ograniczyć czynności, które użytkownik może wykonać w aplikacji Outlook. Utworzono również zasady dostępu warunkowego, aby wymagać użycia aplikacji Outlook i usługi MFA w przypadku nowoczesnych klientów uwierzytelniania. Aby dowiedzieć się więcej na temat ochrony innych aplikacji i usług za pomocą usługi Intune z dostępem warunkowym, zobacz [Konfigurowanie dostępu warunkowego](conditional-access.md).
