---
title: Dodawanie zasad konfiguracji aplikacji dla zarządzanych urządzeń z systemem iOS
titleSuffix: Microsoft Intune
description: Informacje dotyczące korzystania z zasad konfiguracji aplikacji w celu przekazywania danych konfiguracyjnych do aplikacji dla systemu iOS po jej uruchomieniu.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/15/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 542d9c7890f9484311ca8e6400d0a75a41e13d7c
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71725702"
---
# <a name="add-app-configuration-policies-for-managed-ios-devices"></a>Dodawanie zasad konfiguracji aplikacji dla zarządzanych urządzeń z systemem iOS

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Zasady konfiguracji aplikacji w usłudze Microsoft Intune umożliwiają określenie niestandardowych ustawień konfiguracji dla aplikacji dla systemu iOS. Dzięki tym ustawieniom konfiguracji aplikację można dostosować na podstawie wskazówek dostawcy aplikacji. Te ustawienia konfiguracji (klucze i wartości) należy uzyskać od dostawcy aplikacji. Aby skonfigurować aplikację, określ ustawienia jako klucze i wartości lub jako plik XML zawierający klucze i wartości.

Jako administrator usługi Microsoft Intune masz możliwość kontrolowania kont użytkownika dodawanych do aplikacji pakietu Microsoft Office na urządzeniach zarządzanych. Istnieje możliwość ograniczenia dostępu tylko do dozwolonych kont użytkowników w organizacji oraz blokowania kont osobistych na zarejestrowanych urządzeniach. Aplikacje pomocnicze przetwarzają konfigurację aplikacji i usuwają oraz blokują niezatwierdzone konta. Ustawienia zasad konfiguracji są stosowane, gdy aplikacja je wyszukuje (zazwyczaj podczas pierwszego uruchomienia).

Po dodaniu zasad konfiguracji aplikacji możesz ustawić przypisania zasad konfiguracji aplikacji. Po ustawieniu przypisań dla zasad możesz dołączać i wykluczać grupy użytkowników, dla których zasady będą stosowane. Po wybraniu dołączenia co najmniej jednej grupy możesz wybrać określone grupy do dołączenia lub wybrać wbudowane grupy. Wbudowane grupy obejmują **Wszystkich użytkowników**, **Wszystkie urządzenia** i **Wszystkich użytkowników i wszystkie urządzenia**. 

> [!NOTE]
> Usługa Intune udostępnia w konsoli wstępnie utworzone grupy **Wszyscy użytkownicy** i **Wszystkie urządzenia** z wbudowanymi optymalizacjami dla wygody użytkownika. Zdecydowanie zaleca się używanie tych grup dla wszystkich użytkowników i wszystkich urządzeń zamiast wszelkich grup „Wszyscy użytkownicy” lub „Wszystkie urządzenia”, które mogły zostać utworzone samodzielnie.

Po wybraniu dołączonych grup dla zasad konfiguracji aplikacji możesz też wybrać określone grupy, które mają zostać wykluczone. Aby uzyskać więcej informacji, zobacz [Dołączanie i wykluczanie przypisań aplikacji w usłudze Microsoft Intune](apps-inc-exl-assignments.md).

