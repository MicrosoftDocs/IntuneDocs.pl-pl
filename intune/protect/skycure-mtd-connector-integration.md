---
title: Konfigurowanie integracji z programem firmy Symantec w usłudze Microsoft Intune
titleSuffix: Microsoft Intune
description: Sposób konfigurowania rozwiązania Symantec Endpoint Protection Mobile za pomocą usługi Microsoft Intune w celu kontrolowania dostępu urządzeń przenośnych do zasobów firmy.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 359448d9-2384-42ac-a21c-a25148c20a7b
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f6c28b222307ee20e3198033ef6aa4af3d756e7e
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72681316"
---
# <a name="set-up-symantec-endpoint-protection-mobile-integration-with-intune"></a>Konfigurowanie integracji programu Symantec Endpoint Protection Mobile w usłudze Intune

Wykonaj poniższe kroki, aby zintegrować rozwiązanie Symantec Endpoint Protection Mobile (SEP Mobile) z usługą Intune. Aby uzyskać możliwości logowania jednokrotnego, do usługi Azure AD należy dodać aplikacje SEP Mobile.

> [!NOTE]
> Ten dostawca rozwiązania Mobile Threat Defense nie jest obsługiwany w przypadku niezarejestrowanych urządzeń.

## <a name="before-you-begin"></a>Przed rozpoczęciem

### <a name="azure-ad-account-used-to-integrate-intune-and-sep-mobile"></a>Konto usługi Azure AD używane do integracji usługi Intune i programu SEP Mobile

