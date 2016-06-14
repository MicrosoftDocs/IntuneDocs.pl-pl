---
# required metadata

title: Ustawienia zasad zgodności dla urządzeń z systemem Android | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Ustawienia zasad zgodności dla urządzeń z systemem Android w usłudze Microsoft Intune

Ustawienia zasad opisane w tym temacie dotyczą urządzeń z systemem Android 4.0 i nowszymi wersjami lub Samsung KNOX 4.0 i nowszymi wersjami.

Jeśli szukasz informacji o innych platformach, wybierz jedną z następujących opcji:
> [!div class="op_single_selector"]
- [Ustawienia zasad zgodności dla urządzeń z systemem iOS](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Ustawienia zasad zgodności dla urządzeń z systemem Windows](windows-compliance-policy-settings-in-microsoft-intune.md)

## Ustawienia zabezpieczeń systemu
### Hasło
- **Wymagaj hasła do odblokowania urządzeń przenośnych:** Uustaw tę opcję na **Tak**, aby wymagać od użytkowników podania hasła przed
  uzyskaniem dostępu do urządzenia.

-  **Minimalna długość hasła:** Określ minimalną liczbę cyfr lub znaków, które musi zawierać hasło użytkownika.

- **Jakość hasła:** Włącz to ustawienie, aby skonfigurować wymagania dotyczące haseł dla urządzeń z systemem Android. Wybierz spośród opcji:
  -   **Zabezpieczenia biometryczne na niskim poziomie**
  - **Wymagane**
  -   **Co najmniej numeryczne**
  -   **Co najmniej alfabetyczne**
  -   **Co najmniej alfanumeryczne**
  -   **Alfanumeryczne z symbolami**

- **Liczba minut braku aktywności, zanim będzie wymagane hasło:** określa czas bezczynności, po którym użytkownik musi ponownie wprowadzić swoje hasło.

- **Wygaśnięcie hasła (dni):** Wybierz liczbę dni, po których hasło użytkownika wygasa
  i należy utworzyć nowe.

- **Pamiętaj historię haseł:** użyj tego ustawienia w połączeniu z ustawieniem **Zapobiegaj ponownemu używaniu poprzednich haseł**, aby uniemożliwić użytkownikowi
  ponowne używanie wcześniej utworzonych haseł.

- **Zapobiegaj ponownemu używaniu poprzednich haseł:** jeśli wybrano opcję **Pamiętaj historię haseł**, określ
  liczbę wcześniej używanych haseł, których nie można użyć ponownie.

- **Wymagaj hasła, gdy urządzenie powraca ze stanu bezczynności:**
  Tego ustawienia należy używać razem z ustawieniem **Liczba minut braku aktywności, zanim będzie wymagane hasło**. Użytkownicy końcowi otrzymają monit o wprowadzenie hasła w celu uzyskania dostępu do urządzenia, które było nieaktywne przez czas określony w ustawieniu
  **Liczba minut braku aktywności, zanim będzie wymagane hasło**.

### Szyfrowanie
- **Wymagaj szyfrowania na urządzeniu przenośnym:** Ustaw tę opcję na **Tak**, aby wymagać
  zaszyfrowania urządzenia w celu połączenia się z zasobami. Urządzenia są
  szyfrowane po skonfigurowaniu ustawienia **Wymagaj hasła do
  odblokowania urządzeń przenośnych**.

## Ustawienia kondycji urządzenia

- **Nie zezwalaj na zdjęcie zabezpieczeń systemu ani na uzyskanie dostępu do konta root:** w przypadku włączenia tego ustawienia
  urządzenia ze zdjętymi zabezpieczeniami systemu zostaną ocenione jako niezgodne.

## Ustawienia właściwości urządzenia
- **Wymagana minimalna wersja systemu operacyjnego:** jeśli urządzenie nie spełnia wymagań dotyczących minimalnej
  wersji systemu operacyjnego, zostaje zgłoszone jako niezgodne.
  Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik końcowy może zdecydować się na uaktualnienie swojego urządzenia, co umożliwi mu dostęp do zasobów firmy.

- **Dozwolona maksymalna wersja systemu operacyjnego:** jeśli urządzenie korzysta
  z wersji systemu operacyjnego nowszej niż określona w regule, powoduje to zablokowanie dostępu do zasobów firmy i wyświetlenie monitu o kontakt z administratorem IT. Do momentu zmiany reguły dopuszczającej daną wersję systemu operacyjnego urządzenie nie może być stosowane do uzyskiwania dostępu do zasobów firmy.


<!--HONumber=May16_HO1-->


