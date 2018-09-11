---
title: Konfigurowanie sieci VPN dla aplikacji na urządzeniach z systemem iOS w usłudze Microsoft Intune na platformie Azure | Microsoft Docs
description: W tym artykule opisano wymagania wstępne, tworzenie grupy dla użytkowników wirtualnej sieci prywatnej (sieci VPN), dodawanie profilu certyfikatu SCEP, konfigurowanie profilu sieci VPN dla aplikacji oraz przypisywanie aplikacji do profilu sieci VPN w usłudze Microsoft Intune na urządzeniach z systemem iOS. Zawiera on także instrukcje weryfikowania połączenia z siecią VPN na urządzeniu.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: D9958CBF-34BF-41C2-A86C-28F832F87C94
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7cf005b225dd11ca6b95dbed0a82330544575f92
ms.sourcegitcommit: 2d1e89fa5fa721e79648e41fde147a035e7b047d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/31/2018
ms.locfileid: "43347478"
---
# <a name="set-up-per-app-virtual-private-network-vpn-in-intune-for-ios-devices"></a>Konfigurowanie wirtualnej sieci prywatnej (sieci VPN) dla aplikacji na urządzeniach z systemem iOS w usłudze Intune

Możesz określić aplikacje zarządzane, które mogą używać wirtualnej sieci prywatnej (VPN) na urządzeniach z systemem iOS zarządzanych przez usługę Intune. Po utworzeniu sieci VPN dla aplikacji w usłudze Intune użytkownik końcowy automatycznie nawiązuje połączenie za pośrednictwem sieci VPN przy uzyskiwaniu dostępu do dokumentów firmowych.

Sieć VPN dla aplikacji jest obecnie dostępna dla następujących dostawców:

 - Check Point Remote Access VPN
 - Cisco AnyConnect
 - Citrix
 - F5
 - Pulse Connect Secure
 - SonicWall
 - Palo Alto Networks GlobalProtect
 - Zscaler

## <a name="prerequisites-for-per-app-vpn"></a>Wymagania wstępne dotyczące sieci VPN dla aplikacji

> [!IMPORTANT]
> Dostawca połączeń VPN może mieć inne określone wymagania dotyczące sieci VPN dla danej aplikacji, na przykład dotyczące sprzętu lub licencjonowania. Należy zapoznać się z dokumentacją dostawcy połączeń VPN i spełnić określone w niej wymagania wstępne przed skonfigurowaniem połączenia VPN dla aplikacji w usłudze Intune.

Aby potwierdzić swoją tożsamość, serwer sieci VPN przedstawia certyfikat, który bez monitu musi zostać zaakceptowany przez urządzenie. W celu zapewnienia automatycznego zatwierdzania certyfikatu utwórz profil zaufanego certyfikatu, który zawiera certyfikat główny serwera sieci VPN wystawiony przez urząd certyfikacji. 

Wyeksportuj certyfikat i dodaj urząd certyfikacji.

1. Otwórz konsolę administracyjną na serwerze sieci VPN.
2. Upewnij się, że serwer sieci VPN korzysta z uwierzytelniania opartego na certyfikatach. 
3. Wyeksportuj plik zaufanego certyfikatu głównego. Jego rozszerzenie to cer, a dodaje się go podczas tworzenia profilu zaufanego certyfikatu.
4. Dodaj nazwę urzędu certyfikacji, który wystawił certyfikat uwierzytelniania serwera sieci VPN.
    Jeśli urząd certyfikacji przedstawiony przez urządzenie pasuje do jednego z urzędów certyfikacji na liście zaufanych urzędów certyfikacji na serwerze sieci VPN, serwer sieci VPN pomyślnie uwierzytelnia urządzenie.

## <a name="create-a-group-for-your-vpn-users"></a>Tworzenie grupy dla użytkowników sieci VPN

