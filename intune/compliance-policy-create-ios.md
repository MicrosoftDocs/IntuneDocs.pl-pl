---
title: Tworzenie zasad zgodności urządzeń z systemem iOS w usłudze Microsoft Intune — Azure | Microsoft Intune
description: Można utworzyć lub skonfigurować zasady zgodności urządzeń w usłudze Microsoft Intune dla urządzeń z systemem iOS, aby wprowadzać konto e-mail, sprawdzać urządzenia z wyłączonymi zabezpieczeniami systemu, sprawdzać minimalne i maksymalne wersje systemu operacyjnego oraz ustawiać ograniczenia haseł, w tym długość hasła i brak aktywności urządzenia.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/14/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 42ce05d2f726147caee198c79db185b87854cffb
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57566152"
---
# <a name="add-a-device-compliance-policy-for-ios-devices-in-intune"></a>Dodawanie zasad zgodności dla urządzeń z systemem iOS w usłudze Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Zasady zgodności urządzeń z systemem iOS w usłudze Intune określają reguły i ustawienia, które urządzenia z systemem iOS muszą spełnić, aby zapewnić zgodność. Gdy zasady zgodności urządzeń są używane z zasadami dostępu warunkowego, można umożliwić lub zablokować dostęp do zasobów firmy. Można również pobrać raporty urządzeń i podjąć akcje w przypadku niezgodności. Zasady zgodności urządzeń są tworzone dla każdej platformy w witrynie Azure Portal usługi Intune. Aby dowiedzieć się więcej na temat zasad zgodności i wymagań wstępnych, zobacz [Wprowadzenie do zasad zgodności urządzeń](device-compliance-get-started.md).

W poniższej tabeli opisano sposób postępowania z niezgodnymi ustawieniami w przypadku, gdy zasady zgodności są używane wraz z zasadami dostępu warunkowego.

---------------------------

| **Ustawienie zasad** | **System iOS 8.0 lub nowszy** |
| --- | --- |
| **Konfiguracja kodu PIN lub hasła** | Skorygowane |
| **Szyfrowanie urządzenia** | Skorygowane (przez ustawienie kodu PIN) |
| **Urządzenie ze złamanymi ograniczeniami lub z odblokowanym dostępem** | Poddane kwarantannie (to nie jest ustawienie)
| **Profil e-mail** | Poddane kwarantannie |
|**Minimalna wersja systemu operacyjnego** | Poddane kwarantannie |
| **Maksymalna wersja systemu operacyjnego** | Poddane kwarantannie |
| **Zaświadczanie o kondycji systemu Windows** | Nie dotyczy |

---------------------------

**Skorygowane** — system operacyjny urządzenia wymusza zgodność. (Na przykład użytkownik jest zmuszony do ustawienia kodu PIN).

**Poddane kwarantannie** — system operacyjny urządzenia nie wymusza zgodności. (Na przykład urządzenie z systemem Android nie zmusza użytkownika do szyfrowania urządzenia). Gdy urządzenie nie jest zgodne, zostaną wykonane następujące akcje:

- Urządzenie zostanie zablokowane, jeśli użytkownik podlega zasadom dostępu warunkowego.
- Portal firmy powiadomi użytkownika o wszelkich problemach ze zgodnością.

## <a name="create-a-device-compliance-policy"></a>Tworzenie zasad zgodności urządzenia

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
4. W polu **Platforma** wybierz opcję **iOS**. 
5. Wybierz opcję **Konfigurowanie ustawień** i wprowadź wartości ustawień **Poczta e-mail**, **Kondycja urządzenia**, **Właściwości urządzenia** i **Zabezpieczenia systemu** opisanych w tym temacie. Po zakończeniu wybierz kolejno przycisk **OK** i pozycję **Utwórz**.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
7. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="email"></a>Poczta e-mail

