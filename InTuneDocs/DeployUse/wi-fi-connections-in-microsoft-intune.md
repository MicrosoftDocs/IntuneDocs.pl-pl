---
title: "Połączenia Wi-Fi | Microsoft Intune"
description: "Aby ułatwić użytkownikom nawiązywanie połączeń z sieciami Wi-Fi, użyj profilów sieci Wi-Fi."
keywords: 
author: Nbigman
ms.author: nbigman
manager: angrobe
ms.date: 10/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0b1b86ed-2e80-474d-8437-17dd4bc07b55
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 27ba29f57bba1f3807c4b593ecac8c0af0851962
ms.openlocfilehash: 7b49b7d9b6054f7d153359c1ee1b6cf5875fba32


---

# Konfigurowanie urządzeń do łączenia się z firmową siecią Wi-Fi

Aby wdrożyć ustawienia sieci bezprzewodowej dla użytkowników i urządzeń w Twojej organizacji, użyj profilu sieci Wi-Fi usługi Microsoft Intune. W przypadku wdrożenia profilu sieci Wi-Fi użytkownicy będą mieli dostęp do firmowej sieci Wi-Fi bez konieczności samodzielnego konfigurowania połączenia.

Załóżmy, że zainstalowano nową sieć Wi-Fi o nazwie **Sieć Wi-Fi firmy Contoso** i chcesz skonfigurować wszystkie urządzenia z systemem iOS do łączenia się z tą siecią. Oto proces:

![Podsumowanie procesu profilu sieci Wi-Fi](..\media\wi-fi-process-diagram.png) 

1.   Utwórz profil sieci Wi-Fi zawierający ustawienia wymagane do łączenia się z siecią bezprzewodową **Sieć Wi-Fi firmy Contoso**.

2.   Wdróż profil w grupie użytkowników z urządzeniami z systemem iOS.

3.   Użytkownicy znajdują nową sieć **Sieć Wi-Fi firmy Contoso** na liście sieci bezprzewodowych i mogą łatwo łączyć się z tą siecią.


## Jak utworzyć profil sieci Wi-Fi

Profile sieci Wi-Fi można wdrażać na poniższych platformach:

-   Android 4.0 i nowsze

-   Program Android for Work   

-   System iOS 8.0 i nowsze

-   System Mac OS X 10.9 lub nowszy

W przypadku urządzeń z systemem Windows 8.1 albo systemem Windows 10 Desktop lub Mobile można zaimportować profil konfiguracji sieci Wi-Fi, który został wcześniej wyeksportowany do pliku. Aby uzyskać szczegółowe informacje, zobacz [Eksportowanie lub importowanie profilu konfiguracji sieci Wi-Fi dla urządzeń z systemem Windows](#export-or-import-a-wi-fi-configuration-profile-for-windows-devices).

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) kliknij pozycje **Zasady** &gt; **Dodaj zasady**.

2.  Wybierz jeden z następujących typów zasad, a następnie kliknij pozycję **Utwórz zasady**:

    -   Profil sieci Wi-Fi (system Android 4 i nowsze)

    -   Profil sieci Wi-Fi (program Android for Work)

    -   Profil sieci Wi-Fi (system iOS 8.0 i nowsze)

    -   Profil sieci Wi-Fi (system Mac OS X 10.9 lub nowszy)
    
    
    Nie ma żadnych zalecanych ustawień dla tego typu zasad. Należy utworzyć zasady niestandardowe.

3.  Podaj nazwę i opis profilu.

4. Określ wartości w obszarze **Połączenia sieciowe**.
 - **Identyfikator zestawu usług (SSID)**: użytkownicy widzą nazwę sieci, a nie identyfikator SSID.
 - **Połącz, gdy sieć nie emituje swojej nazwy (SSID)**: wybierz tę opcję, aby zezwolić urządzeniom na łączenie się z tą siecią, gdy nie jest ona widoczna na liście sieci (ponieważ jest ukryta i nie rozgłasza swojej nazwy).
 
