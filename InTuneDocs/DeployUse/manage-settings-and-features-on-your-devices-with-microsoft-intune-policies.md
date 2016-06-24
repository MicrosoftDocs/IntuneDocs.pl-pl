---
# required metadata

title: Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 06/14/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 09bae0b9-4f79-4658-8ca1-a71ab992c1b2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune
**Zasady** usługi Microsoft Intune są grupami ustawień kontrolujących funkcje na komputerach i urządzeniach przenośnych. Możesz utworzyć zasady za pomocą szablonów zawierających zalecane lub dostosowane ustawienia, a następnie wdrożyć je w grupach urządzeń lub użytkowników.

## Jakich typów zasad można użyć?

Zasady usługi Intune można podzielić na następujące kategorie. Używana kategoria wpływa na sposób tworzenia i wdrażania zasad.


- **Zasady konfiguracji:** często są one używane do zarządzania ustawieniami zabezpieczeń i funkcjami na urządzeniach. Skorzystaj z informacji przedstawionych w tym temacie, aby dowiedzieć się więcej o tworzeniu i wdrażaniu tych zasad oraz poznać dostępne ustawienia.
- **Zasady zgodności urządzeń:** są to zasady definiujące reguły i ustawienia, z którymi urządzenie musi być zgodne, aby można je było uważać za spełniające zasady dostępu warunkowego. Zasady zgodności mogą być również wykorzystane do monitorowania i rozwiązywania kwestii związanych ze zgodnością urządzeń niezależnie od dostępu warunkowego.
Aby uzyskać więcej informacji, zobacz [Zasady zgodności urządzeń w usłudze Microsoft Intune](introduction-to-device-compliance-policies-in-microsoft-intune.md).
- **Zasady dostępu warunkowego:** zasady te ułatwiają zabezpieczanie poczty e-mail i innych usług w oparciu o wybrane warunki.
Aby uzyskać szczegółowe informacje, zobacz [Ograniczanie dostępu do poczty e-mail i usług O365 przy użyciu usługi Microsoft Intune](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).
- **Zasady rejestracji urządzeń firmowych:** aby uzyskać informacje na temat zasad rejestracji urządzeń firmowych, zobacz [Konfigurowanie zarządzania systemem iOS i komputerami Mac przez usługę Microsoft Intune](set-up-ios-and-mac-management-with-microsoft-intune.md).
- **Zasady dostępu do zasobów:** zasady z tej grupy działają razem, ułatwiając użytkownikom uzyskiwanie dostępu do plików i zasobów potrzebnych im do skutecznej pracy, niezależnie od miejsca, w którym się znajdują.
Aby uzyskać więcej informacji, zobacz [Zapewnianie dostępu do zasobów firmy przy użyciu usługi Microsoft Intune](enable-access-to-company-resources-with-microsoft-intune.md).


Aby uzyskać pełną listę zasad usługi Intune, zobacz [Informacje o zasadach usługi Microsoft Intune](microsoft-intune-policy-reference.md).




## Tworzenie zasad konfiguracji

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/) wybierz pozycję **Zasady** &gt; **Zasady konfiguracji** &gt; **Dodaj**.

2.  Wybierz zasady, a następnie wybierz opcję użycia zalecanych ustawień zasad (jeśli jest dostępna; te ustawienia można zmienić później) lub utworzenia niestandardowych zasad z własnymi ustawieniami.

    > [!TIP] Aby uzyskać pomoc związaną z wyborem odpowiednich zasad, zobacz [Informacje o zasadach usługi Microsoft Intune](microsoft-intune-policy-reference.md).

3.  Gdy skończysz, wybierz pozycję **Utwórz zasady**.

4.  Na ekranie **Tworzenie zasad** skonfiguruj nazwę i opcjonalny opis zasad.

5.  Skonfiguruj wymagane ustawienia zasad, a następnie wybierz pozycję **Zapisz zasady**.

    Jeśli potrzebujesz pomocy związanej z ustawieniami zasad, wybierz typ zasad z następującej listy:

    - [Ustawienia dotyczące urządzeń z systemem iOS](ios-policy-settings-in-microsoft-intune.md)
    - [Ustawienia dotyczące urządzeń z systemem Android](android-policy-settings-in-microsoft-intune.md)
    - [Ustawienia dotyczące urządzeń z systemami Windows 8 i Windows 8.1](windows-configuration-policy-settings-in-microsoft-intune.md)
    - [Ustawienia dotyczące urządzeń z systemem Windows Phone 8.1](windows-phone-8-1-policy-settings-in-microsoft-intune.md)
    - [Ustawienia dotyczące urządzeń z systemami Windows 10 Desktop i Windows 10 Mobile](windows-10-policy-settings-in-microsoft-intune.md)
    - [Ustawienia dotyczące urządzeń z systemem Windows Team](windows-team-configuration-policy-settings-in-microsoft-intune.md)
    - [Ustawienia dotyczące uaktualnienia wersji systemu Windows](edition-upgrade-policy-settings-in-microsoft-intune.md)
    - [Ustawienia dotyczące urządzeń z systemem Mac OS X](mac-os-x-policy-settings-in-microsoft-intune.md)
    - [Ustawienia dotyczące programu Exchange ActiveSync](exchange-activesync-policy-settings-in-microsoft-intune.md)
    - [Ustawienia zasad dotyczących warunków i postanowień](terms-and-condition-policy-settings-in-microsoft-intune.md)
    - [Ustawienia ogólne dotyczące urządzeń przenośnych (starszych)](mobile-device-security-policy-settings-in-microsoft-intune.md)

