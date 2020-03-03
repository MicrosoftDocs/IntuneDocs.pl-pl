---
title: Konfigurowanie rozwiązania Wandera Mobile Threat Protection za pomocą usługi Intune
titleSuffix: Intune on Azure
description: Jak skonfigurować rozwiązanie Wandera Mobile Threat Protection za pomocą usługi Microsoft Intune w celu kontrolowania dostępu urządzeń przenośnych do zasobów firmy.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/18/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: d90e3757ced90bea21e4033b6baa93bfa201b1f2
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514221"
---
# <a name="integrate-wandera-mobile-threat-protection-with-intune"></a>Integracja rozwiązania Wandera Mobile Threat Protection z usługą Intune  

Aby zintegrować rozwiązanie Wandera Mobile Threat Defense z usługą Intune, wykonaj kroki opisane poniżej.  

> [!NOTE]
> Ten dostawca rozwiązania Mobile Threat Defense nie jest obsługiwany w przypadku niezarejestrowanych urządzeń.

## <a name="before-you-begin"></a>Przed rozpoczęciem  

Przed rozpoczęciem procesu integracji rozwiązania Wandera z usługą Intune, upewnij się, że zostały spełnione następujące wymagania wstępne:
- Subskrypcja usługi Microsoft Intune  
- Poświadczenia administratora usługi Azure Active Directory umożliwiające przyznanie następujących uprawnień:  
  - Logowanie i odczyt profilu użytkownika  
  - Dostęp do katalogu jako zalogowany użytkownik  
  - Odczyt danych katalogu  
  - Wysyłanie informacji o urządzeniu do usługi Intune  

- Subskrypcja rozwiązania Wandera:
  - Co najmniej jedno konto Wandera z licencją dla połączenia EMM Connect  
  - Konto z uprawnieniami superadministratora w rozwiązaniu Wandera  
 
### <a name="wandera-mobile-threat-defense-app-authorization"></a>Autoryzacja aplikacji Wandera Mobile Threat Defense  

Proces autoryzacji aplikacji Wandera Mobile Threat Defense:  
- Zezwól usłudze Wandera Mobile Threat Defense na przekazywanie informacji związanych z kondycją urządzenia z powrotem do usługi Intune.  
- Usługa Wandera synchronizuje się z członkostwem grupy rejestracji usługi Azure AD, aby wypełnić bazę danych urządzenia.  
- Zezwól portalowi administracyjnemu Wandera RADAR na używanie logowania jednokrotnego usługi Azure AD.  
- Zezwól aplikacji Wandera Mobile Threat Defense na logowanie przy użyciu logowania jednokrotnego usługi Azure AD.  


## <a name="set-up-wandera-mobile-threat-defense-integration"></a>Konfigurowanie integracji rozwiązania Wandera Mobile Threat Defense  
Konfiguracja połączenia *EMM Connect* dla rozwiązania Wandera wymaga jednorazowego procesu konfiguracji, który jest przeprowadzany zarówno w usłudze Intune, jak i w konsoli rozwiązania Wandera. Proces konfiguracji trwa około 15 minut. Konfigurację można wykonać bez koordynacji z kontem technicznym lub przedstawicielem pomocy technicznej firmy Wandera.  

### <a name="enable-support-for-wandera-in-intune"></a>Włączanie obsługi rozwiązania Wandera w usłudze Intune

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Administracja dzierżawą** > **Łączniki i tokeny** > **Mobile Threat Defense** > **Dodaj**.
3. Na stronie **Dodawanie łącznika** użyj listy rozwijanej i wybierz pozycję **Wandera**. Następnie wybierz pozycję **Utwórz**.  
4. W okienku usługi Mobile Threat Defense wybierz łącznik **Wandera** MTD z listy łączników, aby otworzyć okienko *Edytuj łącznik*. Wybierz pozycję **Open the Wandera admin console** (Otwórz konsolę administracyjną rozwiązania Wandera), aby otworzyć konsolę administracyjną rozwiązania Wandera o nazwie [RADAR](https://radar.wandera.com/login), i zaloguj się. 
5. W konsoli rozwiązania Wandera wybierz pozycję **Settings** > **EMM Integration** (Ustawienia > Integracja EMM), a następnie wybierz kartę **EMM Connect**. Użyj listy rozwijanej *EMM Vendor* (Dostawca EMM) i wybierz pozycję *Microsoft Intune*.

   ![Wybierz pozycję Intune](./media/wandera-mtd-connector-integration/set-up-intune-in-radar.png)

6. Wybierz pozycję **Grant permissions** (Udziel uprawnień), aby otworzyć połączenie z portalem usługi Intune. Zaloguj się przy użyciu poświadczeń administratora usługi Intune, zaznacz pole wyboru, a następnie **zaakceptuj** żądanie dotyczące uprawnień.  

   ![Zaakceptuj uprawnienia](./media/wandera-mtd-connector-integration/permissions.png) 

7. Rozwiązanie Wandera zakończy połączenie i ponownie wyświetli konsolę administracyjną RADAR. Powtórz ten proces, aby **udzielić** dostępu do dodatkowych konfiguracji zgodnie z potrzebami.  

   ![Integracje i uprawnienia](./media/wandera-mtd-connector-integration/integrations-and-permissions.png) 

8. W konsoli RADAR skopiuj nazwę grupy **SyncOnly**, która jest widoczna poniżej pozycji **EMM Label** (Etykieta EMM). Użyjesz tej nazwy, aby skonfigurować grupę w usłudze Intune w celu synchronizacji z rozwiązaniem Wandera.

   ![Grupa synchronizacji](./media/wandera-mtd-connector-integration/sync-group-name.png) 

9. Wróć do konsoli usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) i edytuj łącznik Wandera MTD. Dla dostępnych przełączników ustaw wartość **Wł.** i kliknij przycisk **Zapisz**, aby zapisać konfigurację.  

   ![Włączanie rozwiązania Wandera](./media/wandera-mtd-connector-integration/enable-wandera.png) 

