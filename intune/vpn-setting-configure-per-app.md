---
title: Konfigurowanie sieci VPN dla aplikacji na urządzeniach z systemem iOS w usłudze Microsoft Intune na platformie Azure | Microsoft Docs
description: W tym artykule opisano wymagania wstępne, tworzenie grupy dla użytkowników wirtualnej sieci prywatnej (sieci VPN), dodawanie profilu certyfikatu SCEP, konfigurowanie profilu sieci VPN dla aplikacji oraz przypisywanie aplikacji do profilu sieci VPN w usłudze Microsoft Intune na urządzeniach z systemem iOS. Zawiera on także instrukcje weryfikowania połączenia z siecią VPN na urządzeniu.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/04/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: D9958CBF-34BF-41C2-A86C-28F832F87C94
ms.reviewer: tycast
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 36ba25941950e403d1ab1861efac8db7dd3daede
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55841712"
---
# <a name="set-up-per-app-virtual-private-network-vpn-for-ios-devices-in-intune"></a>Konfigurowanie wirtualnej sieci prywatnej dla aplikacji na urządzeniach z systemem iOS w usłudze Intune

Usługa Microsoft Intune umożliwia utworzenie sieci wirtualnej przypisanej do aplikacji i korzystanie z niej. Ta funkcja jest nazywana „siecią VPN dla aplikacji”. Należy wybrać aplikacje zarządzane, które mogą używać sieci VPN na urządzeniach zarządzanych przez usługę Intune. Podczas korzystania z sieci VPN dla aplikacji użytkownicy końcowi automatycznie łączą się przez sieć VPN i uzyskują dostęp do zasobów organizacji, takich jak dokumenty.

Ta funkcja ma zastosowanie do:

- System iOS 9 lub nowszy

Przejrzyj dokumentację dostawcy sieci VPN, aby sprawdzić, czy używana sieć VPN obsługuje sieć VPN dla aplikacji.

W tym artykule przedstawiono sposób tworzenia profilu sieci VPN dla aplikacji, a następnie przypisywania tego profilu do aplikacji. Te kroki umożliwiają utworzenie bezproblemowego środowiska sieci VPN dla aplikacji na potrzeby użytkowników końcowych. W przypadku większości sieci VPN obsługujących sieć VPN dla aplikacji użytkownik otwiera aplikację i automatycznie nawiązuje połączenie z siecią VPN.

Niektóre sieci VPN umożliwiają uwierzytelnianie za pomocą nazwy użytkownika i hasła w przypadku sieci VPN dla aplikacji. To znaczy użytkownicy muszą podać nazwę użytkownika i hasło, aby nawiązać połączenie z siecią VPN.

## <a name="per-app-vpn-with-zscaler"></a>Sieć VPN dla aplikacji z rozwiązaniem Zscaler

