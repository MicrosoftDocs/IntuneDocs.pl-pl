---
title: Dodawanie zasad konfiguracji aplikacji dla zarządzanych urządzeń z systemem iOS
titlesuffix: Microsoft Intune
description: Informacje dotyczące korzystania z zasad konfiguracji aplikacji w celu przekazywania danych konfiguracyjnych do aplikacji dla systemu iOS po jej uruchomieniu.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/12/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 685803f6ef30994a943969e3642bd8349dcf9f6e
ms.sourcegitcommit: 874d9a00cc4666920069d54f99c6c2e687fa34a6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/13/2018
ms.locfileid: "53324943"
---
# <a name="add-app-configuration-policies-for-managed-ios-devices"></a>Dodawanie zasad konfiguracji aplikacji dla zarządzanych urządzeń z systemem iOS

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Zasady konfiguracji aplikacji w usłudze Microsoft Intune umożliwiają określenie niestandardowych ustawień konfiguracji dla aplikacji dla systemu iOS. Dzięki tym ustawieniom konfiguracji aplikację można dostosować na podstawie wskazówek dostawcy. Te ustawienia konfiguracji (klucze i wartości) należy uzyskać od dostawcy aplikacji. Aby skonfigurować aplikację, określ ustawienia jako klucze i wartości lub jako plik XML zawierający klucze i wartości. Ponadto zasad konfiguracji nie można przypisywać bezpośrednio do użytkowników i urządzeń. Zamiast tego należy skojarzyć je z aplikacją, a następnie przypisać tę aplikację. Ustawienia zasad konfiguracji są stosowane, gdy aplikacja je wyszukuje (zazwyczaj podczas pierwszego uruchomienia).

Po dodaniu zasad konfiguracji aplikacji możesz ustawić przypisania zasad konfiguracji aplikacji. Po ustawieniu przypisań dla zasad możesz dołączać i wykluczać grupy użytkowników, dla których zasady będą stosowane. Po wybraniu dołączenia co najmniej jednej grupy możesz wybrać określone grupy do dołączenia lub wybrać wbudowane grupy. Wbudowane grupy obejmują **Wszystkich użytkowników**, **Wszystkie urządzenia** i **Wszystkich użytkowników i wszystkie urządzenia**. 

>[!NOTE]
>Usługa Intune udostępnia w konsoli wstępnie utworzone grupy **Wszyscy użytkownicy** i **Wszystkie urządzenia** z wbudowanymi optymalizacjami dla wygody użytkownika. Zdecydowanie zaleca się używanie tych grup dla wszystkich użytkowników i wszystkich urządzeń zamiast wszelkich grup „Wszyscy użytkownicy” lub „Wszystkie urządzenia”, które mogły zostać utworzone samodzielnie.<p></p>
>Jako administrator usługi Microsoft Intune masz możliwość kontrolowania kont użytkownika dodawanych do aplikacji pakietu Microsoft Office na urządzeniach zarządzanych. Istnieje możliwość ograniczenia dostępu tylko do dozwolonych kont użytkowników w organizacji oraz blokowania kont osobistych na zarejestrowanych urządzeniach. Aplikacje pomocnicze przetwarzają konfigurację aplikacji i usuwają oraz blokują niezatwierdzone konta.

Po wybraniu dołączonych grup dla zasad konfiguracji aplikacji możesz też wybrać określone grupy, które mają zostać wykluczone. Aby uzyskać więcej informacji, zobacz [Dołączanie i wykluczanie przypisań aplikacji w usłudze Microsoft Intune](apps-inc-exl-assignments.md).

> [!TIP]
> Ten typ zasad jest obecnie dostępny tylko na urządzeniach z systemem iOS 8.0 lub nowszym. Obsługiwane są następujące typy instalacji aplikacji:
>
> -   **Zarządzana aplikacja systemu iOS ze sklepu App Store**
> -   **Pakiet aplikacji dla systemu iOS**
>
> Aby uzyskać więcej informacji na temat typów instalacji aplikacji, zobacz artykuł [How to add an app to Microsoft Intune](apps-add.md) (Jak dodać aplikację do usługi Microsoft Intune).

