---
title: Dodawanie zasad konfiguracji aplikacji dla zarządzanych urządzeń z systemem Android
titlesuffix: Microsoft Intune
description: Zasady konfiguracji aplikacji w usłudze Microsoft Intune umożliwiają określanie ustawień podczas uruchamiania aplikacji profilu służbowego systemu Android przez użytkowników.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: db6aed3d87b8a8df55c5c95e52eb3dd9ccc690a7
ms.sourcegitcommit: 911923e9fe0eed52b1c93e400f776956835e582f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/17/2019
ms.locfileid: "54386964"
---
# <a name="add-app-configuration-policies-for-managed-android-devices"></a>Dodawanie zasad konfiguracji aplikacji dla zarządzanych urządzeń z systemem Android

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Zasady konfiguracji aplikacji w usłudze Microsoft Intune umożliwiają określanie ustawień aplikacji profilu służbowego systemu Android. Deweloper aplikacji musi ujawnić ustawienia konfiguracji aplikacji zarządzane w systemie Android, aby określić ustawienia konfiguracji dla aplikacji. Przypisz zasady konfiguracji aplikacji do grupy użytkowników, wobec których chcesz zastosować ustawienia.  Ustawienia zasad są stosowane, gdy aplikacja je wyszukuje (zazwyczaj podczas pierwszego uruchomienia).

> [!Note]  
> Nie wszystkie aplikacje obsługują konfigurację aplikacji. Skontaktuj się z deweloperem aplikacji, aby dowiedzieć się, czy jego aplikacja obsługuje zasady konfiguracji aplikacji.

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. Wybierz obciążenie **Aplikacje klienckie**.
4. Wybierz pozycję **Zasady konfiguracji aplikacji** w grupie **Zarządzaj**, a następnie wybierz przycisk **Dodaj**.
5. Ustaw następujące szczegóły:
    - **Nazwa** — nazwa profilu, która będzie wyświetlana w witrynie Azure Portal.
    - **Opis** — opis profilu, który będzie wyświetlany w witrynie Azure Portal.
    - **Typ rejestracji urządzenia** — wybierz pozycję **Urządzenia zarządzane**.
