---
title: "Role Intune (RBAC) usługi Microsoft Intune"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: dowiedz się, jak kontrola dostępu oparta na rolach pozwala określić, kto może wykonywać akcje i wprowadzać zmiany."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 04/26/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ca3de752-3caa-46a4-b4ed-ee9012ccae8e
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: deea78dcea9ade031441bf12b388a862235a8e9c
ms.openlocfilehash: e60edd86289e0fca2aa03660d8ce782e373c0236
ms.lasthandoff: 03/15/2017


---

# <a name="intune-roles-rbac-for-microsoft-intune"></a>Role Intune (RBAC) usługi Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Mówiąc najprościej, **role** usługi Intune pozwalają decydować, kto może wykonywać w usłudze Intune różne akcje oraz kogo te akcje będą dotyczyć. Możesz użyć wbudowanych ról, które obejmują kilka typowych scenariuszy usługi Intune, lub utworzyć własne.

Rolę definiują następujące właściwości:

- **Definicja** — nazwa roli i uprawnienia, jakie rola uwzględnia.
- **Członkowie** — użytkownik lub grupa użytkowników, którzy otrzymują uprawnienia.
- **Zakres** — użytkownicy lub urządzenia, którymi może zarządzać określona osoba (członek).
- **Przypisanie** — po skonfigurowaniu definicji, członków i zakresu następuje przypisanie roli.

## <a name="built-in-roles"></a>Wbudowane role

Poniższe role są wbudowane w usługę Intune i można je dostosować lub przypisać je do grup bez dalszej konfiguracji.

- **Administrator usługi Intune** — administrator ma pełne uprawnienia w zakresie wszystkich akcji w usłudze Intune.
- **Menedżer aplikacji** — zarządzanie aplikacjami i profilami oraz ich wdrażanie.
- **Menedżer zasad konfiguracji** — zarządzanie ustawieniami i profilami konfiguracji oraz ich wdrażanie.
- **Pracownik punktu pomocy** — wykonywanie zadań zdalnych i wyświetlanie informacji o użytkownikach i urządzeniach.
- **Operator tylko do odczytu** — wyświetlanie w portalu usługi Intune informacji bez możliwości wprowadzania w nich zmian.


## <a name="custom-roles"></a>Role niestandardowe

Jeśli żadna z wbudowanych ról nie spełnia Twoich potrzeb, możesz utworzyć własną rolę, wybierając ustawienia obejmujące wiele możliwości usługi Intune. Lista dostępnych ustawień znajduje się w dalszej części tego tematu.

### <a name="example"></a>Przykład

Zatrudniasz nowego administratora IT, który będzie zapewniał użytkownikom z biura w Londynie pomoc w zakresie wdrażania aplikacji oraz zarządzania nimi. Użytkownicy należą do grupy usługi Azure AD o nazwie **Londyn**. Chcesz mieć pewność, że administrator IT nie może wdrażać aplikacji na urządzeniach użytkowników z innych biur. Wykonujesz następujące czynności:

- Przypisanie wbudowanej roli **Menedżer aplikacji** z następującymi właściwościami:
    - **Członkowie** — wybierz grupę, do której należy administrator IT, który będzie odpowiadał za wdrażanie aplikacji
    - **Zakres** — wybierz grupę **Londyn** usługi Azure AD.

    >[!IMPORTANT]
    >Aby możliwe było tworzenie, edytowanie i przypisywanie ról, konto musi mieć w usłudze Azure AD jedno z następujących uprawnień:
    >- **Globalny administrator usługi AAD**
    >- **Administrator usługi Intune**

### <a name="how-to-create-a-custom-role"></a>Jak utworzyć rolę niestandardową

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Role Intune**.
![Obciążenie Kontrola dostępu](./media/axxess-control.png)
1. W bloku **Role** obciążenia **Kontrola dostępu** wybierz pozycję **Dodaj niestandardowe**.
2. W bloku **Dodaj rolę niestandardową** wprowadź nazwę i opis nowej roli, a następnie kliknij pozycję **Uprawnienia**.
3. W bloku **Uprawnienia** wybierz uprawnienia do użycia w ramach tej roli. Dla ułatwienia możesz użyć listy odwołań ustawień ról niestandardowych znajdującej się w dalszej części tego tematu.
4. Gdy wszystko będzie gotowe, kliknij przycisk **OK**.
5. W bloku **Dodaj rolę niestandardową** kliknij pozycję **Utwórz**.

Nowa rola zostanie wyświetlona na liście w bloku **Role**.

## <a name="how-to-assign-a-role"></a>Jak przypisać rolę

1. W bloku **Role** obciążenia **Kontrola dostępu** wybierz rolę wbudowaną lub niestandardową, którą chcesz przypisać.
2. W bloku <*nazwa roli*> — **właściwości** wybierz kolejno pozycje **Zarządzaj** > **Przypisania**. W tym bloku możesz również edytować i usuwać istniejące role.
3. W następnym bloku wybierz pozycję **Przypisz**.
4. W bloku **Przypisania ról** uzupełnij pole **Nazwa** i opcjonalne pole **Opis** odnoszące się do przypisania, po czym wybierz następujące właściwości:
    - **Członkowie** — wybierz grupę, do której należy użytkownik, któremu chcesz nadać uprawnienia.
    - **Zakres** — wybierz grupę, do której należą użytkownicy, którymi będzie mógł zarządzać wskazany wcześniej członek.
