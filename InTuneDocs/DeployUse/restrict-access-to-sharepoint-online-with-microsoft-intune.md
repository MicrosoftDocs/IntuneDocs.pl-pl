---
# required metadata

title: Ograniczanie dostępu do usługi SharePoint Online | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: b088e5a0-fd4a-4fe7-aa49-cb9c8cfb1585

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Ograniczanie dostępu do usługi SharePoint Online przy użyciu usługi Microsoft Intune
Za pomocą dostępu warunkowego usługi [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] możliwe jest kontrolowanie dostępu do plików znajdujących się w usłudze SharePoint Online.
Dostęp warunkowy ma dwa składniki:
- Zasady zgodności urządzenia, które urządzenie musi spełniać, aby można je było uważać za zgodne.
- Zasady dostępu warunkowego, w ramach których określane są warunki, które urządzenie musi spełniać w celu uzyskania dostępu do usługi.
Aby dowiedzieć się więcej o sposobie działania dostępu warunkowego, przeczytaj temat [Ograniczanie dostępu do poczty e-mail i usług O365](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).

Gdy użytkownik próbuje połączyć się z plikiem za pomocą obsługiwanej aplikacji na swoim urządzeniu, takiej jak usługa OneDrive, sprawdzane są następujące kwestie:

![Diagram przedstawiający punkty decyzyjne, które określają, czy urządzenie ma mieć dostęp do usługi SharePoint, czy ma być blokowane ](../media/ConditionalAccess8-6.png)

>[!IMPORTANT]
>Dostęp warunkowy dla komputerów i urządzeń z systemem Windows 10 Mobile za pomocą aplikacji korzystających z nowoczesnego uwierzytelniania nie jest obecnie dostępny dla wszystkich klientów usługi Intune. Jeśli te funkcje są już używane, nie ma potrzeby podejmowania żadnych działań. Możesz nadal z nich korzystać.

>Jeśli zasady dostępu warunkowego dla komputerów lub urządzeń z systemem Windows 10 Mobile dla aplikacji korzystających z nowoczesnego uwierzytelniania nie zostały utworzone, a chcesz je utworzyć, musisz przesłać żądanie.  Więcej informacji o znanych problemach, jak również informacje dotyczące sposobu uzyskania dostępu do tej funkcji można znaleźć w [witrynie Microsoft Connect](http://go.microsoft.com/fwlink/?LinkId=761472).

**Przed** skonfigurowaniem zasad dostępu warunkowego dla usługi SharePoint Online konieczne jest:
- Posiadanie **subskrypcji usługi SharePoint Online**; ponadto użytkownicy muszą mieć licencję na usługę SharePoint Online.
- Posiadanie subskrypcji pakietu **Enterprise Mobility Suite** lub usługi **Azure Active Directory — wersja Premium**.

  Aby nawiązać połączenie z wymaganymi plikami, urządzenie musi:
-   Zostać **zarejestrowane** w usłudze [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] lub na komputerze przyłączonym do domeny.

-   Zostać **zarejestrowane** w usłudze Azure Active Directory; dzieje się to automatycznie podczas rejestrowania urządzenia w [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]).


-   Być zgodne z wdrożonymi zasadami zgodności usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

Stan urządzenia jest przechowywany w usłudze Azure Active Directory, która na podstawie wybranych warunków blokuje dostęp do plików lub go przydziela.

Jeśli warunek nie jest spełniony, użytkownik zobaczy podczas logowania jeden z następujących komunikatów:

-   Jeśli urządzenie nie zostało zarejestrowane w usłudze [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] lub Azure Active Directory, zostanie wyświetlony komunikat z instrukcjami dotyczącymi sposobu instalowania aplikacji Portal firmy i rejestrowania.

-   Jeśli urządzenie nie jest zgodne, zostanie wyświetlony komunikat kierujący użytkownika do witryny internetowej Portal firmy usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], gdzie można znaleźć informacje o problemie i sposobie jego rozwiązania.

## Obsługa urządzeń przenośnych
- System iOS 7.1 lub nowszy
- System Android 4.0 lub nowszy, system Samsung Knox Standard 4.0 lub nowszy
- System Windows Phone 8.1 lub nowszy

