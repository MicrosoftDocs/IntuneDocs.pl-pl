---
title: Tworzenie zasad zgodności urządzeń z systemem Android w usłudze Microsoft Intune — Azure | Microsoft Docs
description: W usłudze Microsoft Intune dla urządzeń z programem Android for Work można tworzyć i konfigurować zasady zgodności. Można wybrać, czy zezwolić na dostęp urządzeniom z wyłączonymi zabezpieczeniami systemu, ustawić dopuszczalny poziom zagrożenia, sprawdzić, czy jest zainstalowana aplikacja Google Play, wprowadzić minimalną i maksymalną wersję systemu operacyjnego, określić wymagania dotyczące hasła i zezwalać na aplikacje ładowane bezpośrednio.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/16/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 74fe0897764957e84e5a13944305221cc85bd8c7
ms.sourcegitcommit: 2773f388f50654366197a95a6838306f70fc18b8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/18/2018
---
# <a name="add-a-device-compliance-policy-for-android-for-work-devices-in-intune"></a>Dodawanie zasad zgodności dla urządzeń z programem Android for Work w usłudze Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Zasady zgodności urządzeń z programem Android for Work w usłudze Intune określają reguły i ustawienia, które te urządzenia muszą spełniać, aby zostały uznane za zgodne. Można je wykorzystać do dostępu warunkowego, aby zezwolić na dostęp do zasobów firmy lub go zablokować. Można również pobrać raporty urządzeń i podjąć działania przewidziane w przypadku niezgodności. Zasady zgodności urządzeń są tworzone dla różnych platform w witrynie Azure Portal usługi Intune. Aby dowiedzieć się więcej na temat zasad zgodności urządzeń i wymagań wstępnych, zobacz temat [Wprowadzenie do zgodności urządzeń](device-compliance-get-started.md).

W poniższej tabeli opisano sposób postępowania z niezgodnymi ustawieniami w przypadku, gdy zasady zgodności są używane wraz z zasadami dostępu warunkowego.

--------------------------

|**ustawienie zasad**| **Android for Work** |
| --- | --- |
| **Konfiguracja kodu PIN lub hasła** |  Poddane kwarantannie |
| **Szyfrowanie urządzenia** |  Poddane kwarantannie |
| **Urządzenie ze złamanymi ograniczeniami lub z odblokowanym dostępem** | Poddane kwarantannie (to nie jest ustawienie) |
| **profil e-mail** | Nie dotyczy |
| **Minimalna wersja systemu operacyjnego** | Poddane kwarantannie |
| **Maksymalna wersja systemu operacyjnego** | Poddane kwarantannie |
| **Zaświadczanie o kondycji systemu Windows** |Nie dotyczy |

**Skorygowane** — system operacyjny urządzenia wymusza zgodność. (Na przykład użytkownik jest zmuszony do ustawienia kodu PIN).+

**Poddane kwarantannie** — system operacyjny urządzenia nie wymusza zgodności. (Na przykład urządzenie z systemem Android nie zmusza użytkownika do szyfrowania urządzenia). Gdy urządzenie nie jest zgodne, zostaną wykonane następujące akcje:

- Jeśli użytkownik podlega zasadom dostępu warunkowego, urządzenie zostanie zablokowane.
- Portal firmy powiadomi użytkownika o wszelkich problemach ze zgodnością.

## <a name="create-a-device-compliance-policy"></a>Tworzenie zasad zgodności urządzenia

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
5. W polu **Platforma** wybierz opcję **Android for Work**. Wybierz opcję **Konfigurowanie ustawień** i wprowadź wartości ustawień dla pól **Kondycja urządzenia**, **Właściwości urządzenia** i **Zabezpieczenia systemu**. Gdy wszystko będzie gotowe, wybierz opcję **OK** i **Utwórz**.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="device-health"></a>Device health

