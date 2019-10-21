---
title: Dodawanie zasad konfiguracji aplikacji dla zarządzanych urządzeń z systemem Android Enterprise
titleSuffix: Microsoft Intune
description: Zasady konfiguracji aplikacji w usłudze Microsoft Intune umożliwiają określanie ustawień podczas uruchamiania aplikacji zarządzanego sklepu Google Play przez użytkowników.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d31126a259274a2c75f933428632e274d8710aa6
ms.sourcegitcommit: b8127c7a62d9ac4d0f768980fa1424567bb58733
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/15/2019
ms.locfileid: "72350028"
---
# <a name="add-app-configuration-policies-for-managed-android-enterprise-devices"></a>Dodawanie zasad konfiguracji aplikacji dla zarządzanych urządzeń z systemem Android Enterprise

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Zasady konfiguracji aplikacji w usłudze Microsoft Intune zawierają ustawienia dla aplikacji zarządzanego sklepu Google Play na zarządzanych urządzeniach z systemem Android Enterprise. Deweloper aplikacji uwidacznia ustawienia konfiguracji aplikacji zarządzanej przez system Android. Usługa Intune używa tych uwidocznionych ustawień, aby umożliwić administratorowi skonfigurowanie funkcji dla aplikacji. Zasady konfiguracji aplikacji są przypisane do Twoich grup użytkowników. Ustawienia zasad są stosowane, gdy aplikacja je wyszukuje (zazwyczaj podczas pierwszego uruchomienia aplikacji).

> [!NOTE]  
> Nie wszystkie aplikacje obsługują konfigurację aplikacji. Skontaktuj się z deweloperem aplikacji, aby dowiedzieć się, czy jego aplikacja obsługuje zasady konfiguracji aplikacji.

1. W usłudze [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) wybierz pozycje **Aplikacje klienckie** > **Zasady konfiguracji aplikacji** >  **Dodaj**.
2. Wprowadź następujące właściwości:

    - **Nazwa**: wprowadź opisową nazwę zasad. Nadaj nazwę zasadom, aby można było je później łatwo rozpoznać. Na przykład dobrą nazwą zasad jest **Zasady aplikacji Android Enterprise Nine Work dla całej firmy**.
    - **Opis**: Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
    - **Typ rejestracji urządzenia**: Wybierz pozycję **Urządzenia zarządzane**.
    - **Platforma**: — wybierz opcję **Android**.

