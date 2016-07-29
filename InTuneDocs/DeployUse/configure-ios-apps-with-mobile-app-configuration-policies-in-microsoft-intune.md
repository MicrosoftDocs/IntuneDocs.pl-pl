---
title: "Użycie zasad konfiguracji aplikacji mobilnych systemu iOS | Microsoft Intune"
description: "Zasady konfiguracji aplikacji mobilnych w usłudze Intune umożliwiają określanie wartości ustawień, które mogą być wymagane, jeśli użytkownik uruchamia aplikację systemu iOS."
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fc6b645a-e837-4b2a-a10f-144065cbd8dd
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c1850e89830de61ccdeb81cb6ee9cc0f0c1d237a
ms.openlocfilehash: faf65ddbb4772f8c0ce0a4125bb108b3b1bcfb5c


---

# Konfigurowanie aplikacji systemu iOS przy użyciu zasad konfiguracji aplikacji mobilnych w usłudze Microsoft Intune
Zasady konfiguracji aplikacji mobilnych w usłudze Microsoft Intune umożliwiają określanie wartości ustawień, które mogą być wymagane, jeśli użytkownik uruchamia aplikację. Aplikacja może na przykład wymagać, aby użytkownik określił:

-   Numer portu niestandardowego na potrzeby jej uruchamiania

-   Ustawienia języka

-   Ustawienia zabezpieczeń

-   Ustawienia oznaczeń marki, takich jak logo firmy

Nieprawidłowe określenie tych ustawień przez użytkownika może zwiększyć obciążenie działu pomocy technicznej, a także spowolnić wdrażanie technologii nowych aplikacji.

Zasady konfiguracji aplikacji mobilnych mogą pomóc wyeliminować te problemy, umożliwiając wdrażanie tych ustawień do użytkowników w zasadach, zanim uruchomią oni aplikację. Ustawienia są następnie określane automatycznie, a użytkownik nie musi podejmować żadnej akcji.

Tych zasad nie można wdrażać bezpośrednio do użytkowników i urządzeń. W zamian należy skojarzyć je z aplikacją, a następnie wdrożyć tę aplikację. Ustawienia zasad będą stosowane zawsze, gdy aplikacja będzie je wyszukiwać (zazwyczaj podczas pierwszego uruchomienia).

> [!TIP]
> Ten typ zasad jest obecnie dostępny tylko na urządzeniach z systemem iOS 7.1 lub nowszym. Obsługuje on następujące typy instalacji aplikacji:
> 
> -   **Zarządzana aplikacja systemu iOS ze sklepu App Store**
> -   **Pakiet aplikacji dla systemu iOS**
> 
> Aby uzyskać więcej informacji na temat typów instalacji aplikacji, zobacz [Wdrażanie aplikacji w usłudze Microsoft Intune](deploy-apps.md).

## Konfigurowanie zasad konfiguracji aplikacji mobilnych

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) kliknij pozycje **Zasady** &gt; **Przegląd** &gt; **Dodaj zasady**.

2.  Na liście zasad rozwiń węzeł **iOS**, kliknij pozycję **Konfiguracja aplikacji mobilnej**, a następnie kliknij pozycję **Utwórz zasady**.

    > [!TIP]
    > W przypadku tego typu zasad możesz skonfigurować tylko ustawienia niestandardowe. Zalecane ustawienia są niedostępne.

3.  W części **Ogólne** strony **Tworzenie zasad** podaj nazwę i opcjonalny opis zasad konfiguracji aplikacji mobilnej.

4.  W części **Zasady konfiguracji aplikacji mobilnej** wpisz lub wklej listę właściwości XML zawierającą ustawienia konfiguracji aplikacji do umieszczenia w polu.

    > [!TIP]
    > Aby dowiedzieć się więcej na temat list właściwości XML, zobacz [Informacje na temat list właściwości XML](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) w bibliotece deweloperów systemu iOS.
    > 
    > Format listy właściwości XML różni się zależnie od konfigurowanej aplikacji. Szczegółowe informacje na temat dokładnego formatu do użycia możesz uzyskać od dostawcy aplikacji.
    > 
    > Usługa Intune obsługuje następujące typy danych na liście właściwości:
    > 
    > &lt;liczba całkowita&gt;
    > &lt;liczba rzeczywista&gt;
    > &lt;ciąg&gt;
    > &lt;tablica&gt;
    > &lt;słownik&gt;
    > &lt;true /&gt; lub &lt;false /&gt;
    > 
    > Aby uzyskać więcej informacji na temat typów danych, zobacz temat [Listy właściwości — informacje](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/AboutPropertyLists/AboutPropertyLists.html) w bibliotece deweloperów systemu iOS.
    >
        > Ponadto usługa Intune obsługuje następujące typy tokenów na liście właściwości:
    >    
    > \{\{userprincipalname\}\} — (przykład: **John@contoso.com**) \{\{mail\}\} — (przykład: **John@contoso.com**) \{\{partialupn\}\} — (przykład: **John**) \{\{accountid\}\} — (przykład: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**) \{\{deviceid\}\} — (przykład: **b9841cd9-9843-405f-be28-b2265c59ef97**) \{\{userid\}\} — (przykład: **3ec2c00f-b125-4519-acf0-302ac3761822**) \{\{username\}\} — (przykład: **John Doe**) \{\{serialnumber\}\} — (przykład: **F4KN99ZUG5V2**) dla urządzeń z systemem iOS \{\{serialnumberlast4digits\}\} — (przykład: **G5V2**) dla urządzeń z systemem iOS
>
> Znaki \{\{ i \}\} są używane tylko przez typy tokenów i nie mogą być używane do innych celów.




5.  Kliknij pozycję **Sprawdź poprawność** , aby upewnić się, że wprowadzony kod XML ma prawidłowy format listy właściwości.

    > [!IMPORTANT]
    > Po kliknięciu pozycji **Sprawdź poprawność**usługa Intune sprawdza, czy wprowadzony kod XML ma prawidłowy format. Nie sprawdza ona, czy lista właściwości XML będzie współdziałać z aplikacją, z którą została skojarzona.

6.  Następnie kliknij przycisk **Zapisz zasady**.

Nowe zasady zostaną wyświetlone w węźle **Zasady konfiguracji** .

## Kojarzenie zasad konfiguracji aplikacji mobilnej z aplikacją
Po utworzeniu zasad konfiguracji aplikacji mobilnej należy je skojarzyć z aplikacją systemu iOS, w której mają być stosowane ustawienia zasadach konfiguracji.

Aby to zrobić, wykonaj kroki mające na celu utworzenie wdrożenia aplikacji opisane w tematach [Dodawanie aplikacji dla urządzeń przenośnych w usłudze Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md) i [Wdrażanie aplikacji w usłudze Microsoft Intune](deploy-apps-in-microsoft-intune.md). Po przejściu na stronę **Konfiguracja aplikacji mobilnej** kreatora wybierz zasady do skojarzenia z aplikacją z listy rozwijanej **Zasady konfiguracji aplikacji**.

Następnie kontynuuj wdrażanie i monitorowanie wdrożenia aplikacji w zwykły sposób.

Po uruchomieniu wdrożonej aplikacji na urządzeniu zostaną uruchomione ustawienia skonfigurowane w zasadach konfiguracji aplikacji mobilnej.

> [!TIP]
> Jeśli co najmniej jedne zasady konfiguracji aplikacji mobilnej wywołują konflikt, żadne zasady nie są wymuszane, a konflikt jest zgłaszany na **pulpicie nawigacyjnym** konsoli administracyjnej usługi Intune.

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





<!--HONumber=Jul16_HO3-->