## Obsługa komputerów
- System Windows 8.1 lub nowszy (jeśli jest zarejestrowany w usłudze Intune)
- System Windows 7.0 lub Windows 8.1 (jeśli jest przyłączony do domeny)

  - Komputery przyłączone do domeny muszą zostać skonfigurowane do [automatycznego rejestrowania](https://azure.microsoft.com/en-us/documentation/articles/active-directory-conditional-access-automatic-device-registration/) w usłudze Azure Active Directory.
Usługa AAD DRS zostanie automatycznie uaktywniona dla klientów usług Intune i Office 365. Klienci, którzy już wdrożyli usługę rejestrowania urządzeń usług AD FS, nie będą widzieć zarejestrowanych urządzeń w lokalnej usłudze Active Directory.

  - Jeśli zasady zostały ustawione tak, aby przyłączenie do domeny było wymagane, a komputer nie został przyłączony do domeny, zostanie wyświetlony komunikat o konieczności skontaktowania się z administratorem IT.

  - Jeśli zasady zostały ustawione tak, aby wymagane było przyłączenie do domeny lub zgodność, a komputer nie spełnia żadnego z tych wymagań, zostanie wyświetlony komunikat z instrukcjami dotyczącymi sposobu instalowania aplikacji Portal firmy i rejestrowania.
-    [Należy włączyć nowoczesne uwierzytelnianie usługi Office 365](https://support.office.com/en-US/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) i zainstalować wszystkie najnowsze aktualizacje pakietu Office.

    Nowoczesne uwierzytelniane umożliwia logowanie do klientów systemu Windows z pakietem Office 2013 oparte na bibliotece uwierzytelniania usługi Active Directory (ADAL), a także udostępnia lepsze zabezpieczenia, takie jak **uwierzytelnianie wieloskładnikowe** i **uwierzytelnianie oparte na certyfikatach**.


## Konfigurowanie warunkowego dostępu do usługi SharePoint Online

### Krok 1. Konfigurowanie grup zabezpieczeń usługi Active Directory
Przed rozpoczęciem skonfiguruj grupy zabezpieczeń usługi Azure Active Directory dla zasad dostępu warunkowego. Możesz skonfigurować te grupy w **centrum administracyjnym usługi Office 365**lub w **portalu konta usługi Intune**. Grupy te zostaną użyte do objęcia użytkowników zasadami lub wykluczenia użytkowników z zasad. Jeśli zasady obejmują użytkownika, każde używane przez niego urządzenie musi być zgodne, aby mógł uzyskać dostęp do zasobów.

Możesz określić dwa typy grup dla zasad usługi SharePoint Online:

-   **Grupy docelowe** — grupy użytkowników, do których zasady będą stosowane.

-   **Wykluczone grupy** — grupy użytkowników, którzy są wykluczeni z zasad.

Jeśli użytkownik należy do obu grup, będzie wykluczony z zasad.

### Krok 2. Konfigurowanie i wdrażanie zasad zgodności
Jeśli nie zostało zrobione to wcześniej, utwórz i wdróż zasady zgodności dla użytkowników, którzy będą objęci zasadami dostępu usługi SharePoint Online.

> [!NOTE]
> Jeśli zasady zgodności są wdrażane w grupach usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], zasady dostępu warunkowego są stosowane dla grup zabezpieczeń usługi Azure Active Directory.

Aby uzyskać szczegółowe informacje o sposobie konfigurowania zasad zgodności, zobacz [Tworzenie zasad zgodności](create-a-device-compliance-policy-in-microsoft-intune.md).

> [!IMPORTANT]
> Jeśli zasady zgodności nie zostały wdrożone, urządzenia będą traktowane jako zgodne.

Gdy wszystko będzie gotowe, przejdź do **kroku 3**.

### Krok 3. Konfigurowanie zasad usługi SharePoint Online
Skonfiguruj zasady wymagające, aby tylko urządzenia zarządzane i zgodne miały dostęp do usługi SharePoint Online. Te zasady będą przechowywane w usłudze Azure Active Directory.

#### <a name="bkmk_spopolicy"></a>

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) kliknij pozycję **Zasady** > **Dostęp warunkowy** > **Zasady usługi SharePoint Online**.
![Zrzut ekranu przedstawiający stronę zasad usługi SharePoint Online](../media/IntuneSASharePointOnlineCAPolicy.png)

2.  Wybierz pozycję **Włącz zasady dostępu warunkowego dla usługi SharePoint Online**..

