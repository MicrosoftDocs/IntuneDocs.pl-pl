---
title: "Tworzenie zasad zgodności dla systemu iOS"
titleSuffix: Intune on Azure
description: "Informacje dotyczące tworzenia zasad zgodności dla urządzeń z systemem iOS."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9337586ad5daa909f38aba2b25fc159b44f55e65
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-create-a-device-compliance-policy-for-ios-devices-in-intune"></a>Tworzenie zasad zgodności dla urządzeń z systemem iOS w usłudze Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Zasady zgodności są tworzone dla każdej platformy.  Zasady zgodności można tworzyć w witrynie Azure Portal. Aby dowiedzieć się więcej na temat tego, czym są zasady zgodności, zobacz artykuł [What is a device compliance](device-compliance.md) (Czym jest zgodność z urządzeniem). Aby dowiedzieć się więcej o wymaganiach wstępnych, które należy spełnić przed utworzeniem zasad zgodności, zobacz artykuł [Get started with device compliance](device-compliance-get-started.md) (Wprowadzenie do zgodności z urządzeniem).

W tabeli poniżej opisano sposób postępowania z niezgodnymi ustawieniami w przypadku, gdy zasady zgodności są używane wraz z zasadami dostępu warunkowego.

-------------------------------


| **Ustawienie zasad** | **System iOS 8.0 lub nowszy** |
| --- | --- |
| **Konfiguracja kodu PIN lub hasła** | Skorygowane |   
| **Szyfrowanie urządzenia** | Skorygowane (przez ustawienie kodu PIN) |
| **Urządzenie ze złamanymi ograniczeniami lub z odblokowanym dostępem** | Poddane kwarantannie (to nie jest ustawienie)
| **Profil e-mail** | Poddane kwarantannie |
|**Minimalna wersja systemu operacyjnego** | Poddane kwarantannie |
| **Maksymalna wersja systemu operacyjnego** | Poddane kwarantannie |  
| **Zaświadczanie o kondycji systemu Windows** | Nie dotyczy |  
----------------------------


**Skorygowane** — system operacyjny urządzenia wymusza zgodność. (Na przykład użytkownik jest zmuszony do ustawienia kodu PIN).

**Poddane kwarantannie** — system operacyjny urządzenia nie wymusza zgodności. (Na przykład urządzenie z systemem Android nie zmusza użytkownika do szyfrowania urządzenia). Gdy urządzenia nie są zgodne, zostaną wykonane następujące akcje:

- Urządzenie zostanie zablokowane, jeśli użytkownik podlega zasadom dostępu warunkowego.
- Portal firmy powiadomi użytkownika o wszelkich problemach ze zgodnością.

## <a name="create-a-compliance-policy-in-the-azure-portal"></a>Tworzenie zasad zgodności w witrynie Azure Portal

1. W bloku **Intune** wybierz pozycję **Ustaw zgodność urządzenia**. W obszarze **Zarządzaj** wybierz pozycję **Wszystkie zasady zgodności urządzeń** i wybierz przycisk **Utwórz**.
2. Wpisz nazwę, opis i wybierz platformę, której te zasady mają dotyczyć.
3. Wybierz pozycję **Wymagania zgodności**, aby określić ustawienia **Zabezpieczenia**, **Kondycja urządzenia** i **Właściwości urządzenia**, a gdy wszystko będzie gotowe, wybierz przycisk **Ok**.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** blade, choose **Add** to create a new action.  The action parameters blade allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
7. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="assign-user-groups"></a>Przypisywanie grup użytkowników

Aby przypisać użytkownikom zasady zgodności, wybierz skonfigurowane przez siebie zasady. Istniejące zasady znajdują się w bloku **Zgodność — zasady**.

1. Wybierz zasady, które chcesz przypisać użytkownikom, a następnie wybierz pozycję **Przypisania**. Spowoduje to otwarcie bloku, w którym można wybrać **grupy zabezpieczeń usługi Azure Active Directory** i przypisać je do zasad.
2. Wybierz pozycję **Wybierz grupy**, aby otworzyć blok, w którym zostaną wyświetlone grupy zabezpieczeń usługi Azure AD.  Wybranie pozycji **Wybierz** powoduje wdrożenie zasad dla użytkowników.

Zasady zostały zastosowane do użytkowników.  Urządzenia, którymi posługują się użytkownicy objęci zasadami, zostaną ocenione pod kątem zgodności.

<!---## Compliance policy settings--->

## <a name="system-security-settings"></a>Ustawienia zabezpieczeń systemu

### <a name="password"></a>Hasło

