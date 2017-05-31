---
title: "Konfigurowanie subskrypcji przy użyciu usługi Lookout | Dokumentacja firmy Microsoft"
description: "Ten temat zawiera szczegółowe informacje dotyczące sposobu konfigurowania ochrony urządzeń przed zagrożeniami w usłudze Lookout."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8477a2f1-2e1d-4d42-8bcb-e1181cc900bb
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 3c777d8857fd177e5a27840ab8a97c8a137aa189
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---

# <a name="set-up-your-lookout-mobile-threat-defense-subscription"></a>Konfigurowanie subskrypcji usługi Lookout Mobile Threat Defense

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Do skonfigurowania usługi Lookout Mobile Threat Defense wymagane są następujące kroki:

| #        |Krok  |
| ------------- |:-------------|
| 1 | [Zbieranie informacji z usługi Azure AD](#collect-azure-ad-information) |
| 2 | [Konfigurowanie subskrypcji](#configure-your-subscription) |
| 3 | [Konfigurowanie grup rejestracji](#configure-enrollment-groups) |
| 4 | [Konfigurowanie synchronizacji stanu](#configure-state-sync) |
| 5 | [Konfigurowanie informacji o adresie e-mail odbiorcy raportów o błędach](#configure-error-report-email-recipient-information) |
| 6 | [Konfigurowanie ustawień rejestracji](#configure-enrollment-settings) |
| 7 | [Konfigurowanie powiadomień e-mail](#configure-email-notifications) |
| 8 | [Konfigurowanie klasyfikacji zagrożeń](#configure-threat-classification) |
| 1 | [Obserwowanie rejestracji](#watching-enrollment) |


> [!IMPORTANT]
> Nie można użyć istniejącej dzierżawy usługi Lookout Mobile Endpoint Security, która nie została wcześniej skojarzona z dzierżawą usługi Azure AD, w celu integracji z usługami Azure AD i Intune. Skontaktuj się z pomocą techniczną firmy Lookout, aby utworzyć nową dzierżawę usługi Lookout Mobile Endpoint Security. Przy użyciu nowej dzierżawy dodaj użytkowników usługi Azure AD.

## <a name="collect-azure-ad-information"></a>Zbieranie informacji z usługi Azure AD
Dzierżawa usługi Lookout Mobility Endpoint Security zostanie skojarzona z subskrypcją usługi Azure AD w celu zintegrowania usługi Lookout z usługą Intune. Aby włączyć subskrypcję usługi Lookout Mobile Threat Defense, zespół pomocy technicznej firmy Lookout (enterprisesupport@lookout.com) potrzebuje następujących informacji:  

* **Identyfikator dzierżawy usługi Azure AD**
* **Identyfikator obiektu grupy usługi Azure AD** dla **pełnego** dostępu do konsoli usługi Lookout
* **Identyfikator obiektu grupy usługi Azure AD** dla **ograniczonego** dostępu do konsoli usługi Lookout (opcjonalnie)

Wykonaj poniższe kroki w celu zebrania informacji, które musisz przekazać zespołowi pomocy technicznej firmy Lookout.

1. Zaloguj się do [portalu zarządzania usługi Azure AD](https://manage.windowsazure.com) i wybierz swoją subskrypcję. 
  ![Zrzut ekranu strony usługi Azure AD przedstawiający nazwę dzierżawy](../media/mtp/aad_tenant_name.png)
2. Po wybraniu nazwy subskrypcji wynikowy adres URL zawiera identyfikator subskrypcji.  Jeśli masz problemy ze znalezieniem identyfikatora subskrypcji, zobacz ten [artykuł pomocy technicznej firmy Microsoft](https://support.office.com/article/Find-your-Office-365-tenant-ID-6891b561-a52d-4ade-9f39-b492285e2c9b), aby uzyskać wskazówki dotyczące znajdowania identyfikatora subskrypcji. 
3. Wyszukaj identyfikator grupy usługi Azure AD. Konsola usługi Lookout obsługuje 2 poziomy dostępu:  
  * **Pełny dostęp:** administrator usługi Azure AD może utworzyć grupę użytkowników, którzy będą mieć pełny dostęp i opcjonalnie utworzyć grupę użytkowników z ograniczonym dostępem.  Tylko użytkownicy z tych grup będą mogli logować się do **konsoli usługi Lookout**.
  * **Ograniczony dostęp:** użytkownicy w tej grupie nie będą mieć dostępu do kilku modułów konsoli usługi Lookout związanych z konfiguracją oraz rejestracją i będą mieć dostęp tylko do odczytu do modułu **Security Policy** (Zasady zabezpieczeń) konsoli usługi Lookout.  

  Więcej informacji dotyczących uprawnień znajduje się w witrynie sieci Web [w tym artykule](https://personal.support.lookout.com/hc/articles/114094105653).

  **Identyfikator obiektu grupy** można znaleźć na stronie **Właściwości** grupy w **konsoli zarządzania usługi Azure AD**.

  ![Zrzut ekranu strony właściwości z wyróżnionym polem Identyfikator grupy](../media/mtp/aad_group_object_id.png)

4. Po zebraniu tych informacji skontaktuj się z zespołem pomocy technicznej firmy Lookout (adres e-mail: enterprisesupport@lookout.com). Pomoc techniczna firmy Lookout wspólnie z główną osobą kontaktową doda subskrypcję i utworzy konto przedsiębiorstwa w usłudze Lookout przy użyciu zebranych wcześniej informacji.

## <a name="configure-your-subscription"></a>Konfigurowanie subskrypcji
1. Po utworzeniu przez zespół pomocy technicznej firmy Lookout konta usługi Lookout Enterprise do głównej osoby kontaktowej w firmie zostanie wysłana wiadomość e-mail zawierająca link do adresu URL logowania: https://aad.lookout.com/les?action=consent.

2.  Podczas pierwszego logowania do konsoli usługi Lookout należy użyć konta użytkownika w roli administratora globalnego usługi Azure AD w celu zarejestrowania dzierżawy usługi Azure AD. Później podczas logowania ten poziom uprawnienia usługi Azure AD nie będzie używany. Zostanie wyświetlona strona zgody użytkownika. Wybierz przycisk **Accept** (Akceptuj) w celu ukończenia rejestracji.

  ![Zrzut ekranu strony pierwszego logowania do konsoli aplikacji Lookout](../media/mtp/lookout_mtp_initial_login.png) Po zaakceptowaniu i wyrażeniu zgody nastąpi przekierowanie do konsoli usługi Lookout.

  Aby uzyskać pomoc dotyczącą problemów z logowaniem, zobacz [Rozwiązywanie problemów dotyczących integracji aplikacji Lookout z usługą Intune](/intune-classic/troubleshoot/troubleshooting-lookout-integration).

3.  W [konsoli usługi Lookout](https://aad.lookout.com) w module **System** wybierz kartę **Connectors** (Łączniki), a następnie wybierz pozycję **Intune**.

  ![Zrzut ekranu konsoli usługi Lookout z otwartą kartą łączników i wyróżnioną opcją Intune](../media/mtp/lookout_mtp_setup-intune-connector.png)

4.  Wybierz kolejno pozycje **Connectors** > **Connection Settings** (Łączniki > Ustawienia połączeń) i określ wartość **Heartbeat Frequency** (Częstotliwość pulsu) w minutach.

  ![Zrzut ekranu przedstawiający kartę ustawień połączenia i skonfigurowaną częstotliwość pulsu](../media/mtp/lookout-mtp-connection-settings.png)

## <a name="configure-enrollment-groups"></a>Konfigurowanie grup rejestracji
1. Najlepszym rozwiązaniem jest utworzenie w [portalu zarządzania usługi Azure AD](https://manage.windowsazure.com) grupy zabezpieczeń usługi Azure AD zawierającej małą liczbę użytkowników na potrzeby testowania integracji z usługą Lookout.

  Wszystkie urządzenia obsługiwane przez usługę Lookout i zarejestrowane w usłudze Intune, które należą do użytkowników w grupie rejestracji w usłudze Azure AD oraz zostały zidentyfikowane w usłudze Azure AD i są przez nią obsługiwane, są zarejestrowane i uprawnione do aktywacji w usłudze ochrony urządzeń przed zagrożeniami w usłudze Lookout.

2. W [konsoli usługi Lookout](https://aad.lookout.com) w module **System** wybierz kartę **Connectors** (Łączniki), a następnie wybierz pozycję **Enrollment Management** (Zarządzenia rejestracjami), aby zdefiniować zestaw użytkowników, których urządzenia powinny zostać zarejestrowane w usłudze Lookout. Dodaj grupę zabezpieczeń usługi Azure AD **Nazwa wyświetlana** na potrzeby rejestracji.

  ![Zrzut ekranu strony rejestracji łącznika usługi Intune](../media/mtp/lookout-mtp-enrollment.png)

  >[!IMPORTANT]
  > Wartość **Nazwa wyświetlana** uwzględnia wielkość liter, jak pokazano w obszarze **Właściwości** grupy zabezpieczeń w witrynie Azure Portal. Jak widać poniżej, wartość **Nazwa wyświetlana** ma format camelCase, a tytuł jest pisany małymi literami. W konsoli usługi Lookout dopasuj wielkość liter wartości **Nazwa wyświetlana** dla grupy zabezpieczeń.
  >![Zrzut ekranu przedstawiający witrynę Azure Portal, usługę Azure Active Directory i stronę właściwości](../media/mtp/aad-group-display-name.png)

  Najlepszym rozwiązaniem jest użycie domyślnej wartości (5 minut) określającej, ile czasu ma upłynąć między kolejnymi próbami wykrywania nowego urządzenia.

  **Aktualne ograniczenia:**
  * Usługa Lookout nie może walidować nazw wyświetlanych grup.  Upewnij się, że wartość pola **NAZWA WYŚWIETLANA** w witrynie Azure Portal odpowiada dokładnie grupie zabezpieczeń usługi Azure AD.
  * Tworzenie grup zagnieżdżonych nie jest obsługiwane.  Grupy zabezpieczeń usługi Azure AD używane w usłudze Lookout muszą zawierać tylko użytkowników. Nie mogą zawierać innych grup.

3.  Po dodaniu grupy przy następnym otwarciu aplikacji Lookout for Work przez użytkownika na obsługiwanym urządzeniu zostanie ono aktywowane w usłudze Lookout.

4.  Jeśli wyniki są satysfakcjonujące, można rozszerzyć rejestrację na dodatkowe grupy użytkowników.

## <a name="configure-state-sync"></a>Konfigurowanie synchronizacji stanu
W opcji **State Sync** (Synchronizacja stanu) określ typ danych, które powinny być przesyłane do usługi Intune.  Do prawidłowego działania integracji usług Lookout i Intune jest wymagany stan urządzenia i stan zagrożenia.  Oba są domyślnie włączone.

## <a name="configure-error-report-email-recipient-information"></a>Konfigurowanie informacji o adresie e-mail odbiorcy raportów o błędach
W opcji **Error Management** (Zarządzanie błędami) wpisz adres e-mail, na który mają być wysyłane raporty o błędach.

![Zrzut ekranu strony zarządzania błędami łącznika usługi Intune](../media/mtp/lookout-mtp-connector-error-notifications.png)

## <a name="configure-enrollment-settings"></a>Konfigurowanie ustawień rejestracji
W module **System** na stronie **Connectors** (Łączniki) określ liczbę dni, zanim urządzenie zostanie uznane za odłączone.  Odłączone urządzenia są uznawane za niezgodne i nie mają dostępu do aplikacji firmowych zgodnie z zasadami dostępu warunkowego usługi Intune. Można określić wartości z zakresu od 1 do 90 dni.

![](../media/mtp/lookout-console-enrollment-settings.png)

## <a name="configure-email-notifications"></a>Konfigurowanie powiadomień e-mail
Jeśli chcesz otrzymywać alerty e-mail dotyczące zagrożeń, zaloguj się do [konsoli usługi Lookout](https://aad.lookout.com) przy użyciu konta użytkownika, który powinien otrzymywać powiadomienia. Na karcie **Preferences** (Preferencje) modułu **System** wybierz poziom zagrożenia, który powinien wywoływać powiadomienia, i ustaw go na wartość **ON** (Włącz). Zapisz zmiany.

![Zrzut ekranu strony preferencji z wyświetlonym kontem użytkownika](../media/mtp/lookout-mtp-email-notifications.png) Jeśli nie chcesz już otrzymywać powiadomień pocztą e-mail, ustaw dla powiadomień wartość **OFF** (Wyłącz) i zapisz zmiany.

### <a name="configure-threat-classification"></a>Konfigurowanie klasyfikacji zagrożeń
Usługa Lookout Mobile Threat Defense klasyfikuje różne typy zagrożeń dla urządzeń przenośnych. [Klasyfikacje zagrożeń w usłudze Lookout](http://personal.support.lookout.com/hc/articles/114094130693) mają domyślne poziomy ryzyka, które są z nimi skojarzone. Można je zmienić w dowolnym momencie zależnie od potrzeb firmy.

![Zrzut ekranu przedstawiający stronę zasad wraz z zagrożeniem i klasyfikacjami](../media/mtp/lookout-mtp-threat-classification.png)

>[!IMPORTANT]
> Poziomy ryzyka są istotnym elementem usługi Mobile Threat Defense, ponieważ podczas integracji usługi Intune na ich podstawie jest określana zgodność urządzenia w czasie wykonywania. Administrator usługi Intune ustawia regułę w zasadach, aby uznawać urządzenie za niezgodne, jeśli zawiera ono aktywne zagrożenie z **wysokim**, **średnim** lub **niskim** poziomem ryzyka. Obliczanie zgodności urządzenia w usłudze Intune zależy bezpośrednio od zasad klasyfikacji zagrożeń w usłudze Lookout Mobile Threat Defense.

## <a name="watching-enrollment"></a>Obserwowanie rejestracji
Po zakończeniu konfiguracji usługa Lookout Mobile Threat Defense rozpoczyna sondowanie usługi Azure AD pod kątem urządzeń, które odpowiadają określonym grupom rejestracji.  Informacje o zarejestrowanych urządzeniach znajdują się w module Devices (Urządzenia).  Początkowy stan urządzeń jest wyświetlany jako oczekujący.  Stan urządzenia ulega zmianie po zainstalowaniu, otwarciu i aktywowaniu aplikacji Lookout for Work na danym urządzeniu.  Aby uzyskać szczegółowe informacje na temat sposobu wypychania aplikacji Lookout for Work do urządzenia, zobacz temat [Configure and deploy Lookout for work apps](configure-deploy-lookout-for-work-app.md) (Konfigurowanie i wdrażanie aplikacji Lookout for Work).
## <a name="next-steps"></a>Następne kroki
[Włączanie połączenia Lookout MTP dla usługi Intune](/intune-classic/deploy-use/enable-lookout-mtd-connection)

