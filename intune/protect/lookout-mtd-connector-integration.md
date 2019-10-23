---
title: Konfigurowanie integracji usługi Lookout za pomocą usługi Microsoft Intune
titleSuffix: Microsoft Intune
description: Dowiedz się więcej na temat integracji usługi Intune z usługą Lookout Mobile Endpoint Security jako rozwiązaniem usługi Mobile Threat Defense w celu kontrolowania dostępu urządzeń przenośnych do zasobów firmy.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/11/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5b0d7644-3183-45ba-a165-0d82d70cb71e
ms.reviewer: davera
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b61281b0e82bcb839efdc31726d398eea08c364f
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72502192"
---
# <a name="set-up-lookout-mobile-endpoint-security-integration-with-intune"></a>Konfigurowanie integracji usługi Lookout Mobile Endpoint Security z usługą Intune
Jeśli środowisko spełnia [wymagania wstępne](lookout-mobile-threat-defense-connector.md#prerequisites), można zintegrować usługę Lookout Mobile Endpoint Security z usługą Intune. Informacje przedstawione w tym artykule ułatwią skonfigurowanie integracji oraz ważnych ustawień w usłudze Lookout do użycia z usługą Intune.  

> [!IMPORTANT]
> Nie można użyć istniejącej dzierżawy usługi Lookout Mobile Endpoint Security, która nie została wcześniej skojarzona z dzierżawą usługi Azure AD, w celu integracji z usługami Azure AD i Intune. Skontaktuj się z pomocą techniczną firmy Lookout, aby utworzyć nową dzierżawę usługi Lookout Mobile Endpoint Security. Przy użyciu nowej dzierżawy dodaj użytkowników usługi Azure AD.

## <a name="collect-azure-ad-information"></a>Zbieranie informacji z usługi Azure AD  
Aby zintegrować usługę Lookout z usługą Intune, należy skojarzyć dzierżawę usługi Lookout Mobility Endpoint Security z subskrypcją usługi Azure Active Directory (AD).

Aby włączyć integrację subskrypcji usługi Lookout Mobile Endpoint Security z usługą Intune, podaj następujące informacje zespołowi pomocy technicznej firmy Lookout (enterprisesupport@lookout.com):  

- **Identyfikator katalogu dzierżawy usługi Azure AD**  

- **Identyfikator obiektu grupy usługi Azure AD** dla grupy z **pełnym** dostępem do konsoli usługi Lookout Mobile Endpoint Security (MES).  
  Ta grupa użytkowników jest tworzona w usłudze Azure AD i zawiera użytkowników, którzy mają *pełny dostęp* do logowania się do **konsoli usługi Lookout**. Użytkownicy muszą być członkami tej grupy lub opcjonalnej grupy z *ograniczonym dostępem*, aby logować się do konsoli usługi Lookout. 

- **Identyfikator obiektu grupy usługi Active AD** dla grupy z **ograniczonym** dostępem do konsoli usługi Lookout MES *(grupa opcjonalna)* . 
  Ta opcjonalna grupa użytkowników jest tworzona w usłudze Azure AD i zawiera użytkowników, którzy nie powinni mieć dostępu do kilku modułów konsoli usługi Lookout powiązanych z konfiguracją i rejestracją. W zamian użytkownicy ci mają dostęp tylko do odczytu do modułu **zasad zabezpieczeń** konsoli usługi Lookout. Użytkownicy muszą być członkami tej opcjonalnej grupy lub wymaganej grupy z *pełnym dostępem*, aby logować się do konsoli usługi Lookout.

 > [!TIP] 
 > Więcej informacji dotyczących uprawnień znajduje się w witrynie sieci Web [w tym artykule](https://personal.support.lookout.com/hc/articles/114094105653).

### <a name="collect-information-from-azure-ad"></a>Zbieranie informacji z usługi Azure AD 

1. Zaloguj się do witryny [Azure Portal](https://portal.azure.com) przy użyciu konta administratora globalnego.

2. Przejdź do obszaru **Azure Active Directory** > **Właściwości** i znajdź swój **identyfikator katalogu**. Użyj przycisku *kopiowania*, aby skopiować identyfikator katalogu, a następnie zapisz go w pliku tekstowym.

   ![Właściwości usługi Azure AD](./media/lookout-mtd-connector-integration/azure-ad-properties.png)  

3. Następnie znajdź identyfikator grupy usługi Azure AD dla kont, których używasz do udzielania użytkownikom usługi Azure AD dostępu do konsoli usługi Lookout. Jedna grupa ma *pełny dostęp*, a druga grupa z *ograniczonym dostępem* jest opcjonalna. Aby uzyskać *identyfikator obiektu* dla każdego konta:  
   1. Przejdź do obszaru **Azure Active Directory** > **Grupy**, aby otworzyć okienko *Grupy — wszystkie grupy*.  

   2. Wybierz utworzoną grupę z *pełnym dostępem*, aby otworzyć okienko jej *omówienia*.  

   3. Użyj przycisku *kopiowania*, aby skopiować identyfikator obiektu, a następnie zapisz go w pliku tekstowym.  

   4. Powtórz proces dla grupy z *ograniczonym dostępem*, jeśli z niej korzystasz.  

      ![Identyfikator obiektu grupy usługi Azure AD](./media/lookout-mtd-connector-integration/azure-ad-group-id.png)  

   Po zebraniu tych informacji skontaktuj się z zespołem pomocy technicznej firmy Lookout (adres e-mail: enterprisesupport@lookout.com). Pomoc techniczna firmy Lookout wspólnie z główną osobą kontaktową doda subskrypcję i utworzy konto usługi Lookout Enterprise przy użyciu podanych wcześniej informacji.  

## <a name="configure-your-lookout-subscription"></a>Konfigurowanie subskrypcji usługi Lookout  
Po utworzeniu przez zespół pomocy technicznej firmy Lookout konta usługi Lookout Enterprise zespół ten wysyła do głównej osoby kontaktowej w firmie wiadomość e-mail zawierającą link do adresu URL logowania: https://aad.lookout.com/les?action=consent. 

### <a name="initial-sign-in"></a>Logowanie początkowe  
Podczas pierwszego logowania do konsoli usługi Lookout MES jest wyświetlana strona wyrażania zgody (https://aad.lookout.com/les?action=consent). Wystarczy zalogować się jako administrator globalny usługi Azure AD i wybrać pozycję **Akceptuj**. Kolejne logowanie nie wymaga od użytkownika posiadania tego poziomu uprawnień dla usługi Azure AD. 

 Zostanie wyświetlona strona zgody użytkownika. Wybierz przycisk **Accept** (Akceptuj) w celu ukończenia rejestracji. 
   ![zrzut ekranu przedstawiający stronę pierwszego logowania konsoli usługi Lookout](./media/lookout-mtd-connector-integration/lookout_mtp_initial_login.png)

Podczas zaakceptowaniu i wyrażeniu zgody nastąpi przekierowanie do konsoli usługi Lookout.

Po zakończeniu logowania początkowego i wyrażeniu zgody użytkownicy, którzy logują się w witrynie https://aad.lookout.com, są przekierowywani do konsoli usługi MES. Do momentu wyrażenia zgody wszystkie próby logowania będą powodować wystąpienie błędu nieprawidłowego logowania.

### <a name="configure-the-intune-connector"></a>Konfigurowanie łącznika usługi Intune  
W poniższej procedurze przyjęto, że wcześniej utworzono w usłudze Azure AD grupę użytkowników na potrzeby testowania wdrożenia aplikacji Lookout. Najlepszym rozwiązaniem jest rozpoczęcie od małej grupy użytkowników, co umożliwi administratorom usług Lookout i Intune zapoznanie się z procesami integracji produktów. Gdy już je poznają, będzie można rozszerzyć rejestrację o dodatkowe grupy użytkowników.

1. Zaloguj się do [konsoli usługi Lookout MES](https://aad.lookout.com) i przejdź do pozycji **System** > **Connectors** (System > Łączniki), a następnie wybierz pozycję **Add Connector** (Dodaj łącznik).  Wybierz pozycję **Intune**.

   ![Obraz przedstawiający konsolę usługi Lookout z opcją Intune na karcie Connectors (Łączniki)](./media/lookout-mtd-connector-integration/lookout_mtp_setup-intune-connector.png)

2. W okienku *Microsoft Intune* wybierz pozycję **Connection Settings** (Ustawienia połączeń) i określ wartość **Heartbeat Frequency** (Częstotliwość pulsu) w minutach. 

   ![Obraz przedstawiający kartę ustawień połączenia ze skonfigurowaną częstotliwością pulsu](./media/lookout-mtd-connector-integration/lookout-mtp-connection-settings.png)

3. Wybierz pozycję **Enrollment Management** (Zarządzanie rejestracją), w polu **Use the following Azure AD security groups to identify devices that should be enrolled in Lookout for Work** (Użyj następujących grup zabezpieczeń usługi Azure AD do identyfikowania urządzeń do zarejestrowania w aplikacji Lookout for Work) podaj *nazwę grupy* usługi Azure AD do użycia z usługą Lookout, a następnie wybierz przycisk **Save changes** (Zapisz zmiany).

    ![Zrzut ekranu strony rejestracji łącznika usługi Intune](./media/lookout-mtd-connector-integration/lookout-mtp-enrollment.png)  

   **Informacje na temat używanych grup**:
   - Najlepszym rozwiązaniem jest rozpoczęcie od grupy zabezpieczeń usługi Azure AD zawierającej małą liczbę użytkowników na potrzeby testowania integracji z usługą Lookout.
   - **Nazwa grupy** uwzględnia wielkość liter, jak pokazano w obszarze **Właściwości** grupy zabezpieczeń w witrynie Azure Portal.  
   - Grupy wybrane w obszarze **Enrollment Management** (Zarządzanie rejestracją) definiują zestaw użytkowników, których urządzenia zostaną zarejestrowane w usłudze Lookout. Jeśli użytkownik znajduje się w grupie rejestracji, jego urządzenia w usłudze Azure AD, są rejestrowane i uprawnione do aktywacji w usłudze Lookout MES. Gdy użytkownik po raz pierwszy otworzy aplikację *Lookout for Work* na obsługiwanym urządzeniu, zostanie wyświetlony monit o jej uaktywnienie.

4. Wybierz pozycję **State Sync** (Synchronizacja stanu) i upewnij się, że *stan urządzenia* i *stan zagrożenia* zostały ustawione na **On** (Włącz).  Do prawidłowego działania integracji usług Lookout i Intune są wymagane obydwa te stany.  

5. Wybierz pozycję **Error Management** (Zarządzanie błędami), określ adres e-mail, który powinien otrzymywać raporty o błędach, a następnie wybierz przycisk **Save changes** (Zapisz zmiany).
 
   ![Zrzut ekranu strony zarządzania błędami łącznika usługi Intune](./media/lookout-mtd-connector-integration/lookout-mtp-connector-error-notifications.png)

6. Wybierz pozycję **Create connector** (Utwórz łącznik), aby ukończyć konfigurowanie łącznika. Jeśli wyniki są satysfakcjonujące, można później rozszerzyć rejestrację na dodatkowe grupy użytkowników.

## <a name="configure-intune-to-use-lookout-as-a-mobile-threat-defense-provider"></a>Konfigurowanie usługi Intune do używania aplikacji Lookout jako dostawcy usługi Mobile Threat Defense
Po skonfigurowaniu usługi Lookout MES należy skonfigurować połączenie usługi Lookout w usłudze Intune.  

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).

2. Przejdź do pozycji **Zgodność urządzenia** > **Mobile Threat Defense** i wybierz pozycję **Dodaj**.

3. W okienku *Dodawanie łącznika* użyj listy rozwijanej i wybierz pozycję **Lookout for Work**.  

4. Wybierz przycisk **Utwórz**. Po nawiązaniu kontaktu między łącznikiem i pozycja *Connector Settings* (Ustawienia łącznika) stanie się dostępna.

5. Ustaw pozycję **Włącz synchronizację aplikacji dla urządzeń z systemem iOS** na **Wł.** 

6. Wybierz przycisk **Zapisz**, aby ukończyć konfigurację.  Usługi Intune i Lookout MES są teraz zintegrowane i gotowe do użycia.


## <a name="additional-settings-in-the-lookout-mes-console"></a>Dodatkowe ustawienia w konsoli usługi Lookout MES
Poniżej przedstawiono dodatkowe ustawienia, które można skonfigurować w konsoli usługi Lookout MES.  

### <a name="configure-enrollment-settings"></a>Konfigurowanie ustawień rejestracji
W konsoli usługi Lookout MES wybierz kolejno pozycje **System** > **Manage Enrollment** > **Enrollment settings** (System > Zarządzanie rejestracją > Ustawienia rejestracji).  

- W obszarze **Disconnected Status** (Stan odłączenia) określ liczbę dni, po którym urządzenie niepołączone zostanie oznaczone jako odłączone.  

  Odłączone urządzenia są uznawane za niezgodne i nie mają dostępu do aplikacji firmowych zgodnie z zasadami dostępu warunkowego usługi Intune. Można określić wartości z zakresu od 1 do 90 dni.

  ![Ustawienia rejestracji usługi Lookout w module System](./media/lookout-mtd-connector-integration/lookout-console-enrollment-settings.png)

### <a name="configure-email-notifications"></a>Konfigurowanie powiadomień e-mail
Aby otrzymywać alerty e-mail dotyczące zagrożeń, zaloguj się do [konsoli usługi Lookout MES](https://aad.lookout.com) przy użyciu konta użytkownika, które powinno otrzymywać powiadomienia.  

- Przejdź do pozycji **Preferences** (Preferencje) i ustaw powiadomienia, które chcesz otrzymywać, na **ON** (Włącz), a następnie użyj przycisku **Save** (Zapisz) w celu zapisania zmian.  

- Jeśli nie chcesz już otrzymywać powiadomień e-mail, ustaw dla powiadomień wartość **OFF** (Wyłącz) i zapisz zmiany.

  ![zrzut ekranu strony preferencji z wyświetlonym kontem użytkownika](./media/lookout-mtd-connector-integration/lookout-mtp-email-notifications.png)



## <a name="configure-threat-classifications"></a>Konfigurowanie klasyfikacji zagrożeń  
Usługa Lookout Mobile Endpoint Security klasyfikuje różne typy zagrożeń dla urządzeń przenośnych. Klasyfikacje zagrożeń w usłudze Lookout mają domyślne poziomy ryzyka, które są z nimi skojarzone. Poziomy ryzyka można zmienić w dowolnym momencie zależnie od potrzeb firmy.

Aby uzyskać informacje na temat klasyfikacji poziomów zagrożeń i sposobów zarządzania skojarzonymi z nimi poziomami ryzyka, zapoznaj się z [dokumentacją dotyczącą zagrożeń usługi Lookout](https://enterprise.support.lookout.com/hc/articles/360011812974).

>[!IMPORTANT]
> Poziomy ryzyka są istotnym elementem usługi Mobile Endpoint Security, ponieważ podczas integracji usługi Intune na ich podstawie jest określana zgodność urządzenia w czasie wykonywania.  
> 
> Administrator usługi Intune ustawia regułę w zasadach, aby uznawać urządzenie za niezgodne, jeśli zawiera ono aktywne zagrożenie z **wysokim**, **średnim** lub **niskim** poziomem ryzyka. Obliczanie zgodności urządzenia w usłudze Intune zależy bezpośrednio od zasad klasyfikacji zagrożeń w usłudze Lookout Mobile Endpoint Security.  

## <a name="monitor-enrollment"></a>Monitorowanie rejestracji
Po zakończeniu konfiguracji usługa Lookout Mobile Endpoint Security rozpoczyna sondowanie usługi Azure AD pod kątem urządzeń, które odpowiadają określonym grupom rejestracji.  Informacje dotyczące zarejestrowanych urządzeń można znaleźć, przechodząc do obszaru **Devices** (Urządzenia) w konsoli usługi Lookout MES.  
- Początkowy stan urządzeń to *oczekujące*.  
- Stan urządzenia jest aktualizowany po zainstalowaniu, otwarciu i aktywowaniu aplikacji *Lookout for Work* na danym urządzeniu.

Aby uzyskać szczegółowe informacje na temat wdrażania aplikacji *Lookout for Work* na urządzeniu, zobacz [Add Lookout for work apps with Intune](mtd-apps-ios-app-configuration-policy-add-assign.md) (Dodawanie aplikacji Lookout for Work za pomocą usługi Intune).

## <a name="next-steps"></a>Następne kroki

[Konfiguracja aplikacji Lookout](mtd-apps-ios-app-configuration-policy-add-assign.md)
