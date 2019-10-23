---
title: Konfigurowanie usługi zarządzania wydatkami telekomunikacyjnymi w usłudze Microsoft Intune — Azure | Microsoft Docs
titleSuffix: ''
description: Zintegruj usługę Microsoft Intune z usługą zarządzania wydatkami telekomunikacyjnymi Saaswedo w celu monitorowania użycia danych oraz ustawiania progów lub limitów na urządzeniach z systemem Android i iOS.
keywords: Saaswedo
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/09/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: b7bf5802-4b65-4aeb-ac99-8e639dd89c2a
ms.reviewer: sumitp
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ce9a6916cc77714a87aeac33555c0be1e59463f5
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72506631"
---
# <a name="set-up-a-telecom-expense-management-service-in-intune"></a>Konfigurowanie usługi do zarządzania wydatkami telekomunikacyjnymi w usłudze Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Za pomocą usługi Intune można zarządzać wydatkami telekomunikacyjnymi związanymi z użyciem danych na urządzeniach przenośnych należących do organizacji. Usługa Intune integruje się z [usługą do zarządzania wydatkami telekomunikacyjnymi Datalert](http://datalert.biz/get-started) firmy Saaswedo. Datalert to rozwiązanie do zarządzania wydatkami telekomunikacyjnymi w czasie rzeczywistym, które umożliwia zarządzanie użyciem danych telekomunikacyjnych. Pomaga unikać kosztownych i nieoczekiwanych opłat za użycie danych i roamingu na urządzeniach zarządzanych przez usługę Intune.

Integracja z rozwiązaniem Datalert umożliwia ustawianie, monitorowanie i wymuszanie limitów użycia danych w ramach roamingu i połączeń krajowych. Gdy limity przekroczą zdefiniowane progi, alerty są wyzwalane automatycznie. Możesz również skonfigurować usługę tak, aby stosować różne akcje, np. wyłączenie funkcji roamingu po przekroczeniu wartości progowej, do konkretnych osób lub grup. Konsola zarządzania usługi Datalert obejmuje raporty zawierające informacje dotyczące użycia i monitorowania danych.

Na poniższym obrazie przedstawiono sposób, w jaki usługa Intune jest zintegrowana z rozwiązaniem Datalert:

  ![Diagram przedstawiający integrację usług Intune i Datalert](./media/telecom-expenses-monitor/tem-datalert-intune-solution-diagram.png)

Aby korzystanie z usługi Datalert w usłudze Intune było możliwe, w usługach Datalert i Intune istnieją pewne ustawienia konfiguracji. W tym artykule wyjaśniono, jak:

- Skonfigurować ustawienia w konsoli usługi Datalert, aby połączyć usługę Datalert z usługą Intune.
- Sprawdzić, czy to połączenie jest aktywne i włączone w usłudze Intune.
- Użyć usługi Intune, aby dodać aplikację Datalert do swoich urządzeń.
- Wyłączyć usługi Datalert oraz Intune (opcjonalnie).

## <a name="supported-platforms"></a>Obsługiwane platformy