- **Wymagaj hasła do odblokowania urządzeń przenośnych:** ustaw tę opcję na wartość **Tak**, aby wymagać od użytkowników podania hasła przed uzyskaniem dostępu do swoich urządzeń. Urządzenia z systemem iOS używające haseł są szyfrowane.
- **Zezwalaj na proste hasła**: ustaw tę opcję na wartość **Tak**, aby zezwolić użytkownikom na tworzenie prostych haseł, takich jak **1234** lub **1111**.
- **Minimalna długość hasła**: określ minimalną liczbę cyfr lub znaków, które musi zawierać hasło.
- **Wymagany typ hasła**: określ, czy użytkownicy muszą tworzyć hasła **alfanumeryczne** czy też **numeryczne**.
- **Minimalna liczba zestawów znaków**: jeśli parametr **Wymagany typ hasła** ma wartość **Alfanumeryczne**, ustawienie to określa minimalną liczbę zestawów znaków użytych w haśle. Są cztery zestawy znaków:
  - Małe litery
  - Wielkie litery
  - Symbole
  - Liczby

Ustawienie większej liczby spowoduje wymaganie wprowadzenia bardziej skomplikowanego hasła przez użytkownika.

W przypadku urządzeń z systemem iOS to ustawienie oznacza liczbę znaków specjalnych (na przykład **!** , **#**, **&amp;**), które muszą znajdować się w haśle.

- **Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**: określ czas bezczynności, po którym użytkownik musi ponownie wprowadzić hasło.
- **Wygaśnięcie hasła (w dniach)**: wybierz liczbę dni, po których hasło wygasa i należy utworzyć nowe.
- **Pamiętaj historię haseł**: używaj tego ustawienia w połączeniu z ustawieniem **Zapobiegaj ponownemu używaniu poprzednich haseł**, aby uniemożliwić użytkownikowi ponowne używanie wcześniej utworzonych haseł.
- **Zapobiegaj ponownemu używaniu poprzednich haseł**: jeśli jest zaznaczona opcja **Pamiętaj historię haseł**, określ liczbę uprzednio używanych haseł, które nie mogą być ponownie używane.
- **Wymagaj hasła, gdy urządzenie powraca ze stanu bezczynności**: tego ustawienia należy używać razem z ustawieniem **Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**. Użytkownik otrzyma monit o wprowadzenie hasła w celu uzyskania dostępu do urządzenia, które było nieaktywne przez czas określony w ustawieniu **Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**.

### <a name="email-profile"></a>Profil e-mail

- **Konto e-mail musi być zarządzane przez usługę Intune**: jeśli ta opcja została ustawiona na **Tak**, urządzenie musi używać profilu poczty e-mail wdrożonego na urządzeniu. Urządzenie jest uznawane za niezgodne w następujących sytuacjach:
  - Profil poczty e-mail jest wdrażany w innej grupie użytkowników niż grupa, której dotyczą zasady zgodności.
  - Użytkownik skonfigurował już na urządzeniu konto e-mail zgodne z profilem poczty e-mail usługi Intune wdrożonym na urządzeniu. Usługa Intune nie może zastąpić profilu określonego przez użytkownika i dlatego nie może nim zarządzać. W celu zapewnienia zgodności użytkownik musi usunąć istniejące ustawienia poczty e-mail. Umożliwi to usłudze Intune zainstalowanie zarządzanego profilu poczty e-mail.
- **Wybierz profil poczty e-mail, który ma być zarządzany przez usługę Intune**: jeśli zaznaczona jest opcja **Konto e-mail musi być zarządzane przez usługę Intune**, kliknij pozycję **Wybierz**, aby określić profil poczty e-mail usługi Intune. Ten profil poczty e-mail musi znajdować się na urządzeniu.

Aby uzyskać szczegółowe informacje na temat profilów poczty e-mail, zobacz artykuł [Konfigurowanie dostępu do firmowej poczty e-mail przy użyciu profilów poczty e-mail w usłudze Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune).

## <a name="device-health-settings"></a>Ustawienia kondycji urządzenia

- **Nie zezwalaj na zdjęcie zabezpieczeń systemu ani na uzyskanie dostępu do konta root**: w przypadku włączenia tego ustawienia urządzenia ze zdjętymi zabezpieczeniami systemu nie będą zgodne.

## <a name="device-properties"></a>Właściwości urządzenia

- **Wymagana minimalna wersja systemu operacyjnego**: jeśli urządzenie nie spełnia wymagań dotyczących minimalnej wersji systemu operacyjnego, będzie zgłaszane jako niezgodne. Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik może wybrać opcję uaktualnienia urządzenia, co umożliwi korzystanie z zasobów firmy.
- **Dozwolona maksymalna wersja systemu operacyjnego**: jeśli urządzenie korzysta z wersji systemu operacyjnego nowszej niż określona w regule, powoduje to zablokowanie dostępu do zasobów firmy i wyświetlenie monitu o kontakt z administratorem IT. Do momentu zmiany reguły dopuszczającej daną wersję systemu operacyjnego urządzenie nie może być stosowane do uzyskiwania dostępu do zasobów firmy.

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->
