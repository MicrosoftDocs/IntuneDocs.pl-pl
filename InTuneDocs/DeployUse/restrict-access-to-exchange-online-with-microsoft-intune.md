---
# required metadata

title: Ograniczanie dostępu poczty e-mail do usługi Exchange Online i nowej usługi Exchange Online w wersji dedykowanej | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 09c82f5d-531c-474d-add6-784c83f96d93

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisgre
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Ograniczanie dostępu poczty e-mail do usługi Exchange Online i nowej usługi Exchange Online w wersji dedykowanej przy użyciu usługi Intune

Jeśli masz środowisko usługi Exchange Online w wersji dedykowanej i chcesz sprawdzić, czy zawiera ono nową, czy starszą konfigurację, skontaktuj się z menedżerem ds. klientów.

Aby kontrolować dostęp poczty e-mail do usługi Exchange Online lub do nowego środowiska usługi Exchange Online w wersji dedykowanej, skonfiguruj dostęp warunkowy dla usługi Exchange Online w usłudze Intune.
Aby dowiedzieć się więcej o sposobie działania dostępu warunkowego, przeczytaj artykuł [Ograniczanie dostępu do poczty e-mail i usług O365](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).

>[!IMPORTANT]
>Dostęp warunkowy dla komputerów i urządzeń z systemem Windows 10 Mobile za pomocą aplikacji korzystających z nowoczesnego uwierzytelniania nie jest obecnie dostępny dla wszystkich klientów usługi Intune. Jeśli te funkcje są już używane, nie ma potrzeby podejmowania żadnych działań. Możesz nadal z nich korzystać.

>Jeśli zasady dostępu warunkowego dla komputerów lub urządzeń z systemem Windows 10 Mobile dla aplikacji korzystających z nowoczesnego uwierzytelniania nie zostały utworzone, a chcesz je utworzyć, musisz przesłać żądanie.  Więcej informacji o znanych problemach, jak również informacje dotyczące sposobu uzyskania dostępu do tej funkcji, można znaleźć w [witrynie Microsoft Connect](http://go.microsoft.com/fwlink/?LinkId=761472).

**Przed** skonfigurowaniem dostępu warunkowego należy:

-   Mieć **subskrypcję usługi Office 365 obejmującą usługę Exchange Online (na przykład E3)**, a użytkownicy muszą mieć licencję na usługę Exchange Online.

-  Rozważyć skonfigurowanie opcjonalnego **łącznika Service To Service Connector usługi Microsoft Intune**, który łączy usługę [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] z usługą Microsoft Exchange Online i ułatwia zarządzanie informacjami o urządzeniu za pośrednictwem konsoli usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. Łącznik nie musi być używany do stosowania zasad zgodności lub dostępu warunkowego, ale jest wymagany do uruchamiania raportów umożliwiających ocenę wpływu dostępu warunkowego.

   > [!NOTE] Nie należy konfigurować łącznika Service To Service Connector, jeśli zamierza się używać dostępu warunkowego zarówno dla usługi Exchange Online, jak i dla lokalnego programu Exchange

   Aby uzyskać instrukcje dotyczące sposobu konfigurowania łącznika, zobacz [Łącznik Service To Service Connector usługi Intune](intune-service-to-service-exchange-connector.md)

Aby po skonfigurowaniu zasad dostępu warunkowego i skierowaniu ich do użytkownika mógł on połączyć się ze swoją pocztą e-mail, jego **urządzenie** musi:

-   Zostać **zarejestrowane** w usłudze [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] lub być komputerem przyłączonym do domeny.

-  **Zostać zarejestrowane w usłudze Azure Active Directory**. Dzieje się to automatycznie podczas rejestrowania urządzenia w usłudze [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. Ponadto identyfikator klienta programu Exchange ActiveSync musi być zarejestrowany w usłudze Azure Active Directory.

  Usługa AAD DRS zostanie automatycznie uaktywniona dla klientów usług Intune i Office 365. Klienci, którzy już wdrożyli usługę rejestrowania urządzeń usług AD FS, nie będą widzieć zarejestrowanych urządzeń w lokalnej usłudze Active Directory.

-   **Być zgodne** ze wszystkimi zasadami zgodności usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] wdrożonymi na tym urządzeniu lub podłączone do domeny lokalnej.

Jeśli zasady dostępu warunkowego nie są spełnione, użytkownikowi podczas logowania zostanie wyświetlony jeden z następujących komunikatów:

- Jeśli urządzenie nie zostało zarejestrowane w usłudze [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] lub Azure Active Directory, zostanie wyświetlony komunikat z instrukcjami dotyczącymi sposobu instalowania aplikacji Portal firmy, rejestrowania urządzenia i aktywowania poczty e-mail. Ten proces powoduje również skojarzenie identyfikatora programu Exchange ActiveSync urządzenia z rekordem w usłudze Azure Active Directory.

-   Jeśli urządzenie nie zostało ocenione jako zgodne z regułami zasad zgodności, użytkownik końcowy zostanie skierowany do witryny sieci Web Portal firmy lub do aplikacji Portal firmy usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], gdzie można znaleźć informacje o problemie i sposobie jego rozwiązania.


