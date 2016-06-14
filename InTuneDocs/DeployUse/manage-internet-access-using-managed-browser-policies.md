---
# required metadata

title: Zarządzanie dostępem do Internetu za pomocą zasad programu Managed Browser | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: dc946303-e09b-4d73-8bf4-87742299bc54

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Zarządzanie dostępem do Internetu za pomocą zasad programu Managed Browser w usłudze Microsoft Intune
Program Managed Browser to aplikacja służąca do przeglądania sieci Web, którą można wdrożyć w organizacji za pomocą usługi Microsoft Intune. Zasady programu Managed Browser umożliwiają skonfigurowanie listy dozwolonych lub zablokowanych witryn sieci Web ograniczającej zakres witryn, które użytkownicy programu Managed Browser mogą odwiedzać.

Ze względu na to, że jest to aplikacja zarządzana, można także zastosować dla niej zasady zarządzania aplikacjami mobilnymi, takie jak kontrolowanie użycia funkcji wycinania, kopiowania i wklejania, zapobieganie przechwytywaniu ekranu oraz upewnianie się, że klikane przez użytkowników linki do zawartości są otwierane tylko w innych zarządzanych aplikacjach. Aby uzyskać więcej informacji, zobacz [Konfigurowanie i wdrażanie zasad zarządzania aplikacjami mobilnymi w konsoli usługi Microsoft Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).

> [!IMPORTANT]
>Jeśli użytkownicy zainstalują program Managed Browser ze sklepu z aplikacjami i nie będzie on zarządzany przez usługę Intune, stosowane są następujące rozwiązania:
iOS — program Managed Browser może być używany jako podstawowa przeglądarka sieci Web, ale niektóre funkcje nie będą dostępne i nie będzie mógł on uzyskać dostępu do danych z innych aplikacji zarządzanych przez usługę Intune.
Android — nie można używać programu Managed Browser.
Jeśli użytkownicy sami zainstalują program Managed Browser na urządzeniu z systemem iOS w wersji wcześniejszej niż 9, nie będzie on zarządzany zgodnie z żadną z wybranych przez Ciebie zasad. Aby upewnić się, że przeglądarka jest zarządzana przez usługę Intune, użytkownicy muszą odinstalować aplikację, zanim wdrożysz ją dla nich jako zarządzaną aplikację. W systemach iOS w wersji 9 lub nowszych jeśli użytkownik sam zainstaluje program Managed Browser, zostanie wyświetlony monit o umożliwienie zarządzania tym programem przez zasady.

Zasady programu Managed Browser można tworzyć dla następujących typów urządzeń:

-   Urządzenia z systemem Android 4 i nowszym

-   Urządzenia z systemem iOS 7.1 i nowszymi

Program Intune Managed Browser obsługuje otwieranie zawartości sieci Web od [partnerów aplikacji usługi Microsoft Intune](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx).

## Tworzenie zasad programu Managed Browser

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) kliknij kolejno pozycje **Zasady** &gt; **Dodaj zasady**.