> [!TIP]
> Ten typ zasad jest obecnie dostępny tylko na urządzeniach z systemem iOS 8.0 lub nowszym. Obsługiwane są następujące typy instalacji aplikacji:
>
> - **Zarządzana aplikacja systemu iOS ze sklepu App Store**
> - **Pakiet aplikacji dla systemu iOS**
>
> Aby uzyskać więcej informacji na temat typów instalacji aplikacji, zobacz artykuł [How to add an app to Microsoft Intune](apps-add.md) (Jak dodać aplikację do usługi Microsoft Intune). Aby uzyskać więcej informacji dotyczących dołączania konfiguracji aplikacji do pakietu aplikacji .ipa dla zarządzanych urządzeń, zobacz temat Managed App Configuration (Konfiguracja zarządzanych aplikacji) w [dokumentacji dla deweloperów systemu iOS](https://developer.apple.com/library/archive/samplecode/sc2279/Introduction/Intro.html).

## <a name="create-an-app-configuration-policy"></a>Tworzenie zasad konfiguracji aplikacji

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Wybierz obciążenie **Aplikacje klienckie**.
4. Wybierz pozycję **Zasady konfiguracji aplikacji** w grupie **Zarządzaj**, a następnie wybierz przycisk **Dodaj**.
5. Ustaw następujące szczegóły:
    - **Nazwa** — nazwa profilu, która będzie wyświetlana w witrynie Azure Portal.
    - **Opis** — opis profilu, który będzie wyświetlany w witrynie Azure Portal.
    - **Typ rejestracji urządzeń** — wybierz pozycję **Zarządzane urządzenia** dla urządzeń, które zostały zarejestrowane w usłudze Intune.
6. Dla elementu **Platforma** wybierz pozycję **iOS**.
7. Wybierz pozycję **Skojarzona aplikacja**. Następnie w okienku **Skojarzona aplikacja** wybierz aplikację zarządzaną, do której chcesz zastosować konfigurację, a następnie wybierz opcję **OK**.
8. W okienku **Dodaj zasady konfiguracji** wybierz pozycję **Ustawienia konfiguracji**.
9. Wybierz pozycję **Format ustawień konfiguracji**. Wybierz jedną z następujących metod, aby dodać informacje o konfiguracji:
    - **Korzystanie z projektanta konfiguracji**
    - **Wprowadzanie danych XML**<br><br>
    Aby uzyskać szczegółowe informacje o używaniu projektanta konfiguracji, zobacz [Korzystanie z projektanta konfiguracji](#use-configuration-designer). Aby uzyskać szczegółowe informacji o wprowadzaniu danych XML, zobacz [Wprowadzanie danych XML](#enter-xml-data). 
10. Po dodaniu informacji dotyczących konfiguracji wybierz przycisk **OK**, a następnie wybierz pozycję **Dodaj**, aby dodać zasady konfiguracji. Zostanie wyświetlone okienko omówienia zasad konfiguracji.
11. Wybierz pozycję **Przypisania**, aby wyświetlić opcje dołączania i wykluczania. 

    ![Zrzut ekranu karty Dołącz okna przypisywania zasad](./media/app-configuration-policies-use-ios/app-config-policy01.png)
12. Wybierz pozycję **Wszyscy użytkownicy** na karcie **Dołącz**.

    ![Zrzut ekranu przypisywania zasad — opcja listy rozwijanej Wszyscy użytkownicy](./media/app-configuration-policies-use-ios/app-config-policy02.png)
13. Wybierz kartę **Wyklucz**. 
14. Kliknij pozycję **Wybierz grupy do wykluczenia**, aby wyświetlić powiązane okienko.

    ![Zrzut ekranu bloku Przypisanie zasad — Wybierz grupy do wykluczenia](./media/app-configuration-policies-use-ios/app-config-policy03.png)
15. Wybierz grupy, które chcesz wykluczyć, a następnie kliknij pozycję **Wybierz**.

    >[!NOTE]
    >Jeśli podczas dodawania grupy jakakolwiek inna grupa została już dołączona do danego typu przypisania, zostanie ona wstępnie wybrana i nie będzie zmieniana dla innych typów dołączania przypisania. W związku z tym ta grupa, który została użyta, nie może zostać użyta jako wykluczona grupa.
16. Kliknij polecenie **Zapisz**.

## <a name="use-configuration-designer"></a>Korzystanie z projektanta konfiguracji

Usługa Microsoft Intune dostarcza ustawienia konfiguracji, które są unikatowe dla aplikacji. Projektanta konfiguracji można używać w przypadku aplikacji na urządzeniach zarejestrowanych lub niezarejestrowanych w usłudze Microsoft Intune. Projektant umożliwia skonfigurowanie określonych kluczy i wartości konfiguracji, które pomagają w utworzeniu bazowego pliku XML. Dla każdej wartości należy również wskazać typ danych. Te ustawienia są dostarczane do aplikacji automatycznie po zainstalowaniu aplikacji.

### <a name="add-a-setting"></a>Dodawanie ustawienia

1. Dla każdego klucza i wartości konfiguracji ustaw następujące elementy:
   - **Klucz konfiguracji** — klucz, który jednoznacznie identyfikuje konfigurację określonego ustawienia.
   - **Typ wartości** — typ danych wartości konfiguracji. Typy obejmują liczby całkowite, liczby rzeczywiste, ciągi i wartości logiczne.
   - **Wartość konfiguracji** — wartość dla danej konfiguracji.
2. Wybierz przycisk **OK**, aby zastosować ustawienia konfiguracji.

### <a name="delete-a-setting"></a>Usuwanie ustawienia

1. Wybierz przycisk wielokropka ( **...** ) obok ustawienia.
2. Wybierz pozycję **Usuń**.

Znaki \{\{ i \}\} są używane tylko przez typy tokenów i nie mogą być używane do innych celów.

### <a name="allow-only-configured-organization-accounts-in-multi-identity-apps"></a>Zezwalanie tylko na skonfigurowane konta organizacji w aplikacjach z obsługą wielu tożsamości 

W przypadku urządzeń z systemem iOS używaj następujących par klucz/wartość:

| **Klucz** | IntuneMAMAllowedAccountsOnly |
|--------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Wartości** | <ul><li>**Włączone**: jedynym dozwolonym kontem jest zarządzane konto użytkownika zdefiniowane za pomocą klucza [IntuneMAMUPN](data-transfer-between-apps-manage-ios.md#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm).</li><li>**Wyłączone** (lub dowolna wartość, która nie stanowi dopasowania do opcji **Włączone** bez uwzględniania wielkości liter): każde konto jest dozwolone.</li></ul> |.

   > [!NOTE]
   > W przypadku zezwalania wyłącznie na skonfigurowane konta organizacji w aplikacjach z obsługą wielu tożsamości należy użyć usługi OneDrive dla systemu iOS 10.34 lub jego nowszej wersji bądź programu Outlook dla systemu iOS 2.99.0 lub jego nowszej wersji, a w aplikacji należy zastosować [zasady ochrony aplikacji usługi Intune](app-protection-policy.md).

## <a name="enter-xml-data"></a>Wprowadzanie danych XML

Możesz wpisać lub wkleić listę właściwości XML zawierającą ustawienia konfiguracji aplikacji dla urządzeń zarejestrowanych w usłudze Intune. Format listy właściwości XML różni się zależnie od konfigurowanej aplikacji. Aby uzyskać szczegółowe informacje na temat dokładnego formatu do użycia, skontaktuj się z dostawcą aplikacji.

Usługa Intune weryfikuje format XML. Nie sprawdza ona jednak, czy lista właściwości XML (PList) współpracuje z docelową aplikacją.

Aby dowiedzieć się więcej na temat list właściwości XML:

- Zobacz temat [Understand XML Property Lists (Listy właściwości XML)](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) w bibliotece deweloperów systemu iOS.

### <a name="example-format-for-an-app-configuration-xml-file"></a>Przykładowy format pliku XML konfiguracji aplikacji

Podczas tworzenia pliku konfiguracji aplikacji można określić co najmniej jedną z poniższych wartości, używając następującego formatu:

```xml
<dict>
  <key>userprincipalname</key>
  <string>{{userprincipalname}}</string>
  <key>mail</key>
  <string>{{mail}}</string>
  <key>partialupn</key>
  <string>{{partialupn}}</string>
  <key>accountid</key>
  <string>{{accountid}}</string>
  <key>deviceid</key>
  <string>{{deviceid}}</string>
  <key>userid</key>
  <string>{{userid}}</string>
  <key>username</key>
  <string>{{username}}</string>
  <key>serialnumber</key>
  <string>{{serialnumber}}</string>
  <key>serialnumberlast4digits</key>
  <string>{{serialnumberlast4digits}}</string>
  <key>udidlast4digits</key>
  <string>{{udidlast4digits}}</string>
  <key>aaddeviceid</key>
  <string>{{aaddeviceid}}</string>
</dict>
```

### <a name="supported-xml-plist-data-types"></a>Obsługiwane typy danych XML PList

Usługa Intune obsługuje następujące typy danych na liście właściwości:

- &lt;integer&gt;
- &lt;real&gt;
- &lt;string&gt;
- &lt;array&gt;
- &lt;dict&gt;
- &lt;true /&gt; lub &lt;false /&gt;

### <a name="tokens-used-in-the-property-list"></a>Tokeny używane na liście właściwości

Ponadto usługa Intune obsługuje następujące typy tokenów na liście właściwości:
- \{\{userprincipalname\}\}—na przykład **John@contoso.com**
- \{\{mail\}\}—na przykład **John@contoso.com**
- \{\{partialupn\}\}—na przykład **Jan**
- \{\{accountid\}\}—na przykład **fc0dc142-71d8-4b12-bbea-bae2a8514c81**
- \{\{deviceid\}\}—na przykład **b9841cd9-9843-405f-be28-b2265c59ef97**
- \{\{userid\}\}—na przykład **3ec2c00f-b125-4519-acf0-302ac3761822**
- \{\{username\}\}—na przykład **Jan Nowak**
- \{\{serialnumber\}\}—na przykład **F4KN99ZUG5V2** (dla urządzeń z systemem iOS)
- \{\{serialnumberlast4digits\}\}—na przykład **G5V2** (dla urządzeń z systemem iOS)
- \{\{aaddeviceid\}\} — na przykład **ab0dc123-45d6-7e89-aabb-cde0a1234b56**

## <a name="configure-the-company-portal-app-to-support-ios-dep-devices"></a>Konfigurowanie aplikacji Portal firmy na potrzeby obsługi urządzeń DEP z systemem iOS

Rejestracje programu DEP (Device Enrollment Program firmy Apple) nie są zgodne z wersją aplikacji Portal firmy ze sklepu z aplikacjami. Można jednak skonfigurować aplikację Portal firmy do obsługi urządzeń DEP z systemem iOS, wykonując następujące czynności.

1. W usłudze Intune w witrynie Azure Portal:
    - Jeśli to konieczne dodaj aplikację Intune — Portal firmy, przechodząc do pozycji **Intune** > **Aplikacje klienckie** > **Aplikacje** > **Dodaj**.
    - Przejdź do pozycji **Aplikacje klienckie** > **Zasady konfiguracji aplikacji**, aby utworzyć zasady konfiguracji aplikacji dla aplikacji Portal firmy.
2. Utwórz zasady konfiguracji aplikacji za pomocą pliku XML poniżej. Więcej informacji na temat tworzenia zasad konfiguracji aplikacji oraz wprowadzania danych XML można znaleźć w temacie [Add app configuration policies for managed iOS devices](app-configuration-policies-use-ios.md) (Dodawanie zasad konfiguracji aplikacji w przypadku zarządzanych urządzeń z systemem iOS) lub w przypadku hybrydowej usługi MDM w temacie [Apply settings to iOS apps with app configuration policies in System Center Configuration Manager](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-ios-apps-with-app-configuration-policies) (Wprowadzanie ustawień w aplikacjach iOS z zastosowaniem zasad konfiguracji aplikacji w programie System Center Configuration Manager).

    ``` xml
    <dict>
        <key>IntuneCompanyPortalEnrollmentAfterUDA</key>
        <dict>
            <key>IntuneDeviceId</key>
            <string>{{deviceid}}</string>
            <key>UserId</key>
            <string>{{userid}}</string>
        </dict>
    </dict>
    ```

3. Wdróż aplikację Portal firmy na urządzeniach z zasadami konfiguracji aplikacji przeznaczonymi dla żądanych grup. Pamiętaj, aby wdrażać tylko zasady w grupach urządzeń, które są już zarejestrowane w programie DEP.
4. Poinformuj użytkowników końcowych, że powinni zalogować się w aplikacji Portal firmy po jej automatycznym zainstalowaniu.

## <a name="monitor-ios--app-configuration-status-per-device"></a>Monitorowanie stanu konfiguracji aplikacji systemu iOS na poszczególnych urządzeniach 
Po przypisaniu zasad konfiguracji można monitorować stan konfiguracji aplikacji systemu iOS dla każdego zarządzanego urządzenia. W usłudze **Microsoft Intune** w witrynie Azure Portal wybierz pozycję **Urządzenia** > **Wszystkie urządzenia**. Z listy zarządzanych urządzeń wybierz konkretne urządzenie, aby wyświetlić blok dla tego urządzenia. W bloku urządzenia wybierz pozycję **Konfiguracja aplikacji**.  

## <a name="additional-information"></a>Dodatkowe informacje

- [Deploying Outlook for iOS and Android app configuration settings](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune) (Wdrażanie ustawień konfiguracji aplikacji Outlook dla systemu iOS i Android)

## <a name="next-steps"></a>Następne kroki

Kontynuuj [przypisywanie](apps-deploy.md) i [monitorowanie](apps-monitor.md) aplikacji.