- Urządzenia z systemem Android 4.4 i nowszym, które obsługują rozwiązanie Knox (Samsung)

  [Lista wersji systemu Android obsługujących rozwiązanie Knox](https://seap.samsung.com/faq/what-versions-android-support-knox-standard-and-knox-premium-sdks-0) znajduje się w witrynie internetowej firmy Samsung.

- System iOS 8.0 i nowsze

## <a name="prerequisites"></a>Wymagania wstępne

- Subskrypcja usługi Microsoft Intune i dostęp do witryny [Azure Portal](https://portal.azure.com)
- Subskrypcja usługi [Datalert](http://www.datalert.biz/) (link do witryny internetowej usługi Datalert)

## <a name="telecom-expense-management-providers"></a>Dostawcy usług zarządzania wydatkami telekomunikacyjnymi

Usługa Intune obsługuje integrację z następującym dostawcą usługi zarządzania wydatkami telekomunikacyjnymi:

- [Usługi zarządzania wydatkami telekomunikacyjnymi Datalert firmy Saaswedo](http://www.datalert.biz/) (link do witryny internetowej usługi Datalert)

## <a name="deploy-the-intune-and-datalert-solution"></a>Wdrażanie rozwiązania usług Intune i Datalert

### <a name="step-1-connect-the-datalert-service-to-intune"></a>Krok 1. Połączenie usługi Datalert z usługą Intune

1. Zaloguj się do konsoli zarządzania usługi Datalert przy użyciu poświadczeń administratora.

2. W konsoli przejdź do karty **Ustawienia** > **Konfiguracja oprogramowania MDM**.

3. Wybierz opcję **Odblokuj**. Opcja **Odblokuj** pozwala zmienić lub zaktualizować ustawienia na stronie.

4. W sekcji **Intune/Datalert Connection** (Połączenie usługi Intune/Datalert) > **Server MDM** (Serwer MDM) wybierz opcję **Microsoft Intune**.

5. W pozycji **Azure AD domain** (Domena usługi Azure AD) wprowadź identyfikator dzierżawy platformy Azure. Wybierz pozycję **Połączenie**.

    Wybranie opcji **Połączenie** usługa Datalert zostaje zaewidencjonowana w usłudze Intune. Potwierdza, że nie ma żadnych istniejących połączeń usługi Datalert. Po chwili zostanie wyświetlona strona logowania firmy Microsoft, po czym nastąpi uwierzytelnianie usługi Datalert na platformie Azure.

6. Na stronie uwierzytelniania firmy Microsoft wybierz opcję **Akceptuj**.

    Nastąpi przekierowanie do strony **podziękowania** usługi Datalert, która po chwili zostanie zamknięta. Usługa Datalert zweryfikuje połączenie i wyświetli zielone znaczniki wyboru obok zweryfikowanych elementów. Jeśli sprawdzanie poprawności zakończy się niepowodzeniem, zostanie wyświetlony komunikat w kolorze czerwonym. Skontaktuj się z pomocą techniczną usługi Datalert w celu uzyskania pomocy.

    Na poniższym obrazie przedstawiono zielone znaczniki wyboru, które pojawiają się w przypadku pomyślnego nawiązania połączenia:

      ![Strona usługi Datalert przedstawiająca pomyślne nawiązanie połączenia](./media/telecom-expenses-monitor/tem-datalert-connection.png)

7. W sekcji **Datalert App/ADAL Consent** (Zgoda dotycząca aplikacji/biblioteki ADAL usługi Datalert) ustaw przełącznik w położeniu **On** (Wł.). Na stronie uwierzytelniania firmy Microsoft wybierz opcję **Akceptuj**.

    Nastąpi przekierowanie do strony **podziękowania** usługi Datalert, która po chwili zostanie zamknięta. Usługa Datalert zweryfikuje połączenie i wyświetli zielone znaczniki wyboru obok zweryfikowanych elementów. Jeśli sprawdzanie poprawności zakończy się niepowodzeniem, zostanie wyświetlony komunikat w kolorze czerwonym. Skontaktuj się z pomocą techniczną usługi Datalert w celu uzyskania pomocy.

    Na poniższym obrazie przedstawiono zielone znaczniki wyboru, które pojawiają się w przypadku pomyślnego nawiązania połączenia:

      ![Strona usługi Datalert przedstawiająca pomyślne nawiązanie połączenia](./media/telecom-expenses-monitor/tem-datalert-adal-consent.png)

8. W sekcji **MDM Profiles management (optional)** [Zarządzanie profilami MDM (opcjonalne)] ustaw przełącznik w położeniu **On** (Wł.). To ustawienie umożliwia usłudze Datalert odczytywanie dostępnych profilów w usłudze Intune w celu ułatwienia konfigurowania zasad. 

    Na stronie uwierzytelniania firmy Microsoft wybierz opcję **Akceptuj**.

    Nastąpi przekierowanie do strony **podziękowania** usługi Datalert, która po chwili zostanie zamknięta. Usługa Datalert zweryfikuje połączenie i wyświetli zielone znaczniki wyboru obok zweryfikowanych elementów. Jeśli sprawdzanie poprawności zakończy się niepowodzeniem, zostanie wyświetlony komunikat w kolorze czerwonym. Skontaktuj się z pomocą techniczną usługi Datalert w celu uzyskania pomocy.

    Na poniższym obrazie przedstawiono zielone znaczniki wyboru, które pojawiają się w przypadku pomyślnego nawiązania połączenia:

   ![Strona usługi Datalert przedstawiająca pomyślne nawiązanie połączenia](./media/telecom-expenses-monitor/tem-datalert-mdm-profiles.png)

### <a name="step-2-confirm-telecom-expense-management-is-active-in-intune"></a>Krok 2: Potwierdzenie aktywności funkcji zarządzania wydatkami telekomunikacyjnymi w usłudze Intune

Po wykonaniu kroku 1 połączenie zostanie automatycznie włączone. W usłudze Intune stanem połączenia jest **Aktywny**. Aby potwierdzić, że stan jest aktywny, wykonaj następujące czynności:

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).

2. Wybierz kolejno pozycje **Konfiguracja urządzenia** > **Zarządzanie wydatkami telekomunikacyjnymi**. Odszukaj stan połączenia **Aktywne**:

   ![Strona usługi Intune przedstawiająca stan połączenia usługi Datalert jako Aktywne](./media/telecom-expenses-monitor/tem-azure-portal-enable-service.png)

### <a name="step-3-deploy-the-datalert-app-to-devices"></a>Krok 3: Wdrożenie aplikacji Datalert na urządzeniach

Aby potwierdzić, że zbierane są dane dotyczące użycia tylko z wierszy należących do organizacji, pamiętaj, aby:

- utworzyć kategorie urządzeń w usłudze Intune;
- ukierunkować aplikację Datalert tak, aby jej celem były tylko telefony organizacji.

Niniejsza sekcja zawiera listę tych kroków.

#### <a name="create-device-categories-and-device-groups-mapped-to-your-categories"></a>Utworzyć kategorie urządzeń i grupy urządzeń mapowane na kategorie

W zależności od potrzeb organizacji należy utworzyć co najmniej dwie kategorie urządzeń, na przykład Firmowe i Osobiste. Następnie należy utworzyć dynamiczne grupy urządzeń dla każdej kategorii. W razie potrzeby możesz utworzyć więcej kategorii.

Aby dowiedzieć się, jak utworzyć kategorie urządzeń w usłudze Intune, zobacz temat dotyczący [mapowania urządzeń na grupy](../enrollment/device-group-mapping.md).

Te kategorie są widoczne dla użytkowników podczas rejestracji ([Enroll Android Devices](../enrollment/android-enroll.md) [Rejestrowanie urządzeń z systemem Android]). W zależności od wybranej kategorii zarejestrowane urządzenie zostanie przeniesione do odpowiedniej grupy urządzeń.

  ![Zrzut ekranu przedstawiający okienko Dodawanie zasad](./media/telecom-expenses-monitor/tem-dynamic-membership-rules.png)

#### <a name="add-the-datalert-app-to-intune"></a>Dodawanie aplikacji Datalert do usługi Intune

Następujące czynności powodują dodanie aplikacji Datalert. Na przykład jest używany system iOS. Bardziej szczegółowe informacje dotyczące tych czynności znajdują się w tematach dotyczących [dodawania aplikacji](../apps/apps-add.md) oraz [użycia tagów zakresu](../fundamentals/scope-tags.md).

1. W sekcji **[Intune](https://go.microsoft.com/fwlink/?linkid=2090973)** wybierz pozycje **Aplikacje klienckie** > **Aplikacje** > **Dodaj**.

2. Wybierz pozycję **Typ aplikacji**. Na przykład dla systemu iOS wybierz pozycję **Aplikacja ze sklepu — iOS**.

3. W polu **Wyszukaj w sklepie App Store** wpisz **Datalert**, aby znaleźć aplikację Datalert.

4. Wybierz aplikację **Datalert** > **Wybierz**:

   ![Dodawanie aplikacji Datalert ze sklepu z aplikacjami do aplikacji klienckich usługi Intune](./media/telecom-expenses-monitor/tem-select-app-from-apple-app-store.png)

5. Wprowadź wszelkie dodatkowe właściwości, takie jak informacje o aplikacji i tagi zakresu:

   ![Wprowadź właściwości aplikacji, w tym nazwę, opis, wybierz system operacyjny i więcej ustawień aplikacji w usłudze Intune](./media/telecom-expenses-monitor/tem-steps-to-create-the-app.png)

6. Wybierz przyciski **OK** > **Dodaj**, aby zapisać zmiany. Aplikacja Datalert zostanie wyświetlona na liście.

#### <a name="assign-the-datalert-app-to-the-corporate-device-group"></a>Przypisanie aplikacji Datalert do grupy urządzeń firmowych

1. W sekcji **Client apps — Apps** (Aplikacje klienckie — aplikacje) wybierz aplikację Datalert dodaną w poprzednim kroku.

2. Wybierz pozycje **Przypisania** > **Dodaj grupę**. Wybierz sposób przypisywania aplikacji. Więcej szczegółowych informacji dotyczących tych ustawień znajduje się w temacie [Assign apps to groups in Intune](../apps/apps-deploy.md) (Przypisywanie aplikacji do grup w usłudze Intune).

    W tych krokach zdecydujesz, czy zainstalowanie aplikacji dla grupy ma być wymagane, czy opcjonalne. W poniższym przykładzie przedstawiono instalację zgodnie z wymaganiami. Jeśli jest to wymagane, użytkownicy muszą zainstalować aplikację Datalert po zarejestrowaniu urządzenia.

   ![Zrzut ekranu przedstawiający okienko Dodawanie zasad](./media/telecom-expenses-monitor/tem-assign-datalert-app-to-device-group.png)

### <a name="step-4-add-organization-phone-lines-to-the-datalert-console"></a>Krok 4. Dodanie linii telefonicznych organizacji do konsoli usługi Datalert

Usługi Intune i Datalert zostały skonfigurowane i mogą się ze sobą komunikować. Następnie dodaj płatne linie telefoniczne organizacji do konsoli Datalert. Wprowadź wartości progowe i akcje dla wszelkich naruszeń użycia sieci komórkowej lub mobilnej. Firmowe płatne linie telefoniczne można dodać do konsoli Datalert ręcznie lub automatycznie po zarejestrowaniu urządzenia w usłudze Intune.

Aby ustawić te elementy, przejdź do sekcji [Datalert setup for Microsoft Intune](http://www.datalert.fr/microsoft-intune/intune-setup) (Konfiguracja usługi Datalert w usłudze Microsoft Intune; link do witryny internetowej usługi Datalert). W obszarze karty **Ustawienia** postępuj zgodnie z instrukcjami kreatora konfiguracji.

  ![Zrzut ekranu przedstawiający okienko Dodawanie zasad](./media/telecom-expenses-monitor/tem-add-phone-lines-to-datalert-console.png)

Usługa Datalert jest teraz aktywna. Rozpoczyna monitorowanie użycia danych oraz wyłączanie danych sieci komórkowej i roamingu na urządzeniach, które przekraczają skonfigurowane limity użycia.

## <a name="end-user-enrollment"></a>Rejestrowanie przez użytkownika końcowego

W odniesieniu do środowiska użytkownika końcowego mogą być przydatne następujące artykuły:

- [Rejestrowanie urządzenia z systemem iOS w rozwiązaniu do zarządzania wydatkami telekomunikacyjnymi](https://docs.microsoft.com/intune-user-help/enroll-your-device-with-telecom-expense-management-ios)
- [Rejestrowanie urządzenia z systemem Android w rozwiązaniu do zarządzania wydatkami telekomunikacyjnymi](https://docs.microsoft.com/intune-user-help/enroll-your-device-with-telecom-expense-management-android)

## <a name="turn-off-the-datalert-service"></a>Wyłączanie usługi Datalert

1. W sekcji **[Intune](https://go.microsoft.com/fwlink/?linkid=2090973)** wybierz pozycje **Konfiguracja urządzeń** > **Zarządzanie wydatkami telekomunikacyjnymi**.
2. Ustaw opcję **Enable Telecom Expense Management and block cellular or roaming data on devices that exceed usage quotas you configure** (Włącz zarządzanie wydatkami telekomunikacyjnymi i blokuj dane sieci komórkowych lub mobilnych na urządzeniach, które przekraczają skonfigurowane limity przydziału użycia) w położeniu **Wyłącz**.
3. **Zapisz** zmiany.

> [!IMPORTANT]
> Po wyłączeniu usługi Datalert w usłudze Intune:
>
> - Wszystkie akcje, które zostały zastosowane do urządzeń z powodu naruszenia limitów użycia, zostaną cofnięte.
> - Dostęp użytkowników do danych i roamingu nie będzie zablokowany.
> - Usługa Intune nadal będzie odbierać sygnały pochodzące z usługi, ale będzie je ignorować.

## <a name="next-steps"></a>Następne kroki

Funkcja raportowania użycia danych jest dostępna w konsoli zarządzania usługi Datalert firmy Saaswedo.
