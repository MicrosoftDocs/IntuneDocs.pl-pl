---
title: Ochrona poczty e-mail w lokalnym programie Exchange | Microsoft Docs
description: "Chroń i kontroluj dostęp do firmowej poczty e-mail w lokalnej instalacji programu Exchange przy użyciu dostępu warunkowego."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a55071f5-101e-4829-908d-07d3414011fc
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 33febef8787887401960592d95356347f6917681
ms.openlocfilehash: 3098a301550413a982d3ce9664646f7dfc0b1d1f
ms.contentlocale: pl-pl
ms.lasthandoff: 05/04/2017


---

# <a name="protect-email-access-to-exchange-on-premises-and-legacy-exchange-online-dedicated-with-intune"></a>Ochrona dostępu do poczty e-mail w lokalnej instalacji programu Exchange i w starszej wersji usługi Exchange Online w wersji dedykowanej przy użyciu usługi Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Przy użyciu usługi Microsoft Intune można skonfigurować dostęp warunkowy do lokalnego programu Exchange lub do starszej wersji usługi Exchange Online w wersji dedykowanej.
Aby dowiedzieć się więcej o sposobie działania dostępu warunkowego, przeczytaj artykuł [Ochrona dostępu do poczty e-mail i usług O365](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).

> [!NOTE]
> Jeśli masz środowisko usługi Exchange Online w wersji dedykowanej i chcesz sprawdzić, czy zawiera ono nową, czy starszą konfigurację, skontaktuj się z menedżerem ds. klientów.

## <a name="before-you-begin"></a>Przed rozpoczęciem

Koniecznie sprawdź, czy są spełnione następujące warunki:

-   Program Exchange musi być w wersji **Exchange 2010 lub nowszej**. Macierze serwerów dostępu klienta (CAS) serwera programu Exchange są obsługiwane.

-   Należy użyć [łącznika lokalnego programu Exchange usługi Intune](intune-on-premises-exchange-connector.md), który łączy usługę Intune z lokalnym programem Exchange. Dzięki temu możliwe jest zarządzanie urządzeniami za pośrednictwem konsoli usługi Intune.

    -   Łącznik lokalnego programu Exchange dostępny w konsoli usługi Intune jest przeznaczony dla Twojej dzierżawy usługi Intune i nie może być używany z innymi dzierżawami. Ponadto zalecamy sprawdzenie, czy łącznik programu Exchange dla Twojej dzierżawy został zainstalowany **tylko na jednym komputerze**.

        Łącznik można pobrać z konsoli administracyjnej usługi Intune. Przewodnik dotyczący sposobu konfigurowania łącznika lokalnego programu Exchange znajduje się w temacie [Konfigurowanie łącznika On-Premises Connector programu Exchange dla lokalnego lub hostowanego programu Exchange](intune-on-premises-exchange-connector.md).

    -   Łącznik można zainstalować na dowolnej maszynie, jeśli jest ona w stanie komunikować się z serwerem programu Exchange.

    -   Łącznik obsługuje **środowisko serwera CAS programu Exchange**. Jeśli chcesz, możesz zainstalować łącznik bezpośrednio na serwerze CAS programu Exchange. Jednak nie zalecamy tego, ponieważ ta operacja zwiększa obciążenie serwera. Podczas konfigurowania łącznika należy ustawić go tak, aby komunikował się z jednym z serwerów CAS programu Exchange.

-   Musisz skonfigurować program **Exchange ActiveSync** przy użyciu uwierzytelniania opartego na certyfikatach lub wpisu poświadczeń użytkownika.

### <a name="device-compliance-requirements"></a>Wymagania dotyczące zgodności urządzeń

Aby po skonfigurowaniu zasad dostępu warunkowego i skierowaniu ich do użytkownika mógł on połączyć się ze swoją pocztą e-mail, jego **urządzenie** musi:

-  Być komputerem przyłączonym do domeny lub zostać **zarejestrowane** w usłudze Intune.

-  **Zostać zarejestrowane w usłudze Azure Active Directory**. Ponadto identyfikator klienta programu Exchange ActiveSync musi być zarejestrowany w usłudze Azure Active Directory.

  Usługa rejestracji urządzeń w usłudze Azure Active Directory zostanie aktywowana automatycznie dla klientów usług Intune i Office 365. Klienci, którzy już wdrożyli usługę rejestracji urządzeń w usługach AD FS, nie będą widzieć zarejestrowanych urządzeń w lokalnej usłudze Active Directory. **Nie dotyczy to komputerów z systemem Windows i urządzeń z systemem Windows Phone**.

-   Być **zgodne** ze wszystkimi zasadami zgodności usługi Intune wdrożonymi na tym urządzeniu.

### <a name="how-conditional-access-works-with-exchange-on-premises"></a>Jak działa dostęp warunkowy w przypadku lokalnego programu Exchange

