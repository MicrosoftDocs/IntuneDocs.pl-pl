---
title: "Ustawienia zasad zgodności dla systemu Android | Microsoft Docs"
description: "W tym temacie opisano ustawienia zasad zgodności urządzeń dla urządzeń z systemem Android."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 06996ca5d6c330357d6fdee19963d425bc353070
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---


# <a name="compliance-policy-settings-for-android-devices-in-microsoft-intune"></a>Ustawienia zasad zgodności dla urządzeń z systemem Android w usłudze Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ustawienia zasad opisane w tym temacie dotyczą urządzeń z systemem Android 4.0 i nowszymi wersjami lub Samsung KNOX 4.0 i nowszymi wersjami.

Jeśli szukasz informacji o innych platformach, wybierz jedną z następujących opcji:
> [!div class="op_single_selector"]
- [Ustawienia zasad zgodności dla urządzeń z systemem iOS](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Ustawienia zasad zgodności dla urządzeń z systemem Windows](windows-compliance-policy-settings-in-microsoft-intune.md)
- [Ustawienia zasad zgodności dla urządzeń z programem Android for Work](afw-compliance-policy-settings-in-microsoft-intune.md)

## <a name="system-security-settings"></a>Ustawienia zabezpieczeń systemu
### <a name="password"></a>Hasło
- **Wymagaj hasła do odblokowania urządzeń przenośnych:** ustaw tę pozycję na wartość **Tak**, aby wymagać od użytkowników podania hasła przed uzyskaniem dostępu do swojego urządzenia.

-  **Minimalna długość hasła:** Określ minimalną liczbę cyfr lub znaków, które musi zawierać hasło użytkownika.

- **Jakość hasła:** to ustawienie wykrywa, czy określone przez Ciebie wymagania dotyczące hasła zostały skonfigurowane na urządzeniu. Włącz to ustawienie, aby wymagać od użytkowników spełnienia pewnych wymagań dotyczących haseł dla urządzeń z systemem Android. Wybierz spośród opcji:

  -   **Zabezpieczenia biometryczne na niskim poziomie**
  -   **Wymagane**
  -   **Co najmniej numeryczne**
  -   **Co najmniej alfabetyczne**
  -   **Co najmniej alfanumeryczne**
  -   **Alfanumeryczne z symbolami**

- **Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła:** określ czas bezczynności, po którym użytkownik musi ponownie wprowadzić swoje hasło.

- **Wygaśnięcie hasła (dni):** wybierz liczbę dni, po których wygasa hasło użytkownika i należy utworzyć nowe.

- **Pamiętaj historię haseł:** używaj tego ustawienia w połączeniu z ustawieniem **Zapobiegaj ponownemu używaniu poprzednich haseł**, aby uniemożliwić użytkownikowi ponowne używanie wcześniej utworzonych haseł.

- **Zapobiegaj ponownemu używaniu poprzednich haseł:** określ liczbę uprzednio używanych haseł, które nie mogą być ponownie używane (jeśli zaznaczono pozycję **Pamiętaj historię haseł**).

- **Wymagaj hasła, gdy urządzenie powraca ze stanu bezczynności:** używaj tego ustawienia razem z ustawieniem **Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**. Użytkownicy otrzymają monit o wprowadzenie hasła w celu uzyskania dostępu do urządzenia, które było nieaktywne przez czas określony w ustawieniu **Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**.

### <a name="encryption"></a>Szyfrowanie
- **Wymagaj szyfrowania na urządzeniu przenośnym:** ustaw tę pozycję na wartość **Tak**, aby wymagać zaszyfrowania urządzenia w celu połączenia się z zasobami. Urządzenia są szyfrowane po skonfigurowaniu ustawienia **Wymagaj hasła do odblokowania urządzeń przenośnych**.

## <a name="device-health-and-security-settings"></a>Kondycja urządzeń i ustawienia zabezpieczeń