- **Urządzenia z odblokowanym dostępem**: jeśli włączysz to ustawienie, urządzenia z wyłączonymi zabezpieczeniami systemu będą uznawane za niezgodne.
- **Wymagaj, aby poziom zagrożenia urządzenia był niższy lub równy podanemu poziomowi zagrożenia urządzenia**: użyj tego ustawienia, aby uzyskać ocenę ryzyka z rozwiązania Lookout MTP jako warunek zgodności. Wybierz maksymalny dozwolony poziom zagrożenia:
  - **Zabezpieczony**: ta opcja jest najbezpieczniejsza i oznacza, że urządzenie nie może mieć żadnych zagrożeń. Jeśli urządzenie zostanie wykryte jako posiadające jakikolwiek poziom zagrożenia, zostanie ono ocenione jako niezgodne.
  - **Niski**: urządzenie jest oceniane jako zgodne, jeśli istnieją tylko zagrożenia niskiego poziomu. Jakiekolwiek zagrożenia wyższego poziomu spowodują, że urządzenie będzie miało status urządzenia niezgodnego.
  - **Średni**: urządzenie jest oceniane jako zgodne, jeśli dotyczące go zagrożenia są na poziomie niskim lub średnim. W przypadku wykrycia na urządzeniu zagrożeń wysokiego poziomu zostanie ono określone jako niezgodne.
  - **Wysoki**: ta opcja jest najmniej bezpieczna, ponieważ zezwala na wszystkie poziomy zagrożeń. To ustawienie może być przydatne, jeśli rozwiązanie jest używane tylko na potrzeby raportowania.
