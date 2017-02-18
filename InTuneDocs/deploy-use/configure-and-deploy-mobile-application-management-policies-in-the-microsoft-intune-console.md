---
title: "Konfigurowanie zasad zarządzania aplikacjami mobilnymi w konsoli usługi Intune | Microsoft Docs"
description: "Zasady zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune umożliwiają modyfikację funkcji wdrażanych aplikacji, co pomaga dostosować je do zasad zgodności i zabezpieczeń w firmie."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b4fb33a8-a2fa-4353-bd89-5bda48b68e83
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e7d1760a10e63233fe7cc7f6fd57a68c5283647c
ms.openlocfilehash: f7504657f5fb2d73242f25f2f059c8c4e7ab1547


---

# <a name="configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console"></a>Konfigurowanie i wdrażanie zasad zarządzania aplikacjami mobilnymi w konsoli usługi Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Zasady zarządzania aplikacjami mobilnymi (MAM) w usłudze Microsoft Intune umożliwiają modyfikację funkcji wdrażanych aplikacji, co pomaga dostosować je do zasad zgodności i zabezpieczeń w firmie. Na przykład w aplikacji zarządzanej można ograniczyć wykonywanie operacji wycinania, kopiowania i wklejania lub skonfigurować aplikację tak, aby wszystkie linki sieci Web były otwierane w przeglądarce zarządzanej.

Zasady zarządzania aplikacjami mobilnymi obsługują następujące urządzenia:

-   Urządzenia z systemem Android w wersji 4 lub nowszej.

-   Urządzenia z systemem iOS w wersji 8.0 lub nowszej.

> [!TIP]
> Zasady zarządzania aplikacjami mobilnymi obsługują urządzenia zarejestrowane w usłudze Intune.
>
> Informacje na temat tworzenia zasad zarządzania aplikacjami dla urządzeń niezarządzanych przez usługę Intune zawiera temat [Ochrona danych aplikacji przy użyciu zasad zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).

W odróżnieniu od innych zasad usługi Intune, zasady zarządzania aplikacjami mobilnymi nie są wdrażane bezpośrednio. Zamiast tego należy je skojarzyć z aplikacją, która ma zostać ograniczona. Określone ustawienia zostaną zastosowane po wdrożeniu i zainstalowaniu aplikacji na urządzeniach.

Aby zastosować ograniczenia dla aplikacji, musi ona zawierać zestaw SDK aplikacji usługi Microsoft Intune. Istnieją trzy metody uzyskania tego typu aplikacji:

-   **Użycie aplikacji zarządzanej przez zasady**. Aplikacja zarządzana przez zasady zawiera wbudowany zestaw SDK aplikacji. Aby dodać ten typ aplikacji, wystarczy podać link do wybranej aplikacji w sklepie z aplikacjami, takim jak iTunes lub Google Play. Żadne dalsze przetwarzanie nie jest wymagane w przypadku tego typu aplikacji. Aby uzyskać więcej informacji, zobacz [listę aplikacji, których można używać z zasadami zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps).

-   **Użycie opakowanej aplikacji**. Opakowana aplikacja to aplikacja ponownie umieszczana w pakietach za pomocą narzędzia opakowującego aplikacje w usłudze Microsoft Intune w celu dodania do niej zestawu SDK aplikacji. To narzędzie jest zwykle używane do przetwarzania aplikacji firmowych utworzonych wewnętrznie. Nie można go używać do przetwarzania aplikacji, które zostały pobrane ze sklepu z aplikacjami. Aby uzyskać więcej informacji, zobacz [Przygotowanie aplikacji systemu iOS do zarządzania aplikacjami mobilnymi za pomocą narzędzia opakowującego aplikacje w usłudze Microsoft Intune](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) i [Przygotowanie aplikacji systemu Android do zarządzania aplikacjami mobilnymi za pomocą narzędzia opakowującego aplikacje w usłudze Microsoft Intune](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md).

- **Napisanie własnej aplikacji, która będzie zawierała zestaw SDK aplikacji usługi Intune**. Zestaw SDK aplikacji usługi Intune pozwala dołączyć funkcje zarządzania aplikacjami do aplikacji podczas jej pisania. Aby uzyskać więcej informacji, zobacz [Omówienie zestawu SDK aplikacji usługi Intune](/intune/develop/intune-app-sdk).