Na poniższym diagramie przedstawiono przepływ używany przez zasady dostępu warunkowego dla lokalnego programu Exchange na potrzeby oceniania, czy urządzenia mają mieć do niego dostęp, czy dostęp ma być blokowany.

![Diagram przedstawiający punkty decyzyjne, które określają, czy urządzenie ma dostęp do lokalnego programu Exchange, czy też jest blokowane](../media/ConditionalAccess8-2.png)

Jeśli warunek dostępu nie zostanie spełniony, upłynie 10 minut do momentu zablokowania urządzenia i otrzymania przez użytkownika przy próbie zalogowania się jednego z następujących komunikatów dotyczących kwarantanny:

- Jeśli urządzenie nie zostało zarejestrowane w usłudze Intune lub Azure Active Directory, zostanie wyświetlony komunikat z instrukcjami dotyczącymi sposobu instalowania aplikacji Portal firmy, rejestrowania urządzenia i aktywowania poczty e-mail. Ten proces powoduje również skojarzenie identyfikatora programu Exchange ActiveSync urządzenia z rekordem urządzenia w usłudze Azure Active Directory.

-   Jeśli urządzenie nie jest zgodne, zostanie wyświetlony komunikat kierujący użytkownika do witryny sieci Web Portal firmy usługi Intune lub aplikacji Portal firmy, gdzie można znaleźć informacje o problemie i sposobie jego rozwiązania.

## <a name="support-for-mobile-devices"></a>Obsługa urządzeń przenośnych
Obsługiwane są następujące funkcje:
-   System Windows Phone (8.1 lub nowszy).

-   Natywna aplikacja poczty e-mail w systemie iOS.

-   Klienci poczty korzystający z protokołu Exchange ActiveSync, np. Gmail w systemie Android 4 lub nowszym.
-   Klienci poczty korzystający z protokołu Exchange ActiveSync na **urządzeniach z programem Android for Work:** na urządzeniach z programem Android for Work są obsługiwane tylko aplikacje **Gmail** i **Nine Work** w **profilu służbowym**. Aby dostęp warunkowy współdziałał z programem Android for Work, należy wdrożyć profil poczty e-mail dla aplikacji Gmail lub Nine Work, a także wdrożyć te aplikacje jako wymaganą instalację. 

> [!NOTE]
> Aplikacja Microsoft Outlook dla systemów Android i iOS nie jest obsługiwana.

## <a name="support-for-pcs"></a>Obsługa komputerów
Są obsługiwane następujące elementy:
-   Aplikacja **do obsługi poczty** w systemie Windows 8.1 lub nowszym (w przypadku zarejestrowania komputera w usłudze Intune).

##  <a name="configure-a-conditional-access-policy"></a>Konfigurowanie zasad dostępu warunkowego

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) wybierz pozycję **Zasady** > **Dostęp warunkowy** > **Zasady lokalnej instalacji programu Exchange**.
![IntuneSA5aSelectExchOnPremPolicy](../media/IntuneSA5aSelectExchOnPremPolicy.png)

2.  Skonfiguruj zasady za pomocą wymaganych ustawień: ![Zrzut ekranu przedstawiający stronę z zasadami lokalnego programu Exchange](../media/IntuneSA5bExchangeOnPremPolicy.png)

  - **Zablokuj dostęp aplikacjom poczty e-mail do lokalnego programu Exchange, jeśli urządzenie jest niezgodne lub nie jest zarejestrowane w usłudze Microsoft Intune:** po wybraniu tej opcji urządzenia, które nie są zarządzane przez usługę Intune lub nie są zgodne z zasadami zgodności, nie będą miały dostępu do usług programu Exchange.

  - **Przesłanianie reguły domyślnej — zawsze zezwalaj zarejestrowanym i zgodnym urządzeniom na dostęp do programu Exchange:** po wybraniu tej opcji urządzenia zarejestrowane w usłudze Intune i zgodne z zasadami zgodności będą mogły uzyskać dostęp do programu Exchange.
  Ta reguła przesłania **regułę domyślną**, co oznacza, że nawet jeśli wartość **reguły domyślnej** zostanie ustawiona na kwarantannę lub blokowanie dostępu, urządzenia zarejestrowane i zgodne nadal będą mogły uzyskać dostęp do programu Exchange.

  - **Grupy docelowe:** wybierz grupy użytkowników usługi Intune, którzy muszą zarejestrować urządzenie w usłudze Intune, aby uzyskać dostęp do programu Exchange.

  - **Wykluczone grupy:** wybierz grupy użytkowników usługi Intune, którzy są wykluczeni z zasad dostępu warunkowego. Użytkownicy znajdujący się na liście są wykluczani nawet wtedy, gdy znajdują się również na liście **Grupy docelowe**.

  - **Wyjątki dla platform:** wybierz polecenie **Dodaj regułę**, aby skonfigurować regułę definiującą poziomy dostępu dla określonych rodzin i modeli urządzeń przenośnych. Ponieważ te urządzenia mogą być dowolnego typu, możesz także skonfigurować typy urządzeń, które nie są obsługiwane przez usługę Intune.

  - **Reguła domyślna:** dla urządzeń nieobjętych żadnymi innymi regułami możesz wybrać, czy mają mieć dostęp do programu Exchange, czy mają być zablokowane lub czy mają zostać umieszczone w kwarantannie. W przypadku ustawienia reguły zezwalającej na dostęp urządzeń, które są zarejestrowane i zgodne, dostęp do poczty e-mail będzie udzielany automatycznie dla urządzeń z systemem iOS, Windows i Samsung KNOX. Użytkownik nie musi przechodzić przez żaden proces, aby uzyskać dostęp do swojej poczty e-mail.
      - Na urządzeniach, które nie korzystają z systemu KNOX, użytkownicy otrzymują wiadomość e-mail z kwarantanny zawierającą przewodnik krok po kroku w celu sprawdzenia rejestracji i zgodności, zanim uzyskają dostęp do poczty e-mail. Jeśli ustawisz regułę blokującą dostęp do urządzenia lub poddającą je kwarantannie, wszystkie urządzenia będą miały blokowany dostęp do programu Exchange, niezależnie od tego, czy zostały już zarejestrowane w usłudze Intune, czy nie. Aby zapobiec wpływowi tej reguły na urządzenia zarejestrowane i zgodne, zaznacz pole **Przesłonięcie reguły domyślnej**.