- **Nie zezwalaj na zdjęcie zabezpieczeń systemu ani na uzyskanie dostępu do konta root:** w przypadku włączenia tego ustawienia urządzenia ze zdjętymi zabezpieczeniami systemu są oceniane jako niezgodne.
- **Wymagaj zapobiegania instalacji aplikacji z nieznanych źródeł (Android 4.0 i nowsze):** aby zablokować urządzenia z włączonym ustawieniem **Bezpieczeństwo > Nieznane źródła**, włącz to ustawienie i wybierz opcję **Tak**.  

>[!IMPORTANT]
>Aplikacje ładowania bezpośredniego wymagają włączenia ustawienia **Nieznane źródła**. Te zasady zgodności należy włączyć tylko w przypadku braku bezpośredniego ładowania aplikacji Android na urządzeniach.

- **Wymagaj wyłączenia debugowania USB (Android 4.2 i nowsze):** określ, czy należy wykrywać włączenie opcji debugowania USB na urządzeniu.
- **Wymagaj włączenia na urządzeniach opcji Skanuj urządzenie pod kątem zagrożeń zabezpieczeń (Android 4.2–4.4)**: określ, czy funkcja **Weryfikuj aplikacje** została włączona na urządzeniu.
- **Minimalny poziom poprawek bezpieczeństwa (Android 6.0 i nowsze)**: określ minimalny poziom poprawek bezpieczeństwa systemu Android.  Urządzenia, które nie mają co najmniej tego poziomu poprawek, będą niezgodne. Data musi mieć następujący format: RRRR-MM-DD.
- **Wymagaj włączonej ochrony urządzenia przed zagrożeniami**: Użyj tego ustawienia, aby uzyskać ocenę ryzyka z rozwiązania Lookout MTP jako warunku zgodności. Wybierz maksymalny dozwolony poziom zagrożenia, który będzie miał jedną z następujących wartości:

  - **Brak (zabezpieczone)** — to ustawienie zapewnia najwyższy poziom zabezpieczeń. Oznacza to, że urządzenie nie może mieć żadnych zagrożeń. Urządzenie wykryte jako posiadające zagrożenia zostanie ocenione jako niezgodne.
  - **Niski**: urządzenie jest oceniane jako zgodne, jeśli istnieją tylko zagrożenia niskiego poziomu. Jakiekolwiek zagrożenia wyższego poziomu spowodują, że urządzenie będzie miało stan urządzenia niezgodnego.
  - **Średni**: urządzenie jest oceniane jako zgodne, jeśli dotyczące go zagrożenia są na poziomie niskim lub średnim. W przypadku wykrycia na urządzeniu zagrożeń wysokiego poziomu zostanie ono określone jako niezgodne.
  - **Wysoki** to ustawienie zapewnia najniższy poziom zabezpieczeń. Zasadniczo to ustawienie zezwala na wszystkie poziomy zagrożeń i może być przydatne tylko wtedy, gdy to rozwiązanie jest używane jedynie na potrzeby raportowania.

  Aby uzyskać więcej szczegółów, zobacz [Tworzenie zasad zgodności urządzeń z rozwiązaniem Lookout](create-lookout-device-compliance-policy.md).

## <a name="device-property-settings"></a>Ustawienia właściwości urządzenia

- **Wymagana minimalna wersja systemu operacyjnego:** jeśli urządzenie nie spełnia wymagań dotyczących minimalnej wersji systemu operacyjnego, będzie zgłaszane jako niezgodne.
  Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik może zdecydować się na uaktualnienie swojego urządzenia, co umożliwi mu dostęp do zasobów firmy.

- **Dozwolona maksymalna wersja systemu operacyjnego:** jeśli urządzenie korzysta z wersji systemu operacyjnego nowszej niż określona w regule, powoduje to zablokowanie dostępu do zasobów firmy i wyświetlenie monitu o kontakt z administratorem IT. Do momentu zmiany reguły dopuszczającej daną wersję systemu operacyjnego urządzenie nie może być stosowane do uzyskiwania dostępu do zasobów firmy.
