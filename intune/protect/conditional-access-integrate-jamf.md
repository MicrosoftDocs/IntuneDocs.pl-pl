---
title: Integrowanie narzędzia Jamf Pro z usługą Microsoft Intune w celu zachowania zgodności
titleSuffix: Microsoft Intune
description: Stosuj zasady zgodności usługi Microsoft Intune z dostępem warunkowym usługi Azure Active Directory, aby pomóc zabezpieczać urządzenia zarządzane przez narzędzie Jamf.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/20/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4b6dcbcc-4661-4463-9a36-698d673502c6
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d7a63f3ff1e2936eff0961d4a9b368b0289e2b65
ms.sourcegitcommit: f04e21ec459998922ba9c7091ab5f8efafd8a01c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71813972"
---
# <a name="integrate-jamf-pro-with-intune-for-compliance"></a>Integrowanie narzędzia Jamf Pro z usługą Intune w celu zachowania zgodności

Dotyczy: Usługa Intune w witrynie Azure Portal

Jeśli do zarządzania urządzeniami z systemem macOS Twoja organizacja używa narzędzia [Jamf Pro](https://www.jamf.com), zastosowanie zasad zgodności usługi Microsoft Intune i dostępu warunkowego usługi Azure Active Directory (Azure AD) zapewnia, że urządzenia w organizacji będą zgodne, zanim uzyskają dostęp do zasobów firmowych. Ten artykuł pomoże Ci skonfigurować integrację narzędzia Jamf z usługą Intune.

Gdy narzędzie Jamf Pro jest zintegrowane z usługą Intune, można za pośrednictwem usługi Azure AD synchronizować dane spisu z urządzeń z systemem macOS z usługą Intune. Aparat zgodności usługi Intune analizuje następnie dane spisu w celu wygenerowania raportu. Analiza usługi Intune jest połączona z analizą dotyczącą tożsamości użytkownika urządzenia w usłudze Azure AD w celu przeprowadzenia wymuszania przy użyciu dostępu warunkowego. Urządzenia, które są zgodne z zasadami dostępu warunkowego, mogą uzyskać dostęp do chronionych zasobów firmy.

Po skonfigurowaniu integracji należy [skonfigurować narzędzie Jamf i usługę Intune tak, aby wymusić zgodność z dostępem warunkowym](conditional-access-assign-jamf.md) na urządzeniach zarządzanych przez narzędzie Jamf.  


## <a name="prerequisites"></a>Wymagania wstępne

### <a name="products-and-services"></a>Produkty i usługi
Aby skonfigurować dostęp warunkowy przy użyciu narzędzia Jamf Pro, wymagane są następujące elementy:

- Program Jamf Pro 10.1.0 lub nowsza wersja
- [Aplikacja Portal firmy dla systemu macOS](https://aka.ms/macoscompanyportal)
- Urządzenia z systemem macOS (OS X 10.11 Yosemite lub nowszy)

### <a name="network-ports"></a>Porty sieciowe
<!-- source: https://support.microsoft.com/en-us/help/4519171/troubleshoot-problems-when-integrating-jamf-with-microsoft-intune -->
Aby umożliwić poprawną integrację, następujące porty powinny być dostępne dla narzędzia Jamf i usługi Intune: 
- **Intune**: port 443
- **Apple**: porty 2195, 2196 i 5223 (wypychanie powiadomień do usługi Intune)
- **Jamf**: porty 80 i 5223

Aby umożliwić usłudze APNS poprawne działanie w sieci, należy również włączyć połączenia wychodzące do i przekierowania z:
- bloku Apple 17.0.0.0/8 przez porty TCP 5223 i 443 ze wszystkich sieci klienta,   
- portów 2195 i 2196 z serwerów Jamf Pro.  

Aby uzyskać więcej informacji o tych portach, zobacz następujące artykuły:  
- [Przepustowość i wymagania dotyczące konfiguracji sieci usługi Intune](../fundamentals/network-bandwidth-use.md).
- [Network Ports Used by Jamf Pro](https://www.jamf.com/jamf-nation/articles/34/network-ports-used-by-jamf-pro) (Porty sieciowe używane przez Jamf Pro) w witrynie jamf.com.
- [Porty TCP i UDP używane przez produkty Apple](https://support.apple.com/HT202944) w witrynie support.apple.com


## <a name="connect-intune-to-jamf-pro"></a>Łączenie usługi Intune z narzędziem Jamf Pro

Aby połączyć usługę Intune z narzędziem Jamf Pro:

1. Utwórz nową aplikację na platformie Azure.
2. Włącz możliwość integracji usługi Intune z narzędziem Jamf Pro.
3. Skonfiguruj dostęp warunkowy w narzędziu Jamf Pro.

## <a name="create-an-application-in-azure-active-directory"></a>Utworzenie aplikacji w usłudze Azure Active Directory

1. W witrynie [Azure Portal](https://portal.azure.com) przejdź kolejno do pozycji **Azure Active Directory** > **Rejestracje aplikacji**, a następnie wybierz pozycję **Nowa rejestracja**. 

2. Na stronie **Zarejestruj aplikację** określ następujące informacje:
   - W sekcji **Nazwa** wprowadź nazwę opisową aplikacji, na przykład **Dostęp warunkowy Jamf**.
   - W sekcji **Obsługiwane typy kont** wybierz pozycję **Konta w dowolnym katalogu organizacyjnym**. 
   - W polu **Identyfikator URI przekierowania** pozostaw wartość domyślną sieci Web, a następnie określ adres URL wystąpienia narzędzia Jamf Pro.  

3. Wybierz opcję **Zarejestruj**, aby utworzyć aplikację i otworzyć stronę **Przegląd** dotyczącą nowej aplikacji.  

4. Na stronie **Przegląd** aplikacji skopiuj wartość **Identyfikator klienta aplikacji** i zapisz ją w celu późniejszego użycia. Będzie potrzebna w późniejszych procedurach.  

5. Wybierz pozycję **Certyfikaty i klucze tajne** w obszarze **Zarządzaj**. Wybierz przycisk **Nowy klucz tajny klienta**. Wprowadź wartość w polu **Opis**, wybierz dowolną opcję w polu **Wygasa** i wybierz polecenie **Dodaj**.

   > [!IMPORTANT]  
   > Zanim opuścisz tę stronę, skopiuj wartość klucza tajnego klienta i zapisz ją do późniejszego użycia. Będzie potrzebna w późniejszych procedurach. Ta wartość nie będzie dostępna później bez ponownego tworzenia rejestracji aplikacji.  

6. Wybierz pozycję **Uprawnienia interfejsu API** w sekcji **Zarządzanie**. Wybierz istniejące uprawnienia, a następnie wybierz pozycję **Usuń uprawnienie**, aby usunąć te uprawnienia. Usunięcie istniejących uprawnień jest konieczne, ponieważ dodajesz nowe uprawnienie, a aplikacja działa wyłącznie wówczas, gdy ma tylko jedno wymagane uprawnienie.  

7. Aby przypisać nowe uprawnienie, wybierz pozycję **Dodaj uprawnienie**. Na stronie **Żądanie uprawnień interfejsu API** wybierz pozycję **Intune**, a następnie wybierz pozycję **Uprawnienia aplikacji**. Zaznacz pole wyboru tylko przy pozycji **update_device_attributes**.  

   Wybierz opcję **Dodaj uprawnienie**, aby zapisać tę konfigurację.  

8. Na stronie **Uprawnienia interfejsu API** wybierz pozycję **Wyraź zgodę administratora dla *\<Twój dzierżawca>*** i wybierz **Tak**.  Po pomyślnym zarejestrowaniu aplikacji uprawnienia interfejsu API powinny wyglądać następująco: ![Uprawnienia po pomyślnej rejestracji](./media/conditional-access-integrate-jamf/sucessfull-app-registration.png)

   Proces rejestracji aplikacji w usłudze Azure AD został ukończony.


    > [!NOTE]
    > Jeśli klucz tajny klienta wygaśnie, należy utworzyć nowy klucz tajny klienta na platformie Azure, a następnie zaktualizować dane dostępu warunkowego w narzędziu Jamf Pro. Aby uniknąć zakłóceń w świadczeniu usług, platforma Azure umożliwia stosowanie zarówno starego klucza tajnego, jak i nowego klucza.

## <a name="enable-intune-to-integrate-with-jamf-pro"></a>Włączanie możliwości integracji usługi Intune z narzędziem Jamf Pro

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) i przejdź do pozycji **Microsoft Intune** > **Zgodność urządzenia** > **Zarządzanie urządzeniem partnera**.

2. Włącz Łącznik zgodności dla narzędzia Jamf poprzez wklejenie identyfikatora aplikacji zapisanego we wcześniejszej części procedury w polu **Identyfikator aplikacji usługi Azure Active Directory w oprogramowaniu Jamf**.

3. Wybierz pozycję **Zapisz**.

## <a name="configure-microsoft-intune-integration-in-jamf-pro"></a>Konfigurowanie integracji z usługą Microsoft Intune w narzędziu Jamf Pro

1. W narzędziu Jamf Pro przejdź do opcji **Globalne zarządzanie** > **Dostęp warunkowy**. Kliknij przycisk **Edytuj** na karcie **Integracja systemu macOS z usługą Intune**.

2. Zaznacz pole wyboru przy opcji **Włącz integrację z usługą Intune dla systemu macOS**.

3. Podaj wymagane informacje o dzierżawie platformy Azure, w tym wartości pól **Lokalizacja**, **Nazwa domeny**, **Identyfikator aplikacji** oraz wartość *klucza tajnego klienta* zapisaną podczas tworzenia aplikacji w usłudze Azure AD.  

4. Wybierz pozycję **Zapisz**. Narzędzie Jamf Pro sprawdza ustawienia i weryfikuje poprawność konfiguracji.

## <a name="set-up-compliance-policies-and-register-devices"></a>Konfigurowanie zasad zgodności i rejestrowanie urządzeń

Po skonfigurowaniu integracji między usługą Intune i narzędziem Jamf musisz [zastosować zasady zgodności do urządzeń zarządzanych za pomocą narzędzia Jamf](conditional-access-assign-jamf.md).


## <a name="disconnect-jamf-pro-and-intune"></a>Rozłączanie narzędzia Jamf Pro i usługi Intune 

Jeśli nie korzystasz już z narzędzia Jamf Pro do zarządzania komputerami Mac w organizacji i chcesz zarządzać użytkownikami w usłudze Intune, musisz usunąć połączenie między narzędziem Jamf Pro a usługą Intune. Połączenie można usunąć, używając konsoli narzędzia Jamf Pro. 

1. W narzędziu Jamf Pro wybierz kolejno opcje **Globalne zarządzanie** > **Dostęp warunkowy**. Na karcie **Integracja systemu macOS z usługą Intune** kliknij przycisk **Edytuj**.
2. Wyczyść pole wyboru przy opcji **Włącz integrację z usługą Intune dla systemu macOS**.
3. Wybierz pozycję **Zapisz**. Narzędzie Jamf Pro wyśle konfigurację do usługi Intune i integracja zostanie wyłączona.
4. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973). Kliknij kolejno pozycje **Microsoft Intune** > **Zgodność urządzeń** > **Zarządzanie urządzeniem partnera**, aby upewnić się, że bieżący stan to **Zakończono**. 

   > [!NOTE]
   > Urządzenia Mac w Twojej organizacji zostaną usunięte w dniu wskazanym w konsoli (po trzech miesiącach). 

## <a name="next-steps"></a>Następne kroki

- [Stosowanie zasad zgodności do urządzeń zarządzanych za pomocą narzędzia Jamf](conditional-access-assign-jamf.md)
- [Dane wysyłane do usługi Intune przez narzędzie Jamf](data-jamf-sends-to-intune.md)
