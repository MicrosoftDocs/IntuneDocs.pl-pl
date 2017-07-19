---
title: "Jak korzystać z zasad konfiguracji aplikacji usługi Intune dla systemu iOS"
titleSuffix: Intune on Azure
description: "Informacje dotyczące korzystania z zasad konfiguracji aplikacji w celu przekazywania danych konfiguracyjnych do aplikacji dla systemu iOS po jej uruchomieniu."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 112f60ff208c27825ddd0f4c812535b255894333
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/03/2017
---
# <a name="how-to-use-microsoft-intune-app-configuration-policies-for-ios"></a>Jak używać zasad konfiguracji aplikacji usługi Microsoft Intune dla systemu iOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Zasady konfiguracji aplikacji w usłudze Microsoft Intune umożliwiają określanie wartości ustawień, które mogą być wymagane, jeśli użytkownicy uruchamiają aplikację dla systemu iOS. Aplikacja może na przykład wymagać, aby użytkownicy określili:

-   Niestandardowy numer portu

-   Ustawienia języka

-   Ustawienia zabezpieczeń

-   Ustawienia oznaczeń marki, takich jak logo firmy

Nieprawidłowe określenie tych ustawień przez użytkowników może zwiększyć obciążenie działu pomocy technicznej i spowolnić wdrażanie technologii nowych aplikacji.

Zasady konfiguracji aplikacji mogą pomóc wyeliminować te problemy, umożliwiając przypisanie tych ustawień do użytkowników w zasadach, zanim uruchomią oni aplikację. Ustawienia są następnie określane automatycznie, a użytkownicy nie muszą podejmować żadnej akcji.

Tych zasad nie można przypisywać bezpośrednio do użytkowników i urządzeń. W zamian należy skojarzyć je z aplikacją, a następnie przypisać tę aplikację. Ustawienia zasad będą stosowane zawsze, gdy aplikacja będzie je wyszukiwać (zazwyczaj podczas pierwszego uruchomienia).

> [!TIP]
> Ten typ zasad jest obecnie dostępny tylko na urządzeniach z systemem iOS 8.0 lub nowszym. Obsługiwane są następujące typy instalacji aplikacji:
>
> -   **Zarządzana aplikacja systemu iOS ze sklepu App Store**
> -   **Pakiet aplikacji dla systemu iOS**
>
> Aby uzyskać więcej informacji na temat typów instalacji aplikacji, zobacz artykuł [How to add an app to Microsoft Intune](apps-add.md) (Jak dodać aplikację do usługi Microsoft Intune).

## <a name="create-an-app-configuration-policy"></a>Tworzenie zasad konfiguracji aplikacji

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz pozycję **Aplikacje mobilne**.
1.  W obciążeniu **Aplikacje mobilne** wybierz kolejno pozycje **Zarządzaj** > **Zasady konfiguracji aplikacji**.

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

Następnie kontynuuj [przypisywanie](apps-deploy.md) i [monitorowanie](apps-monitor.md) aplikacji jak do tej pory.

Po uruchomieniu przypisanej aplikacji na urządzeniu zostaną uruchomione ustawienia skonfigurowane w zasadach konfiguracji aplikacji.

> [!TIP]
> Jeśli nawet jedna zasada konfiguracji aplikacji pozostaje w konflikcie, żadna zasada nie zostanie wymuszona.