5. Skonfiguruj opcje w obszarze **Ustawienia zabezpieczeń** dla wybranej platformy. Dostępne ustawienia zależą od wybranych typów zabezpieczeń i są opisane w temacie [Ustawienia zabezpieczeń](#security-settings).

6. Konfigurowanie **ustawień serwera proxy** (dotyczy tylko systemów iOS i Mac OS X)

    |Nazwa ustawienia|Więcej informacji|Zastosowania:|
    |----------------|-------------------|-------------|
    |**Ustawienia serwera proxy dla tego połączenia Wi-Fi**|Wybierz typ ustawień serwera proxy:<br /><br />-   **Brak** (domyślnie)<br />-   **Ręczne** — ręcznie podaj adres URL i numer portu serwera proxy.<br />-   **Automatyczne** — skonfiguruj serwer proxy przy użyciu pliku konfiguracji.|Zawsze|
    |**Adres serwera proxy** i **Numer portu**|Podaj adres URL i numer portu serwera proxy.|Dla opcji **Ustawienia serwera proxy dla tego połączenia Wi-Fi** jest wybrana wartość **Ręczne**.|
    |**Adres URL serwera proxy**|Podaj adres URL pliku zawierającego ustawienia serwera proxy.|Dla opcji **Ustawienia serwera proxy dla tego połączenia Wi-Fi** jest wybrana wartość **Automatyczne**.|

7.  Zapisywanie profilu sieci Wi-Fi

Nowe zasady są wyświetlane w węźle **Zasady konfiguracji** w obszarze roboczym **Zasady**. Informacje o wdrażaniu usługi można znaleźć w temacie **Następne kroki**.

## Eksportowanie lub importowanie profilu konfiguracji sieci Wi-Fi dla urządzeń z systemem Windows
 
W przypadku urządzeń z systemem Windows 8.1 albo systemem Windows 10 Desktop lub Mobile można zaimportować profil konfiguracji sieci Wi-Fi, który został wcześniej wyeksportowany do pliku. 

### Eksportowanie profilu sieci Wi-Fi
W systemie Windows można użyć narzędzia **netsh wlan**, aby wyeksportować istniejący profil sieci Wi-Fi do pliku XML, który może zostać odczytany przez usługę Intune. Na komputerze z systemem Windows, na którym jest już zainstalowany wymagany profil sieci Wi-Fi, wykonaj następującą procedurę.

1.  Utwórz folder lokalny dla wyeksportowanych profilów sieci Wi-Fi, np. c:\WiFi.

2.  Otwórz wiersz polecenia jako administrator.

3.  Uruchom polecenie `netsh wlan show profiles` i określ nazwę profilu, który chcesz wyeksportować.  W tym przykładzie nazwa profilu brzmi *WiFiName*.

4.  Uruchom to polecenie: `netsh wlan export profile name="ProfileName" folder=c:\Wifi`. Spowoduje to utworzenie pliku profilu sieci Wi-Fi o nazwie „Wi-Fi-WiFiName.xml” w folderze docelowym.

### Importowanie profilu sieci Wi-Fi
Aby zaimportować zestaw ustawień sieci Wi-Fi, które można następnie wdrożyć dla wymaganych grup użytkowników lub urządzeń, użyj zasady typu **Zasady importowania profilów Wi-Fi systemu Windows**.


1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) kliknij pozycje **Zasady** &gt; **Dodaj zasady**.

2.  Skonfiguruj zasady typu **Windows** i **Importowanie profilów sieci Wi-Fi (system Windows 8.1 i nowsze)**.

    Te zasady można zastosować do urządzeń z systemami Windows 8.1 i Windows 10 Desktop lub Mobile.

    Można tworzyć i wdrażać tylko *niestandardowe* zasady importowania profilów sieci Wi-Fi systemu Windows. Zalecane ustawienia są niedostępne.

3.  Określ następujące wartości ogólne zasady importowania profilów Wi-Fi systemu Windows:

    |Nazwa ustawienia|Więcej informacji|
    |----------------|--------------------|
    |**Nazwa**|Wprowadź unikatową nazwę profilu sieci Wi-Fi, aby zidentyfikować go w konsoli usługi Intune.|
    |**Opis**|Podaj opis profilu sieci Wi-Fi i inne odpowiednie informacje ułatwiające jego znalezienie.|

4.  W obszarze nagłówka **Niestandardowy profil sieci Wi-Fi** podaj następujące wartości:

    |Nazwa ustawienia|Więcej informacji|
    |----------------|--------------------|
    |**Plik profilu konfiguracji**|Kliknij przycisk **Importuj**, aby wybrać plik XML zawierający ustawienia profilu sieci Wi-Fi, który chcesz zaimportować do usługi Intune.|
    |**Nazwa niestandardowego profilu konfiguracji (wyświetlana dla użytkowników)**|Wyświetla nazwę profilu konfiguracji sieci Wi-Fi w takiej postaci, w jakiej będzie ona pokazywana użytkownikom na ich urządzeniach.|
    |**Szczegóły profilu konfiguracji**|Wyświetla kod XML wybranego profilu konfiguracji.|

5.  Gdy skończysz, kliknij pozycję **Zapisz zasady**.

6.  Nowe zasady zostaną wyświetlone w węźle **Zasady konfiguracji** w obszarze roboczym **Zasady** .

## Wdrażanie profilu

Profil jest typem zasad, a więc w celu jego wdrożenia należy użyć obszaru roboczego Zasady.

1.  W obszarze roboczym **Zasady** wybierz zasady do wdrożenia, a następnie kliknij pozycję **Zarządzaj wdrożeniem**.