- **Wymagaj zarządzanego profilu poczty e-mail urządzeń przenośnych**: jeśli ustawisz to wymaganie na wartość Wymagaj, urządzenia, których profil poczty e-mail nie jest zarządzany przez usługę Intune, będą traktowane jako niezgodne. Urządzenie może nie mieć zarządzanego profilu poczty e-mail, gdy nie zostało przekazane właściwemu użytkownikowi docelowemu lub jeśli użytkownik ręcznie skonfigurował na nim konto e-mail.

  Urządzenie jest uznawane za niezgodne w następujących sytuacjach:
  - Profil poczty e-mail jest wdrażany w innej grupie użytkowników niż grupa, której dotyczą zasady zgodności.
  - Użytkownik skonfigurował już na urządzeniu konto e-mail zgodne z profilem poczty e-mail usługi Intune wdrożonym na urządzeniu. Usługa Intune nie może zastąpić profilu określonego przez użytkownika i dlatego nie może nim zarządzać. W celu zapewnienia zgodności użytkownik musi usunąć istniejące ustawienia poczty e-mail. Umożliwi to usłudze Intune zainstalowanie zarządzanego profilu poczty e-mail.

- **Wybierz profil poczty e-mail, który ma być zarządzany przez usługę Intune:** jeśli zaznaczona jest opcja **Konto e-mail musi być zarządzane przez usługę Intune**, kliknij pozycję **Wybierz**, aby określić profil poczty e-mail usługi Intune. Ten profil poczty e-mail musi znajdować się na urządzeniu.

Aby uzyskać szczegółowe informacje na temat profilów poczty e-mail, zobacz artykuł [Konfigurowanie dostępu do firmowej poczty e-mail przy użyciu profilów poczty e-mail w usłudze Microsoft Intune](email-settings-configure.md).

## <a name="device-health"></a>Device health

- **Urządzenia ze zdjętymi zabezpieczeniami systemu**: jeśli włączysz to ustawienie, urządzenia, w przypadku których wykonano jailbreak, nie będą uznawane za zgodne.
- **Wymagaj, aby poziom zagrożenia urządzenia był niższy lub równy podanemu poziomowi zagrożenia urządzenia** (iOS 8.0 lub nowszy): wybierz maksymalny poziom zagrożenia, wykorzystywany podczas oznaczania urządzenia jako niezgodne. Urządzenia, które przekraczają ten poziom zagrożenia, zostaną oznaczone jako niezgodne:
  - **Zabezpieczony**: ta opcja jest najbezpieczniejsza, ponieważ urządzenie nie może mieć żadnych zagrożeń. Jeśli urządzenie zostanie wykryte jako posiadające jakikolwiek poziom zagrożenia, zostanie ono ocenione jako niezgodne.
  - **Niski**: urządzenie jest oceniane jako zgodne, jeśli istnieją tylko zagrożenia niskiego poziomu. Jakiekolwiek zagrożenia wyższego poziomu spowodują, że urządzenie będzie miało status urządzenia niezgodnego.
  - **Średni**: urządzenie jest oceniane jako zgodne, jeśli istniejące zagrożenia są na poziomie niskim lub średnim. W przypadku wykrycia na urządzeniu zagrożeń wysokiego poziomu zostanie ono określone jako niezgodne.
  - **Wysoki**: ta opcja jest najmniej bezpieczna i zezwala na wszystkie poziomy zagrożeń. To ustawienie może być przydatne, jeśli rozwiązanie jest używane tylko na potrzeby raportowania.

## <a name="device-properties"></a>Właściwości urządzenia

- **Wymagana minimalna wersja systemu operacyjnego:** jeśli urządzenie nie spełnia wymagań dotyczących minimalnej wersji systemu operacyjnego, będzie zgłaszane jako niezgodne. Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik może wybrać opcję uaktualnienia urządzenia, co umożliwi korzystanie z zasobów firmy.
- **Dozwolona maksymalna wersja systemu operacyjnego**: jeśli urządzenie korzysta z wersji systemu operacyjnego nowszej niż określona w regule, powoduje to zablokowanie dostępu do zasobów firmy. Następnie użytkownik zostanie poproszony o kontakt z administratorem IT. Do momentu zmiany reguły, aby dopuścić daną wersję systemu operacyjnego, urządzenie nie będzie mogło uzyskać dostępu do zasobów firmy.
- **Minimalna wersja kompilacji systemu operacyjnego**: gdy firma Apple publikuje aktualizacje zabezpieczeń, zwykle jest aktualizowany numer kompilacji, a nie wersja systemu operacyjnego. Użyj tej funkcji, aby wprowadzić minimalny numer kompilacji dozwolony na urządzeniu. To proces sprawdzenia zgodności obsługuje urządzenia z systemem iOS 8.0 lub nowszym. 
- **Maksymalna wersja kompilacji systemu operacyjnego**: gdy firma Apple publikuje aktualizacje zabezpieczeń, zwykle jest aktualizowany numer kompilacji, a nie wersja systemu operacyjnego. Użyj tej funkcji, aby wprowadzić maksymalny numer kompilacji dozwolony na urządzeniu. To proces sprawdzenia zgodności obsługuje urządzenia z systemem iOS 8.0 lub nowszym.

