---
title: Ustawienia zgodności dla urządzeń z systemem iOS w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zapoznaj się z listą ustawień umożliwiających skonfigurowanie zgodności dla urządzeń z systemem iOS w usłudze Microsoft Intune. Możesz między innymi wymagać profilu poczty e-mail, sprawdzać urządzenia ze zdjętymi zabezpieczeniami systemu lub odblokowanym dostępem do konta root, ustawiać minimalną lub maksymalną wersję systemu operacyjnego, określać ograniczenia dotyczące haseł takie jak długość hasła czy czas nieaktywności urządzenia oraz ograniczać aplikacje.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/22/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d
ms.reviewer: samyada
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3b83b764af415349b287df2a09f9b4c355734c28
ms.sourcegitcommit: 3ace4cba6e2f6fefa9120be3807387a49b200c9b
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2019
ms.locfileid: "72810240"
---
# <a name="ios-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Ustawienia urządzeń z systemem iOS umożliwiające oznaczenie ich jako zgodne lub niezgodne w usłudze Intune

W tym artykule wymieniono i opisano różne ustawienia zgodności, które można skonfigurować na urządzeniach z systemem iOS za pomocą usługi Intune. Możesz stosować te ustawienia w ramach rozwiązania do zarządzania urządzeniami mobilnymi (MDM), aby między innymi wymagać profilu poczty e-mail, oznaczać urządzenia z odblokowanym dostępem do konta root lub zdjętymi zabezpieczeniami systemu jako niezgodne, określać dozwolony poziom zagrożenia, czy ustawiać wygasanie haseł.

Ta funkcja ma zastosowanie do:

- iOS
- iPadOS

