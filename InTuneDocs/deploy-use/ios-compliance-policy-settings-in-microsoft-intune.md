---
title: "Ustawienia zasad zgodności dla urządzeń z systemem iOS | Microsoft Docs"
description: "W tym temacie opisano reguły i ustawienia, które można skonfigurować w zasadach zgodności dla urządzeń z systemem iOS."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a59d24f-ed58-49b1-b874-b2d4aea3ec76
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b068da7685792757825a4bc0d555e28ee0168cb1
ms.openlocfilehash: f09ad4f705d152b25918ca477b97cf7b1df7bfc8


---


# <a name="compliance-policy-settings-for-ios-devices-in-microsoft-intune"></a>Ustawienia zasad zgodności dla urządzeń z systemem iOS w usłudze Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ustawienia zasad opisane w tym temacie dotyczą urządzeń z systemem iOS w wersji 8.0 lub nowszej.

Jeśli szukasz informacji o innych platformach, wybierz jedną z następujących opcji:
> [!div class="op_single_selector"]
- [Ustawienia zasad zgodności dla urządzeń z systemem Android](android-compliance-policy-settings-in-microsoft-intune.md)
- [Ustawienia zasad zgodności dla programu Android for Work](afw-compliance-policy-settings-in-microsoft-intune.md)
- [Ustawienia zasad zgodności dla urządzeń z systemem Windows](windows-compliance-policy-settings-in-microsoft-intune.md)

## <a name="system-security-settings"></a>Ustawienia zabezpieczeń systemu
### <a name="password"></a>Hasło
- **Wymagaj hasła do odblokowania urządzeń przenośnych:** ustaw tę opcję na wartość **Tak**, aby wymagać od użytkowników podania hasła przed uzyskaniem dostępu do swoich urządzeń. Urządzenia z systemem iOS używające haseł są szyfrowane.

- **Zezwalaj na proste hasła:** ustaw tę opcję na wartość **Tak**, aby zezwolić użytkownikom na tworzenie prostych haseł, takich jak **1234** lub **1111**.

-  **Minimalna długość hasła:** Określ minimalną liczbę cyfr lub znaków, które musi zawierać hasło użytkownika.

- **Wymagany typ hasła:** określ, czy użytkownicy muszą utworzyć hasła **alfanumeryczne** czy też **numeryczne**.

- **Minimalna liczba zestawów znaków:** jeśli parametr **Wymagany typ hasła** ma wartość **Alfanumeryczne**, ustawienie to określa minimalną liczbę zestawów znaków użytych w haśle. Są cztery zestawy znaków:
  -   Małe litery
  -   Wielkie litery
  -   Symbole
  -   Liczby

  Ustawienie większej liczby spowoduje wymaganie wprowadzenia bardziej skomplikowanego hasła przez użytkownika.

  W przypadku urządzeń z systemem iOS to ustawienie oznacza liczbę znaków specjalnych (na przykład **!**, **#**, **&amp;**), które muszą znaleźć się w haśle.

- **Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła:** określ czas bezczynności, po którym użytkownik musi ponownie wprowadzić swoje hasło.

- **Wygaśnięcie hasła (dni):** wybierz liczbę dni, po których wygasa hasło użytkownika i należy utworzyć nowe.

- **Pamiętaj historię haseł:** użyj tego ustawienia w połączeniu z ustawieniem **Zapobiegaj ponownemu używaniu poprzednich haseł**, aby uniemożliwić użytkownikowi ponowne używanie wcześniej utworzonych haseł.

- **Zapobiegaj ponownemu używaniu poprzednich haseł:** jeśli jest zaznaczona opcja **Pamiętaj historię haseł**, określ liczbę uprzednio używanych haseł, które nie mogą być ponownie używane.

- **Wymagaj hasła, gdy urządzenie powraca ze stanu bezczynności:** tego ustawienia należy używać razem z ustawieniem **Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**. Użytkownik otrzyma monit o wprowadzenie hasła w celu uzyskania dostępu do urządzenia, które było nieaktywne przez czas określony w ustawieniu **Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**.

### <a name="email-profile"></a>Profil e-mail
- **Konto e-mail musi być zarządzane przez usługę Intune:** jeśli ta opcja została ustawiona na **Tak**, urządzenie musi używać profilu poczty e-mail wdrożonego na urządzeniu. Urządzenie jest uznawane za niezgodne w następujących sytuacjach:
  - Profil poczty e-mail jest wdrażany w innej grupie użytkowników niż grupa, której dotyczą zasady zgodności.
  - Użytkownik skonfigurował już na urządzeniu konto e-mail zgodne z profilem poczty e-mail usługi Intune wdrożonym na urządzeniu. Usługa Intune nie może zastąpić profilu określonego przez użytkownika i dlatego nie może nim zarządzać. W celu zapewnienia zgodności użytkownik musi usunąć istniejące ustawienia poczty e-mail. Umożliwi to usłudze Intune zainstalowanie zarządzanego profilu poczty e-mail.

- **Wybierz profil poczty e-mail, który ma być zarządzany przez usługę Intune:** jeśli zaznaczona jest opcja **Konto e-mail musi być zarządzane przez usługę Intune**, kliknij pozycję **Wybierz**, aby określić profil poczty e-mail usługi Intune. Ten profil poczty e-mail musi znajdować się na urządzeniu.

     Aby uzyskać szczegółowe informacje na temat profilów poczty e-mail, zobacz [Konfigurowanie dostępu do firmowej poczty e-mail przy użyciu profilów poczty e-mail w usłudze Microsoft Intune](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).

## <a name="device-health-settings"></a>Ustawienia kondycji urządzenia

- **Nie zezwalaj na zdjęcie zabezpieczeń systemu ani na uzyskanie dostępu do konta root:** w przypadku włączenia tego ustawienia urządzenia ze zdjętymi zabezpieczeniami systemu nie będą zgodne.

##  <a name="device-properties"></a>Właściwości urządzenia
- **Wymagana minimalna wersja systemu operacyjnego:** jeśli urządzenie nie spełnia wymagań dotyczących minimalnej wersji systemu operacyjnego, będzie zgłaszane jako niezgodne.
Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik może wybrać opcję uaktualnienia urządzenia, co umożliwi korzystanie z zasobów firmy.

- **Dozwolona maksymalna wersja systemu operacyjnego:** jeśli urządzenie korzysta z wersji systemu operacyjnego nowszej niż określona w regule, powoduje to zablokowanie dostępu do zasobów firmy i wyświetlenie monitu o kontakt z administratorem IT. Do momentu zmiany reguły dopuszczającej daną wersję systemu operacyjnego urządzenie nie może być stosowane do uzyskiwania dostępu do zasobów firmy.



<!--HONumber=Dec16_HO3-->


