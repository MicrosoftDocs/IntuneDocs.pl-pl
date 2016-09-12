---
title: "Użycie zasad konfiguracji aplikacji mobilnych systemu iOS | Microsoft Intune"
description: "Zasady konfiguracji aplikacji mobilnych w usłudze Intune umożliwiają określanie wartości ustawień, które mogą być wymagane, jeśli użytkownicy uruchamiają aplikację systemu iOS."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fc6b645a-e837-4b2a-a10f-144065cbd8dd
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 727d28cff074124b5401f6c2931f87df3a9d2d23
ms.openlocfilehash: 917761ab6be2ccd94f32e7d2f12c0ed18d335d41


---

# Konfigurowanie aplikacji systemu iOS przy użyciu zasad konfiguracji aplikacji mobilnych w usłudze Microsoft Intune
Zasady konfiguracji aplikacji mobilnych w usłudze Microsoft Intune umożliwiają określanie wartości ustawień, które mogą być wymagane, jeśli użytkownicy uruchamiają aplikację. Aplikacja może na przykład wymagać, aby użytkownicy określili:

-   Niestandardowy numer portu

-   Ustawienia języka

-   Ustawienia zabezpieczeń

-   Ustawienia oznaczeń marki, takich jak logo firmy

Nieprawidłowe określenie tych ustawień przez użytkowników może zwiększyć obciążenie działu pomocy technicznej i spowolnić wdrażanie technologii nowych aplikacji.

Zasady konfiguracji aplikacji mobilnych mogą pomóc wyeliminować te problemy, umożliwiając wdrażanie tych ustawień do użytkowników w zasadach, zanim uruchomią oni aplikację. Ustawienia są następnie określane automatycznie, a użytkownicy nie muszą podejmować żadnej akcji.

Tych zasad nie można wdrażać bezpośrednio do użytkowników i urządzeń. W zamian należy skojarzyć je z aplikacją, a następnie wdrożyć tę aplikację. Ustawienia zasad będą stosowane zawsze, gdy aplikacja będzie je wyszukiwać (zazwyczaj podczas pierwszego uruchomienia).

> [!TIP]
> Ten typ zasad jest obecnie dostępny tylko na urządzeniach z systemem iOS 7.1 i nowszych. Obsługiwane są następujące typy instalacji aplikacji:
>
> -   **Zarządzana aplikacja systemu iOS ze sklepu App Store**
> -   **Pakiet aplikacji dla systemu iOS**
>
> Aby uzyskać więcej informacji na temat typów instalacji aplikacji, zobacz [Wdrażanie aplikacji w usłudze Microsoft Intune](deploy-apps.md).

## Konfigurowanie zasad konfiguracji aplikacji mobilnych

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) wybierz pozycję **Zasady** &gt; **Przegląd** &gt; **Dodaj zasady**.

2.  Na liście zasad rozwiń węzeł **iOS**, wybierz pozycję **Konfiguracja aplikacji mobilnej**, a następnie wybierz pozycję **Utwórz zasady**.

    > [!TIP]
    > W przypadku tego typu zasad możesz skonfigurować tylko ustawienia niestandardowe. Zalecane ustawienia są niedostępne.

3.  W części **Ogólne** strony **Tworzenie zasad** podaj nazwę i opcjonalny opis zasad konfiguracji aplikacji mobilnej.

4.  W części **Zasady konfiguracji aplikacji mobilnej** w odpowiednim polu wpisz lub wklej listę właściwości XML zawierającą wymagane ustawienia konfiguracji aplikacji. Format listy właściwości XML różni się zależnie od konfigurowanej aplikacji. Szczegółowe informacje na temat dokładnego formatu do użycia możesz uzyskać od dostawcy aplikacji.

    > [!TIP]
    > Aby dowiedzieć się więcej na temat list właściwości XML, zobacz [Informacje na temat list właściwości XML](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) w bibliotece deweloperów systemu iOS.

