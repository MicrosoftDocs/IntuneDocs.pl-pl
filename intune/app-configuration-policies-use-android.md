---
title: Dodawanie zasad konfiguracji aplikacji dla zarządzanych urządzeń z systemem Android
titlesuffix: Microsoft Intune
description: Zasady konfiguracji aplikacji w usłudze Microsoft Intune umożliwiają określanie ustawień podczas uruchamiania aplikacji Android for Work przez użytkowników.
keywords: ''
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6fbf70630124614aa1ed302a41d6e3f33c10c63d
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="add-app-configuration-policies-for-managed-android-devices"></a>Dodawanie zasad konfiguracji aplikacji dla zarządzanych urządzeń z systemem Android

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Zasady konfiguracji aplikacji w usłudze Microsoft Intune umożliwiają określanie ustawień podczas uruchamiania aplikacji Android for Work. Deweloper aplikacji musi ujawnić ustawienia konfiguracji aplikacji zarządzane w systemie Android, aby określić ustawienia konfiguracji dla aplikacji. Przypisz zasady konfiguracji aplikacji do grupy użytkowników, wobec których chcesz zastosować ustawienia.  Ustawienia zasad są stosowane, gdy aplikacja je wyszukuje (zazwyczaj podczas pierwszego uruchomienia).

> [!Note]  
> Nie wszystkie aplikacje obsługują konfigurację aplikacji. Skontaktuj się z deweloperem aplikacji, aby dowiedzieć się, czy jego aplikacja obsługuje zasady konfiguracji aplikacji.

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. Wybierz obciążenie **Aplikacje mobilne**.
4. Wybierz pozycję **Zasady konfiguracji aplikacji** w grupie **Zarządzaj**, a następnie wybierz przycisk **Dodaj**.
5. Ustaw następujące szczegóły:
    - **Nazwa**  
      — nazwa profilu, która będzie wyświetlana w witrynie Azure Portal
    - **Opis**  
      — opis profilu, który będzie wyświetlany w witrynie Azure Portal
    - **Typ rejestracji urządzenia**  
      Wybierz pozycję **Urządzenia zarządzane**.
6. Wybierz pozycję **Android for Work** w obszarze **Platforma**.
7. Wybierz pozycję **Skojarzona aplikacja**, aby wybrać aplikację, dla której chcesz zdefiniować zasady konfiguracji. Wybierz z listy programu Android for Work aplikacje zatwierdzone i zsynchronizowane z usługą Intune.
8. Wybierz pozycję **Ustawienia konfiguracji**. Konfigurację możesz ustawić przy użyciu następujących narzędzi:
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
- Główna nazwa użytkownika — na przykład **John@contoso.com**
- Poczta — na przykład **John@contoso.com**
- Częściowa nazwa UPN — na przykład **John**
- Identyfikator konta — na przykład **fc0dc142-71d8-4b12-bbea-bae2a8514c81**
- Identyfikator urządzenia — na przykład **b9841cd9-9843-405f-be28-b2265c59ef97**
- Identyfikator użytkownika — na przykład **3ec2c00f-b125-4519-acf0-302ac3761822**
- Nazwa użytkownika — na przykład **John Doe**


## <a name="enter-the-json-editor"></a>Edytor JSON

Nie jest możliwa konfiguracja niektórych ustawień konfiguracji aplikacji (np. typów pakietu) przy użyciu projektanta konfiguracji. W przypadku tych wartości niezbędne jest użycie edytora JSON. Ustawienia są dostarczane do aplikacji automatycznie po zainstalowaniu aplikacji.

1. Dla opcji **Format ustawień konfiguracji** wybierz opcję **Edytor JSON**.
2. W edytorze można zdefiniować wartości JSON dla ustawień konfiguracji. Możesz wybrać pozycję **Pobierz szablon JSON**, aby pobrać przykładowy plik, który można następnie skonfigurować.
3. Wybierz **OK**, a następnie wybierz pozycję **Dodaj**.

Zasady zostaną utworzone i wyświetlone w bloku listy zasad.

Po uruchomieniu przypisanej aplikacji na urządzeniu uruchamiane są ustawienia skonfigurowane w zasadach konfiguracji aplikacji.

## <a name="preconfigure-the-permissions-grant-state-for-apps"></a>Wstępna konfiguracja stanu uprawnień dla aplikacji

Możesz również wstępnie skonfigurować uprawnienia dla aplikacji pod kątem dostępu do funkcji urządzenia z systemem Android. Domyślnie aplikacje systemu Android, które wymagają uprawnień urządzenia, takich jak dostęp do lokalizacji lub aparatu urządzenia, wyświetlają monit o zaakceptowanie lub odrzucenie uprawnień przez użytkownika. Na przykład jeśli aplikacja używa mikrofonu urządzenia, użytkownik otrzyma monit o przyznanie aplikacji uprawnienia do użycia mikrofonu.

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. Wybierz pozycję **Mobile Apps**.
3. W obszarze **Zarządzaj** wybierz pozycję **Zasady konfiguracji** aplikacji, a następnie wybierz pozycję **Dodaj**.
4. Ustaw następujące szczegóły:
    - **Nazwa**. — nazwa profilu, która będzie wyświetlana w witrynie Azure Portal
    - **Opis**. — opis profilu, który będzie wyświetlany w witrynie Azure Portal
    - **Typ rejestracji urządzenia**. Wybierz pozycję **Urządzenia zarządzane**.
    - **Platforma**. Wybierz pozycję **Android for Work**.
5. Wybierz pozycję **Skojarzona aplikacja**, aby wybrać aplikację, dla której chcesz zdefiniować zasady konfiguracji. Wybierz z listy programu Android for Work aplikacje zatwierdzone i zsynchronizowane z usługą Intune.
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

