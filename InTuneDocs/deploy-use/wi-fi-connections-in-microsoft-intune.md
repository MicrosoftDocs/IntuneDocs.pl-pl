---
title: "Połączenia Wi-Fi | Microsoft Docs"
description: "Aby ułatwić użytkownikom nawiązywanie połączeń z sieciami Wi-Fi, użyj profilów sieci Wi-Fi."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0b1b86ed-2e80-474d-8437-17dd4bc07b55
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 985b3d14091f1adff15ae08dd95800640363d2f2


---

# <a name="configure-devices-to-connect-to-your-corporate-wi-fi-networks"></a>Konfigurowanie urządzeń do łączenia się z firmową siecią Wi-Fi

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Aby wdrożyć ustawienia sieci bezprzewodowej dla użytkowników i urządzeń w Twojej organizacji, użyj profilu sieci Wi-Fi usługi Microsoft Intune. W przypadku wdrożenia profilu sieci Wi-Fi użytkownicy mają dostęp do firmowej sieci Wi-Fi bez konieczności samodzielnego jej konfigurowania.

Załóżmy, że zainstalowano nową sieć Wi-Fi o nazwie **Sieć Wi-Fi firmy Contoso** i chcesz skonfigurować wszystkie urządzenia z systemem iOS do łączenia się z tą siecią. Oto proces:

![Podsumowanie procesu profilu sieci Wi-Fi](..\media\wi-fi-process-diagram.png)

1.   Utwórz profil sieci Wi-Fi zawierający ustawienia wymagane do łączenia się z siecią bezprzewodową **Sieć Wi-Fi firmy Contoso**.

2.   Wdróż profil w grupie użytkowników z urządzeniami z systemem iOS.

3.   Użytkownicy znajdują nową sieć **Sieć Wi-Fi firmy Contoso** na liście sieci bezprzewodowych i mogą łatwo łączyć się z tą siecią.


## <a name="create-a-wi-fi-profile"></a>Tworzenie profilu sieci Wi-Fi

Profile sieci Wi-Fi można wdrażać na poniższych platformach:

-   Android 4.0 i nowsze

-   Program Android for Work   

-   System iOS 8.0 i nowsze

-   System Mac OS X 10.9 lub nowszy

W przypadku urządzeń z systemami operacyjnymi Windows 8.1 oraz Windows 10 (na komputery i urządzenia mobilne) można zaimportować profil konfiguracji sieci Wi-Fi, który został wcześniej wyeksportowany do pliku. Aby uzyskać szczegółowe informacje, zobacz [Eksportowanie lub importowanie profilu konfiguracji sieci Wi-Fi dla urządzeń z systemem Windows](#export-or-import-a-wi-fi-configuration-profile-for-windows-devices).

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) wybierz kolejno pozycje **Zasady** &gt; **Dodaj zasady**.

2.  Wybierz jeden z następujących typów zasad, a następnie wybierz pozycję **Utwórz zasady**:

    -   Profil sieci Wi-Fi (system Android 4 i nowsze)

    -   Profil sieci Wi-Fi (program Android for Work)

    -   Profil sieci Wi-Fi (system iOS 8.0 i nowsze)

    -   Profil sieci Wi-Fi (system Mac OS X 10.9 lub nowszy)


Nie ma żadnych zalecanych ustawień dla tego typu zasad. Należy utworzyć zasady niestandardowe.

3.  Podaj nazwę i opis profilu.

4. Określ wartości w obszarze **Połączenia sieciowe**.
 - **Identyfikator zestawu usług (SSID)**: wybierz tę opcję, jeśli użytkownicy mają widzieć nazwę sieci, a nie identyfikator SSID.
 - **Połącz, gdy sieć nie rozgłasza swojej nazwy (SSID)**: wybierz tę opcję, aby umożliwić urządzeniom łączenie się z siecią, gdy nie jest ona widoczna na liście sieci (ponieważ jest ukryta i nie rozgłasza swojej nazwy).