5. Gdy wszystko będzie gotowe, kliknij przycisk **OK**.

Nowe przypisanie zostanie wyświetlone na liście przypisań.

## <a name="custom-role-settings-reference"></a>Odwołania ustawień ról niestandardowych

Podczas tworzenia roli niestandardowej można skonfigurować co najmniej jedno z następujących ustawień:

### <a name="device-configurations"></a>Konfiguracja urządzenia

|||
|-|-|
|**Przypisanie**|Przypisywanie profilów urządzeń do grup.|
|**Utworzenie**|Tworzenie profilów urządzeń.|
|**Usuwanie**|Usuwanie profilów urządzeń.|
|**Odczyt**|Odczyt profilów urządzeń i ich właściwości.|
|**Aktualizacja**|Aktualizowanie istniejących profilów urządzeń.|

### <a name="managed-apps"></a>Aplikacje zarządzane

|||
|-|-|
|**Przypisanie**|Przypisywanie zarządzanych aplikacji do grup.|
|**Utworzenie**|Dodawanie nowych aplikacji zarządzanych do usługi Intune.|
|**Usuwanie**|Usuwanie aplikacji zarządzanych.|
|**Odczyt**|Odczyt aplikacji zarządzanych i ich właściwości.|
|**Aktualizacja**|Aktualizowanie istniejących aplikacji zarządzanych.|
|**Czyszczenie danych**|Czyszczenie aplikacji zarządzanych z urządzeń.|

### <a name="managed-devices"></a>Urządzenia zarządzane

|||
|-|-|
|**Usuwanie**|Usuwanie urządzeń zarządzanych z usługi Intune.|
|**Odczyt**|Wyświetlenie informacji o urządzeniach zarządzanych w portalu usługi Intune.|
|**Aktualizacja**|Aktualizacja informacji o urządzeniach zarządzanych.|

### <a name="mobile-apps"></a>Aplikacje mobilne

|||
|-|-|
|**Przypisanie**|Przypisywanie aplikacji mobilnych do grup.|
|**Utworzenie**|Dodawanie nowych aplikacji mobilnych do usługi Intune.|
|**Usuwanie**|Usuwanie aplikacji mobilnych.|
|**Odczyt**|Odczyt aplikacji mobilnych i ich właściwości.|
|**Aktualizacja**|Aktualizowanie istniejących aplikacji mobilnych.|

### <a name="organization"></a>Organizacja

|||
|-|-|
|**Odczyt**|Odczyt ustawień dzierżawy.|
|**Aktualizacja**|Aktualizowanie ustawień dzierżawy.|

### <a name="remote-tasks"></a>Zadania zdalne

|||
|-|-|
|**Zastosowanie obejścia blokady aktywacji**|Powoduje usunięcie blokady aktywacji z urządzenia z systemem iOS bez identyfikatora Apple ID i hasła użytkownika. |
|**Wyłączenie trybu zgubienia**|Wyłączenie trybu zgubienia. Na potrzeby trybu zgubienia można określić komunikat i numer telefonu, które będą wyświetlane na ekranie blokady urządzenia.|
|**Włączenie trybu zgubienia**|Włączenie trybu zgubienia. Na potrzeby trybu zgubienia można określić komunikat i numer telefonu, które będą wyświetlane na ekranie blokady urządzenia.|
|**Zlokalizowanie urządzenia**|-|
|**Ponowne uruchomienie teraz**|Powoduje ponowne uruchomienie urządzenia.|
|**Zdalne blokowanie**|Powoduje zablokowanie urządzenia. W celu odblokowania urządzenia jego właściciel musi użyć swojego kodu dostępu.|
|**Resetowanie kodu dostępu**|Generuje dla urządzenia nowy kod dostępu, który zostanie wyświetlony w bloku <device name> — przegląd.|
|**Wycofaj**|Usuwa tylko dane firmy zarządzane przez usługę Intune. Nie usuwa z urządzenia danych osobistych.|
|**Czyszczenie danych**|Przywraca na urządzeniu ustawienia domyślne.|



### <a name="telecom-expenses"></a>Wydatki telekomunikacyjne

|||
|-|-|
|**Odczyt**|Odczyt ustawień usługi Telecom Expense Management (TEM).|
|**Aktualizacja**|Aktualizowanie ustawień usługi Telecom Expense Management (TEM).|

### <a name="terms-and-conditions"></a>Warunki i postanowienia

|||
|-|-|
|**Przypisanie**|Przypisywanie warunków i postanowień do grup.|
|**Utworzenie**|Tworzenie ustawień warunków i postanowień.|
|**Usuwanie**|Usuwanie ustawień warunków i postanowień.|
|**Odczyt**|Odczyt ustawień warunków i postanowień w portalu usługi Intune.|
|**Aktualizacja**|Aktualizowanie ustawień warunków i postanowień.|
