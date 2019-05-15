---
title: Ustawienia zgodności dla urządzeń z systemem iOS w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zapoznaj się z listą ustawień umożliwiających skonfigurowanie zgodności dla urządzeń z systemem iOS w usłudze Microsoft Intune. Możesz między innymi wymagać profilu poczty e-mail, sprawdzać urządzenia ze zdjętymi zabezpieczeniami systemu lub odblokowanym dostępem do konta root, ustawiać minimalną lub maksymalną wersję systemu operacyjnego, określać ograniczenia dotyczące haseł takie jak długość hasła czy czas nieaktywności urządzenia oraz ograniczać aplikacje.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/04/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6ec071622a2e0d49068864f8bfb47954f54c8ba4
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/09/2019
ms.locfileid: "59423615"
---
# <a name="ios-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Ustawienia urządzeń z systemem iOS umożliwiające oznaczenie ich jako zgodne lub niezgodne w usłudze Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

W tym artykule wymieniono i opisano różne ustawienia zgodności, które można skonfigurować na urządzeniach z systemem iOS za pomocą usługi Intune. Możesz stosować te ustawienia w ramach rozwiązania do zarządzania urządzeniami mobilnymi (MDM), aby między innymi wymagać profilu poczty e-mail, oznaczać urządzenia z odblokowanym dostępem do konta root lub zdjętymi zabezpieczeniami systemu jako niezgodne, określać dozwolony poziom zagrożenia, czy ustawiać wygasanie haseł.

Ta funkcja ma zastosowanie do:

- iOS

