---
title: Używanie certyfikatów kluczy prywatnych i publicznych w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dodawanie lub tworzenie certyfikatów PKCS (Public Key Cryptography Standards) za pomocą usługi Microsoft Intune, w tym kroki eksportowania certyfikatu głównego, konfigurowania szablonu certyfikatów, pobierania i instalowania Łącznika certyfikatów usługi Intune (NDES), tworzenia profilu konfiguracji urządzenia oraz tworzenia profilu certyfikatu PKCS na platformie Azure i w urzędzie certyfikacji.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 08/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5ee5ef1b5c59bbef3834d44354508b767ae99088
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71722933"
---
# <a name="configure-and-use-pkcs-certificates-with-intune"></a>Konfigurowanie certyfikatów PKCS i korzystanie z nich za pomocą usługi Intune

Usługa Intune obsługuje korzystanie z certyfikatów pary kluczy prywatny-publiczny (PKCS). Ten artykuł ułatwia skonfigurowanie wymaganej infrastruktury, takiej jak lokalne łączniki certyfikatów, wyeksportowanie certyfikatu PKCS, a następnie dodanie certyfikatu do profilu konfiguracji urządzenia w usłudze Intune.

Usługa Microsoft Intune obejmuje wbudowane ustawienia umożliwiające korzystanie z certyfikatów PKCS na potrzeby dostępu do zasobów organizacji i uwierzytelniania w nich. Certyfikaty służą do uwierzytelniania i zabezpieczania dostępu do zasobów firmowych, takich jak sieć VPN lub sieć WiFi. Te ustawienia wdraża się na urządzeniach przy użyciu profilów konfiguracji urządzeń w usłudze Intune.

Aby uzyskać więcej informacji o korzystaniu z zaimportowanych certyfikatów PKCS, zobacz artykuł o [zaimportowanych certyfikatach PFX](certificates-imported-pfx-configure.md).


## <a name="requirements"></a>Wymagania

Aby korzystać z certyfikatów PKCS za pomocą usługi Intune, musisz mieć następującą infrastrukturę:

- **Domena usługi Active Directory**:  
  Wszystkie serwery wymienione w tej sekcji muszą być dołączone do Twojej domeny usługi Active Directory.

  Aby uzyskać więcej informacji na temat instalowania i konfigurowania usługi Active Directory Domain Services (AD DS), zobacz [Projekt i planowanie AD DS](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning).

