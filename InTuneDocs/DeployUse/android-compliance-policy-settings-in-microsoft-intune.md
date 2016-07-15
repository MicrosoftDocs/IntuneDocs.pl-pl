---
title: "Ustawienia zasad zgodności dla urządzeń z systemem Android | Microsoft Intune"
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
ms.reviewer: chrisgre
ms.suite: ems
ms.sourcegitcommit: e736d688032dd2ddee5be9edf2a33d5e7ba5257b
ms.openlocfilehash: dd3369cf59ea972f1ecc4953881ddbbede9a99c8


---


# Ustawienia zasad zgodności dla urządzeń z systemem Android w usłudze Microsoft Intune

Ustawienia zasad opisane w tym temacie dotyczą urządzeń z systemem Android 4.0 i nowszymi wersjami lub Samsung KNOX 4.0 i nowszymi wersjami.

Jeśli szukasz informacji o innych platformach, wybierz jedną z następujących opcji:
> [!div class="op_single_selector"]
- [Ustawienia zasad zgodności dla urządzeń z systemem iOS](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Ustawienia zasad zgodności dla urządzeń z systemem Windows](windows-compliance-policy-settings-in-microsoft-intune.md)

## Ustawienia zabezpieczeń systemu
### Hasło
- **Wymagaj hasła do odblokowania urządzeń przenośnych:** ustaw tę pozycję na wartość **Tak**, aby wymagać od użytkowników podania hasła przed uzyskaniem dostępu do swojego urządzenia.

-  **Minimalna długość hasła:** Określ minimalną liczbę cyfr lub znaków, które musi zawierać hasło użytkownika.

- **Jakość hasła:** Włącz to ustawienie, aby skonfigurować wymagania dotyczące haseł dla urządzeń z systemem Android. Wybierz spośród opcji:
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

### Szyfrowanie
- **Wymagaj szyfrowania na urządzeniu przenośnym:** ustaw tę pozycję na wartość **Tak**, aby wymagać zaszyfrowania urządzenia w celu połączenia się z zasobami. Urządzenia są szyfrowane po skonfigurowaniu ustawienia **Wymagaj hasła do odblokowania urządzeń przenośnych**.

## Ustawienia kondycji urządzenia

- **Nie zezwalaj na zdjęcie zabezpieczeń systemu ani na uzyskanie dostępu do konta root:** w przypadku włączenia tego ustawienia urządzenia ze zdjętymi zabezpieczeniami systemu zostaną ocenione jako niezgodne.

## Ustawienia właściwości urządzenia
- **Wymagana minimalna wersja systemu operacyjnego:** jeśli urządzenie nie spełnia wymagań dotyczących minimalnej wersji systemu operacyjnego, będzie zgłaszane jako niezgodne.
  Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik końcowy może zdecydować się na uaktualnienie swojego urządzenia, co umożliwi mu dostęp do zasobów firmy.

- **Dozwolona maksymalna wersja systemu operacyjnego:** jeśli urządzenie korzysta z wersji systemu operacyjnego późniejszej niż określona w regule, powoduje to zablokowanie dostępu do zasobów firmy i wyświetlenie monitu o kontakt z administratorem IT. Do momentu zmiany reguły dopuszczającej daną wersję systemu operacyjnego urządzenie nie może być stosowane do uzyskiwania dostępu do zasobów firmy.



<!--HONumber=Jul16_HO1-->