3. Wybierz pozycję **Skojarzona aplikacja**. Wybierz aplikację, dla której chcesz zdefiniować zasady konfiguracji aplikacji. Wybierz z listy aplikacji zarządzanego sklepu Google Play aplikacje zatwierdzone i zsynchronizowane z usługą Intune.
4. Wybierz pozycję **Uprawnienia**. Konfigurację możesz ustawić przy użyciu następujących narzędzi:

    - [projektant konfiguracji](#use-the-configuration-designer)
    - [edytor JSON](#enter-the-json-editor)

5. Wybierz przyciski **OK** > **Dodaj**.

## <a name="use-the-configuration-designer"></a>Korzystanie z projektanta konfiguracji

W przypadku aplikacji zarządzanego sklepu Google Play zaprojektowanych pod kątem obsługi ustawień konfiguracji możesz użyć projektanta konfiguracji. Konfiguracja dotyczy urządzeń zarejestrowanych w usłudze Intune. Projektant umożliwia określanie konkretnych wartości konfiguracji dla ustawień ujawnianych przez aplikację.

1. Wybierz pozycję **Dodaj**. Wybierz listę ustawień konfiguracji, które chcesz wprowadzić dla aplikacji.

    Jeśli aplikacja poczty e-mail, z której korzystasz, to GMail lub Nine Work, więcej informacji dotyczących tych ustawień znajduje się w temacie [Android Enterprise device settings to configure email](../email-settings-android-enterprise.md) (Ustawienia urządzeń z systemem Android Enterprise do konfiguracji poczty e-mail).

2. Dla każdego klucza i wartości konfiguracji ustaw następujące elementy:

    - **Typ wartości**: Typ danych wartości konfiguracji. W przypadku typu wartości ciągu możesz opcjonalnie wybrać zmienną lub profil certyfikatu jako typ wartości.
    - **Wartość konfiguracji**: Wartość konfiguracji. Jeśli wybierzesz zmienną lub certyfikat w polu **Typ wartości**, wybierz z listy zmiennych lub profilów certyfikatów. Jeżeli wybierzesz certyfikat, alias certyfikatu wdrożonego na urządzeniu zostanie wypełniony w czasie uruchamiania.

### <a name="supported-variables-for-configuration-values"></a>Obsługiwane zmienne dla wartości konfiguracji

Jeśli wybierzesz zmienną jako typ wartości, możesz wybrać następujące opcje:

| Opcja | Przykład |
|----|----|
| Mail | john@contoso.com |
| Nazwa główna użytkownika | john@contoso.com |
| Częściowa nazwa UPN | jan |
| Domena | contoso.com |
| Nazwa użytkownika | Jan Kowalski |
| Identyfikator konta | fc0dc142-71d8-4b12-bbea-bae2a8514c81 |
| Identyfikator użytkownika | 3ec2c00f-b125-4519-acf0-302ac3761822 |
| Identyfikator urządzenia | b9841cd9-9843-405f-be28-b2265c59ef97 |

### <a name="allow-only-configured-organization-accounts-in-multi-identity-apps"></a>Zezwalanie tylko na skonfigurowane konta organizacji w aplikacjach z obsługą wielu tożsamości 

W przypadku urządzeń z systemem Android używaj następujących par klucz/wartość:

| **Klucz** | com.microsoft.intune.mam.AllowedAccountUPNs |
|---|---|
| **Wartości** | <ul><li>Jedna nazwa UPN lub więcej nazw UPN rozdzielonych znakiem <code>;</code>.</li><li>Jedynymi dopuszczonymi kontami są zarządzane konta użytkownika zdefiniowane przez ten klucz.</li><li> W przypadku urządzeń zarejestrowanych w usłudze Intune token <code>{{userprincipalname}}</code> może służyć do reprezentowania zarejestrowanego konta użytkownika.</li></ul> |

   > [!NOTE]
   > Zezwalając jedynie na skonfigurowane konta organizacji z wieloma tożsamościami, musisz używać programu Outlook dla systemu Android w wersji 2.2.222 lub nowszej, programów Word, Excel i PowerPoint dla systemu Android w wersji 16.0.9327.1000 lub nowszej bądź usługi OneDrive dla systemu Android w wersji 5.28 lub nowszej.<p></p>
   > Jako administrator usługi Microsoft Intune masz możliwość kontrolowania kont użytkownika dodawanych do aplikacji pakietu Microsoft Office na urządzeniach zarządzanych. Istnieje możliwość ograniczenia dostępu tylko do dozwolonych kont użytkowników w organizacji oraz blokowania kont osobistych na zarejestrowanych urządzeniach. Aplikacje pomocnicze przetwarzają konfigurację aplikacji i usuwają oraz blokują niezatwierdzone konta.<p></p>

## <a name="enter-the-json-editor"></a>Edytor JSON

Nie jest możliwa konfiguracja niektórych ustawień konfiguracji aplikacji (np. typów pakietu) przy użyciu projektanta konfiguracji. W przypadku tych wartości użyj edytora JSON. Ustawienia są dostarczane do aplikacji automatycznie po zainstalowaniu aplikacji.

1. Dla opcji **Format ustawień konfiguracji** wybierz opcję **Edytor JSON**.
2. W edytorze można zdefiniować wartości JSON dla ustawień konfiguracji. Możesz wybrać pozycję **Pobierz szablon JSON**, aby pobrać przykładowy plik, który można następnie skonfigurować.
3. Wybierz **OK**, a następnie wybierz pozycję **Dodaj**.

Zasady zostaną utworzone i wyświetlone na liście.

Po uruchomieniu przypisanej aplikacji na urządzeniu uruchamiane są ustawienia skonfigurowane w zasadach konfiguracji aplikacji.

## <a name="preconfigure-the-permissions-grant-state-for-apps"></a>Wstępna konfiguracja stanu uprawnień dla aplikacji

Możesz również wstępnie skonfigurować uprawnienia aplikacji pod kątem dostępu do funkcji urządzenia z systemem Android. Domyślnie aplikacje systemu Android, które wymagają uprawnień urządzenia, takich jak dostęp do lokalizacji lub aparatu urządzenia, wyświetlają monit o zaakceptowanie lub odmowę przyznania uprawnień przez użytkownika.

Na przykład aplikacja używa mikrofonu urządzenia. Użytkownik otrzymuje monit o przyznanie aplikacji uprawnienia do korzystania z mikrofonu.

1. W usłudze [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) wybierz pozycje **Aplikacje klienckie** > **Zasady konfiguracji aplikacji** >  **Dodaj**.
2. Wprowadź następujące właściwości:

    - **Nazwa**: wprowadź opisową nazwę zasad. Nadaj nazwę zasadom, aby można było je później łatwo rozpoznać. Na przykład dobrą nazwą zasad jest **Zasady aplikacji monitu o uprawnienia systemu Android Enterprise dla całej firmy**.
    - **Opis**. Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
    - **Typ rejestracji urządzenia**: Wybierz pozycję **Urządzenia zarządzane**.
    - **Platforma**: — wybierz opcję **Android**.

3. Wybierz pozycję **Skojarzona aplikacja**. Wybierz aplikację, dla której chcesz zdefiniować zasady konfiguracji. Wybierz z listy aplikacji profilu służbowego systemu Android aplikacje zatwierdzone i zsynchronizowane z usługą Intune.
4. Wybierz pozycje **Uprawnienia** > **Dodaj**. Z listy wybierz dostępne uprawnienia aplikacji > **OK**.
5. Wybierz opcję dla każdego uprawnienia, które ma zostać przyznane zgodnie z tymi zasadami:
    - **Monituj**. Wyświetlenie monitu o zaakceptowanie lub odrzucenie przez użytkownika.
    - **Automatyczne udzielaj**. Automatyczne zatwierdzenie bez powiadamiania użytkownika.
    - **Automatyczne odmawiaj**. Automatyczna odmowa bez powiadamiania użytkownika.
6. Aby przypisać zasady konfiguracji aplikacji, wybierz zasady konfiguracji aplikacji > **Przypisanie** > **Wybierz grupy**. Wybierz grupy użytkowników do przypisania > **Wybierz**.
7. Wybierz pozycję **Zapisz**, aby przypisać zasady.

## <a name="additional-information"></a>Dodatkowe informacje

- [Przypisywanie aplikacji zarządzanego sklepu Google Play do urządzeń z systemem Android Enterprise](apps-add-android-for-work.md#assigning-a-managed-google-play-app-to-android-enterprise-work-profile-devices)
- [Deploying Outlook for iOS and Android app configuration settings](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune) (Wdrażanie ustawień konfiguracji aplikacji Outlook dla systemu iOS i Android)

## <a name="next-steps"></a>Następne kroki

Kontynuuj [przypisywanie](apps-deploy.md) i [monitorowanie](apps-monitor.md) aplikacji.