Usługa Zscaler Private Access (ZPA) integruje się z usługą Azure Active Directory (Azure AD) na potrzeby uwierzytelniania. Korzystając z usługi ZPA, nie potrzebujesz [certyfikatu zaufanego](#create-a-trusted-certificate-profile) ani profilów [certyfikatu SCEP lub PKCS](#create-a-scep-or-pkcs-certificate-profile) (opisanych w tym artykule). Jeśli masz profil sieci VPN dla aplikacji skonfigurowany pod kątem rozwiązania Zscaler, otwarcie jednej ze skojarzonych aplikacji nie spowoduje automatycznego nawiązania połączenia z usługą ZPA. Zamiast tego użytkownik musi najpierw zalogować się do aplikacji Zscaler. Dostęp będzie wtedy ograniczony do skojarzonych aplikacji.

## <a name="prerequisites-for-per-app-vpn"></a>Wymagania wstępne dotyczące sieci VPN dla aplikacji

> [!IMPORTANT]
> Dostawca połączeń VPN może mieć inne wymagania dotyczące sieci VPN dla aplikacji, na przykład dotyczące sprzętu lub licencjonowania. Należy zapoznać się z dokumentacją dostawcy połączeń VPN i spełnić określone w niej wymagania wstępne przed skonfigurowaniem połączenia VPN dla aplikacji w usłudze Intune.

Aby potwierdzić swoją tożsamość, serwer sieci VPN przedstawia certyfikat, który bez monitu musi zostać zaakceptowany przez urządzenie. W celu potwierdzenia automatycznego zatwierdzania certyfikatu utwórz profil zaufanego certyfikatu, który zawiera certyfikat główny serwera sieci VPN wystawiony przez urząd certyfikacji. 

#### <a name="export-the-certificate-and-add-the-ca"></a>Eksportowanie certyfikatu i dodawanie urzędu certyfikacji

1. Otwórz konsolę administracyjną na serwerze sieci VPN.
2. Potwierdź, że serwer sieci VPN korzysta z uwierzytelniania opartego na certyfikatach. 
3. Wyeksportuj plik zaufanego certyfikatu głównego. Jego rozszerzenie to cer, a dodaje się go podczas tworzenia profilu zaufanego certyfikatu.
4. Dodaj nazwę urzędu certyfikacji, który wystawił certyfikat uwierzytelniania serwera sieci VPN.

    Jeśli urząd certyfikacji przedstawiony przez urządzenie pasuje do urzędu certyfikacji na liście zaufanych urzędów certyfikacji na serwerze sieci VPN, serwer sieci VPN pomyślnie uwierzytelni urządzenie.

## <a name="create-a-group-for-your-vpn-users"></a>Tworzenie grupy dla użytkowników sieci VPN

Utwórz lub wybierz istniejącą grupę w usłudze Azure Active Directory (Azure AD) dla użytkowników lub urządzeń, które używają sieci VPN dla aplikacji. Aby utworzyć nową grupę, zobacz [Dodawanie grup w celu zorganizowania użytkowników i urządzeń](groups-add.md).

## <a name="create-a-trusted-certificate-profile"></a>Tworzenie profilu zaufanego certyfikatu

Zaimportuj certyfikat główny serwera sieci VPN wystawiony przez urząd certyfikacji do profilu utworzonego w usłudze Intune. Profil zaufanego certyfikatu powoduje, że urządzenia z systemem iOS automatycznie zaufają urzędowi certyfikacji przedstawianemu przez serwer sieci VPN.

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi**, wpisz nazwę usługi **Intune** w filtrze, a następnie wybierz pozycję **Intune**.
2. Wybierz pozycję **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Wprowadź następujące właściwości:
    - **Nazwa**
    - **Opis**
    - **Platforma**: Wybierz pozycję **iOS**.
    - **Typ profilu**: Wybierz pozycję **Zaufany certyfikat**.
4. Wybierz ikonę folderu i przejdź do certyfikatu sieci VPN (pliku cer), który został wyeksportowany z konsoli administracyjnej sieci VPN. 
5. Wybierz pozycje **OK** > **Utwórz**.

    ![Tworzenie profilu zaufanego certyfikatu dla urządzeń z systemem iOS w usłudze Microsoft Intune](./media/vpn-per-app-create-trusted-cert.png)

## <a name="create-a-scep-or-pkcs-certificate-profile"></a>Tworzenie profilu certyfikatu SCEP lub PKCS

Profil zaufanego certyfikatu głównego umożliwia urządzeniu automatyczne zaufanie serwerowi sieci VPN. Certyfikat SCEP lub PKCS dostarcza poświadczenia od klienta sieci VPN systemu iOS do serwera sieci VPN. Dzięki certyfikatowi urządzenie może przeprowadzić dyskretne uwierzytelnianie bez monitowania o nazwę użytkownika i hasło. 

Aby skonfigurować i przypisać certyfikat uwierzytelniania klienta, zobacz jeden z następujących artykułów:

- [Konfigurowanie certyfikatów protokołu SCEP i zarządzanie nimi za pomocą usługi Intune](certificates-scep-configure.md)
- [Konfigurowanie certyfikatów PKCS i zarządzanie nimi za pomocą usługi Intune](certficates-pfx-configure.md)

Pamiętaj o skonfigurowaniu certyfikatu dla uwierzytelniania klienta. Możesz ustawić go bezpośrednio w profilach certyfikatów SCEP (**Rozszerzone użycie klucza** lista > **Uwierzytelnianie klienta**). W przypadku standardu PKCS należy ustawić uwierzytelnianie klienta w szablonie certyfikatu w urzędzie certyfikacji.

![Utwórz profil certyfikatu SCEP w usłudze Microsoft Intune, w tym format nazwy podmiotu, użycie klucza, rozszerzone użycia klucza i inne](./media/vpn-per-app-create-scep-cert.png)

## <a name="create-a-per-app-vpn-profile"></a>Tworzenie profilu sieci VPN dla aplikacji

Profil sieci VPN obejmuje certyfikat SCEP lub PKCS zawierający poświadczenia klienta, informacje o połączeniu z siecią VPN i flagę sieci VPN dla aplikacji, aby umożliwić używanie funkcji sieci VPN dla aplikacji przez aplikację systemu iOS.

1. W usłudze **Intune** wybierz kolejno pozycje **Konfiguracja urządzenia** > **Profile** > **Utwórz profil**. 
2. Wprowadź następujące właściwości: 
    - **Nazwa**
    - **Opis**
    - **Platforma**: Wybierz pozycję **iOS**.
    - **Typ profilu**: Wybierz pozycję **Sieć VPN**.
3. W polu **Typ połączenia** wybierz aplikację klienta sieci VPN.
4. Wybierz element **Podstawowa sieć VPN**. Artykuł [Ustawienia sieci VPN dla systemu iOS](vpn-settings-ios.md) zawiera listę wszystkich ustawień wraz z opisami. Jeśli korzystasz z sieci VPN dla aplikacji, upewnij się, że skonfigurowano następujące ustawienia w podany sposób: 
    
    - **Metoda uwierzytelniania**: wybierz opcję **Certyfikaty**. 
    - **Certyfikat uwierzytelniania**: wybierz istniejący certyfikat SCEP lub PKCS > **OK**.      
    - **Podziel tunelowanie**: wybierz opcję **Wyłącz**, aby wymusić kierowanie całego ruchu przez tunel sieci VPN, gdy połączenie sieci VPN jest aktywne. 

      ![W profilu sieci VPN dla aplikacji podaj połączenie, adres IP lub nazwę FQDN, metodę uwierzytelniania i tunelowanie podzielone w usłudze Microsoft Intune](./media/vpn-per-app-create-vpn-profile.png)

    Aby uzyskać informacje na temat innych ustawień, zobacz [Ustawienia sieci VPN dla systemu iOS](vpn-settings-ios.md).

5. Wybierz pozycje **Automatyczne połączenie VPN** > **Typ automatycznego połączenia VPN** > **Sieć VPN dla aplikacji**

    ![W usłudze Intune ustaw dla pozycji Automatyczne połączenie VPN wartość Sieć VPN dla aplikacji na urządzeniach z systemem iOS](./media/vpn-per-app-automatic.png)

6. Wybierz pozycje **OK** > **OK** > **Utwórz**.

## <a name="associate-an-app-with-the-vpn-profile"></a>Kojarzenie aplikacji z profilem sieci VPN

Po dodaniu profilu sieci VPN skojarz aplikację i grupę usługi Azure AD z profilem.

1. W usłudze **Intune** wybierz pozycję **Aplikacje klienckie** > **Aplikacje**.
2. Wybierz aplikację z listy > **Przypisania** > **Dodaj grupę**.
3. W pozycji **Typ przypisania** wybierz opcję **Wymagane** lub **Dostępne dla zarejestrowanych urządzeń**.
4. Wybierz pozycję **Uwzględnione grupy** > **Wybierz grupy do uwzględnienia** > Wybierz grupę [utworzoną](#create-a-group-for-your-vpn-users) w tym artykule > **Wybierz**.
5. W polu **Sieci VPN** wybierz profil sieci VPN dla aplikacji [utworzony](#create-a-per-app-vpn-profile) w tym artykule.

    ![Przypisywanie aplikacji do profilu sieci VPN dla aplikacji w usłudze Microsoft Intune](./media/vpn-per-app-app-to-vpn.png)

6. Wybierz pozycje **OK** > **Zapisz**.

Skojarzenie między aplikacją i profilem zostanie usunięte podczas następnego zaewidencjonowania urządzenia, jeśli zostaną spełnione wszystkie następujące warunki:

- Aplikacja została oznaczona jako docelowa przy użyciu intencji wymaganej instalacji.
- Zarówno profil, jak i aplikacja mają tę samą grupę docelową.
- Konfiguracja sieci VPN dla aplikacji jest usuwana z przypisania aplikacji.

Skojarzenie między aplikacją i profilem będzie nadal istnieć do momentu, gdy użytkownik zażąda ponownej instalacji z aplikacji Portal firmy, jeśli wszystkie następujące warunki zostaną spełnione:

- Aplikacja została oznaczona jako docelowa przy użyciu intencji dostępnej instalacji.
- Zarówno profil, jak i aplikacja mają tę samą grupę docelową.
- Użytkownik zażądał instalacji aplikacji z aplikacji Portal firmy, w wyniku czego aplikacja i profil są instalowane na urządzeniu.
- Konfiguracja sieci VPN dla aplikacji została usunięta lub zmieniona z poziomu przypisania aplikacji.

## <a name="verify-the-connection-on-the-ios-device"></a>Sprawdzanie połączenia na urządzeniu z systemem iOS

Za pomocą skonfigurowanej i skojarzonej z aplikacją sieci VPN dla aplikacji sprawdź, czy połączenie działa z urządzenia.

### <a name="before-you-attempt-to-connect"></a>Przed podjęciem próby nawiązania połączenia

 - Upewnij się, że wszystkie wyżej wymienione zasady zostały wdrożone do tej samej grupy. W przeciwnym przypadku środowisko sieci VPN dla aplikacji nie będzie działać.
 - Jeśli używasz aplikacji sieci VPN połączenia Pulse Secure lub niestandardowej aplikacji klienckiej sieci VPN, możesz użyć warstwy aplikacji lub tunelowania w warstwie pakietów. Ustaw opcję **Typ dostawcy** na wartość **app-proxy** w celu tunelowania w warstwie aplikacji lub **packet-tunnel** w celu tunelowania w warstwie pakietów. Sprawdź dokumentację dostawcy sieci VPN, aby upewnić się, że używasz poprawnej wartości.

### <a name="connect-using-the-per-app-vpn"></a>Nawiązywanie połączenia przy użyciu sieci VPN dla aplikacji

Sprawdź środowisko bezobsługowe, nawiązując połączenie bez konieczności wyboru sieci VPN lub wprowadzania swoich poświadczeń. Środowisko bezobsługowe oznacza, że:

 - Urządzenie nie pyta o zaufanie serwerowi sieci VPN. To znaczy, że okno dialogowe **Zaufanie dynamiczne** nie jest wyświetlane.
 - Użytkownik nie musi podawać poświadczeń.
 - Urządzenie użytkownika łączy się z siecią VPN, gdy użytkownik otworzy jedną ze skojarzonych aplikacji.

<!-- ## Troubleshooting the per-app VPN

The user experiences the feature by silently connecting to the VPN. This experience, however, can provide little information for troubleshooting. You can review the event logs crated by the iOS device.

`Note -- use the Apple Configurator as the supported tool. Only runs on a mac.'

To review event logs:

1. Connect your iOS device to a PC
2. Open the **iPhone Configuration Utility** (IPCU). If you do not have a copy, you can install it from [CompatCenter](http://www.microsoft.com/en-us/windows/compatibility/CompatCenter/ProductDetailsViewer?Name=iPhone%20Configuration%20Utility&vendor=Apple&Locale=1033%2C2057%2C3081%2C4105%2C16393&ModelOrVersion=3&BreadCrumbPath=iphone%20configuration%20utility&LastSearchTerm=iphone%2Bconfiguration%2Butility&Type=Software&tempOsid=Windows%208.1)
3. Review the logs. -->

## <a name="next-steps"></a>Następne kroki

- Aby przejrzeć ustawienia systemu iOS, zobacz temat [Ustawienia sieci VPN dla urządzeń z systemem iOS w usłudze Microsoft Intune](vpn-settings-ios.md).
- Aby dowiedzieć się więcej na temat ustawień sieci VPN i usługi Intune, zobacz temat [Konfigurowanie ustawień sieci VPN w usłudze Microsoft Intune](vpn-settings-configure.md).
