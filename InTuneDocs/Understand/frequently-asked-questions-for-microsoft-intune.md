---
# required metadata

title: Często zadawane pytania | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a8126cca-9ec4-454b-a20b-dc1bb6797327

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Często zadawane pytania dotyczące usługi Microsoft Intune
Ten artykuł zawiera odpowiedzi na niektóre często zadawane pytania dotyczące usługi Intune. Jeśli nie widzisz tutaj odpowiedź na swoje pytanie, [daj nam znać](https://microsoftintune.uservoice.com/).

## Ogólne problemy

-   **Jak sprawdzić, czy usługa Intune została zaktualizowana?**

    Zaloguj się do swojego konta w witrynie manage.microsoft.com. W obszarze Przegląd administracji wybierz pozycję **Wyświetl stan usługi**. W tym miejscu są podane lokalizacja dzierżawy i harmonogram konserwacji. Przeczytaj o aktualizacjach usługi w artykule [Co nowego](/intune/deploy-use/whats-new-in-microsoft-intune).

-   **Jeśli użytkownik zmieni nazwę urządzenia w aplikacji Portal firmy, czy ta nazwa zostanie zmieniona w usłudze Intune lub programie Configuration Manager?**

    Nie, taka zmiana nazwy jest wyłącznie dla wygody użytkownika.

-   **Czy dla urządzeń przenośnych w usłudze Intune jest dostępna funkcja Pomoc zdalna?**

    Nie, nie jest. Przydatne mogą być aplikacje innych producentów, takie jak [Bomgar](http://www.bomgar.com/) i [TeamViewer](https://www.teamviewer.com/).

## Konta

-   **Czy w przypadku rozpoczęcia ewaluacji usługi Intune i utworzenia nowej dzierżawy w wersji próbnej można dodać usługę Office 365 do środowiska ewaluacyjnego przy użyciu tej samej dzierżawy?**

    Tak. Tak. Wystarczy zalogować się jako administrator globalny istniejącej subskrypcji/dzierżawy usługi Intune, np. *globaladmin@&lt;firma&gt;.onmicrosoft.com*.

-   **Czy jeśli przypiszę urząd zarządzania urządzeniami przenośnymi do usługi Intune w okresie próbnym subskrypcji utrudni to przełączenie się do usługi innej firmy w przypadku zmiany zdania na temat usługi Intune?**

    Chociaż trudno nam sobie wyobrazić, że usługa Intune nie spełni Twoich oczekiwań, wybór urzędu zarządzania urządzeniami przenośnymi nie wpływa na możliwość przejścia do innej usługi. W szczególności dotyczy to wyboru między zarządzaniem urządzeniami przenośnymi za pomocą usługi Intune lub za pomocą usługi Intune z programem System Center Configuration Manager.

-   **Czy mogę używać mojej istniejącej nazwy domeny usługi Office 365 z utworzonym później kontem usługi Intune?**

    Tak, jeśli podczas tworzenia wersji próbnej usługi Intune lub aktywacji licencji zalogujesz się za pomocą identyfikatora organizacji skojarzonego z istniejącą dzierżawą usługi Office 365 i zweryfikowaną domeną.

    Usługa Intune będzie używać między innymi tej samej domeny i użytkowników co konto usługi Office 365. Uwaga: każdy użytkownik usługi Office 365 będzie musiał zostać skonfigurowany jako użytkownik usługi Intune z odpowiednią licencją usługi Intune. Musi to zrobić administrator globalny, który zarządza dzierżawcą.

## Rejestrowanie

-   **Gdzie moi użytkownicy mogą dowiedzieć się, jak zarejestrować swoje urządzenia?**

    Możesz użyć lub dostosować informacje z [instrukcji rejestracji w usłudze Microsoft Intune dla administratorów IT](https://gallery.technet.microsoft.com/End-user-Intune-enrollment-55dfd64a).

-   **Jak rozwiązywać problemy z rejestrowaniem urządzeń?**

    Sposoby rozwiązywania typowych problemów z rejestracją zawiera temat [Rozwiązywanie problemów dotyczących rejestrowania urządzeń w usłudze Intune](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune).

-   **Jak zebrać dzienniki rejestracji, jeśli użytkownik ma problem z rejestracją?**

    Postępuj zgodnie z [tymi instrukcjami](http://www.microsoft.com/en-us/download/46391).

## Zarządzanie urządzeniami przenośnymi

-   **Zarządzanie urządzeniami przenośnymi — ogólne**

    -   **Czy usługa Intune wykrywa, że na urządzeniu zdjęto zabezpieczenia systemu?**

        Tak, w niektórych systemach operacyjnych. Aby uzyskać informacje na temat zarządzania urządzeniami, na których zdjęto zabezpieczenia systemu, zobacz [Tworzenie zasad zgodności urządzenia](/intune/deploy-use/create-a-device-compliance-policy-in-microsoft-intune.md).

    -   **Czy mogę selektywnie wyczyścić dane firmowe z urządzenia?**

        Tak. Aby uzyskać informacje o czyszczeniu selektywnym, zobacz [Łatwiejsza ochrona danych za pomocą czyszczenia danych, zdalnego blokowania lub resetowania kodu dostępu](/intune/deploy-use/use-remote-lock-and-passcode-reset-in-microsoft-intune.md).

    -   **Czy można zablokować konkretne witryny sieci Web w przeglądarce urządzenia przenośnego za pośrednictwem usługi Intune?**

        Nie w przeglądarce natywnej danej platformy. Możesz jednak zezwalać na przechodzenie pod adresy URL lub blokować adresy URL po wdrożeniu przeglądarki sieci Web zarządzanej przez usługę Intune na urządzeniach z systemem iOS i Android. Aby uzyskać więcej informacji, zobacz [Zarządzanie dostępem do Internetu za pomocą zasad programu Managed Browser](/intune/Deploy-Use/Manage-Internet-access-using-managed-browser-policies-with-Microsoft-Intune.md).

    -   **Czy możemy uniemożliwić użytkownikowi odinstalowywanie aplikacji?**

        Ogólnie rzecz biorąc — nie. Jednak na nadzorowanym urządzeniu z systemem iOS można uniemożliwić użytkownikowi odinstalowanie aplikacji, która została rozpowszechniona za pośrednictwem narzędzia Apple Configurator. 

    -   **Czy istnieje sposób zarządzania użyciem danych mobilnych?**

        Nie bezpośrednio, ale można zapewnić, że preferowaną metodą nawiązywania połączeń będzie sieć Wi-Fi, wypychając do urządzeń profile sieci Wi-Fi — zgodnie z opisem w temacie [Pomaganie użytkownikom w łączeniu się z sieciami firmowymi przy użyciu profilów sieci Wi-Fi](/intune/Deploy-Use/wi-fi-connections-in-microsoft-intune.md) Ponadto niektóre platformy (na przykład iOS i Android KNOX) umożliwiają sterowanie ustawieniami, takimi jak roaming danych i komunikacja głosowa.

    -   **Czy można uniemożliwić użytkownikowi anulowanie rejestracji urządzenia? Co jeśli jest to urządzenie będące własnością firmy?**

        Ogólnie rzecz biorąc — nie. Jednak za pomocą ustawień niestandardowych systemu Windows Phone można zapobiec anulowaniu rejestracji użytkownika w systemie Windows Phone 8.1. Ponadto użytkownikom można uniemożliwić anulowanie rejestracji urządzeń z systemem iOS, które są nadzorowane i zarejestrowane w programie Device Enrollment Program (DEP) firmy Apple.

    -   **Czy mogę zmienić wybrany urząd zarządzania urządzeniami przenośnymi?**

        W niektórych sytuacjach można zmienić urząd zarządzania urządzeniami przenośnymi. W tym celu należy skontaktować się z pomocą techniczną zgodnie z opisem w temacie [Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](/intune/Troubleshoot/How-to-get-support-for-Microsoft-Intune.md). W poniższej tabeli opisano, jakie zmiany są możliwe. Zmiany dotyczące urzędu zarządzania urządzeniami przenośnymi wymagają ponownego zarejestrowania urządzeń.

        ||**Do:** Intune!**Do:** O365|**Do:** Program Configuration Manager z usługą Intune|
        |**Od:** Intune| |Tak&#42;|Tak|
        |**Od:** O365||Tak&#42;||Tak|
        |**Od:** Program Configuration Manager z usługą Intune|Tak|Tak| |
        
        &#42;Urzędy zarządzania urządzeniami przenośnymi usług O365 i Intune mogą współistnieć, co eliminuje konieczność ponownego rejestrowania urządzeń przenośnych.



-   **Windows**

    -   **Czy mogę ładować bezpośrednio aplikację ze Sklepu Windows?**

        Aplikacje dostępne publicznie nie mogą być ładowane bezpośrednio. Mimo że można pobrać aplikację XAP, nie można przekazać jej do usługi Intune, ponieważ jest to publiczna aplikacja XAP, zaszyfrowana i podpisana za pomocą certyfikatu podpisywania kodu dewelopera. Tylko samodzielnie opracowane aplikacje podpisane własnym certyfikatem podpisywania kodu można ładować bezpośrednio.

    -   **Czy aplikacje ze Sklepu Windows Phone dystrybuowane za pośrednictwem portalu firmy wymagają, aby użytkownik końcowy miał konto Microsoft?**

        Tak, użytkownik końcowy nie będzie mógł uzyskać aplikacji bez konta Microsoft. Wyjątkiem są ładowane bezpośrednio, prywatne aplikacje biznesowe, które można wdrażać na urządzeniu bez konta Microsoft.

    -   **Czy aby telefonem Windows Phone 8.1 można było zarządzać w usłudze Intune, musi być na nim używane konto Microsoft?**

        Nie. Jednak jest ono potrzebne do zainstalowania większości aplikacji ze sklepu publicznego.

        **Dlaczego w systemie Windows Phone jest wymagany certyfikat firmy Symantec na potrzeby zarządzania?**
        System Windows Phone umożliwia sterowanie sposobem instalowania aplikacji. Każdy użytkownik, który ma konto Microsoft, może instalować aplikacje ze Sklepu Windows Phone. Firmy mogą instalować lub ładować bezpośrednio własne aplikacje biznesowe (LOB) przy użyciu specjalnej procedury opisanej w dokumentacji systemu Windows Phone. W ramach procesu instalowania aplikacji biznesowych urządzenia z systemem Windows Phone traktują jako zaufany tylko jeden specjalny typ certyfikatu wystawionego przez firmę Symantec. Nie ma możliwości użycia innego certyfikatu komercyjnego ani prywatnego. To wymaganie dotyczy nie tylko usługi Intune, ale obowiązuje dla wszystkich rozwiązań zarządzania urządzeniami przenośnymi.

        Certyfikat firmy Symantec umożliwia utworzenie tokenu rejestracji aplikacji (AET). Token rejestracji aplikacji można zainstalować podczas rejestrowania urządzenia w usłudze zarządzania urządzeniami przenośnymi lub innym sposobem z bezpiecznej witryny internetowej albo przy użyciu załącznika wiadomości e-mail. Administratorzy muszą podpisać wszystkie aplikacje biznesowe za pomocą certyfikatu firmy Symantec, korzystając z narzędzi dostępnych w [zestawie SDK systemu Windows Phone](http://go.microsoft.com/fwlink/?LinkId=268439). Gdy użytkownicy próbują zainstalować aplikacje biznesowe, system operacyjny Windows Phone sprawdza zgodność podpisu aplikacji z podpisem zawartym w tokenie rejestracji aplikacji. Jeśli podpisy są zgodne, można kontynuować instalację. Jeśli nie można zweryfikować tokenu rejestracji aplikacji, instalacja nie powiedzie się. Istnieje kilka przyczyn braku możliwości zweryfikowania tokenu rejestracji aplikacji:

        -   Token rejestracji aplikacji nie został zainstalowany na urządzeniu

        -   Token rejestracji aplikacji wygasł

        -   Token rejestracji aplikacji nie został utworzony przy użyciu tego samego certyfikatu firmy Symantec, który został użyty do podpisania aplikacji

        System Windows Phone nie wymaga tokenu rejestracji aplikacji podczas rejestrowania urządzenia w usłudze zarządzania urządzeniami przenośnymi. Wersje usługi Intune, które zostały udostępnione przed listopadem 2014 r., wymagały tokenu rejestracji aplikacji oraz podpisanego pliku ssp.xap, ponieważ nie było możliwości ich zainstalowania poza procesem rejestracji.

    **W jaki sposób jest tworzony token rejestracji aplikacji dla użytkowników usługi Intune?**
  Gdy administratorzy przekazują plik pfx skojarzony z certyfikatem firmy Symantec, usługa Intune automatycznie tworzy token rejestracji aplikacji i wdraża go na zarejestrowanych urządzeniach z systemem Windows Phone. Administratorzy usługi Intune nie muszą korzystać z narzędzia generatora tokenów rejestracji aplikacji, które jest dostępne w zestawie SDK systemu Windows Phone.

      > [!IMPORTANT]
        > Usługa Intune nie obsługuje ręcznego tworzenia tokenu rejestracji aplikacji i wdrażania go innym sposobem.

    **Co spowodowało rezygnację z wymagania certyfikatu firmy Symantec?**
       W wersji wydanej w listopadzie 2014 r. w usłudze Intune wprowadzono zmiany umożliwiające realizację scenariuszy, w których przedsiębiorstwa nie mają certyfikatu firmy Symantec.

       -   Aplikacja Portal firmy dla systemu Windows Phone 8.1 jest dostępna do zainstalowania ze Sklepu, więc nie musi być podpisywana przy użyciu certyfikatu firmy Symantec ani weryfikowana pod kątem zgodności z tokenem rejestracji aplikacji. Zamiast tego aplikacja jest weryfikowana w ramach procesu publikowania w Sklepie.

        -   Urządzenia z systemem Windows Phone 8.1 można rejestrować niezależnie od dostępności tokenu rejestracji aplikacji w telefonie. Jeśli token rejestracji aplikacji jest dostępny, zostanie zainstalowany podczas pierwszego synchronizowania urządzenia z usługą Intune. W przeciwnym razie wciąż można zarządzać urządzeniem w usłudze Intune. Użytkownicy mogą zainstalować aplikację Portal firmy ze Sklepu i używać większości jej funkcji bez konieczności korzystania z certyfikatu firmy Symantec umożliwiającego podpisywanie aplikacji.

        W przypadku urządzeń z systemem Windows Phone 8 nie wprowadzono zmian w zakresie wymagania certyfikatu firmy Symantec. Aby można było zarejestrować urządzenia z systemem Windows Phone 8, musi być na nich dostępny podpisany plik ssp.xap i token rejestracji aplikacji. W razie niespełnienia tego wymagania rejestracja takich urządzeń zostanie zablokowana.

        **Jakie funkcje są obsługiwane w przypadku zarejestrowania urządzenia z systemem Windows Phone 8.1 bez certyfikatu firmy Symantec?**
        Po zarejestrowaniu urządzenia z systemem Windows Phone 8.1 bez certyfikatu firmy Symantec można wykonywać następujące czynności:

        -   Tworzenie zasad i wypychanie ich na urządzenie

        -   Konfigurowanie informacji kontaktowych działu informatycznego, które będą wyświetlane w aplikacji Portal firmy

        -   Tworzenie linków bezpośrednich do Sklepu i wdrażanie ich w aplikacji Portal firmy

        -   Tworzenie linków do stron internetowych i wdrażanie ich w aplikacji Portal firmy

        -   Tworzenie warunków i postanowień, które muszą zostać zaakceptowane przez użytkowników, zanim będą oni mogli korzystać z aplikacji Portal firmy

        Jedyną operacją, której nie można wykonywać bez certyfikatu firmy Symantec, jest wdrażanie aplikacji biznesowych.

        > [!IMPORTANT]
        > Narzędzie Wydawca oprogramowania usługi Intune nie weryfikuje podpisów aplikacji podczas ich przekazywania. W przypadku wdrożenia niepodpisanych aplikacji próba zainstalowania ich przez użytkowników zakończy się niepowodzeniem.

        **Co mogą zrobić użytkownicy, jeśli mają aplikację Portal firmy, ale nie dysponują certyfikatem firmy Symantec?**
        Nie trzeba rejestrować urządzeń z systemem Windows Phone 8.1 przed zainstalowaniem aplikacji Portal firmy ze Sklepu. Jeśli urządzenie nie jest zarejestrowane, zostanie wyświetlony monit o zarejestrowanie go. Dotknięcie monitu w aplikacji Portal firmy spowoduje bezpośrednie przejście do pozycji **Ustawienia / Miejsce pracy**, która umożliwia zarejestrowanie urządzenia.

        Nawet jeśli urządzenie nie zostanie zarejestrowane, użytkownicy mogą wykonywać następujące czynności w aplikacji Portal firmy ze Sklepu:

        -   Akceptowanie lub odrzucanie dowolnych warunków i postanowień skonfigurowanych przez administratora. W przypadku odrzucenia postanowień aplikacja Portal firmy zostanie zamknięta.

        -   Wyświetlanie informacji kontaktowych działu informatycznego

        -   Wyświetlanie zarejestrowanych urządzeń z systemami iOS, Android i Windows

        -   Korzystanie z linków bezpośrednich do aplikacji w Sklepie

        -   Otwieranie stron internetowych za pomocą linków

        Po zarejestrowaniu urządzenia będzie ono widoczne na liście **Moje urządzenia** . Zarejestrowane urządzenie podlega wszystkim zasadom wdrożonym w usłudze Intune. Uzyskiwanie tokenów rejestracji aplikacji oraz instalowanie aplikacji biznesowych wymaga zarejestrowania urządzeń. W przypadku próby zainstalowania aplikacji biznesowej na niezarejestrowanym urządzeniu zostanie wyświetlony monit o zarejestrowanie go.

        Jedyną operacją, której nie można wykonywać, jeśli przedsiębiorstwo nie dysponuje certyfikatem firmy Symantec, jest instalowanie aplikacji biznesowych wdrożonych przez administratora.

        **Nasza firma ma już certyfikat i rejestruje urządzenia z systemem Windows Phone 8.1. Czy trzeba wykonywać dodatkowe czynności, skoro aplikacja Portal firmy jest dostępna w Sklepie?**
        Bieżąca wersja pliku ssp.xap dostępna w Centrum pobierania wciąż działa na urządzeniach z systemem Windows Phone 8.1. Można nadal proponować użytkownikom zarejestrowanie urządzeń w celu uzyskania Portalu firmy podczas instalacji.

        **Jakie są zalety i wady uzyskiwania przez użytkowników aplikacji Portal firmy ze Sklepu?**
        Zalety:

        -   Użytkownicy mogą korzystać z linków bezpośrednich i linków do stron internetowych, nawet jeśli urządzenie z systemem Windows Phone 8.1 nie jest zarejestrowane

        -   W przypadku zaktualizowania aplikacji Portal firmy przez firmę Microsoft aplikacja ze Sklepu zostanie zaktualizowana automatycznie. Nie ma konieczności pobierania, podpisywania ani ponownego wdrażania aplikacji ssp.xap

        -   Instrukcje dla użytkowników w dokumentacji dotyczącej systemów Windows Phone 8.1, iOS, Android i Windows pozostają spójne: „przejdź do Sklepu i zainstaluj aplikację Portal firmy”.

        -   Użytkownicy mogą śledzić proces instalacji aplikacji, a także korzystać z instrukcji dotyczących rejestracji po otwarciu aplikacji

        Wady:

        -   Widoczne jest pole wyboru dotyczące instalacji „**centrum aplikacji firmowych**”, ale z poziomu listy aplikacji urządzenia nie można przejść do aplikacji Portal firmy

        -   Komunikat dotyczący zaakceptowania niestandardowych warunków i postanowień jest wyświetlany dopiero po otwarciu aplikacji Portal firmy

        W następujących sytuacjach można nadal proponować użytkownikom zarejestrowanie urządzeń bez konieczności rezygnacji z instalacji pliku ssp.xap podczas rejestracji:

        -   Jeśli firma zablokuje dostęp do Sklepu z urządzeń z systemem Windows Phone, użytkownicy muszą zainstalować plik ssp.xap podczas rejestracji.

        -   Jeśli użytkownicy nie mają skonfigurowanych kont Microsoft na swoich urządzeniach z systemem Windows Phone, nie będą mogli zainstalować aplikacji Portal firmy ze Sklepu.

        -   Jeśli istniejąca dokumentacja dotycząca rejestracji urządzeń z systemem Windows Phone zawiera instrukcję przejścia w pierwszej kolejności do pozycji Ustawienia > Obszar roboczy, może upłynąć trochę czasu, zanim dokumenty zostaną zaktualizowane, tak aby ich treść zawierała instrukcję przejścia do Sklepu.

        **Czym różni się plik ssp.xap dostępny w Centrum pobierania od aplikacji ze Sklepu?**

        -   Instalacja aplikacji Portal firmy ze Sklepu nie wymaga podpisania za pomocą certyfikatu firmy Symantec

        -   Aplikacja Portal firmy ze Sklepu wyświetla użytkownikowi postanowienia, a aplikacja ssp.xap z Centrum pobierania nie wykonuje tego działania

        -   Plik aplikacji Portal firmy ze Sklepu ma rozszerzenie appx, a nie xap

        **Czy można uzyskać plik aplikacji Portal firmy i wypchnąć go do użytkowników zamiast kierować ich do Sklepu?**
        Tak. Aplikację Portal firmy dla następujących systemów operacyjnych można pobrać z Centrum pobierania:

        -   Windows Phone 8.1: [http://go.microsoft.com/fwlink/?LinkId=615799](http://go.microsoft.com/fwlink/?LinkId=615799)

        -   Windows Phone 8.0: [http://go.microsoft.com/fwlink/?LinkId=268440](http://go.microsoft.com/fwlink/?LinkId=268440)

        -   Windows 8.1: [http://go.microsoft.com/fwlink/?LinkId=615800](http://go.microsoft.com/fwlink/?LinkId=615800)

        **Czy przy zachowaniu przez użytkowników możliwości instalowania aplikacji Portal firmy ze Sklepu firmy wciąż mogą korzystać z narzędzia pomocy technicznej do zarządzania wersją próbną usługi Windows Intune dla systemu Windows Phone, jeśli nie mają certyfikatu firmy Symantec?**
        Tak. Wersja próbna narzędzia do zarządzania współpracuje z wersją portalu firmy dostępną w Sklepie, co umożliwia wykonanie projektu obejmującego instalację aplikacji biznesowych. Dzięki temu, że token rejestracji aplikacji w ramach certyfikatu firmy Symantec nie jest już wymagany do zarejestrowania urządzeń z systemem Windows Phone 8.1, firmy mogą testować instalację aplikacji za pomocą linków bezpośrednich do aplikacji w Sklepie.

        Narzędzie pomocy technicznej do zarządzania wersją próbną usługi Windows Intune dla systemu Windows Phone ma zastosowanie tylko w przypadku subskrypcji wersji próbnej usługi Intune.

        > [!IMPORTANT]
        > Do testowania należy używać tylko wersji próbnej narzędzia do zarządzania. Jeśli certyfikat firmy Symantec dla wersji próbnej narzędzia do zarządzania będzie niedostępny lub firma uzyska własny certyfikat na potrzeby podpisywania aplikacji, urządzenia zarejestrowane przy użyciu tokenu rejestracji aplikacji uzyskanego za pomocą wersji próbnej narzędzia do zarządzania muszą zostać wyrejestrowane i ponownie zarejestrowane.

        **Czy można rozpocząć korzystanie z usługi bez certyfikatu firmy Symantec i dodać go później, po zarejestrowaniu urządzeń z systemem Windows Phone 8.1?**
        Tak. Po zarejestrowaniu urządzeń z systemem Windows Phone 8.1 również można uzyskać certyfikat firmy Symantec, podpisać plik ssp.xap, a następnie przekazać go razem z plikiem pfx. Usługa Intune wygeneruje wtedy token rejestracji aplikacji. Token rejestracji aplikacji zostanie pobrany na urządzenia z systemem Windows Phone 8.1 podczas następnej synchronizacji, w ciągu maksymalnie ośmiu godzin. Po przekazaniu plików xap i pfx odczekaj co najmniej 8 godzin przed wdrażaniem aplikacji biznesowych.


-   **Android**

    -   **Jak długo trwa szyfrowanie urządzenia z systemem Android?**

        Zależy to przede wszystkim od szybkości procesora urządzenia oraz od ilości całkowitej i używanej pamięci, a nie od usługi Intune.

-   **iOS**

    -   **Czy w przypadku wdrażania aplikacji systemu iOS za pomocą usługi Intune kontynuowanie instalacji wymaga określenia dla urządzenie identyfikatora AppleID, jeśli wcześniej przekazano pliki Manifest i IPA aplikacji?**

        Nie. Gdy bity są dostarczane przez usługę Intune (do usługi Intune przekazano plik IPA), aplikacje są ładowane bezpośrednio i nie wymagają identyfikatora Apple ID.

    -   **Czy można umożliwić instalację aplikacji w systemie iOS bez zezwalania na dostęp do sklepu Apple?**

        Nie, ale można włączyć sklep App Store i za pomocą list dozwolonych/zablokowanych aplikacji w systemie iOS monitorować to, co robią użytkownicy. Ładowane bezpośrednio aplikacje biznesowe nie wymagają dostępu do sklepu App Store firmy Apple.

    -   **Czy aplikacje ze sklepu Apple dystrybuowane za pośrednictwem portalu firmy wymagają, aby użytkownik końcowy miał konto iTunes?**

        Tak, użytkownik końcowy nie będzie mógł uzyskać aplikacji bez konta iTunes.

    -   **Czy można zablokować sklep App Store?**

        Tak, można, ale spowoduje to zablokowanie instalacji i aktualizacji wszystkich aplikacji ze sklepu App Store, nie tylko tych zainicjowanych przez użytkownika końcowego. Oznacza to, że za pośrednictwem usługi Intune nie będzie można wdrożyć żadnych publicznych aplikacji ze sklepu App Store.

## Wdrażanie aplikacji

-   **Jak dodać zalecaną aplikację?**

    W usłudze Intune te aplikacje są nazywane „polecanymi” lub „wyróżnionymi” i opisano je w temacie [Wdrażanie aplikacji w usłudze Microsoft Intune](/Intune/Deploy-Use/deploy-apps-in-microsoft-intune.md)..

-   **Czy można uzyskać dodatkową przestrzeń dyskową w chmurze na aplikacje do wdrożenia?**

    Tak. Informacje zawiera temat [Wdrażanie aplikacji](/Intune/Deploy-Use/deploy-apps.md), sekcja *Wymagania dotyczące magazynu w chmurze*.

## Zabezpieczenia

-   **Czy za pomocą usługi Intune można wymusić stosowanie funkcji BitLocker?**

    Agent OMA-DM w systemie Windows 8.1/RT umożliwia odczytanie (uzyskanie) stanu szyfrowania. Nie można go ustawić. Dotyczy to usługi Intune oraz innych usług zarządzania urządzeniami przenośnymi.

-   **Czy jeśli zaszyfruję tablet z systemem Windows 8 za pomocą funkcji BitLocker, to w przypadku kilku kolejnych niepomyślnych prób zalogowania się przez użytkownika mogę wymusić całkowite wyczyszczenie danych z urządzenia?**

    Nie jest dostępna opcja całkowitego wyczyszczenia urządzenia z systemem Windows 8.1/RT dla żadnej usługi zarządzania urządzeniami przenośnymi, w tym usługi Intune. Usługa Intune umożliwia selektywne wyczyszczenie tych urządzeń. Aby uzyskać więcej informacji na temat czyszczenia/selektywnego czyszczenia danych w usłudze Intune, zobacz [Ochrona aplikacji i danych w usłudze Microsoft Intune](/intune/Deploy-Use/protect-apps-and-data-with-microsoft-intune.md).

## Portal firmy

-   **Czy mogę dostosować portal firmy?**

    Tak. W konsoli administracyjnej usługi Intune wybierz pozycję **Administrowanie&gt;Portal firmy**, aby uzyskać dostęp do tych ustawień.

## Usługa Microsoft Intune z programem Configuration Manager

-   **Gdy używam programu Configuration Manager z usługą Intune, gdzie mogę zarządzać moimi urządzeniami?**

    Zarządzaj wszystkimi urządzeniami w konsoli programu Configuration Manager, mimo że urządzenia z zainstalowanym agentem usługi Intune będą wyświetlane w konsoli usługi Intune. Urządzenia przenośne nie będą wyświetlane w konsoli usługi Intune.

-   **Czy można selektywnie czyścić dane na urządzeniach?**

    Jeśli używasz programu System Center 2012 R2 Configuration Manager lub nowszego z usługą Intune, możesz wykonać selektywne czyszczenie, które spowoduje usunięcie danych firmy. Aby uzyskać więcej informacji, zobacz [Ochrona aplikacji i danych w usłudze Microsoft Intune](/intune/Deploy-Use/protect-apps-and-data-with-microsoft-intune.md).

-   **Jeśli używam programu Configuration Manager z usługą Intune, czy nadal mogę korzystać z portalu administratora usługi Intune?**

    Tak, ale z poziomu tego portalu będzie można zarządzać jedynie komputerami z zainstalowanym agentem usługi Intune. Portal zawiera też inne przydatne informacje dotyczące alertów związanych z usługą, stanu usługi itp. Jednak żadne dostępne w nim ustawienia zarządzania urządzeniami nie dotyczą zarejestrowanych urządzeń.



<!--HONumber=May16_HO1-->


