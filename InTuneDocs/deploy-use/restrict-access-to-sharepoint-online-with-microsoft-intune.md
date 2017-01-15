---
title: "Ograniczanie dostępu do usługi SharePoint Online | Microsoft Docs"
description: "Ochrona i kontrola dostępu do danych firmy w usłudze SharePoint Online przy użyciu dostępu warunkowego."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b088e5a0-fd4a-4fe7-aa49-cb9c8cfb1585
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 6b900f2bf41ea84088f8453f59b71136e013a884


---

# <a name="restrict-access-to-sharepoint-online-with-microsoft-intune"></a>Ograniczanie dostępu do usługi SharePoint Online przy użyciu usługi Microsoft Intune
Za pomocą dostępu warunkowego usługi [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] możesz kontrolować dostęp do plików znajdujących się w usłudze SharePoint Online.
Dostęp warunkowy ma dwa składniki:
- Zasady zgodności urządzenia, które urządzenie musi spełniać, aby zostało uznane za zgodne.
- Zasady dostępu warunkowego, w ramach których określane są warunki, które urządzenie musi spełniać w celu uzyskania dostępu do usługi.
Aby dowiedzieć się więcej o sposobie działania dostępu warunkowego, przeczytaj temat [Ograniczanie dostępu do poczty e-mail, usługi O365 i innych usług](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).

Zasady zgodności i dostępu warunkowego są wdrażane dla użytkowników. Wszystkie urządzenia, za pomocą których użytkownik uzyskuje dostęp do usług, są sprawdzane pod kątem zgodności z zasadami.

Gdy użytkownik próbuje połączyć się z plikiem za pomocą obsługiwanej aplikacji na swoim urządzeniu, takiej jak OneDrive, sprawdzane są następujące kwestie:

![Diagram przedstawiający punkty decyzyjne, które określają, czy urządzenie może uzyskać dostęp do usługi SharePoint, czy ma być blokowane](../media/ConditionalAccess8-6.png)


**Przed** skonfigurowaniem zasad dostępu warunkowego dla usługi SharePoint Online konieczne jest:
- Posiadanie **subskrypcji usługi SharePoint Online** oraz posiadanie licencji użytkowników na usługę SharePoint Online.
- Posiadanie **subskrypcji pakietu Enterprise Mobility + Security (EMS)** lub **subskrypcji usługi Azure Active Directory (Azure AD) Premium** oraz posiadanie licencji użytkowników na usługi EMS lub Azure AD. Aby uzyskać więcej szczegółowych informacji, zobacz [Cennik pakietu Enterprise Mobility](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility-pricing) lub [Cennik usługi Azure Active Directory](https://azure.microsoft.com/en-us/pricing/details/active-directory/).


  Aby nawiązać połączenie z wymaganymi plikami, urządzenie musi być:
-   **zarejestrowane** przy użyciu usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] lub komputera przyłączonego do domeny;

-   **zarejestrowane** w usłudze Azure Active Directory (jest to wykonywane automatycznie podczas rejestrowania urządzenia w usłudze [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]);


-   **zgodne** z wdrożonymi zasadami zgodności usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

Stan urządzenia jest przechowywany w usłudze Azure Active Directory, która na podstawie określonych warunków blokuje dostęp do plików lub go przydziela.

Jeśli warunek nie jest spełniony, użytkownik widzi podczas logowania jeden z następujących komunikatów:

-   Jeśli urządzenie nie zostało zarejestrowane w usługach [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] lub Azure Active Directory, zostanie wyświetlony komunikat z instrukcjami dotyczącymi sposobu instalacji aplikacji Portal firmy oraz dokonywania rejestracji.

-   Jeśli urządzenie nie jest zgodne, zostanie wyświetlony komunikat kierujący użytkownika do witryny internetowej Portal firmy usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], gdzie można znaleźć informacje na temat problemu i sposobu jego rozwiązania.

**Dostęp warunkowy nie ma zastosowania do udostępniania zewnętrznego**. Aby dowiedzieć się, jak zapobiegać zewnętrznemu udostępnianiu w dzierżawie lub zbiorze witryn, zobacz temat [Zarządzanie udostępnianiem zewnętrznym w środowisku usługi SharePoint Online](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85?ui=en-US&rs=en-US&ad=US).

