---
title: Dodawanie zasad konfiguracji aplikacji dla zarządzanych urządzeń z systemem Android Enterprise
titleSuffix: Microsoft Intune
description: Zasady konfiguracji aplikacji w usłudze Microsoft Intune umożliwiają określanie ustawień podczas uruchamiania aplikacji zarządzanego sklepu Google Play przez użytkowników.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/23/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 52c8d10f0b8d06d68d75450c3d708f910bc5ddd4
ms.sourcegitcommit: 51591b862d97904291af7aa53a6eb341b11a761e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2020
ms.locfileid: "77415039"
---
# <a name="add-app-configuration-policies-for-managed-android-enterprise-devices"></a>Dodawanie zasad konfiguracji aplikacji dla zarządzanych urządzeń z systemem Android Enterprise

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Zasady konfiguracji aplikacji w usłudze Microsoft Intune zawierają ustawienia dla aplikacji zarządzanego sklepu Google Play na zarządzanych urządzeniach z systemem Android Enterprise. Deweloper aplikacji uwidacznia ustawienia konfiguracji aplikacji zarządzanej przez system Android. Usługa Intune używa tych uwidocznionych ustawień, aby umożliwić administratorowi skonfigurowanie funkcji dla aplikacji. Zasady konfiguracji aplikacji są przypisane do Twoich grup użytkowników. Ustawienia zasad są stosowane, gdy aplikacja je wyszukuje (zazwyczaj podczas pierwszego uruchomienia aplikacji).

