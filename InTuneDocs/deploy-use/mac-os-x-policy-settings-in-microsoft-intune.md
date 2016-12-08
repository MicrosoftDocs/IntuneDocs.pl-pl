---
title: Ustawienia zasad systemu Mac OS X | Microsoft Intune
description: "Usługa Intune udostępnia szereg wbudowanych ustawień ogólnych, które można skonfigurować na urządzeniach z systemem Mac OS X. Ponadto przy użyciu narzędzia Apple Configurator można utworzyć ustawienia niestandardowe, które nie są dostępne w usłudze Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 98b2f19b-bee8-42d7-a215-a716d56a25a3
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a4f7a503417938eabb4334757dcf12a63f082fd3
ms.openlocfilehash: ce30ab0e5a4ce709aafa5892789590b42b484db4


---

# Ustawienia zasad konfiguracji systemu Mac OS X w usłudze Microsoft Intune

Usługa Intune udostępnia szereg wbudowanych ustawień ogólnych, które można skonfigurować na urządzeniach z systemem Mac OS X. Ponadto przy użyciu narzędzia Apple Configurator można utworzyć ustawienia niestandardowe, które nie są dostępne w usłudze Intune.

## Ustawienia ogólnych zasad konfiguracji

**Ogólne zasady konfiguracji systemu Mac OS X** w usłudze Microsoft Intune umożliwiają konfigurację następujących ustawień:

-   **Ustawienia zabezpieczeń urządzenia**. Możesz wybrać ustawienia z listy wstępnie zdefiniowanych ustawień, które pozwalają na kontrolowanie szeregu funkcji urządzenia.

-   **Zgodne i niezgodne aplikacje**. Określ listę zgodnych i niezgodnych aplikacji w firmie. Raport o niezgodnych aplikacjach pozwala porównać aplikacje zainstalowane przez użytkowników z listą zgodnych aplikacji (ale nie pozwala zablokować instalacji aplikacji).

Jeśli danego ustawienia nie ma na liście, można je utworzyć za pomocą zasad niestandardowych systemu Mac OS X, które umożliwiają importowanie ustawień utworzonych za pomocą narzędzia Apple Configurator. Aby uzyskać więcej informacji, zobacz sekcję „Ustawienia zasad niestandardowych” w dalszej części tego tematu.

### Ustawienia hasła

|Nazwa ustawienia|Szczegóły|
|----------------|---------------|
|**Wymagaj hasła w celu odblokowania urządzeń**|Określa, czy użytkownik musi użyć hasła w celu uzyskania dostępu do komputera Mac. **Ważne:** W odróżnieniu od urządzeń z systemem iOS w przypadku urządzeń z systemem Mac OS X użytkownik nie jest od razu powiadamiany o konieczności zaktualizowania hasła w celu zachowania zgodności z tym ustawieniem.|
|**Wymagany typ hasła**|Określa, czy hasło może być wyłącznie **numeryczne** (zawierać tylko cyfry), czy też musi być **alfanumeryczne** (zawierać litery i cyfry). **Ważne:** to ustawienie jest obsługiwane tylko w systemie Mac OS X w wersji 10.10.3 lub nowszej.|
|**Wymagana liczba znaków złożonych w haśle**|Określa wymaganą liczbę znaków złożonych w haśle (od **0** do **4**).<br /><br />Znak złożony to symbol, taki jak **?**.|
|**Minimalna długość hasła**|Określa minimalną długość hasła (od **4** do **14** znaków).|
|**Zezwalaj na proste hasła**|Zezwala na korzystanie z prostych haseł, takich jak **0000** lub **1234**.|
|**Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**|Określa czas nieaktywności komputera, po upływie którego do jego odblokowania będzie wymagane hasło.|
|**Wygaśnięcie hasła (dni)**|Określa czas, po jakim użytkownik musi zmienić hasło (od **1** do **255** dni).|
|**Pamiętaj historię haseł**|To ustawienie uniemożliwia użytkownikowi skorzystanie z wcześniej używanego hasła. Jeśli je skonfigurowano, można też skonfigurować ustawienie **Zapobiegaj ponownemu używaniu poprzednich haseł** w celu określenia liczby wcześniej używanych haseł, których nie można użyć ponownie (od **1** do **24**).|
|**Czas braku aktywności (w minutach) przed uaktywnieniem wygaszacza ekranu**|Określa czas bezczynności komputera, po upływie którego jest uaktywniany wygaszacz ekranu.|

