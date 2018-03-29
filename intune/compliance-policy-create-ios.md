---
title: Tworzenie zasad zgodności urządzeń z systemem iOS w usłudze Microsoft Intune — Azure | Microsoft Intune
description: Utwórz zasady zgodności urządzeń w usłudze Microsoft Intune dla urządzeń z systemem iOS, aby wprowadzać konto e-mail, sprawdzać urządzenia, w przypadku których wykonano jailbreak, sprawdzać minimalne i maksymalne wersje systemu operacyjnego oraz ustawiać ograniczenia haseł, w tym długość hasła i brak aktywności urządzenia.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b05eb725adb61ae47a24ca884d0e73ffe0dd269f
ms.sourcegitcommit: a22309174e617e59ab0cdd0a55abde38711a5f35
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/23/2018
---
# <a name="add-a-device-compliance-policy-for-ios-devices-in-intune"></a>Dodawanie zasad zgodności dla urządzeń z systemem iOS w usłudze Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Zasady zgodności urządzeń z systemem iOS w usłudze Intune określają reguły i ustawienia, które urządzenia z systemem iOS muszą spełnić, aby zapewnić zgodność. Gdy zasady zgodności urządzeń są używane z zasadami dostępu warunkowego, można umożliwić lub zablokować dostęp do zasobów firmy. Można również pobrać raporty urządzeń i podjąć akcje w przypadku niezgodności. Zasady zgodności urządzeń są tworzone dla każdej platformy w witrynie Azure Portal usługi Intune. Aby dowiedzieć się więcej o zasadach zgodności i wymaganiach wstępnych, które należy spełnić przed utworzeniem zasad zgodności, zobacz artykuł [Wprowadzenie do zasad zgodności urządzeń](device-compliance-get-started.md).

W poniższej tabeli opisano sposób postępowania z niezgodnymi ustawieniami w przypadku, gdy zasady zgodności są używane wraz z zasadami dostępu warunkowego.

| **Ustawienie zasad** | **System iOS 8.0 lub nowszy** |
| --- | --- |
| **Konfiguracja kodu PIN lub hasła** | Skorygowane |
| **Szyfrowanie urządzenia** | Skorygowane (przez ustawienie kodu PIN) |
| **Urządzenie ze złamanymi ograniczeniami lub z odblokowanym dostępem** | Poddane kwarantannie (to nie jest ustawienie)
| **Profil e-mail** | Poddane kwarantannie |
|**Minimalna wersja systemu operacyjnego** | Poddane kwarantannie |
| **Maksymalna wersja systemu operacyjnego** | Poddane kwarantannie |
| **Zaświadczanie o kondycji systemu Windows** | Nie dotyczy |

**Skorygowane** — system operacyjny urządzenia wymusza zgodność. (Na przykład użytkownik jest zmuszony do ustawienia kodu PIN).

**Poddane kwarantannie** — system operacyjny urządzenia nie wymusza zgodności. (Na przykład urządzenie z systemem Android nie zmusza użytkownika do szyfrowania urządzenia). Gdy urządzenie nie jest zgodne, zostaną wykonane następujące akcje:

- Urządzenie zostanie zablokowane, jeśli użytkownik podlega zasadom dostępu warunkowego.
- Portal firmy powiadomi użytkownika o wszelkich problemach ze zgodnością.

## <a name="create-a-compliance-policy-in-the-azure-portal"></a>Tworzenie zasad zgodności w witrynie Azure Portal

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz opcję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz pozycję **Zgodność urządzeń** > **Zasady** > **Utwórz zasady**.
4. Wpisz nazwę i opis oraz wybierz platformę, której te zasady mają dotyczyć.
5. Wybierz pozycję **Ustawienia**, aby określić ustawienia **E-mail**, **Kondycja urządzenia**, **Właściwości urządzenia** oraz **Zabezpieczenia systemu**. Gdy wszystko będzie gotowe, wybierz przycisk **OK**.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
7. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="assign-user-groups"></a>Przypisywanie grup użytkowników

Aby przypisać użytkownikom zasady zgodności, wybierz skonfigurowane przez siebie zasady. Istniejące zasady znajdują się w okienku **Zgodność urządzeń — zasady**.

1. Wybierz zasady, które chcesz przypisać użytkownikom, a następnie wybierz pozycję **Przypisania**. Zostanie otwarte okienko, w którym można wybrać **grupy zabezpieczeń usługi Azure Active Directory** i przypisać je do zasad.
2. Wybierz pozycję **Wybrane grupy**, aby otworzyć okienko, w którym zostaną wyświetlone grupy zabezpieczeń usługi Azure AD.  Wybranie pozycji **Zapisz** powoduje wdrożenie zasad dla użytkowników.

Zasady zostały zastosowane do użytkowników.  Urządzenia, którymi posługują się użytkownicy objęci zasadami, zostaną ocenione pod kątem zgodności.

<!---## Compliance policy settings--->

