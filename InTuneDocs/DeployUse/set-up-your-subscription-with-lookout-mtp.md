---
title: "Konfigurowanie subskrypcji przy użyciu usługi Lookout | Microsoft Intune"
description: "Ten temat zawiera szczegółowe informacje dotyczące sposobu konfigurowania ochrony urządzeń przed zagrożeniami w usłudze Lookout."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8477a2f1-2e1d-4d42-8bcb-e1181cc900bb
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1187ad3fdd4a427333d610686698c1f806c6ee33
ms.openlocfilehash: 1d8cdaa36a852fba5912c250daa500e16bd3b661


---

# <a name="set-up-your-subscription-for-lookout-device-threat-protection"></a>Konfigurowanie subskrypcji pod kątem ochrony urządzeń przed zagrożeniami w usłudze Lookout
Aby umożliwić przygotowanie subskrypcji dla usługi ochrony urządzeń przed zagrożeniami w usłudze Lookout, pomoc techniczna firmy Lookout (enterprisesupport@lookout.com) potrzebuje poniższych informacji na temat subskrypcji usługi Azure Active Directory (Azure AD). Dzierżawa usługi Lookout Mobility Endpoint Security zostanie skojarzona z subskrypcją usługi Azure AD w celu zintegrowania usługi Lookout z usługą Intune. 

* **Identyfikator dzierżawy usługi Azure AD**
* **Identyfikator obiektu grupy usługi Azure AD** dla **pełnego** dostępu do konsoli usługi Lookout
* **Identyfikator obiektu grupy usługi Azure AD** dla **ograniczonego** dostępu do konsoli usługi Lookout (opcjonalnie)

> [!IMPORTANT]
> Nie można użyć istniejącej dzierżawy usługi Lookout Mobile Endpoint Security, która nie została wcześniej skojarzona z dzierżawą usługi Azure AD, w celu integracji z usługami Azure AD i Intune. Skontaktuj się z pomocą techniczną firmy Lookout, aby utworzyć nową dzierżawę usługi Lookout Mobile Endpoint Security. Przy użyciu nowej dzierżawy dodaj użytkowników usługi Azure AD.

Użyj poniższej sekcji w celu zebrania informacji potrzebnych do przekazania zespołowi pomocy technicznej firmy Lookout.  