Jako administrator usługi Intune możesz użyć tych ustawień zgodności, aby chronić zasoby organizacji. Aby dowiedzieć się więcej na temat zasad zgodności i ich działania, zobacz [Wprowadzenie do zasad zgodności urządzeń](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz zasady zgodności](create-compliance-policy.md#create-the-policy). W polu **Platforma** wybierz opcję **iOS/iPadOS**.

## <a name="email"></a>Poczta e-mail

- **Wymagaj zarządzanego profilu poczty e-mail urządzeń przenośnych**:  
  - **Nieskonfigurowane** (*wartość domyślna*) — ustawienie nie jest oceniane na potrzeby określenia zgodności.
  - **Wymagaj** — urządzenia, których profil poczty e-mail nie jest zarządzany przez usługę Intune, będą traktowane jako niezgodne. Urządzenie nie może mieć zarządzanego profilu poczty e-mail, jeśli nie zostało przekazane właściwemu użytkownikowi docelowemu lub jeśli użytkownik ręcznie skonfigurował na nim konto e-mail.

  Urządzenie jest uznawane za niezgodne w następujących sytuacjach:  
  - Profil poczty e-mail jest przypisany do innej grupy użytkowników niż grupa, której dotyczą zasady zgodności.
  - Użytkownik skonfigurował już na urządzeniu konto e-mail odpowiadające profilowi poczty e-mail usługi Intune wdrożonemu na urządzeniu. Usługa Intune nie może zastąpić profilu skonfigurowanego przez użytkownika i nie może nim zarządzać. W celu zapewnienia zgodności użytkownik końcowy musi usunąć istniejące ustawienia poczty e-mail. Umożliwi to usłudze Intune zainstalowanie zarządzanego profilu poczty e-mail.  

Aby uzyskać szczegółowe informacje na temat profilów poczty e-mail, zobacz [Konfigurowanie dostępu do poczty e-mail organizacji przy użyciu profilów poczty e-mail w usłudze Intune](../configuration/email-settings-configure.md).

## <a name="device-health"></a>Kondycja urządzenia

- **Urządzenia ze zdjętymi zabezpieczeniami systemu**:  
  - **Nieskonfigurowane** (*wartość domyślna*) — ustawienie nie jest oceniane na potrzeby określenia zgodności.
  - **Blokuj** — urządzenia z odblokowanym dostępem do konta root (ze zdjętymi zabezpieczeniami systemu) są oznaczane jako niezgodne.  

- **Wymagaj, aby poziom zagrożenia urządzenia był niższy lub równy podanemu poziomowi zagrożenia urządzenia** *(system iOS 8.0 i nowsze)* :  
  Użyj tego ustawienia, aby zastosować ocenę ryzyka jako warunek zgodności. Wybierz dozwolony poziom zagrożenia:  
  - **Nieskonfigurowane** (*wartość domyślna*) — ustawienie nie jest oceniane na potrzeby określenia zgodności.
  - **Zabezpieczone** — ta opcja jest najbezpieczniejsza i oznacza, że urządzenie nie może mieć żadnych zagrożeń. W przypadku wykrycia na urządzeniu zagrożeń dowolnego poziomu zostanie ono ocenione jako niezgodne.
  - **Niski** — urządzenie jest oceniane jako zgodne, jeśli istnieją tylko zagrożenia niskiego poziomu. Jakiekolwiek zagrożenia wyższego poziomu spowodują, że urządzenie będzie miało status urządzenia niezgodnego.
  - **Średni** — urządzenie jest oceniane jako zgodne, jeśli dotyczące go zagrożenia są na poziomie niskim lub średnim. W przypadku wykrycia na urządzeniu zagrożeń wysokiego poziomu zostanie ono określone jako niezgodne.
  - **Wysoki** — ta opcja jest najmniej bezpieczna, ponieważ zezwala na wszystkie poziomy zagrożeń. To ustawienie może być przydatne, jeśli rozwiązanie jest używane tylko na potrzeby raportowania.

## <a name="device-properties"></a>Właściwości urządzenia

### <a name="operating-system-version"></a>Wersja systemu operacyjnego  

- **Wymagana minimalna wersja systemu operacyjnego** *(iOS 8,0 i nowsze)* :  
  Jeśli urządzenie nie spełnia wymagań dotyczących minimalnej wersji systemu operacyjnego, będzie zgłaszane jako niezgodne. Zostanie wyświetlony link ze wskazówkami dotyczącymi uaktualniania. Użytkownik końcowy może wybrać opcję uaktualnienia urządzenia. Następnie może uzyskać dostęp do zasobów organizacji.

- **Dozwolona maksymalna wersja systemu operacyjnego** *(iOS 8,0 i nowsze)* :  
  Jeśli urządzenie korzysta z wersji systemu operacyjnego nowszej niż określona w regule, powoduje to zablokowanie dostępu do zasobów organizacji. Użytkownik końcowy zostanie poproszony o kontakt z administratorem IT. Urządzenie nie może uzyskiwać dostępu do zasobów organizacji do momentu zmiany reguły na dopuszczającą daną wersję systemu operacyjnego.

- **Minimalna wersja kompilacji systemu operacyjnego** *(iOS 8,0 i nowsze)* :  
  gdy firma Apple publikuje aktualizacje zabezpieczeń, zwykle jest aktualizowany numer kompilacji, a nie wersja systemu operacyjnego. Użyj tej funkcji, aby wprowadzić minimalny numer kompilacji dozwolony na urządzeniu.

- **Maksymalna wersja kompilacji systemu operacyjnego** *(iOS 8,0 i nowsze)* :  
  gdy firma Apple publikuje aktualizacje zabezpieczeń, zwykle jest aktualizowany numer kompilacji, a nie wersja systemu operacyjnego. Użyj tej funkcji, aby wprowadzić maksymalny numer kompilacji dozwolony na urządzeniu.

## <a name="system-security"></a>Zabezpieczenia systemu

### <a name="password"></a>Hasło

> [!NOTE]
> Po zastosowaniu zasad zgodności lub konfiguracji do urządzenia z systemem iOS użytkownicy będą otrzymywać monit o ustawienie kodu dostępu co 15 minut. Monity będą wyświetlane, dopóki kod dostępu nie zostanie ustawiony. Po ustawieniu kodu dostępu dla urządzenia z systemem iOS proces szyfrowania zostaje automatycznie uruchomiony. Urządzenie pozostanie zaszyfrowane do momentu wyłączenia kodu dostępu.

- **Wymagaj hasła do odblokowania urządzeń przenośnych**:  
  - **Nieskonfigurowane** (*wartość domyślna*) — ustawienie nie jest oceniane na potrzeby określenia zgodności.  
  - **Wymagaj** — użytkownicy muszą wprowadzić hasło podczas uzyskiwania dostępu do swoich urządzeń. Urządzenia z systemem iOS używające haseł są szyfrowane.

- **Proste hasła**:  
  - **Nie skonfigurowano** (*Domyślnie*) — użytkownicy mogą tworzyć proste hasła, takie jak **1234** lub **1111**.
  - **Blokuj** — użytkownicy nie mogą tworzyć prostych haseł, takich jak **1234** lub **1111**. 

- **Minimalna długość hasła**:  
  wprowadź minimalną liczbę cyfr lub znaków, które musi zawierać hasło.  

- **Wymagany typ hasła**:  
  określ, czy hasło ma zawierać tylko znaki **numeryczne**, czy też ma być dopuszczalna kombinacja cyfr i innych znaków (**Alfanumeryczne**).

- **Liczba znaków innych niż alfanumeryczne w haśle**:  
  wprowadź minimalną liczbę znaków specjalnych, takich jak `&`, `#`, `%`, `!` itp., którą musi zawierać hasło. 

  Ustawienie większej liczby wymaga wprowadzenia bardziej skomplikowanego hasła przez użytkownika.

- **Maksymalna liczba minut po zablokowaniu ekranu, po których jest wymagane wprowadzenie hasła** *(system iOS 8.0 i nowsze)* :  
  Określ, jak wkrótce po zablokowaniu ekranu użytkownik musi wprowadzić hasło w celu uzyskania dostępu do urządzenia. Opcje obejmują domyślnie *Nieskonfigurowane*, *natychmiastowe*i od *1 minuty* do *4 godzin*.

- **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu**:  
  Wprowadź czas bezczynności, po którym urządzenie zostanie zablokowane. Opcje obejmują domyślnie wartość *Nieskonfigurowane*, *natychmiast*i od *1 minuty* do *15 minut*.

- **Wygaśnięcie hasła (dni)** :  
  wybierz liczbę dni, po których wygasa hasło i należy utworzyć nowe. 

- **Liczba poprzednich haseł, których nie można użyć ponownie** *(system iOS 8.0 i nowsze)* :   
  wprowadź liczbę wcześniej używanych haseł, których nie można użyć ponownie.

### <a name="device-security"></a>Zabezpieczenia urządzeń

- **Aplikacje z ograniczeniami**:  
  Możesz ograniczyć aplikacje poprzez dodanie ich identyfikatorów pakietu do zasad. Jeśli urządzenie ma zainstalowaną określoną aplikację, jest oznaczane jako niezgodne.

  - **Nazwa aplikacji** — wprowadź przyjazną nazwę, która ułatwia rozpoznanie identyfikatora pakietu.
  - **Identyfikator pakietu aplikacji** — wprowadź unikatowy identyfikator pakietu dostarczony przez dostawcę aplikacji. Aby znaleźć identyfikator pakietu, zobacz [How to find the bundle ID for an iOS app (Jak znaleźć identyfikator pakietu aplikacji z systemem iOS](https://support.microsoft.com/help/4294074/how-to-find-the-bundle-id-for-an-ios-app) — link otwiera inną witrynę internetową firmy Microsoft).  

## <a name="next-steps"></a>Następne kroki

- [Dodaj akcje dla niezgodnych urządzeń](actions-for-noncompliance.md) i [użyj tagów zakresu do filtrowania zasad](../fundamentals/scope-tags.md).
- [Zastosuj monitorowanie zasad zgodności](compliance-policy-monitor.md).
- Zobacz [Ustawienia zasad zgodności dla urządzeń z systemem macOS](compliance-policy-create-mac-os.md).