4.  W oknie dialogowym z potwierdzeniem wybierz pozycję **Tak**, aby wdrożyć zasady teraz, lub wybierz pozycję **Nie**, aby utworzyć zasady bez ich wdrażania.

Możesz wyświetlić i edytować nowe zasady, przeglądając sekcje dla każdego typu zasad w obszarze roboczym **Zasady** .

W przypadku tworzenia zasad, które korzystają z zalecanych ustawień, nazwa nowych zasad jest kombinacją nazwy szablonu, daty i godziny. Przy edytowaniu zasad nazwa jest aktualizowana pod kątem godziny i daty edycji.

Teraz, gdy zasada została utworzona, zwykle można wdrożyć ją w co najmniej jednej grupie użytkowników lub urządzeń.

> [!TIP]
> Nie można wdrożyć wszystkich typów zasad. Na przykład zasady zarządzania aplikacjami mobilnymi nie są wdrażane. Ten typ zasad jest w zamian kojarzony z aplikacją, która jest następnie wdrażana.

## Wdrażanie zasad konfiguracji

1.  W obszarze roboczym **Zasady** wybierz zasady do wdrożenia, a następnie wybierz pozycję **Zarządzaj wdrożeniem**.

2.  W oknie dialogowym **Zarządzanie wdrażaniem** :

    -   **Aby wdrożyć zasady** — wybierz co najmniej jedną grupę, w której chcesz wdrożyć zasady, a następnie wybierz pozycję **Dodaj** &gt; **OK**.

    -   **Aby zamknąć okno dialogowe bez wdrażania** — wybierz pozycję **Anuluj**.

Po wybraniu wdrożonych zasad można wyświetlić więcej informacji dotyczących wdrożenia w dolnej części listy zasad.

## Zarządzanie zasadami

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/) wybierz pozycję **Zasady**, a następnie wyszukaj i wybierz zasady, którymi chcesz zarządzać.

2.  Wybierz jedno z następujących działań:

- **Edytuj** — otwiera właściwości dla wybranych zasad i umożliwia wprowadzenie zmian.
- **Usuń** — usuwa wybrane zasady.<br>Po usunięciu zasad są one usuwane ze wszystkich grup, w których zostały wdrożone.
- **Zarządzanie wdrażaniem** — wybierz grupę, w której chcesz wdrożyć zasady, a następnie wybierz pozycję **Dodaj**.


## Często zadawane pytania dotyczące zasad usługi Intune

### Jak długo trwa pobieranie zasad lub aplikacji przeznaczonych dla urządzeń przenośnych po ich wdrożeniu?
Po wdrożeniu zasad lub aplikacji usługa Intune natychmiast rozpoczyna próby powiadomienia urządzenia, które powinno zostać zaewidencjonowane przez usługę Intune. Trwa to zazwyczaj mniej niż 5 minut.

Jeśli urządzenie nie zostanie zaewidencjonowane w celu pobrania zasad po wysłaniu pierwszego powiadomienia, nastąpią 3 kolejne próby.  Jeśli urządzenie działa w trybie offline (na przykład zostało wyłączone lub nie zostało podłączone do sieci), może nie odbierać powiadomień.

W takim przypadku urządzenie pobierze zasady podczas następnego zaplanowanego zaewidencjonowania przy użyciu usługi Intune w następujący sposób:

- iOS — co 6 godzin
- Android — co 8 godzin
- Windows Phone — co 8 godzin
- Zarejestrowane urządzenia z systemem Windows RT — co 24 godziny
- Komputery z systemem Windows 8.1 i Windows 10 zarejestrowane jako urządzenia — co 8 godzin

Jeśli urządzenie zostało właśnie zarejestrowane, częstotliwość zaewidencjonowania będzie większa:

