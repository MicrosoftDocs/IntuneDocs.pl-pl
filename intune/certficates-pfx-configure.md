---
title: "Konfigurowanie certyfikatów PKCS i zarządzanie nimi za pomocą usługi Intune"
titleSuffix: Intune on Azure
description: "Tworzenie i przypisywanie certyfikatów PKCS za pomocą usługi Intune."
keywords: 
author: MicrosoftGuyJFlo
ms.author: joflore
manager: angrobe
ms.date: 11/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 105b5fc73bc537eaca67a0e6943701ba25a53972
ms.sourcegitcommit: 2b35c99ca7d3dbafe2dfe1e0b9de29573db403b9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/16/2017
---
# <a name="configure-and-manage-pkcs-certificates-with-intune"></a>Konfigurowanie certyfikatów PKCS i zarządzanie nimi za pomocą usługi Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="requirements"></a>Wymagania

Aby korzystać z certyfikatów PKCS za pomocą usługi Intune, musisz mieć następującą infrastrukturę:

* Skonfigurowana istniejąca domena usługi Active Directory Domain Services (AD DS).
 
  Aby uzyskać więcej informacji o sposobie instalowania i konfigurowania usług AD DS, zobacz artykuł [Projekt i planowanie AD DS](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning).

* Skonfigurowany istniejący urząd certyfikacji przedsiębiorstwa (CA).

  Aby uzyskać więcej informacji o sposobie instalowania i konfigurowania usług certyfikatów Active Directory (AD CS), zobacz artykuł [Active Directory Certificate Services Step-by-Step Guide](https://technet.microsoft.com/library/cc772393) (Usługi certyfikatów Active Directory — przewodnik krok po kroku).

  > [!WARNING]
  > Usługa Intune wymaga uruchomienia usług AD CS z urzędu certyfikacji przedsiębiorstwa (CA), a nie autonomicznego urzędu certyfikacji.

* Klient, który jest połączony z urzędem certyfikacji przedsiębiorstwa.
* Wyeksportowana kopia certyfikatu głównego z urzędu certyfikacji przedsiębiorstwa.
* Program Łącznik certyfikatów usługi Microsoft Intune (NDESConnectorSetup.exe) pobrany z portalu usługi Intune.
* System Windows Server dostępny na potrzeby hostowania programu Łącznik certyfikatów usługi Microsoft Intune (NDESConnectorSetup.exe).

## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Eksportowanie certyfikatu głównego z urzędu certyfikacji przedsiębiorstwa

Na każdym urządzeniu wymagany jest certyfikat głównego lub pośredniego urzędu certyfikacji do uwierzytelniania w ramach sieci VPN, Wi-Fi i innych zasobów. Poniższe kroki objaśniają, jak uzyskać wymagany certyfikat z Twojego urzędu certyfikacji przedsiębiorstwa.

1. Zaloguj się do swojego urzędu certyfikacji przedsiębiorstwa za pomocą konta z uprawnieniami administracyjnymi.
2. Otwórz wiersz polecenia jako administrator.
3. Wyeksportuj certyfikat głównego urzędu certyfikacji do lokalizacji, w której można będzie później uzyskać do niego dostęp.

   Na przykład:

   `certutil -ca.cert certnew.cer`

   Aby uzyskać więcej informacji, zobacz temat [Zadania polecenia certutil służące do zarządzania certyfikatami](https://technet.microsoft.com/library/cc772898.aspx#BKMK_ret_sign).


## <a name="configure-certificate-templates-on-the-certification-authority"></a>Konfigurowanie szablonów certyfikatów w urzędzie certyfikacji

1. Zaloguj się do swojego urzędu certyfikacji przedsiębiorstwa za pomocą konta z uprawnieniami administracyjnymi.
2. Otwórz konsolę **Urząd certyfikacji**.
3. Kliknij prawym przyciskiem myszy pozycję **Szablony certyfikatów**, a następnie kliknij polecenie **Zarządzaj**.
4. Zlokalizuj szablon certyfikatu **Użytkownik**, kliknij go prawym przyciskiem myszy i wybierz opcję **Duplikuj szablon**. Zostanie otwarte okno **Właściwości nowego szablonu**.
5. Na karcie **Zgodność**
   * W opcji **Urząd certyfikacji** podaj wartość **Windows Server 2008 R2**
   * W opcji **Odbiorca certyfikatu** podaj wartość **Windows 7 / Server 2008 R2**
6. Na karcie **Ogólne**:
   * W polu **Nazwa wyświetlana szablonu** wpisz zrozumiały dla Ciebie tekst opisowy.

   > [!WARNING]
   > Domyślnie pole **Nazwa szablonu** ma taką samą wartość jak pole **Nazwa wyświetlana szablonu** *bez spacji*. Zanotuj nazwę szablonu do późniejszego użycia.

7. Na karcie **Obsługiwanie żądań** zaznacz opcję **Zezwalaj na eksportowanie klucza prywatnego**.
8. Na karcie **Kryptografia** potwierdź, że **Minimalny rozmiar klucza** wynosi 2048.
9. Na karcie **Nazwa podmiotu** wybierz przycisk radiowy **Dostarcz w żądaniu**.
10. Na karcie **Rozszerzenia** upewnij się, że w obszarze **Zasady aplikacji** wyświetlane są pozycje System szyfrowania plików, Bezpieczna poczta e-mail i Uwierzytelnienie klienta.
    
      > [!IMPORTANT]
      > W przypadku szablonów certyfikatów dla systemu iOS i macOS na karcie **Rozszerzenia** edytuj pozycję **Użycie klucza** i upewnij się, że opcja **Podpis jest dowodem pochodzenia** nie jest zaznaczona.

11. Na karcie **Zabezpieczenia** dodaj konto komputera dla serwera, na którym instalowany jest program Łącznik certyfikatów usługi Microsoft Intune.
    * Nadaj dla tego konta uprawnienia **Odczyt** i **Rejestracja**.
12. Kliknij przycisk **Zastosuj**, a następnie kliknij przycisk **OK**, aby zapisać szablon certyfikatu.
13. Zamknij okno **Konsola szablonów certyfikatów**.
14. W konsoli **Urząd certyfikacji** kliknij prawym przyciskiem myszy pozycję **Szablony certyfikatów**, **Nowy**, **Szablon certyfikatu do wystawienia**.
    * Wybierz szablon utworzony w poprzednich krokach, a następnie kliknij przycisk **OK**.
15. W przypadku serwera do zarządzania certyfikatami w imieniu urządzeń i użytkowników zarejestrowanych w usłudze Intune wykonaj następujące kroki:

    a. Kliknij prawym przyciskiem myszy urząd certyfikacji, a następnie wybierz pozycję **Właściwości**.

    b. Na karcie Zabezpieczenia dodaj konto komputera serwera, na którym uruchamiasz program Łącznik certyfikatów usługi Microsoft Intune.
      * Dla konta komputera przydziel uprawnienia **Wystawianie certyfikatów i zarządzanie nimi** i **Żądaj certyfikatów**.
16. Wyloguj się z urzędu certyfikacji przedsiębiorstwa.

## <a name="download-install-and-configure-the-microsoft-intune-certificate-connector"></a>Pobieranie, instalowanie i konfigurowanie programu Łącznik certyfikatów usługi Microsoft Intune

![ConnectorDownload][ConnectorDownload]

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Przejdź do opcji **Intune**, **Konfiguracja urządzeń**, **Urząd certyfikacji** i kliknij przycisk **Pobierz łącznik certyfikatów**.
   * Pobraną zawartość należy zapisać w lokalizacji dostępnej z serwera, na którym zostanie ona zainstalowana.
3. Zaloguj się do serwera, na którym zostanie zainstalowany program Łącznik certyfikatów usługi Microsoft Intune.
4. Uruchom Instalatora i zaakceptuj lokalizację domyślną. Łącznik zostanie zainstalowany w lokalizacji C:\Program Files\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe.

      a. Na stronie Opcje instalatora wybierz pozycję **Dystrybucja PFX** i kliknij przycisk **Dalej**.

   b. Kliknij opcję **Zainstaluj** i zaczekaj na ukończenie instalacji.

   c. Na stronie ukończenia zaznacz pole wyboru o nazwie **Uruchom łącznik usługi Intune** i kliknij przycisk **Zakończ**.

5. W oknie łącznika usługi NDES powinna zostać teraz otwarta karta **Rejestracja**. Aby włączyć połączenia z usługą Intune, należy kliknąć opcję **Zaloguj** i podać nazwę konta z uprawnieniami administracyjnymi.
6. Na karcie **Zaawansowane** można pozostawić wybrany przycisk radiowy **Użyj konta SYSTEM na tym komputerze (domyślnie)**.
7. Kliknij przycisk **Zastosuj**, a następnie **Zamknij**.
8. Teraz wróć do witryny Azure Portal. W obszarze **Intune**, **Konfiguracja urządzeń**, **Urząd certyfikacji** po kilku minutach powinien zostać wyświetlony zielony znacznik wyboru oraz słowo **Aktywne** w obszarze **Stan połączenia**. Dzięki temu możesz upewnić się, że serwer łącznika może komunikować się z usługą Intune.

## <a name="create-a-device-configuration-profile"></a>Tworzenie profilu konfiguracji urządzenia

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Przejdź do opcji **Intune**, **Konfiguracja urządzeń**, **Profile** i kliknij przycisk **Utwórz profil**.

   ![NavigateIntune][NavigateIntune]

3. Wprowadź następujące informacje:
   * **Nazwa** profilu
   * Opcjonalne określenie opisu
   * **Platforma**, na której ma być wdrożony profil
   * Ustaw wartość pola **Typ profilu** na **Zaufany certyfikat**
4. Przejdź do opcji **Ustawienia** i wskaż wyeksportowany wcześniej plik .CER certyfikatu głównego urzędu certyfikacji.

   > [!NOTE]
   > W zależności od platformy wybranej w ramach **Kroku 3** możesz mieć możliwość wyboru **Magazynu docelowego** certyfikatu lub jej nie mieć.

   ![ProfileSettings][ProfileSettings]

5. Kliknij przycisk **OK**, a następnie przycisk **Utwórz**, aby zapisać profil.
6. Aby przypisać nowy profil do jednego lub wielu urządzeń, zobacz temat [Jak przypisywać profile urządzeń usługi Microsoft Intune](device-profile-assign.md).

## <a name="create-a-pkcs-certificate-profile"></a>Tworzenie profilu certyfikatu PKCS

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Przejdź do opcji **Intune**, **Konfiguracja urządzeń**, **Profile** i kliknij przycisk **Utwórz profil**.
3. Wprowadź następujące informacje:
   * **Nazwa** profilu
   * Opcjonalne określenie opisu
   * **Platforma**, na której ma być wdrożony profil
   * Ustaw wartość pola **Typ profilu** na **Certyfikat PKCS**
4. Przejdź do opcji **Ustawienia** i podaj następujące informacje:
   * **Próg odnawiania (%)** — zalecana wartość wynosi 20%.
   * **Okres ważności certyfikatu** — jeśli nie zmieniono szablonu certyfikatu, wartość tej opcji powinna być ustawiona na jeden rok.
   * **Urząd certyfikacji** — ta opcja określa wewnętrzną w pełni kwalifikowaną nazwę domeny (nazwę FQDN) urzędu certyfikacji przedsiębiorstwa.
   * **Nazwa urzędu certyfikacji** — ta opcja określa nazwę urzędu certyfikacji przedsiębiorstwa i może różnić się od poprzedniej pozycji.
   * **Nazwa szablonu certyfikatu** — ta opcja określa nazwę utworzonego wcześniej szablonu. Należy pamiętać, że **Nazwa szablonu** domyślnie jest taka sama jak **Nazwa wyświetlana szablonu** *bez spacji*.
   * **Format nazwy podmiotu** — ta opcja powinna mieć wartość **Nazwa pospolita**, chyba że wymagana jest inna wartość.
   * **Alternatywna nazwa podmiotu** — ta opcja powinna mieć wartość **Główna nazwa użytkownika (UPN)**, chyba że wymagana jest inna.
   * **Rozszerzone użycie klucza** — jeśli w kroku 10 w poprzedniej sekcji **Konfigurowanie szablonów certyfikatów w urzędzie certyfikacji** używane są ustawienia domyślne, z pola wyboru należy dodać następujące **wstępnie zdefiniowane wartości**:
      * **Dowolny cel**
      * **Uwierzytelnianie klienta**
      * **Bezpieczna poczta e-mail**
   * **Certyfikat główny** — (dla profilów systemu Android) wartość tej opcji określa plik CER wyeksportowany w kroku 3 w poprzedniej sekcji [Eksportowanie certyfikatu głównego z urzędu certyfikacji przedsiębiorstwa](#export-the-root-certificate-from-the-enterprise-ca).

5. Kliknij przycisk **OK**, a następnie przycisk **Utwórz**, aby zapisać swój profil.
6. Aby przypisać nowy profil do jednego lub wielu urządzeń, zobacz artykuł [Jak przypisywać profile urządzeń usługi Microsoft Intune](device-profile-assign.md).


[NavigateIntune]: ./media/certificates-pfx-configure-profile-new.png "Przejdź do usługi Intune w witrynie Azure portal i utwórz nowy profil zaufanego certyfikatu"
[ProfileSettings]: ./media/certificates-pfx-configure-profile-fill.png "Utwórz profil i przekaż zaufany certyfikat"
[ConnectorDownload]: ./media/certificates-pfx-configure-connector-download.png "Pobierz łącznik certyfikatów z witryny Azure portal"