2.  W oknie dialogowym **Zarządzanie wdrażaniem** :

    -   **Aby wdrożyć zasady** — wybierz co najmniej jedną grupę, w której chcesz wdrożyć zasady, a następnie kliknij pozycję **Dodaj** &gt; **OK**.

    -   **Aby zamknąć okno dialogowe bez wdrażania** — kliknij przycisk **Anuluj**.


W podsumowaniu stanu i alertach na stronie **Przegląd** obszaru roboczego **Zasady** są pokazane problemy z zasadami, które wymagają Twojej uwagi. Ponadto w obszarze roboczym Pulpit nawigacyjny jest wyświetlane podsumowanie stanu.

## Ustawienia zabezpieczeń
Te tabele zawierają szczegółowe informacje dotyczące ustawień zabezpieczeń, które są dostępne dla profilów sieci Wi-Fi systemu Android, iOS i Mac OS X. 

### Ustawienia zabezpieczeń dla urządzeń z systemem Android

  |Nazwa ustawienia|Więcej informacji|Zastosowania:|
|----------------|--------------------|-------------|
|**Typ zabezpieczeń**|Wybierz protokół zabezpieczeń sieci bezprzewodowej:<br /><br />-   **WPA-Enterprise/WPA2-Enterprise**<br />-   **Bez uwierzytelnienia (otwarte)**, jeśli sieć jest niezabezpieczona.|Zawsze|
|**Typ protokołu EAP**|Wybierz typ protokołu uwierzytelniania rozszerzonego (EAP) używany do uwierzytelniania zabezpieczonych połączeń bezprzewodowych:<br /><br />-   **EAP-TLS**<br />-   **PEAP**<br />-   **EAP-TTLS**|Wybrano typ zabezpieczeń **WPA-Enterprise/WPA2-Enterprise**.|
|**Wybierz certyfikaty główne do sprawdzania poprawności serwera**|Kliknij przycisk **Wybierz**, a następnie wybierz profil zaufanych certyfikatów głównych używany do uwierzytelniania połączenia. **Ważne:** Aby utworzyć profil zaufanych certyfikatów głównych, zobacz temat [Bezpieczny dostęp do zasobów przy użyciu profilów certyfikatów](secure-resource-access-with-certificate-profiles.md).|Dla ustawienia **Typ protokołu EAP** wybrana jest dowolna wartość.|
|**Metoda uwierzytelniania**|Wybierz metodę uwierzytelniania dla połączenia:<br /><br />-   **Certyfikaty** , aby określić certyfikat klienta.<br />-   **Nazwa użytkownika i hasło**, aby określić inną metodę uwierzytelniania.|Dla ustawienia **Typ protokołu EAP** jest wybrana wartość **PEAP** lub **EAP-TTLS**.|
|**Wybierz metodę inną niż EAP na potrzeby uwierzytelniania (tożsamość wewnętrzna)**|Wybierz sposób uwierzytelniania połączenia:<br /><br />-   **Brak**<br />-   **Hasło nieszyfrowane (PAP)**<br />-   **Protokół uwierzytelniania typu Challenge Handshake (CHAP)**<br />-   **Microsoft CHAP (MS-CHAP)**<br />-   **Microsoft CHAP wersja 2 (MS-CHAP v2)**<br /><br />Dostępne opcje zależą od wybranego typu protokołu EAP.|Dla ustawienia **Metoda uwierzytelniania** wybrana jest wartość **Nazwa użytkownika i hasło**.|
|**Włącz prywatność tożsamości (tożsamość zewnętrzna)**|Podaj tekst, który będzie wysyłany w odpowiedzi na żądanie podania tożsamości zgłaszane przez protokół EAP. Ten tekst może mieć dowolną wartość. Podczas uwierzytelniania na początku wysyłana jest ta tożsamość anonimowa, a po niej — tożsamość rzeczywista, która jest wysyłana w bezpiecznym tunelu.|Dla ustawienia **Typ protokołu EAP** jest wybrana wartość **PEAP** lub **EAP-TTLS**.|
|**Wybierz certyfikat klienta na potrzeby uwierzytelniania klienta (certyfikat tożsamości)**|Kliknij przycisk **Wybierz**, a następnie wybierz profil certyfikatu SCEP używany do uwierzytelniania połączenia. **Ważne:** Aby utworzyć profil certyfikatu SCEP, zobacz temat [Bezpieczny dostęp do zasobów przy użyciu profilów certyfikatów](secure-resource-access-with-certificate-profiles.md).|Typ zabezpieczeń to **WPA-Enterprise/WPA2-Enterprise**, natomiast dla ustawienia **Typ protokołu EAP** wybrana jest dowolna wartość.|

### Ustawienia zabezpieczeń dla urządzeń z systemem iOS i Mac OS X

  |Nazwa ustawienia|Więcej informacji|Zastosowania:|