3.  W obszarze **Dostęp do aplikacji** możesz wybrać platformy, do których zostaną zastosowane zasady dostępu warunkowego:

    -   **Wszystkie platformy**

        W przypadku wybrania tego ustawienia wszystkie urządzenia próbujące uzyskać dostęp do usługi **SharePoint Online** będą musiały być zarejestrowane w usłudze Intune i zgodne z zasadami.  Każda aplikacja kliencka korzystająca z **nowoczesnego uwierzytelniania** będzie podlegała zasadom dostępu warunkowego. Jeśli dana platforma nie jest aktualnie obsługiwana w usłudze Intune, dostęp do usługi **SharePoint Online** zostanie zablokowany.
        >[!TIP]
        >Ta opcja może nie być wyświetlana, jeśli nie jest jeszcze używany dostęp warunkowy dla komputerów.  Zamiast tego należy wtedy użyć pozycji **Określone platformy**. Dostęp warunkowy dla komputerów nie jest obecnie dostępny dla wszystkich klientów usługi Intune.   Więcej informacji o znanych problemach, jak również informacje dotyczące sposobu uzyskania dostępu do tej funkcji można znaleźć w [witrynie Microsoft Connect](http://go.microsoft.com/fwlink/?LinkId=761472).

    -   **Określone platformy**

         Zasady dostępu warunkowego są stosowane do wszystkich aplikacji klienckich korzystających z nowoczesnego uwierzytelniania na określonych platformach.

     Komputery z systemem Windows muszą zostać przyłączone do domeny lub zarejestrowane w usłudze [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] i być zgodne. Można ustawić następujące wymagania:

     -   **Urządzenia muszą zostać przyłączone do domeny lub być zgodne.** Wybierz tę opcję, jeśli komputery mają być przyłączone do domeny lub zgodne z zasadami ustawionymi w usłudze [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. Jeśli komputer nie spełnia żadnego z tych wymagań, użytkownik zobaczy monit o zarejestrowanie urządzenia w [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

     -   **Urządzenia muszą zostać przyłączone do domeny.** Wybierz tę opcję, jeśli komputery muszą być przyłączone do domeny, aby mogły uzyskiwać dostęp do usługi Exchange Online. Jeśli komputer nie został przyłączony do domeny, dostęp do poczty e-mail będzie zablokowany, a użytkownik zostanie poproszony o skontaktowanie się z administratorem IT.

     -   **Urządzenia muszą być zgodne.** Wybierz tę opcję, jeśli komputery muszą być zarejestrowane w usłudze [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] i zgodne. Jeśli komputer nie został zarejestrowany, zostanie wyświetlony komunikat z instrukcjami dotyczącymi rejestrowania.

4.  W obszarze **Grupy docelowe**kliknij pozycję **Modyfikuj** , aby wybrać grupy zabezpieczeń usługi Azure Active Directory, do których zasady zostaną zastosowane. Możesz objąć zasadami wszystkich użytkowników lub wybrane grupy.

5.  W obszarze **Wykluczone grupy**możesz kliknąć pozycję **Modyfikuj** , jeśli chcesz, aby zasady nie były stosowane dla wskazanych grup zabezpieczeń usługi Azure Active Directory.

6.  Gdy wszystko będzie gotowe, kliknij pozycję **Zapisz**.

Nie musisz wdrażać zasad dostępu warunkowego; są one aktywne natychmiast.

### Krok 4. Monitorowanie zgodności i zasad dostępu warunkowego
W obszarze roboczym **Grupy** można przeglądać informacje o stanie urządzeń.

Wybierz dowolną grupę urządzeń przenośnych, a następnie na karcie **Urządzenia** wybierz jeden z następujących **filtrów**:

-   **Urządzenia, które nie zostały zarejestrowane przy użyciu usługi AAD** — dostęp tych urządzeń do usługi SharePoint Online jest zablokowany.

-   **Urządzenia, które nie są zgodne** — dostęp tych urządzeń do usługi SharePoint Online jest zablokowany.

-   **Urządzenia, które zostały zarejestrowane przy użyciu usługi AAD i są zgodne** — te urządzenia mogą uzyskiwać dostęp do usługi SharePoint Online.

### Zobacz także
[Ograniczanie dostępu do poczty e-mail i usług O365 przy użyciu usługi Microsoft Intune](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)


<!--HONumber=May16_HO1-->


