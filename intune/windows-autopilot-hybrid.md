---
title: Rejestracja na potrzeby urządzeń przyłączonych do hybrydowej usługi Azure AD – rozwiązanie Windows Autopilot
titleSuffix: ''
description: Użycie rozwiązania Windows Autopilot do zarejestrowania urządzeń przyłączonych do hybrydowej usługi Azure AD w usłudze Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/06/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
ms.reviewer: damionw
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: e51c13136b5dd79ba9ff395008c6a8cb3e67e9e4
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/02/2019
ms.locfileid: "57238187"
---
# <a name="deploy-hybrid-azure-ad-joined-devices-by-using-intune-and-windows-autopilot-preview"></a>Wdrażanie urządzeń przyłączonych do hybrydowej usługi Azure AD przy użyciu usługi Intune i rozwiązania Windows Autopilot (wersja zapoznawcza)
Za pomocą usługi Intune i rozwiązania Windows Autopilot można skonfigurować urządzenia przyłączone do hybrydowej usługi Azure Active Directory (Azure AD). Aby to zrobić, wykonaj kroki opisane w tym artykule.

## <a name="prerequisites"></a>Wymagania wstępne

Pomyślnie skonfigurowano [urządzenia przyłączone do hybrydowej usługi Azure AD](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan). [Sprawdzono rejestrację urządzenia]( https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#verify-the-registration) za pomocą polecenia cmdlet Get-MsolDevice.

Urządzenia, które mają zostać zarejestrowane, muszą spełniać również następujące warunki:
- Muszą działać pod kontrolą systemu Windows 10 z [aktualizacją z października 2018 roku](https://blogs.windows.com/windowsexperience/2018/10/02/how-to-get-the-windows-10-october-2018-update/).
- Muszą mieć dostęp do Internetu.
- Muszą mieć dostęp do usługi Active Directory (połączenie sieci VPN nie jest obsługiwane).
- Muszą przejść przez proces OOBE (Out-of-Box Experience).

## <a name="set-up-windows-10-automatic-enrollment"></a>Konfigurowanie automatycznego rejestrowania urządzeń z systemem Windows 10

1. Zaloguj się w witrynie [Azure Portal](https://portal.azure.com) i w lewym okienku wybierz pozycję **Azure Active Directory**.

   ![Witryna Azure Portal](./media/auto-enroll-azure-main.png)

1. Wybierz pozycję **Mobilność (MDM i MAM)**.

   ![Okienko usługi Azure Active Directory](./media/auto-enroll-mdm.png)

1. Wybierz pozycję **Microsoft Intune**.

   ![Okienko Mobilność (MDM i MAM)](./media/auto-enroll-intune.png)

1. Upewnij się, że użytkownicy wdrażający urządzenia przyłączone do usługi Azure AD za pomocą usługi Intune i systemu Windows są członkami grupy znajdującej się w Twoim **zakresie użytkownika oprogramowania MDM**.

   ![Okienko Mobilność (MDM i MAM) — Konfigurowanie](./media/auto-enroll-scope.png)

1. Użyj wartości domyślnych w polach **Adres URL warunków użytkowania usługi MDM**, **Adres URL odnajdywania usługi MDM** i **Adres URL zgodności usługi MDM**, a następnie wybierz pozycję **Zapisz**.

## <a name="increase-the-computer-account-limit-in-the-organizational-unit"></a>Zwiększanie limitu kont komputerów w jednostce organizacyjnej

Łącznik usługi Intune dla usługi Active Directory tworzy komputery rejestrujące się za pomocą rozwiązania Autopilot w lokalnej domenie usługi Active Directory. Komputer hostujący łącznik usługi Intune musi mieć uprawnienia do tworzenia obiektów komputerów w ramach domeny. 

W przypadku niektórych domen komputerom nie są przyznawane uprawnienia do tworzenia komputerów. Ponadto domeny mają wbudowany limit (domyślnie 10), mający zastosowanie do wszystkich użytkowników i komputerów, które nie mają delegowanych uprawnień do tworzenia obiektów komputerów. W związku z tym uprawnienia muszą zostać delegowane do komputerów hostujących łącznik usługi Intune w jednostce organizacyjnej, w której tworzone są urządzenia przyłączone do hybrydowej usługi Azure AD.

Jednostka organizacyjna, której przyznano uprawnienia do tworzenia komputerów, musi być zgodna z:
- jednostką organizacyjną wprowadzoną w profilu przyłączania do domeny
- lub, jeśli nie wybrano profilu, nazwą domeny komputera dla Twojej domeny.

1. Otwórz narzędzie **Użytkownicy i komputery usługi Active Directory (DSA.msc)**.

1. Kliknij prawym przyciskiem myszy jednostkę organizacyjną, która będzie używana do tworzenia komputerów przyłączonych do hybrydowej usługi Azure AD, a następnie wybierz pozycję **Deleguj kontrolę**.

    ![Polecenie Deleguj kontrolę](media/windows-autopilot-hybrid/delegate-control.png)

1. W kreatorze **Delegowanie kontroli** wybierz pozycję **Dalej** > **Dodaj** > **Typy obiektów**.

1. W okienku **Typy obiektów** zaznacz pole wyboru **Komputery**, a następnie wybierz przycisk **OK**.

    ![Okienko Typy obiektów](media/windows-autopilot-hybrid/object-types-computers.png)

1. W okienku **Wybieranie: Użytkownicy, komputery lub grupy** w polu **Wprowadź nazwy obiektów do wybrania** wprowadź nazwę komputera, na którym zainstalowano łącznik.

    ![Okienko Wybieranie: Użytkownicy, komputery lub grupy](media/windows-autopilot-hybrid/enter-object-names.png)

1. Wybierz pozycję **Sprawdź nazwy**, aby zweryfikować swój wpis, wybierz przycisk **OK**, a następnie wybierz przycisk **Dalej**.

1. Wybierz pozycję **Utwórz zadanie niestandardowe do delegowania** > **Dalej**.

1. Zaznacz pole wyboru **Tylko następujące obiekty w tym folderze**, a następnie zaznacz pola wyboru **Obiekty komputerów**, **Utwórz wybrane obiekty w tym folderze** i **Usuń wybrane obiekty w tym folderze**.

    ![Okienko Typ obiektu usługi Active Directory](media/windows-autopilot-hybrid/only-following-objects.png)
    
1. Wybierz pozycję **Dalej**.

1. W obszarze **Uprawnienia** zaznacz pole wyboru **Pełna kontrola**.  
    Ta akcja powoduje zaznaczenie wszystkich innych opcji.

    ![Okienko Uprawnienia](media/windows-autopilot-hybrid/full-control.png)

1. Wybierz pozycję **Dalej**, a następnie **Zakończ**.

## <a name="install-the-intune-connector"></a>Instalowanie łącznika usługi Intune

Łącznik usługi Intune dla usługi Active Directory musi być zainstalowany na komputerze z systemem Windows Server 2016 lub nowszym. Ten komputer musi również mieć dostęp do Internetu i usługi Active Directory. W celu zwiększenia skalowalności i dostępności lub obsługi wielu domen usługi Active Directory można zainstalować wiele łączników w danym środowisku. Zaleca się instalowanie łącznika na serwerze, na którym nie są uruchomione inne łączniki usługi Intune.

1. Upewnij się, że pakiet językowy został zainstalowany i skonfigurowany zgodnie z opisem w temacie [Intune Connector (Preview) language requirements](https://docs.microsoft.com/windows/deployment/windows-autopilot/intune-connector) (Wymagania językowe łącznika usługi Intune (wersja zapoznawcza)).
2. W usłudze [Intune](https://aka.ms/intuneportal) wybierz pozycję **Rejestracja urządzenia** > **Rejestracja w systemie Windows** > **Łącznik usługi Intune dla usługi Active Directory (wersja zapoznawcza)** > **Dodaj łącznik**. 
3. Postępuj zgodnie z instrukcjami, aby pobrać łącznik.
4. Otwórz pobrany plik konfiguracji łącznika, *ODJConnectorBootstrapper.exe*, aby zainstalować łącznik.
5. Na koniec instalacji wybierz pozycję **Konfiguruj**.
6. Wybierz polecenie **Zaloguj się**.
7. Wprowadź poświadczenia roli Administrator globalny lub Administrator usługi Intune użytkownika.  
   Konto użytkownika musi mieć przypisaną licencję usługi Intune.
8. Wybierz pozycję **Rejestracja urządzenia** > **Rejestracja w systemie Windows** > **Łącznik usługi Intune dla usługi Active Directory (wersja zapoznawcza)** i upewnij się, że połączenie jest w stanie **Aktywne**.

> [!NOTE]
> Od zalogowania się w łączniku do jego pojawienia się w usłudze [Intune](https://aka.ms/intuneportal) może upłynąć kilka minut. Łącznik pojawi się tylko wtedy, jeśli pomyślnie skomunikuje się z usługą Intune.

### <a name="configure-web-proxy-settings"></a>Konfigurowanie ustawień internetowego serwera proxy

Jeśli w środowisku sieciowym znajduje się internetowy serwer proxy, upewnij się, że łącznik usługi Intune dla usługi Active Directory działał prawidłowo, postępując zgodnie z instrukcjami z artykułu [Work with existing on-premises proxy servers (Praca z istniejącymi lokalnymi internetowymi serwerami proxy)](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-configure-connectors-with-proxy-servers).


## <a name="create-a-device-group"></a>Tworzenie grupy urządzeń
1. W usłudze [Intune](https://aka.ms/intuneportal) wybierz kolejno pozycje **Grupy** > **Nowa grupa**.

1. W okienku **Grupa** wykonaj następujące czynności:

    a. W obszarze **Typ grupy** wybierz pozycję **Zabezpieczenia**.

    b. Wprowadź odpowiedni tekst w polach **Nazwa grupy** i **Opis grupy**.

    c. Wybierz **typ członkostwa**.

1. Jeśli jako typ członkostwa wybrano pozycję **Urządzenie dynamiczne**, to w bloku **Grupa** wybierz pozycję **Dynamiczne urządzenia członkowskie**, a następnie w polu **Reguła zaawansowana** wykonaj jedną z poniższych czynności:
    - Aby utworzyć grupę obejmującą wszystkie urządzenia rozwiązania Autopilot, wprowadź `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`.
    - Aby utworzyć grupę obejmującą wszystkie urządzenia rozwiązania Autopilot z określonym identyfikatorem zamówienia, wprowadź `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`.
    - Aby utworzyć grupę obejmującą wszystkie urządzenia rozwiązania Autopilot z określonym identyfikatorem zamówienia zakupu, wprowadź `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`.
    
1. Wybierz pozycję **Zapisz**.

1. Wybierz przycisk **Utwórz**.  

## <a name="register-your-autopilot-devices"></a>Rejestrowanie urządzeń z rozwiązaniem Autopilot

Wybierz jeden z następujących sposobów rejestrowania urządzeń z rozwiązaniem Autopilot.

### <a name="register-autopilot-devices-that-are-already-enrolled"></a>Rejestrowanie już zarejestrowanych urządzeń z rozwiązaniem Autopilot

1. Utwórz profil wdrażania programu Autopilot z pozycją **Konwertuj wszystkie urządzenia docelowe na rozwiązanie Autopilot** ustawioną na wartość **Tak**. 
2. Przypisz profil do grupy zawierającej elementy członkowskie, które mają zostać automatycznie zarejestrowane za pomocą rozwiązania Autopilot.

Aby uzyskać więcej informacji, zobacz [Tworzenie profilu wdrażania rozwiązania Autopilot](enrollment-autopilot.md#create-an-autopilot-deployment-profile).

### <a name="register-autopilot-devices-that-arent-enrolled"></a>Rejestrowanie niezarejestrowanych urządzeń z rozwiązaniem Autopilot

Jeśli Twoje urządzenia nie są jeszcze zarejestrowane, możesz je samodzielnie zarejestrować. Aby uzyskać więcej informacji, zobacz [Dodawanie urządzeń](enrollment-autopilot.md#add-devices).

### <a name="register-devices-from-an-oem"></a>Rejestrowanie urządzeń od producentów OEM

Jeśli kupujesz nowe urządzenia, niektórzy producenci OEM mogą je zarejestrować za Ciebie. Więcej informacji możesz znaleźć na [stronie rozwiązania Windows Autopilot](http://aka.ms/WindowsAutopilot).

Gdy urządzenia z rozwiązaniem Autopilot są *zarejestrowane* (przed zarejestrowaniem ich w usłudze Intune), są one wyświetlane w trzech miejscach (nazwami będą ich numery seryjne):
- Okienko **Urządzenia rozwiązania Autopilot** w usłudze Intune w witrynie Azure Portal. Wybierz pozycję **Rejestracja urządzenia** > **Rejestracja w systemie Windows** > **Urządzenia**.
- Okienko **Urządzenia usługi Azure AD** w usłudze Intune w witrynie Azure Portal. Wybierz pozycję **Urządzenia** > **Urządzenia usługi Azure AD**.
- Okienko **Wszystkie urządzenia w usłudze Azure AD** w usłudze Azure Active Directory w witrynie Azure Portal (po wybraniu pozycji **Urządzenia** > **Wszystkie urządzenia**).

Po *zarejestrowaniu* urządzenia rozwiązania Autopilot są wyświetlane w czterech miejscach:
- Okienko **Urządzenia rozwiązania Autopilot** w usłudze Intune w witrynie Azure Portal. Wybierz pozycję **Rejestracja urządzenia** > **Rejestracja w systemie Windows** > **Urządzenia**.
- Okienko **Urządzenia usługi Azure AD** w usłudze Intune w witrynie Azure Portal. Wybierz pozycję **Urządzenia** > **Urządzenia usługi Azure AD**.
- Okienko **Wszystkie urządzenia w usłudze Azure AD** w usłudze Azure Active Directory w witrynie Azure Portal. Wybierz pozycję **Urządzenia** > **Wszystkie urządzenia**.
- Okienko **Wszystkie urządzenia** w usłudze Intune w witrynie Azure Portal. Wybierz pozycję **Urządzenia** > **Wszystkie urządzenia**.

Po zarejestrowaniu urządzeń rozwiązania Autopilot ich nazwy stają się nazwami hostów tych urządzeń. Domyślnie nazwa hosta zaczyna się od ciągu *DESKTOP-*.


## <a name="create-and-assign-an-autopilot-deployment-profile"></a>Tworzenie i przypisywanie profilu wdrażania rozwiązania Autopilot
Profile wdrażania rozwiązania Autopilot służą do konfigurowania urządzeń z rozwiązaniem Autopilot.

1. W usłudze [Intune](https://aka.ms/intuneportal) wybierz kolejno pozycje **Rejestracja urządzenia** > **Rejestracja w systemie Windows** > **Profile wdrażania** > **Utwórz profil**.
1. Wpisz **Nazwę** i opcjonalnie **Opis**.
1. W obszarze **Tryb wdrożenia** wybierz pozycję **Sterowane przez użytkownika**.
1. W polu **Dołącz do usługi Azure AD jako** wybierz pozycję **Dołączono hybrydowo do usługi Azure AD (wersja zapoznawcza)**.
1. Wybierz pozycję **Środowisko gotowe do użycia (OOBE, Out-of-box experience)**, skonfiguruj odpowiednie opcje, a następnie wybierz przycisk **Zapisz**.
1. Wybierz pozycję **Utwórz**, aby utworzyć profil. 
1. W okienku profilu wybierz pozycję **Przypisania**.
1. Wybierz pozycję **Wybierz grupy**.
1. W okienku **Wybierz grupy** wybierz grupę urządzeń, a następnie kliknij pozycję **Wybierz**.

Zmiana stanu urządzenia z wartości *Nieprzypisane* do wartości *Przypisywanie*, a na koniec do wartości *Przypisane* trwa około 15 minut.

## <a name="optional-turn-on-the-enrollment-status-page"></a>(Opcjonalnie) Włączanie strony stanu rejestracji

1. W usłudze [Intune](https://aka.ms/intuneportal) wybierz kolejno pozycje **Rejestracja urządzenia** > **Rejestracja w systemie Windows** > **Strona ze stanem rejestracji (wersja zapoznawcza)**.
1. W okienku **Strona ze stanem rejestracji** wybierz pozycje **Domyślne** > **Ustawienia**.
1. W polu **Pokaż postęp instalacji aplikacji i profilu** wybierz pozycję **Tak**.
1. Zgodnie z potrzebami skonfiguruj inne opcje.
1. Wybierz pozycję **Zapisz**.

## <a name="create-and-assign-a-domain-join-profile"></a>Tworzenie i przypisywanie profilu przyłączania do domeny

1. W usłudze [Intune](https://aka.ms/intuneportal) wybierz kolejno pozycje **Konfiguracja urządzenia** > **Profile** > **Utwórz profil**.
1. Wprowadź następujące właściwości:
   - **Nazwa**: Wprowadź opisową nazwę nowego profilu.
   - **Opis**: Wprowadź opis profilu.
   - **Platforma**: Wybierz pozycję **Windows 10 i nowsze**.
   - **Typ profilu**: Wybierz pozycję **Dołączanie do domeny (wersja zapoznawcza)**.
1. Wybierz pozycję **Ustawienia**, a następnie podaj wartości w polach **Prefiks nazwy komputera**, **Nazwa domeny** i (opcjonalnie) **Jednostka organizacyjna** w [formacie DN](https://docs.microsoft.com/windows/desktop/ad/object-names-and-identities#distinguished-name). 
1. Wybierz pozycje **OK** > **Utwórz**.  
    Profil zostanie utworzony i wyświetlony na liście.
1. Aby przypisać ten profil, wykonaj kroki w obszarze [Przypisywanie profilu urządzenia](device-profile-assign.md#assign-a-device-profile). 

## <a name="next-steps"></a>Następne kroki

Po skonfigurowaniu rozwiązania Windows Autopilot dowiedz się, jak zarządzać tymi urządzeniami. Aby uzyskać więcej informacji, zobacz artykuł [Co to jest zarządzanie urządzeniami w usłudze Microsoft Intune?](device-management.md)