|----------------|--------------------|-------------|
|**Typ zabezpieczeń**|Wybierz protokół zabezpieczeń sieci bezprzewodowej:<br /><br />-   **WPA-Personal/WPA2-Personal**<br />-   **WPA-Enterprise/WPA2-Enterprise**<br />-   **WEP**<br />-   **Bez uwierzytelnienia (otwarte)**, jeśli sieć jest niezabezpieczona.|Zawsze|
|**Typ protokołu EAP**|Wybierz typ protokołu uwierzytelniania rozszerzonego (EAP) używany do uwierzytelniania zabezpieczonych połączeń bezprzewodowych:<br /><br />-   **EAP-TLS**<br />-   **PEAP**<br />-   **EAP-TLS**<br />-   **EAP-AST**<br />-   **LEAP**<br />-   **EAP-SIM**|Wybrano typ zabezpieczeń **WPA-Enterprise/WPA2-Enterprise**.|
|**Nazwy zaufanych certyfikatów serwera**|Wybierz profil zaufanych certyfikatów głównych używany do uwierzytelniania połączenia. **Ważne:** Aby utworzyć profil zaufanych certyfikatów głównych, zobacz temat [Bezpieczny dostęp do zasobów przy użyciu profilów certyfikatów](secure-resource-access-with-certificate-profiles.md).|Wybrano typ protokołu EAP **EAP-TLS**, **PEAP**, **EAP-TTLS** lub **EAP-FAST**.|
|**Użyj uwierzytelniania PAC (Protected Access Credential)**|Wybierz tę wartość, aby ustanowić uwierzytelniony tunel między klientem i serwerem uwierzytelniania przy użyciu uwierzytelniania PAC. Zostanie użyty istniejący plik PAC, jeśli jest obecny.|Dla ustawienia **Typ protokołu EAP** wybrana jest wartość **EAP-FAST**.|
|**Zapewnij uwierzytelnianie PAC**|Inicjuje obsługę pliku PAC dla urządzeń.<br /><br />Gdy ta opcja jest używana, można także wybrać opcję **Zapewnij anonimowe uwierzytelnianie PAC** , aby zagwarantować, że obsługa pliku PAC zostanie zainicjowana bez uwierzytelniania serwera.|Wybrana jest opcja**Użyj uwierzytelniania PAC (Protected Access Credential)** .|
|**Metoda uwierzytelniania**|Wybierz metodę uwierzytelniania używaną dla połączenia:<br /><br /><ul><li>**Certyfikaty** , aby określić certyfikat klienta.</li><li>**Nazwa użytkownika i hasło**, aby określić jedną z poniższych metod uwierzytelniania bez użycia protokołu EAP (jest to również nazywane tożsamością wewnętrzną):<br /><br /><ul><li>**Brak**</li><li>**Hasło nieszyfrowane (PAP)**</li><li>**Protokół uwierzytelniania typu Challenge Handshake (CHAP)**</li><li>**Microsoft CHAP (MS-CHAP)**</li><li>**Microsoft CHAP wersja 2 (MS-CHAP v2)**</li><li>**EAP-TLS**</li></ul></li></ul>|Dla ustawienia **Typ protokołu EAP** jest wybrana wartość **PEAP** lub **EAP-TTLS**.|
|**Wybierz certyfikat klienta na potrzeby uwierzytelniania klienta (certyfikat tożsamości)**|Wybierz profil certyfikatu SCEP używany do uwierzytelniania połączenia. **Ważne:** Aby utworzyć profil certyfikatu SCEP, zobacz temat [Bezpieczny dostęp do zasobów przy użyciu profilów certyfikatów](secure-resource-access-with-certificate-profiles.md).|Gdy typ zabezpieczeń to **WPA-Enterprise/WPA2-Enterprise**, a dla ustawienia **Typ protokołu EAP** wybrana jest wartość **EAP-TLS**, **PEAP** lub **EAP-TTLS**.|
|**Włącz prywatność tożsamości (tożsamość zewnętrzna)**|Podaj tekst, który będzie wysyłany w odpowiedzi na żądanie podania tożsamości zgłaszane przez protokół EAP. Ten tekst może mieć dowolną wartość.<br /><br />Podczas uwierzytelniania na początku wysyłana jest ta tożsamość anonimowa, a po niej — tożsamość rzeczywista, która jest wysyłana w bezpiecznym tunelu.|Gdy dla ustawienia **Typ protokołu EAP** wybrana jest wartość **PEAP**, **EAP-TTLS** lub **EAP-FAST**.|


### Zobacz także
Dowiedz się, jak utworzyć profil sieci Wi-Fi z użyciem klucza wstępnego — zobacz [Profil sieci Wi-Fi z użyciem klucza wstępnego](pre-shared-key-wi-fi-profile.md)



<!--HONumber=Oct16_HO2-->


