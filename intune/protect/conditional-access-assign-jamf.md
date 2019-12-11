---
title: Zasady zgodności urządzeń dla urządzeń Jamf
titleSuffix: Microsoft Intune
description: Stosuj zasady zgodności usługi Microsoft Intune z dostępem warunkowym usługi Azure Active Directory, aby pomóc zabezpieczać urządzenia zarządzane przez narzędzie Jamf.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/18/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c87fd2bd-7f53-4f1b-b985-c34f2d85a7bc
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b09b30fd32caace9ed3259350c01548d5e5fae15
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "74161592"
---
# <a name="enforce-compliance-on-macs-managed-with-jamf-pro"></a>Wymuszanie zgodności na urządzeniach Mac zarządzanych za pomocą narzędzia Jamf Pro

W przypadku [integracji narzędzia Jamf Pro z usługą Intune](conditional-access-integrate-jamf.md) można użyć zasad dostępu warunkowego, aby wymusić zgodność urządzeń Mac z wymaganiami organizacji.  Ten artykuł pomoże Ci w następujących zadaniach:  

- Tworzenie zasad dostępu warunkowego.
- Konfigurowanie narzędzia Jamf Pro, aby wdrożyć aplikację Intune — Portal firmy na urządzeniach zarządzanych za pomocą rozwiązania Jamf.
- Konfigurowanie urządzeń w celu rejestracji w usłudze Azure AD wykonywanej, gdy użytkownik urządzenia zaloguje się do aplikacji Portal firmy uruchamianej z poziomu aplikacji samoobsługowej Jamf. Rejestracja urządzenia ustanawia tożsamość w usłudze Azure AD, która umożliwia ocenę urządzenia przez zasady dostępu warunkowego w celu uzyskania dostępu do zasobów firmy.  
 
Procedury opisane w tym artykule wymagają dostępu zarówno do konsoli usługi Intune, jak i konsoli Jamf Pro.

## <a name="set-up-device-compliance-policies-in-intune"></a>Konfigurowanie zasad zgodności urządzeń w usłudze Intune

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Wybierz pozycję **Urządzenia** > **Zasady zgodności**. Jeśli używasz wcześniej utworzonych zasad, wybierz te zasady w konsoli, a następnie przejdź do następnego kroku tej procedury. Aby utworzyć nowe zasady, wybierz pozycję **Utwórz zasady**, a następnie określ szczegóły zasad, ustawiając pole *Platforma* na wartość **macOS**. Skonfiguruj *Ustawienia* i *Akcje w przypadku niezgodności*, aby spełnić wymagania organizacyjne, a następnie wybierz pozycję **Utwórz**, aby zapisać zasady.

3. W okienku *Przegląd* zasad wybierz pozycję **Przypisania**. Użyj dostępnych opcji, aby skonfigurować, którzy użytkownicy i które grupy zabezpieczeń usługi Azure Active Directory (Azure AD) mają otrzymywać te zasady. Integracja narzędzia Jamf z usługą Intune nie obsługuje zasad zgodności, które są przeznaczone dla grup urządzeń.

4. Po wybraniu opcji **Zapisz** zasady są wdrażane dla użytkowników.  

Wdrażane zasady są przeznaczone dla urządzeń, które są używane przez przypisanych użytkowników. Te urządzenia są oceniane pod kątem zgodności. Zgodne urządzenia są oznaczone jako zgodne w przypadku ustawienia „*Wymagaj, aby urządzenie było oznaczone jako zgodne*” w usłudze Azure AD.  

> [!NOTE]
> Aby zachować zgodność z przepisami, usługa Intune wymaga pełnego szyfrowania dysku.

## <a name="deploy-the-company-portal-app-for-macos-in-jamf-pro"></a>Wdrażanie aplikacji Portal firmy dla systemu macOS w narzędziu Jamf Pro

Utwórz w narzędziu Jamf Pro zasady w celu wdrożenia aplikacji Intune — Portal firmy. Te zasady powodują wdrożenie aplikacji Portal firmy w taki sposób, aby była dostępna w funkcji samoobsługi narzędzia Jamf. Utwórz te zasady przed utworzeniem w narzędziu Jamf Pro zasad wymagających, aby użytkownicy rejestrowali urządzenia w usłudze Azure AD.  

Aby wykonać poniższą procedurę, musisz mieć dostęp do urządzenia z systemem macOS i portalu Jamf Pro. 

### <a name="to-deploy-the-company-portal-app"></a>Aby wdrożyć aplikację Portal firmy  