Utwórz lub wybierz istniejącą grupę w usłudze Azure Active Directory (Azure AD), aby zawierała członków, którzy mają dostęp do sieci VPN dla aplikacji.

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz opcję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
2. Wybierz element **Grupy**, a następnie kliknij polecenie **Nowa grupa**.
3. Wybierz element **Typ grupy** dla grupy. 
3. Uzupełnij pole **Nazwa grupy** dla grupy. 
4. Uzupełnij pole **Opis grupy** dla grupy. 
5. Dla elementu **Typ członkostwa** wybierz pozycję **Przypisany**.
7. W okienku **Członkowie** wyszukaj użytkowników sieci VPN według nazwy lub adresu e-mail.
8. Zaznacz każdego użytkownika, a następnie kliknij przycisk **Wybierz**.
9. Kliknij przycisk **Utwórz**.

## <a name="create-a-trusted-certificate-profile"></a>Tworzenie profilu zaufanego certyfikatu

Zaimportuj certyfikat główny serwera sieci VPN wystawiony przez urząd certyfikacji do profilu utworzonego w usłudze Intune. Profil zaufanego certyfikatu powoduje, że urządzenia z systemem iOS automatycznie zaufają urzędowi certyfikacji przedstawianemu przez serwer sieci VPN.

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz opcję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
2. Wybierz element **Konfiguracja urządzenia**, a następnie kliknij pozycję **Profile**.
3. Kliknij pozycję **Utwórz profil**. W obszarze **Utwórz profil**:
    1. Uzupełnij pole **Nazwa**.
    2. Uzupełnij pole **Opis**.
    3. Dla elementu **Platforma** wybierz pozycję **iOS**.
    4. Dla elementu **Typ profilu** wybierz pozycję **Zaufany certyfikat**.
4. Kliknij ikonę folderu i przejdź do certyfikatu sieci VPN (plik cer), który został wyeksportowany z konsoli administracyjnej sieci VPN. Kliknij przycisk **OK**.
5. Kliknij przycisk **Utwórz**.

    ![Tworzenie profilu zaufanego certyfikatu](./media/vpn-per-app-create-trusted-cert.png)

## <a name="create-a-scep-certificate-profile"></a>Tworzenie profilu certyfikatu protokołu SCEP

Profil zaufanego certyfikatu głównego umożliwia urządzeniom z systemem iOS automatyczne zaufanie serwerowi sieci VPN. Certyfikat protokołu SCEP dostarcza poświadczenia od klienta sieci VPN systemu iOS do serwera sieci VPN. Dzięki certyfikatowi urządzenie może przeprowadzić dyskretne uwierzytelnienie bez monitowania użytkownika urządzenia z systemem iOS o nazwę użytkownika i hasło. 

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz opcję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
2. Wybierz element **Konfiguracja urządzenia**, a następnie kliknij pozycję **Profile**.
3. Kliknij pozycję **Utwórz profil**. W obszarze **Utwórz profil**:
    1. Uzupełnij pole **Nazwa**.
    2. Uzupełnij pole **Opis**.
    3. Dla elementu **Platforma** wybierz pozycję **iOS**.
    4. Dla elementu **Typ profilu** wybierz pozycję **Certyfikat protokołu SCEP**.
4. Dla elementu **Okres ważności certyfikatu** wybierz pozycję **Lata** i wprowadź wartość `2`.
5. Dla elementu **Format nazwy podmiotu** wybierz pozycję **Nazwa pospolita**.
6. Dla elementu **Alternatywna nazwa podmiotu** wybierz pozycję **Główna nazwa użytkownika (UPN)**.
7. Dla elementu **Użycie klucza** wybierz pozycje **Podpis cyfrowy** i **Szyfrowanie klucza**.
8. Dla elementu **Rozmiar klucza (bity)** wybierz pozycję **2048**.
9. Kliknij pozycję Certyfikat główny, a następnie wybierz certyfikat protokołu SCEP. Kliknij przycisk **OK**.
10. Dla elementu **Rozszerzone użycie klucza** wprowadź wartość `Client Authentication` w polu **Nazwa**.
11. Wprowadź wartość `1.3.6.1.5.5.7.3.2` w polu **Identyfikator obiektu**.
12. Kliknij pozycję **Dodaj**.
13. Wprowadź ***adres URL serwera*** i kliknij przycisk **Dodaj**.
14. Kliknij przycisk **OK**.
15. Kliknij przycisk **Utwórz**.

    ![Tworzenie profilu certyfikatu protokołu SCEP](./media/vpn-per-app-create-scep-cert.png)