## <a name="create-a-mam-targeted-configuration-policy"></a>Tworzenie zasad docelowej konfiguracji MAM
Docelowa konfiguracja MAM umożliwia aplikacjom odbieranie danych konfiguracji za pośrednictwem zestawu SDK aplikacji usługi Intune. Format i odmiany tych danych muszą zostać zdefiniowane i przekazane klientom usługi Intune przez właściciela/dewelopera aplikacji. Administratorzy usługi Intune mogą przekazywać dane konfiguracji do miejsc docelowych i wdrażać te dane za pośrednictwem konsoli usługi Intune na platformie Azure. Dane docelowej konfiguracji MAM mogą zostać dostarczone za pośrednictwem usługi MAM do aplikacji z obsługą mechanizmów MAM-WE. Konfigurowanie list dozwolonych i zablokowanych adresów URL jest możliwie na przykład w programie [Intune Managed Browser](https://docs.microsoft.com/intune/app-configuration-managed-browser). Dane konfiguracji aplikacji zostaną przypisane do aplikacji bezpośrednio za pośrednictwem naszej usługi MAM zamiast za pośrednictwem kanału zarządzania urządzeniami mobilnymi (MDM). [Zasady konfiguracji aplikacji w ramach kanału MDM](https://docs.microsoft.com/intune/app-configuration-policies-use-ios#create-an-app-configuration-policy) stanowią natywne rozwiązanie realizowane w ramach zarządzania urządzeniami przenośnymi. Najważniejsza różnica, która odróżnia tę metodę od konfiguracji docelowej MAM, to fakt, że urządzenie, na którym jest uruchamiana aplikacja, nie musi być zarejestrowane przez funkcję MDM. Docelowa konfiguracja MAM jest dostępna w przypadku urządzeń z systemem iOS i Android. W przypadku systemu iOS aplikacja musi uwzględniać zestaw SDK aplikacji usługi Intune dla systemu iOS (v 7.0.1) i musi być uwzględniona w ustawieniach konfiguracji aplikacji. Procedura tworzenia zasad docelowej konfiguracji MAM: 

1. Zaloguj się do portalu **Azure Portal**.

2. Wybierz kolejno **Intune > Aplikacje mobilne — zasady konfiguracji aplikacji**.

3. W bloku **Zasady konfiguracji aplikacji** wybierz pozycję **Dodaj**.

4. Uzupełnij pola **Nazwa** i **Opis** (opcjonalnie) odnoszące się do ustawień konfiguracji aplikacji i wybierz pozycję **Niezarejestrowane w usłudze Intune**.

5. Wybierz pozycję **Wybierz wymagane aplikacje**, a następnie, w bloku aplikacji **docelowych**, wybierz aplikacje dla żądanych platform. <br>
**Uwaga:** w przypadku aplikacji biznesowych należy wybrać **Więcej aplikacji**. Wprowadź identyfikator pakietu aplikacji.

6. Wybierz pozycję **OK**, aby powrócić do bloku **Dodaj konfigurację aplikacji**.

7. Wybierz pozycję **Definiuj konfigurację**. W bloku **Konfiguracja** należy zdefiniować pary kluczy i wartości do dostarczania konfiguracji.

8. Gdy wszystko będzie gotowe, wybierz pozycję **OK**.

9. W bloku **Dodaj konfigurację aplikacji** wybierz pozycję **Utwórz**.

Nowa konfiguracja zostanie utworzona i wyświetlona w bloku Konfiguracja aplikacji.

Następnie kontynuuj [przypisywanie](apps-deploy.md) i [monitorowanie](apps-monitor.md) aplikacji jak do tej pory.

Po uruchomieniu przypisanej aplikacji (zintegrowanej z zestawem SDK aplikacji usługi Intune) na urządzeniu zostaną uruchomione ustawienia skonfigurowane w zasadach docelowej konfiguracji MAM. Przypisana aplikacja musi mieć zintegrowaną obsługiwaną wersję zestawu SDK aplikacji usługi Intune. Aby uzyskać więcej informacji o wymaganiach dotyczących tworzenia aplikacji odnoszących się do użycia zasad docelowej konfiguracji MAM, zobacz [iOS Intune APP SDK Integration Guide](https://docs.microsoft.com/intune/app-sdk-ios) (Przewodnik po integracji zestawu SDK aplikacji usługi Intune dla systemu iOS).

Aby uzyskać więcej informacji o możliwościach interfejsu API Graph w odniesieniu do wartości docelowej konfiguracji MAM, zobacz [Graph API Reference MAM Targeted Config](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create) (Konfiguracja docelowej konfiguracji MAM w zakresie odwołań do interfejsu API Graph).

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