5. Skonfiguruj opcje w obszarze **Ustawienia zabezpieczeń** dla wybranej platformy. Dostępne ustawienia zależą od wybranych typów zabezpieczeń. Opisano je w części [Ustawienia zabezpieczeń](#security-settings).

6. Skonfiguruj **ustawienia serwera proxy** (dotyczy tylko systemów iOS i MAC OS X).

    |Nazwa ustawienia|Więcej informacji|Kiedy używać|
    |----------------|-------------------|-------------|
    |**Ustawienia serwera proxy dla tego połączenia Wi-Fi**|Wybierz typ ustawień serwera proxy:<br /><br />-   **Brak** (domyślnie)<br />-   **Ręczne** — ręcznie podaj adres URL i numer portu serwera proxy.<br />-   **Automatyczne** — skonfiguruj serwer proxy przy użyciu pliku konfiguracji.|Zawsze|
    |**Adres serwera proxy** i **Numer portu**|Podaj adres URL i numer portu serwera proxy.|Jeśli opcja **Ustawienia serwera proxy dla tego połączenia Wi-Fi** ma wartość **Ręczne**|
    |**Adres URL serwera proxy**|Podaj adres URL pliku zawierającego ustawienia serwera proxy.|Jeśli opcja **Ustawienia serwera proxy dla tego połączenia Wi-Fi** ma wartość **Automatyczne**|

7.  Zapisywanie profilu sieci Wi-Fi

Nowe zasady są wyświetlane w węźle **Zasady konfiguracji** w obszarze roboczym **Zasady**. Informacje o wdrażaniu usługi można znaleźć w temacie **Następne kroki**.

## <a name="export-or-import-a-wi-fi-configuration-profile-for-windows-devices"></a>Eksportowanie lub importowanie profilu konfiguracji sieci Wi-Fi dla urządzeń z systemem Windows

W przypadku urządzeń z systemami operacyjnymi Windows 8.1 oraz Windows 10 (na komputery i urządzenia mobilne) można zaimportować profil konfiguracji sieci Wi-Fi, który został wcześniej wyeksportowany do pliku.

### <a name="export-a-wi-fi-profile"></a>Eksportowanie profilu sieci Wi-Fi
W systemie Windows można przy użyciu narzędzia **netsh wlan** wyeksportować istniejący profil sieci Wi-Fi do pliku XML, który odczyta usługa Intune. Na komputerze z systemem Windows, na którym już zainstalowano wymagany profil sieci Wi-Fi, wykonaj następujące kroki:

1.  Utwórz folder lokalny dla wyeksportowanych profilów sieci Wi-Fi. Na przykład utwórz folder o nazwie **c:\WiFi**.

2.  Otwórz wiersz polecenia jako administrator.

3.  Uruchom polecenie `netsh wlan show profiles` i określ nazwę profilu, który chcesz wyeksportować.  W tym przykładzie nazwa profilu brzmi **WiFiName**.

4.  Uruchom następujące polecenie: `netsh wlan export profile name="ProfileName" folder=c:\Wifi`. Spowoduje to utworzenie pliku profilu sieci Wi-Fi o nazwie **Wi-Fi-WiFiName.xml** w folderze docelowym.

### <a name="import-a-wi-fi-profile"></a>Importowanie profilu sieci Wi-Fi
Aby zaimportować zestaw ustawień sieci Wi-Fi, które można następnie wdrożyć dla wymaganych grup użytkowników lub urządzeń, użyj zasady typu **Zasady importowania profilów Wi-Fi systemu Windows**.


1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) kliknij pozycje **Zasady** &gt; **Dodaj zasady**.

2.  Skonfiguruj zasady typu **Windows** i **Importowanie profilów sieci Wi-Fi (system Windows 8.1 i nowsze)**.

    Te zasady można zastosować do urządzeń z systemami operacyjnymi Windows 8.1 i Windows 10 na komputery i urządzenia mobilne.

    Można tworzyć i wdrażać tylko *niestandardowe* zasady importowania profilów sieci Wi-Fi systemu Windows. Zalecane ustawienia są niedostępne.

