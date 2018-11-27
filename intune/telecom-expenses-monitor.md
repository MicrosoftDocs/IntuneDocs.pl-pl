---
title: Konfigurowanie usługi Telecom Expense Management
titleSuffix: Microsoft Intune
description: Zintegruj usługę Intune z usługą do zarządzania wydatkami telekomunikacyjnymi firmy Saaswedo.
keywords: Saaswedo
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: b7bf5802-4b65-4aeb-ac99-8e639dd89c2a
ms.reviewer: sumitp
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: b3ca1b95a6dcf7bdc30b61469fa747894d20fe73
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52188096"
---
# <a name="set-up-a-telecom-expense-management-service-in-intune"></a>Konfigurowanie usługi do zarządzania wydatkami telekomunikacyjnymi w usłudze Intune
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Usługa Intune umożliwia zarządzanie wydatkami telekomunikacyjnymi poniesionymi w związku z użyciem danych na urządzeniach przenośnych należących do firmy. W tym celu usługa Intune została zintegrowana z [rozwiązaniem Datalert do zarządzania wydatkami telekomunikacyjnymi](http://datalert.biz/get-started) firmy Saaswedo. Rozwiązanie Datalert to oprogramowanie do zarządzania wydatkami telekomunikacyjnymi w czasie rzeczywistym, które umożliwia zarządzanie danymi dotyczącymi użycia rozwiązań telekomunikacyjnych. Pomaga unikać kosztownych i nieoczekiwanych nadwyżek użycia roamingu na urządzeniach zarządzanych przez usługę Intune.

Integracja usługi Intune z rozwiązaniem Datalert umożliwia centralne ustawianie, monitorowanie i wymuszanie limitów użycia danych w roamingu i połączeniach krajowych. Automatyczne alerty są wyzwalane, gdy limity przekroczą zdefiniowane progi. Możesz skonfigurować usługę tak, aby stosować różne akcje do konkretnych osób lub grup użytkowników końcowych (np. wyłączać funkcję roamingu w przypadku przekroczenia wartości progowej). Raporty, które zawierają informacje dotyczące użycia danych i informacje monitorowania, są dostępne w konsoli zarządzania usługi Datalert.

Na poniższym diagramie przedstawiono sposób, w jaki usługa Intune jest zintegrowana z rozwiązaniem Datalert.

  ![Diagram przedstawiający integrację usług Intune i Datalert](./media/tem-datalert-intune-solution-diagram.png)

Przed rozpoczęciem korzystania z usługi Datalert w usłudze Intune należy skonfigurować ustawienia w konsoli usługi Datalert i w usłudze Intune. Połączenie musi być włączone dla usługi Datalert oraz usługi Intune. Jeśli połączenie po stronie usługi Datalert jest włączone, a nie jest włączone po stronie usługi Intune, usługa Intune odbiera komunikaty, ale je ignoruje.

## <a name="supported-platforms"></a>Obsługiwane platformy

- Samsung Knox
- System iOS 8.0 i nowsze

## <a name="prerequisites"></a>Wymagania wstępne

- Subskrypcja usługi Microsoft Intune i dostęp do witryny Azure Portal.
- Subskrypcja usługi zarządzania wydatkami telekomunikacyjnymi Datalert

## <a name="list-of-telecom-expense-management-providers"></a>Lista dostawców usług zarządzania wydatkami telekomunikacyjnymi

Usługa Intune obecnie obsługuje integrację z następującymi dostawcami usługi zarządzania wydatkami telekomunikacyjnymi:

[Usługa zarządzania wydatkami telekomunikacyjnymi Saaswedo Datalert](http://www.datalert.biz/)

## <a name="deploy-the-intune-and-datalert-integrated-solution"></a>Wdrażanie zintegrowanego rozwiązania usług Intune i Datalert

Przed rozpoczęciem upewnij się, że masz już subskrypcję usług Intune i Datalert.

### <a name="step-1-connect-the-datalert-service-to-microsoft-intune"></a>Krok 1: Połączenie usługi Datalert z usługą Microsoft Intune

1. Zaloguj się do konsoli zarządzania usługi Datalert przy użyciu poświadczeń administratora.

2. W konsoli zarządzania usługi Datalert przejdź do karty **Settings** (Ustawienia), a następnie do pozycji **MDM configuration** (Konfiguracja zarządzania urządzeniami przenośnymi).

3. Wybierz pozycję **Unblock** (Odblokuj) w dolnej części strony, co umożliwi modyfikowanie ustawień na stronie.

4. W sekcji **Intune/Datalert Connection** (Połączenie usługi Intune/Datalert) wybierz pozycję **Microsoft Intune** w obszarze **Server MDM** (Oprogramowanie MDM serwera).    

5. W pozycji **Azure AD domain** (Domena usługi Azure AD) wprowadź identyfikator dzierżawy platformy Azure, a następnie wybierz pozycję **Connection** (Połączenie).

    Wybranie przycisku **Connection** (Połączenie) spowoduje, że usługa Datalert zostanie zewidencjonowana w usłudze Intune, aby uzyskać pewność, że nie istnieją wcześniejsze połączenia usługi Datalert z usługą Intune. Po kilku sekundach zostanie wyświetlona strona logowania firmy Microsoft, po czym nastąpi uwierzytelnienie usługi Datalert na platformie Azure.

6. Na stronie uwierzytelniania firmy Microsoft wybierz opcję **Akceptuj**. Nastąpi przekierowanie do strony **podziękowania** usługi Datalert, która po kilku sekundach zostanie zamknięta. Usługa Datalert zweryfikuje połączenie i wyświetli zielone znaczniki obok zweryfikowanych elementów listy. Jeśli weryfikacja nie powiedzie się, zobaczysz komunikat w kolorze czerwonym. Skontaktuj się z pomocą techniczną firmy Datalert, aby uzyskać pomoc.

    Na poniższym zrzucie ekranu przedstawiono zielone znaczniki wyświetlane po pomyślnym nawiązaniu połączenia.

   ![Strona usługi Datalert przedstawiająca pomyślne nawiązanie połączenia](./media/tem-datalert-connection.png)

7. W sekcji **Datalert App/ADAL Consent** (Zgoda dotycząca aplikacji/biblioteki ADAL usługi Datalert) ustaw przełącznik w położeniu **On** (Wł.). Na stronie uwierzytelniania firmy Microsoft wybierz opcję **Akceptuj**. Nastąpi przekierowanie do strony **podziękowania** usługi Datalert, która po kilku sekundach zostanie zamknięta. Usługa Datalert zweryfikuje połączenie i wyświetli zielone znaczniki obok zweryfikowanych elementów listy. Jeśli weryfikacja nie powiedzie się, zobaczysz komunikat w kolorze czerwonym. Skontaktuj się z pomocą techniczną firmy Datalert, aby uzyskać pomoc.    

    Na poniższym zrzucie ekranu przedstawiono zielone znaczniki wyświetlane po pomyślnym nawiązaniu połączenia.

   ![Strona usługi Datalert przedstawiająca pomyślne nawiązanie połączenia](./media/tem-datalert-adal-consent.png)

8. W sekcji **MDM Profiles management (optional)** (Zarządzanie profilami MDM (opcjonalne)) ustaw przełącznik w położeniu **On** (Wł.), aby odczytywać dostępne profile w usłudze Intune. Ułatwi to konfigurowanie zasad. Na stronie uwierzytelniania firmy Microsoft wybierz opcję **Akceptuj**. Nastąpi przekierowanie do strony **podziękowania** usługi Datalert, która po kilku sekundach zostanie zamknięta. Usługa Datalert zweryfikuje połączenie i wyświetli zielone znaczniki obok zweryfikowanych elementów listy. Jeśli weryfikacja nie powiedzie się, zobaczysz komunikat w kolorze czerwonym. Skontaktuj się z pomocą techniczną firmy Datalert, aby uzyskać pomoc.    

    Na poniższym zrzucie ekranu przedstawiono zielone znaczniki wyświetlane po pomyślnym nawiązaniu połączenia.

   ![Strona usługi Datalert przedstawiająca pomyślne nawiązanie połączenia](./media/tem-datalert-mdm-profiles.png)

### <a name="step-2-check-that-the-telecom-expense-management-feature-is-active-in-intune"></a>Krok 2: Sprawdzenie, czy funkcja zarządzania wydatkami telekomunikacyjnymi jest aktywna w usłudze Intune

Po wykonaniu kroku 1 połączenie powinno zostać automatycznie włączone, a w witrynie Azure Portal stan połączenia powinien być wyświetlany jako **Aktywne**. W tych krokach wyjaśniono, jak sprawdzić, czy połączenie jest **aktywne**.

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).

2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.

3. W okienku **Intune** wybierz pozycję **Konfiguracja urządzeń**.

4. W okienku **Konfiguracja urządzeń** wybierz pozycję **Instalacja** > **Telecom Expense Management**.

   Odszukaj stan połączenia **Aktywne** w górnej części strony.

   ![Strona usługi Intune przedstawiająca stan połączenia usługi Datalert jako Aktywne](./media/tem-azure-portal-enable-service.png)

### <a name="step-3-deploy-the-datalert-app-to-corporate-enrolled-devices"></a>Krok 3: Wdrożenie aplikacji Datalert na urządzeniach zarejestrowanych przez firmę

Aby upewnić się, że zbierane jest tylko użycie danych z urządzeń należących do firmy, musisz wykonać dwie czynności:
- utworzyć kategorie urządzeń w usłudze Intune,
- ukierunkować aplikację Datalert tak, aby jej celem były tylko firmowe telefony.

#### <a name="define-device-categories-and-device-groups-mapped-to-the-categories"></a>Definiowanie kategorii urządzeń i grup urządzeń mapowanych na kategorie

W zależności od potrzeb organizacji należy utworzyć co najmniej dwie kategorie urządzeń (na przykład Firmowe i Osobiste). Następnie należy utworzyć dynamiczne grupy urządzeń dla każdej kategorii. W razie potrzeby możesz utworzyć więcej kategorii.

Te kategorie będą wyświetlane użytkownikom podczas rejestrowania. W zależności od wybranej kategorii zarejestrowane urządzenie zostanie przeniesione do odpowiedniej grupy urządzeń. Aby dowiedzieć się, jak utworzyć kategorie urządzeń, zobacz [Mapowanie urządzeń na grupy](device-group-mapping.md).

  ![Zrzut ekranu przedstawiający okienko Dodawanie zasad](./media/tem-dynamic-membership-rules.png)

#### <a name="create-the-datalert-app-in-intune"></a>Tworzenie aplikacji Datalert w usłudze Intune

Wykonaj następujące czynności, aby utworzyć aplikację Datalert w usłudze Intune dla każdej z platform. Jako przykład użyto systemu iOS.

1. W okienku **Intune** witryny [Azure Portal](https://portal.azure.com) wybierz pozycję **Aplikacje klienckie**.

2. W okienku **Aplikacje klienckie** wybierz pozycję **Zarządzanie** > **Aplikacje**.

3. Wybierz pozycję **Dodaj**, aby dodać aplikację.

4. Wybierz typ aplikacji. Przykładowo w przypadku systemu iOS należy wybrać pozycję **Sklep z aplikacjami dla systemu iOS**.

5. W obszarze **Wyszukaj w sklepie App Store** odszukaj aplikację Datalert, wpisując **Datalert** w oknie wyszukiwania.

6. Wybierz aplikację **Datalert** i opcję **Wybierz**.

   ![Zrzut ekranu przedstawiający okienko Dodawanie zasad](./media/tem-select-app-from-apple-app-store.png)

7. Wykonaj pozostałe czynności, aby utworzyć aplikację dla systemu iOS.

   ![Zrzut ekranu przedstawiający okienko Dodawanie zasad](./media/tem-steps-to-create-the-app.png)

#### <a name="assign-the-datalert-app-to-the-corporate-device-group"></a>Przypisanie aplikacji Datalert do grupy urządzeń firmowych

1. W okienku **Aplikacje klienckie— Aplikacje** wybierz aplikację Datalert dla systemu iOS utworzoną w poprzednim kroku.

2. W okienku **Aplikacje** wybierz pozycję **Zarządzaj** > **Przypisania**.

3. Wybierz pozycję **Dodaj grupę** i postępuj zgodnie z instrukcjami, aby wybrać grupę urządzeń firmowych.

4. Wybierz, czy zainstalowanie aplikacji dla grupy ma być wymagane, czy opcjonalne. Na poniższym przykładowym zrzucie ekranu instalacja jest wymagana, co oznacza, że użytkownicy muszą zainstalować aplikację Datalert po zarejestrowaniu urządzenia.

   ![Zrzut ekranu przedstawiający okienko Dodawanie zasad](./media/tem-assign-datalert-app-to-device-group.png)

### <a name="step-4-add-corporate-paid-phone-lines-to-the-datalert-console"></a>Krok 4: Dodanie firmowych płatnych linii telefonicznych do konsoli usługi Datalert

Usługi Intune i Datalert zostały skonfigurowane i mogą się ze sobą komunikować. Teraz należy dodać firmowe płatne linie telefoniczne do konsoli usługi Datalert oraz zdefiniować progi i akcje dla każdego naruszenia użycia połączeń komórkowych lub roamingu. Można firmowe płatne linie telefoniczne dodać do konsoli Datalert ręcznie lub dodać je automatycznie po zarejestrowaniu urządzenia w usłudze Intune.

Aby ustawić te elementy, przejdź do strony [Konfigurowanie usługi Datalert na potrzeby usługi Microsoft Intune](http://www.datalert.fr/microsoft-intune/intune-setup) (http://www.datalert.fr/microsoft-intune/intune-setup)) i postępuj zgodnie z instrukcjami kreatora konfiguracji na karcie **Ustawienia**.

  ![Zrzut ekranu przedstawiający okienko Dodawanie zasad](./media/tem-add-phone-lines-to-datalert-console.png)


Usługa Datalert jest teraz aktywna i rozpoczyna monitorowanie użycia danych oraz wyłączanie danych sieci komórkowej i roamingu na urządzeniach, które przekraczają skonfigurowane limity użycia.

## <a name="client-enrollment-experience"></a>Środowisko rejestracji klienta
Informacje na temat środowiska rejestracji klienta zawierają następujące tematy:
-   [Rejestrowanie urządzenia z systemem iOS w rozwiązaniu do zarządzania wydatkami telekomunikacyjnymi](https://docs.microsoft.com/intune-user-help/enroll-your-device-with-telecom-expense-management-ios)
-   [Rejestrowanie urządzenia z systemem Android w rozwiązaniu do zarządzania wydatkami telekomunikacyjnymi](https://docs.microsoft.com/intune-user-help/enroll-your-device-with-telecom-expense-management-android)

## <a name="turning-off-the-datalert-service"></a>Wyłączanie usługi Datalert

Po wyłączeniu usługi Datalert w portalu Azure Portal:

- Wszystkie akcje, które zostały zastosowane do urządzeń z powodu naruszenia limitów użycia, zostaną cofnięte.
- Dostęp użytkowników do danych i roamingu nie będzie zablokowany.
- Usługa Intune nadal będzie odbierać sygnały pochodzące z usługi, ale będzie je ignorować.

**Aby wyłączyć usługę**

1. W okienku **Telecom Expense Management** w portalu Azure Portal wybierz pozycję **Wyłącz**.

2. Wybierz pozycję **Zapisz**.

## <a name="viewing-data-usage-and-roaming-reports"></a>Wyświetlanie raportów dotyczących użycia danych i roamingu

W tej chwili funkcja raportowania użycia danych jest dostępna tylko w konsoli zarządzania usługi Datalert firmy Saaswedo.

Instrukcje dla użytkowników końcowych dotyczące instalowania aplikacji Datalert zostaną dodane wkrótce.
