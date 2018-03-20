---
title: "Używanie certyfikatów PKCS z usługą Microsoft Intune — Azure | Micrososft Docs"
description: "Dodawanie lub tworzenie certyfikatów Public Key Cryptography Standards za pomocą usługi Microsoft Intune, w tym kroki eksportowania certyfikatu głównego, konfigurowania szablonu certyfikatów, pobierania i instalowania Łącznika certyfikatów usługi Microsoft Intune, tworzenia profilu konfiguracji urządzenia, tworzenia profilu certyfikatu PKCS na platformie Azure i w urzędzie certyfikacji"
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c0668921f03b24b319c2c37837dbd2cc053370ca
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/08/2018
---
# <a name="configure-and-use-pkcs-certificates-with-intune"></a>Konfigurowanie certyfikatów PKCS i korzystanie z nich za pomocą usługi Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Certyfikaty służą do uwierzytelniania i zabezpieczania dostępu do zasobów firmowych, takich jak sieć VPN lub sieć WiFi. W tym artykule pokazano, jak wyeksportować certyfikat PKCS, a następnie dodać ten certyfikat do profilu usługi Intune. 

## <a name="requirements"></a>Wymagania

Aby korzystać z certyfikatów PKCS za pomocą usługi Intune, musisz mieć następującą infrastrukturę:

* Skonfigurowana istniejąca domena usługi Active Directory Domain Services (AD DS).
 
  Aby uzyskać więcej informacji na temat instalowania i konfigurowania usługi AD DS, zobacz [Projekt i planowanie AD DS](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning).