Jako administrator usługi Intune możesz użyć tych ustawień zgodności, aby chronić zasoby organizacji. Aby dowiedzieć się więcej na temat zasad zgodności i ich działania, zobacz [Wprowadzenie do zasad zgodności urządzeń](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz zasady zgodności](create-compliance-policy.md#create-the-policy). W polu **Platforma** wybierz opcję **iOS**.

## <a name="email"></a>Poczta e-mail

- **Wymagaj zarządzanego profilu poczty e-mail urządzeń przenośnych**: jeśli ustawisz opcję **Wymagaj**, urządzenia, których profil poczty e-mail nie jest zarządzany przez usługę Intune, będą traktowane jako niezgodne. Urządzenie nie może mieć zarządzanego profilu poczty e-mail, jeśli nie zostało przekazane właściwemu użytkownikowi docelowemu lub jeśli użytkownik ręcznie skonfigurował na nim konto e-mail. W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności.

  Urządzenie jest uznawane za niezgodne w następujących sytuacjach:

  - Profil poczty e-mail jest przypisany do innej grupy użytkowników niż grupa, której dotyczą zasady zgodności.
  - Użytkownik skonfigurował już na urządzeniu konto e-mail odpowiadające profilowi poczty e-mail usługi Intune wdrożonemu na urządzeniu. Usługa Intune nie może zastąpić profilu skonfigurowanego przez użytkownika i nie może nim zarządzać. W celu zapewnienia zgodności użytkownik końcowy musi usunąć istniejące ustawienia poczty e-mail. Umożliwi to usłudze Intune zainstalowanie zarządzanego profilu poczty e-mail.

- **Wybierz profil poczty e-mail, który ma być zarządzany przez usługę Intune**: jeśli zaznaczona jest opcja **Konto e-mail musi być zarządzane przez usługę Intune**, kliknij pozycję **Wybierz**, aby wprowadzić profil poczty e-mail usługi Intune. Ten profil poczty e-mail musi znajdować się na urządzeniu.

Aby uzyskać szczegółowe informacje na temat profilów poczty e-mail, zobacz [Konfigurowanie dostępu do poczty e-mail organizacji przy użyciu profilów poczty e-mail w usłudze Intune](email-settings-configure.md).

## <a name="device-health"></a>Device health

- **Urządzenia ze zdjętymi zabezpieczeniami systemu**: wybierz opcję **Blokuj**, aby oznaczyć urządzenia ze zdjętymi zabezpieczeniami systemu (z odblokowanym dostępem do konta root) jako niezgodne. W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności.
- **Wymagaj, aby poziom zagrożenia urządzenia był niższy lub równy podanemu poziomowi zagrożenia urządzenia** (wersja systemu iOS 8.0 lub nowsza): użyj tego ustawienia, aby uzyskać ocenę ryzyka jako warunek zgodności. W przypadku wybrania opcji **Nieskonfigurowane** (wartość domyślna), to ustawienie nie jest oceniane na potrzeby określenia zgodności. Aby użyć tego ustawienia, wybierz dozwolony poziom zagrożenia:
  - **Zabezpieczony**: ta opcja jest najbezpieczniejsza i oznacza, że urządzenie nie może mieć żadnych zagrożeń. W przypadku wykrycia na urządzeniu zagrożeń dowolnego poziomu zostanie ono ocenione jako niezgodne.
  - **Niski**: urządzenie jest oceniane jako zgodne, jeśli istnieją tylko zagrożenia niskiego poziomu. Jakiekolwiek zagrożenia wyższego poziomu spowodują, że urządzenie będzie miało status urządzenia niezgodnego.
  - **Średni**: urządzenie jest oceniane jako zgodne, jeśli dotyczące go zagrożenia są na poziomie niskim lub średnim. W przypadku wykrycia na urządzeniu zagrożeń wysokiego poziomu zostanie ono określone jako niezgodne.
  - **Wysoki**: ta opcja jest najmniej bezpieczna, ponieważ zezwala na wszystkie poziomy zagrożeń. To ustawienie może być przydatne, jeśli rozwiązanie jest używane tylko na potrzeby raportowania.

## <a name="device-properties"></a>Właściwości urządzenia

- **Wymagana minimalna wersja systemu operacyjnego** (wersja systemu iOS 8.0 lub nowsza): jeśli urządzenie nie spełnia wymagań dotyczących minimalnej wersji systemu operacyjnego, będzie zgłaszane jako niezgodne. Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik końcowy może wybrać opcję uaktualnienia urządzenia. Następnie może uzyskać dostęp do zasobów organizacji.
- **Dozwolona maksymalna wersja systemu operacyjnego** (wersja systemu iOS 8.0 lub nowsza): jeśli urządzenie korzysta z wersji systemu operacyjnego nowszej niż określona w regule, powoduje to zablokowanie dostępu do zasobów organizacji. Użytkownik końcowy zostanie poproszony o kontakt z administratorem IT. Urządzenie nie może uzyskiwać dostępu do zasobów organizacji do momentu zmiany reguły na dopuszczającą daną wersję systemu operacyjnego.
- **Minimalna wersja kompilacji systemu operacyjnego** (wersja systemu iOS 8.0 lub nowsza): gdy firma Apple publikuje aktualizacje zabezpieczeń, zwykle jest aktualizowany numer kompilacji, a nie wersja systemu operacyjnego. Użyj tej funkcji, aby wprowadzić minimalny numer kompilacji dozwolony na urządzeniu.
- **Maksymalna wersja kompilacji systemu operacyjnego** (wersja systemu iOS 8.0 lub nowsza): gdy firma Apple publikuje aktualizacje zabezpieczeń, zwykle jest aktualizowany numer kompilacji, a nie wersja systemu operacyjnego. Użyj tej funkcji, aby wprowadzić maksymalny numer kompilacji dozwolony na urządzeniu.

## <a name="system-security"></a>Zabezpieczenia systemu

### <a name="password"></a>Hasło

> [!NOTE]
> Po zastosowaniu zasad zgodności lub konfiguracji do urządzenia z systemem iOS użytkownicy będą otrzymywać monit o ustawienie kodu dostępu co 15 minut. Monity będą wyświetlane, dopóki kod dostępu nie zostanie ustawiony.

- **Wymagaj hasła do odblokowania urządzeń przenośnych**: wybierz pozycję **Wymagaj**, aby wymagać od użytkowników podania hasła przed uzyskaniem dostępu do urządzenia. Urządzenia z systemem iOS używające haseł są szyfrowane.
- **Proste hasła**: ustaw wartość **Blokuj**, aby uniemożliwić użytkownikom tworzenie prostych haseł, takich jak **1234** lub **1111**. Ustaw wartość **Nieskonfigurowane**, aby umożliwić użytkownikom tworzenie haseł, takich jak **1234** lub **1111**.
- **Minimalna długość hasła**: wprowadź minimalną liczbę cyfr lub znaków, które musi zawierać hasło.
- **Wymagany typ hasła**: określ, czy w skład hasła powinny wchodzić tylko znaki **Numeryczne** lub czy ma być dopuszczalna kombinacja cyfr i innych znaków (**Alfanumeryczne**).
- **Liczba znaków innych niż alfanumeryczne w haśle**: określ minimalną liczbę znaków specjalnych (takich jak `&`, `#`, `%` i `!`), którą musi zawierać hasło.

    Ustawienie większej liczby wymaga wprowadzenia bardziej skomplikowanego hasła przez użytkownika.

- **Maksymalny czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**: wprowadź czas bezczynności, po którym użytkownik musi ponownie wprowadzić hasło.
- **Wygaśnięcie hasła (dni)**: wybierz liczbę dni, po których hasło wygasa i należy utworzyć nowe.
- **Liczba poprzednich haseł, których nie można użyć ponownie**: wprowadź liczbę poprzednio używanych haseł, których ponowne użycie nie jest możliwe.

### <a name="device-security"></a>Zabezpieczenia urządzeń

- **Aplikacje z ograniczeniami**: możesz ograniczyć aplikacje poprzez dodanie ich identyfikatorów pakietu do zasad. Jeśli urządzenie ma zainstalowaną określoną aplikację, jest oznaczane jako niezgodne.

  - **Nazwa aplikacji**: wprowadź przyjazną nazwę, która ułatwia rozpoznanie identyfikatora pakietu.
  - **Identyfikator pakietu aplikacji**: wprowadź unikatowy identyfikator pakietu dostarczony przez dostawcę aplikacji. Aby znaleźć identyfikator pakietu, zobacz [How to find the bundle ID for an iOS app (Jak znaleźć identyfikator pakietu aplikacji z systemem iOS](https://support.microsoft.com/help/4294074/how-to-find-the-bundle-id-for-an-ios-app) — link otwiera inną witrynę internetową firmy Microsoft).  

Wybierz kolejno pozycje **OK** > **Utwórz**, aby zapisać zmiany.

## <a name="next-steps"></a>Następne kroki

- [Dodaj akcje dla niezgodnych urządzeń](actions-for-noncompliance.md) i [użyj tagów zakresu do filtrowania zasad](scope-tags.md).
- [Zastosuj monitorowanie zasad zgodności](compliance-policy-monitor.md).
- Zobacz [Ustawienia zasad zgodności dla urządzeń z systemem macOS](compliance-policy-create-mac-os.md).
