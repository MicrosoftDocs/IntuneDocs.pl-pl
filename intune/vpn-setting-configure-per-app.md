---
title: "Konfigurowanie sieci VPN dla aplikacji w usłudze Microsoft Intune na urządzeniach z systemem iOS"
titleSuffix: Intune on Azure
description: "Określ aplikacje zarządzane, które mogą używać sieci VPN na urządzeniach z systemem iOS zarządzanych przez usługę Intune."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/5/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: D9958CBF-34BF-41C2-A86C-28F832F87C94
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6f7e53f9a440d945d834c17b9db85ed5f6e42229
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/25/2018
---
# <a name="set-up-per-app-vpn-in-microsoft-intune-for-ios-devices"></a>Konfigurowanie sieci VPN dla aplikacji w usłudze Microsoft Intune na urządzeniach z systemem iOS

Możesz określić aplikacje zarządzane, które mogą używać wirtualnej sieci prywatnej (VPN) na urządzeniach z systemem iOS zarządzanych przez usługę Intune. Po określeniu sieci VPN dla aplikacji w usłudze Intune użytkownik końcowy automatycznie nawiązuje połączenie za pośrednictwem sieci VPN przy uzyskiwaniu dostępu do dokumentów firmowych.

## <a name="prerequisites-for-the-per-app-vpn"></a>Wymagania wstępne dotyczące sieci VPN dla aplikacji

Aby potwierdzić swoją tożsamość, serwer sieci VPN przedstawia certyfikat, który bez monitu musi zostać zaakceptowany przez urządzenie. W celu zapewnienia automatycznego zatwierdzania certyfikatu utwórz profil zaufanego certyfikatu, który zawiera certyfikat główny serwera sieci VPN wystawiony przez urząd certyfikacji. 

Wyeksportuj certyfikat i dodaj urząd certyfikacji.

1. Otwórz konsolę administracyjną na serwerze sieci VPN.
2. Upewnij się, że serwer sieci VPN korzysta z uwierzytelniania opartego na certyfikatach. 
3. Wyeksportuj plik zaufanego certyfikatu głównego. Jego rozszerzenie to cer, a dodaje się go podczas tworzenia profilu zaufanego certyfikatu.
4. Dodaj nazwę urzędu certyfikacji, który wystawił certyfikat uwierzytelniania serwera sieci VPN.
    Jeśli urząd certyfikacji przedstawiony przez urządzenie pasuje do jednego z urzędów certyfikacji na liście zaufanych urzędów certyfikacji na serwerze sieci VPN, serwer sieci VPN pomyślnie uwierzytelnia urządzenie.

## <a name="create-a--group-for-your-vpn-users"></a>Tworzenie grupy dla użytkowników sieci VPN

Utwórz lub wybierz istniejącą grupę w usłudze Azure Active Directory (Azure AD), aby zawierała członków, którzy mają dostęp do sieci VPN dla aplikacji.

1. Otwórz witrynę Azure Portal. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
2. Wybierz element **Grupy**, a następnie kliknij polecenie **Nowa grupa**.
3. Uzupełnij pole **Nazwa** grupy. 
4. Uzupełnij pole **Opis** grupy. 
5. Dla elementu **Typ członkostwa** wybierz pozycję **Przypisany**.
6. Opcję **Włącz funkcje pakietu Office** ustaw na wartość **Nie**.
7. W bloku **Członkowie** wyszukaj użytkowników sieci VPN według nazwy lub adresu e-mail.
8. Zaznacz każdego użytkownika, a następnie kliknij przycisk **Wybierz**.
9. Kliknij przycisk **Utwórz**.

## <a name="create-a-trusted-certificate-profile"></a>Tworzenie profilu zaufanego certyfikatu

Zaimportuj certyfikat główny serwera sieci VPN wystawiony przez urząd certyfikacji do profilu utworzonego w usłudze Intune. Profil zaufanego certyfikatu powoduje, że urządzenia z systemem iOS automatycznie zaufają urzędowi certyfikacji przedstawianemu przez serwer sieci VPN.

1. Otwórz witrynę Azure Portal. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
2. Wybierz element **Konfiguracja urządzenia**, a następnie kliknij pozycję **Profile**.
3. Kliknij polecenie **+ Utwórz profil**. W obszarze **Utwórz profil**:
    1. Uzupełnij pole **Nazwa**.
    2. Uzupełnij pole **Opis**.
    3. Dla elementu **Platforma** wybierz pozycję **iOS**.
    4. Dla elementu **Typ profilu** wybierz pozycję **Zaufany certyfikat**.
4. Kliknij ikonę folderu i przejdź do certyfikatu sieci VPN (plik cer), który został wyeksportowany z konsoli administracyjnej sieci VPN. Kliknij przycisk OK.
5. Kliknij przycisk **Utwórz**.

    ![Tworzenie profilu zaufanego certyfikatu](media\vpn-per-app-create-trusted-cert.png)

## <a name="create-a-scep-certificate-profile"></a>Tworzenie profilu certyfikatu protokołu SCEP

Profil zaufanego certyfikatu głównego umożliwia urządzeniom z systemem iOS automatyczne zaufanie serwerowi sieci VPN. Certyfikat protokołu SCEP dostarcza poświadczenia od klienta sieci VPN systemu iOS do serwera sieci VPN. Dzięki certyfikatowi urządzenie może przeprowadzić dyskretne uwierzytelnienie bez monitowania użytkownika urządzenia z systemem iOS o nazwę użytkownika i hasło. 