## <a name="create-a-per-app-vpn-profile"></a>Tworzenie profilu sieci VPN dla aplikacji

Profil sieci VPN obejmuje certyfikat protokołu SCEP zawierający poświadczenia klienta, informacje o połączeniu z siecią VPN i flagę sieci VPN dla aplikacji w celu umożliwienia używania funkcji sieci VPN dla aplikacji przez aplikację systemu iOS.

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz opcję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
2. Wybierz element **Konfiguracja urządzenia**, a następnie kliknij pozycję **Profile**.
3. Kliknij pozycję **Utwórz profil**. W obszarze **Utwórz profil**:
    1. Uzupełnij pole **Nazwa**.
    2. Uzupełnij pole **Opis**.
    3. Dla elementu **Platforma** wybierz pozycję **iOS**.
    4. Dla elementu **Typ profilu** wybierz pozycję **Sieć VPN**.
4. Wybierz element **Podstawowa sieć VPN**. W obszarze **Podstawowa sieć VPN**:
    1. Uzupełnij pole **Nazwa połączenia**.
    2. Uzupełnij pole **Adres IP lub nazwa FQDN**.
    3. Dla elementu **Metoda uwierzytelniania** wybierz pozycję **Certyfikaty**.
    4. W obszarze **Certyfikat uwierzytelniania** wybierz certyfikat protokołu SCEP i kliknij przycisk **OK**.
    5. Dla elementu **Typ połączenia** wybierz swoją sieć VPN.
    6. W razie potrzeby skonfiguruj atrybuty dla sieci VPN.
    7. Wybierz **wyłączenie tunelowania podzielonego**.
5. Kliknij pozycję **Automatyczna sieć VPN**. W obszarze **Automatyczna sieć VPN**:
    1. Dla elementu **Typ automatycznej sieci VPN** wybierz pozycję **Sieć VPN dla aplikacji**.
    2. Wprowadź adres URL sieci VPN i kliknij przycisk **Dodaj**.
    3. Kliknij przycisk **OK**.
6. Kliknij przycisk **OK**.
7. Kliknij przycisk **Utwórz**.

    ![Tworzenie profilu sieci VPN dla aplikacji](./media/vpn-per-app-create-vpn-profile.png)


## <a name="associate-an-app-with-the-vpn-profile"></a>Kojarzenie aplikacji z profilem sieci VPN

Po dodaniu profilu sieci VPN skojarz aplikację i grupę usługi Azure AD z profilem.

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz opcję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz pozycję **Aplikacje klienckie**.
4. Kliknij pozycję **Aplikacje**.
5. Wybierz aplikację z listy aplikacji.
6. Kliknij pozycję **Przypisania**.
7. Kliknij pozycję **Dodawanie grupy**.
8. Wybierz wartość **Wymagane** dla elementu **Typ przydziału** w okienku **Dodaj grupę**.
9. Wybierz wcześniej zdefiniowaną grupę i wybierz pozycję **Ustaw tę aplikację jako wymaganą**.
10. Wybierz definicję sieci VPN dla elementu **Sieć VPN**.
 
    > [!NOTE]  
    > Czasami pobranie wartości zajmuje definicji sieci VPN kilka chwil. Poczekaj od 3 do 5 minut, zanim klikniesz polecenie **Zapisz**.

11. Kliknij przycisk **OK**, a następnie pozycję **Zapisz**.

    ![Kojarzenie aplikacji z siecią VPN](./media/vpn-per-app-app-to-vpn.png)

Skojarzenie między aplikacją i profilem zostanie usunięte podczas następnego zaewidencjonowania urządzenia, jeśli zostaną spełnione następujące warunki:
- Aplikacja została oznaczona jako docelowa przy użyciu intencji wymaganej instalacji.
- Zarówno profil, jak i aplikacja mają tę samą grupę docelową.
- Konfiguracja sieci VPN dla aplikacji jest usuwana z przypisania aplikacji.

