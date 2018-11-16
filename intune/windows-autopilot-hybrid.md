---
title: Konfigurowanie rejestracji w usłudze Intune na potrzeby urządzeń przyłączonych do hybrydowej usługi Active Directory przy użyciu rozwiązania Windows Autopilot
titleSuffix: Microsoft Intune
description: Użyj rozwiązania Windows Autopilot do zarejestrowania urządzeń przyłączonych do hybrydowej usługi Active Directory w usłudze Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/2/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7ce54f3bc51735c763359b3e59832454d0a89fad
ms.sourcegitcommit: cfce9318b5b5a3005929be6eab632038a12379c3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/09/2018
ms.locfileid: "51298092"
---
# <a name="deploy-hybrid-azure-ad-joined-devices-using-intune-and-windows-autopilot-preview"></a>Wdrażanie urządzeń przyłączonych do hybrydowej usługi Active Directory przy użyciu usługi Intune i rozwiązania Windows Autopilot (wersja zapoznawcza)
Za pomocą usługi Intune i rozwiązania Windows Autopilot można skonfigurować urządzenia przyłączone do hybrydowej usługi Azure Active Directory. Aby to zrobić, wykonaj poniższe czynności.

> [!NOTE]
> Ta funkcja będzie stopniowo wprowadzana dla użytkowników w ciągu kilku następnych dni. W związku z tym wykonanie tych kroków może nie być możliwe do momentu wdrożenia jej na Twoim koncie.

## <a name="prerequisites"></a>Wymagania wstępne