3.  Określ następujące wartości ogólne zasady importowania profilów Wi-Fi systemu Windows:

    |Nazwa ustawienia|Więcej informacji|
    |----------------|--------------------|
    |**Nazwa**|Wprowadź unikatową nazwę profilu sieci Wi-Fi, aby zidentyfikować go w konsoli usługi Intune.|
    |**Opis**|Podaj opis profilu sieci Wi-Fi i inne odpowiednie informacje, które pomogą Ci go zlokalizować.|

4.  W obszarze nagłówka **Niestandardowy profil sieci Wi-Fi** podaj następujące wartości:

    |Nazwa ustawienia|Więcej informacji|
    |----------------|--------------------|
    |**Plik profilu konfiguracji**|Wybierz pozycję **Importuj**, aby wybrać plik XML zawierający ustawienia profilu sieci Wi-Fi, który chcesz zaimportować do usługi Intune.|
    |**Nazwa niestandardowego profilu konfiguracji (wyświetlana dla użytkowników)**|Wybierz sposób wyświetlania nazwy profilu konfiguracji sieci Wi-Fi w takiej postaci, w jakiej będzie ona pokazywana użytkownikom na ich urządzeniach.|
    |**Szczegóły profilu konfiguracji**|Wybierz sposób wyświetlania kodu XML wybranego profilu konfiguracji.|

5.  Gdy skończysz, wybierz pozycję **Zapisz zasady**.

6.  Nowe zasady zostaną wyświetlone w węźle **Zasady konfiguracji** w obszarze roboczym **Zasady** .

## <a name="deploy-the-profile"></a>Wdrażanie profilu

Ze względu na to, że profil jest typem zasad, w celu jego wdrożenia użyj obszaru roboczego **Zasady**.

1.  W obszarze roboczym **Zasady** wybierz zasady do wdrożenia, a następnie wybierz pozycję **Zarządzaj wdrożeniem**.

2.  W oknie dialogowym **Zarządzanie wdrażaniem** :

    -   **Aby wdrożyć zasady**: wybierz dla nich co najmniej jedną grupę. Następnie wybierz kolejno pozycje **Dodaj** &gt; **OK**.

    -   **Aby zamknąć okno dialogowe bez wdrażania**: kliknij przycisk **Anuluj**.


Na stronie **Przegląd** w obszarze roboczym **Zasady** są wyświetlane problemy z zasadami, które wymagają uwagi. Ponadto w obszarze roboczym Pulpit nawigacyjny jest wyświetlane podsumowanie stanu.

## <a name="security-settings"></a>Ustawienia zabezpieczeń
Te tabele zawierają szczegółowe informacje dotyczące ustawień zabezpieczeń, które są dostępne dla profilów sieci Wi-Fi systemu Android, iOS i Mac OS X.

### <a name="security-settings-for-android-devices"></a>Ustawienia zabezpieczeń dla urządzeń z systemem Android

  |Nazwa ustawienia|Więcej informacji|Kiedy używać|
