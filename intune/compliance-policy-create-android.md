---
title: "Tworzenie zasad zgodności urządzeń z systemem Android w usłudze Microsoft Intune"
titleSuffix: 
description: "Utwórz zasady zgodności urządzeń w usłudze Microsoft Intune dla urządzeń z systemem Android w celu określenia wymagań, które urządzenie musi spełniać, aby było zgodne."
keywords: 
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e1258fe4-0b5c-4485-8bd1-152090df6345
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2539ff1703809f5f89183a9d0cfd448f2e57fd64
ms.sourcegitcommit: 54fc806036f84a8667cf8f74086358bccd30aa7d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/20/2018
---
# <a name="how-to-create-a-device-compliance-policy-for-android-devices-in-intune"></a>Tworzenie zasad zgodności dla urządzeń z systemem Android w usłudze Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Zasady zgodności urządzeń w usłudze Intune dla systemu Android określają reguły i ustawienia, które urządzenia z systemem Android muszą spełnić, aby zostały uznane za zgodne. Tych zasad można używać z dostępem warunkowym, aby zezwalać na dostęp do zasobów firmy lub go blokować. Można także uzyskiwać raporty urządzeń i podejmować działania w przypadku niezgodności. Zasady zgodności urządzeń są tworzone dla każdej platformy w witrynie Azure Portal usługi Intune. Aby dowiedzieć się więcej o zasadach zgodności i wymaganiach wstępnych, które należy spełnić przed utworzeniem zasad zgodności, zobacz artykuł [Wprowadzenie do zasad zgodności urządzeń](device-compliance-get-started.md).

## <a name="to-create-a-device-compliance-policy"></a>Aby utworzyć zasadę zgodności urządzenia

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
1. W okienku **Intune** wybierz pozycję **Zgodność urządzeń**. W obszarze **Zarządzaj** wybierz pozycję **Zasady** i wybierz pozycję **Utwórz zasady**.
3. Wybierz pozycję **Konfiguruj ustawienia**, aby określić ustawienia **zabezpieczeń systemu**, **kondycji urządzenia** i **właściwości urządzenia** w tym miejscu. Gdy wszystko będzie gotowe, wybierz pozycję **OK**.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant based on the configured settings in this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **OK** when you are finished creating all the actions.--->

## <a name="to-assign-user-groups"></a>Aby przypisać grupy użytkowników

Aby przypisać użytkownikom zasady zgodności, wybierz skonfigurowane przez siebie zasady. Istniejące zasady znajdują się w okienku **Zgodność urządzeń — zasady**.

1. Wybierz zasady i pozycję **Przypisania**. Spowoduje to otwarcie okienka, w którym można wybrać **grupy zabezpieczeń usługi Azure Active Directory** i przypisać je do zasad.
2. Wybierz pozycję **Wybrane grupy**, aby otworzyć okienko, w którym zostaną wyświetlone grupy zabezpieczeń usługi Azure AD. Tutaj można znaleźć grupy zabezpieczeń w usłudze Azure Active Directory.  Możesz wybrać grupy użytkowników, których mają dotyczyć te zasady, a następnie wybrać pozycję **Zapisz**, aby wdrożyć te zasady dla użytkowników.

Zasady zostały zastosowane do użytkowników.  Urządzenia, którymi posługują się użytkownicy objęci zasadami, zostaną ocenione pod kątem zgodności.

<!---##  Compliance policy settings--->

## <a name="device-health-and-security-settings"></a>Kondycja urządzeń i ustawienia zabezpieczeń

- **Nie zezwalaj na zdjęcie zabezpieczeń systemu ani na uzyskanie dostępu do konta root:** w przypadku włączenia tego ustawienia urządzenia ze zdjętymi zabezpieczeniami systemu zostaną ocenione jako niezgodne.
- **Wymagaj zapobiegania instalacji aplikacji z nieznanych źródeł (Android 4.0 i nowsze):** aby zablokować urządzenia z włączonym ustawieniem **Bezpieczeństwo** > **Nieznane źródła**, włącz to ustawienie i wybierz opcję **Tak**.

