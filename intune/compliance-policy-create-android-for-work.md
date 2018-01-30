---
title: "Tworzenie zasad zgodności dla programu Android for Work"
titleSuffix: Azure portal
description: "Informacje dotyczące tworzenia zasad zgodności dla urządzeń z programem Android for Work."
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e9ec660fcbd1f02fb0767e322edfdfa7f85964a7
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-create-a-device-compliance-policy-for-android-for-work-devices-in-intune"></a>Tworzenie zasad zgodności dla urządzeń z programem Android for Work w usłudze Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Zasady zgodności są tworzone dla każdej platformy.  Zasady zgodności można tworzyć w witrynie Azure Portal. Aby dowiedzieć się więcej o tym, czym są zasady zgodności, zobacz temat [What is device compliance](device-compliance.md) (Czym jest zgodność z urządzeniem). Aby dowiedzieć się więcej o wymaganiach wstępnych, które należy spełnić przed utworzeniem zasad zgodności, zobacz artykuł [Get started with device compliance](device-compliance-get-started.md) (Wprowadzenie do zgodności z urządzeniem).

W tabeli poniżej opisano sposób postępowania z niezgodnymi ustawieniami w przypadku, gdy zasady zgodności są używane wraz z zasadami dostępu warunkowego.

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

**Poddane kwarantannie** — system operacyjny urządzenia nie wymusza zgodności. (Na przykład urządzenie z systemem Android nie zmusza użytkownika do szyfrowania urządzenia). Gdy urządzenia nie są zgodne, zostaną wykonane następujące akcje:

- Urządzenie zostanie zablokowane, jeśli użytkownik podlega zasadom dostępu warunkowego.
- Portal firmy powiadomi użytkownika o wszelkich problemach ze zgodnością.

## <a name="create-a-compliance-policy-in-the-azure-portal"></a>Tworzenie zasad zgodności w witrynie Azure Portal

1. W bloku **Intune** wybierz pozycję **Ustaw zgodność urządzenia**. W obszarze **Zarządzaj** wybierz pozycję **Wszystkie zasady zgodności urządzeń** i wybierz przycisk **Utwórz**.
2. Wpisz nazwę, opis i wybierz platformę, której te zasady mają dotyczyć.
3. Wybierz pozycję **Wymagania zgodności**, aby określić ustawienia **Zabezpieczenia**, **Kondycja urządzenia** i **Właściwości urządzenia**, a gdy wszystko będzie gotowe, wybierz przycisk **Ok**.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** blade, choose **Add** to create a new action.  The action parameters blade allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="assign-user-groups"></a>Przypisywanie grup użytkowników

Aby przypisać użytkownikom zasady zgodności, wybierz skonfigurowane przez siebie zasady. Istniejące zasady znajdują się w bloku **Zgodność — zasady**.

1. Wybierz zasady, które chcesz przypisać użytkownikom, a następnie wybierz pozycję **Przypisania**. Spowoduje to otwarcie bloku, w którym można wybrać **grupy zabezpieczeń usługi Azure Active Directory** i przypisać je do zasad.
2. Wybierz pozycję **Wybierz grupy**, aby otworzyć blok, w którym zostaną wyświetlone grupy zabezpieczeń usługi Azure AD.  Wybranie pozycji **Wybierz** powoduje wdrożenie zasad dla użytkowników.

Zasady zostały zastosowane do użytkowników.  Urządzenia, którymi posługują się użytkownicy objęci zasadami, zostaną ocenione pod kątem zgodności.

<!--- ##  Compliance policy settings--->

## <a name="system-security-settings"></a>Ustawienia zabezpieczeń systemu

### <a name="password"></a>Hasło

- **Wymagaj hasła do odblokowania urządzeń przenośnych:** ustaw tę pozycję na wartość **Tak**, aby wymagać od użytkowników podania hasła przed uzyskaniem dostępu do swojego urządzenia.
- **Minimalna długość hasła**: określ minimalną liczbę cyfr lub znaków, które musi zawierać hasło.
- **Jakość hasła:** to ustawienie wykrywa, czy określone przez Ciebie wymagania dotyczące hasła zostały skonfigurowane na urządzeniu. Włącz to ustawienie, aby wymagać od użytkowników skonfigurowania pewnych wymagań dotyczących haseł dla urządzeń z systemem Android. Wybierz spośród opcji:
  - **Zabezpieczenia biometryczne na niskim poziomie**
  - **Wymagane**
  - **Co najmniej numeryczne**
  - **Co najmniej alfabetyczne**
  - **Co najmniej alfanumeryczne**
  - **Alfanumeryczne z symbolami**