|----------------|--------------------|-------------|
|**Typ zabezpieczeń**|Wybierz protokół zabezpieczeń sieci bezprzewodowej:<br /><br />-   **WPA-Enterprise/WPA2-Enterprise**<br />-   **Bez uwierzytelnienia (otwarte)**, jeśli sieć jest niezabezpieczona.|Zawsze|
|**Typ protokołu EAP**|Wybierz typ protokołu uwierzytelniania rozszerzonego (EAP) używany do uwierzytelniania zabezpieczonych połączeń bezprzewodowych:<br /><br />-   **EAP-TLS**<br />-   **PEAP**<br />-   **EAP-TTLS**|Jeśli wybrano typ zabezpieczeń **WPA-Enterprise/WPA2-Enterprise**.|
|**Wybierz certyfikaty główne do sprawdzania poprawności serwera**|Kliknij pozycję **Wybierz**, a następnie wskaż profil zaufanego certyfikatu głównego używany do uwierzytelniania połączenia. Aby uzyskać więcej informacji o sposobie tworzenia profilu zaufanego certyfikatu głównego, zobacz temat [Bezpieczny dostęp do zasobów przy użyciu profilów certyfikatów](secure-resource-access-with-certificate-profiles.md).|Jeśli wybrano dowolną wartość ustawienia **Typ protokołu EAP**.|
|**Metoda uwierzytelniania**|Wybierz metodę uwierzytelniania używaną dla połączenia:<br /><br />-   **Certyfikaty**, aby określić certyfikat klienta<br />-   **Nazwa użytkownika i hasło**, aby określić inną metodę uwierzytelniania|Dla ustawienia **Typ protokołu EAP** jest wybrana wartość **PEAP** lub **EAP-TTLS**.|
|**Wybierz metodę inną niż EAP na potrzeby uwierzytelniania (tożsamość wewnętrzna)**|Wybierz sposób uwierzytelniania połączenia:<br /><br />-   **Brak**<br />-   **Hasło nieszyfrowane (PAP)**<br />-   **Protokół uwierzytelniania typu Challenge Handshake (CHAP)**<br />-   **Microsoft CHAP (MS-CHAP)**<br />-   **Microsoft CHAP wersja 2 (MS-CHAP v2)**<br /><br />Dostępne opcje zależą od wybranego typu protokołu EAP.|Dla ustawienia **Metoda uwierzytelniania** wybrana jest wartość **Nazwa użytkownika i hasło**.|
|**Włącz prywatność tożsamości (tożsamość zewnętrzna)**|Podaj tekst, który będzie wysyłany w odpowiedzi na żądanie podania tożsamości zgłaszane przez protokół EAP. Ten tekst może mieć dowolną wartość. Podczas uwierzytelniania początkowo jest wysyłana tożsamość anonimowa. Następnie za pośrednictwem bezpiecznego tunelu jest wysyłana tożsamość rzeczywista.|Jeśli ustawienie **Typ protokołu EAP** ma wartość **PEAP** lub **EAP-TTLS**.|
|**Wybierz certyfikat klienta na potrzeby uwierzytelniania klienta (certyfikat tożsamości)**|Kliknij pozycję **Wybierz**, a następnie wskaż profil certyfikatu SCEP używany do uwierzytelniania połączenia. Aby uzyskać więcej informacji o sposobie tworzenia profilu certyfikatu SCEP, zobacz temat [Bezpieczny dostęp do zasobów przy użyciu profilów certyfikatów](secure-resource-access-with-certificate-profiles.md).|Jeśli typ zabezpieczeń to **WPA-Enterprise/WPA2-Enterprise** i dla ustawienia **Typ protokołu EAP** wybrano dowolną wartość.|

### <a name="security-settings-for-ios-and-mac-os-x-devices"></a>Ustawienia zabezpieczeń dla urządzeń z systemem iOS i Mac OS X

  |Nazwa ustawienia|Więcej informacji|Kiedy używać|