>[!NOTE]
>Po włączeniu dostępu warunkowego dla usługi SharePoint Online zaleca się wyłączenie domeny na liście zgodnie z opisem w temacie [Remove-SPOTenantSyncClientRestriction](https://technet.microsoft.com/en-us/library/dn917451.aspx).  

## <a name="support-for-mobile-devices"></a>Obsługa urządzeń przenośnych
Obsługiwane są następujące funkcje:
- System iOS 8.0 i nowsze
- System Android 4.0 lub nowszy, system Samsung Knox Standard 4.0 lub nowszy
- System Windows Phone 8.1 lub nowszy

Można ograniczyć dostęp do usługi SharePoint Online w przypadku uzyskiwania dostępu za pomocą przeglądarki na urządzeniach z systemem **iOS** i **Android**. Dostęp może być dozwolony tylko za pośrednictwem obsługiwanych przeglądarek na zgodnych urządzeniach:
* Safari (iOS)
* Chrome (Android)
* Intune Managed Browser (systemy iOS i Android 5.0 lub nowszy)

**Nieobsługiwane przeglądarki są blokowane**.

## <a name="support-for-pcs"></a>Obsługa komputerów
Obsługiwane są następujące funkcje:
- System Windows 8.1 lub nowszy (jeśli komputery są zarejestrowane w usłudze Intune)
- System Windows 7.0, Windows 8.1 lub Windows 10 (jeśli komputery są przyłączone do domeny)
> [!NOTE]
>Aby korzystać z dostępu warunkowego na komputerach z systemem Windows 10, trzeba na nich zainstalować Rocznicową aktualizację systemu Windows 10.

  - Komputery przyłączone do domeny muszą zostać skonfigurowane do [automatycznego rejestrowania](https://azure.microsoft.com/en-us/documentation/articles/active-directory-conditional-access-automatic-device-registration/) w usłudze Azure Active Directory. Usługa rejestracji urządzeń w usłudze Azure AD zostanie aktywowana automatycznie dla klientów usług Intune i Office 365. Klienci, którzy już wdrożyli usługę rejestracji urządzeń w usługach AD FS, nie będą widzieć zarejestrowanych urządzeń w lokalnej usłudze Active Directory.

  - Jeśli zasady zostały skonfigurowane w taki sposób, aby przyłączenie do domeny było wymagane, a komputer nie został przyłączony do domeny, zostanie wyświetlony komunikat o konieczności skontaktowania się z administratorem IT.

  - Jeśli zasady zostały ustawione w taki sposób, aby wymagane było przyłączenie do domeny lub zgodność, a komputer nie spełnia żadnego z tych wymagań, zostanie wyświetlony komunikat z instrukcjami dotyczącymi sposobu instalacji aplikacji Portal firmy i dokonywania rejestracji.
  >[!NOTE]
  >Dostęp warunkowy nie jest obsługiwany na komputerach z uruchomionym oprogramowaniem klienckim usługi Intune.

[Należy włączyć nowoczesne uwierzytelnianie w usłudze Office 365](https://support.office.com/en-US/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) i zainstalować wszystkie najnowsze aktualizacje pakietu Office.

Nowoczesne uwierzytelnianie umożliwia logowanie do klientów systemu Windows z pakietem Office 2013 oparte na bibliotece Active Directory Authentication Library (ADAL), a także udostępnia lepsze zabezpieczenia, takie jak **uwierzytelnianie wieloskładnikowe** i **uwierzytelnianie oparte na certyfikatach**.


## <a name="configure-conditional-access-for-sharepoint-online"></a>Konfigurowanie warunkowego dostępu do usługi SharePoint Online

### <a name="step-1-configure-active-directory-security-groups"></a>Krok 1. Konfigurowanie grup zabezpieczeń usługi Active Directory
Przed rozpoczęciem skonfiguruj grupy zabezpieczeń usługi Azure Active Directory dla zasad dostępu warunkowego. Możesz skonfigurować te grupy w **centrum administracyjnym usługi Office 365**lub w **portalu konta usługi Intune**. Te grupy są używane do objęcia użytkowników zasadami lub wykluczenia ich z zasad. Jeśli zasady obejmują użytkownika, każde używane przez niego urządzenie musi być z nimi zgodne, aby uzyskać dostęp do zasobów.

Możesz określić dwa typy grup dla zasad usługi SharePoint Online:

-   **Grupy docelowe**: grupy użytkowników, do których zasady mają zastosowanie.

-   **Wykluczone grupy**: grupy użytkowników, którzy są wykluczeni z zasad.

Jeśli użytkownik należy do obu grup, będzie wykluczony z zasad.

### <a name="step-2-configure-and-deploy-a-compliance-policy"></a>Krok 2. Konfigurowanie i wdrażanie zasad zgodności
Jeśli nie zostało zrobione to wcześniej, utwórz zasady zgodności i dokonaj ich wdrożenia dla użytkowników, którzy będą objęci zasadami usługi SharePoint Online.

> [!NOTE]
> Jeśli zasady zgodności są wdrażane w grupach usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], zasady dostępu warunkowego są stosowane dla grup zabezpieczeń usługi Azure Active Directory.

Aby uzyskać szczegółowe informacje o sposobie konfigurowania zasad zgodności, zobacz temat [Tworzenie zasad zgodności](create-a-device-compliance-policy-in-microsoft-intune.md).

> [!IMPORTANT]
> Jeśli zasady zgodności nie zostały wdrożone, urządzenia są traktowane jako zgodne.

Gdy wszystko będzie gotowe, przejdź do **kroku 3**.

### <a name="step-3-configure-the-sharepoint-online-policy"></a>Krok 3. Konfigurowanie zasad usługi SharePoint Online
Skonfiguruj zasady wymagające, aby tylko urządzenia zarządzane i zgodne miały dostęp do usługi SharePoint Online. Te zasady będą przechowywane w usłudze Azure Active Directory.

#### <a name="bkmk_spopolicy"></a>

>[!NOTE]
> Można też utworzyć zasady dostępu warunkowego dla urządzeń z usługą Intune w konsoli zarządzania usługi Azure AD (w usłudze Azure AD zasady są określane jako **zasady dostępu warunkowego oparte na urządzeniu**). Ponadto można tworzyć inne zasady dostępu warunkowego, np. dotyczące uwierzytelniania wieloskładnikowego. Można także ustawić zasady dostępu warunkowego dla aplikacji korporacyjnych innych firm obsługiwanych przez usługę Azure AD, np. Salesforce i Box. Aby uzyskać więcej informacji, zobacz [Jak ustawić oparte na urządzeniach zasady dostępu warunkowego usługi Azure Active Directory w celu kontrolowania dostępu do aplikacji połączonych z usługą Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-conditional-access-policy-connected-applications/).


1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) wybierz pozycję **Zasady** > **Dostęp warunkowy** > **Zasady usługi SharePoint Online**.
![Zrzut ekranu przedstawiający stronę zasad usługi SharePoint Online](../media/mdm-ca-spo-policy-configuration.png)

2.  Wybierz pozycję **Włącz zasady dostępu warunkowego dla usługi SharePoint Online**.

3.  W obszarze **Dostęp do aplikacji** możesz wybrać platformy, do których zostaną zastosowane zasady dostępu warunkowego:

    -   **Wszystkie platformy**

        W przypadku wybrania tego ustawienia wszystkie urządzenia próbujące uzyskać dostęp do usługi **SharePoint Online** będą musiały być zarejestrowane w usłudze Intune i zgodne z zasadami. Każda aplikacja kliencka korzystająca z **nowoczesnego uwierzytelniania** będzie podlegała zasadom dostępu warunkowego. Jeśli dana platforma nie jest aktualnie obsługiwana przez usługę Intune, dostęp do usługi **SharePoint Online** zostanie zablokowany.

        Wybranie opcji **Wszystkie platformy** oznacza, że usługa Azure Active Directory będzie stosować te zasady do wszystkich żądań uwierzytelniania zgłoszonych przez aplikację klienta, niezależnie od platformy. W przypadku wszystkich platform będzie wymagana rejestracja w usłudze Intune oraz zgodność, z następującymi wyjątkami:
        *   Urządzenia z systemem Windows, które są objęte wymogiem rejestracji i zgodności, przyłączone do domeny przy użyciu lokalnej usługi Active Directory lub spełniające oba te wymogi.
        * Nieobsługiwane platformy takie jak Mac. Aplikacje korzystające z nowoczesnego uwierzytelniania pochodzące z tych platform będą jednak nadal blokowane.

    -   **Określone platformy**

         Zasady dostępu warunkowego są stosowane do wszystkich aplikacji klienckich korzystających z nowoczesnego uwierzytelniania na określonych platformach.

     Komputery z systemem Windows muszą zostać przyłączone do domeny lub zarejestrowane w usłudze [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] i być zgodne. Można ustawić następujące wymagania:

     -   **Urządzenia muszą zostać przyłączone do domeny lub być zgodne.** Wybierz tę opcję, jeśli komputery mają być przyłączone do domeny lub zgodne z zasadami skonfigurowanymi w usłudze [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. Jeśli komputer nie spełnia żadnego z tych wymagań, użytkownik otrzyma monit o zarejestrowanie urządzenia w usłudze [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

     -   **Urządzenia muszą zostać przyłączone do domeny.** Wybierz tę opcję, jeśli komputery mają być przyłączone do domeny, aby mogły uzyskiwać dostęp do usługi Exchange Online. Jeśli komputer nie został przyłączony do domeny, dostęp do poczty e-mail będzie zablokowany, a użytkownik zostanie poproszony o skontaktowanie się z administratorem IT.

     -   **Urządzenia muszą być zgodne.** Wybierz tę opcję, jeśli komputery mają być zarejestrowane w usłudze [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] i zgodne. Jeśli komputer nie został zarejestrowany, zostanie wyświetlony komunikat z instrukcjami dotyczącymi rejestracji.

4.   W obszarze **dostępu za pomocą przeglądarki** do usług SharePoint Online i OneDrive dla Firm można zezwolić na dostęp do usługi Exchange Online tylko za pośrednictwem obsługiwanych przeglądarek: Safari (iOS) i Chrome (Android). Dostęp z innych przeglądarek będzie zablokowany. Ograniczenia platformy wybrane dla dostępu aplikacji do usługi OneDrive mają zastosowanie również w tym miejscu.

  Na urządzeniach z systemem **Android** użytkownicy muszą włączyć dostęp za pomocą przeglądarki. W tym celu użytkownik musi wybrać opcję **Włączanie dostępu za pomocą przeglądarki** na zarejestrowanym urządzeniu, wykonując następujące czynności:
  1.    Otworzyć aplikację **Portal firmy**.
  2.    Przejść do strony **Ustawienia** za pomocą przycisku oznaczonego wielokropkiem (…) lub przycisku menu urządzenia.
  3.    Nacisnąć przycisk **Włącz dostęp za pomocą przeglądarki**.
  4.    W przeglądarce Chrome wylogować się z usługi Office 365 i ponownie uruchomić przeglądarkę Chrome.

  Na platformach **iOS** i **Android** w celu zidentyfikowania urządzenia używanego do uzyskania dostępu do usługi usługa Azure Active Directory wystawi certyfikat TLS (Transport Layer Security) dla urządzenia. Urządzenie wyświetli użytkownikowi certyfikat wraz z monitem o wybranie certyfikatu, jak przedstawiono na zrzutach ekranu poniżej. Użytkownik musi wybrać ten certyfikat przed rozpoczęciem korzystania z przeglądarki.

  **iOS**

  ![Zrzut ekranu przedstawiający monit dotyczący certyfikatu na urządzeniu iPad](../media/mdm-browser-ca-ios-cert-prompt.png)

  **Android**

  ![Zrzut ekranu przedstawiający monit dotyczący certyfikatu na urządzeniu z systemem Android](../media/mdm-browser-ca-android-cert-prompt.png)
5.  W obszarze **Grupy docelowe** wybierz pozycję **Modyfikuj**, aby wybrać grupy zabezpieczeń usługi Azure Active Directory, które zostaną objęte zasadami. Możesz objąć zasadami wszystkich użytkowników lub ich wybrane grupy.

6.  W obszarze **Wykluczone grupy** możesz wybrać pozycję **Modyfikuj**, jeśli chcesz, aby zasady nie były stosowane dla wskazanych grup zabezpieczeń usługi Azure Active Directory.

7.  Po zakończeniu tych czynności wybierz pozycję **Zapisz**.

Nie musisz wdrażać zasad dostępu warunkowego, ponieważ zostają one natychmiast zastosowane.

### <a name="step-4-monitor-the-compliance-and-conditional-access-policies"></a>Krok 4. Monitorowanie zgodności i zasad dostępu warunkowego
W obszarze roboczym **Grupy** można przeglądać informacje o stanie urządzeń.

Wybierz dowolną grupę urządzeń przenośnych. Następnie na karcie **Urządzenia**, w obszarze **Filtry** wybierz jedną z następujących opcji:

-   **Urządzenia, które nie są zarejestrowane w usłudze AAD**. Dostęp tych urządzeń do usługi SharePoint Online jest zablokowany.

-   **Urządzenia, które nie są zgodne**. Dostęp tych urządzeń do usługi SharePoint Online jest zablokowany.

-   **Urządzenia, które są zarejestrowane w usłudze AAD i są zgodne**. Te urządzenia mogą uzyskiwać dostęp do usługi SharePoint Online.

### <a name="see-also"></a>Zobacz także
[Ograniczanie dostępu do poczty e-mail i usług O365 przy użyciu usługi Microsoft Intune](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