1. Na urządzeniu z systemem macOS pobierz bieżącą wersję [aplikacji Portal firmy dla systemu macOS](https://go.microsoft.com/fwlink/?linkid=862280), ale nie instaluj jej. Potrzebna jest tylko kopia aplikacji, aby można było przekazać ją do narzędzia Jamf Pro.  

2. Otwórz program Jamf Pro i przejdź do opcji **Zarządzanie komputerem** > **Pakiety**.

3. Utwórz nowy pakiet z aplikacją Portal firmy dla systemu macOS, a następnie wybierz przycisk **Zapisz**.

4. Otwórz opcję **Komputery** > **Zasady**, a następnie wybierz pozycję **Nowy**.

5. Użyj ładunku **Ogólne**, aby skonfigurować ustawienia zasad. Te ustawienia powinny być następujące:
   - Wyzwalacz: wybierz opcję **Ukończenie rejestracji** i **Cykliczne zaewidencjonowanie**
   - Częstotliwość wykonywania: wybierz opcję **Raz na komputerze**

6. Wybierz ładunek **Pakiety** i kliknij przycisk **Konfiguruj**.

7. Aby wybrać pakiet z aplikacją Portal firmy, kliknij przycisk **Dodaj**.

8. Wybierz opcję **Zainstaluj** z menu podręcznego **Akcje**.
9. Skonfiguruj ustawienia pakietu.

10. Wybierz kartę **Zakres**, aby określić, na których komputerach ma być zainstalowana aplikacja Portal firmy. Wybierz pozycję **Zapisz**. W urządzeniach objętych zakresem zasady zostaną uruchomione przy następnym wystąpieniu na komputerze wybranego wyzwalacza i spełnieniu kryteriów ładunku **Ogólne**.

## <a name="create-a-policy-in-jamf-pro-to-have-users-register-their-devices-with-azure-active-directory"></a>Tworzenie zasad narzędzia Jamf Pro, które umożliwią użytkownikom rejestrowanie swoich urządzeń w usłudze Azure Active Directory  

Po [wdrożeniu aplikacji Portal firmy](conditional-access-assign-jamf.md#deploy-the-company-portal-app-for-macos-in-jamf-pro) dla systemu macOS za pośrednictwem funkcji samoobsługi narzędzia Jamf Pro można utworzyć zasady narzędzia Jamf Pro, które rejestrują urządzenie użytkownika w usłudze Azure AD. 

Rejestracja urządzenia wymaga od użytkownika urządzenia ręcznego wybrania aplikacji Intune — Portal firmy z poziomu funkcji samoobsługi narzędzia Jamf. Zalecamy [skontaktowanie się z użytkownikami końcowymi](../fundamentals/end-user-educate.md) za pośrednictwem poczty e-mail, powiadomień narzędzia Jamf Pro lub innych metod używanych w organizacji, aby poinstruować ich, że powinni wykonać tę akcję w celu zarejestrowania swoich urządzeń. 

> [!WARNING]
> Uruchomienie aplikacji Portal firmy ręcznie (np. z poziomu folderów Aplikacje lub Pobrane pliki) nie spowoduje zarejestrowania urządzenia. Jeśli użytkownik urządzenia uruchomi Portal firmy ręcznie, zobaczy ostrzeżenie **„AccountNotOnboarded”** .

### <a name="to-create-the-registration-policy"></a>Aby utworzyć zasady rejestracji  

1. W programie Jamf Pro przejdź do opcji **Komputery** > **Zasady** i utwórz nowe zasady na potrzeby rejestracji urządzeń.

2. Skonfiguruj ładunek **Integracja z usługą Intune**, łącznie z określeniem wyzwalacza i częstotliwości wykonywania.

3. Wybierz kartę **Zakres** i ustaw zakres zasad dla wszystkich urządzeń docelowych.

4. Wybierz kartę **Samoobsługa**, aby udostępnić zasady w funkcji samoobsługi narzędzia Jamf. Dołącz zasady do kategorii **Zgodność urządzeń**. Kliknij polecenie **Zapisz**.

## <a name="validate-intune-and-jamf-integration"></a>Sprawdzanie poprawności integracji usługi Intune i narzędzia Jamf  

Użyj konsoli Jamf Pro, aby potwierdzić, że komunikacja między narzędziem Jamf Pro i usługą Microsoft Intune przebiega pomyślnie. 

- W Jamf Pro przejdź do pozycji **Ustawienia** > **Zarządzanie globalne** > **Integracja z usługą Microsoft Intune**, a następnie wybierz pozycję **Test**.

    W konsoli programu zostanie wyświetlony komunikat o powodzeniu lub niepowodzeniu próby połączenia.  

Jeśli test połączenia z konsoli Jamf Pro zakończy się niepowodzeniem, sprawdź konfigurację narzędzia Jamf. 


## <a name="removing-a-jamf-managed-device-from-intune"></a>Usuwanie urządzenia zarządzanego za pomocą narzędzia Jamf z usługi Intune

Aby usunąć urządzenie zarządzane przez narzędzie Jamf, otwórz centrum administracyjne programu Microsoft Endpoint Manager i wybierz pozycję **Urządzenia** > **Wszystkie urządzenia**, wybierz urządzenie, a następnie wybierz pozycję **Usuń**.  Zbiorcze usuwanie urządzeń można włączyć, zaznaczając wiele urządzeń i klikając pozycję **Usuń**.

Zapoznaj się z informacjami na temat [usuwania urządzenia zarządzanego za pomocą narzędzia Jamf w dokumentacji programu Jamf Pro](https://www.jamf.com/jamf-nation/articles/80/unmanaging-computers-while-preserving-their-inventory-information). Możesz również wypełnić bilet pomocy technicznej dla [obsługi Jamf](https://www.jamf.com/support/) w celu uzyskania dodatkowej pomocy. 

## <a name="next-steps"></a>Następne kroki

- [Conditional Access in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) (Dostęp warunkowy w usłudze Azure Active Directory)
- [Wprowadzenie do dostępu warunkowego w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)