6. Dla opcji **Platforma** wybierz pozycję **Android**.
7. Wybierz pozycję **Skojarzona aplikacja**, aby wybrać aplikację, dla której chcesz zdefiniować zasady konfiguracji aplikacji. Wybierz z listy aplikacji profilu służbowego systemu Android aplikacje zatwierdzone i zsynchronizowane z usługą Intune.
8. Wybierz pozycję **Uprawnienia**. Konfigurację możesz ustawić przy użyciu następujących narzędzi:
    - [projektant konfiguracji](#Use-the-configuration-designer)
    - [edytor JSON](#Enter-the-JSON-editor)
9. Wybierz **OK**, a następnie wybierz pozycję **Dodaj**.

## <a name="use-the-configuration-designer"></a>Korzystanie z projektanta konfiguracji

W przypadku aplikacji systemu Android obsługujących konfigurację możesz użyć projektanta konfiguracji. Konfiguracja będzie mieć zastosowanie wobec urządzeń zarejestrowanych w usłudze Intune. Projektant umożliwia określanie konkretnych wartości konfiguracji dla ustawień ujawnianych przez aplikację.

Wybierz opcję **Dodaj**, aby wybrać listę ustawień konfiguracji, które chcesz określić dla aplikacji.  
Dla każdego klucza i wartości konfiguracji ustaw następujące elementy:

  - **Typ wartości**  
    Typ danych wartości konfiguracji. W przypadku typu wartości ciągu możesz opcjonalnie wybrać zmienną lub profil certyfikatu jako typ wartości.
  - **Wartość konfiguracji**  
    Wartość konfiguracji. Jeśli wybierzesz zmienną lub certyfikat jako typ wartości, możesz wybrać pozycję z listy zmiennych lub profilów certyfikatów dostępnej na liście rozwijanej wartości konfiguracji.  Jeżeli wybierzesz certyfikat, alias certyfikatu wdrożonego na urządzeniu zostanie wypełniony w czasie uruchamiania.
    
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
|--------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Wartości** | <ul><li>Jedna nazwa UPN lub więcej nazw UPN rozdzielonych znakiem <code>;</code>.</li><li>Jedynymi dopuszczonymi kontami są zarządzane konta użytkownika zdefiniowane przez ten klucz.</li><li> W przypadku urządzeń zarejestrowanych w usłudze Intune token <code>{{userprincipalname}}</code> może służyć do reprezentowania zarejestrowanego konta użytkownika.</li></ul> |

   > [!NOTE]
   > W przypadku zezwalania wyłącznie na skonfigurowane konta organizacji w aplikacjach z obsługą wielu tożsamości należy użyć programu Outlook dla systemu Android 2.2.222 lub jego nowszej wersji.<p></p>
   > Jako administrator usługi Microsoft Intune masz możliwość kontrolowania kont użytkownika dodawanych do aplikacji pakietu Microsoft Office na urządzeniach zarządzanych. Istnieje możliwość ograniczenia dostępu tylko do dozwolonych kont użytkowników w organizacji oraz blokowania kont osobistych na zarejestrowanych urządzeniach. Aplikacje pomocnicze przetwarzają konfigurację aplikacji i usuwają oraz blokują niezatwierdzone konta.<p></p>
   > W przypadku programów Microsoft Word, Microsoft Excel i Microsoft PowerPoint należy korzystać z aplikacji w wersji 16.0.9327.1000 lub nowszej. 

## <a name="enter-the-json-editor"></a>Edytor JSON

Nie jest możliwa konfiguracja niektórych ustawień konfiguracji aplikacji (np. typów pakietu) przy użyciu projektanta konfiguracji. W przypadku tych wartości niezbędne jest użycie edytora JSON. Ustawienia są dostarczane do aplikacji automatycznie po zainstalowaniu aplikacji.

1. Dla opcji **Format ustawień konfiguracji** wybierz opcję **Edytor JSON**.
2. W edytorze można zdefiniować wartości JSON dla ustawień konfiguracji. Możesz wybrać pozycję **Pobierz szablon JSON**, aby pobrać przykładowy plik, który można następnie skonfigurować.
3. Wybierz **OK**, a następnie wybierz pozycję **Dodaj**.

Zasady zostaną utworzone i wyświetlone w bloku listy zasad.

Po uruchomieniu przypisanej aplikacji na urządzeniu uruchamiane są ustawienia skonfigurowane w zasadach konfiguracji aplikacji.

## <a name="preconfigure-the-permissions-grant-state-for-apps"></a>Wstępna konfiguracja stanu uprawnień dla aplikacji

Możesz również wstępnie skonfigurować uprawnienia dla aplikacji pod kątem dostępu do funkcji urządzenia z systemem Android. Domyślnie aplikacje systemu Android, które wymagają uprawnień urządzenia, takich jak dostęp do lokalizacji lub aparatu urządzenia, wyświetlają monit o zaakceptowanie lub odrzucenie uprawnień przez użytkownika. Na przykład jeśli aplikacja używa mikrofonu urządzenia, użytkownik otrzyma monit o przyznanie aplikacji uprawnienia do użycia mikrofonu.

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. Wybierz pozycję **Aplikacje klienckie**.
3. W obszarze **Zarządzaj** wybierz pozycję **Zasady konfiguracji** aplikacji, a następnie wybierz pozycję **Dodaj**.
4. Ustaw następujące szczegóły:
    - **Nazwa**. — nazwa profilu, która będzie wyświetlana w witrynie Azure Portal
    - **Opis**. — opis profilu, który będzie wyświetlany w witrynie Azure Portal
    - **Typ rejestracji urządzenia**. Wybierz pozycję **Urządzenia zarządzane**.
    - **Platforma**. — wybierz opcję **Android**.
5. Wybierz pozycję **Skojarzona aplikacja**, aby wybrać aplikację, dla której chcesz zdefiniować zasady konfiguracji. Wybierz z listy aplikacji profilu służbowego systemu Android aplikacje zatwierdzone i zsynchronizowane z usługą Intune.
6. Wybierz **Uprawnienia**, a następnie wybierz **Dodaj**.
7. Wybierz odpowiednie opcje z listy dostępnych uprawnień aplikacji, a następnie wybierz pozycję **OK**.
8. Wybierz opcję dla każdego uprawnienia, które ma zostać przyznane zgodnie z tymi zasadami:
    - **Monituj**. Wyświetlenie monitu o zaakceptowanie lub odrzucenie przez użytkownika.
    - **Automatyczne udzielaj**. Automatyczne zatwierdzenie bez powiadamiania użytkownika.
    - **Automatyczne odmawiaj**. Automatyczna odmowa bez powiadamiania użytkownika.
9. Aby przypisać zasady konfiguracji aplikacji, wybierz zasady konfiguracji aplikacji, wybierz pozycję **Przypisania**, a następnie wybierz pozycję **Wybierz grupy**.
10. Wybierz grupy użytkowników do przypisania, a następnie wybierz pozycję **Wybierz**.
11. Wybierz pozycję **Zapisz**, aby przypisać zasady.

## <a name="next-steps"></a>Następne kroki

Kontynuuj [przypisywanie](apps-deploy.md) i [monitorowanie](apps-monitor.md) aplikacji.