## <a name="system-security"></a>Zabezpieczenia systemu

### <a name="password"></a>Hasło

> [!NOTE]
> Po zastosowaniu zasad zgodności lub konfiguracji do urządzenia z systemem iOS użytkownicy będą otrzymywać monit o ustawienie kodu dostępu co 15 minut. Monity będą wyświetlane, dopóki kod dostępu nie zostanie ustawiony.

- **Wymagaj hasła do odblokowania urządzeń przenośnych**: wybierz pozycję **Wymagaj**, aby wymagać od użytkowników podania hasła przed uzyskaniem dostępu do urządzenia. Urządzenia z systemem iOS używające haseł są szyfrowane.
- **Proste hasła**: ustaw wartość **Blokuj**, aby uniemożliwić użytkownikom tworzenie prostych haseł, takich jak **1234** lub **1111**. Ustaw wartość **Nieskonfigurowane**, aby umożliwić użytkownikom tworzenie haseł, takich jak **1234** lub **1111**.
- **Minimalna długość hasła**: wprowadź minimalną liczbę cyfr lub znaków, które musi zawierać hasło.
- **Wymagany typ hasła**: określ, czy w skład hasła powinny wchodzić tylko znaki **Numeryczne** lub czy ma być dopuszczalna kombinacja cyfr i innych znaków (**Alfanumeryczne**).
- **Liczba znaków innych niż alfanumeryczne w haśle**: określ minimalną liczbę znaków specjalnych (takich jak &, #, % i !), którą musi zawierać hasło.

    Ustawienie większej liczby wymaga wprowadzenia bardziej skomplikowanego hasła przez użytkownika.

- **Maksymalny czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**: wprowadź czas bezczynności, po którym użytkownik musi ponownie wprowadzić hasło.
- **Wygaśnięcie hasła (dni)**: wybierz liczbę dni, po których hasło wygasa i należy utworzyć nowe.
- **Liczba poprzednich haseł, których nie można użyć ponownie**: wprowadź liczbę poprzednio używanych haseł, których ponowne użycie nie jest możliwe.

### <a name="restricted-applications"></a>Aplikacje z ograniczeniami 
Możesz ograniczyć aplikacje poprzez dodanie ich identyfikatorów pakietu do zasad. Następnie, jeśli urządzenie ma zainstalowaną aplikację, zostanie oznaczone jako niezgodne. 
- **Nazwa aplikacji**: wprowadź przyjazną nazwę, która ułatwia rozpoznanie identyfikatora pakietu. 
- **Identyfikator pakietu aplikacji**: wprowadź unikatowy identyfikator pakietu dostarczony przez dostawcę aplikacji. Aby znaleźć identyfikator pakietu, zobacz [Jak znaleźć identyfikator pakietu aplikacji z systemem iOS](https://support.microsoft.com/help/4294074/how-to-find-the-bundle-id-for-an-ios-app).  

## <a name="assign-user-groups"></a>Przypisywanie grup użytkowników

1. Wybierz skonfigurowane przez siebie zasady. Dostęp do istniejących zasad można uzyskać po wybraniu pozycji **Zgodność urządzeń** > **Zasady**.
2. Wybierz zasady, a następnie wybierz opcję **Przypisania**. Możesz włączyć lub wyłączyć grupy zabezpieczeń usługi Azure Active Directory (AD).
3. Wybierz opcję **Wybrane grupy**, aby wyświetlić grupy zabezpieczeń usługi Azure AD. Wybierz grupy użytkowników, których mają dotyczyć te zasady, a następnie opcję **Zapisz**, aby je wdrożyć.

Zasady zostały zastosowane do użytkowników. Urządzenia, którymi posługują się użytkownicy objęci zasadami, zostaną ocenione pod kątem zgodności.

## <a name="next-steps"></a>Następne kroki
[Automatyzowanie poczty e-mail i dodawanie akcji dla niezgodnych urządzeń](actions-for-noncompliance.md)  
[Monitorowanie zasad zgodności urządzeń Intune](compliance-policy-monitor.md)
