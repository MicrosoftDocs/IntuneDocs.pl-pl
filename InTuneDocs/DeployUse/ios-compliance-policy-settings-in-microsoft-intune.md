---
# required metadata

title: Ustawienia zasad zgodności dla urządzeń z systemem iOS | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4a59d24f-ed58-49b1-b874-b2d4aea3ec76

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisgre
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Ustawienia zasad zgodności dla urządzeń z systemem iOS w usłudze Microsoft Intune

Ustawienia zasad opisane w tym temacie dotyczą urządzeń z systemem iOS 6 i nowszymi wersjami.

Jeśli szukasz informacji o innych platformach, wybierz jedną z następujących opcji:
> [!div class="op_single_selector"]
- [Ustawienia zasad zgodności dla urządzeń z systemem Android](android-compliance-policy-settings-in-microsoft-intune.md)
- [Ustawienia zasad zgodności dla urządzeń z systemem Windows](windows-compliance-policy-settings-in-microsoft-intune.md)

## Ustawienia zabezpieczeń systemu
### Hasło
- **Wymagaj hasła do odblokowania urządzeń przenośnych:** ustaw tę opcję na wartość **Tak**, aby wymagać od użytkowników podania hasła przed uzyskaniem dostępu do swojego urządzenia. Urządzenia z systemem iOS używające haseł są szyfrowane.

- **Zezwalaj na proste hasła:** ustaw tę opcję na wartość **Tak**, aby zezwolić użytkownikom na tworzenie prostych haseł, takich jak „**1234**” lub „**1111**”.

-  **Minimalna długość hasła:** Określ minimalną liczbę cyfr lub znaków, które musi zawierać hasło użytkownika.
- **Wymagany typ hasła:** określ, czy użytkownicy muszą utworzyć hasła **alfanumeryczne**, czy też **numeryczne**.

- **Minimalna liczba zestawów znaków:** jeśli parametr **Wymagany typ hasła** ma wartość **Alfanumeryczne**, to ustawienie określa minimalną liczbę zestawów znaków użytych w haśle. Są cztery zestawy znaków:
  -   Małe litery
  -   Wielkie litery
  -   Symbole
  -   Liczby

  Im większa liczba zostanie podana dla tego ustawienia, tym bardziej skomplikowane hasła będą musieli tworzyć użytkownicy.

  W przypadku urządzeń z systemem iOS to ustawienie oznacza liczbę znaków specjalnych (na przykład **!**, **#**, **&amp;**), które muszą znaleźć się w haśle.
- **Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła:** określ czas bezczynności, po którym użytkownik musi ponownie wprowadzić swoje hasło.

- **Wygaśnięcie hasła (dni):** wybierz liczbę dni, po których wygasa hasło użytkownika i należy utworzyć nowe.

- **Pamiętaj historię haseł:** używaj tego ustawienia w połączeniu z ustawieniem **Zapobiegaj ponownemu używaniu poprzednich haseł**, aby uniemożliwić użytkownikowi ponowne używanie wcześniej utworzonych haseł.

- **Zapobiegaj ponownemu używaniu poprzednich haseł:** jeśli jest zaznaczona opcja **Pamiętaj historię haseł**, określ liczbę uprzednio używanych haseł, które nie mogą być ponownie używane.

- **Wymagaj hasła, gdy urządzenie powraca ze stanu bezczynności:** tego ustawienia należy używać razem z ustawieniem **Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**. Użytkownicy końcowi otrzymają monit o wprowadzenie hasła w celu uzyskania dostępu do urządzenia, które było nieaktywne przez czas określony w ustawieniu **Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**.

### Profil e-mail
- **Konto e-mail musi być zarządzane przez usługę Intune:** jeśli ta opcja została ustawiona na **Tak**, urządzenie musi używać zgodnych adresów e-mail wdrożonych na urządzeniu. Urządzenie jest uznawane za niezgodne w następujących sytuacjach:
  - Profil poczty e-mail musi również zostać wdrożony do tej samej grupy użytkowników, która została objęta zasadami zgodności. W przeciwnym razie urządzenia użytkowników będą uznane za niezgodne.
  - Urządzenia będą zgłaszane jako niezgodne, jeśli użytkownik skonfigurował już konto e-mail w urządzeniu zgodnym z profilem e-mail usługi Intune, który został wdrożony na urządzeniu. Usługa Intune nie może zastąpić profilu określonego przez użytkownika i dlatego nie może nim zarządzać. W celu zapewnienia zgodności, użytkownik musi usunąć istniejące ustawienia poczty e-mail, aby usługa Intune mogła zainstalować zarządzany profil poczty e-mail.


- **Wybierz profil poczty e-mail, który ma być zarządzany przez usługę Intune:**
   jeśli zaznaczona jest opcja **Konto e-mail musi być zarządzane przez usługę Intune**, kliknij pozycję **Wybierz**, aby określić profil poczty e-mail usługi Intune. Ten profil poczty e-mail musi znajdować się na urządzeniu.

     Aby uzyskać szczegółowe informacje na temat profilów poczty e-mail, zobacz [Konfigurowanie dostępu do firmowej poczty e-mail przy użyciu profilów poczty e-mail w usłudze Microsoft Intune](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).

## Ustawienia kondycji urządzenia

- **Nie zezwalaj na zdjęcie zabezpieczeń systemu ani na uzyskanie dostępu do konta root:** w przypadku włączenia tego ustawienia urządzenia ze zdjętymi zabezpieczeniami systemu nie będą zgodne.

##  Właściwości urządzenia
- **Wymagana minimalna wersja systemu operacyjnego:** jeśli urządzenie nie spełnia wymagań dotyczących minimalnej wersji systemu operacyjnego, będzie zgłaszane jako niezgodne.
Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik końcowy może zdecydować się na uaktualnienie swojego urządzenia, co powinno umożliwić mu dostęp do zasobów firmy.

- **Dozwolona maksymalna wersja systemu operacyjnego:** jeśli urządzenie korzysta z wersji systemu operacyjnego późniejszej niż określona w regule, powoduje to zablokowanie dostępu do zasobów firmy i wyświetlenie monitu o kontakt z administratorem IT. Do momentu zmiany reguły dopuszczającej daną wersję systemu operacyjnego urządzenie nie może być stosowane do uzyskiwania dostępu do zasobów firmy.


<!--HONumber=Jun16_HO2-->