### Ustawienia dotyczące aplikacji zgodnych i niezgodnych
Na **liście zgodnych i niezgodnych aplikacji dla systemu Mac OS X** włącz ustawienie **Zarządzane ustawienia urządzeń**, a następnie określ listę zgodnych i niezgodnych aplikacji, korzystając z poniższych informacji.

> [!NOTE]
> W ramach jednych zasad można określić wyłącznie listę zgodnych lub wyłącznie listę niezgodnych aplikacji. Nie można wprowadzić obu list w ramach jednych zasad.
>
> Usługa Intune umożliwia zgłaszanie urządzeń z niezgodnymi aplikacjami. Nie blokuje to instalacji ani nie powoduje usunięcia niezgodnych aplikacji.

|Nazwa ustawienia|Szczegóły|
|----------------|---------------|
|**Zgłaszaj niezgodność, gdy użytkownicy instalują aplikacje z listy**|Wyświetla listę aplikacji systemu Mac OS X, których użytkownicy nie mogą instalować. Użytkownicy, którzy zainstalują dowolną z tych aplikacji, będą zgłaszani w **raportach o niezgodnych aplikacjach**.|
|**Zgłaszaj brak zgodności, jeśli użytkownicy będą instalować aplikacje spoza listy**|Wyświetla listę aplikacji systemu Mac OS X, które użytkownicy mogą instalować. Użytkownicy, którzy zainstalują inne aplikacje, będą zgłaszani w **raportach o niezgodnych aplikacjach**.|
|**Dodaj**|Dodaje aplikację do wybranej listy. Określ nazwę, wydawcę aplikacji (opcjonalnie) i identyfikator pakietu aplikacji. **Porada:** Aby znaleźć identyfikator pakietu aplikacji, wykonaj następujące czynności na komputerze Mac z zainstalowaną aplikacją:<ol><li>Otwórz folder, w którym zainstalowano aplikację (na przykład **/Aplikacje**).</li><li>Wybierz pakiet *&lt;Nazwa aplikacji&gt;***.app**, a następnie wybierz pozycję **Pokaż zawartość pakietu**.</li><li>Otwórz plik **Info.plist**.</li><li>Sprawdź wartość skojarzoną z kluczem **CFBundleIdentifier**.</li></ol>Identyfikator pakietu ma format **com.contoso.nazwa_aplikacji**.|
|**Importuj aplikacje**|Importuje listę aplikacji wprowadzoną w pliku w formacie wartości rozdzielanych przecinkami. W pliku użyj formatu: nazwa aplikacji, wydawca, identyfikator pakietu aplikacji.|
|**Edytowanie**|Umożliwia edytowanie nazwy, wydawcy i identyfikatora pakietu wybranej aplikacji.|
|**Usuwanie**|Usuwa wybraną aplikację z listy.|
> [!TIP]
> Aby uzyskać więcej informacji o raportach usługi Intune, zobacz [Informacje o operacjach usługi Microsoft Intune — korzystanie z raportów](understand-microsoft-intune-operations-by-using-reports.md).

> [!IMPORTANT]
> Jeśli urządzenie z systemem Mac OS X jest w trybie uśpienia, nie można dostarczać zasad i profilów ani dodawać ich do spisu. Dlatego w konsoli usługi Intune może być tymczasowo wyświetlany stan **Ustawienia zasad z błędami** do następnego wznowienia działania urządzenia z trybu uśpienia.