- iOS — co 15 minut przez 6 godzin, a następnie co 6 godzin
- Android — co 3 minuty przez 15 minut, następnie co 15 minut przez 2 godziny, a następnie co 8 godzin
- Windows Phone — co 5 minut przez 15 minut, następnie co 15 minut przez 2 godziny, a następnie co 8 godzin
- Komputery z systemem Windows zarejestrowane jako urządzenia — co 3 minuty przez 30 minut, a następnie co 24 godziny

Użytkownicy mogą także uruchamiać aplikację Portal firmy i synchronizować urządzenie, aby natychmiast w dowolnym momencie wyszukać zasady.

### Jakie akcje mogą spowodować natychmiastowe wysłanie powiadomienia do urządzenia z usługi Intune?
Urządzenia są zaewidencjonowywane przy użyciu usługi Intune po otrzymaniu powiadomienia z poleceniem zaewidencjonowania lub podczas zaplanowanego zaewidencjonowania zgodnie z informacjami podanymi w tabelach powyżej.  Jeśli akcja, taka jak czyszczenie, blokowanie, resetowanie kodu dostępu, wdrażanie aplikacji, wdrażanie profilu (Wi-Fi, VPN, poczta e-mail itd.) lub wdrażanie zasad, zostanie rozpoczęta dla określonego urządzenia lub użytkownika, usługa Intune natychmiast podejmie próbę powiadomienia urządzenia o konieczności zaewidencjonowania w usłudze Intune w celu odbierania aktualizacji.

Inne zmiany, takie jak zmiana informacji kontaktowych w Portalu firmy, nie powodują natychmiastowego wysłania powiadomienia do urządzeń.

> [!TIP]
> Po wdrożeniu zasady zawierającej ustawienia na urządzeniu z systemem Android użytkownik jest monitowany w celu wykonania akcji zgodnej z zasadami. Ustawienia nowych zasad będą obowiązywać dopiero wówczas, gdy użytkownik wykona akcję lub urządzenie zostanie uruchomione ponownie.

### Jeśli do tego samego użytkownika lub urządzenia wdrożono wiele zasad, jak mogę zidentyfikować ustawienia, które zostaną zastosowane?
Należy pamiętać, że jeśli co najmniej dwie zasady są wdrażane do tego samego użytkownika lub urządzenia, ocena ustawień do zastosowania odbywa się na poziomie indywidualnego ustawienia.

-   Ustawienia zasad zgodności mają zawsze pierwszeństwo przed ustawieniami zasad konfiguracji

-   Jeśli ocena dotyczy tego samego ustawienia w innych zasadach zgodności, zostanie zastosowane najbardziej restrykcyjne ustawienie zasad zgodności

-   Jeśli ocena dotyczy tego samego ustawienia w innych zasadach konfiguracji, zostanie zastosowane najbardziej restrykcyjne ustawienie zasad konfiguracji

### Co się stanie w przypadku wystąpienia konfliktu zasad zarządzania aplikacjami mobilnymi? Które z nich zostaną zastosowane w aplikacji?
Wartości powodujące konflikt to najbardziej restrykcyjne ustawienia dostępne w zasadach zarządzania aplikacjami mobilnymi, z wyjątkiem pól wprowadzania liczb (służących na przykład do podejmowania prób wpisania kodu PIN przed zresetowaniem).  Pola wprowadzania liczb zostaną ustawione na wartości, który zostałyby użyte w przypadku utworzenia zasad zarządzania aplikacjami mobilnymi w konsoli przy użyciu opcji zalecanych ustawień.

Konflikty występują, jeśli dwa ustawienia zasad są takie same.  Można na przykład skonfigurować dwie identyczne zasady zarządzania aplikacjami różniące się jedynie ustawieniem kopiowania/wklejania.  W tym scenariuszu operacja kopiowania/wklejania zostanie ustawiona na najbardziej restrykcyjną wartość, ale pozostałe ustawienia będą stosowane zgodnie z konfiguracją.

Jeśli jedna zasada została wdrożona w aplikacji i obowiązuje, a następnie wdrażana jest druga, pierwsza z nich będzie mieć pierwszeństwo i będzie nadal stosowana, a druga spowoduje wystąpienie konfliktu. Jeśli jednak obydwie zasady zostaną zastosowane w tym samym czasie, czyli żadna z zasad nie ma pierwszeństwa, obydwie będą pozostawać w konflikcie i wszelkie sprzeczne ustawienia będą ustawiane na wartości najbardziej restrykcyjne.

### Co się stanie w przypadku konfliktu zasad niestandardowych systemu iOS?
Usługa Intune nie może oszacować ładunku plików konfiguracyjnych firmy Apple lub niestandardowych zasad OMA-URI, służy ona jedynie jako mechanizm dostarczania.

Dlatego podczas wdrażania niestandardowych zasad upewnij się, że skonfigurowane ustawienia nie pozostają w konflikcie z zasadami zgodności, konfiguracji lub innymi zasadami niestandardowymi. Jeśli wystąpią konflikty ustawień zasad niestandardowych, ustawienia będą stosowane w kolejności losowej.

