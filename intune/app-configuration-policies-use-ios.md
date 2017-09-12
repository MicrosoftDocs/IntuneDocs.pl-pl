---
title: "Jak korzystać z zasad konfiguracji aplikacji usługi Intune dla systemu iOS"
titlesuffix: Azure portal
description: "Informacje dotyczące korzystania z zasad konfiguracji aplikacji w celu przekazywania danych konfiguracyjnych do aplikacji dla systemu iOS po jej uruchomieniu."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/26/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bc42f3cafa83b5f7ba053d03dbd066b725bb1fee
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-use-microsoft-intune-app-configuration-policies-for-ios"></a>Jak używać zasad konfiguracji aplikacji usługi Microsoft Intune dla systemu iOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Zasady konfiguracji aplikacji w usłudze Microsoft Intune umożliwiają określanie wartości ustawień, które są używane, gdy użytkownicy uruchamiają aplikację dla systemu iOS. Aplikacja może na przykład wymagać, aby użytkownicy określili:

-   Niestandardowy numer portu

-   Ustawienia języka

-   Ustawienia zabezpieczeń

-   Ustawienia oznaczeń marki, takich jak logo firmy

Nieprawidłowe określenie tych ustawień przez użytkowników może zwiększyć obciążenie działu pomocy technicznej i spowolnić wdrażanie technologii nowych aplikacji.

Zasady konfiguracji aplikacji mogą pomóc wyeliminować te problemy, umożliwiając przypisanie tych ustawień do użytkowników w zasadach, zanim uruchomią oni aplikację. Ustawienia są następnie określane automatycznie, a użytkownicy nie muszą podejmować żadnej akcji. Aplikacje muszą być napisane tak, aby obsługiwały korzystanie z konfiguracji aplikacji. Aby uzyskać więcej informacji, skonsultuj się z dostawcą aplikacji.

Tych zasad nie można przypisywać bezpośrednio do użytkowników i urządzeń. W zamian należy skojarzyć je z aplikacją, a następnie przypisać tę aplikację. Ustawienia zasad są stosowane zawsze, gdy aplikacja ich szuka (zazwyczaj podczas pierwszego uruchomienia).

> [!TIP]
> Ten typ zasad jest obecnie dostępny tylko na urządzeniach z systemem iOS 8.0 lub nowszym. Obsługiwane są następujące typy instalacji aplikacji:
>
> -   **Zarządzana aplikacja systemu iOS ze sklepu App Store**
> -   **Pakiet aplikacji dla systemu iOS**
>
> Aby uzyskać więcej informacji na temat typów instalacji aplikacji, zobacz artykuł [How to add an app to Microsoft Intune](apps-add.md) (Jak dodać aplikację do usługi Microsoft Intune).

## <a name="create-an-app-configuration-policy"></a>Tworzenie zasad konfiguracji aplikacji
1.  Zaloguj się do portalu Azure Portal.
2.  Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3.  W bloku **Intune** wybierz pozycję **Aplikacje mobilne**.
4.  W obciążeniu **Aplikacje mobilne** wybierz kolejno pozycje **Zarządzaj** > **Zasady konfiguracji aplikacji**.
5.  W bloku listy zasad wybierz przycisk **Dodaj**.
6.  W bloku **Dodawanie zasad konfiguracji** podaj nazwę (**Nazwa**) oraz opcjonalny opis (**Opis**) zasad konfiguracji aplikacji.
7.  Jako wartość pozycji **Typ rejestracji urządzenia** wybierz jedną z następujących:
    - **Zarejestrowane w usłudze Intune** — dla aplikacji zarządzanych przez usługę Intune.
    - **Niezarejestrowane w usłudze Intune** — dla aplikacji, które nie są zarządzane przez usługę Intune lub są zarządzane przez inne rozwiązanie.
8.  W pozycji **Platforma** wybierz **iOS** (tylko w przypadku urządzeń zarejestrowanych w usłudze Intune)
9.  Wybierz pozycję **Skojarzona aplikacja**, po czym w bloku **Skojarzona aplikacja** wybierz aplikację zarządzaną, do której chcesz zastosować konfigurację.
10. W bloku **Dodaj zasady konfiguracji** wybierz pozycję **Ustawienia konfiguracji**.
11. W bloku **Ustawienia konfiguracji** wybierz, jak chcesz określić wartości XML, które składają się na profil konfiguracji:
    - **Wprowadź dane XML** (tylko w przypadku urządzeń zarejestrowanych w usłudze Intune) — wprowadź lub wklej listę właściwości XML zawierającą wybrane ustawienia konfiguracji aplikacji. Format listy właściwości XML różni się zależnie od konfigurowanej aplikacji. Szczegółowe informacje na temat dokładnego formatu do użycia możesz uzyskać od dostawcy aplikacji.