Na poniższym diagramie przedstawiono przepływ używany przez zasady dostępu warunkowego dla usługi Exchange Online.

![Diagram ilustrujący punkty decyzyjne określające, czy urządzenie uzyska zezwolenie na dostęp, czy zostanie zablokowane](../media/ConditionalAccess8-1.png)

## Obsługa urządzeń przenośnych
Możliwe jest ograniczenie dostępu do usługi Exchange Online z poziomu programu **Outlook** i innych **aplikacji używających nowoczesnego uwierzytelniania**:

- System Android 4.0 lub nowszy, system Samsung Knox Standard 4.0 lub nowszy
- System iOS 7.1 lub nowszy
- System Windows Phone 8.1 lub nowszy

 **Nowoczesne uwierzytelnianie** umożliwia klientom pakietu Microsoft Office logowanie się przy użyciu biblioteki uwierzytelniania usługi Active Directory (ADAL).

> -   Uwierzytelnianie oparte na bibliotece ADAL umożliwia klientom pakietu Office korzystanie z uwierzytelniania za pomocą przeglądarki (nazywanego też uwierzytelnianiem pasywnym).  W celu uwierzytelnienia użytkownik jest kierowany do strony logowania. Ta nowa metoda logowania zapewnia większe bezpieczeństwo dzięki zastosowaniu **uwierzytelniania wieloskładnikowego** i **uwierzytelniania opartego na certyfikatach**. W tym [artykule](https://support.office.com/en-US/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517) przedstawiono bardziej szczegółowe informacje dotyczące sposobu działania nowoczesnego uwierzytelniania.


Możesz ograniczyć dostęp do poczty e-mail programu Exchange z poziomu wbudowanego **klienta poczty e-mail programu Exchange ActiveSync** na następujących platformach:

- System Android 4.0 lub nowszy, system Samsung Knox Standard 4.0 lub nowszy

- System iOS 7.1 lub nowszy

- System Windows Phone 8.1 lub nowszy

## Obsługa komputerów

Dostęp warunkowy można skonfigurować dla komputerów z aplikacjami klasycznymi pakietu Office, aby uzyskiwać dostęp do usług **Exchange Online** i **SharePoint Online** na komputerach spełniających następujące wymagania:

-   Na komputerze musi działać system Windows 7.0 lub Windows 8.1.

-   Komputer musi zostać przyłączony do domeny lub być zgodny z regułami zasad zgodności.

    W celu zapewnienia zgodności komputer musi zostać zarejestrowany w usłudze [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] i być zgodny z zasadami.

    W przypadku komputerów przyłączonych do domeny musisz skonfigurować [automatyczne rejestrowanie urządzenia](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-automatic-device-registration/) w usłudze Azure Active Directory.

-   [Należy włączyć nowoczesne uwierzytelnianie usługi Office 365](https://support.office.com/en-US/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) i zainstalować wszystkie najnowsze aktualizacje pakietu Office.

    Nowoczesne uwierzytelniane umożliwia logowanie do klientów systemu Windows z pakietem Office 2013 oparte na bibliotece Active Directory Authentication Library (ADAL), a także udostępnia lepsze zabezpieczenia, takie jak **uwierzytelnianie wieloskładnikowe** i **uwierzytelnianie oparte na certyfikatach**.

-   Aby zablokować nienowoczesne protokoły uwierzytelniania, należy skonfigurować reguły oświadczeń ADFS. Szczegółowe instrukcje zostały przedstawione w scenariuszu 3 — [całkowite blokowanie dostępu do usługi O365 z wyjątkiem aplikacji opartych na przeglądarce](https://technet.microsoft.com/library/dn592182.aspx).

## Konfigurowanie zasad dostępu warunkowego
### Krok 1. Konfigurowanie i wdrażanie zasad zgodności
Upewnij się, że zasada zgodności zostanie [utworzona](create-a-device-compliance-policy-in-microsoft-intune.md) i [wdrożona](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md) dla grup użytkowników, którzy otrzymają również zasady dostępu warunkowego.


> [!IMPORTANT] Jeśli zasady zgodności nie zostały wdrożone, urządzenia będą uznawane za zgodne i będą miały dostęp do programu Exchange.

### Krok 2. Ocena wpływu zasad dostępu warunkowego
Możliwe jest użycie **raportów ze spisu urządzeń przenośnych** w celu zidentyfikowania urządzeń, które mogą mieć zablokowany dostęp do programu Exchange po skonfigurowaniu zasad dostępu warunkowego.

W tym celu należy skonfigurować połączenie między usługą [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] i programem Exchange za pomocą [łącznika Service To Service Connector usługi Microsoft Intune](intune-service-to-service-exchange-connector.md).
1.  Przejdź do pozycji **Raporty -> Raporty ze spisu urządzeń przenośnych**.
![Zrzut ekranu przedstawiający stronę z raportem ze spisu urządzeń przenośnych](../media/IntuneSA2bMobileDeviceInventoryReport.png)

2.  W parametrach raportu wybierz grupę usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], która ma zostać oceniona, a następnie, w razie potrzeby, platformy urządzeń, których mają dotyczyć zasady.
3.  Po wybraniu kryteriów spełniających potrzeby organizacji wybierz pozycję **Wyświetl raport**.
Podgląd raportów zostanie otwarty w nowym oknie.
![Zrzut ekranu przedstawiający przykładowy raport ze spisu urządzeń przenośnych](../media/IntuneSA2cViewReport.PNG)

Po uruchomieniu raportu sprawdź następujące cztery kolumny w celu określenia, czy użytkownik będzie zablokowany:

-   **Kanał zarządzania** — wskazuje, czy urządzenie jest zarządzane przez usługę Intune, program Exchange ActiveSync, czy jednocześnie przez usługę i przez program.

-   **Zarejestrowane w usłudze AAD** — wskazuje, czy urządzenie jest zarejestrowane w usłudze Azure Active Directory (tzn. dołączone do obszaru roboczego).

-   **Zgodne** — wskazuje, czy urządzenie jest zgodne ze wszystkimi wdrożonymi zasadami zgodności.

-   **Identyfikator programu Exchange ActiveSync** — urządzenia z systemami iOS i Android muszą mieć identyfikator programu Exchange ActiveSync skojarzony z rekordem rejestracji urządzenia w usłudze Azure Active Directory. Kojarzenie jest wykonywane, gdy użytkownik wybierze link **Uaktywnij pocztę e-mail** w wiadomości e-mail z kwarantanny.

    > [!NOTE] Urządzenia z systemem Windows Phone zawsze wyświetlają wartość w tej kolumnie.

Urządzenia, które należą do grupy docelowej, nie będą mieć dostępu do programu Exchange, chyba że wartości w kolumnach są zgodne z wartościami w poniższej tabeli:

--------------------------
|Kanał zarządzania|Zarejestrowane w usłudze AAD|Zgodny|Identyfikator programu Exchange ActiveSync|Wynikowa akcja|
|----------------------|------------------|-------------|--------------------------|--------------------|
|**Zarządzane przez usługę Microsoft Intune i program Exchange ActiveSync**|Tak|Tak|Wartość jest wyświetlana|Dozwolony dostęp do poczty e-mail|
|Dowolna inna wartość|Nie|Nie|Żadna wartość nie jest wyświetlana|Zablokowany dostęp do poczty e-mail|
----------------------
Możesz wyeksportować zawartość raportu i użyć kolumny **Adres e-mail**, aby poinformować użytkowników o tym, że będą blokowani.

### Krok 3. Konfigurowanie grup użytkowników pod kątem zasad dostępu warunkowego
Zasady dostępu warunkowego są przeznaczone dla innej grupy użytkowników zabezpieczeń usługi Azure Active Directory. Możliwe jest również wykluczenie niektórych grup użytkowników z tych zasad.  Jeśli zasady obejmują użytkownika, każde używane przez niego urządzenie musi być zgodne, aby mógł uzyskać dostęp do poczty e-mail.

Możesz skonfigurować te grupy w **centrum administracyjnym usługi Office 365**lub w **portalu konta usługi Intune**.

Możesz określić dwa typy grup dla każdej zasady:

-   **Grupy docelowe** — grupy użytkowników, dla których zasady są stosowane.

-   **Wykluczone grupy** — grupy użytkowników, którzy są wykluczeni z zasad (opcjonalnie).

Jeśli użytkownik należy do obu grup, będzie wykluczony z zasad.

Oceniane są tylko grupy objęte zasadami dostępu warunkowego.

### Krok 4. Konfigurowanie zasad dostępu warunkowego

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) wybierz pozycję **Zasady** > **Dostęp warunkowy** > **Zasady usługi Exchange Online**.
![Zrzut ekranu przedstawiający stronę zasad dostępu warunkowego usługi Exchange Online](../media/IntuneSA5dExchangeOnlinePolicy.png)

2.  Na stronie **Zasady usługi Exchange Online** zaznacz opcję **Włącz zasady dostępu warunkowego dla usługi Exchange Online**.

    > [!NOTE] Jeśli zasady zgodności nie zostały wdrożone, urządzenia są traktowane jako zgodne.
    >
    > Bez względu na stan zgodności wszyscy użytkownicy, którzy są objęci zasadami, będą musieli zarejestrować używane urządzenia w usłudze [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

3.  W obszarze **Dostęp do aplikacji** w przypadku aplikacji używających nowoczesnego uwierzytelniania użytkownik ma dwa sposoby wyboru platform, których mają dotyczyć zasady. Obsługiwane platformy to Android, iOS, Windows i Windows Phone.

    -   **Wszystkie platformy**

        W przypadku wybrania tego ustawienia wszystkie urządzenia próbujące uzyskać dostęp do usługi **Exchange Online** będą musiały być zarejestrowane w usłudze Intune i zgodne z zasadami.  Każda aplikacja kliencka korzystająca z **nowoczesnego uwierzytelniania** będzie podlegała zasadom dostępu warunkowego, a jeśli dana platforma nie jest aktualnie obsługiwana w usłudze Intune, dostęp do usługi **Exchange Online** zostanie zablokowany.
        >[!TIP]
           Ta opcja może nie być wyświetlana, jeśli nie jest jeszcze używany dostęp warunkowy dla komputerów.  Zamiast tego należy wtedy użyć pozycji **Określone platformy**. Dostęp warunkowy dla komputerów nie jest obecnie dostępny dla wszystkich klientów usługi Intune.   Więcej informacji o znanych problemach, jak również informacje dotyczące sposobu uzyskania dostępu do tej funkcji, można znaleźć w [witrynie Microsoft Connect](http://go.microsoft.com/fwlink/?LinkId=761472).

    -   **Określone platformy**

         Zasady dostępu warunkowego będą stosowane do wszystkich aplikacji klienckich korzystających z **nowoczesnego uwierzytelniania** na określonych platformach urządzeń.

4.  W obszarze **Aplikacje programu Exchange ActiveSync** można zablokować niezgodnym urządzeniom dostęp do usługi Exchange Online. Można również wybrać, czy dostęp do poczty e-mail ma być blokowany, czy nie, gdy na urządzeniu nie działa obsługiwana platforma. Obsługiwane platformy to Android, iOS, Windows i Windows Phone.


5.  W obszarze **Grupy docelowe**wybierz grupy zabezpieczeń użytkowników usługi Active Directory obejmowane przez te zasady. Można wybrać objęcie wszystkich użytkowników lub wybranej listy grup użytkowników.
![Zrzut ekranu przedstawiający stronę zasad dostępu warunkowego usługi Exchange Online, na której wyświetlone są opcje Grupy docelowe i Wykluczone grupy](../media/IntuneSA5eTargetedExemptedGroups.PNG)
    > [!NOTE]W przypadku użytkowników należących do **grup docelowych** zasady usługi Intune spowodują zastąpienie reguł i zasad programu Exchange.
    >
    > Program Exchange będzie tylko wymuszać reguły zezwalania, blokowania i kwarantanny programu Exchange oraz zasady programu Exchange w następujących sytuacjach:
    >
    > -   Użytkownik nie ma licencji na usługę Intune.
    > -   Użytkownik ma licencję na usługę Intune, ale nie należy do żadnej grupy zabezpieczeń użytej w zasadach dostępu warunkowego.

6.  W obszarze **Grupy docelowe**wybierz grupy zabezpieczeń użytkowników usługi Active Directory wykluczane z tych zasad. Jeśli użytkownik należy zarówno do grupy objętej zasadami, jak i do grupy wykluczonej z zasad, będzie wykluczony z zasad.

7.  Gdy wszystko będzie gotowe, wybierz pozycję **Zapisz**.

-   Nie musisz wdrażać zasad dostępu warunkowego; są one aktywne natychmiast.

-   Gdy użytkownik utworzy konto e-mail, urządzenie zostanie od razu zablokowane.

-   Jeśli zablokowany użytkownik zarejestruje urządzenia w usłudze [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] i rozwiąże wszystkie problemy z niezgodnością, dostęp do poczty e-mail zostanie odblokowany w ciągu 2 minut.

-   Jeśli użytkownik wyrejestruje swoje urządzenie, poczta e-mail zostanie zablokowana po około 6 godzinach.

**Aby wyświetlić niektóre przykładowe scenariusze dotyczące sposobu konfigurowania zasad dostępu warunkowego w celu ograniczenia dostępu urządzeń, zobacz [przykładowe scenariusze ograniczania dostępu do poczty e-mail](restrict-email-access-example-scenarios.md).**

## Monitorowanie zgodności i zasad dostępu warunkowego

#### Wyświetlanie urządzeń z zablokowanym dostępem do programu Exchange

Na pulpicie nawigacyjnym usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] wybierz kafelek **Urządzenia z zablokowanym dostępem do programu Exchange**, aby wyświetlić liczbę zablokowanych urządzeń i linki do szczegółowych informacji.
![Zrzut ekranu przedstawiający pulpit nawigacyjny usługi Intune, na którym wyświetlana jest liczba urządzeń, których dostęp do programu Exchange jest zablokowany](../media/IntuneSA6BlockedDevices.PNG)

## Następne kroki
[Ograniczanie dostępu do usługi SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)

[Ograniczanie dostępu do usługi Skype dla firm Online](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)


<!--HONumber=Jun16_HO2-->