- Przed rozpoczęciem procesu konfiguracji podstawowej programu SEP Mobile upewnij się, że konto usługi Azure AD zostało poprawnie skonfigurowane w [konsoli zarządzania programu Symantec Endpoint Protection Mobile](https://aad.skycure.com).
- Konto usługi Azure AD musi być kontem administratora globalnego, aby można było przeprowadzić integrację.
### <a name="network-setup"></a>Konfiguracja sieci

Aby sprawdzić, czy sieć została prawidłowo skonfigurowana na potrzeby integracji z instalacją programu SEP Mobile, można zapoznać się z artykułem firmy Symantec [Setting up your network configuration](https://portal.skycure.com/articles/Documentation/Setting-up-your-network-configuration-26-8-2016) (Przeprowadzanie konfiguracji sieci).

### <a name="full-integration-vs-read-only"></a>Pełna integracja a integracja tylko do odczytu

Program SEP Mobile obsługuje dwa tryby integracji z usługą Intune:

- **Integracja tylko do odczytu (konfiguracja podstawowa):** dokonuje tylko inwentaryzacji urządzeń z usługi Azure Active Directory i umieszcza je w konsoli zarządzania programu Symantec Endpoint Protection Mobile.
<br>
  - Jeśli opcje **Przekaż kondycję i ryzyko urządzeń do usługi Intune** oraz **Zgłoś również zdarzenia związane z bezpieczeństwem do usługi Intune** nie są zaznaczone w konsoli zarządzania programu Symantec Endpoint Protection Mobile, integracja jest tylko do odczytu i w związku z tym nigdy nie spowoduje zmiany stanu urządzeń (zgodnych lub niezgodnych) w usłudze Intune.
<br></br>
- **Pełna integracja:** umożliwia raportowanie do usługi Intune ryzyka i szczegółowych informacji dotyczących incydentów zabezpieczeń na urządzeniach w programie SEP Mobile, co powoduje utworzenie dwukierunkowej komunikacji między obiema usługami w chmurze.

### <a name="how-are-the-sep-mobile-apps-used-with-azure-ad-and-intune"></a>Jak aplikacje programu SEP Mobile są używane w usługach Azure AD i Intune?

- **Aplikacja systemu iOS:** umożliwia użytkownikom końcowym logowanie się do usługi Azure AD za pomocą aplikacji dla systemu iOS.

- **Aplikacja systemu Android:** umożliwia użytkownikom końcowym logowanie się do usługi Azure AD za pomocą aplikacji dla systemu Android.

- **Aplikacja zarządzania:** jest to wielodostępna aplikacja SEP Mobile usługi Azure AD umożliwiająca komunikację typu Service to Service z usługą Intune.

## <a name="to-set-up-the-read-only-integration-between-intune-and-sep-mobile"></a>Aby skonfigurować integrację tylko do odczytu między usługą Intune i programem SEP Mobile

> [!IMPORTANT]
> Poświadczenia administratora programu SEP Mobile muszą składać się z konta e-mail należącego do prawidłowego użytkownika w usłudze Azure Active Directory. W przeciwnym razie logowanie zakończy się niepowodzeniem. Program SEP Mobile używa usługi Azure Active Directory do uwierzytelniania swojego administratora za pomocą funkcji logowania jednokrotnego.

1. Przejdź do [konsoli zarządzania programu Symantec Endpoint Protection Mobile](https://aad.skycure.com).

2. Wprowadź **poświadczenia administratora programu SEP Mobile**, a następnie wybierz pozycję **Kontynuuj**.

3. Przejdź do pozycji **Ustawienia** i w obszarze **Integracja z usługą Intune** wybierz pozycję **Konfiguracja podstawowa**.

4. Obok pozycji **Aplikacja systemu iOS** wybierz pozycję **Dodaj do usługi Active Directory**.

    ![Obraz przedstawiający konsolę zarządzania programu Symantec Endpoint Protection Mobile](./media/skycure-mtd-connector-integration/symantec-portal-basic-add.png)

5. Po otwarciu strony logowania wprowadź swoje poświadczenia usługi Intune, a następnie wybierz pozycję **Akceptuj**.

    ![Obraz przedstawiający monit logowania usługi Intune aplikacji systemu iOS](./media/skycure-mtd-connector-integration/symantec-portal-basic-accept.png)

6. Po dodaniu aplikacji do usługi Azure AD zostanie wyświetlona informacja o pomyślnym dodaniu aplikacji.

    ![Obraz przedstawiający ekran końcowy aplikacji systemu iOS](./media/skycure-mtd-connector-integration/symantec-portal-basic-added.png)

7. Powtórz te kroki dla aplikacji **SEP Mobile Android** i **Zarządzanie**.

### <a name="add-an-azure-ad-security-group-into-sep-mobile"></a>Dodawanie grupy zabezpieczeń usługi Azure AD do programu SEP Mobile

Należy dodać grupę zabezpieczeń usługi Azure AD, która zawiera wszystkie urządzenia z uruchomionym programem SEP Mobile.

- Wprowadź i wybierz wszystkie grupy zabezpieczeń urządzeń z uruchomionym programem SEP Mobile, a następnie zapisz zmiany.

    ![Obraz przedstawiający grupy użytkowników dla aplikacji SEP Mobile](./media/skycure-mtd-connector-integration/symantec-portal-basic-groups.png)

Program SEP Mobile synchronizuje urządzenia z uruchomioną usługą Mobile Threat Defense z grupami zabezpieczeń usługi Azure AD.

![Obraz przedstawiający konfigurację grupy zabezpieczeń w konsoli zarządzania programu SEP Mobile](./media/skycure-mtd-connector-integration/symantec-portal-basic-status.png)

## <a name="to-set-up-the-full-integration-between-intune-and-sep-mobile"></a>Aby skonfigurować pełną integrację między usługą Intune i programem SEP Mobile

### <a name="retrieve-the-directory-id-in-azure-ad"></a>Pobieranie identyfikatora katalogu w usłudze Azure AD

1. Zaloguj się do [portalu Azure](https://portal.azure.com).

2. W polu wyszukiwania wpisz „Active Directory”, a następnie wybierz pozycję **Azure Active Directory**.

3. Wybierz pozycję **Właściwości**.

4. Obok pozycji **Identyfikator katalogu** wybierz ikonę kopiowania i wklej identyfikator w bezpiecznym miejscu. Będziesz potrzebować tego identyfikatora w kolejnym kroku.

    ![Obraz przedstawiający identyfikator katalogu w witrynie Azure Portal](./media/skycure-mtd-connector-integration/symantec-azure-portal-directory-ID.png)

### <a name="optional-create-a-dedicated-security-group-for-devices-that-need-to-run-the-sep-mobile-apps"></a>(Opcjonalnie) Tworzenie dedykowanej grupy zabezpieczeń dla urządzeń, które muszą uruchamiać aplikacje SEP Mobile
1. W witrynie [Azure Portal](https://portal.azure.com)w obszarze **Zarządzanie** wybierz pozycję **Użytkownicy i grupy**, a następnie wybierz pozycję **Wszystkie grupy**.

2. Wybierz przycisk **Dodaj**. Wpisz **nazwę** grupy. W obszarze **Typ członkostwa** wybierz pozycję **Przypisane**.

3. W bloku **Członkowie** wybierz członków grupy, a następnie wybierz przycisk **Wybierz**.

4. W bloku **Grupa** wybierz pozycję **Utwórz**.

### <a name="set-up-the-integration-between-symantec-endpoint-protection-mobile-and-intune"></a>Konfigurowanie integracji programu Symantec Endpoint Protection Mobile i usługi Intune

1. Przejdź do [konsoli zarządzania programu Symantec Endpoint Protection Mobile](https://aad.skycure.com).

2. Wprowadź **poświadczenia administratora programu SEP Mobile**, a następnie wybierz pozycję **Kontynuuj**.

3. Przejdź kolejno do pozycji **Ustawienia** > **Integracje** > **Intune** > **Wybór integracji EMM** (sekcja).

4. W polu **Identyfikator katalogu** wklej identyfikator skopiowany z usługi Azure Active Directory w poprzedniej sekcji i zapisz ustawienia.

    ![Obraz przedstawiający identyfikator katalogu w portalu programu SEP Mobile](./media/skycure-mtd-connector-integration/symantec-portal-directory-ID.png)

5. Przejdź kolejno do pozycji **Ustawienia** > **Integracje** > **Intune** > **Konfiguracja podstawowa** (sekcja).

6. Obok pozycji **Aplikacja systemu iOS** wybierz przycisk **Dodaj do usługi Active Directory**.

    ![Obraz przedstawiający dodawanie aplikacji systemu iOS do usługi Active Directory](./media/skycure-mtd-connector-integration/symantec-portal-basic-add.png)

7. Zaloguj się przy użyciu poświadczeń usługi Azure Active Directory dla konta usługi Office 365, które zarządza katalogiem.

8. Wybierz przycisk **Akceptuj**, aby dodać aplikację systemu iOS dla programu SEP Mobile do usługi Azure Active Directory.

    ![Obraz przedstawiający przycisk Akceptuj](./media/skycure-mtd-connector-integration/symantec-portal-basic-accept.png)

9. Powtórz ten sam proces dla **aplikacji systemu Android** i **aplikacji zarządzania**.

10. Wybierz wszystkie grupy użytkowników, które muszą uruchamiać aplikacje SEP Mobile, na przykład utworzoną wcześniej grupę zabezpieczeń.

    ![Obraz przedstawiający grupy użytkowników dla aplikacji SEP Mobile](./media/skycure-mtd-connector-integration/symantec-portal-basic-groups.png)

11. Program SEP Mobile synchronizuje urządzenia w wybranych grupach i rozpoczyna raportowanie informacji do usługi Intune. Te dane można wyświetlić w sekcji pełnej integracji. Przejdź kolejno do pozycji **Ustawienia** > **Integracje** > **Intune** > **Pełna integracja** (sekcja).

     ![Obraz przedstawiający ukończoną pełną integrację z programem SEP Mobile](./media/skycure-mtd-connector-integration/symantec-portal-basic-status.PNG)
## <a name="next-steps"></a>Następne kroki

[Konfigurowanie aplikacji SEP Mobile](mtd-apps-ios-app-configuration-policy-add-assign.md)