- **Urząd certyfikacji**:  
   Urząd certyfikacji przedsiębiorstwa.

  Aby uzyskać informacje o sposobie instalowania i konfigurowania Usług certyfikatów Active Directory (AD CS), zobacz [Usługi certyfikatów Active Directory — przewodnik krok po kroku](https://technet.microsoft.com/library/cc772393).

  > [!WARNING]  
  > Usługa Intune wymaga uruchomienia usług AD CS z urzędu certyfikacji przedsiębiorstwa (CA), a nie autonomicznego urzędu certyfikacji.

- **Klient**:  
  Na potrzeby nawiązania połączenia z urzędem certyfikacji przedsiębiorstwa.

- **Certyfikat główny**:  
  Wyeksportowana kopia certyfikatu głównego z urzędu certyfikacji przedsiębiorstwa.

- **Łącznik certyfikatów usługi Microsoft Intune** (nazywany także *Łącznikiem certyfikatów usługi NDES*):  
  W portalu usługi Intune przejdź do pozycji **Konfiguracja urządzenia** > **Łączniki certyfikatu** > **Dodaj** i postępuj zgodnie z *krokami instalowania łącznika dla standardu PKCS #12*. Użyj linku pobierania w portalu, aby rozpocząć pobieranie instalatora łącznika certyfikatów w postaci pliku **NDESConnectorSetup.exe**.  

  Usługa Intune obsługuje do 100 wystąpień tego łącznika na dzierżawę, z każdym wystąpieniem na osobnym serwerze z systemem Windows. Wystąpienie tego łącznika można zainstalować na tym samym serwerze, na którym znajduje się wystąpienie łącznika certyfikatu PFX dla Microsoft Intune. W przypadku korzystania z wielu łączników infrastruktura łączników obsługuje wysoką dostępność i równoważenie obciążenia, ponieważ dowolne dostępne wystąpienie łącznika może przetwarzać żądania certyfikatów PKCS. 

  Ten łącznik przetwarza żądania certyfikatu PKCS używane do uwierzytelniania lub podpisywania wiadomości e-mail za pomocą protokołu S/MIME.

  Łącznik certyfikatów usługi Microsoft Intune obsługuje też tryb Federal Information Processing Standard (FIPS). Tryb FIPS nie jest wymagany, ale gdy jest on włączony, możesz wystawiać i odwoływać certyfikaty.

- **Łącznik certyfikatów PFX dla usługi Microsoft Intune**:  
  Jeśli zamierzasz korzystać z szyfrowania wiadomości e-mail za pomocą protokołu S/MIME, pobierz z portalu usługi Intune łącznik *PFX Certificate Connector*, który obsługuje importowanie certyfikatów PFX.  Przejdź do pozycji **Konfiguracja urządzenia** > **Łączniki certyfikatu** > **Dodaj** i postępuj zgodnie z *krokami instalowania łącznika dla zaimportowanych certyfikatów PFX*. Użyj linku pobierania w portalu, aby rozpocząć pobieranie instalatora **PfxCertificateConnectorBootstrapper.exe**. 

  Każda dzierżawa usługi Intune obsługuje pojedyncze wystąpienie tego łącznika. Możesz zainstalować ten łącznik na tym samym serwerze jako wystąpienie łącznika certyfikatu usługi Microsoft Intune.

  Ten łącznik obsługuje żądania dotyczące plików PFX zaimportowanych do usługi Intune na potrzeby szyfrowania wiadomości e-mail za pomocą protokołu S/MIME dla określonego użytkownika.  

  Ten łącznik może zaktualizować się automatycznie po udostępnieniu nowej wersji. Aby używać możliwości aktualizacji:
  - Zainstaluj łącznik PFX Certificate Connector for Microsoft Intune na serwerze.  
  - Aby automatycznie otrzymywać ważne aktualizacje, upewnij się, że zapory są otwarte, umożliwiając łącznikowi komunikację z hostem **autoupdate.msappproxy.net** na porcie **443**.   

  Aby uzyskać więcej informacji o sieciowych punktach końcowych, do których musi mieć dostęp usługa Intune oraz łącznik, zobacz artykuł [Punkty końcowe sieci dla usługi Microsoft Intune](../fundamentals/intune-endpoints.md).

- **Windows Server**:  
  Używasz systemu Windows Server do hostowania:

  - Łącznik certyfikatów usługi Microsoft Intune — na potrzeby scenariuszy uwierzytelniania i szyfrowania wiadomości e-mail za pomocą protokołu S/MIME
  - Łącznik certyfikatów PFX dla usługi Microsoft Intune — na potrzeby scenariuszy szyfrowania wiadomości e-mail za pomocą protokołu S/MIME.

  W usłudze Intune łącznik *PFX Certificate Connector* można zainstalować na tym samym serwerze co *Łącznik certyfikatów usługi Microsoft Intune*.
  
## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Eksportowanie certyfikatu głównego z urzędu certyfikacji przedsiębiorstwa

Do uwierzytelnienia urządzenia za pomocą sieci VPN, sieci WiFi lub innych zasobów urządzenie potrzebuje certyfikatu głównego lub pośredniego urzędu certyfikacji. Poniższe kroki objaśniają, jak uzyskać wymagany certyfikat z Twojego urzędu certyfikacji przedsiębiorstwa.

**Użyj wiersza polecenia**:  
1. Zaloguj się do serwera głównego urzędu certyfikacji przy użyciu konta administratora.
 
2. Przejdź do pozycji **Start** > **Uruchom**, a następnie wpisz **Cmd**, aby otworzyć wiersz polecenia. 
    
3. Podaj polecenie **certutil -ca.cert ca_name.cer**, aby wyeksportować certyfikat główny jako plik o nazwie *ca_name.cer*.



## <a name="configure-certificate-templates-on-the-ca"></a>Konfigurowanie szablonów certyfikatów w urzędzie certyfikacji

1. Zaloguj się do swojego urzędu certyfikacji przedsiębiorstwa za pomocą konta z uprawnieniami administracyjnymi.
2. Otwórz konsolę **Urząd certyfikacji**, kliknij prawym przyciskiem myszy pozycję **Szablony certyfikatów** i wybierz pozycje **Zarządzaj**.
3. Znajdź szablon certyfikatu **Użytkownik**, kliknij go prawym przyciskiem myszy i wybierz pozycję **Duplikuj szablon**. Zostanie otwarty obszar **Właściwości nowego szablonu**.

    > [!NOTE]
    > W scenariuszach podpisywania i szyfrowania wiadomości e-mail za pomocą protokołu S/MIME wielu administratorów używa oddzielnych certyfikatów do podpisywania i szyfrowania. Jeśli używasz usług certyfikatów usługi Microsoft Active Directory, możesz użyć szablonu **Tylko podpis programu Exchange** na potrzeby certyfikatów podpisywania wiadomości e-mail za pomocą protokołu S/MIME i szablonu **Użytkownik programu Exchange** na potrzeby certyfikatów szyfrowania protokołu S/MIME.  Jeśli używasz urzędu certyfikacji innej firmy, zalecane jest przejrzenie ich wskazówek dotyczących definiowania szablonów podpisywania i szyfrowania.

4. Na karcie **Zgodność**:

    - W opcji **Urząd certyfikacji** podaj wartość **Windows Server 2008 R2**
    - W opcji **Odbiorca certyfikatu** podaj wartość **Windows 7 / Server 2008 R2**

5. Na karcie **Ogólne** w polu **Nazwa wyświetlana szablonu** wpisz zrozumiały dla Ciebie tekst opisowy.

    > [!WARNING]
    > Domyślnie pole **Nazwa szablonu** ma taką samą wartość jak pole **Nazwa wyświetlana szablonu** *bez spacji*. Zanotuj nazwę szablonu — będzie ona potrzebna później.

6. W obszarze **Obsługiwanie żądań** wybierz pozycję **Zezwalaj na eksportowanie klucza prywatnego**.
7. W obszarze **Kryptografia** potwierdź, że **Minimalny rozmiar klucza** wynosi 2048.
8. W obszarze **Nazwa podmiotu** wybierz pozycję **Podaj w żądaniu**.
9. W obszarze **Rozszerzenia** upewnij się, że w sekcji **Zasady aplikacji** wyświetlane są pozycje System szyfrowania plików, Bezpieczna poczta e-mail i Uwierzytelnienie klienta.

    > [!IMPORTANT]
    > W przypadku szablonów certyfikatów dla systemu iOS przejdź na kartę **Rozszerzenia**, zaktualizuj pozycję **Użycie klucza** i upewnij się, że opcja **Podpis jest dowodem pochodzenia** nie jest zaznaczona.

10. W obszarze **Zabezpieczenia** dodaj konto komputera dla serwera, na którym instalowany jest Łącznik certyfikatów usługi Microsoft Intune. Nadaj dla tego konta uprawnienia **Odczyt** i **Rejestracja**.
11. Wybierz kolejno pozycje **Zastosuj** > **OK**, aby zapisać szablon certyfikatu. Zamknij okno **Konsola szablonów certyfikatów**.
12. W konsoli **Urząd certyfikacji** kliknij prawym przyciskiem myszy pozycję **Szablony certyfikatów** > **Nowy** > **Szablon certyfikatu do wystawienia**. Wybierz szablon utworzony w poprzednich krokach. Wybierz przycisk **OK**.
13. W przypadku serwera do zarządzania certyfikatami dla zarejestrowanych urządzeń i użytkowników wykonaj następujące kroki:

    1. Kliknij prawym przyciskiem myszy urząd certyfikacji, a następnie wybierz pozycję **Właściwości**.
    2. Na karcie Zabezpieczenia dodaj konto komputera serwera, na którym uruchamiasz łączniki (**Łącznik certyfikatów usługi Microsoft Intune** lub **Łącznik certyfikatów PFX dla usługi Microsoft Intune**). 
    3. Dla konta komputera przydziel uprawnienia **Wystawianie certyfikatów i zarządzanie nimi** i **Żądaj certyfikatów**.

14. Wyloguj się z urzędu certyfikacji przedsiębiorstwa.

## <a name="download-install-and-configure-the-microsoft-intune-certificate-connector"></a>Pobieranie, instalowanie i konfigurowanie Łącznika certyfikatów usługi Microsoft Intune

> [!IMPORTANT]  
> Łącznika certyfikatów usługi Microsoft Intune nie można zainstalować na hoście wystawiającego urzędu certyfikacji, a zamiast tego należy zainstalować go na osobnym serwerze z systemem Windows.  

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz pozycję **Konfiguracja urządzenia** > **Łączniki certyfikatu** > **Dodaj**.
3. Pobierz i zapisz plik łącznika w lokalizacji dostępnej z serwera, na którym ma zostać zainstalowany łącznik.

    ![Pobieranie łącznika certyfikatów usługi Microsoft Intune](./media/certficates-pfx-configure/download-ndes-connector.png)
 

4. Po zakończeniu pobierania zaloguj się na serwerze. Następnie:

    1. Upewnij się, że jest zainstalowany program .NET 4.5 Framework lub nowszy, ponieważ jest on wymagany przez łącznik certyfikatów usługi NDES. Program .NET 4.5 Framework jest automatycznie dołączany do systemu Windows Server 2012 R2 i nowszych wersji.
    2. Uruchom Instalatora (NDESConnectorSetup.exe) i zaakceptuj lokalizację domyślną. Spowoduje ona zainstalowanie łącznika w ścieżce `\Program Files\Microsoft Intune\NDESConnectorUI`. W opcjach instalatora wybierz pozycję **Dystrybucja PFX**. Kontynuuj i ukończ instalację.
    3. Domyślnie usługa łącznika jest uruchamiana na koncie systemu lokalnego. Jeśli serwer proxy jest wymagany na potrzeby dostępu do Internetu, potwierdź, że konto usługi lokalnej może uzyskać dostęp do ustawień serwera proxy na serwerze.

5. Łącznik certyfikatów usługi Microsoft Intune powoduje otwarcie karty **Rejestracja**. Aby włączyć połączenie z usługą Intune, **zaloguj się** i wprowadź nazwę konta z globalnymi uprawnieniami administracyjnymi.
6. Na karcie **Zaawansowane** zaleca się pozostawienie zaznaczonej pozycji **Użyj konta SYSTEM na tym komputerze (domyślnie)** .
7. **Zastosuj** > **Zamknij**
8. Wróć do portalu usługi Intune (**Intune** > **Konfiguracja urządzeń** > **Łączniki certyfikatu**). Po kilku chwilach zostanie wyświetlony zielony znacznik wyboru, a **Stan połączenia** będzie ustawiony na **Aktywny**. Twój serwer łącznika może się teraz komunikować z usługą Intune.
9. Jeśli masz internetowy serwer proxy w środowisku sieciowym, może być wymagana dodatkowa konfiguracja, aby łącznik działał. Aby uzyskać więcej informacji, zobacz [Praca z istniejącymi lokalnymi serwerami proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-configure-connectors-with-proxy-servers) w dokumentacji usługi Azure Active Directory.

> [!NOTE]  
> Łącznik certyfikatów usługi Microsoft Intune obsługuje protokół TLS 1.2. Jeśli protokół TLS 1.2 jest zainstalowany na serwerze hostującym łącznik, łącznik będzie używać protokołu TLS 1.2. W przeciwnym razie będzie używany protokół TLS 1.1. Obecnie protokół TLS 1.1 jest używany do uwierzytelniania między urządzeniami a serwerem.

## <a name="create-a-trusted-certificate-profile"></a>Tworzenie profilu zaufanego certyfikatu

1. W witrynie [Azure Portal](https://portal.azure.com) przejdź do pozycji **Intune** > **Konfiguracja urządzenia** > **Profile** > **Utwórz profil**.
    ![Przejdź do usługi Intune i utwórz nowy profil zaufanego certyfikatu](./media/certficates-pfx-configure/certificates-pfx-configure-profile-new.png)

2. Wprowadź następujące właściwości:

    - **Nazwa** profilu
    - Opcjonalne określenie opisu
    - **Platforma**, na której ma być wdrożony profil
    - Ustaw wartość pola **Typ profilu** na **Zaufany certyfikat**

3. Przejdź do pozycji **Ustawienia**, a następnie wprowadź plik cer wcześniej wyeksportowanego certyfikatu głównego urzędu certyfikacji.

   > [!NOTE]
   > W zależności od platformy wybranej w ramach **Kroku 2** możesz mieć możliwość wyboru **Magazynu docelowego** certyfikatu lub jej nie mieć.

   ![Tworzenie profilu i przekazanie zaufanego certyfikatu](./media/certficates-pfx-configure/certificates-pfx-configure-profile-fill.png) 

4. Wybierz kolejno pozycje **OK** > **Utwórz**, aby zapisać profil.
5. Aby przypisać nowy profil do jednego lub wielu urządzeń, zobacz opis [przypisywania profilów urządzeń usługi Microsoft Intune](../configuration/device-profile-assign.md).

## <a name="create-a-pkcs-certificate-profile"></a>Tworzenie profilu certyfikatu PKCS

1. W witrynie [Azure Portal](https://portal.azure.com) przejdź do pozycji **Intune** > **Konfiguracja urządzenia** > **Profile** > **Utwórz profil**.
2. Wprowadź następujące właściwości:

    - **Nazwa** profilu
    - Opcjonalne określenie opisu
    - **Platforma**, na której ma być wdrożony profil
    - Ustaw wartość pola **Typ profilu** na **Certyfikat PKCS**

3. Przejdź do pozycji **Ustawienia**, a następnie wprowadź następujące właściwości:

    - **Próg odnawiania (%)** : Zalecana wartość to 20%.
    - **Okres ważności certyfikatu**: Jeśli szablon certyfikatu nie został zmieniony, wartość tej opcji może być ustawiona na jeden rok.
    - **Dostawca magazynu kluczy**: W przypadku systemu Windows wybierz miejsce przechowywania kluczy na urządzeniu.
    - **Urząd certyfikacji**: Wyświetla wewnętrzną w pełni kwalifikowaną nazwę domeny (nazwę FQDN) urzędu certyfikacji przedsiębiorstwa.
    - **Nazwa urzędu certyfikacji**: Wyświetla nazwę urzędu certyfikacji przedsiębiorstwa, na przykład „Urząd certyfikacji firmy Contoso”.
    - **Nazwa szablonu certyfikatu**: Nazwa szablonu utworzonego wcześniej. Należy pamiętać, że **Nazwa szablonu** domyślnie jest taka sama jak **Nazwa wyświetlana szablonu** *bez spacji*.
    - **Format nazwy podmiotu**: Ustaw tę opcję na wartość **Nazwa pospolita**, chyba że wymagana jest inna nazwa.
    - **Alternatywna nazwa podmiotu**: Ustaw tę opcję na wartość **Główna nazwa użytkownika (UPN)** , chyba że wymagana jest inna nazwa.

4. Wybierz kolejno pozycje **OK** > **Utwórz**, aby zapisać profil.
5. Aby przypisać nowy profil do jednego lub wielu urządzeń, zobacz opis [przypisywania profilów urządzeń usługi Microsoft Intune](../configuration/device-profile-assign.md).

   > [!NOTE]
   > Na urządzeniach z profilem systemu Android Enterprise certyfikaty zainstalowane przy użyciu profilu certyfikatu PKCS nie są widoczne. Aby potwierdzić pomyślne wdrożenie certyfikatu, sprawdź stan profilu w konsoli usługi Intune.

## <a name="whats-new-for-connectors"></a>Nowości dotyczące łączników
Okresowo są publikowane aktualizacje dla dwóch łączników certyfikatów. Po zaktualizowaniu łącznika możesz przeczytać w tym miejscu o wprowadzonych zmianach. 

*Łącznik certyfikatów PFX dla usługi Microsoft Intune* [obsługuje aktualizacje automatyczne](#requirements), zaś *Łącznik certyfikatów usługi Intune* należy aktualizować ręcznie.

### <a name="may-17-2019"></a>17 maja 2019 r.  
- **Łącznik certyfikatów PFX dla usługi Microsoft Intune — wersja 6.1905.0.404**  
  Zmiany w tej wersji:  
  - Rozwiązano problem polegający na tym, że istniejące certyfikaty PFX były nadal ponownie przetwarzane, co powodowało zatrzymywanie przetwarzania nowych żądań przez łącznik. 

### <a name="may-6-2019"></a>6 maja 2019 r.  
- **Łącznik certyfikatów PFX dla usługi Microsoft Intune — wersja 6.1905.0.402**  
  Zmiany w tej wersji:  
  - Odstęp czasu sondowania dla łącznika został skrócony z 5 minut do 30 sekund.
 
### <a name="april-2-2019"></a>2 kwietnia 2019 r.  
- **Łącznik certyfikatów usługi Intune — wersja 6.1904.1.0**  
  Zmiany w tej wersji:  
  - Rozwiązano problem powodujący niepowodzenie rejestracji łącznika w usłudze Intune po zalogowaniu się do łącznika przy użyciu konta administratora globalnego.  
  - Obejmuje poprawki dotyczące niezawodności odwoływania certyfikatów.  
  - Obejmuje poprawki dotyczące podwyższenia wydajności przetwarzania żądań certyfikatów PKCS.  

- **Łącznik certyfikatów PFX dla usługi Microsoft Intune — wersja 6.1904.0.401**
  > [!NOTE]  
  > Automatyczna aktualizacja dla tej wersji łącznika PFX nie będzie dostępna do 11 kwietnia 2019 r.  

  Zmiany w tej wersji:  
  - Rozwiązano problem powodujący niepowodzenie rejestracji łącznika w usłudze Intune po zalogowaniu się do łącznika przy użyciu konta administratora globalnego.  


## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje jeszcze żadnych czynności. W dalszej części [przypiszesz profil](../configuration/device-profile-assign.md) i będziesz [monitorować jego stan](../configuration/device-profile-monitor.md).

[Użyj protokołu SCEP dla certyfikatów](certificates-scep-configure.md) lub [wystaw certyfikaty PKCS z poziomu usługi internetowej Symantec PKI Manager](certificates-digicert-configure.md).
