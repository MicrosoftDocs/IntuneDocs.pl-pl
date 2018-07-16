---
title: Tworzenie zasad zgodności urządzeń z systemem Android w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Można tworzyć i konfigurować zasady zgodności w usłudze Microsoft Intune dla urządzeń z systemem Android. Można wybrać, czy zezwolić na dostęp urządzeniom z wyłączonymi zabezpieczeniami systemu, ustawić dopuszczalny poziom zagrożenia, sprawdzić, czy jest zainstalowana aplikacja Google Play, wprowadzić minimalną i maksymalną wersję systemu operacyjnego, określić wymagania dotyczące hasła i zezwalać na aplikacje ładowane bezpośrednio.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e1258fe4-0b5c-4485-8bd1-152090df6345
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 85f11e3a9bfd43affde35806d9aeaf40dcbfe03d
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/07/2018
ms.locfileid: "37906196"
---
# <a name="add-a-device-compliance-policy-for-android-devices-in-intune"></a>Dodawanie zasad zgodności dla urządzeń z systemem Android w usłudze Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Zasady zgodności urządzeń w usłudze Intune dla systemu Android określają reguły i ustawienia, które urządzenia z systemem Android muszą spełnić, aby zostały uznane za zgodne. Można je wykorzystać do dostępu warunkowego, aby zezwolić na dostęp do zasobów firmy lub go zablokować. Można również pobrać raporty urządzeń i podjąć akcje w przypadku niezgodności. Zasady zgodności urządzeń są tworzone dla każdej platformy w witrynie Azure Portal usługi Intune. Aby dowiedzieć się więcej na temat zasad zgodności i wymagań wstępnych, zobacz [Wprowadzenie do zasad zgodności urządzeń](device-compliance-get-started.md).

W poniższej tabeli opisano sposób postępowania z niezgodnymi ustawieniami w przypadku, gdy zasady zgodności są używane wraz z zasadami dostępu warunkowego.

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

## <a name="create-a-device-compliance-policy"></a>Tworzenie zasad zgodności urządzenia

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
5. W polu **Platforma** wybierz opcję **Android**. Wybierz opcję **Konfigurowanie ustawień** i wprowadź wartości ustawień dla pól **Kondycja urządzenia**, **Właściwości urządzenia** i **Zabezpieczenia systemu**. Gdy wszystko będzie gotowe, wybierz opcję **OK** i **Utwórz**.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant based on the configured settings in this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **OK** when you are finished creating all the actions.--->

<!---##  Compliance policy settings--->

## <a name="device-health"></a>Device health

- **Urządzenia z odblokowanym dostępem**: jeśli włączysz to ustawienie, urządzenia z wyłączonymi zabezpieczeniami systemu będą uznawane za niezgodne.
- **Wymagaj, aby poziom zagrożenia urządzenia był niższy lub równy podanemu poziomowi zagrożenia urządzenia**: użyj tego ustawienia, aby uzyskać ocenę ryzyka z rozwiązania Lookout MTP jako warunek zgodności. Wybierz maksymalny dozwolony poziom zagrożenia:
  - **Zabezpieczony**: ta opcja jest najbezpieczniejsza, ponieważ urządzenie nie może mieć żadnych zagrożeń. Jeśli urządzenie zostanie wykryte jako posiadające jakikolwiek poziom zagrożenia, zostanie ono ocenione jako niezgodne.
  - **Niski**: urządzenie jest oceniane jako zgodne, jeśli istnieją tylko zagrożenia niskiego poziomu. Jakiekolwiek zagrożenia wyższego poziomu spowodują, że urządzenie będzie miało status urządzenia niezgodnego.
  - **Średni**: urządzenie jest oceniane jako zgodne, jeśli istniejące zagrożenia są na poziomie niskim lub średnim. W przypadku wykrycia na urządzeniu zagrożeń wysokiego poziomu zostanie ono określone jako niezgodne.
  - **Wysoki**: ta opcja jest najmniej bezpieczna i zezwala na wszystkie poziomy zagrożeń. To ustawienie może być przydatne, jeśli rozwiązanie jest używane tylko na potrzeby raportowania.