- **Usługi Google Play są skonfigurowane**: wymagane jest zainstalowanie i włączenie aplikacji usług Google Play. Usługi Google Play umożliwiają aktualizacje zabezpieczeń i stanowią zależność na poziomie podstawowym dla wielu funkcji zabezpieczeń w urządzeniach certyfikowanych przez firmę Google.
- **Zaktualizowany dostawca zabezpieczeń**: wymagane jest, aby zaktualizowany dostawca zabezpieczeń mógł chronić urządzenie przed znanymi lukami w zabezpieczeniach.
- **Zaświadczenie urządzeń SafetyNet**: wprowadź poziom [zaświadczenia rozwiązania SafetyNet](https://developer.android.com/training/safetynet/attestation.html), którego warunki muszą zostać spełnione. Dostępne opcje:
  - **Nieskonfigurowany**
  - **Sprawdź podstawową integralność**
  - **Sprawdź podstawową integralność i certyfikowane urządzenia**

#### <a name="threat-scan-on-apps"></a>Skanowanie aplikacji pod kątem zagrożeń

W urządzeniach z profilami służbowymi (Android for Work) ustawienie **Skanowanie aplikacji pod kątem zagrożeń** można znaleźć w obszarze ustawień zasad konfiguracji. Administratorzy mają możliwość włączenia tego ustawienia dla urządzenia.

Jeśli w przedsiębiorstwie są używane profile służbowe systemu Android, można włączyć opcję **Skanowanie aplikacji pod kątem zagrożeń** dla zarejestrowanych urządzeń. Ustanów profil urządzenia i wymagaj ustawienia zabezpieczeń systemu. Aby uzyskać więcej informacji, zobacz temat [Ustawienia ograniczeń urządzenia z programem Android for Work w usłudze Microsoft Intune](device-restrictions-android-for-work.md).

## <a name="device-property-settings"></a>Ustawienia właściwości urządzenia

- **Minimalna wersja systemu operacyjnego**: jeśli urządzenie nie spełnia wymagań dotyczących minimalnej wersji systemu operacyjnego, będzie zgłaszane jako niezgodne. Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik końcowy może zdecydować się na uaktualnienie swojego urządzenia i w konsekwencji uzyskanie dostępu do zasobów firmy.
- **Maksymalna wersja systemu operacyjnego**: jeśli urządzenie korzysta z wersji systemu operacyjnego nowszej niż określona w regule, powoduje to zablokowanie dostępu do zasobów firmy. W takiej sytuacji użytkownik zostanie poproszony o kontakt z administratorem IT. Dopóki reguła nie zostanie zmieniona tak, aby dopuszczać daną wersję systemu operacyjnego, urządzenie nie będzie mogło uzyskać dostępu do zasobów firmy.

## <a name="system-security-settings"></a>Ustawienia zabezpieczeń systemu

### <a name="password"></a>Hasło

- **Wymagaj hasła do odblokowania urządzeń przenośnych**: wybierz pozycję **Wymagaj**, aby wymagać od użytkowników podania hasła przed uzyskaniem dostępu do urządzenia.
- **Minimalna długość hasła**: wprowadź minimalną liczbę cyfr lub znaków, które musi zawierać hasło użytkownika.
- **Wymagany typ hasła**: określ, czy w skład hasła powinny wchodzić tylko znaki numeryczne czy ma być dopuszczalna kombinacja cyfr i innych znaków. Wybierz spośród opcji:
  - **Ustawienie domyślne urządzenia**
  - **Zabezpieczenia biometryczne na niskim poziomie**
  - **Co najmniej numeryczne**
  - **Wartość liczbowa/złożona**
  - **Co najmniej alfabetyczne**
  - **Co najmniej alfanumeryczne**
  - **Co najmniej alfanumeryczne z symbolami**
- **Maksymalny czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**: wprowadź czas bezczynności, po którym użytkownik musi ponownie wprowadzić hasło.
- **Wygaśnięcie hasła (w dniach)**: wybierz liczbę dni, po których hasło wygasa i należy utworzyć nowe.
- **Liczba poprzednich haseł, których nie można użyć ponownie**: wprowadź liczbę ostatnich haseł, których ponowne użycie nie jest możliwe. To ustawienie można wykorzystać w celu ograniczenia użytkownikowi możliwości tworzenia wcześniej używanych haseł.

### <a name="encryption"></a>Szyfrowanie

- **Wymagaj szyfrowania na urządzeniu przenośnym:** nie musisz konfigurować tego ustawienia, ponieważ urządzenia z programem Android for Work wymuszają szyfrowanie.

### <a name="device-security"></a>Zabezpieczenia urządzeń

- **Blokuj aplikacje z nieznanych źródeł**: nie musisz konfigurować tego ustawienia, ponieważ urządzenia z programem Android for Work zawsze ograniczają instalację z nieznanych źródeł.
- **Integralność środowiska uruchomieniowego aplikacji Portal firmy**: sprawdza, czy aplikacja Portal firmy ma zainstalowane domyślne środowisko uruchomieniowe, jest poprawnie podpisana, nie jest w trybie debugowania i została zainstalowana ze znanego źródła.
- **Blokuj debugowanie USB na urządzeniu**: nie musisz konfigurować tego ustawienia, ponieważ debugowanie USB na urządzeniach z programem Android for Work zostało już wyłączone.
- **Minimalny poziom poprawki bezpieczeństwa**: wybierz poziom najstarszej poprawki bezpieczeństwa, która może znajdować się w urządzeniu. Urządzenia, które nie mają co najmniej tego poziomu poprawek, są niezgodne. Data musi być wprowadzona w formacie `YYYY-MM-DD`.

## <a name="assign-user-groups"></a>Przypisywanie grup użytkowników

1. Wybierz zasady, które zostały przez Ciebie skonfigurowane. Dostęp do istniejących zasad można uzyskać po wybraniu opcji **Zgodność urządzeń** > **Zasady**.
2. Wybierz zasady, a następnie wybierz opcję **Przypisania**. Możesz włączyć lub wyłączyć grupy zabezpieczeń usługi Azure Active Directory (AD).
3. Wybierz opcję **Wybrane grupy**, aby wyświetlić grupy zabezpieczeń usługi Azure AD. Wybierz grupy użytkowników, których mają dotyczyć te zasady, a następnie opcję **Zapisz**, aby je wdrożyć.

Zasady zostały zastosowane do użytkowników. Urządzenia, którymi posługują się użytkownicy objęci zasadami, zostaną ocenione pod kątem zgodności.

## <a name="next-steps"></a>Następne kroki
[Automatyzowanie poczty e-mail i dodawanie akcji dla niezgodnych urządzeń](actions-for-noncompliance.md)  
[Monitorowanie zasad zgodności urządzeń Intune](compliance-policy-monitor.md)