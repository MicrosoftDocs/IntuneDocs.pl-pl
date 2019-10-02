---
title: Integrowanie narzędzia Jamf Pro z usługą Microsoft Intune w celu zachowania zgodności
titleSuffix: Microsoft Intune
description: Stosuj zasady zgodności usługi Microsoft Intune z dostępem warunkowym usługi Azure Active Directory, aby pomóc zabezpieczać urządzenia zarządzane przez narzędzie Jamf.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 05/16/2019
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
ms.openlocfilehash: b439067d06cf49a4ff83288e109d1fccd3801106
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71722725"
---
# <a name="integrate-jamf-pro-with-intune-for-compliance"></a>Integrowanie narzędzia Jamf Pro z usługą Intune w celu zachowania zgodności

Dotyczy: Usługa Intune w witrynie Azure Portal

Jeśli do zarządzania użytkownikami końcowymi komputerów Mac Twoja organizacja używa narzędzia [Jamf Pro](https://www.jamf.com), zastosowanie zasad zgodności usługi Microsoft Intune i dostępu warunkowego usługi Azure Active Directory zapewnia, że urządzenia w organizacji będą zgodne.

## <a name="prerequisites"></a>Wymagania wstępne

Aby skonfigurować dostęp warunkowy przy użyciu narzędzia Jamf Pro, wymagane są następujące elementy:

- Program Jamf Pro 10.1.0 lub nowsza wersja
- [Aplikacja Portal firmy dla systemu macOS](https://aka.ms/macoscompanyportal)
- Urządzenia z systemem macOS (OS X 10.11 Yosemite lub nowszy)

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

8. Na stronie **Uprawnienia interfejsu API** wybierz pozycję **Wyraź zgodę administratora dla Microsoft** i kliknij **Tak**.  

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