> [!NOTE]  
> Nie wszystkie aplikacje obsługują konfigurację aplikacji. Skontaktuj się z deweloperem aplikacji, aby dowiedzieć się, czy jego aplikacja obsługuje zasady konfiguracji aplikacji.

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz kolejno pozycje **Aplikacje** > **Zasady konfiguracji aplikacji** > **Dodaj** > **Urządzenia zarządzane**. Pamiętaj, że możesz wybrać między pozycjami **Urządzenia zarządzane** i **Aplikacje zarządzane**. Aby uzyskać więcej informacji, zobacz temat [Aplikacje obsługujące konfigurację aplikacji](~/apps/app-configuration-policies-overview.md#apps-that-support-app-configuration).
3. Na stronie **podstawowych informacji** ustaw następujące szczegóły:
    - **Nazwa** — nazwa profilu, która będzie wyświetlana w witrynie Azure Portal.
    - **Opis** — opis profilu, który będzie wyświetlany w witrynie Azure Portal.
    - **Typ rejestracji urządzenia** — to ustawienie ma wartość **Urządzenia zarządzane**.
4. Wybierz pozycję **Android Enterprise** w obszarze **Platforma**.
5. Kliknij pozycję **Wybierz aplikację** obok pozycji **Aplikacja docelowa**. Zostanie wyświetlone okienko **Skojarzona aplikacja**. 
6. W okienku **Skojarzona aplikacja** wybierz aplikację zarządzaną, która ma zostać skojarzona z zasadami konfiguracji, a następnie kliknij przycisk **OK**.
7. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Ustawienia**.
8. Kliknij przycisk **Dodaj**, aby wyświetlić okienko **Dodaj uprawnienia**.
9. Wybierz uprawnienia, które chcesz zastąpić. Przyznane uprawnienia zastąpią zasady „Domyślne uprawnienia aplikacji” dla wybranych aplikacji.
10. Ustaw **Stan uprawnienia** dla każdego uprawnienia. Możesz wybrać jedną z następujących wartości: **Monituj**, **Przyznaj automatycznie** lub **Odrzuć automatycznie**. Aby uzyskać więcej informacji o uprawnieniach, zobacz artykuł [Ustawienia urządzeń z rozwiązaniem Android Enterprise umożliwiające oznaczenie ich jako zgodne lub niezgodne w usłudze Intune](~/protect/compliance-policy-create-android-for-work.md).
11. W polu listy rozwijanej wybierz pozycję **Format ustawień konfiguracji**. Wybierz jedną z następujących metod, aby dodać informacje o konfiguracji:
    - **Korzystanie z projektanta konfiguracji**
    - **Wprowadzanie danych JSON**<br><br>
    Aby uzyskać szczegółowe informacje o używaniu projektanta konfiguracji, zobacz [Korzystanie z projektanta konfiguracji](#use-the-configuration-designer). Aby uzyskać szczegółowe informacji o wprowadzaniu danych XML, zobacz [Wprowadzanie danych JSON](#enter-json-data). 
12. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Przypisania**.
13. W polu listy rozwijanej obok pozycji **Przypisz do** wybierz pozycję **Wybrane grupy**, **Wszyscy użytkownicy**, **Wszystkie urządzenia** lub **Wszyscy użytkownicy i wszystkie urządzenia**, aby odpowiednio przypisać zasady konfiguracji aplikacji.

    ![Zrzut ekranu karty Dołącz okna przypisywania zasad](./media/app-configuration-policies-use-ios/app-config-policy01.png)

14. W polu listy rozwijanej wybierz pozycję **Wszyscy użytkownicy**.

    ![Zrzut ekranu przypisywania zasad — opcja listy rozwijanej Wszyscy użytkownicy](./media/app-configuration-policies-use-ios/app-config-policy02.png)

15. Kliknij pozycję **Wybierz grupy do wykluczenia**, aby wyświetlić powiązane okienko.

    ![Zrzut ekranu bloku Przypisanie zasad — Wybierz okienko Grupy do wykluczenia](./media/app-configuration-policies-use-ios/app-config-policy03.png)

16. Wybierz grupy, które chcesz wykluczyć, a następnie kliknij pozycję **Wybierz**.

    >[!NOTE]
    >Jeśli podczas dodawania grupy jakakolwiek inna grupa została już dołączona do danego typu przypisania, zostanie ona wstępnie wybrana i nie będzie zmieniana dla innych typów dołączania przypisania. W związku z tym ta grupa, który została użyta, nie może zostać użyta jako wykluczona grupa.

17. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Recenzja i tworzenie**.
18. Kliknij pozycję **Utwórz**, aby dodać zasady konfiguracji do usługi Intune.

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
| Identyfikator urządzenia w usłudze AAD | dc0dc142-11d8-4b12-bfea-cae2a8514c82 |
| Identyfikator konta | fc0dc142-71d8-4b12-bbea-bae2a8514c81 |
| Identyfikator urządzenia usługi Intune | b9841cd9-9843-405f-be28-b2265c59ef97 |
| Domena | contoso.com |
| Mail | john@contoso.com |
| Częściowa nazwa UPN | jan |
| Identyfikator użytkownika | 3ec2c00f-b125-4519-acf0-302ac3761822 |
| Nazwa użytkownika | Jan Kowalski |
| Nazwa główna użytkownika | john@contoso.com |


### <a name="allow-only-configured-organization-accounts-in-multi-identity-apps"></a>Zezwalanie tylko na skonfigurowane konta organizacji w aplikacjach z obsługą wielu tożsamości 

W przypadku urządzeń z systemem Android używaj następujących par klucz/wartość:

| **Klucz** | com.microsoft.intune.mam.AllowedAccountUPNs |
|---|---|
| **Wartości** | <ul><li>Jedna nazwa UPN lub więcej nazw UPN rozdzielonych znakiem <code>;</code>.</li><li>Jedynymi dopuszczonymi kontami są zarządzane konta użytkownika zdefiniowane przez ten klucz.</li><li> W przypadku urządzeń zarejestrowanych w usłudze Intune token <code>{{userprincipalname}}</code> może służyć do reprezentowania zarejestrowanego konta użytkownika.</li></ul> |

   > [!NOTE]
   > Zezwalając jedynie na skonfigurowane konta organizacji z wieloma tożsamościami, musisz używać programu Outlook dla systemu Android w wersji 2.2.222 lub nowszej, programów Word, Excel i PowerPoint dla systemu Android w wersji 16.0.9327.1000 lub nowszej bądź usługi OneDrive dla systemu Android w wersji 5.28 lub nowszej.<p></p>
   > Jako administrator usługi Microsoft Intune masz możliwość kontrolowania kont użytkownika dodawanych do aplikacji pakietu Microsoft Office na urządzeniach zarządzanych. Istnieje możliwość ograniczenia dostępu tylko do dozwolonych kont użytkowników w organizacji oraz blokowania kont osobistych na zarejestrowanych urządzeniach. Aplikacje pomocnicze przetwarzają konfigurację aplikacji i usuwają oraz blokują niezatwierdzone konta.<p></p>

## <a name="enter-json-data"></a>Wprowadzanie danych JSON

Nie jest możliwa konfiguracja niektórych ustawień konfiguracji aplikacji (np. typów pakietu) przy użyciu projektanta konfiguracji. W przypadku tych wartości użyj edytora JSON. Ustawienia są dostarczane do aplikacji automatycznie po zainstalowaniu aplikacji.

1. Dla opcji **Format ustawień konfiguracji** wybierz opcję **Edytor JSON**.
2. W edytorze można zdefiniować wartości JSON dla ustawień konfiguracji. Możesz wybrać pozycję **Pobierz szablon JSON**, aby pobrać przykładowy plik, który można następnie skonfigurować.
3. Wybierz **OK**, a następnie wybierz pozycję **Dodaj**.

Zasady zostaną utworzone i wyświetlone na liście.

Po uruchomieniu przypisanej aplikacji na urządzeniu uruchamiane są ustawienia skonfigurowane w zasadach konfiguracji aplikacji.

## <a name="preconfigure-the-permissions-grant-state-for-apps"></a>Wstępna konfiguracja stanu uprawnień dla aplikacji

Możesz również wstępnie skonfigurować uprawnienia aplikacji pod kątem dostępu do funkcji urządzenia z systemem Android. Domyślnie aplikacje systemu Android, które wymagają uprawnień urządzenia, takich jak dostęp do lokalizacji lub aparatu urządzenia, wyświetlają monit o zaakceptowanie lub odmowę przyznania uprawnień przez użytkownika.

Na przykład aplikacja używa mikrofonu urządzenia. Użytkownik otrzymuje monit o przyznanie aplikacji uprawnienia do korzystania z mikrofonu.

1. W [centrum administracyjnym programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) wybierz pozycję **Aplikacje** > **Zasady konfiguracji aplikacji** >  **Dodaj** > **Urządzenia zarządzane**.
2. Dodaj następujące właściwości:

    - **Nazwa**: wprowadź opisową nazwę zasad. Nadaj nazwę zasadom, aby można było je później łatwo rozpoznać. Na przykład dobrą nazwą zasad jest **Zasady aplikacji monitu o uprawnienia systemu Android Enterprise dla całej firmy**.
    - **Opis**. Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
    - **Typ rejestracji urządzenia**: to ustawienie ma wartość **Urządzenia zarządzane**.
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
- [Deploying Outlook for iOS and Android app configuration settings](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune) (Wdrażanie ustawień konfiguracji aplikacji Outlook dla systemów iOS, iPadOS i Android)

## <a name="next-steps"></a>Następne kroki

Kontynuuj [przypisywanie](apps-deploy.md) i [monitorowanie](apps-monitor.md) aplikacji.