2.  Skonfiguruj jeden z następujących typów zasad z grupy **Oprogramowanie** :

    -   **Zasady programu Managed Browser (system Android 4 i nowsze)**

    -   **Zasady programu Managed Browser (system iOS 7.1 i nowsze)**

    Aby uzyskać więcej informacji na temat tworzenia i wdrażania zasad, zobacz temat [Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Poniższa tabela pomoże Ci w skonfigurowaniu ustawień zasad programu Managed Browser:

|Nazwa ustawienia|Szczegóły|
    |----------------|--------------------|
    |**Nazwa**|Wprowadzenie unikatowej nazwy zasad programu Managed Browser pomaga zidentyfikować te zasady w konsoli usługi Intune.|
    |**Opis**|Wprowadzony opis powinien zawierać omówienie zasad programu Managed Browser i inne istotne informacje ułatwiające wyszukanie tych zasad.|
    |**Włączenie listy witryn dozwolonych lub zablokowanych pozwala na ograniczenie adresów, które można otworzyć w programie Managed Browser.**|Wybierz jedną z następujących opcji:<br /><br />**Zezwalaj programowi Managed Browser na otwieranie tylko adresów URL wymienionych poniżej** — określ listę adresów URL, które można otworzyć w programie Managed Browser.<br /><br />**Blokuj w programie Managed Browser otwieranie adresów URL wymienionych poniżej** — określ listę adresów URL, których otwieranie zostanie zablokowane w programie Managed Browser. **Uwaga:** w jednej zasadzie programu Managed Browser nie można uwzględnić jednocześnie dozwolonych i zablokowanych adresów URL.<br />Aby uzyskać więcej informacji na temat możliwych do określenia formatów adresów URL, zobacz sekcję **Format adresu URL dla dozwolonych i zablokowanych adresów URL** w tym temacie.|

4.  Gdy skończysz, kliknij pozycję **Zapisz zasady**.

Nowe zasady zostaną wyświetlone w węźle **Zasady konfiguracji** w obszarze roboczym **Zasady** .

## Tworzenie wdrożenia dla aplikacji programu Managed Browser
Po utworzeniu zasad programu Managed Browser można utworzyć wdrożenie oprogramowania dla aplikacji programu Managed Browser i skojarzyć je z utworzonymi zasadami programu Managed Browser.

> [!IMPORTANT]
> Zasady programu Managed Browser nie są wdrażane w taki sam sposób jak inne zasady usługi Intune. Ten typ zasad należy skojarzyć z pakietem oprogramowania Managed Browser.

Wdróż aplikację, wybierając zasady programu Managed Browser na stronie **Zarządzanie aplikacjami mobilnymi** , aby skojarzyć zasady z aplikacją.

Aby uzyskać więcej informacji na temat sposobu wdrażania aplikacji, zobacz [Wdrażanie aplikacji w usłudze Microsoft Intune](deploy-apps-in-microsoft-intune.md).

## Zabezpieczenia i prywatność programu Managed Browser

-   Na urządzeniach z systemem iOS nie można otwierać odwiedzanych przez użytkowników witryn sieci Web z certyfikatem nieważnym lub niezaufanym.

-   Ustawienia przeglądarki wbudowanej na urządzeniach użytkowników nie są używane w programie Managed Browser. Dzieje się tak, ponieważ program Managed Browser nie ma dostępu do tych ustawień.

-   Jeśli w zasadach zarządzania aplikacjami mobilnymi skojarzonych z programem Managed Browser są konfigurowane opcje **Wymagaj prostego numeru PIN w celu udzielenia dostępu** lub **Wymagaj poświadczeń firmowych w celu udzielenia dostępu** , a użytkownik kliknie link Pomoc na stronie uwierzytelniania, umożliwi to przeglądanie dowolnych witryn internetowych bez względu na to, czy zostały one dodane do listy witryn zablokowanych w zasadach programu Managed Browser.

-   Program Managed Browser może zablokować dostęp do witryn tylko w przypadku uzyskiwania do nich bezpośredniego dostępu. Dostępu do witryny nie można zablokować, jeśli jest on uzyskiwany za pomocą usług pośrednich (na przykład usługi tłumaczenia).

-   W celu umożliwienia uwierzytelniania i zapewnienia, że można uzyskać dostęp do dokumentacji usługi Intune, witryna **&#42;.microsoft.com** jest wyłączona z ustawień listy dozwolonych lub zablokowanych witryn —jest ona zawsze dozwolona.

### Wyłączanie danych użycia
Firma Microsoft automatycznie zbiera anonimowe dane dotyczące wydajności i korzystania z programu Managed Browser w celu ulepszania swoich produktów i usług, ale użytkownicy mogą wyłączyć zbieranie danych przy użyciu ustawienia **Dane użycia** na swoim urządzeniu. Użytkownik nie kontroluje zbierania tych danych.

## Informacje referencyjne

### Format adresu URL dla dozwolonych i zablokowanych adresów URL
Poniższe informacje dotyczą dopuszczalnych formatów i symboli wieloznacznych, których można używać podczas określania adresów URL na listach witryn dozwolonych i zablokowanych.

-   Symbol wieloznaczny „**&#42;**” może być używany zgodnie z regułami z poniższej listy dozwolonych wzorców.

-   Upewnij się, że wszystkie adresy URL dodawane do listy będą mieć prefiks **http** lub **https** .

-   W adresie można określić numery portów. Jeśli nie określisz numeru portu, będą używane następujące wartości:

    -   Port 80 dla protokołu http

    -   Port 443 dla protokołu https

    Symboli wieloznacznych nie można używać w numerze portu, na przykład **http://www.contoso.com:*;** i **http://www.contoso.com: /*;**

-   W poniższej tabeli przedstawiono dozwolone wzorce do użycia podczas określania adresów URL:

|Adres URL|Szczegóły|Jest zgodny z|Nie jest zgodny z|
    |-------|---------------|-----------|------------------|
    |http://www.contoso.com|Zgodny z pojedynczą stroną|www.contoso.com|host.contoso.com<br /><br />www.contoso.com/images<br /><br />contoso.com/|
    |http://contoso.com|Zgodny z pojedynczą stroną|contoso.com/|host.contoso.com<br /><br />www.contoso.com/images<br /><br />www.contoso.com|
    |http://www.contoso.com/&#42;|Zgodny ze wszystkimi adresami URL rozpoczynającymi się od www.contoso.com|www.contoso.com<br /><br />www.contoso.com/images<br /><br />www.contoso.com/videos/tvshows|host.contoso.com<br /><br />host.contoso.com/images|
    |http://&#42;.contoso.com/&#42;|Zgodny ze wszystkimi domenami podrzędnymi w domenie contoso.com|developer.contoso.com/resources<br /><br />news.contoso.com/images<br /><br />news.contoso.com/videos|contoso.host.com|
    |http://www.contoso.com/images|Zgodny z pojedynczym folderem|www.contoso.com/images|www.contoso.com/images/dogs|
    |http://www.contoso.com:80|Zgodny z pojedynczą stroną z użyciem numeru portu|http://www.contoso.com:80||
    |https://www.contoso.com|Zgodny z pojedynczą, bezpieczną stroną|https://www.contoso.com|http://www.contoso.com|
    |http://www.contoso.com/images/&#42;|Zgodny z pojedynczym folderem ze wszystkimi podfolderami|www.contoso.com/images/dogs<br /><br />www.contoso.com/images/cats|www.contoso.com/videos|

-   Poniżej przedstawiono niektóre niedozwolone wzorce:

    -   &#42;.com

    -   &#42;.contoso/&#42;

    -   www.contoso.com/&#42;images

    -   www.contoso.com/&#42;images&#42;pigs

    -   www.contoso.com/page&#42;

    -   Adresy IP

    -   https://&#42;

    -   http://&#42;

    -   http://www.contoso.com:&#42;

    -   http://www.contoso.com: /&#42;

### Jak rozwiązywane są konflikty pozycji list witryn dozwolonych i zablokowanych
Jeśli zasady programu Managed Browser są wdrażane na urządzeniu i wystąpi konflikt ustawień, analizowane są listy trybu (zezwalania lub blokowania) oraz adresów URL. W przypadku konfliktu stosowane są następujące rozwiązania:

-   Jeśli tryby w każdej z zasad są takie same, a adresy URL są różne, adresy URL nie są wymuszane na urządzeniu.

-   Jeśli tryby w każdej z zasad są różne, a adresy URL są takie same, adresy URL nie są wymuszane na urządzeniu.

-   Jeśli urządzenie otrzymuje zasady programu Managed Browser po raz pierwszy i wystąpi konflikt dwóch zasad, adresy URL nie są wymuszane na urządzeniu. Aby przejrzeć informacje o konfliktach, użyj węzła **Konflikty zasad** w obszarze roboczym **Zasady** .

-   Jeśli urządzenie już otrzymało zasady programu Managed Browser, a drugie zasady są wdrażane z ustawieniami powodującymi konflikt, na urządzeniu będą używane ustawienia oryginalne. Aby przejrzeć informacje o konfliktach, użyj węzła **Konflikty zasad** w obszarze roboczym **Zasady** .


<!--HONumber=May16_HO1-->