1. Otwórz witrynę Azure Portal. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**. 
2. Wybierz element **Konfiguracja urządzenia**, a następnie kliknij pozycję **Profile**.
3. Kliknij polecenie **+ Utwórz profil**. W obszarze **Utwórz profil**:
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

    ![Tworzenie profilu certyfikatu protokołu SCEP](media\vpn-per-app-create-scep-cert.png)

## <a name="create-a-per-app-vpn-profile"></a>Tworzenie profilu sieci VPN dla aplikacji

Profil sieci VPN obejmuje certyfikat protokołu SCEP zawierający poświadczenia klienta, informacje o połączeniu z siecią VPN i flagę sieci VPN dla aplikacji w celu umożliwienia używania funkcji sieci VPN dla aplikacji przez aplikację systemu iOS.

1. Otwórz witrynę Azure Portal. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
2. Wybierz element **Konfiguracja urządzenia**, a następnie kliknij pozycję **Profile**.
3. Kliknij polecenie **+ Utwórz profil**. W obszarze **Utwórz profil**:
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

    ![Tworzenie profilu sieci VPN dla aplikacji](media\vpn-per-app-create-vpn-profile.png)


## <a name="associate-an-app-with-the-vpn-profile"></a>Kojarzenie aplikacji z profilem sieci VPN

Po dodaniu profilu sieci VPN skojarz aplikację i grupę usługi Azure AD z profilem.

1. Otwórz witrynę Azure Portal. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
2. Wybierz pozycję **Mobile Apps**.
3. Kliknij pozycję **Aplikacje**.
4. Wybierz aplikację z listy aplikacji.
5. Kliknij pozycję **Przypisania**.
6. Kliknij polecenie **Wybierz grupy** i wybierz wcześniej zdefiniowaną grupę. Kliknij pozycję **Wybierz**.
7. W bloku **Przypisania** dla elementu **Typ** wybierz wartość **Wymagane**.
8. Wybierz definicję sieci VPN dla elementu **Sieci VPN**.
 
    > [!NOTE]  
    > Czasami pobranie wartości zajmuje definicji sieci VPN kilka chwil. Poczekaj od 3 do 5 minut, zanim klikniesz polecenie **Zapisz**.

9. Kliknij polecenie **Zapisz**.

    ![Kojarzenie aplikacji z siecią VPN](media\vpn-per-app-app-to-vpn.png)

## <a name="verify-the-connection-on-the-ios-device"></a>Sprawdzanie połączenia na urządzeniu z systemem iOS

Za pomocą skonfigurowanej i skojarzonej z aplikacją sieci VPN dla aplikacji sprawdź, czy połączenie działa z urządzenia.

### <a name="before-you-attempt-to-connect"></a>Przed podjęciem próby nawiązania połączenia

 - Upewnij się, że używasz systemu iOS 7 lub nowszego.
 - Upewnij się, że *wszystkie* wyżej wymienione zasady zostały wdrożone do tej samej grupy użytkowników. Nieprzestrzeganie tego kroku spowoduje, że środowisko sieci VPN dla aplikacji na pewno zostanie przerwane.  
 - Upewnij się, że masz zainstalowaną obsługiwaną aplikację sieci VPN innych firm. Obsługiwane są następujące aplikacje sieci VPN:
    - Pulse Secure
    - Punkt kontrolny
    - F5
    - SonicWall

### <a name="connect-using-the-per-app-vpn"></a>Nawiązywanie połączenia przy użyciu sieci VPN dla aplikacji

Sprawdź środowisko bezobsługowe, nawiązując połączenie bez konieczności wyboru sieci VPN lub wprowadzania swoich poświadczeń. Środowisko bezobsługowe oznacza, że:

 - Urządzenie nie pyta o zaufanie serwerowi sieci VPN. To znaczy, że wyświetlane jest dynamiczne okno dialogowe **zaufania**.
 - Nie musisz wprowadzać poświadczeń.
 - Nawiązano połączenie z siecią VPN po naciśnięciu przycisku Połącz.

Sprawdź połączenie na urządzeniu z systemem iOS.

1. Wybierz aplikację sieci VPN.
2. Naciśnij polecenie **Połącz**.  
Sieć VPN pomyślnie nawiązuje połączenie bez żadnych dodatkowych monitów.

<!-- ## Troubleshooting the Per-App VPN

The user experiences the feature by silently connecting to the VPN. This experience, however, can provide little information for troubleshooting. You can review the event logs crated by the iOS device.

`Note -- use the Apple Configurator as the supported tool. Only runs on a mac.'

To review event logs:

1. Connect your iOS device to a PC
2. Open the **iPhone Configuration Utility** (IPCU). If you do not have a copy, you can install it from [CompatCenter](http://www.microsoft.com/en-us/windows/compatibility/CompatCenter/ProductDetailsViewer?Name=iPhone%20Configuration%20Utility&vendor=Apple&Locale=1033%2C2057%2C3081%2C4105%2C16393&ModelOrVersion=3&BreadCrumbPath=iphone%20configuration%20utility&LastSearchTerm=iphone%2Bconfiguration%2Butility&Type=Software&tempOsid=Windows%208.1)
3. Review the logs. -->

## <a name="next-steps"></a>Następne kroki

- Aby przejrzeć ustawienia systemu iOS, zobacz temat [Ustawienia sieci VPN dla urządzeń z systemem iOS w usłudze Microsoft Intune](vpn-settings-ios.md).
-  Aby dowiedzieć się więcej na temat ustawień sieci VPN i usługi Intune, zobacz temat [Jak skonfigurować ustawienia sieci VPN w usłudze Microsoft Intune](vpn-settings-configure.md).