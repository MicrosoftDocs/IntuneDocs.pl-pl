---
title: "Ustawienia zgodności programu Android for Work | Microsoft Docs"
description: "W tym temacie opisano ustawienia zasad zgodności urządzeń dla urządzeń z systemem Android, które są zgodne z programem Android for Work."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 31e28514ab4bdb0f5af261a1f7c87633ca0bd4a6
ms.openlocfilehash: 1b84b7137bd01b695d20bea67d77c694f2533b4e


---


# <a name="compliance-policy-settings-for-android-for-work-devices-in-microsoft-intune"></a>Ustawienia zasad zgodności dla urządzeń z systemem Android for Work w usłudze Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ustawienia zasad opisane w tym temacie dotyczą urządzeń z programem Android for Work.

Jeśli szukasz informacji o innych platformach, wybierz jedną z następujących opcji:
> [!div class="op_single_selector"]
- [Ustawienia zasad zgodności dla systemu Android](android-compliance-policy-settings-in-microsoft-intune.md)
- [Ustawienia zasad zgodności dla urządzeń z systemem iOS](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Ustawienia zasad zgodności dla urządzeń z systemem Windows](windows-compliance-policy-settings-in-microsoft-intune.md)

## <a name="system-security-settings"></a>Ustawienia zabezpieczeń systemu
### <a name="password"></a>Hasło
- **Wymagaj hasła do odblokowania urządzeń przenośnych:** ustaw tę pozycję na wartość **Tak**, aby wymagać od użytkowników podania hasła przed uzyskaniem dostępu do swojego urządzenia.

-  **Minimalna długość hasła:** Określ minimalną liczbę cyfr lub znaków, które musi zawierać hasło użytkownika.

- **Jakość hasła:** to ustawienie wykrywa, czy określone przez Ciebie wymagania dotyczące hasła zostały skonfigurowane na urządzeniu. Włącz to ustawienie, aby wymagać od użytkowników skonfigurowania pewnych wymagań dotyczących haseł dla urządzeń z systemem Android. Wybierz spośród opcji:
  -   **Zabezpieczenia biometryczne na niskim poziomie**
  - **Wymagane**
  -   **Co najmniej numeryczne**
  -   **Co najmniej alfabetyczne**
  -   **Co najmniej alfanumeryczne**
  -   **Alfanumeryczne z symbolami**

- **Liczba minut braku aktywności, zanim będzie wymagane hasło:** określa czas bezczynności, po którym użytkownik musi ponownie wprowadzić swoje hasło.

- **Wygaśnięcie hasła (dni):** wybierz liczbę dni, po których wygasa hasło użytkownika i należy utworzyć nowe.

- **Pamiętaj historię haseł:** używaj tego ustawienia w połączeniu z ustawieniem **Zapobiegaj ponownemu używaniu poprzednich haseł**, aby uniemożliwić użytkownikowi ponowne używanie wcześniej utworzonych haseł.

- **Zapobiegaj ponownemu używaniu poprzednich haseł:** jeśli jest zaznaczona opcja **Pamiętaj historię haseł**, określ liczbę uprzednio używanych haseł, które nie mogą być ponownie używane.

- **Wymagaj hasła, gdy urządzenie powraca ze stanu bezczynności:** tego ustawienia należy używać razem z ustawieniem **Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**. Użytkownicy końcowi otrzymają monit o wprowadzenie hasła w celu uzyskania dostępu do urządzenia, które było nieaktywne przez czas określony w ustawieniu **Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**.

### <a name="encryption"></a>Encryption
- **Wymagaj szyfrowania na urządzeniu przenośnym:** nie musisz konfigurować tego ustawienia, ponieważ urządzenia z programem Android for Work wymuszają szyfrowanie.

## <a name="device-health-and-security-settings"></a>Kondycja urządzeń i ustawienia zabezpieczeń

- **Nie zezwalaj na zdjęcie zabezpieczeń systemu ani na uzyskanie dostępu do konta root:** w przypadku włączenia tego ustawienia urządzenia ze zdjętymi zabezpieczeniami systemu zostaną ocenione jako niezgodne.
- **Wymagaj, aby urządzenia uniemożliwiały instalację aplikacji z nieznanych źródeł:** nie musisz konfigurować tego ustawienia, ponieważ urządzenia z programem Android for Work zawsze ograniczają instalację z nieznanych źródeł. .  

- **Wymagaj, aby debugowanie USB było wyłączone**: nie musisz konfigurować tego ustawienia, ponieważ debugowanie USB w urządzeniach z programem Android for Work zostało już wyłączone.

- **Minimalny poziom poprawek zabezpieczeń systemu Android**: użyj tego ustawienia, aby określić minimalny poziom poprawek bezpieczeństwa systemu Android.  Urządzenia, które nie mają co najmniej tego poziomu poprawek, będą niezgodne. Data musi mieć określony format: RRRR-MM-DD.
- **Wymagaj włączonej ochrony urządzenia przed zagrożeniami**: użyj tego ustawienia, aby uzyskać ocenę ryzyka z rozwiązania do ochrony urządzenia przed zagrożeniami jako warunku zgodności. Wybierz maksymalny dozwolony poziom zagrożenia, który będzie miał jedną z następujących wartości:

  - **Brak (zabezpieczone)** — to ustawienie zapewnia najwyższy poziom zabezpieczeń. Oznacza to, że urządzenie nie może mieć żadnych zagrożeń. Jeśli urządzenie zostanie wykryte jako posiadające dowolny poziom zagrożenia, zostanie ono ocenione jako niezgodne.
  - **Niski**: urządzenie jest oceniane jako zgodne, jeśli istnieją tylko zagrożenia niskiego poziomu. Jakiekolwiek zagrożenia wyższego poziomu spowodują, że urządzenie będzie miało status urządzenia niezgodnego.
  - **Średni**: urządzenie jest oceniane jako zgodne, jeśli dotyczące go zagrożenia są na poziomie niskim lub średnim. W przypadku wykrycia na urządzeniu zagrożeń wysokiego poziomu zostanie ono określone jako niezgodne.
  - **Wysoki** to ustawienie zapewnia najniższy poziom zabezpieczeń. Zasadniczo to ustawienie zezwala na wszystkie poziomy zagrożeń i może być przydatne tylko wtedy, jeśli jest używane jedynie na potrzeby raportowania.

  Aby uzyskać więcej informacji, zobacz [Włączanie reguły ochrony urządzenia przed zagrożeniami w zasadach zgodności](enable-device-threat-protection-rule-in-compliance-policy.md).

## <a name="device-property-settings"></a>Ustawienia właściwości urządzenia
- **Wymagana minimalna wersja systemu operacyjnego:** jeśli urządzenie nie spełnia wymagań dotyczących minimalnej wersji systemu operacyjnego, będzie zgłaszane jako niezgodne.
  Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik końcowy może zdecydować się na uaktualnienie swojego urządzenia, co umożliwi mu dostęp do zasobów firmy.

- **Dozwolona maksymalna wersja systemu operacyjnego:** jeśli urządzenie korzysta z wersji systemu operacyjnego nowszej niż określona w regule, powoduje to zablokowanie dostępu do zasobów firmy i wyświetlenie monitu o kontakt z administratorem IT. Do momentu zmiany reguły dopuszczającej daną wersję systemu operacyjnego urządzenie nie może być stosowane do uzyskiwania dostępu do zasobów firmy.



<!--HONumber=Feb17_HO1-->