|----------------|--------------------|-------------|
|**Typ zabezpieczeń**|Wybierz protokół zabezpieczeń sieci bezprzewodowej:<br /><br />-   **WPA-Personal/WPA2-Personal**<br />-   **WPA-Enterprise/WPA2-Enterprise**<br />-   **WEP**<br />-   **Bez uwierzytelnienia (otwarte)**, jeśli sieć jest niezabezpieczona.|Zawsze|
|**Typ protokołu EAP**|Wybierz typ protokołu uwierzytelniania rozszerzonego (EAP) używany do uwierzytelniania zabezpieczonych połączeń bezprzewodowych:<br /><br />-   **EAP-TLS**<br />-   **PEAP**<br />-   **EAP-TLS**<br />-   **EAP-AST**<br />-   **LEAP**<br />-   **EAP-SIM**|Jeśli wybrano typ zabezpieczeń **WPA-Enterprise/WPA2-Enterprise**.|
|**Nazwy zaufanych certyfikatów serwera**|Wybierz profil zaufanego certyfikatu głównego używany do uwierzytelniania połączenia. Aby uzyskać więcej informacji o sposobie tworzenia profilu zaufanego certyfikatu głównego, zobacz temat [Bezpieczny dostęp do zasobów przy użyciu profilów certyfikatów](secure-resource-access-with-certificate-profiles.md).|Jeśli wybrano typ protokołu EAP **EAP-TLS**, **PEAP**, **EAP-TTLS** lub **EAP-FAST**.|
|**Użyj uwierzytelniania PAC (Protected Access Credential)**|Wybierz tę wartość, aby ustanowić uwierzytelniony tunel między klientem i serwerem uwierzytelniania przy użyciu uwierzytelniania PAC. Zostanie użyty istniejący plik PAC, jeśli jest obecny.|Jeśli dla ustawienia **Typ protokołu EAP** wybrano wartość **EAP-FAST**.|
|**Aprowizuj uwierzytelnianie PAC**|Służy do wybierania pliku PAC na urządzeniach.<br /><br />Gdy ta opcja jest używana, można także wybrać opcję **Zapewnij anonimowe uwierzytelnianie PAC**, aby zagwarantować, że plik PAC zostanie skonfigurowany bez uwierzytelniania serwera.|Jeśli wybrano opcję **Użyj uwierzytelniania PAC (Protected Access Credential)**.|
|**Metoda uwierzytelniania**|Wybierz metodę uwierzytelniania używaną dla połączenia:<br /><br /><ul><li>**Certyfikaty** , aby określić certyfikat klienta.</li><li>**Nazwa użytkownika i hasło**, aby określić jedną z poniższych metod uwierzytelniania bez użycia protokołu EAP (jest to również nazywane tożsamością wewnętrzną):<br /><br /><ul><li>**Brak**</li><li>**Hasło nieszyfrowane (PAP)**</li><li>**Protokół uwierzytelniania typu Challenge Handshake (CHAP)**</li><li>**Microsoft CHAP (MS-CHAP)**</li><li>**Microsoft CHAP wersja 2 (MS-CHAP v2)**</li><li>**EAP-TLS**</li></ul></li></ul>|Jeśli ustawienie **Typ protokołu EAP** ma wartość **PEAP** lub **EAP-TTLS**.|
|**Wybierz certyfikat klienta na potrzeby uwierzytelniania klienta (certyfikat tożsamości)**|Wybierz profil certyfikatu SCEP używany do uwierzytelniania połączenia. Aby uzyskać więcej informacji o sposobie tworzenia profilu certyfikatu SCEP, zobacz temat [Bezpieczny dostęp do zasobów przy użyciu profilów certyfikatów](secure-resource-access-with-certificate-profiles.md).|Jeśli typ zabezpieczeń to **WPA-Enterprise/WPA2-Enterprise**, a dla ustawienia **Typ protokołu EAP** wybrano wartość **EAP-TLS**, **PEAP** lub **EAP-TTLS**.|
|**Włącz prywatność tożsamości (tożsamość zewnętrzna)**|Podaj tekst, który będzie wysyłany w odpowiedzi na żądanie podania tożsamości zgłaszane przez protokół EAP. Ten tekst może mieć dowolną wartość.<br /><br />Podczas uwierzytelniania początkowo jest wysyłana tożsamość anonimowa. Następnie za pośrednictwem bezpiecznego tunelu jest wysyłana tożsamość rzeczywista.|Jeśli dla ustawienia **Typ protokołu EAP** wybrano wartość **PEAP**, **EAP-TTLS** lub **EAP-FAST**.|


### <a name="see-also"></a>Zobacz także
Dowiedz się, jak utworzyć profil sieci Wi-Fi z użyciem klucza wstępnego — zobacz temat [Tworzenie profilu sieci Wi-Fi z użyciem klucza wstępnego](pre-shared-key-wi-fi-profile.md).



<!--HONumber=Dec16_HO2-->


