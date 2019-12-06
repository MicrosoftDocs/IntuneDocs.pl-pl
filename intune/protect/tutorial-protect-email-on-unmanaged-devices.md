---
title: Samouczek — chronienie poczty e-mail usługi Exchange Online na urządzeniach niezarządzanych
titleSuffix: Microsoft Intune
description: Dowiedz się, jak zabezpieczyć usługę Office 365 Exchange Online za pomocą zasad ochrony aplikacji usługi Intune i dostępu warunkowego usługi Azure AD.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/21/2019
ms.topic: tutorial
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 810a898a3b2d1981babc231f32ed386bde37a856
ms.sourcegitcommit: ce518a5dfe62c546a77f32ef372f36efbaad473f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2019
ms.locfileid: "74465790"
---
# <a name="tutorial-protect-exchange-online-email-on-unmanaged-devices"></a>Samouczek: chronienie poczty e-mail usługi Exchange Online na urządzeniach niezarządzanych

Dowiedz się więcej na temat używania zasad ochrony aplikacji z dostępem warunkowym w celu chronienia usługi Exchange Online, nawet gdy urządzenia nie zostały zarejestrowane w rozwiązaniu do zarządzania urządzeniami, takim jak usługa Intune. Z tego samouczka dowiesz się, jak wykonywać następujące czynności:

> [!div class="checklist"]
> * Tworzenie zasad ochrony aplikacji usługi Intune na potrzeby aplikacji Outlook. Ograniczysz czynności, które użytkownik może wykonywać w stosunku do danych aplikacji, uniemożliwiając korzystanie z polecenia „Zapisz jako”, a także ograniczysz akcje wycinania, kopiowania i wklejania.
> * Tworzenie zasad dostępu warunkowego usługi Azure Active Directory (Azure AD) zezwalających tylko aplikacji Outlook na uzyskiwanie dostępu do firmowej poczty e-mail w usłudze Exchange Online. Będziesz również wymagać uwierzytelniania wieloskładnikowego (MFA) w przypadku klientów z nowoczesnym uwierzytelnianiem, takich jak program Outlook dla systemów iOS i Android.

## <a name="prerequisites"></a>Wymagania wstępne

W tym samouczku będziesz potrzebować dzierżawy testowej z następującymi subskrypcjami:

- Azure Active Directory Premium ([bezpłatna wersja próbna](https://azure.microsoft.com/free/?WT.mc_id=A261C142F))
- Subskrypcja usługi Intune ([bezpłatna wersja próbna](../fundamentals/free-trial-sign-up.md))
- Subskrypcja Office 365 Business obejmująca program Exchange ([bezpłatna wersja próbna](https://go.microsoft.com/fwlink/p/?LinkID=510938))

## <a name="sign-in-to-intune"></a>Logowanie się do usługi Intune

Na potrzeby tego samouczka, logując się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), zaloguj się jako [administrator globalny](../fundamentals/users-add.md#types-of-administrators) lub [administrator usługi Intune](../fundamentals/users-add.md#types-of-administrators). Jeśli utworzono subskrypcję wersji próbnej usługi Intune, konto, którego użyto do utworzenia subskrypcji, jest administratorem globalnym.

## <a name="create-the-app-protection-policy"></a>Tworzenie zasad ochrony aplikacji

W tym samouczku skonfigurujemy zasady ochrony aplikacji usługi Intune dla systemu iOS dla aplikacji Outlook w celu zastosowania zabezpieczeń na poziomie aplikacji. Do otwarcia aplikacji w kontekście służbowym będziemy wymagać kodu PIN. Ograniczymy również udostępnianie danych między aplikacjami i uniemożliwimy zapisywanie danych firmowych w lokalizacji prywatnej.

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Wybierz pozycję **Aplikacje** > **Zasady ochrony aplikacji** > **Utwórz zasady** i jako platformę wybierz opcję **iOS/iPadOS**.

3. Na stronie **Podstawy** skonfiguruj następujące ustawienia:

   - **Nazwa**: wprowadź wartość **Test zasad aplikacji Outlook**.
   - **Opis**: wprowadź wartość **Test zasad aplikacji Outlook**.

   Wartość **Platforma** jest ustawiona zgodnie z poprzednim wyborem.

   Kliknij przycisk **Dalej** , aby kontynuować.

4. Strona **Aplikacje** umożliwia wybranie sposobu zastosowania zasad do aplikacji na różnych urządzeniach. Skonfiguruj następujące opcje:

   - W obszarze **Dotyczy wszystkich typów aplikacji**: wybierz pozycję **Nie**, a następnie w obszarze **Typy aplikacji** zaznacz pole wyboru **Aplikacje na urządzeniach niezarządzanych**.
   - Kliknij pozycję **Wybierz aplikacje publiczne**. Na liście aplikacji wybierz pozycję **Outlook**, a następnie wybierz pozycję **Wybierz**.  Program Outlook jest teraz wyświetlany w obszarze *Aplikacje publiczne*.

   Kliknij przycisk **Dalej** , aby kontynuować.

5. Ustawienia na stronie **Ochrona danych** określają, jak użytkownicy używają danych w aplikacjach, do których mają zastosowanie zasady ochrony. Skonfiguruj następujące opcje:

   Poniżej pozycji *Transfer danych* skonfiguruj następujące ustawienia, pozostawiając wartości domyślne dla wszystkich pozostałych ustawień:

   - W obszarze **Wyślij dane organizacji do innych aplikacji** wybierz pozycję **Brak**.  
   - W obszarze **Odbierz dane z innych aplikacji** wybierz pozycję **Brak**.  
   - W obszarze **Zapisz kopie danych organizacji** wybierz opcję **Blokuj**.  
   - W obszarze **Ogranicz wycinanie, kopiowanie i wklejanie między innymi aplikacjami** wybierz pozycję **Zablokowane**. 

   ![Wybieranie ustawień relokacji danych zasad ochrony aplikacji Outlook](./media/tutorial-protect-email-on-unmanaged-devices/data-protection-settings.png)

   Wybierz przycisk **Dalej**, aby kontynuować.

6. Strona **Wymagania dotyczące dostępu** zawiera ustawienia pozwalające skonfigurować wymagania dotyczące numeru PIN i poświadczeń, które użytkownicy muszą spełnić, aby uzyskać dostęp do aplikacji w kontekście służbowym. Skonfiguruj następujące ustawienia, pozostawiając dla wszystkich pozostałych ustawień wartości domyślne:

   - W obszarze **Kod PIN na potrzeby dostępu** wybierz pozycję **Wymagaj**.
   - W obszarze **Poświadczenia konta służbowego na potrzeby dostępu** wybierz pozycję **Wymagaj**.

   ![Wybieranie akcji dostępu zasad ochrony aplikacji Outlook](./media/tutorial-protect-email-on-unmanaged-devices/access-requirements-settings.png)

   Wybierz przycisk **Dalej**, aby kontynuować.

7. Strona **Uruchamianie warunkowe** zawiera ustawienia umożliwiające skonfigurowanie wymagań dotyczących zabezpieczeń logowania na potrzeby zasad ochrony aplikacji. W tym samouczku nie trzeba konfigurować tych ustawień.

   Kliknij przycisk **Dalej** , aby kontynuować.

8. Użyj strony **Przypisania**, aby przypisać zasady ochrony aplikacji do grup użytkowników. W tym samouczku nie będziemy przypisywać tych zasad do grupy.  
 Nie musisz konfigurować tych ustawień.

   Kliknij przycisk **Dalej** , aby kontynuować.

9. Na stronie **Dalej: Przeglądanie + tworzenie**, przejrzyj wartości i ustawienia wprowadzone dla tych zasad ochrony aplikacji. Kliknij pozycję **Utwórz**, aby utworzyć zasady ochrony aplikacji w usłudze Intune.

Zostały utworzone zasady ochrony aplikacji dla programu Outlook. Następnie skonfigurujesz dostęp warunkowy, aby urządzenia musiały korzystać z aplikacji Outlook.

## <a name="create-conditional-access-policies"></a>Tworzenie zasad dostępu warunkowego

Teraz utworzymy dwie zasady dostępu warunkowego, aby uwzględnić wszystkie platformy urządzeń.  

- Pierwsze zasady będą wymagać, aby klienci z nowoczesnym uwierzytelnianiem korzystali z zatwierdzonej aplikacji Outlook i uwierzytelniania wieloskładnikowego (usługi MFA). Klienci z nowoczesnym uwierzytelnianiem to m.in. programy Outlook dla systemu iOS i Outlook dla systemu Android.  

- Drugie zasady będą wymagać od klientów programu Exchange ActiveSync używania zatwierdzonej aplikacji Outlook. (Obecnie program Exchange Active Sync nie obsługuje warunków innych niż platforma urządzenia). Zasady dostępu warunkowego można konfigurować w portalu usługi Azure AD lub w portalu usługi Intune. Ponieważ pracujemy już w portalu usługi Intune zasady także utworzymy w tym miejscu.  

### <a name="create-an-mfa-policy-for-modern-authentication-clients"></a>Tworzenie zasad usługi MFA dla klientów z nowoczesnym uwierzytelnianiem  

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Wybierz pozycję **Zabezpieczenia punktu końcowego** >  **Dostęp warunkowy** > **Nowe zasady**.  

3. W polu **Nazwa** wprowadź frazę **Testowe zasady dla klientów z nowoczesnym uwierzytelnianiem**.  

4. W obszarze **Przypisania** wybierz pozycję **Użytkownicy i grupy**. Na karcie **Dołączanie** wybierz pozycję **Wszyscy użytkownicy**, a następnie wybierz pozycję **Gotowe**.

5. W obszarze **Przypisania** wybierz pozycję **Aplikacje w chmurze lub akcje**. Ponieważ chcemy chronić pocztę e-mail usługi Office 365 Exchange Online, wybierzemy ją, wykonując następujące kroki:

   1. Na karcie **Dołączanie** wybierz pozycję **Wybierz aplikacje**.
   2. Wybierz pozycję **Wybierz**.
   3. Na liście aplikacji wybierz pozycję **Office 365 Exchange Online**, a następnie wybierz pozycję **Wybierz**.
   4. Wybierz pozycję **Gotowe**, aby wrócić do okienka nowych zasad.

   ![Wybieranie aplikacji Office 365 Exchange Online](./media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-cloud-apps.png)

6. W obszarze **Przypisania** wybierz kolejno pozycje **Warunki** > **Platformy urządzeń**.

   1. W obszarze **Konfiguruj** wybierz pozycję **Tak**.
   2. Na karcie **Dołączanie** wybierz pozycję **Dowolne urządzenie**.
   3. Wybierz pozycję **Gotowe**.

7. W okienku **Warunki** wybierz pozycję **Aplikacje klienckie**.

   1. W obszarze **Konfiguruj** wybierz pozycję **Tak**.
   2. Wybierz pozycje **Aplikacje mobilne i klienci stacjonarni** oraz **Nowocześni klienci uwierzytelniania**.
   3. Usuń zaznaczenia pozostałych pól wyboru.
   4. Wybierz pozycję **Gotowe** > **Gotowe**, aby wrócić do okienka nowych zasad.

   ![Wybieranie pozycji Aplikacje mobilne i klienci](./media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-client-apps.png)

8. W obszarze **Kontrole dostępu** wybierz pozycję **Udziel**.

   1. W okienku **Udzielanie** wybierz pozycję **Udziel dostępu**.
   2. Wybierz pozycję **Wymagaj uwierzytelniania wieloskładnikowego**.
   3. Wybierz pozycję **Wymagaj zatwierdzonej aplikacji klienckiej**.
   4. W obszarze **W przypadku wielu kontrolek** wybierz pozycję **Wymagaj wszystkich wybranych kontrolek**. To ustawienie zapewnia, że obydwa wybrane wymagania są wymuszane, gdy urządzenie próbuje uzyskać dostęp do poczty e-mail.
   5. Wybierz pozycję **Wybierz**.

   ![Wybieranie kontroli dostępu](./media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-mfa.png)

9. W obszarze **Włącz zasady** wybierz pozycję **Wł.** , a następnie wybierz pozycję **Utwórz**.

   ![Tworzenie zasad](./media/tutorial-protect-email-on-unmanaged-devices/enable-policy.png)  

Zostały utworzone zasady dostępu warunkowego dla klientów z nowoczesnym uwierzytelnianiem. Teraz możesz utworzyć zasady dla klientów programu Exchange Active Sync.

### <a name="create-a-policy-for-exchange-active-sync-clients"></a>Tworzenie zasad dla klientów programu Exchange Active Sync

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Wybierz pozycję **Zabezpieczenia punktu końcowego** > **Dostęp warunkowy** > **Nowe zasady**.

3. W polu **Nazwa** wprowadź frazę **Testowe zasady do obsługi klientów programu EAS**.

4. W obszarze **Przypisania** wybierz pozycję **Użytkownicy i grupy**. Na karcie *Dołączanie* wybierz pozycję **Wszyscy użytkownicy**, a następnie wybierz pozycję **Gotowe**.

5. W obszarze **Przypisania** wybierz pozycję **Aplikacje w chmurze lub akcje**. Wybierz pocztę e-mail usługi Office 365 Exchange Online, wykonując następujące kroki:

   1. Na karcie *Dołączanie* wybierz pozycję **Wybierz aplikacje**.
   2. Wybierz pozycję **Wybierz**.
   3. Na liście *Aplikacje* wybierz kolejno pozycje **Office 365 Exchange Online**, **Wybierz** i **Gotowe**.
  
6. W obszarze **Przypisania** wybierz kolejno pozycje **Warunki** > **Platformy urządzeń**.

   1. W obszarze **Konfiguruj** wybierz pozycję **Tak**.
   2. Na karcie **Dołączanie** wybierz pozycję **Dowolne urządzenie**, a następnie wybierz pozycję **Gotowe**.

7. W okienku **Warunki** wybierz pozycję **Aplikacje klienckie**.

   1. W obszarze **Konfiguruj** wybierz pozycję **Tak**.
   2. Wybierz pozycję **Aplikacje mobilne i klienci stacjonarni**.
   3. Wybierz pozycje **Klienci programu Exchange ActiveSync** i **Zastosuj zasady tylko do obsługiwanych platform**.  
   4. Usuń zaznaczenia wszystkich pozostałych pól wyboru.  
   5. Wybierz pozycję **Gotowe**, a następnie ponownie wybierz pozycję **Gotowe**.  

   ![Stosowanie na obsługiwanych platformach](./media/tutorial-protect-email-on-unmanaged-devices/eas-client-apps.png)  

8. W obszarze **Kontrole dostępu** wybierz pozycję **Udziel**.

   1. W okienku **Udzielanie** wybierz pozycję **Udziel dostępu**.
   2. Wybierz pozycję **Wymagaj zatwierdzonej aplikacji klienckiej**. Usuń zaznaczenia wszystkich pozostałych pól wyboru.
   3. Wybierz pozycję **Wybierz**.

   ![Wymaganie zatwierdzonej aplikacji klienckiej](./media/tutorial-protect-email-on-unmanaged-devices/eas-grant-access.png)

9. W obszarze **Włącz zasady** wybierz pozycję **Wł.** , a następnie wybierz pozycję **Utwórz**.

Zasady ochrony aplikacji i dostęp warunkowy zostały teraz utworzone i są gotowe do testowania.

## <a name="try-it-out"></a>Wypróbowywanie działania

Dzięki utworzonym zasadom urządzenia będą musiały zostać zarejestrowane w usłudze Intune i będą musiały używać aplikacji mobilnej Outlook w celu uzyskiwania dostępu do poczty e-mail usługi Office 365. Aby przetestować ten scenariusz w urządzeniu z systemem iOS, zaloguj się do usługi Exchange Online przy użyciu poświadczeń dla użytkownika w dzierżawie testowej.

1. Aby przetestować na telefonie iPhone, przejdź do pozycji **Ustawienia** > **Hasła i konta** > **Dodaj konto** > **Exchange**.

2. Wprowadź adres e-mail użytkownika w dzierżawie testowej, a następnie wybierz pozycję **Dalej**.  
3. Wybierz pozycję **Zaloguj się**.

4. Wprowadź hasło użytkownika testowego i wybierz pozycję **Zaloguj się**.

5. Zostanie wyświetlony komunikat **Wymagane dalsze informacje** oznaczający, że należy skonfigurować usługę MFA. Skonfiguruj dodatkową metodę weryfikacji.

6. Następnie zobaczysz komunikat informujący, że próbujesz otworzyć ten zasób przy użyciu aplikacji, która nie została zatwierdzona przez dział IT. Ten komunikat oznacza, że możliwość korzystania z natywnej aplikacji poczty jest blokowana. Anuluj logowanie.

7. Otwórz aplikację Outlook i wybierz pozycję **Ustawienia** > **Dodaj konto** > **Dodaj konto e-mail**.

8. Wprowadź adres e-mail użytkownika w dzierżawie testowej, a następnie wybierz pozycję **Dalej**.

9. Naciśnij pozycję **Zaloguj się przy użyciu usługi Office 365**. Zostanie wyświetlony monit o dodatkowe uwierzytelnienie i rejestrację. Po zalogowaniu można przetestować akcje, takie jak wycinanie, kopiowanie, wklejanie i używanie polecenia „Zapisz jako”.

## <a name="clean-up-resources"></a>Oczyszczanie zasobów

Gdy zasady testowe nie są już potrzebne, można je usunąć.

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Wybierz pozycję **Urządzenia** **Zasady zgodności**.

3. Z listy **Nazwa zasad** wybierz menu kontekstowe ( **...** ) dla zasad testowych, a następnie wybierz pozycję **Usuń**. Wybierz przycisk **OK**, aby potwierdzić.

4. Wybierz pozycję **Zabezpieczenia punktu końcowego** > **Dostęp warunkowy**.

5. Z listy **Nazwa zasad** wybierz menu kontekstowe ( **...** ) dla każdej z zasad testowych, a następnie wybierz pozycję **Usuń**. Kliknij przycisk **Tak**, aby potwierdzić.

## <a name="next-steps"></a>Następne kroki
W tym samouczku utworzono zasady ochrony aplikacji, aby ograniczyć czynności, które użytkownik może wykonać w aplikacji Outlook. Utworzono również zasady dostępu warunkowego, aby wymagać użycia aplikacji Outlook i usługi MFA w przypadku nowoczesnych klientów uwierzytelniania. Aby dowiedzieć się więcej na temat ochrony innych aplikacji i usług za pomocą usługi Intune z dostępem warunkowym, zobacz artykuł [Konfigurowanie dostępu warunkowego](conditional-access.md).