>[!TIP]
>Jeśli chcesz najpierw blokować dostęp wszystkich urządzeń przed udzieleniem im dostępu do poczty e-mail, wybierz regułę Blokowanie dostępu lub regułę Kwarantanna. Reguła domyślna jest stosowana dla wszystkich typów urządzeń — również typów urządzeń skonfigurowanych jako wyjątki dla platform i nieobsługiwanych przez usługę Intune.

  - **Powiadomienie użytkownika:** oprócz powiadomienia e-mail wysyłanego przez program Exchange usługa Intune wysyła wiadomość e-mail, która zawiera kroki procedury odblokowania urządzenia. Możesz zmienić domyślną wiadomość zgodnie z własnymi potrzebami. W przypadku zablokowania urządzenia użytkownika przed otrzymaniem z usługi Intune powiadomienia e-mail z instrukcjami odblokowywania (dostarczanego do skrzynki pocztowej programu Exchange użytkownika) możliwe jest użycie niezablokowanego urządzenia lub innej metody uzyskania dostępu do programu Exchange i wyświetlenia wiadomości.
      - Jest to szczególnie istotne, kiedy **Reguła domyślna** jest ustawiona na blokowanie lub kwarantannę. W takim przypadku użytkownik musi przejść do swojego sklepu z aplikacjami, pobrać aplikację firmy Microsoft Portal firmy i zarejestrować swoje urządzenie. Dotyczy to urządzeń z systemami iOS, Windows i Samsung KNOX. W przypadku urządzeń, które nie są wyposażone w platformę Samsung KNOX, należy wysłać wiadomość e-mail poddaną kwarantannie na inne konto poczty e-mail. Użytkownik musi skopiować wiadomość e-mail na zablokowane urządzenie w celu ukończenia procesu rejestracji i zapewnienia zgodności.
  > [!NOTE]
  > Aby program Exchange mógł wysłać powiadomienie e-mail, należy określić konto, które będzie używane do wysyłania powiadomień e-mail.
  >
  > Aby uzyskać szczegółowe informacje, zobacz temat [Konfigurowanie łącznika On-Premises Connector dla lokalnego lub hostowanego programu Exchange](intune-on-premises-exchange-connector.md).

3.  Po zakończeniu tych czynności wybierz pozycję **Zapisz**.

-   Nie musisz wdrażać zasad dostępu warunkowego, ponieważ zostają one natychmiast zastosowane.

-   Po skonfigurowaniu przez użytkownika profilu programu Exchange ActiveSync zablokowanie urządzenia może potrwać od jednej do trzech godzin (jeśli nie jest zarządzane przez usługę Intune).

-   Jeśli następnie zablokowany użytkownik zarejestruje urządzenie w usłudze Intune (i rozwiąże problemy z niezgodnością), dostęp do poczty e-mail zostanie odblokowany w ciągu dwóch minut.

-   Jeśli użytkownik wyrejestruje urządzenie z usługi Intune, zablokowanie urządzenia może potrwać od jednej do trzech godzin.

**Aby wyświetlić niektóre przykładowe scenariusze dotyczące sposobu konfigurowania zasad dostępu warunkowego w celu ochrony dostępu urządzeń, zobacz [Przykładowe scenariusze ochrony dostępu do poczty e-mail](restrict-email-access-example-scenarios.md).**

## <a name="next-steps"></a>Następne kroki
-   [Ochrona dostępu do usługi SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)

-   [Ochrona dostępu do usługi Skype dla firm Online](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)