- **Liczba minut braku aktywności, zanim będzie wymagane hasło:** określa czas bezczynności, po którym użytkownik musi ponownie wprowadzić hasło.
- **Wygaśnięcie hasła (w dniach):** wybierz liczbę dni, po których hasło użytkownika wygasa i należy utworzyć nowe.
- **Pamiętaj historię haseł:** używaj tego ustawienia w połączeniu z ustawieniem **Zapobiegaj ponownemu używaniu poprzednich haseł**, aby uniemożliwić użytkownikowi ponowne używanie wcześniej utworzonych haseł.
- **Zapobiegaj ponownemu używaniu poprzednich haseł:** jeśli jest zaznaczona opcja **Pamiętaj historię haseł**, określ liczbę uprzednio używanych haseł, które nie mogą być ponownie używane.
- **Wymagaj hasła, gdy urządzenie powraca ze stanu bezczynności:** tego ustawienia należy używać razem z ustawieniem **Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**. Użytkownicy końcowi otrzymają monit o wprowadzenie hasła w celu uzyskania dostępu do urządzenia, które było nieaktywne przez czas określony w ustawieniu **Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**.


### <a name="encryption"></a>Szyfrowanie

- **Wymagaj szyfrowania na urządzeniu przenośnym:** nie musisz konfigurować tego ustawienia, ponieważ urządzenia z programem Android for Work wymuszają szyfrowanie.


## <a name="device-health-and-security-settings"></a>Kondycja urządzeń i ustawienia zabezpieczeń

- **Nie zezwalaj na zdjęcie zabezpieczeń systemu ani na uzyskanie dostępu do konta root:** w przypadku włączenia tego ustawienia urządzenia ze zdjętymi zabezpieczeniami systemu zostaną ocenione jako niezgodne.
- **Wymagaj, aby urządzenia uniemożliwiały instalację aplikacji z nieznanych źródeł:** nie musisz konfigurować tego ustawienia, ponieważ urządzenia z programem Android for Work zawsze ograniczają instalację z nieznanych źródeł. .
- **Wymagaj, aby debugowanie USB było wyłączone**: nie musisz konfigurować tego ustawienia, ponieważ debugowanie USB w urządzeniach z programem Android for Work zostało już wyłączone.
- **Minimalny poziom poprawek zabezpieczeń systemu Android**: użyj tego ustawienia, aby określić minimalny poziom poprawek bezpieczeństwa systemu Android. Urządzenia, które nie mają co najmniej tego poziomu poprawek, będą niezgodne. Data musi mieć określony format: RRRR-MM-DD.
- **Wymagaj włączonej ochrony urządzenia przed zagrożeniami**: użyj tego ustawienia, aby uzyskać ocenę ryzyka z rozwiązania Lookout MTP jako warunek zgodności. Wybierz maksymalny dozwolony poziom zagrożenia, który będzie miał jedną z następujących wartości:
  - **Brak (zabezpieczone)** — to ustawienie zapewnia najwyższy poziom zabezpieczeń. Oznacza to, że urządzenie nie może mieć żadnych zagrożeń. Jeśli urządzenie zostanie wykryte jako posiadające dowolny poziom zagrożenia, zostanie ono ocenione jako niezgodne.
  - **Niski**: urządzenie jest oceniane jako zgodne, jeśli istnieją tylko zagrożenia niskiego poziomu. Jakiekolwiek zagrożenia wyższego poziomu spowodują, że urządzenie będzie miało status urządzenia niezgodnego.
  - **Średni**: urządzenie jest oceniane jako zgodne, jeśli dotyczące go zagrożenia są na poziomie niskim lub średnim. W przypadku wykrycia na urządzeniu zagrożeń wysokiego poziomu zostanie ono określone jako niezgodne.
  - **Wysoki** to ustawienie zapewnia najniższy poziom zabezpieczeń. Zasadniczo to ustawienie zezwala na wszystkie poziomy zagrożeń i może być przydatne tylko wtedy, jeśli jest używane jedynie na potrzeby raportowania.

Aby uzyskać więcej informacji, zobacz [Włączanie reguły ochrony urządzenia przed zagrożeniami w zasadach zgodności](https://docs.microsoft.com/intune-classic/deploy-use/enable-device-threat-protection-rule-in-compliance-policy).

## <a name="device-property-settings"></a>Ustawienia właściwości urządzenia

- **Wymagana minimalna wersja systemu operacyjnego:** jeśli urządzenie nie spełnia wymagań dotyczących minimalnej wersji systemu operacyjnego, będzie zgłaszane jako niezgodne. Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik końcowy może zdecydować się na uaktualnienie swojego urządzenia, co umożliwi mu dostęp do zasobów firmy.
- **Dozwolona maksymalna wersja systemu operacyjnego:** jeśli urządzenie korzysta z wersji systemu operacyjnego późniejszej niż określona w regule, powoduje to zablokowanie dostępu do zasobów firmy i wyświetlenie monitu o kontakt z administratorem IT. Do momentu zmiany reguły dopuszczającej daną wersję systemu operacyjnego urządzenie nie może być stosowane do uzyskiwania dostępu do zasobów firmy.

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->