* Skonfigurowany istniejący urząd certyfikacji przedsiębiorstwa (CA).

  Aby uzyskać więcej informacji o sposobie instalowania i konfigurowania Usług certyfikatów Active Directory (AD CS), zobacz [Active Directory Certificate Services Step-by-Step Guide](https://technet.microsoft.com/library/cc772393) (Usługi certyfikatów Active Directory — przewodnik krok po kroku).

  > [!WARNING]
  > Usługa Intune wymaga uruchomienia usług AD CS z urzędu certyfikacji przedsiębiorstwa (CA), a nie autonomicznego urzędu certyfikacji.

* Klient, który jest połączony z urzędem certyfikacji przedsiębiorstwa.
* Wyeksportowana kopia certyfikatu głównego z urzędu certyfikacji przedsiębiorstwa.
* Program Łącznik certyfikatów usługi Microsoft Intune (NDESConnectorSetup.exe) pobrany z portalu usługi Intune.
* System Windows Server do hostowania programu Łącznik certyfikatów usługi Microsoft Intune (NDESConnectorSetup.exe).

## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Eksportowanie certyfikatu głównego z urzędu certyfikacji przedsiębiorstwa

Do uwierzytelniania w ramach sieci VPN, sieci Wi-Fi i innych zasobów na każdym urządzeniu wymagany jest certyfikat głównego lub pośredniego urzędu certyfikacji. Poniższe kroki objaśniają, jak uzyskać wymagany certyfikat z Twojego urzędu certyfikacji przedsiębiorstwa.

1. Zaloguj się do swojego urzędu certyfikacji przedsiębiorstwa za pomocą konta z uprawnieniami administracyjnymi.
2. Otwórz wiersz polecenia jako administrator.
3. Wyeksportuj certyfikat głównego urzędu certyfikacji (.cer) do lokalizacji, w której można będzie później uzyskać do niego dostęp.

   Przykład:

4.  Po zakończeniu działania kreatora, ale przed jego zamknięciem, kliknij pozycję **Uruchom interfejs użytkownika łącznika certyfikatów**.

   `certutil -ca.cert certnew.cer`

   Aby uzyskać więcej informacji, zobacz temat [Zadania polecenia certutil służące do zarządzania certyfikatami](https://technet.microsoft.com/library/cc772898.aspx#BKMK_ret_sign).

## <a name="configure-certificate-templates-on-the-certification-authority"></a>Konfigurowanie szablonów certyfikatów w urzędzie certyfikacji

1. Zaloguj się do swojego urzędu certyfikacji przedsiębiorstwa za pomocą konta z uprawnieniami administracyjnymi.
2. Otwórz konsolę **Urząd certyfikacji**, kliknij prawym przyciskiem myszy pozycję **Szablony certyfikatów** i wybierz pozycje **Zarządzaj**.
3. Zlokalizuj szablon certyfikatu **Użytkownik**, kliknij go prawym przyciskiem myszy i wybierz pozycję **Duplikuj szablon**. Zostanie otwarty obszar **Właściwości nowego szablonu**.
4. Na karcie **Zgodność**: 
   * W opcji **Urząd certyfikacji** podaj wartość **Windows Server 2008 R2**
   * W opcji **Odbiorca certyfikatu** podaj wartość **Windows 7 / Server 2008 R2**
5. Na karcie **Ogólne**:
   * W polu **Nazwa wyświetlana szablonu** wpisz zrozumiały dla Ciebie tekst opisowy.

   > [!WARNING]
   > Domyślnie pole **Nazwa szablonu** ma taką samą wartość jak pole **Nazwa wyświetlana szablonu** *bez spacji*. Zanotuj nazwę szablonu — będzie ona potrzebna później.

6. W obszarze **Obsługiwanie żądań** wybierz pozycję **Zezwalaj na eksportowanie klucza prywatnego**.
7. W obszarze **Kryptografia** potwierdź, że **Minimalny rozmiar klucza** wynosi 2048.
8. W obszarze **Nazwa podmiotu** wybierz pozycję **Podaj w żądaniu**.
9. W obszarze **Rozszerzenia** upewnij się, że w sekcji **Zasady aplikacji** wyświetlane są pozycje System szyfrowania plików, Bezpieczna poczta e-mail i Uwierzytelnienie klienta.
    
      > [!IMPORTANT]
      > W przypadku szablonów certyfikatów dla systemu iOS i macOS przejdź na kartę **Rozszerzenia**, zaktualizuj pozycję **Użycie klucza** i upewnij się, że opcja **Podpis jest dowodem pochodzenia** nie jest zaznaczona.

10. W obszarze **Zabezpieczenia** dodaj konto komputera dla serwera, na którym instalowany jest Łącznik certyfikatów usługi Microsoft Intune.
    * Nadaj dla tego konta uprawnienia **Odczyt** i **Rejestracja**.
11. Wybierz pozycję **Zastosuj**, a następnie wybierz pozycję **OK**, aby zapisać szablon certyfikatu.
12. Zamknij okno **Konsola szablonów certyfikatów**.
13. W konsoli **Urząd certyfikacji** kliknij prawym przyciskiem myszy pozycję **Szablony certyfikatów**, **Nowy**, **Szablon certyfikatu do wystawienia**.
    * Wybierz szablon utworzony w poprzednich krokach, a następnie wybierz pozycję **OK**.
14. W przypadku serwera do zarządzania certyfikatami w imieniu urządzeń i użytkowników zarejestrowanych w usłudze Intune wykonaj następujące kroki:

    a. Kliknij prawym przyciskiem myszy urząd certyfikacji, a następnie wybierz pozycję **Właściwości**.

    b. Na karcie Zabezpieczenia dodaj konto komputera serwera, na którym uruchamiasz program Łącznik certyfikatów usługi Microsoft Intune.
      * Dla konta komputera przydziel uprawnienia **Wystawianie certyfikatów i zarządzanie nimi** i **Żądaj certyfikatów**.
15. Wyloguj się z urzędu certyfikacji przedsiębiorstwa.

## <a name="download-install-and-configure-the-microsoft-intune-certificate-connector"></a>Pobieranie, instalowanie i konfigurowanie programu Łącznik certyfikatów usługi Microsoft Intune

![ConnectorDownload][ConnectorDownload]

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi** i wykonaj filtrowanie pod kątem usługi **Intune**. Wybierz pozycję **Microsoft Intune**, a następnie wybierz pozycję **Konfiguracja urządzeń**. 
2. Wybierz pozycję **Urząd certyfikacji**, wybierz pozycję **Dodaj**, a następnie wybierz pozycję **Pobierz plik łącznika**. Zapisz pobraną zawartość w lokalizacji dostępnej z serwera, na którym zostanie ona zainstalowana. 
3. Zaloguj się do tego serwera i uruchom instalatora: 

    1. Zaakceptuj lokalizację domyślną. Spowoduje ona zainstalowanie łącznika w ścieżce `\Program Files\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe`.
    2. W opcjach instalatora wybierz pozycję **Dystrybucja PFX** i wybierz pozycję **Dalej**.
    3. Wybierz pozycję **Zainstaluj** i zaczekaj na ukończenie instalacji.
    4. Gdy instalacja się zakończy, zaznacz pozycję **Uruchom łącznik usługi Intune**, a następnie wybierz pozycję **Zakończ**.

4. W oknie łącznika usługi NDES powinna zostać otwarta karta **Rejestracja**. Aby włączyć połączenie z usługą Intune, wybierz pozycję **Zaloguj się** i wprowadź nazwę konta z globalnymi uprawnieniami administracyjnymi.
5. Na karcie **Zaawansowane** pozostaw zaznaczoną pozycję **Użyj konta SYSTEM na tym komputerze (domyślnie)**.
6. Wybierz pozycję **Zastosuj**, a następnie pozycję **Zamknij**.
7. Wróć do witryny Azure Portal (**Intune** > **Konfiguracja urządzeń** > **Urząd certyfikacji**). Po kilku minutach zostanie wyświetlony zielony znacznik wyboru, a **Stan połączenia** będzie ustawiony na **Aktywny**. Twój serwer łącznika może się teraz komunikować z usługą Intune.

## <a name="create-a-device-configuration-profile"></a>Tworzenie profilu konfiguracji urządzenia

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Przejdź do pozycji **Intune**, **Konfiguracja urządzeń**, **Profile** i wybierz pozycję **Utwórz profil**.

   ![NavigateIntune][NavigateIntune]

3. Wprowadź następujące właściwości:
   * **Nazwa** profilu
   * Opcjonalne określenie opisu
   * **Platforma**, na której ma być wdrożony profil
   * Ustaw wartość pola **Typ profilu** na **Zaufany certyfikat**

4. Przejdź do pozycji **Ustawienia**, a następnie wprowadź plik cer wcześniej wyeksportowanego certyfikatu głównego urzędu certyfikacji.

   > [!NOTE]
   > W zależności od platformy wybranej w ramach **Kroku 3** możesz mieć możliwość wyboru **Magazynu docelowego** certyfikatu lub jej nie mieć.

   ![ProfileSettings][ProfileSettings]

5. Wybierz pozycję **OK**, a następnie pozycję **Utwórz**, aby zapisać profil.
6. Aby przypisać nowy profil do jednego lub wielu urządzeń, zobacz temat [Jak przypisywać profile urządzeń usługi Microsoft Intune](device-profile-assign.md).

## <a name="create-a-pkcs-certificate-profile"></a>Tworzenie profilu certyfikatu PKCS

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Przejdź do pozycji **Intune**, **Konfiguracja urządzeń**, **Profile** i wybierz pozycję **Utwórz profil**.
3. Wprowadź następujące właściwości:
   * **Nazwa** profilu
   * Opcjonalne określenie opisu
   * **Platforma**, na której ma być wdrożony profil
   * Ustaw wartość pola **Typ profilu** na **Certyfikat PKCS**
4. Przejdź do pozycji **Ustawienia**, a następnie wprowadź następujące właściwości:
   * **Próg odnawiania (%)** — zalecana wartość wynosi 20%.
   * **Okres ważności certyfikatu** — jeśli szablon certyfikatu nie został zmieniony, wartość tej opcji może być ustawiona na jeden rok.
   * **Urząd certyfikacji** — wyświetla wewnętrzną w pełni kwalifikowaną nazwę domeny (nazwę FQDN) urzędu certyfikacji przedsiębiorstwa.
   * **Nazwa urzędu certyfikacji** — wyświetla nazwę urzędu certyfikacji przedsiębiorstwa i może różnić się od poprzedniej pozycji.
   * **Nazwa szablonu certyfikatu** — nazwa szablonu utworzonego wcześniej. Należy pamiętać, że **Nazwa szablonu** domyślnie jest taka sama jak **Nazwa wyświetlana szablonu** *bez spacji*.
   * **Format nazwy podmiotu** — ta opcja powinna mieć wartość **Nazwa pospolita**, chyba że wymagana jest inna wartość.
   * **Alternatywna nazwa podmiotu** — ta opcja powinna mieć wartość **Główna nazwa użytkownika (UPN)**, chyba że wymagana jest inna.
   * **Rozszerzone użycie klucza** — jeśli w kroku 10 w sekcji [Konfigurowanie szablonów certyfikatów w urzędzie certyfikacji](#configure-certificate-templates-on-the-certification-authority) (w tym artykule) użyto ustawień domyślnych, należy spośród dostępnych opcji dodać następujące **wstępnie zdefiniowane wartości**:
      * **Dowolny cel**
      * **Uwierzytelnianie klienta**
      * **Bezpieczna poczta e-mail**
   * **Certyfikat główny** — (dla profilów systemu Android) wyświetla plik cer wyeksportowany w kroku 3 sekcji [Eksportowanie certyfikatu głównego z urzędu certyfikacji przedsiębiorstwa](#export-the-root-certificate-from-the-enterprise-ca) (w tym artykule).

5. Wybierz pozycję **OK**, a następnie pozycję **Utwórz**, aby zapisać profil.
6. Aby przypisać nowy profil do jednego lub wielu urządzeń, zobacz artykuł [Jak przypisywać profile urządzeń usługi Microsoft Intune](device-profile-assign.md).


[NavigateIntune]: ./media/certificates-pfx-configure-profile-new.png "Przejdź do usługi Intune w witrynie Azure portal i utwórz nowy profil zaufanego certyfikatu"
[ProfileSettings]: ./media/certificates-pfx-configure-profile-fill.png "Utwórz profil i przekaż zaufany certyfikat"
[ConnectorDownload]: ./media/certificates-download-connector.png "Pobierz łącznik certyfikatów z witryny Azure portal"  