- **Skonfigurowano usługi Google Play**: wymagane jest zainstalowanie i włączenie aplikacji usług Google Play. Usługi Google Play umożliwiają aktualizacje zabezpieczeń i stanowią zależność na poziomie podstawowym dla wielu funkcji zabezpieczeń w urządzeniach certyfikowanych przez firmę Google.
- **Aktualny dostawca zabezpieczeń**: wymagane jest, aby zaktualizowany dostawca zabezpieczeń mógł chronić urządzenie przed znanymi lukami w zabezpieczeniach.
- **Skanowanie aplikacji pod kątem zagrożeń**: wymaga włączenia w systemie Android funkcji **Weryfikuj aplikacje**.

  > [!NOTE]
  > Na platformie systemu Android w starszej wersji ta funkcja jest ustawieniem zgodności. Usługa Intune może tylko sprawdzić, czy to ustawienie zostało włączone na poziomie urządzenia. Na urządzeniach z profilami służbowymi systemu Android to ustawienie można znaleźć w obszarze ustawień zasad konfiguracji. Umożliwia to administratorom włączenie ustawienia dla urządzenia.

  Jeśli w przedsiębiorstwie są używane profile służbowe systemu Android, można włączyć opcję **Skanowanie aplikacji pod kątem zagrożeń** dla zarejestrowanych urządzeń. Ustanów profil urządzenia i wymagaj ustawienia zabezpieczeń systemu. Aby uzyskać więcej informacji, zobacz [Ustawienia ograniczeń urządzenia z profilem służbowym systemu Android w usłudze Intune](device-restrictions-android-for-work.md).

