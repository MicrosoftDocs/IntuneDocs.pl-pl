---
title: Rozwiązywanie problemów z integracją Jamf Pro z usługą Microsoft Intune
titleSuffix: Microsoft Intune
description: Sugestie dotyczące rozwiązywania niektórych typowych problemów związanych z integracją urządzeń z programem Jamf Pro for Mac z Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/02/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 44733eb369e520d2d5f0ff548d4f1921abcb8758
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72503568"
---
# <a name="troubleshoot-integration-of-jamf-pro-with-microsoft-intune"></a>Rozwiązywanie problemów z integracją Jamf Pro z usługą Microsoft Intune

Ten artykuł pomaga administratorom usługi Intune zrozumieć i rozwiązać problemy z integracją usługi Jamf Pro macOS z usługą Intune.

> [!TIP]  
> Większość informacji w tym artykule pojawiło się pierwotnie [podczas rozwiązywania problemów związanych z integracją Jamf z usługą Microsoft Intune](https://support.microsoft.com/help/4519171/troubleshoot-problems-when-integrating-jamf-with-microsoft-intune) na support.Microsoft.com.

## <a name="prerequisites"></a>Wymagania wstępne

Przed rozpoczęciem rozwiązywania problemów Zbierz podstawowe informacje w celu wyjaśnienia problemu i skrócenia czasu, aby znaleźć rozwiązanie. Na przykład w przypadku wystąpienia problemu związanego z integracją usługi Jamf z usługą Intune należy zawsze sprawdzić, czy wszystkie wymagania wstępne zostały spełnione. Przed rozpoczęciem rozwiązywania problemów zapoznaj się z następującymi kwestiami:

- Zapoznaj się z wymaganiami wstępnymi [dotyczącymi integracji usługi Jamf Pro z usługą Intune](conditional-access-integrate-jamf.md#prerequisites).
- Wszyscy użytkownicy muszą mieć licencje Microsoft Intune i Microsoft AAD Premium P1 
- Musisz mieć konto użytkownika, które ma uprawnienia do integracji Microsoft Intune w konsoli programu Jamf Pro.
- Musisz mieć konto użytkownika z uprawnieniami administratora globalnego na platformie Azure.


Podczas badania integracji Jamf Pro z usługą Intune należy wziąć pod uwagę następujące informacje: 
- Jaki jest dokładny komunikat o błędzie?
- Gdzie jest komunikat o błędzie?
- Kiedy problem zaczął występować?  Czy usługa Jamf Pro współpracuje z usługą Intune?
- Ilu użytkowników dotyczy ten wpływ? Czy wszyscy użytkownicy mają te same lub tylko niektóre?
- Ile urządzeń ma wpływ? Czy dotyczy to wszystkich urządzeń?
 

## <a name="common-problems"></a>Typowe problemy 

Poniższe informacje ułatwiają identyfikowanie i rozwiązywanie typowych problemów dotyczących urządzeń po skonfigurowaniu integracji usługi Intune i Jamf Pro.  

| Problem   | Więcej informacji                  |
|-----------------|--------------------------|
| **Urządzenia są oznaczone jako nieodpowiadające w Jamf Pro**  | [Nie można zaewidencjonować urządzeń za pomocą Jamf Pro lub z usługą Azure AD](#devices-are-marked-as-unresponsive-in-jamf-pro) |
| **Monit dotyczący logowania z pęku kluczy na urządzeniach Mac podczas otwierania urządzeń aplikacji nie można zarejestrować**  | [Użytkownicy są monitowani o podanie hasła, aby umożliwić aplikacjom rejestrację w usłudze Azure AD](#mac-devices-prompt-for-keychain-sign-in-when-you-open-an-app). |
| **Nie można zarejestrować urządzeń**  | Mogą być stosowane następujące przyczyny: <br> **-** [ ***Przyczyna 1*** — aplikacja Jamf Pro na platformie Azure ma nieprawidłowe uprawnienia](#cause-1) <br> **-** [ ***Przyczyna 2*** — występuje problem z *Jamf natywnego łącznika macOS* w usłudze Azure AD](#cause-2) <br> **-** [ ***Przyczyna 3*** — użytkownik nie ma ważnej licencji usługi Intune lub Jamf](#cause-3) <br> **-** [ ***Przyczyna 4*** — użytkownik nie korzystał z Jamf samoobsługowego w celu uruchomienia aplikacji Portal firmy](#cause-4) <br> **-** [ ***Przyczyna 5*** — integracja z usługą Intune jest wyłączona](#cause-5) <br> **-** [ ***Przyczyna 6*** — urządzenie zostało wcześniej zarejestrowane w usłudze Intune lub użytkownik próbował zarejestrować urządzenie wiele razy](#cause-6) <br> **-** [ ***spowodować, że 7*** -JamfAAD zażąda dostępu do klucza "Microsoft Workplace Join" z łańcucha kluczy użytkowników](#cause-7) |
|  **Urządzenie Mac ukazuje zgodność w usłudze Intune, ale niezgodne na platformie Azure** | [Problemy z rejestracją urządzenia](#mac-device-shows-compliant-in-intune-but-noncompliant-in-azure) |
| **Zduplikowane wpisy są wyświetlane w konsoli usługi Intune dla urządzeń Mac zarejestrowanych przy użyciu Jamf** | [Wiele rejestracji z tego samego urządzenia](#duplicate-entries-appear-in-the-intune-console-for-mac-devices-enrolled-by-using-jamf) |
| **Szacowanie urządzenia przez zasady zgodności nie powiodło się** | [Zasady są obiektami docelowymi grup urządzeń](#compliance-policy-fails-to-evaluate-the-device) |
| **Nie można pobrać tokenu dostępu dla interfejsu API Microsoft Graph** | Mogą być stosowane następujące przyczyny: <br> [uprawnienia - dla aplikacji Jamf Pro na platformie Azure](#theres-a-permission-issue-with-the-jamf-pro-application-in-azure) <br> - [wygasłą licencję dla usługi Jamf lub usługi Intune](#a-license-required-for-jamf-intune-integration-has-expired) <br> porty **-** [nie są otwarte](#the-required-ports-arent-open-on-your-network)|
 

### <a name="devices-are-marked-as-unresponsive-in-jamf-pro"></a>Urządzenia są oznaczone jako nieodpowiadające w Jamf Pro  

**Przyczyna**: poniżej przedstawiono typowe przyczyny, że urządzenia są oznaczone jako *nieodpowiadające* przez Jamf Pro:

- Nie można zaewidencjonować urządzenia przy użyciu Jamf Pro.  
  Jamf Pro oczekuje, że urządzenia są sprawdzane co 15 minut. Urządzenia są oznaczane jako nieodpowiadające przez Jamf w przypadku niepowodzenia zaewidencjonowania w okresie 24 godzin.  

- Nie można zaewidencjonować urządzenia w usłudze Azure AD.  
  Po pomyślnej rejestracji w usłudze Azure AD urządzenia macOS odbierają token platformy Azure:
  - Ten token odświeża co 12 godzin.   
  - Gdy odświeżanie tokenu kończy się niepowodzeniem przez 24 godziny lub dłużej, Jamf Pro oznacza urządzenie jako nieodpowiadające.  
  - Jeśli token platformy Azure wygaśnie, użytkownicy są monitowani o zalogowanie się do platformy Azure w celu uzyskania nowego tokenu. Token odświeżania dla dostępu do platformy Azure jest generowany co siedem dni.

**Rozwiązanie**  
Gdy urządzenie zostanie oznaczone jako *nieodpowiadające* przez Jamf Pro, zarejestrowanego użytkownika urządzenia musi się zalogować, aby poprawić stan braku odpowiedzi. Musi to być użytkownik, który został dołączony do konta, ponieważ ma tożsamość z usługi Intune w swoim pęku kluczy logowania.



### <a name="mac-devices-prompt-for-keychain-sign-in-when-you-open-an-app"></a>Urządzenia Mac monitują o logowanie do łańcucha kluczy podczas otwierania aplikacji  

Po skonfigurowaniu integracji usługi Intune i Jamf Pro oraz wdrożeniu zasad dostępu warunkowego użytkownicy urządzeń zarządzanych za pomocą usługi Jamf Pro otrzymają monit o hasło podczas otwierania aplikacji Microsoft Office 365, takich jak zespoły, Outlook i inne aplikacje wymagające platformy Azure Uwierzytelnianie usługi AD. 

Na przykład po otwarciu programu Microsoft Teams pojawia się monit z tekstem podobnym do poniższego przykładu:

``` 
  Microsoft Teams wants to sign using key “Microsoft Workplace Join Key” in your keychain.  
  To allow this, enter the “login” keychain password 
```

**Przyczyna**: te monity są generowane przez Jamf Pro dla każdej odpowiedniej aplikacji, która wymaga rejestracji w usłudze Azure AD. 

**Rozwiązanie**   
Po wyświetleniu monitu użytkownik musi podać hasło urządzenia, aby zalogować się do usługi Azure AD. Dostępne opcje:
- **Odmów** — nie loguj się i nie używaj aplikacji.
- **Zezwalaj** — Logowanie jednokrotne. Przy następnym otwarciu aplikacji zostanie wyświetlony komunikat z prośbą o ponowne zalogowanie.
- **Zawsze Zezwalaj** — poświadczenia logowania są buforowane dla aplikacji. Przy następnym otwarciu aplikacji nie zostanie wyświetlony monit o zalogowanie się.  

Wybranie opcji *zawsze Zezwalaj* dla jednej aplikacji powoduje tylko zatwierdzenie tej aplikacji na potrzeby logowania w przyszłości. Dodatkowe aplikacje monitują o uwierzytelnienie, dopóki nie zostaną również ustawione jako *zawsze Zezwalaj*. Poświadczenia buforowane dla jednej aplikacji nie mogą być używane przez inną aplikację.  

### <a name="devices-fail-to-register"></a>Nie można zarejestrować urządzeń  

Istnieje kilka typowych przyczyn niepowodzenia rejestracji urządzeń Mac.  

#### <a name="cause-1"></a>Przyczyna 1  

**Aplikacja Jamf Pro Enterprise na platformie Azure ma nieprawidłowe uprawnienia lub ma więcej niż jedno uprawnienie**  

  Podczas tworzenia aplikacji na platformie Azure należy usunąć wszystkie domyślne uprawnienia interfejsu API, a następnie przypisać do niej pojedyncze uprawnienie *update_device_attributes*. 

  **Rozwiązanie**  
  Przejrzyj i w razie potrzeby popraw uprawnienia dla aplikacji Jamf utworzonej w usłudze Azure AD. Zobacz procedurę [tworzenia aplikacji dla Jamf w usłudze Azure AD](conditional-access-integrate-jamf.md#create-an-application-in-azure-active-directory). 

#### <a name="cause-2"></a>Przyczyna 2  

**Aplikacja **Jamf Native MacOS Connector** nie została utworzona w dzierżawie usługi Azure AD lub nie ma zgody na to, że łącznik został podpisany przy użyciu konta, które nie ma uprawnień administratora globalnego**  

  **Rozwiązanie**  
  Zapoznaj się z sekcją *Konfigurowanie integracji usługi MacOS Intune* w artykule [Integrowanie z usługą Microsoft Intune](https://docs.jamf.com/10.13.0/jamf-pro/administrator-guide/Integrating_with_Microsoft_Intune.html) na docs.jamf.com. 

#### <a name="cause-3"></a>Przyczyna 3

**Użytkownik nie ma prawidłowej licencji usługi Intune lub Jamf**  

  Brak prawidłowej licencji może skutkować następującym błędem, który wskazuje, że licencja Jamf wygasła:  
  ```
    Unable to connect to Microsoft Intune.  
    
    Check your Microsoft Intune Integration configuration.
  ```  

  **Rozwiązanie**
  - Licencja Jamf: skontaktuj się z Jamf, aby uzyskać pomoc w celu uzyskania nowej licencji dla usługi Jamf.  
  - Licencja usługi Intune: przypisz użytkownikowi ważną licencję lub skontaktuj się z firmą Microsoft lub partnerem, aby uzyskać informacje na temat uzyskiwania bieżącej licencji.

#### <a name="cause-4"></a>Przyczyna 4  

**Użytkownik nie korzystał z *Jamf samoobsługowego* w celu uruchomienia aplikacji Portal firmy**

Aby urządzenie zostało pomyślnie zarejestrowane i zarejestrowane w usłudze Intune za pomocą usługi Jamf, użytkownik musi użyć samoobsługowego Jamf, aby otworzyć Intune — Portal firmy. Jeśli użytkownik ręcznie otworzy Portal firmy, urządzenie rejestruje i rejestruje bez połączenia z usługą Jamf.  

Aby określić, która usługa jest używana do rejestrowania i rejestrowania urządzenia, zapoznaj się z aplikacją Portal firmy na urządzeniu. Po zarejestrowaniu za pomocą usługi Jamf należy odebrać powiadomienie, aby otworzyć aplikację samoobsługową w celu wprowadzenia zmian.

W aplikacji Portal firmy użytkownik może zobaczyć **`Not registered`** , a w dziennikach Portal firmy może pojawić się wpis podobny do następującego:  

```
   Line 7783: <DATE> <IP ADDRESS> INFO com.microsoft.ssp.application TID=1  
 
   WelcomeViewController.swift: 253 (startLogin()) Portal launched without WPJ only arg while account is under partner management
```

**Rozwiązanie**  
Aby zmienić źródło rejestracji z usługi Intune na Jamf:
1. [Wyrejestruj urządzenie z systemem macOS z usługi Intune](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-macos). Aby uniknąć dalszych komplikacji dla urządzeń, które nie zostały w pełni usunięte z usługi Intune, zobacz [*Przyczyna 6*](#cause-6) na tej liście przyczyn.  

2. Na urządzeniu Użyj Jamf samoobsługowego, aby otworzyć aplikację Portal firmy, a następnie Zarejestruj urządzenie w usłudze Intune. To zadanie wymaga [użycia Jamf do wdrożenia aplikacji Portal firmy dla macOS](conditional-access-assign-jamf.md#deploy-the-company-portal-app-for-macos-in-jamf-pro)i [utworzenia zasad w programie Jamf Pro, które rejestrują urządzenie użytkowników w usłudze Azure AD](conditional-access-assign-jamf.md#create-a-policy-in-jamf-pro-to-have-users-register-their-devices-with-azure-active-directory).  

3. Po otwarciu portalu wyświetlany jest pierwszy ekran z prośbą o zalogowanie się. Używanie konta służbowego  

4. Portal firmy potwierdzi informacje o Twoim koncie, a następnie pokaże stan rejestracji urządzenia i zgodności urządzenia. Żółtymi trójkątami oznaczono akcje, które należy wykonać, aby zabezpieczyć urządzenie z systemem macOS na potrzeby zadań związanych ze szkołą lub pracą. Kliknij przycisk Rozpocznij, aby rozpocząć rejestrację.  

5. Po wyświetleniu monitu wpisz informacje logowania dla komputera.  
     
Rejestracja urządzenia w zarządzaniu może potrwać kilka minut. W tym czasie można robić inne rzeczy na urządzeniu. Gdy konfigurowanie dostępu do zasobów firmy zostanie zakończone, pojawi się odpowiedni komunikat.

#### <a name="cause-5"></a>Przyczyna 5  

**Integracja z usługą Intune jest wyłączona**

Jeśli integracja z usługą Intune jest wyłączona, użytkownicy będą otrzymywać okna podręczne w Portal firmy z następującym komunikatem podczas próby zarejestrowania urządzenia:  

```
   Invalid command line input
   
   Registration-only command line flag (-r) can only be used when partner management is enabled in Intune. Please contact your IT admin.
```  

Serwer Jamf Pro wysyła puls do serwerów usługi Intune, gdy integracja jest wyłączona, co oznacza, że integracja jest wyłączona. 

**Rozwiązanie**  
Włącz ponownie integrację usługi Intune w ramach Jamf Pro. Zobacz [Konfigurowanie integracji z usługą Microsoft Intune w narzędziu Jamf Pro](conditional-access-integrate-jamf.md#enable-intune-to-integrate-with-jamf-pro).


#### <a name="cause-6"></a>Przyczyna 6  

**Urządzenie zostało wcześniej zarejestrowane w usłudze Intune lub użytkownik próbował zarejestrować urządzenie wiele razy**

Jeśli urządzenie zostanie wyrejestrowane z usługi Jamf, ale nie zostało prawidłowo usunięte z usługi Intune, lub kilka prób rejestracji będzie można zobaczyć wiele wystąpień tego samego urządzenia w portalu. Powoduje to niepowodzenie rejestracji Jamf.

**Rozwiązanie**  
1. Na komputerze Mac Uruchom **Terminal**.
2. Uruchom **sudo JAMF removemdmprofile**.
3. Uruchom **sudo JAMF removeFramework**.
4. Na serwerze JAMF Pro Usuń rekord spisu komputera.
5. Usuń urządzenie z AzureAD.
6. Usuń następujące pliki na urządzeniu, jeśli istnieją:
   - /Library/Application Support support/com. Microsoft. CompanyPortal. UserContext. info
   - /Library/Application Support support/com. Microsoft. CompanyPortal
   - /Library/Application Support support/com. jamfsoftware. samoobsługowy. Mac
   - Aplikacja/Library/Saved
   - State/com. jamfsoftware. samoobsługowy. Mac. savedState
   - /Library/Saved Application State/com. Microsoft. CompanyPortal. savedState
   - /Library/Preferences/com.microsoft.CompanyPortal.plist
   - /Library/Preferences/com.jamfsoftware.selfservice.mac.plist
   - /Library/Preferences/com.jamfsoftware.management.jamfAAD.plist
   - /Users/<username>/Library/Cookies/com.microsoft.CompanyPortal.binarycookies
   - /Users/<username>/Library/Cookies/com.jamf.management.jamfAAD.binarycookies
   - com. Microsoft. CompanyPortal
   - com. Microsoft. CompanyPortal. HockeySDK
   - enterpriseregistration.windows.net
   - https://device.login.microsoftonline.com
   - https://device.login.microsoftonline.com/
   - Klucz transportu sesji firmy Microsoft (klucze publiczne i prywatne)
   - Klucz Workplace Join firmy Microsoft (klucze publiczne i prywatne)
7. Usuń wszystkie elementy z łańcucha kluczy na urządzeniu, które odwołują się do usługi *Microsoft*, usługi *Intune*lub *Portal firmy*, w tym certyfikatów DeviceLogin.Microsoft.com. Usuń odwołania *JAMF* z wyjątkiem klucza publicznego i prywatnego. 
   > [!IMPORTANT]  
   > Usunięcie klucza publicznego i prywatnego spowoduje uszkodzenie rejestracji urządzeń.

8. Usuń dowolne z następujących wpisów:  
   - Rodzaj: hasło aplikacji; Konto: com. Microsoft. workplacejoin. odcisk palca
   - Rodzaj: hasło aplikacji; Konto: com. Microsoft. workplacejoin. registeredUserPrincipalName
   - Rodzaj: certyfikat; Wystawiony przez: MS-Organization-Access
   - Rodzaj: preferencje tożsamości; Nazwa (adres URL usługi AD FS, jeśli istnieje): https://adfs\<DNSName>.com/adfs/ls
   - Rodzaj: preferencje tożsamości; Nazwa: https://enterpriseregistration.windows.net
   - Rodzaj: preferencje tożsamości; Nazwa: https://enterpriseregistration.windows.net/  
9. Uruchom ponownie urządzenie Mac.
10. Odinstaluj Portal firmy z urządzenia.
11. Przejdź do portal.manage.microsoft.com i Usuń wszystkie wystąpienia urządzenia Mac. Zaczekaj co najmniej 30 minut, zanim przejdziesz do następnego kroku.
12. Zarejestruj ponownie urządzenie w usłudze JAMF Pro.
13. Otwórz ponownie samoobsługowe i uruchom zasady rejestracji.


#### <a name="cause-7"></a>Przyczyna 7  

**JamfAAD żąda dostępu do "klucza Workplace Join Microsoft" z łańcucha kluczy użytkowników**

Podczas rejestracji użytkownik urządzenia macOS otrzymuje następujący monit, aby umożliwić JamfAAD dostęp do klucza z poziomu łańcucha kluczy: 

```
   JamfAAD wants to access key “Microsoft Workplace Join Key" in your keychain. 
    
   To allow this, enter the “login” keychain password
```

**Rozwiązanie**  
Aby pomyślnie zarejestrować urządzenie w usłudze Azure AD, Jamf wymaga od użytkownika podania hasła konta i wybrania opcji **Zezwalaj**.

To żądanie jest podobne do [monitu o zalogowanie urządzenia Mac podczas otwierania aplikacji](#mac-devices-prompt-for-keychain-sign-in-when-you-open-an-app)wcześniej w tym artykule.  

 
### <a name="mac-device-shows-compliant-in-intune-but-noncompliant-in-azure"></a>Urządzenie Mac ukazuje zgodność w usłudze Intune, ale niezgodne na platformie Azure  

**Przyczyna**: poniższe warunki mogą spowodować, że urządzenie będzie wyświetlane jako zgodne w usłudze Intune, ale nie jako zgodne na platformie Azure:  
- Urządzenie nie jest poprawnie zarejestrowane.  
- Urządzenie zostało zarejestrowane wiele razy bez konieczności czyszczenia.

**Rozwiązanie**  
Aby rozwiązać ten problem, należy wykonać czynności opisane [*w temacie w przypadku*](#cause-6) *niepowodzenia rejestracji urządzeń*w dalszej części tego artykułu. 


### <a name="duplicate-entries-appear-in-the-intune-console-for-mac-devices-enrolled-by-using-jamf"></a>Zduplikowane wpisy są wyświetlane w konsoli usługi Intune dla urządzeń Mac zarejestrowanych przy użyciu Jamf  
 
**Przyczyna**: urządzenie jest rejestrowane w usłudze Intune wielokrotnie, zwykle jest ponownie rejestrowane po usunięciu z usługi Intune.  

Po usunięciu urządzenia z integracji usługi Intune i Jamf Pro niektóre dane mogą pozostać w tle, co może spowodować pomyślne rejestracje w celu utworzenia zduplikowanych wpisów.  

**Rozwiązanie**  
Aby rozwiązać ten problem, należy wykonać czynności opisane [*w temacie w przypadku*](#cause-6) *niepowodzenia rejestracji urządzeń*w dalszej części tego artykułu. 

### <a name="compliance-policy-fails-to-evaluate-the-device"></a>Szacowanie urządzenia przez zasady zgodności nie powiodło się  

**Przyczyna**: integracja narzędzia Jamf z usługą Intune nie obsługuje zasad zgodności, które są przeznaczone dla grup urządzeń. 

**Rozwiązanie**  
Zmodyfikuj zasady zgodności dla urządzeń macOS, które mają być przypisane do grup użytkowników. 


### <a name="could-not-retrieve-the-access-token-for-microsoft-graph-api"></a>Nie można pobrać tokenu dostępu dla interfejsu API Microsoft Graph

Jest wyświetlany następujący komunikat o błędzie:

```
   Could not retrieve the access token for Microsoft Graph API. Check the configuration for Microsoft Intune Integration.
```   

Źródłem tego błędu może być jeden z następujących przyczyn: 

#### <a name="theres-a-permission-issue-with-the-jamf-pro-application-in-azure"></a>Wystąpił problem z uprawnieniami w aplikacji Jamf Pro na platformie Azure

Podczas rejestrowania aplikacji Jamf Pro na platformie Azure wystąpił jeden z następujących warunków:  
- Aplikacja otrzymała więcej niż jedno uprawnienie.
- Nie wybrano opcji **Udziel zgody administratora na *\<your > firmy***  .  

**Rozwiązanie**  
Zobacz rozwiązanie dla przyczyny 1, aby [nie można było zarejestrować urządzeń](#devices-fail-to-register)we wcześniejszej części tego artykułu.

#### <a name="a-license-required-for-jamf-intune-integration-has-expired"></a>Licencja wymagana przez usługę Jamf — integracja z usługą Intune wygasła

**Rozwiązanie**: Sprawdź, czy [nie można zarejestrować się](#devices-fail-to-register)w celu uzyskania przyczyny 3. 

#### <a name="the-required-ports-arent-open-on-your-network"></a>Wymagane porty nie są otwarte w sieci

**Rozwiązanie**: Zapoznaj się z informacjami dotyczącymi portów sieciowych w temacie [wymagania wstępne](conditional-access-integrate-jamf.md#prerequisites) dotyczące integrowania Jamf Pro z usługą Intune.


## <a name="next-steps"></a>Następne kroki
Dowiedz się więcej o [integrowaniu usługi Jamf Pro z usługą Intune](conditional-access-integrate-jamf.md)