## <a name="email"></a>Poczta e-mail

- **Konto e-mail musi być zarządzane przez usługę Intune:** jeśli ta opcja została ustawiona na **Tak**, urządzenie musi używać profilu poczty e-mail wdrożonego na urządzeniu. Urządzenie jest uznawane za niezgodne w następujących sytuacjach:
  - Profil poczty e-mail jest wdrażany w innej grupie użytkowników niż grupa, której dotyczą zasady zgodności.
  - Użytkownik skonfigurował już na urządzeniu konto e-mail zgodne z profilem poczty e-mail usługi Intune wdrożonym na urządzeniu. Usługa Intune nie może zastąpić profilu określonego przez użytkownika i dlatego nie może nim zarządzać. W celu zapewnienia zgodności użytkownik musi usunąć istniejące ustawienia poczty e-mail. Umożliwi to usłudze Intune zainstalowanie zarządzanego profilu poczty e-mail.
- **Wybierz profil poczty e-mail, który ma być zarządzany przez usługę Intune:** jeśli zaznaczona jest opcja **Konto e-mail musi być zarządzane przez usługę Intune**, kliknij pozycję **Wybierz**, aby określić profil poczty e-mail usługi Intune. Ten profil poczty e-mail musi znajdować się na urządzeniu.

Aby uzyskać szczegółowe informacje na temat profilów poczty e-mail, zobacz artykuł [Konfigurowanie dostępu do firmowej poczty e-mail przy użyciu profilów poczty e-mail w usłudze Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune).

## <a name="device-health"></a>Device health

- **Urządzenia ze zdjętymi zabezpieczeniami systemu**: jeśli włączysz to ustawienie, urządzenia, w przypadku których wykonano jailbreak, nie będą uznawane za zgodne.
- **Wymagaj od urządzenia, aby jego poziom zagrożenia był niższy lub równy poziomowi zagrożenia urządzenia**: wybierz maksymalny poziom zagrożenia na potrzeby oznaczania urządzenia jako niezgodnego. Jeśli przykładowo ustawisz poziom zagrożenia **Średni**, urządzenia na poziomie średnim, niskim lub zabezpieczonym będą zgodne. Urządzenia o wysokim poziomie zagrożenia będą niezgodne.

## <a name="device-properties"></a>Właściwości urządzenia

- **Wymagana minimalna wersja systemu operacyjnego:** jeśli urządzenie nie spełnia wymagań dotyczących minimalnej wersji systemu operacyjnego, będzie zgłaszane jako niezgodne. Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik może wybrać opcję uaktualnienia urządzenia, co umożliwi korzystanie z zasobów firmy.
- **Dozwolona maksymalna wersja systemu operacyjnego**: jeśli urządzenie korzysta z wersji systemu operacyjnego nowszej niż określona w regule, powoduje to zablokowanie dostępu do zasobów firmy. Następnie użytkownik zostanie poproszony o kontakt z administratorem IT. Do momentu zmiany reguły, aby dopuścić daną wersję systemu operacyjnego, urządzenie nie będzie mogło uzyskać dostępu do zasobów firmy.

## <a name="system-security"></a>Zabezpieczenia systemu

### <a name="password"></a>Hasło

> [!NOTE]
> Po zastosowaniu zasad zgodności lub konfiguracji do urządzenia z systemem iOS użytkownicy będą otrzymywać monit o ustawienie kodu dostępu co 15 minut. Monity będą wyświetlane, dopóki kod dostępu nie zostanie ustawiony.

- **Wymagaj hasła do odblokowania urządzeń przenośnych**: ustaw tę opcję na wartość **Tak**, aby wymagać od użytkowników podania hasła przed uzyskaniem dostępu do swoich urządzeń. Urządzenia z systemem iOS używające haseł są szyfrowane.
- **Proste hasła**: ustaw tę opcję na wartość **Tak**, aby zezwolić użytkownikom na tworzenie haseł takich jak **1234** lub **1111**.
- **Minimalna długość hasła**: wprowadź minimalną liczbę cyfr lub znaków, które musi zawierać hasło.
- **Wymagany typ hasła**: określ, czy użytkownik musi utworzyć hasło **alfanumeryczne**, czy **liczbowe**.
- **Liczba znaków innych niż alfanumeryczne w haśle**: określ minimalną liczbę znaków specjalnych (takich jak &, #, % i !), którą musi zawierać hasło.

    Ustawienie większej liczby wymaga wprowadzenia bardziej skomplikowanego hasła przez użytkownika.

- **Maksymalny czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**: wprowadź czas bezczynności, po którym użytkownik musi ponownie wprowadzić hasło.
- **Wygaśnięcie hasła (w dniach)**: wybierz liczbę dni, po których hasło wygasa i należy utworzyć nowe.
- **Liczba poprzednich haseł, których nie można użyć ponownie**: wprowadź liczbę poprzednio używanych haseł, których ponowne użycie nie jest możliwe.

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->