Aby łatwiej dokonać wyboru między narzędziem opakowującym aplikacje a zestawem SDK aplikacji usługi Intune, zobacz [Wybieranie sposobu przygotowania aplikacji do zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md).

Niektóre aplikacje zarządzane, takie jak aplikacja Outlook dla systemów iOS i Android, obsługują *wiele tożsamości*. Oznacza to, że usługa Intune stosuje ustawienia zarządzania tylko do firmowych kont lub danych w aplikacji.

Na przykład, jeśli używana jest aplikacja Outlook:

-   Jeśli użytkownik skonfiguruje firmowe i osobiste konta e-mail, usługa Intune będzie stosowała ustawienia zarządzania tylko do konta firmowego i nie będzie zarządzała kontem osobistym.

-   Jeśli urządzenie zostało wycofane lub cofnięto jego rejestrację, z urządzenia są usuwane tylko dane firmowe programu Outlook.

-   Konto firmowe musi być tym samym kontem, które zostało użyte do rejestracji urządzenia w usłudze Intune.

> [!TIP]
> Jeśli używasz usługi Intune z programem Configuration Manager, zobacz [Sterowanie aplikacjami przy użyciu zasad zarządzania aplikacjami mobilnymi w programie Configuration Manager](https://technet.microsoft.com/library/mt131414.aspx).

## <a name="create-and-deploy-an-app-with-a-mobile-application-management-policy"></a>Tworzenie i wdrażanie aplikacji podlegającej zasadom zarządzania aplikacjami mobilnymi

-   **Krok 1.** Uzyskiwanie linku do aplikacji zarządzanej przez zasady, tworzenie opakowanej aplikacji lub używanie zestawu SDK aplikacji usługi Intune do napisania aplikacji objętej zarządzaniem aplikacjami mobilnymi.

-   **Krok 2.** Publikowanie aplikacji w magazynie w chmurze

-   **Krok 3.** Tworzenie zasad zarządzania aplikacjami mobilnymi

-   **Krok 4.** Kojarzenie aplikacji z zasadami zarządzania aplikacjami mobilnymi, a następnie wdrażanie aplikacji

-   **Krok 5.** Monitorowanie wdrożenia aplikacji

## <a name="step-1-get-the-link-to-a-policy-managed-app-create-a-wrapped-app-or-use-the-intune-app-sdk-to-write-a-mam-enabled-app"></a>Krok 1. Uzyskiwanie linku do aplikacji zarządzanej przez zasady, tworzenie opakowanej aplikacji lub używanie zestawu SDK aplikacji usługi Intune do napisania aplikacji objętej zarządzaniem aplikacjami mobilnymi

W sklepie z aplikacjami znajdź i zanotuj adres URL aplikacji zarządzanej przez zasady, którą chcesz wdrożyć. Na przykład adres URL aplikacji Microsoft Word dla urządzenia iPad to **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8**.


## <a name="step-2-publish-the-app-to-your-cloud-storage-space"></a>Krok 2. Publikowanie aplikacji w magazynie w chmurze
Procedura publikowania aplikacji zarządzanej jest różna w zależności od tego, czy jest to aplikacja zarządzana przez zasady, czy aplikacja przetworzona za pomocą dostępnego w usłudze Microsoft Intune narzędzia opakowującego aplikacje dla systemu iOS.

#### <a name="to-publish-a-policy-managed-app"></a>Aby opublikować aplikację zarządzaną przez zasady

1.  Gdy wszystko jest gotowe do przekazania aplikacji do magazynu w chmurze, postępuj zgodnie z instrukcjami w temacie [Dodawanie aplikacji dla urządzeń przenośnych w usłudze Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md).

2.  W przypadku aplikacji dla systemu iOS wybierz opcję **Zarządzana aplikacja systemu iOS ze sklepu App Store**w obszarze **Wybierz w jaki sposób to oprogramowanie ma zostać udostępnione urządzeniom**.

    W przypadku aplikacji dla systemu Android wybierz opcję **Zewnętrzny link**.

3.  W obszarze **Określanie adresu URL**wprowadź zanotowany wcześniej adres URL do aplikacji zarządzanej przez zasady.

Po ukończeniu przekazywania będzie widoczna wartość **Tak** dla opcji **Zasady zarządzania aplikacjami** na stronie **Właściwości oprogramowania** przekazanej aplikacji.

Po upewnieniu się, że aplikacja została pomyślnie przekazana, przejdź do kroku 3.

#### <a name="to-publish-an-app-that-was-processed-through-the-microsoft-intune-app-wrapping-tool"></a>Aby opublikować aplikację, która została przetworzona za pomocą dostępnego w usłudze Microsoft Intune narzędzia opakowującego aplikacje

1.  Gdy wszystko jest gotowe do przekazania aplikacji do magazynu w chmurze, postępuj zgodnie z instrukcjami w temacie [Dodawanie aplikacji dla urządzeń przenośnych w usłudze Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md).

2.  Wybierz opcję **Instalator oprogramowania** w obszarze **Wybierz w jaki sposób to oprogramowanie ma zostać udostępnione urządzeniom**.

3.  Wybierz opcję **Pakiet aplikacji dla systemu iOS (plik &#42;.ipa)** w obszarze **Typ pliku instalatora oprogramowania**.

Po ukończeniu przekazywania będzie widoczna wartość **Tak** dla opcji **Zasady zarządzania aplikacjami** na stronie **Właściwości oprogramowania** przekazanej aplikacji.

Po upewnieniu się, że aplikacja została pomyślnie przekazana, przejdź do kroku 3.

## <a name="step-3-create-a-mobile-application-management-policy"></a>Krok 3. Tworzenie zasad zarządzania aplikacjami mobilnymi

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) wybierz pozycję **Zasady** &gt; **Przegląd** &gt; **Dodaj zasady**.

2.  Skonfiguruj i wdróż jedne z następujących zasad **Oprogramowania** w zależności od typu urządzenia, dla którego chcesz skonfigurować aplikacje:

    -   **Zasady zarządzania aplikacjami mobilnymi (system Android 4 i nowsze)**

    -   **Zasady zarządzania aplikacjami mobilnymi (system iOS 8.0 i nowsze)**

    Możesz skorzystać z zalecanych ustawień lub dostosować je. Aby uzyskać szczegółowe informacje, zobacz [Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Skonfiguruj następujące ustawienia zgodnie z wymaganiami. Opcje mogą się różnić w zależności od typu urządzenia, dla którego konfigurujesz zasady.

|Nazwa ustawienia|Szczegóły|
    |---------|--------------------|
    |**Nazwa**|Określ nazwę dla tych zasad.|
    |**Opis**|Opcjonalnie określ opis dla tych zasad.|
    |**Ogranicz zawartość sieci Web wyświetlaną w zarządzanej przeglądarce firmowej**|Jeśli to ustawienie jest włączone, wszystkie linki w aplikacji będą otwierane w zarządzanej przeglądarce. Aby ta opcja działała, aplikacja musi być wdrożona na urządzeniach.|
    |**Nie zezwalaj na kopie zapasowe systemu Android** lub **Nie zezwalaj na kopie zapasowe programu iTunes i usługi iCloud**|To ustawienie wyłącza wykonywanie kopii zapasowych informacji aplikacji.|
    |**Zezwalaj aplikacji na przesyłanie danych do innych aplikacji**|To ustawienie określa aplikacje, do których ta aplikacja może przesyłać dane. Możesz nie zezwalać na transfer danych do żadnych aplikacji, zezwalać na transfer danych tylko do innych aplikacji zarządzanych lub zezwalać na transfer danych do dowolnych aplikacji. <br /><br />Jeśli na przykład nie zezwalasz na transfer danych, możesz ograniczyć transfer danych do usług, takich jak wiadomości SMS, przypisywanie obrazów do kontaktów oraz publikowanie wpisów w serwisie Facebook lub Twitter.<br /><br />Na urządzeniach z systemem iOS, aby uniemożliwić przesyłanie dokumentów między aplikacjami zarządzanymi i niezarządzanymi, musisz również skonfigurować i wdrożyć zasady zabezpieczeń urządzeń przenośnych, które wyłączają ustawienie **Zezwalaj na niezarządzane dokumenty w innych zarządzanych aplikacjach**. W przypadku zezwolenia na przesyłanie tylko do innych aplikacji zarządzanych do otwierania zawartości odpowiednich typów będą używane przeglądarki plików PDF i obrazów usługi Intune (jeśli je wdrożono).<br /><br />Ponadto jeśli ta opcja zostanie ustawiona na wartość **Aplikacje zarządzane przez zasady** lub **Brak**, zostanie zablokowana funkcja systemu iOS 9, która umożliwia narzędziu Spotlight Search wyszukiwanie danych w ramach aplikacji.<br><br>To ustawienie nie kontroluje użycia funkcji Otwórz za pomocą na urządzeniach przenośnych. Aby zarządzać funkcją Otwórz za pomocą, zobacz [Zarządzanie przesyłaniem danych między aplikacjami systemu iOS za pomocą usługi Microsoft Intune](manage-data-transfer-between-ios-apps-with-microsoft-intune.md).|
    |**Zezwalaj aplikacji na odbieranie danych z innych aplikacji**|To ustawienie określa aplikacje, z których ta aplikacja może odbierać dane. Możesz nie zezwalać na transfer danych z żadnych aplikacji, zezwalać na transfer danych tylko z innych aplikacji zarządzanych lub zezwalać na przesyłanie danych z dowolnych aplikacji.<br /><br />Gdy użytkownik uzyskuje dostęp do danych z aplikacji, która nie jest zarządzana przez zasady zarządzania aplikacjami mobilnymi, te dane będą traktowane jako dane firmowe i będą chronione przez zasady. Dotyczy to aplikacji dla systemu iOS obsługujących wiele tożsamości (w przypadku których usługa Intune stosuje ustawienia zarządzania tylko do firmowych kont lub danych w aplikacji). Może to też dotyczyć zarejestrowanych urządzeń z zastosowanymi zasadami zarządzania aplikacjami mobilnymi.|
    |**Nie zezwalaj na używanie polecenia „Zapisz jako”**|To ustawienie wyłącza opcję **Zapisz jako** we wszystkich aplikacjach korzystających z tych zasad w celu zapisywania danych w chmurze osobistej (na przykład w usłudze OneDrive lub Dropbox).|
    |**Ogranicz wycinanie, kopiowanie i wklejanie w innych aplikacjach**|To ustawienie określa możliwości korzystania z operacji wycinania, kopiowania i wklejania w ramach aplikacji. Wybierz spośród opcji:<br /><br />**Zablokowane**. Nie zezwalaj na wycinanie, kopiowanie i wklejanie między tą aplikacją i innymi aplikacjami.<br /><br />**Aplikacje zarządzane przez zasady**. Zezwalaj na wycinanie, kopiowanie i wklejanie tylko między tą aplikacją i innymi aplikacjami zarządzanymi.<br /><br />**Aplikacje zarządzane przez zasady z funkcją wklejania**. Zezwalaj na wklejanie wyciętych i skopiowanych danych z tej aplikacji tylko do innych aplikacji zarządzanych. Zezwalaj na wklejanie w tej aplikacji danych wyciętych lub skopiowanych z dowolnych aplikacji.<br /><br />**Dowolna aplikacja**. Nie nakładaj żadnych ograniczeń na operacje wycinania, kopiowania i wklejania dotyczące tej aplikacji.<br /><br />Aby możliwe było wykonywanie operacji kopiowania i wklejania danych między aplikacjami zarządzanymi, obie aplikacje muszą mieć skonfigurowane ustawienie **Aplikacje zarządzane przez zasady** lub **Aplikacje zarządzane przez zasady z funkcją wklejania**.|
    |**Wymagaj prostego numeru PIN w celu udzielenia dostępu**|To ustawienie wymaga, aby w celu korzystania z aplikacji użytkownik musiał wprowadzić określony przez siebie numer PIN. Użytkownik zostanie poproszony o skonfigurowanie numeru podczas pierwszego uruchomienia aplikacji.|
    |**Liczba prób przed zresetowaniem numeru PIN**|Określ liczbę prób wprowadzenia numeru PIN, po której użytkownik musi zresetować ten numer.|
    |**Wymagaj poświadczeń firmowych w celu udzielenia dostępu**|To ustawienie wymaga, aby użytkownik wprowadził swoje firmowe informacje logowania, zanim uzyska dostęp do aplikacji.|
    |**Wymagaj zgodności urządzenia z zasadami firmowymi w celu udzielenia dostępu**|To ustawienie umożliwia korzystanie z aplikacji tylko wtedy, gdy urządzenie nie ma zdjętych zabezpieczeń systemu lub nie jest możliwy dostęp do urządzenia z uprawnieniami administratora.|
    |**Ponownie sprawdź wymagania dostępu po (w minutach)**|W polu **Limit czasu** określ częstotliwość sprawdzania wymagań dostępu aplikacji po jej otwarciu.|
    |**Okres prolongaty w trybie offline**|Jeśli urządzenie jest w trybie offline, określ czas do ponownego sprawdzenia wymagań dostępu aplikacji.|
    |**Szyfruj dane aplikacji**|To ustawienie określa, że wszystkie dane skojarzone z tą aplikacją będą szyfrowane. Obejmuje to również dane przechowywane zewnętrznie, na przykład na kartach SD.<br /><br />**Szyfrowanie dla systemu iOS**<br /><br />W przypadku aplikacji, które są skojarzone z zasadami zarządzania aplikacjami mobilnymi usługi Intune, dane są szyfrowane, gdy nie są używane, za pomocą szyfrowania na poziomie urządzenia obsługiwanego przez system operacyjny. Ta funkcja jest włączana za pomocą zasad numeru PIN urządzenia ustawianych przez administratora IT. Jeśli numer PIN jest wymagany, dane będą szyfrowane zgodnie z ustawieniami zasad zarządzania aplikacjami mobilnymi. Zgodnie z dokumentacją firmy Apple [moduły używane przez system iOS mają certyfikaty FIPS 140-2](http://support.apple.com/en-us/HT202739).<br /><br />**Szyfrowanie dla systemu Android**<br /><br />W przypadku aplikacji, które są skojarzone z zasadami zarządzania aplikacjami mobilnymi usługi Intune, szyfrowanie jest obsługiwane przez firmę Microsoft. Dane są szyfrowane synchronicznie podczas operacji wejścia/wyjścia na plikach.  Zawartość w magazynie urządzenia będzie zawsze zaszyfrowana. Metoda szyfrowania nie ma certyfikatu FIPS 140-2.|
    |**Zablokuj przechwytywanie ekranu** (tylko urządzenia z systemem Android)|To ustawienie określa, że możliwości przechwytywania ekranu urządzenia są blokowane podczas korzystania z tej aplikacji.|

4. Gdy skończysz, wybierz pozycję **Zapisz zasady**.

Nowe zasady zostaną wyświetlone w węźle **Zasady konfiguracji** w obszarze roboczym **Zasady**.

## <a name="step-4-associate-the-app-with-a-mobile-application-management-policy-and-then-deploy-the-app"></a>Krok 4. Kojarzenie aplikacji z zasadami zarządzania aplikacjami mobilnymi, a następnie wdrażanie aplikacji
Upewnij się, że wybrano zasady zarządzania aplikacjami mobilnymi na stronie **Zarządzanie aplikacjami mobilnymi** w oknie dialogowym **Zarządzanie wdrażaniem**, aby skojarzyć zasady z aplikacją.

Aby uzyskać szczegółowe informacje, zobacz [Wdrażanie aplikacji w usłudze Microsoft Intune](deploy-apps.md).

> [!IMPORTANT]
> Jeśli rejestracja urządzenia w usłudze Intune zostanie wycofana, zasady nie zostaną usunięte z aplikacji. Aplikacje, do których zastosowano zasady, zachowują ustawienia zasad w przypadku ich odinstalowania i ponownego zainstalowania.

### <a name="what-to-do-when-an-app-is-already-deployed-on-devices"></a>Co robić, jeśli aplikacja została już wdrożona na urządzeniach
W niektórych sytuacjach po wdrożeniu aplikacji może się okazać, że jeden z wybranych użytkowników lub urządzeń ma już zainstalowaną niezarządzaną wersję aplikacji. Na przykład gdy użytkownik zainstalował program Microsoft Word ze sklepu z aplikacjami.

W takim przypadku należy poprosić użytkownika o ręczne odinstalowanie niezarządzanej wersji, co umożliwi zainstalowanie zarządzanej skonfigurowanej wersji.

W przypadku urządzeń z systemem iOS 9 lub nowszym usługa Intune automatycznie poprosi użytkownika o zgodę na przejęcie zarządzania istniejącą aplikacją. Jeśli użytkownik wyrazi zgodę, aplikacja stanie się aplikacją zarządzaną przez usługę Intune, a wszystkie zasady zarządzania aplikacjami mobilnymi skojarzone z aplikacją również będą stosowane.

> [!TIP]
> Jeśli urządzenie działa w trybie nadzorowanym, usługa Intune przejmie zarządzanie istniejącymi aplikacjami bez pytania użytkownika o zgodę.

## <a name="step-5-monitor-the-app-deployment"></a>Krok 5. Monitorowanie wdrożenia aplikacji
Po utworzeniu i wdrożeniu aplikacji skojarzonej z zasadami zarządzania aplikacjami mobilnymi używaj następujących procedur do monitorowania aplikacji i rozwiązywania konfliktów zasad.

#### <a name="to-view-the-status-of-the-deployment"></a>Aby wyświetlić stan wdrożenia

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) wybierz pozycję **Grupy** &gt; **Przegląd**.

2.  Wykonaj jeden z następujących kroków:

    -   Wybierz pozycję **Wszyscy użytkownicy**, a następnie kliknij dwukrotnie użytkownika, którego urządzenie chcesz sprawdzić. Na stronie **Właściwości użytkownika** wybierz pozycję **Urządzenia**, a następnie kliknij dwukrotnie urządzenie do sprawdzenia.

    -   Wybierz pozycję **Wszystkie urządzenia** &gt; **Wszystkie urządzenia przenośne**. Na stronie **Właściwości grupy urządzeń** wybierz pozycję **Urządzenia**, a następnie kliknij dwukrotnie urządzenie do sprawdzenia.

3.  Na stronie **Właściwości urządzenia przenośnego** wybierz pozycję **Zasady**, aby wyświetlić listę zasad zarządzania aplikacjami mobilnymi, które zostały wdrożone na urządzeniu.

4.  Wybierz zasady zarządzania aplikacjami mobilnymi, których stan chcesz sprawdzić. Szczegóły zasad będą widoczne w okienku u dołu. Rozwiń ich węzeł, aby wyświetlić ustawienia.

5.  W kolumnie **Stan** poszczególnych zasad zarządzania aplikacjami mobilnymi będą wyświetlane wartości **Zgodne**, **Zgodne (oczekiwanie)**lub **Błąd**. Jeśli co najmniej jedno ustawienie wybranych zasad powoduje konflikt, w tym polu będzie wyświetlana wartość **Błąd**.

6.  Po zidentyfikowaniu konfliktu możesz skorygować sprzeczne ustawienia zasad, aby używać tego samego ustawienia, lub wdrożyć tylko jedne zasady dla aplikacji i użytkownika.

### <a name="how-policy-conflicts-are-resolved"></a>Jak są rozwiązywane konflikty zasad
Jeśli konflikt zasad zarządzania aplikacjami mobilnymi wystąpi przy pierwszym wdrożeniu dla użytkownika lub urządzenia, wartość ustawienia powodująca konflikt zostanie usunięta z zasad wdrożonych dla aplikacji. Aplikacja będzie używać wartości wbudowanej.

Jeśli konflikt zasad zarządzania aplikacjami mobilnymi wystąpi przy kolejnym wdrożeniu dla aplikacji lub użytkownika, wartość ustawienia powodująca konflikt nie zostanie zaktualizowana w zasadach zarządzania aplikacjami mobilnymi wdrożonych dla aplikacji. Aplikacja będzie używać istniejącej wartości tego ustawienia.

W przypadkach, gdy urządzenie lub użytkownik otrzyma dwie zasady powodujące konflikt, stosuje się następujące działania:

-   Jeśli dla urządzenia już wdrożono zasady, istniejące ustawienia zasad nie zostaną zastąpione.

-   Jeśli dla urządzenia nie wdrożono wcześniej żadnych zasad i zostaną wdrożone dwa ustawienia powodujące konflikt, będzie używane domyślne ustawienie urządzenia.



<!--HONumber=Dec16_HO5-->