Usługa Intune sprawdza, czy wprowadzony kod XML ma prawidłowy format. Nie sprawdza ona, czy lista właściwości XML współdziała z aplikacją, z którą została skojarzona.
Aby dowiedzieć się więcej na temat list właściwości XML, zobacz [Informacje na temat list właściwości XML](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) w bibliotece deweloperów systemu iOS.
    - **Użyj projektanta konfiguracji** (bez względu na to, czy urządzenie jest zarejestrowane w usłudze Intune, czy nie) — umożliwia określenie par kluczy i wartości XML bezpośrednio w portalu.
11. Gdy skończysz, wróć do bloku **Dodawanie zasad konfiguracji** i wybierz pozycję **Utwórz**.

Zasady zostaną utworzone i wyświetlone w bloku listy zasad.



>[!Note]
>Z [zestawu SDK aplikacji usługi Intune](https://docs.microsoft.com/intune/app-sdk-ios) można korzystać w celu przygotowywania aplikacji biznesowych, które będą zarządzane przez zasady ochrony aplikacji usługi Intune i zasady konfiguracji aplikacji — niezależnie od tego, czy urządzenie jest zarejestrowane w usłudze Intune, czy nie. Na przykład można użyć zasad konfiguracji aplikacji do konfigurowania dozwolonych i zablokowanych adresów URL dla programu [Intune Managed Browser](app-configuration-managed-browser.md). Gdy aplikacja jest zgodna z tymi zasadami, można ją skonfigurować przy użyciu zasad.


Po uruchomieniu przypisanej aplikacji na urządzeniu uruchamiane są ustawienia skonfigurowane w zasadach konfiguracji aplikacji.
Zobacz dokumentację dla aplikacji, którą konfigurujesz, aby uzyskać informacje o tym, co się stanie w przypadku konfliktu z co najmniej jedną zasadą konfiguracji aplikacji.

>[!Tip]
>Ponadto w celu wykonywania tych zadań można używać interfejsu API programu Graph. Aby uzyskać więcej informacji, zobacz [Graph API Reference MAM Targeted Config](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create) (Dokumentacja interfejsu API programu Graph — konfiguracja podlegająca zarządzaniu aplikacjami mobilnymi).


## <a name="information-about-the-xml-file-format"></a>Informacje o formacie pliku XML

Usługa Intune obsługuje następujące typy danych na liście właściwości:

- &lt;integer&gt;
- &lt;real&gt;
- &lt;string&gt;
- &lt;array&gt;
- &lt;dict&gt;
- &lt;true /&gt; lub &lt;false /&gt;

Aby uzyskać więcej informacji na temat typów danych, zobacz temat [Listy właściwości — informacje](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/AboutPropertyLists/AboutPropertyLists.html) w bibliotece deweloperów systemu iOS.

Ponadto usługa Intune obsługuje następujące typy tokenów na liście właściwości:
- \{\{userprincipalname\}\} — (przykład: **John@contoso.com**)
- \{\{mail\}\} — (przykład: **John@contoso.com**)
- \{\{partialupn\}\} — (przykład: **Michał**)
- \{\{accountid\}\} -—(przykład: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**)
- \{\{deviceid\}\} — (przykład: **b9841cd9-9843-405f-be28-b2265c59ef97**)
- \{\{userid\}\} — (przykład: **3ec2c00f-b125-4519-acf0-302ac3761822**)
- \{\{username\}\} — (przykład: **Michał Kowalski**)
- \{\{serialnumber\}\} — (przykład: **F4KN99ZUG5V2**) dla urządzeń z systemem iOS
- \{\{serialnumberlast4digits\}\} — (przykład: **G5V2**) dla urządzeń z systemem iOS

Znaki \{\{ i \}\} są używane tylko przez typy tokenów i nie mogą być używane do innych celów.

## <a name="example-format-for-an-app-configuration-xml-file"></a>Przykładowy format pliku XML konfiguracji aplikacji

Podczas tworzenia pliku konfiguracji aplikacji można określić co najmniej jedną z poniższych wartości, używając następującego formatu:

```
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
</dict>

```

## <a name="next-steps"></a>Następne kroki

Kontynuuj [przypisywanie](apps-deploy.md) i [monitorowanie](apps-monitor.md) aplikacji tak jak dotychczas.