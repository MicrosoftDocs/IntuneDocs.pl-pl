---
title: "Jak używać zasad konfiguracji aplikacji usługi Intune | Wersja zapoznawcza usługi Intune Azure | Dokumentacja firmy Microsoft"
description: "Wersja zapoznawcza usługi Intune Azure: informacje dotyczące korzystania z zasad konfiguracji aplikacji w celu przekazywania danych konfiguracyjnych do aplikacji dla systemu iOS po jej uruchomieniu."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 424fae862592c1ab5b4221fb5ad40a52c39f6760
ms.openlocfilehash: 75e3f3f62dd392cda1530321b12cd27e9ee8847f

---

# <a name="how-to-use-intune-app-configuration-policies"></a>Jak korzystać z zasad konfiguracji aplikacji usługi Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Zasady konfiguracji aplikacji w usłudze Microsoft Intune umożliwiają określanie wartości ustawień, które mogą być wymagane, jeśli użytkownicy uruchamiają aplikację. Aplikacja może na przykład wymagać, aby użytkownicy określili:

-   Niestandardowy numer portu

-   Ustawienia języka

-   Ustawienia zabezpieczeń

-   Ustawienia oznaczeń marki, takich jak logo firmy

Nieprawidłowe określenie tych ustawień przez użytkowników może zwiększyć obciążenie działu pomocy technicznej i spowolnić wdrażanie technologii nowych aplikacji.

Zasady konfiguracji aplikacji mogą pomóc wyeliminować te problemy, umożliwiając przypisanie tych ustawień do użytkowników w zasadach, zanim uruchomią oni aplikację. Ustawienia są następnie określane automatycznie, a użytkownicy nie muszą podejmować żadnej akcji.

Tych zasad nie można przypisywać bezpośrednio do użytkowników i urządzeń. W zamian należy skojarzyć je z aplikacją, a następnie wdrożyć tę aplikację. Ustawienia zasad będą stosowane zawsze, gdy aplikacja będzie je wyszukiwać (zazwyczaj podczas pierwszego uruchomienia).

> [!TIP]
> Ten typ zasad jest obecnie dostępny tylko na urządzeniach z systemem iOS 8.0 lub nowszym. Obsługiwane są następujące typy instalacji aplikacji:
>
> -   **Zarządzana aplikacja systemu iOS ze sklepu App Store**
> -   **Pakiet aplikacji dla systemu iOS**
>
> Aby uzyskać więcej informacji na temat typów instalacji aplikacji, zobacz artykuł [How to add an app to Microsoft Intune](/intune-azure/manage-apps/add-apps) (Jak dodać aplikację do usługi Microsoft Intune).

## <a name="create-an-app-configuration-policy"></a>Tworzenie zasad konfiguracji aplikacji

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno pozycje **Więcej usług** > **Inne** > **Intune**.
3. W bloku **Intune** wybierz opcję **Zarządzaj aplikacjami**.
1.  W obciążeniu **Zarządzaj aplikacjami** wybierz kolejno pozycje **Zarządzaj** > **Zasady konfiguracji aplikacji**.

2.  W bloku listy zasad wybierz przycisk **Dodaj**.

3.  W bloku **Dodawanie zasad konfiguracji** podaj nazwę oraz opcjonalny opis zasad konfiguracji aplikacji.
4.  Wybierz pozycję **Skojarzona aplikacja**, po czym w bloku **Skojarzona aplikacja** wybierz aplikację zarządzaną, do której chcesz zastosować konfigurację.
5.  W bloku **Dodawanie zasad konfiguracji** wybierz pozycję **Ustawienia konfiguracji**, a następnie w bloku Ustawienia konfiguracji wybierz, jak chcesz określić wartości XML, które składają się na profil konfiguracji:
    - **Wprowadź dane XML** — wprowadź lub wklej listę właściwości XML zawierającą wybrane ustawienia konfiguracji aplikacji. Format listy właściwości XML różni się zależnie od konfigurowanej aplikacji. Szczegółowe informacje na temat dokładnego formatu do użycia możesz uzyskać od dostawcy aplikacji.
    Usługa Intune sprawdza, czy wprowadzony kod XML ma prawidłowy format. Nie sprawdza ona, czy lista właściwości XML będzie współdziałać z aplikacją, z którą została skojarzona.
    Aby dowiedzieć się więcej na temat list właściwości XML, zobacz [Informacje na temat list właściwości XML](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) w bibliotece deweloperów systemu iOS.
    - **Użyj projektanta konfiguracji** — umożliwia określenie par kluczy i wartości XML bezpośrednio w portalu.
8. Gdy skończysz, wróć do bloku **Dodawanie zasad konfiguracji** i wybierz pozycję **Utwórz**.

Zasady zostaną utworzone i wyświetlone w bloku listy zasad.

Następnie kontynuuj [przypisywanie](deploy-apps.md) i [monitorowanie](monitor-apps.md) aplikacji jak do tej pory.

Po uruchomieniu przypisanej aplikacji na urządzeniu zostaną uruchomione ustawienia skonfigurowane w zasadach konfiguracji aplikacji.

> [!TIP]
> Jeśli nawet jedna zasada konfiguracji aplikacji pozostaje w konflikcie, żadna zasada nie zostanie wymuszona.

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



<!--HONumber=Feb17_HO1-->