### <a name="important"></a>Ważne

Aplikacje ładowania bezpośredniego wymagają włączenia ustawienia **Nieznane źródła**. Te zasady zgodności należy włączyć tylko w przypadku braku bezpośredniego ładowania aplikacji Android na urządzeniach.

- **Wymagaj wyłączenia debugowania USB (Android 4.2 i nowsze):** to ustawienie określa, czy należy wykrywać włączenie opcji debugowania USB na urządzeniu.
- **Wymagaj włączenia na urządzeniach opcji Skanuj urządzenie pod kątem zagrożeń zabezpieczeń (Android 4.2-4.4)**: to ustawienie określa włączenie funkcji **Weryfikuj aplikacje** na urządzeniu.
- **Minimalny poziom poprawek bezpieczeństwa (Android 6.0 i nowsze)**: to ustawienie określa minimalny poziom poprawek bezpieczeństwa systemu Android. Urządzenia, które nie mają co najmniej tego poziomu poprawek, będą niezgodne. Data musi mieć określony format: RRRR-MM-DD.
- **Wymagaj włączonej ochrony urządzenia przed zagrożeniami**: Użyj tego ustawienia, aby uzyskać ocenę ryzyka z rozwiązania Lookout MTP jako warunku zgodności. Wybierz maksymalny dozwolony poziom zagrożenia, który będzie miał jedną z następujących wartości:
  - **Brak (zabezpieczone)**: to ustawienie zapewnia najwyższy poziom zabezpieczeń. Oznacza to, że urządzenie nie może mieć żadnych zagrożeń. Jeśli urządzenie zostanie wykryte jako posiadające dowolny poziom zagrożenia, zostanie ono ocenione jako niezgodne.
  - **Niski**: urządzenie jest oceniane jako zgodne, jeśli istnieją tylko zagrożenia niskiego poziomu. Jakiekolwiek zagrożenia wyższego poziomu spowodują, że urządzenie będzie miało status urządzenia niezgodnego.
  - **Średni**: urządzenie jest oceniane jako zgodne, jeśli dotyczące go zagrożenia są na poziomie niskim lub średnim. W przypadku wykrycia na urządzeniu zagrożeń wysokiego poziomu zostanie ono określone jako niezgodne.
  - **Wysoki**: to ustawienie zapewnia najniższy poziom zabezpieczeń. Zasadniczo to ustawienie dopuszcza wszystkie poziomy zagrożeń. Ustawienie to może być przydatne na przykład w przypadku użycia rozwiązania tylko na potrzeby raportowania.

## <a name="system-security-settings"></a>Ustawienia zabezpieczeń systemu

### <a name="password"></a>Hasło

- **Wymagaj hasła do odblokowania urządzeń przenośnych:** ustaw tę pozycję na wartość **Tak**, aby wymagać od użytkowników podania hasła przed uzyskaniem dostępu do swojego urządzenia.
- **Minimalna długość hasła**: określ minimalną liczbę cyfr lub znaków, które musi zawierać hasło użytkownika.
- **Jakość hasła:** to ustawienie wykrywa, czy określone przez Ciebie wymagania dotyczące hasła zostały skonfigurowane na urządzeniu. Włącz to ustawienie, aby wymagać od użytkowników spełnienia pewnych wymagań dotyczących haseł dla urządzeń z systemem Android. Wybierz spośród opcji:
  - **Zabezpieczenia biometryczne na niskim poziomie**
  - **Wymagane**
  - **Co najmniej numeryczne**
  - **Co najmniej alfabetyczne**
  - **Co najmniej alfanumeryczne**
  - **Alfanumeryczne z symbolami**