5.  Kliknij pozycję **Sprawdź poprawność**, aby się upewnić, że wprowadzony kod XML ma prawidłowy format listy właściwości.

    > [!IMPORTANT]
    > Po kliknięciu pozycji **Sprawdź poprawność**usługa Intune sprawdza, czy wprowadzony kod XML ma prawidłowy format. Nie sprawdza ona, czy lista właściwości XML będzie współdziałać z aplikacją, z którą została skojarzona.

6.  Następnie kliknij przycisk **Zapisz zasady**.

Nowe zasady zostaną wyświetlone w węźle **Zasady konfiguracji** .

## Informacje o formacie pliku XML

Usługa Intune obsługuje następujące typy danych na liście właściwości:
    
- &lt;liczba całkowita&gt;
- &lt;liczba rzeczywista&gt;
- &lt;ciąg&gt;
- &lt;tablica&gt;
- &lt;dict&gt;
- &lt;prawda /&gt; lub &lt;fałsz /&gt;
     
Aby uzyskać więcej informacji na temat typów danych, zobacz temat [Listy właściwości — informacje](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/AboutPropertyLists/AboutPropertyLists.html) w bibliotece deweloperów systemu iOS.

Ponadto usługa Intune obsługuje następujące typy tokenów na liście właściwości:
- \{\{userprincipalname\}\} - (Przykład: **John@contoso.com**)
- \{\{mail\}\} - (Przykład: **John@contoso.com**)
- \{\{partialupn\}\} - (Przykład: **John**)
- \{\{accountid\}\} - (Przykład: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**)
- \{\{deviceid\}\} - (Przykład: **b9841cd9-9843-405f-be28-b2265c59ef97**)
- \{\{userid\}\} - (Przykład: **3ec2c00f-b125-4519-acf0-302ac3761822**)
- \{\{username\}\} - (Przykład: **John Doe**)
- \{\{serialnumber\}\} - (Przykład: **F4KN99ZUG5V2**) dla urządzeń z systemem iOS
- \{\{serialnumberlast4digits\}\} - (Przykład: **G5V2**) dla urządzeń z systemem iOS
    
Znaki \{\{ i \}\} są używane tylko przez typy tokenów i nie mogą być używane do innych celów.

## Kojarzenie zasad konfiguracji aplikacji mobilnej z aplikacją
Po utworzeniu zasad konfiguracji aplikacji mobilnej należy je skojarzyć z aplikacją systemu iOS, w której mają być stosowane ustawienia zasadach konfiguracji.

Aby to zrobić, wykonaj kroki mające na celu utworzenie wdrożenia aplikacji opisane w tematach [Dodawanie aplikacji dla urządzeń przenośnych w usłudze Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md) i [Wdrażanie aplikacji w usłudze Microsoft Intune](deploy-apps-in-microsoft-intune.md). Po przejściu na stronę **Konfiguracja aplikacji mobilnej** kreatora wybierz zasady do skojarzenia z aplikacją z listy rozwijanej **Zasady konfiguracji aplikacji**.

Następnie kontynuuj wdrażanie i monitorowanie wdrożenia aplikacji w zwykły sposób.

Po uruchomieniu wdrożonej aplikacji na urządzeniu zostaną uruchomione ustawienia skonfigurowane w zasadach konfiguracji aplikacji mobilnej.

> [!TIP]
> Jeśli co najmniej jedna zasada konfiguracji aplikacji mobilnej pozostaje w konflikcie, żadna zasada nie zostanie wymuszona. Konflikt zostanie zgłoszony na **pulpicie nawigacyjnym** w konsoli administracyjnej usługi Intune.

## Przykładowy format pliku XML konfiguracji aplikacji mobilnej

Podczas tworzenia pliku konfiguracji aplikacji mobilnej można określić co najmniej jedną z poniższych wartości, używając następującego formatu:

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



<!--HONumber=Aug16_HO5-->