### Monitoruj aplikacje zgodne i niezgodne
**Raport o niezgodnych aplikacjach** zawiera informacje o zgodności określonych aplikacji.

#### Uruchomienie raportu

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) kliknij pozycję **Raporty** &gt; **Raport o niezgodnych aplikacjach**.

2.  Wybierz grupy urządzeń, które chcesz sprawdzić, określ, czy sprawdzić aplikacje zgodne, niezgodne czy oba rodzaje, a następnie wybierz pozycję **Wyświetl raport**.

## Ustawienia zasad niestandardowych systemu Mac OS X w usłudze Microsoft Intune
**Zasady niestandardowe konfiguracji systemu Mac OS X** w usłudze Microsoft Intune umożliwiają wdrażanie ustawień utworzonych przy użyciu [narzędzia Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) na urządzeniach z systemem Mac OS X. To narzędzie umożliwia tworzenie wielu ustawień do kontroli działania tych urządzeń oraz eksportowanie ich do profilu konfiguracji. Następnie można zaimportować ten profil konfiguracji do zasad niestandardowych systemu Mac OS X w usłudze Intune oraz wdrożyć ustawienia dla użytkowników i urządzeń w swojej organizacji.

Ta funkcja umożliwia wdrażanie ustawień systemu Mac OS X, których nie można skonfigurować przy użyciu zasad ogólnych konfiguracji systemu Mac OS X w usłudze Intune.

### Wymagania wstępne
Przed rozpoczęciem trzeba mieć zainstalowany program Apple Configurator i utworzony plik konfiguracji zawierający ustawienia, które mają zostać wdrożone dla użytkowników lub urządzeń. Program Apple Configurator można pobrać ze sklepu [Mac App Store](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12), można tam także znaleźć więcej informacji na jego temat.

> [!NOTE]
> Usługa Intune nie raportuje zgodności poszczególnych ustawień w zasadach niestandardowych systemu Mac OS X. Jednak ogólna zgodność z zasadami jest raportowana.

### Ustawienia ogólne

|Nazwa ustawienia|Szczegóły|
    |----------------|--------------------|
    |**Nazwa**|Wprowadź unikatową nazwę zasad niestandardowych systemu Mac OS X, co pomoże zidentyfikować je w konsoli usługi Intune.|
    |**Opis**|Podaj opis zawierający omówienie zasad niestandardowych systemu Mac OS X oraz inne istotne informacje ułatwiające ich wyszukanie.|


### Ustawienia niestandardowe

|Nazwa ustawienia|Szczegóły|
    |----------------|--------------------|
    |**Nazwa niestandardowego profilu konfiguracji (wyświetlana dla użytkowników)**|Podaj nazwę zasad, która będzie wyświetlana na urządzeniu i w raportach zasad usługi Intune.|
    |**Plik profilu konfiguracji**|Wybierz pozycję **Importuj**, a następnie przejdź do profilu konfiguracji utworzonego przy użyciu programu Apple Configurator. **Porada:** zobacz sekcję „Jak utworzyć plik profilu konfiguracji” w tym temacie, aby uzyskać pomoc przy tworzeniu profilu konfiguracji.|
    |**Szczegóły profilu konfiguracji**|Wyświetla kod XML zaimportowanego profilu konfiguracji.|



### Jak utworzyć plik profilu konfiguracji
Dostępne są dwa sposoby tworzenia pliku profilu konfiguracji używanego przez zasady niestandardowe:

-   Wyeksportowanie pliku (z rozszerzeniem **mobileconfig**) z narzędzia Apple Configurator.

-   Samodzielne utworzenie pliku przy użyciu odpowiedniego schematu ze [strony z informacjami o kluczach profili konfiguracji firmy Apple](https://developer.apple.com/library/ios/featuredarticles/iPhoneConfigurationProfileRef/Introduction/Introduction.html).


### Zobacz także
[Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Oct16_HO4-->