- **Zaświadczenie urządzeń SafetyNet**: wprowadź poziom [zaświadczenia rozwiązania SafetyNet](https://developer.android.com/training/safetynet/attestation.html), którego warunki muszą zostać spełnione. Dostępne opcje:
  - **Nieskonfigurowany**
  - **Sprawdź podstawową integralność**
  - **Sprawdź podstawową integralność i certyfikowane urządzenia**

## <a name="device-property-settings"></a>Ustawienia właściwości urządzenia

- **Minimalna wersja systemu operacyjnego**: jeśli urządzenie nie spełnia wymagań dotyczących minimalnej wersji systemu operacyjnego, będzie zgłaszane jako niezgodne. Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik końcowy może zdecydować się na uaktualnienie swojego urządzenia, co umożliwi mu dostęp do zasobów firmy.
- **Maksymalna wersja systemu operacyjnego**: jeśli urządzenie korzysta z wersji systemu operacyjnego nowszej niż określona w regule, powoduje to zablokowanie dostępu do zasobów firmy. Użytkownik zostanie poproszony o kontakt z administratorem IT. Dopóki reguła nie zostanie zmieniona tak, aby dopuszczać daną wersję systemu operacyjnego, urządzenie nie będzie mogło uzyskać dostępu do zasobów firmy.

## <a name="system-security-settings"></a>Ustawienia zabezpieczeń systemu

### <a name="password"></a>Hasło

- **Wymagaj hasła do odblokowania urządzeń przenośnych**: wybierz pozycję **Wymagaj**, aby wymagać od użytkowników podania hasła przed uzyskaniem dostępu do urządzenia.
- **Minimalna długość hasła**: wprowadź minimalną liczbę cyfr lub znaków, które musi zawierać hasło użytkownika.
- **Wymagany typ hasła**: określ, czy w skład hasła powinny wchodzić tylko znaki numeryczne, czy też ma być wymagana kombinacja cyfr i innych znaków. Wybierz spośród opcji:
  - **Ustawienie domyślne urządzenia**
  - **Zabezpieczenia biometryczne na niskim poziomie**
  - **Co najmniej numeryczne**
  - **Złożona wartość liczbowa**: powtarzające się lub kolejne cyfry (np. „1111” lub „1234”) są niedozwolone.
  - **Co najmniej alfabetyczne**
  - **Co najmniej alfanumeryczne**
  - **Co najmniej alfanumeryczne z symbolami**
- **Maksymalny czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**: wprowadź czas bezczynności, po którym użytkownik musi ponownie wprowadzić hasło.
- **Wygaśnięcie hasła (dni)**: wybierz liczbę dni, po których wygasa hasło użytkownika i należy utworzyć nowe.
- **Liczba poprzednich haseł, których nie można użyć ponownie**: wprowadź liczbę ostatnich haseł, których ponowne użycie nie jest możliwe. To ustawienie można wykorzystać w celu ograniczenia użytkownikowi możliwości tworzenia wcześniej używanych haseł.

### <a name="encryption"></a>Szyfrowanie

- **Szyfrowanie magazynu danych na urządzeniu** (Android 4.0 i nowsze wersje lub KNOX 4.0 i nowsze wersje): wybierz opcję **Wymagaj**, aby zaszyfrować na urządzeniach magazyn danych. Urządzenia są szyfrowane po wybraniu ustawienia **Wymagaj hasła do odblokowania urządzeń przenośnych**.

### <a name="device-security"></a>Zabezpieczenia urządzeń

- **Blokuj aplikacje z nieznanych źródeł**: wybierz blokowanie urządzeń ze źródeł włączonych za pośrednictwem opcji „Zabezpieczenia > Nieznane źródła” (Android 4.0 – Android 7.x. Nieobsługiwane przez Android 8.0 i nowsze). Aby ładować aplikacje bezpośrednio, nieznane źródła muszą być dozwolone. W przypadku braku bezpośredniego ładowania aplikacji Android na urządzeniach należy włączyć te zasady zgodności.

  > [!IMPORTANT]
  > Aplikacje ładowania bezpośredniego wymagają włączenia ustawienia **Blokuj aplikacje z nieznanych źródeł**. Te zasady zgodności należy włączyć tylko w przypadku braku bezpośredniego ładowania aplikacji Android na urządzeniach.

- **Integralność środowiska uruchomieniowego aplikacji Portal firmy**: sprawdza, czy aplikacja Portal firmy ma zainstalowane domyślne środowisko uruchomieniowe, jest poprawnie podpisana, nie jest w trybie debugowania i została zainstalowana ze znanego źródła.
- **Blokuj debugowanie USB na urządzeniu** (Android 4.2 i nowsze): wybierz, aby zablokować używanie funkcji debugowania USB na urządzeniu.
- **Minimalny poziom poprawki bezpieczeństwa** (Android 6.0 lub nowszy): wybierz poziom najstarszej poprawki zabezpieczeń, która może znajdować się w urządzeniu. Urządzenia, które nie mają co najmniej tego poziomu poprawek, są niezgodne. Data musi być wprowadzona w formacie `YYYY-MM-DD`.

## <a name="locations"></a>Lokalizacje

W swoich zasadach dokonuj wyboru spośród istniejących lokalizacji. Nie masz jeszcze lokalizacji? Wskazówki możesz znaleźć w temacie [Korzystanie z lokalizacji (ogrodzenia sieci) w usłudze Intune](use-network-locations.md).

1. Wybierz pozycję **Wybierz lokalizacje**.
2. Na liście zaznacz swoją lokalizację, a następnie wybierz pozycję **Wybierz**.
3. **Zapisz** zasady.
4. Wybierz pozycję **Akcje w przypadku niezgodności**. Domyślna akcja natychmiast oznacza urządzenie jako niezgodne. Ta akcja jest stosowana, gdy wybrana jest co najmniej jedna lokalizacja, a urządzenie nie jest połączone z wybranymi lokalizacjami.

  Tę akcję możesz zmienić, aby zaktualizować harmonogram oznaczania urządzenia jako niezgodnego (np. po jednym dniu). Możesz również skonfigurować drugą akcję, która wysyła wiadomość e-mail do użytkownika, gdy urządzenie nie jest już zgodne z Twoimi lokalizacjami.

## <a name="assign-user-groups"></a>Przypisywanie grup użytkowników

1. Wybierz skonfigurowane przez siebie zasady. Dostęp do istniejących zasad można uzyskać po wybraniu pozycji **Zgodność urządzeń** > **Zasady**.
2. Wybierz zasady, a następnie wybierz opcję **Przypisania**. Możesz włączyć lub wyłączyć grupy zabezpieczeń usługi Azure Active Directory (AD).
3. Wybierz opcję **Wybrane grupy**, aby wyświetlić grupy zabezpieczeń usługi Azure AD. Wybierz grupy użytkowników, których mają dotyczyć te zasady, a następnie opcję **Zapisz**, aby je wdrożyć.

Zasady zostały zastosowane do użytkowników. Urządzenia, którymi posługują się użytkownicy objęci zasadami, zostaną ocenione pod kątem zgodności.

## <a name="next-steps"></a>Następne kroki
[Automatyzowanie poczty e-mail i dodawanie akcji dla niezgodnych urządzeń](actions-for-noncompliance.md)  
[Monitorowanie zasad zgodności urządzeń Intune](compliance-policy-monitor.md)