Skojarzenie między aplikacją i profilem będzie nadal istnieć do momentu, gdy użytkownik końcowy zażąda ponownej instalacji z portalu firmy, jeśli następujące warunki zostaną spełnione:
- Aplikacja została oznaczona jako docelowa przy użyciu intencji dostępnej instalacji.
- Zarówno profil, jak i aplikacja mają tę samą grupę docelową.
- Użytkownik zażądał instalacji aplikacji z portalu firmy, w wyniku czego aplikacja i profil są instalowane na urządzeniu.
- Konfiguracja sieci VPN dla aplikacji jest usuwana z przypisania aplikacji.

## <a name="verify-the-connection-on-the-ios-device"></a>Sprawdzanie połączenia na urządzeniu z systemem iOS

Za pomocą skonfigurowanej i skojarzonej z aplikacją sieci VPN dla aplikacji sprawdź, czy połączenie działa z urządzenia.

### <a name="before-you-attempt-to-connect"></a>Przed podjęciem próby nawiązania połączenia

 - Upewnij się, że używasz systemu iOS 9 lub nowszego.
 - Upewnij się, że *wszystkie* wyżej wymienione zasady zostały wdrożone do tej samej grupy użytkowników. Nieprzestrzeganie tego kroku spowoduje, że środowisko sieci VPN dla aplikacji na pewno zostanie przerwane.  
 - Upewnij się, że masz zainstalowaną obsługiwaną aplikację sieci VPN innych firm. Obsługiwane są następujące aplikacje sieci VPN:
    - Check Point Capsule Connect
    - Cisco AnyConnect
    - Citrix VPN
    - F5 Access
    - Pulse Secure
    - SonicWall Mobile Connect
    - Zscaler App

    > [!NOTE]
    > Jeśli używasz aplikacji sieci VPN połączenia Pulse Secure, możesz użyć warstwy aplikacji lub tunelowania warstwy pakietu. Ustaw wartość **Typ dostawcy** na **app-proxy** dla tunelowania warstwy aplikacji lub na **packet-tunnel** dla tunelowania warstwy pakietu.

### <a name="connect-using-the-per-app-vpn"></a>Nawiązywanie połączenia przy użyciu sieci VPN dla aplikacji

Sprawdź środowisko bezobsługowe, nawiązując połączenie bez konieczności wyboru sieci VPN lub wprowadzania swoich poświadczeń. Środowisko bezobsługowe oznacza, że:

 - Urządzenie nie pyta o zaufanie serwerowi sieci VPN. To znaczy, że wyświetlane jest dynamiczne okno dialogowe **zaufania**.
 - Nie musisz wprowadzać poświadczeń.
 - Nawiązano połączenie z siecią VPN po naciśnięciu przycisku Połącz.

Sprawdź połączenie na urządzeniu z systemem iOS.

1. Wybierz aplikację sieci VPN.
2. Naciśnij polecenie **Połącz**.  
Sieć VPN pomyślnie nawiązuje połączenie bez żadnych dodatkowych monitów.

<!-- ## Troubleshooting the per-app VPN

The user experiences the feature by silently connecting to the VPN. This experience, however, can provide little information for troubleshooting. You can review the event logs crated by the iOS device.

`Note -- use the Apple Configurator as the supported tool. Only runs on a mac.'

To review event logs:

1. Connect your iOS device to a PC
2. Open the **iPhone Configuration Utility** (IPCU). If you do not have a copy, you can install it from [CompatCenter](http://www.microsoft.com/en-us/windows/compatibility/CompatCenter/ProductDetailsViewer?Name=iPhone%20Configuration%20Utility&vendor=Apple&Locale=1033%2C2057%2C3081%2C4105%2C16393&ModelOrVersion=3&BreadCrumbPath=iphone%20configuration%20utility&LastSearchTerm=iphone%2Bconfiguration%2Butility&Type=Software&tempOsid=Windows%208.1)
3. Review the logs. -->

## <a name="next-steps"></a>Następne kroki

- Aby przejrzeć ustawienia systemu iOS, zobacz temat [Ustawienia sieci VPN dla urządzeń z systemem iOS w usłudze Microsoft Intune](vpn-settings-ios.md).
-  Aby dowiedzieć się więcej na temat ustawień sieci VPN i usługi Intune, zobacz temat [Jak skonfigurować ustawienia sieci VPN w usłudze Microsoft Intune](vpn-settings-configure.md).