- Pomyślnie skonfigurowano [urządzenia przyłączone do hybrydowej usługi Active Directory](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan).
    - [Sprawdzono rejestrację za pomocą polecenia cmdlet Get-MsolDevice]( https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#verify-the-registration).

Urządzenia, które mają zostać zarejestrowane, muszą spełniać również następujące warunki:
- Muszą działać pod kontrolą systemu Windows 10 z [aktualizacją z października 2018 roku](https://blogs.windows.com/windowsexperience/2018/10/02/how-to-get-the-windows-10-october-2018-update/).
- Muszą mieć dostęp do Internetu.
- Muszą mieć dostęp do usługi Active Directory (połączenie sieci VPN nie jest obsługiwane).
- Muszą przejść przez proces OOBE (Out-of-Box Experience).

## <a name="set-up-windows-10-automatic-enrollment"></a>Konfigurowanie automatycznego rejestrowania urządzeń z systemem Windows 10

1. Zaloguj się w witrynie [Azure Portal](https://portal.azure.com) i wybierz pozycję **Azure Active Directory**.

   ![Zrzut ekranu witryny Azure Portal](./media/auto-enroll-azure-main.png)

2. Wybierz pozycję **Mobilność (MDM i MAM)**.

   ![Zrzut ekranu witryny Azure Portal](./media/auto-enroll-mdm.png)

3. Wybierz pozycję **Microsoft Intune**.

   ![Zrzut ekranu witryny Azure Portal](./media/auto-enroll-intune.png)

4. Upewnij się, że użytkownicy wdrażający urządzenia przyłączone do usługi Active Directory za pomocą usługi Intune i systemu Windows są członkami grupy znajdującej się w Twoim **zakresie użytkownika oprogramowania MDM**.

   ![Zrzut ekranu witryny Azure Portal](./media/auto-enroll-scope.png)

5. Użyj wartości domyślnych dla następujących adresów URL:
    - **Adres URL Warunków użytkowania zarządzania urządzeniami mobilnymi**
    - **Adres URL odnajdywania zarządzania urządzeniami przenośnymi**
    - **Adres URL zgodności oprogramowania MDM**
6. Wybierz polecenie **Zapisz**.

## <a name="increase-the-computer-account-limit-in-the-organizational-unit"></a>Zwiększanie limitu kont komputerów w jednostce organizacyjnej

Łącznik usługi Intune dla usługi Active Directory tworzy komputery rejestrujące się za pomocą rozwiązania Autopilot w lokalnej domenie usługi Active Directory. Komputer hostujący łącznik usługi Intune musi mieć uprawnienia do tworzenia obiektów komputerów w ramach domeny. 

W przypadku niektórych domen komputerom nie są przyznawane uprawnienia do tworzenia komputerów. Możliwe jest również, że administratorzy nie chcą zwiększać limitu kont komputerów na poziomie domeny. W takich sytuacjach prawa można delegować do jednostki organizacyjnej, w której tworzone są urządzenia przyłączone do hybrydowej usługi Active Directory.

Jednostka organizacyjna, której przyznano uprawnienia do tworzenia komputerów, musi być zgodna z:
- jednostką organizacyjną wprowadzoną w profilu przyłączania do domeny
- lub, jeśli nie wybrano profilu, nazwą domeny komputera dla Twojej domeny.

1. Otwórz narzędzie **Użytkownicy i komputery usługi Active Directory** (DSA.msc).

2. Kliknij prawym przyciskiem myszy jednostkę organizacyjną, która będzie używana do tworzenia komputerów przyłączonych do hybrydowej usługi Active Directory, a następnie wybierz pozycję **Deleguj kontrolę**.

    ![Zrzut ekranu przedstawiający delegowanie kontroli](media/windows-autopilot-hybrid/delegate-control.png)

3. W kreatorze **Delegowanie kontroli** wybierz pozycję **Dalej** > **Dodaj...**  > **Typy obiektów**.

4. W oknie dialogowym **Typy obiektów** zaznacz pole wyboru **Komputery**, a następnie wybierz przycisk **OK**.

    ![Zrzut ekranu przedstawiający delegowanie kontroli](media/windows-autopilot-hybrid/object-types-computers.png)

5. W oknie dialogowym **Wybieranie: Użytkownicy, komputery lub grupy** w polu **Wprowadź nazwy obiektów do wybrania** wprowadź nazwę komputera, na którym zainstalowano łącznik.

    ![Zrzut ekranu przedstawiający delegowanie kontroli](media/windows-autopilot-hybrid/enter-object-names.png)

6. Wybierz przycisk **Sprawdź nazwy**, aby zweryfikować swój wpis, a następnie kliknij przycisk **OK** > **Dalej**.

7. Wybierz pozycję **Utwórz zadanie niestandardowe do delegowania** > **Dalej**.

8. Wybierz pozycję **Tylko następujące obiekty w tym folderze**, a następnie zaznacz następujące pola wyboru:
    - **Obiekty komputerów**
    - **Utwórz wybrane obiekty w tym folderze**
    - **Usuń wybrane obiekty w tym folderze**

    ![Zrzut ekranu przedstawiający delegowanie kontroli](media/windows-autopilot-hybrid/only-following-objects.png)
    
9. Wybierz pozycję **Next** (Dalej).

10. W obszarze **Uprawnienia** zaznacz pole wyboru **Pełna kontrola** (spowoduje to zaznaczenie wszystkich innych opcji), a następnie kliknij przycisk **Dalej** > **Zakończ**.

    ![Zrzut ekranu przedstawiający delegowanie kontroli](media/windows-autopilot-hybrid/full-control.png)

## <a name="install-the-intune-connector"></a>Instalowanie łącznika usługi Intune

Łącznik usługi Intune dla usługi Active Directory musi być zainstalowany na komputerze z systemem Windows Server 2016, który ma dostęp do Internetu i usługi Active Directory. W celu zwiększenia skalowalności i dostępności lub obsługi wielu domen usługi Active Directory można zainstalować wiele łączników w danym środowisku. Zaleca się instalowanie łącznika na serwerze, na którym nie są uruchomione inne łączniki usługi Intune.

1. W usłudze [Intune](https://aka.ms/intuneportal) wybierz pozycję **Rejestracja urządzeń** > **Rejestracja urządzeń z systemem Windows** > **Łącznik usługi Intune dla usługi Active Directory (wersja zapoznawcza)** > **Dodaj łącznik**. 
2. Postępuj zgodnie z instrukcjami, aby pobrać łącznik.
3. Otwórz pobrany plik konfiguracji łącznika, aby zainstalować łącznik (ODJConnectorBootstrapper.exe).
4. Po zakończeniu instalacji wybierz pozycję **Konfiguruj**.
5. Wybierz pozycję **Zaloguj się**.
6. Wprowadź poświadczenia roli Administrator globalny lub Administrator usługi Intune użytkownika.
8. Wybierz pozycję **Rejestracja urządzeń** > **Rejestracja urządzeń z systemem Windows** > **Łącznik usługi Intune dla usługi Active Directory (wersja zapoznawcza)** i upewnij się, że połączenie jest w stanie **Aktywne**.

### <a name="configure-web-proxy-settings"></a>Konfigurowanie ustawień internetowego serwera proxy

Jeśli w środowisku sieciowym znajduje się internetowy serwer proxy, postępuj zgodnie z instrukcjami znajdującymi się w następującym artykule, aby łącznik usługi Intune dla usługi Active Directory działał prawidłowo: [Work with existing on-premises proxy servers (Praca z istniejącymi lokalnymi internetowymi serwerami proxy)](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-configure-connectors-with-proxy-servers).


## <a name="create-a-device-group"></a>Tworzenie grupy urządzeń
1. W usłudze [Intune](https://aka.ms/intuneportal) wybierz kolejno pozycje **Grupy** > **Nowa grupa**.
2. W bloku **Grupa**:
    1. Dla ustawienia **Typ grupy** wybierz pozycję **Zabezpieczenia**.
    2. Wpisz odpowiedni tekst w polach **Nazwa grupy** i **Opis grupy**.
    3. Wybierz **typ członkostwa**.
3. Jeśli powyżej wybrano pozycję **Urządzenie dynamiczne** dla ustawienia **Typ członkostwa**, to w bloku **Grupa** wybierz pozycję **Dynamiczne urządzenia członkowskie** i wpisz dowolny poniższy kod w polu **Reguła zaawansowana**.
    - Aby utworzyć grupę obejmującą wszystkie urządzenia rozwiązania Autopilot, wpisz `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
    - Aby utworzyć grupę obejmującą wszystkie urządzenia rozwiązania Autopilot z określonym identyfikatorem zamówienia, wpisz: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881") `
    - Aby utworzyć grupę obejmującą wszystkie urządzenia rozwiązania Autopilot z określonym identyfikatorem zamówienia zakupu, wpisz: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`
    
    Po dodaniu kodu w polu **Reguła zaawansowana** wybierz pozycję **Zapisz**.
5. Wybierz pozycję **Utwórz**.  

## <a name="register-your-autopilot-devices"></a>Rejestrowanie urządzeń z rozwiązaniem Autopilot

Wybierz jeden z następujących sposobów rejestrowania urządzeń z rozwiązaniem Autopilot:

### <a name="register-autopilot-devices-that-are-already-enrolled"></a>Rejestrowanie już zarejestrowanych urządzeń z rozwiązaniem Autopilot

1. Utwórz profil wdrażania programu Autopilot z pozycją **Konwertuj wszystkie urządzenia docelowe na rozwiązanie Autopilot** ustawioną na wartość **Tak**. 
2. Przypisz profil do grupy zawierającej elementy członkowskie, które mają zostać automatycznie zarejestrowane za pomocą rozwiązania Autopilot.

Aby uzyskać więcej informacji, zobacz [Tworzenie profilu wdrażania rozwiązania Autopilot](enrollment-autopilot.md#create-an-autopilot-deployment-profile).

### <a name="register-autopilot-devices-that-arent-enrolled"></a>Rejestrowanie niezarejestrowanych urządzeń z rozwiązaniem Autopilot

Jeśli Twoje urządzenia nie są jeszcze zarejestrowane, możesz je samodzielnie zarejestrować. Aby uzyskać więcej informacji, zobacz [Dodawanie urządzeń](enrollment-autopilot.md#add-devices).

### <a name="register-devices-from-an-oem"></a>Rejestrowanie urządzeń od producentów OEM

Jeśli kupujesz nowe urządzenia, niektórzy producenci OEM mogą je zarejestrować za Ciebie. Więcej informacji możesz znaleźć na [stronie rozwiązania Windows Autopilot](http://aka.ms/WindowsAutopilot).

Gdy urządzenia z rozwiązaniem Autopilot są zarejestrowane (i przed zarejestrowaniem ich w usłudze Intune), będą one widoczne w trzech miejscach (nazwami będą ich numery seryjne):
- W bloku Urządzenia z rozwiązaniem Autopilot w usłudze Intune w witrynie Azure Portal (**Rejestrowanie urządzeń** > **Rejestracja w systemie Windows** > **Urządzenia**).
- W bloku Urządzenia w usłudze Azure AD w usłudze Intune w witrynie Azure Portal (**Urządzenia** > **Urządzenia w usłudze Azure AD**).
- W bloku Wszystkie urządzenia w usłudze Azure Active Directory w witrynie Azure Portal (**Urządzenia** > **Wszystkie urządzenia**).

Po zarejestrowaniu urządzeń z rozwiązaniem Autopilot będą one widoczne w czterech miejscach:
- W bloku Urządzenia z rozwiązaniem Autopilot w usłudze Intune w witrynie Azure Portal (**Rejestrowanie urządzeń** > **Rejestracja w systemie Windows** > **Urządzenia**).
- W bloku Urządzenia w usłudze Azure AD w usłudze Intune w witrynie Azure Portal (**Urządzenia** > **Urządzenia w usłudze Azure AD**).
- W bloku Wszystkie urządzenia w usłudze Azure Active Directory w witrynie Azure Portal (**Urządzenia** > **Wszystkie urządzenia**).
- W bloku Wszystkie urządzenia w usłudze Intune w witrynie Azure Portal (**Urządzenia** > **Wszystkie urządzenia**).

Po zarejestrowaniu urządzeń z rozwiązaniem Autopilot ich nazwy zmienią się na nazwy hostów tych urządzeń. Domyślnie zaczynają się one od ciągu „DESKTOP-”.




## <a name="create-and-assign-an-autopilot-deployment-profile"></a>Tworzenie i przypisywanie profilu wdrażania rozwiązania Autopilot
Profile wdrażania rozwiązania Autopilot służą do konfigurowania urządzeń z rozwiązaniem Autopilot.

1. W usłudze [Intune](https://aka.ms/intuneportal) wybierz kolejno pozycje **Rejestrowanie urządzenia** > **Rejestracja w systemie Windows** > **Profile wdrażania** > **Utwórz profil**.
2. Podaj **nazwę** i opcjonalny **opis**.
3. W obszarze **Tryb wdrożenia** wybierz pozycję **Sterowane przez użytkownika**.
4. W polu **Dołącz do usługi Azure AD jako** wybierz pozycję **Dołączone do hybrydowej usługi Azure AD (wersja zapoznawcza)**.
5. Wybierz pozycję **Środowisko gotowe do użycia (OOBE, Out-of-box experience)**, skonfiguruj odpowiednie opcje, a następnie wybierz przycisk **Zapisz**.
6. Wybierz pozycję **Utwórz**, aby utworzyć profil. 
7. W bloku profilu wybierz pozycję **Przypisania**.
8. Wybierz pozycję **Wybierz grupy** w bloku **Wybieranie grup**, wybierz grupę urządzeń, a następnie wybierz pozycję **Wybierz**.

Zmiana stanu urządzenia z wartości **Nieprzypisane** do wartości **Przypisywanie**, a na koniec do wartości **Przypisane** potrwa około 15 minut.

## <a name="turn-on-the-enrollment-status-page-optional"></a>Włączanie strony stanu rejestracji (opcjonalnie)

1. W usłudze [Intune](https://aka.ms/intuneportal) wybierz **Rejestracja urządzenia** > **Rejestracja systemu Windows** > **Strona ze stanem rejestracji (wersja zapoznawcza)**.
2. W bloku **Strona ze stanem rejestracji** wybierz pozycje **Domyślne** > **Ustawienia**.
3. Aby **wyświetlić postęp instalacji aplikacji i profilu**, wybierz pozycję **Tak**.
4. Zgodnie z potrzebami skonfiguruj inne opcje.
5. Wybierz polecenie **Zapisz**.

## <a name="create-and-assign-a-domain-join-profile"></a>Tworzenie i przypisywanie profilu przyłączania do domeny

1. W usłudze [Intune](https://aka.ms/intuneportal) wybierz kolejno pozycje **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
2. Wprowadź następujące właściwości:
   - **Nazwa**: wprowadź opisową nazwę nowego profilu.
   - **Opis:** wprowadź opis profilu.
   - **Platforma**: wybierz **system Windows 10 lub nowszy**.
   - **Typ profilu**: wybierz pozycję **Przyłączanie do domeny (wersja zapoznawcza)**.
3. Wybierz pozycję **Ustawienia**, a następnie podaj wartości w polach **Prefiks nazwy komputera**, **Nazwa domeny** i **Jednostka organizacyjna** (opcjonalnie). 
4. Wybierz pozycję **OK** > **Utwórz**. Profil zostanie utworzony i wyświetlony na liście.
5. Aby przypisać ten profil, wykonaj kroki w obszarze [Przypisywanie profilu urządzenia](device-profile-assign.md#assign-a-device-profile). 

## <a name="next-steps"></a>Następne kroki

Po skonfigurowaniu rozwiązania Windows Autopilot dowiedz się, jak zarządzać tymi urządzeniami. Aby uzyskać więcej informacji, zobacz artykuł [Co to jest zarządzanie urządzeniami w usłudze Microsoft Intune?](device-management.md)