## <a name="create-an-app-configuration-policy"></a>Tworzenie zasad konfiguracji aplikacji

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. Wybierz obciążenie **Aplikacje klienckie**.
4. Wybierz pozycję **Zasady konfiguracji aplikacji** w grupie **Zarządzaj**, a następnie wybierz przycisk **Dodaj**.
5. Ustaw następujące szczegóły:
    - **Nazwa** — nazwa profilu, która będzie wyświetlana w witrynie Azure Portal.
    - **Opis** — opis profilu, który będzie wyświetlany w witrynie Azure Portal.
    - **Typ rejestracji urządzenia** — wybierz pozycję **Urządzenia zarządzane**.
6. Dla elementu **Platforma** wybierz pozycję **iOS**.
7.  Wybierz pozycję **Skojarzona aplikacja**. Następnie w okienku **Skojarzona aplikacja** wybierz aplikację zarządzaną, do której chcesz zastosować konfigurację, a następnie wybierz opcję **OK**.
8.  W okienku **Dodaj zasady konfiguracji** wybierz pozycję **Ustawienia konfiguracji**.
9. Wybierz pozycję **Format ustawień konfiguracji**. Aby dodać informacje XML, wybierz jeden z następujących tematów:
    - **Korzystanie z projektanta konfiguracji**
    - **Wprowadzanie danych XML**<br><br>
    Aby uzyskać szczegółowe informacje o używaniu projektanta konfiguracji, zobacz [Korzystanie z projektanta konfiguracji](#use-configuration-designer). Aby uzyskać szczegółowe informacji o wprowadzaniu danych XML, zobacz [Wprowadzanie danych XML](#enter-xml-data). 
10. Po dodaniu informacji XML wybierz przycisk **OK**, a następnie wybierz pozycję **Dodaj**, aby dodać zasady konfiguracji. Zostanie wyświetlone okienko omówienia zasad konfiguracji.
11. Wybierz pozycję **Przypisania**, aby wyświetlić opcje dołączania i wykluczania. 

    ![Zrzut ekranu karty Dołącz okna przypisywania zasad](./media/app-config-policy01.png)
12. Wybierz pozycję **Wszyscy użytkownicy** na karcie **Dołącz**.

    ![Zrzut ekranu przypisywania zasad — opcja listy rozwijanej Wszyscy użytkownicy](./media/app-config-policy02.png)
13. Wybierz kartę **Wyklucz**. 
14. Kliknij pozycję **Wybierz grupy do wykluczenia**, aby wyświetlić powiązane okienko.

    ![Zrzut ekranu bloku Przypisanie zasad — Wybierz grupy do wykluczenia](./media/app-config-policy03.png)
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

1. Wybierz przycisk wielokropka (**...**) obok ustawienia.
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

  -  Zobacz temat [Understand XML Property Lists (Listy właściwości XML)](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) w bibliotece deweloperów systemu iOS.

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

## <a name="monitor-ios--app-configuration-status-per-device"></a>Monitorowanie stanu konfiguracji aplikacji systemu iOS na poszczególnych urządzeniach 
Po przypisaniu zasad konfiguracji można monitorować stan konfiguracji aplikacji systemu iOS dla każdego zarządzanego urządzenia. W usłudze **Microsoft Intune** w witrynie Azure Portal wybierz pozycję **Urządzenia** > **Wszystkie urządzenia**. Z listy zarządzanych urządzeń wybierz konkretne urządzenie, aby wyświetlić blok dla tego urządzenia. W bloku urządzenia wybierz pozycję **Konfiguracja aplikacji**.  

## <a name="next-steps"></a>Następne kroki

Kontynuuj [przypisywanie](apps-deploy.md) i [monitorowanie](apps-monitor.md) aplikacji.