### Co się stanie, gdy zasady zostaną usunięte lub nie będą już miały zastosowania?
Usunięcie zasad lub usunięcie urządzenia z grupy, w której zostały wdrożone zasady, powoduje usunięcie zasad i ustawień z urządzenia zgodnie z następującymi tabelami:

#### zarejestrowane urządzenia

- Profile sieci Wi-Fi, sieci VPN, certyfikatu i poczty e-mail — te profile są usuwane ze wszystkich obsługiwanych zarejestrowanych urządzeń.
- Wszystkie inne typy zasad
    - **Urządzenia z systemami Windows i Android** — ustawienia nie są usuwane z urządzenia.
    - **Urządzenia z systemem Windows Phone 8.1** — następujące ustawienia są usuwane:
        - Wymagaj hasła do odblokowania urządzeń przenośnych
        - Zezwalaj na proste hasła
        - Minimalna długość hasła
        - Wymagany typ hasła
        - Wygaśnięcie hasła w dniach
        - Pamiętaj historię haseł
        - Liczba dopuszczalnych nieudanych logowań przed wyczyszczeniem danych z urządzenia — Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła — Wymagany typ hasła — Minimalna liczba zestawów znaków — Zezwalaj na używanie aparatu — Wymagaj szyfrowania na urządzeniu przenośnym — Zezwalaj na używanie magazynu wymiennego — Zezwalaj na używanie przeglądarki sieci Web — Zezwalaj na korzystanie ze sklepu z aplikacjami — Zezwalaj na przechwytywanie ekranu — Zezwalaj na używanie funkcji geolokalizacji — Zezwalaj na konto Microsoft — Zezwalaj na kopiowanie i wklejanie — Zezwalaj na tethering Wi-Fi — Zezwalaj na automatyczne łączenie z bezpłatnymi punktami hotspot Wi-Fi — Zezwalaj na raportowanie informacji o punktach hotspot Wi-Fi — Zezwalaj na resetowanie do ustawień fabrycznych — Zezwalaj na połączenia Bluetooth — Zezwalaj na komunikację NFC — Zezwalaj na połączenia Wi-Fi
    
    - **iOS** — wszystkie ustawienia są usuwane, z wyjątkiem:
        - Zezwalaj na roaming połączeń głosowych
        - Zezwalaj na roaming danych
        - Zezwalaj na automatyczną synchronizację podczas roamingu

#### Komputery z systemem Windows z uruchomionym oprogramowaniem klienckim usługi Intune

- **Ustawienia programu Endpoint Protection** — zostaną przywrócone zalecane wartości ustawień. Jedynym wyjątkiem jest ustawienie **Dołącz do społeczności Microsoft Active Protection Service** , którego wartość domyślna to **Nie**. Aby uzyskać więcej informacji, zobacz [Zabezpieczanie komputerów z systemem Windows przy użyciu programu Endpoint Protection dla usługi Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).
- **Ustawienia aktualizacji oprogramowania** — zostanie przywrócony stan domyślny ustawień odpowiedni dla systemu operacyjnego. Aby uzyskać więcej informacji, zobacz [Zapewnianie aktualności oprogramowania na komputerach z systemem Windows za pomocą aktualizacji w usłudze Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).
- **Ustawienia programu Microsoft Intune Center** — wszystkie informacje kontaktowe pomocy technicznej, które zostały skonfigurowane przez zasady, zostaną usunięte z komputerów.
- **Ustawienia Zapory systemu Windows** — zostaną przywrócone ustawienia domyślne odpowiednie dla systemu operacyjnego. Aby uzyskać więcej informacji, zobacz [Zabezpieczanie komputerów z systemem Windows przy użyciu programu Endpoint Protection dla usługi Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).


### Jak odświeżyć zasady na urządzeniu w celu zapewnienia ich aktualności (dotyczy wyłącznie komputerów z systemem Windows z uruchomionym oprogramowaniem klienckim usługi Intune)?

1.  W dowolnej grupie urządzeń wybierz urządzenia, na których chcesz odświeżyć zasady, a następnie wybierz pozycję **Zadania zdalne** &gt; **Odśwież zasady**.
2.  Kliknij pozycję **Zadania zdalne** w prawym dolnym rogu konsoli administracyjnej usługi Intune w celu sprawdzenia stanu zadania.

### Gdzie mogę znaleźć pomoc w rozwiązywaniu problemów dotyczących zasad?

Zobacz [Rozwiązywanie problemów dotyczących zasad w usłudze Microsoft Intune](../Troubleshoot/troubleshoot-policies-in-microsoft-intune).


<!--HONumber=Jun16_HO3-->