## <a name="get-your-azure-ad-information"></a>Uzyskiwanie informacji z usługi Azure AD
### <a name="azure-ad-tenant-id"></a>Identyfikator dzierżawy usługi Azure AD
Zaloguj się do [portalu zarządzania usługi Azure AD](https://manage.windowsazure.com) i wybierz swoją subskrypcję. 

![Zrzut ekranu przedstawiający stronę usługi Azure AD z nazwą dzierżawy](../media/mtp/aad_tenant_name.png) Po wybraniu nazwy subskrypcji wynikowy adres URL zawiera identyfikator subskrypcji.  Jeśli masz problemy ze znalezieniem identyfikatora subskrypcji, zobacz ten [artykuł pomocy technicznej firmy Microsoft](https://support.office.com/en-us/article/Find-your-Office-365-tenant-ID-6891b561-a52d-4ade-9f39-b492285e2c9b?ui=en-US&rs=en-US&ad=US), aby uzyskać wskazówki dotyczące znajdowania identyfikatora subskrypcji.   
### <a name="azure-ad-group-id"></a>Identyfikator grupy usługi Azure AD
Konsola usługi Lookout obsługuje 2 poziomy dostępu:  
* **Pełny dostęp:** administrator usługi Azure AD może utworzyć grupę użytkowników, którzy będą mieć pełny dostęp i opcjonalnie utworzyć grupę użytkowników z ograniczonym dostępem.  Tylko użytkownicy z tych grup będą mogli logować się do **konsoli usługi Lookout**.
* **Ograniczony dostęp:** użytkownicy w tej grupie nie będą mieć dostępu do kilku modułów konsoli usługi Lookout związanych z konfiguracją oraz rejestracją i będą mieć dostęp tylko do odczytu do modułu **Security Policy** (Zasady zabezpieczeń) konsoli usługi Lookout.  

Więcej informacji dotyczących uprawnień znajduje się w witrynie sieci Web [w tym artykule](https://personal.support.lookout.com/hc/en-us/articles/114094105653).

**Identyfikator obiektu grupy** można znaleźć na stronie **Właściwości** grupy w **konsoli zarządzania usługi Azure AD**.

![Zrzut ekranu strony właściwości z wyróżnionym polem Identyfikator grupy](../media/mtp/aad_group_object_id.png)

Po zgromadzeniu tych informacji skontaktuj się z pomocą techniczną firmy Lookout (adres e-mail: enterprisesupport@lookout.com).

Pomoc techniczna firmy Lookout wspólnie z główną osobą kontaktową doda subskrypcję i utworzy konto przedsiębiorstwa w usłudze Lookout przy użyciu zebranych wcześniej informacji.


## <a name="configure-your-subscription-with-lookout-device-threat-protection"></a>Konfigurowanie subskrypcji przy użyciu ochrony urządzeń przed zagrożeniami w usłudze Lookout
### <a name="step-1-set-up-your-device-threat-protection"></a>Krok 1. Konfigurowanie ochrony urządzeń przed zagrożeniami w usłudze Lookout
Po utworzeniu konta przedsiębiorstwa przez pomoc techniczną możesz zalogować się do konsoli usługi Lookout.   Do głównej osoby kontaktowej w firmie zostanie wysłana wiadomość e-mail zawierająca link do adresu URL logowania: https://aad.lookout.com/les?action=consent

Podczas pierwszego logowania do konsoli usługi Lookout należy użyć konta użytkownika w roli administratora globalnego usługi Azure AD. Jest to czynność wymagana przez usługę Lookout, aby można było zarejestrować dzierżawę usługi Azure AD.   Kolejne logowanie nie będzie wymagało od użytkownika posiadania tego poziomu uprawnień dla usługi Azure AD.  Podczas pierwszego logowania pojawi się strona zgody użytkownika. Wybierz przycisk **Accept** (Akceptuj) w celu ukończenia rejestracji.

![Zrzut ekranu strony pierwszego logowania do konsoli aplikacji Lookout](../media/mtp/lookout_mtp_initial_login.png) Po zaakceptowaniu i wyrażeniu zgody nastąpi przekierowanie do konsoli usługi Lookout. Po wstępnej rejestracji kolejne logowania można wykonać przy użyciu adresu URL: https://aad.lookout.com

Jeśli wystąpią problemy podczas logowania, zobacz [artykuł na temat rozwiązywania problemów](https://docs.microsoft.com/en-us/intune/troubleshoot/troubleshooting-lookout-integration).

W następnych krokach opisano zadania do wykonania w celu ukończenia konfiguracji usługi Lookout w ramach [konsoli usługi Lookout](https://aad.lookout.com).

### <a name="step-2-configure-the-intune-connector"></a>Krok 2. Konfigurowanie łącznika usługi Intune

1.  W konsoli usługi Lookout w module **System** wybierz kartę **Connectors** (Łączniki), a następnie wybierz pozycję **Intune**.

  ![Zrzut ekranu konsoli usługi Lookout z otwartą kartą łączników i wyróżnioną opcją Intune](../media/mtp/lookout_mtp_setup-intune-connector.png)

2.  W opcji ustawienia połączenia skonfiguruj częstotliwość pulsu w minutach.  Łącznik usługi Intune będzie gotowy.  

  ![Zrzut ekranu przedstawiający kartę ustawień połączenia i skonfigurowaną częstotliwość pulsu](../media/mtp/lookout-mtp-connection-settings.png)

### <a name="step-3-configure-enrollment-groups"></a>Krok 3. Konfigurowanie grup rejestracji
W opcji **Enrollment Management** (Zarządzanie rejestracją) zdefiniuj zestaw użytkowników, których urządzenia powinny być zarejestrowane w usłudze Lookout. Najlepszym rozwiązaniem jest rozpoczęcie testowania od małej grupy użytkowników i zapoznanie się z działaniem integracji.  Jeśli testy okażą się satysfakcjonujące, można rozszerzyć rejestrację o dodatkowe grupy użytkowników.

Aby rozpocząć pracę z grupami rejestracji, należy najpierw zdefiniować grupę zabezpieczeń usługi Azure AD, która może stać się pierwszym zestawem użytkowników do zarejestrowania w usłudze ochrony urządzeń przed zagrożeniami w usłudze Lookout. Po utworzeniu grupy w usłudze Azure AD dla konsoli usługi Lookout przejdź do opcji **Enrollment Management** (Zarządzanie rejestracją) i dodaj grupę zabezpieczeń **Display Name(s)** (Nazwy wyświetlane) usługi Azure AD w celu przeprowadzenia rejestracji.

Jeśli użytkownik znajduje się w grupie rejestracji, wszystkie jego urządzenia, które zostały zidentyfikowane w usłudze Azure AD i są przez nią obsługiwane, są zarejestrowane i uprawnione do aktywacji w usłudze ochrony urządzeń przed zagrożeniami w usłudze Lookout.  Przy pierwszym otwarciu aplikacji Lookout for Work na obsługiwanym urządzeniu jest ono aktywowane w usłudze Lookout.

![Zrzut ekranu strony rejestracji łącznika usługi Intune](../media/mtp/lookout-mtp-enrollment.png)

Najlepszym rozwiązaniem jest użycie domyślnej wartości (5 minut) określającej, ile czasu ma upłynąć między kolejnymi próbami wykrywania nowego urządzenia.

>[!IMPORTANT]
> Wyświetlana nazwa uwzględnia wielkość liter.  Użyj wartości **Nazwa wyświetlana**, jak pokazano na stronie **Właściwości** grupy zabezpieczeń w witrynie Azure Portal. Zwróć uwagę, że na poniższej ilustracji, która przedstawia stronę **Właściwości** grupy zabezpieczeń, wartość Nazwa wyświetlana ma format CamelCase.  Jednak tytuł jest wyświetlany małymi literami i nie powinien być wprowadzany do konsoli usługi Lookout.
>![Zrzut ekranu przedstawiający witrynę Azure Portal, usługę Azure Active Directory i stronę właściwości](../media/mtp/aad-group-display-name.png)

Obecna wersja ma następujące ograniczenia:  
* Nie ma możliwości weryfikacji nazw wyświetlanych grupy.  Upewnij się, że została użyta wartość pola **NAZWA WYŚWIETLANA** widoczna w witrynie Azure Portal dla grupy zabezpieczeń usługi Azure AD.
* Tworzenie grupy w ramach innej grupy nie jest obecnie obsługiwane.  Podane grupy zabezpieczeń usługi Azure AD mogą zawierać tylko użytkowników, a nie grupy zagnieżdżone.


### <a name="step-4-configure-state-sync"></a>Krok 4. Konfigurowanie synchronizacji stanu
W opcji **State Sync** (Synchronizacja stanu) określ typ danych, które powinny być przesyłane do usługi Intune.  Obecnie należy włączyć zarówno stan urządzeń, jak i stan zagrożenia, aby integracja usług Lookout i Intune działała prawidłowo.  Oba są domyślnie włączone.
### <a name="step-5-configure-error-report-email-recipient-information"></a>Krok 5. Konfigurowanie informacji o adresie e-mail odbiorcy raportów o błędach
W opcji **Error Management** (Zarządzanie błędami) wpisz adres e-mail, na który mają być wysyłane raporty o błędach.

![Zrzut ekranu strony zarządzania błędami łącznika usługi Intune](../media/mtp/lookout-mtp-connector-error-notifications.png)

### <a name="step-6-configure-enrollment-settings"></a>Krok 6. Konfigurowanie ustawień rejestracji
W module **System** na stronie **Connectors** (Łączniki) określ liczbę dni, zanim urządzenie zostanie uznane za odłączone.  Odłączone urządzenia są uznawane za niezgodne i nie mają dostępu do aplikacji firmowych zgodnie z zasadami dostępu warunkowego usługi Intune. Można określić wartości z zakresu od 1 do 90 dni.

![](../media/mtp/lookout-console-enrollment-settings.png)

### <a name="step-7-configure-email-notifications"></a>Krok 7. Konfigurowanie powiadomień e-mail
Jeśli chcesz otrzymywać alerty e-mail dotyczące zagrożeń, zaloguj się do [konsoli usługi Lookout](https://aad.lookout.com) przy użyciu konta użytkownika, który powinien otrzymywać powiadomienia. Na karcie **Preferences** (Preferencje) modułu **System** wybierz żądane powiadomienia i ustaw je na wartość **ON** (Włącz). Zapisz zmiany.

![Zrzut ekranu strony preferencji z wyświetlonym kontem użytkownika](../media/mtp/lookout-mtp-email-notifications.png) Jeśli nie chcesz już otrzymywać powiadomień pocztą e-mail, ustaw dla powiadomień wartość **OFF** (Wyłącz) i zapisz zmiany.
### <a name="step-8-configure-threat-classification"></a>Krok 8. Konfigurowanie klasyfikacji zagrożeń
Ochrona urządzeń przed zagrożeniami w usłudze Lookout klasyfikuje różne typy zagrożeń dla urządzeń przenośnych. [Klasyfikacje zagrożeń w usłudze Lookout](http://personal.support.lookout.com/hc/en-us/articles/114094130693) mają domyślne poziomy ryzyka, które są z nimi skojarzone. Można je zmienić w dowolnym momencie zależnie od potrzeb firmy.

![Zrzut ekranu przedstawiający stronę zasad wraz z zagrożeniem i klasyfikacjami](../media/mtp/lookout-mtp-threat-classification.png)

>[!IMPORTANT]
> Określone tutaj poziomy ryzyka są istotnym elementem ochrony urządzeń przed zagrożeniami, ponieważ integracja usługi Intune oblicza zgodność urządzenia na podstawie tych poziomów ryzyka w czasie wykonywania. Innymi słowy administrator usługi Intune ustawia regułę w zasadach, aby uznawać urządzenie za niezgodne, jeśli zawiera ono aktywne zagrożenie, które osiąga poziom ryzyka wysoki, średni lub niski. Obliczanie zgodności urządzenia w usłudze Intune zależy bezpośrednio od zasad klasyfikacji zagrożeń w usłudze ochrony urządzeń przed zagrożeniami w usłudze Lookout.

## <a name="watching-enrollment"></a>Obserwowanie rejestracji
Po zakończeniu konfiguracji usługa ochrony urządzeń przed zagrożeniami w usłudze Lookout rozpoczyna sondowanie usługi Azure AD pod kątem urządzeń, które odpowiadają określonym grupom rejestracji.  Informacje o zarejestrowanych urządzeniach znajdują się w module Devices (Urządzenia).  Początkowy stan urządzeń jest wyświetlany jako oczekujący.  Stan urządzenia ulega zmianie po zainstalowaniu, otwarciu i aktywowaniu aplikacji Lookout for Work na danym urządzeniu.  Aby uzyskać szczegółowe informacje na temat sposobu wypychania aplikacji Lookout for Work do urządzenia, zobacz temat [Configure and deploy Lookout for work apps](configure-and-deploy-lookout-for-work-apps.md) (Konfigurowanie i wdrażanie aplikacji Lookout for Work).
## <a name="next-steps"></a>Następne kroki
[Włączanie połączenia Lookout MTP dla usługi Intune](enable-lookout-mtp-connection-in-intune.md)



<!--HONumber=Nov16_HO1-->