Usługa Intune i rozwiązanie Wandera są teraz połączone.  

## <a name="configure-the-wandera-applications-and-synchronization-group"></a>Konfigurowanie grupy synchronizacji i aplikacji Wandera  
Aby wdrożyć rozwiązanie Wandera, dodasz aplikacje mobilne Wandera dla platform, których używasz (systemy iOS i Android), do usługi Intune i przypiszesz je do określonej grupy w celu synchronizacji: do grupy *SyncOnly*. 

Poniższe sekcje i procedury przeprowadzą Cię przez ten proces.

Aby uzyskać więcej informacji na temat tego procesu po stronie rozwiązania Wandera, zaloguj się do konsoli [RADAR](https://radar.wandera.com/login) rozwiązania Wandera. Wybierz pozycję **Ustawienia** > **Integracja EMM**, wybierz kartę **Wypychanie aplikacji**, a następnie wybierz pozycję **Microsoft Intune**. Karta Wypychanie aplikacji zostanie zaktualizowana za pomocą instrukcji specyficznych dla usługi Intune.  

### <a name="add-the-wandera-apps"></a>Dodawanie aplikacji Wandera  
Utwórz aplikacje klienckie w usłudze Intune, aby wdrożyć aplikację Wandera na urządzeniach z systemami Android i iOS/iPadOS. Zobacz [Dodawanie aplikacji MTD](mtd-apps-ios-app-configuration-policy-add-assign.md), aby zapoznać się z procedurami i niestandardowymi szczegółami, które są specyficzne dla aplikacji Wandera.  

Po utworzeniu aplikacji wróć tutaj, aby utworzyć grupę synchronizacji i przypisać aplikacje.

### <a name="create-the-synchronization-group-and-assign-the-apps"></a>Tworzenie grupy synchronizacji i przypisywanie aplikacji

1. Pobierz nazwę grupy **SyncOnly**, która jest widoczna poniżej pozycji **EMM Label** (Etykieta EMM) w konsoli RADAR rozwiązania Wandera. Być może ta nazwa została zapisana w kroku 7 podczas [włączania obsługi rozwiązania Wandera w usłudze Intune](#enable-support-for-wandera-in-intune). Użyj tej nazwy jako nazwy grupy w usłudze Intune na potrzeby synchronizacji rozwiązania Wandera.  

2. W centrum administracyjnym programu Endpoint Manager przejdź do pozycji **Grupy**, a następnie wybierz pozycję **Nowa grupa**. Określ następujące ustawienia, aby skonfigurować grupę synchronizacji do użycia przez rozwiązanie Wandera:
   - **Typ grupy**: **Zabezpieczenia**
   - **Nazwa grupy**: Określ nazwę **SyncOnly** uzyskaną z konsoli administracyjnej RADAR rozwiązania Wandera.

   ![konfigurowanie grupy synchronizacji](./media/wandera-mtd-connector-integration/configure-sync-group.png)

3. Wybierz **członków** i przypisz grupy zawierające urządzenia z systemami Android i iOS/iPadOS, których chcesz użyć z rozwiązaniem Wandera.

4. Wybierz pozycję **Utwórz**, aby zapisać grupę.

Aby uzyskać więcej informacji, zobacz [Wdrażanie aplikacji](../apps/apps-deploy.md)

### <a name="assign-the-wandera-apps-to-the-synchronization-group"></a>Przypisywanie aplikacji Wandera do grupy synchronizacji  
Powtórz poniższą procedurę dla aplikacji Wandera utworzonej dla systemu iOS/iPadOS i dla systemu Android.

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Aplikacje** > **Wszystkie aplikacje** i wybierz aplikację Wandera.
3. Wybierz pozycję **Przypisania**, a następnie pozycję **Dodaj grupę**.  
4. W okienku *Dodaj grupę* dla elementu *Typ przypisania* wybierz pozycję **Wymagane**.
5. Wybierz pozycję **Objęte grupy**, a następnie pozycję **Wybierz grupy do uwzględnienia**. Określ grupę utworzoną na potrzeby synchronizacji rozwiązania Wandera, a następnie kliknij pozycję **Wybierz** > **OK** > **OK**. Wybierz przycisk **Zapisz**, aby ukończyć przypisywanie grupy. 

## <a name="next-steps"></a>Następne kroki  
Teraz, gdy integracja została skonfigurowana, możesz zacząć konfigurować zasady i zaawansowany dostęp warunkowy oraz wyświetlać raporty w konsoli administracyjnej rozwiązania Wandera. Aby dowiedzieć się więcej na temat konfigurowania rozwiązania Wandera i zarządzania nim, zobacz [przewodnik wprowadzający centrum pomocy technicznej](https://radar.wandera.com/?return_to=https://wandera.force.com/Customer/s/getting-started) w dokumentacji rozwiązania Wandera. 