- **Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła:** określ czas bezczynności, po którym użytkownik musi ponownie wprowadzić swoje hasło.
- **Wygaśnięcie hasła (w dniach)**: wybierz liczbę dni, po których hasło wygasa i należy utworzyć nowe.
- **Pamiętaj historię haseł:** używaj tego ustawienia w połączeniu z ustawieniem **Zapobiegaj ponownemu używaniu poprzednich haseł**, aby uniemożliwić użytkownikowi ponowne używanie wcześniej utworzonych haseł.
- **Zapobiegaj ponownemu używaniu poprzednich haseł:** jeśli jest zaznaczona opcja **Pamiętaj historię haseł**, określ liczbę uprzednio używanych haseł, które nie mogą być ponownie używane.
- **Wymagaj hasła, gdy urządzenie powraca ze stanu bezczynności:** tego ustawienia należy używać razem z ustawieniem **Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**. Użytkownik otrzyma monit o wprowadzenie hasła w celu uzyskania dostępu do urządzenia, które było nieaktywne przez czas określony w ustawieniu **Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**.

### <a name="encryption"></a>Szyfrowanie

- **Wymagaj szyfrowania na urządzeniu przenośnym:** ustaw tę pozycję na wartość **Tak**, aby wymagać zaszyfrowania urządzenia w celu połączenia się z zasobami. Urządzenia są szyfrowane po wybraniu ustawienia **Wymagaj hasła do odblokowania urządzeń przenośnych**.

## <a name="device-property-settings"></a>Ustawienia właściwości urządzenia

- **Wymagana minimalna wersja systemu operacyjnego:** jeśli urządzenie nie spełnia wymagań dotyczących minimalnej wersji systemu operacyjnego, będzie zgłaszane jako niezgodne. Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik może zdecydować się na uaktualnienie swojego urządzenia, co umożliwi mu dostęp do zasobów firmy.
- **Dozwolona maksymalna wersja systemu operacyjnego:** jeśli urządzenie korzysta z wersji systemu operacyjnego nowszej niż określona w regule, powoduje to zablokowanie dostępu do zasobów firmy i wyświetlenie monitu o kontakt z administratorem IT. Do momentu zmiany reguł dopuszczających daną wersję systemu operacyjnego urządzenie nie może być stosowane do uzyskiwania dostępu do zasobów firmy.

## <a name="how-noncompliant-settings-work-with-conditional-access-policies"></a>Jak ustawienia niezgodne współdziałają z zasadami dostępu warunkowego?

W tabeli poniżej opisano sposób postępowania z niezgodnymi ustawieniami w przypadku, gdy zasady zgodności są używane wraz z zasadami dostępu warunkowego.

--------------------

|**Ustawienie zasad**| **System Android 4.0 lub nowszy, system Samsung Knox Standard 4.0 lub nowszy** |
| --- | ----|
| **Konfiguracja kodu PIN lub hasła** |  Poddane kwarantannie |
| **Szyfrowanie urządzenia** | Poddane kwarantannie |
| **Urządzenie ze złamanymi ograniczeniami lub z odblokowanym dostępem** | Poddane kwarantannie (to nie jest ustawienie) |
| **profil e-mail** | Nie dotyczy |
| **Minimalna wersja systemu operacyjnego** | Poddane kwarantannie |
| **Maksymalna wersja systemu operacyjnego** |   Poddane kwarantannie |
| **Zaświadczanie o kondycji systemu Windows** | Nie dotyczy |

--------------------------

**Skorygowane** — system operacyjny urządzenia wymusza zgodność. (Na przykład użytkownik jest zmuszony do ustawienia kodu PIN).

**Poddane kwarantannie** — system operacyjny urządzenia nie wymusza zgodności. (Na przykład urządzenie z systemem Android nie zmusza użytkownika do szyfrowania urządzenia). Gdy urządzenie nie jest zgodne, zostaną wykonane następujące akcje:

- Urządzenie zostanie zablokowane, jeśli użytkownik podlega zasadom dostępu warunkowego.
- Portal firmy powiadomi użytkownika o wszelkich problemach ze zgodnością.

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->
