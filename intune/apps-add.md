---
title: Dodawanie aplikacji do usługi Microsoft Intune
titlesuffix: ''
description: Dowiedz się, jak dodawać aplikacje do usługi Microsoft Intune, aby móc przypisywać aplikacje do użytkowników i urządzeń. Usługa Intune obsługuje szeroką gamę różnych typów aplikacji.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 06/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2db9d991c476d89399058137adb972c06029befc
ms.sourcegitcommit: 391755a4c8a38e3a22744516fd27d75e40438899
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/13/2018
ms.locfileid: "39028732"
---
# <a name="add-apps-to-microsoft-intune"></a>Dodawanie aplikacji do usługi Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Aby móc przypisywać, monitorować, konfigurować i chronić aplikacje, trzeba najpierw dodać je do usługi Intune.

Użytkownicy aplikacji i urządzeń w firmie (pracownicy firmy) mogą mieć kilka wymagań dotyczących aplikacji. Przed dodaniem aplikacji do usługi Intune i udostępnieniem ich pracownikom musisz ocenić i zrozumieć kilka podstawowych informacji na temat aplikacji. Musisz poznać różne typy aplikacji dostępne dla usługi Intune. Konieczna jest ocena wymagań dotyczących aplikacji, takich jak platformy i możliwości potrzebne pracownikom. Musisz określić, czy będziesz używać usługi Intune do zarządzania urządzeniami (w tym aplikacjami), czy do zarządzania aplikacjami bez zarządzania urządzeniami. Wreszcie musisz określić aplikacje i możliwości, których potrzebują pracownicy oraz komu są one potrzebne. Informacje przedstawione w tym artykule ułatwiają rozpoczęcie pracy.

## <a name="app-types-in-microsoft-intune"></a>Typy aplikacji w usłudze Microsoft Intune

Usługa Intune obsługuje szeroką gamę różnych typów aplikacji. Dostępne opcje różnią się dla poszczególnych typów aplikacji. Usługa Intune pozwala dodawać i przypisywać następujące typy aplikacji:

| Typy aplikacji | Instalacja | Updates |
|---|---|---|
| Aplikacje ze sklepu | Usługa Intune instaluje aplikację na urządzeniu.  | Aktualizacje aplikacji są automatyczne.   |
| Aplikacje napisane w firmie (biznesowe)  | Usługa Intune instaluje aplikację na urządzeniu (dostarczasz plik instalacyjny).     | Należy zaktualizować aplikację.  |
| Aplikacje, które są wbudowane (aplikacje wbudowane)    | Usługa Intune instaluje aplikację na urządzeniu.  | Aktualizacje aplikacji są automatyczne.  |
| Aplikacje w Internecie (link internetowy) | Usługa Intune tworzy skrót do aplikacji internetowej na ekranie głównym urządzenia.  | Aktualizacje aplikacji są automatyczne.    |

### <a name="specific-app-type-details"></a>Szczegóły typów specyficznych dla aplikacji
 
W poniższej tabeli przedstawiono typy specyficzne dla aplikacji i sposób ich dodawania za pomocą okienka **Dodaj aplikację** w usłudze Intune:

| **Typ specyficzny dla aplikacji** | **Typ ogólny** | **Procedury specyficzne dla aplikacji** |
| --- | --- | --- |
| Aplikacje ze sklepu dla systemu Android  | Aplikacja ze sklepu  | Wybierz **Android** jako **typ aplikacji**, a następnie wprowadź adres URL sklepu Google Play dla aplikacji. |
| Aplikacje ze sklepu dla systemu iOS  | Aplikacja ze sklepu  | Wybierz **iOS** jako **typ aplikacji**, wyszukaj aplikację i wybierz aplikację w usłudze Intune. |
| Aplikacje ze sklepu dla systemu Windows Phone 8.1  | Aplikacja ze sklepu  | Wybierz **Windows Phone 8.1** jako **typ aplikacji**, a następnie wprowadź adres URL Sklepu Microsoft dla aplikacji. |
| Aplikacje ze sklepu Microsoft Store  | Aplikacja ze sklepu  | Wybierz **Windows** jako **typ aplikacji**, a następnie wprowadź adres URL sklepu Microsoft Store dla aplikacji. |
| Aplikacje profilu służbowego systemu Android | Aplikacja ze sklepu  | Znajdź i zatwierdź aplikację profilu służbowego systemu Android w zarządzanym sklepie Google Play.  |
| Aplikacje pakietu Office 365 dla systemu Windows 10  | Aplikacja ze sklepu (Office 365) | W obszarze **Pakiet Office 365** wybierz **Windows 10** jako **typ aplikacji**, a następnie wybierz aplikację usługi Office 365, którą chcesz zainstalować.  |
| Aplikacje pakietu Office 365 dla systemu macOS | Aplikacja ze sklepu (Office 365) | W obszarze **Pakiet Office 365** wybierz **macOS** jako **typ aplikacji**, a następnie wybierz pakiet aplikacji usługi Office 365. |
| Aplikacje biznesowe (LOB) dla systemu Android | Aplikacja LOB | Wybierz aplikację **Biznesowa** jako **typ aplikacji**, wybierz pozycję **Plik pakietu aplikacji**, a następnie wprowadź plik instalacyjny systemu Android z rozszerzeniem **.apk**.  |
| Aplikacje LOB dla systemu iOS | Aplikacja LOB | Wybierz aplikację **Biznesowa** jako **typ aplikacji**, wybierz pozycję **Plik pakietu aplikacji**, a następnie wprowadź plik instalacyjny systemu iOS z rozszerzeniem **.ipa**.  |
| Aplikacje LOB dla systemu Windows Phone | Aplikacja LOB | Wybierz opcję **Biznesowa** jako **typ aplikacji**, wybierz pozycję **Plik pakietu aplikacji**, a następnie wprowadź plik instalacyjny systemu Windows Phone z rozszerzeniem **xap**.  |
| Aplikacja LOB dla systemu Windows | Aplikacja LOB | Wybierz opcję **Biznesowa** jako typ aplikacji, wybierz pozycję **Plik pakietu aplikacji**, a następnie wprowadź plik instalacyjny systemu Windows z rozszerzeniem **msi**, **appx** lub **appxbundle**. |
| Wbudowana aplikacja systemu iOS  | Aplikacja wbudowana | Wybierz pozycję **Aplikacja wbudowana** jako **typ aplikacji**, a następnie wybierz wbudowaną aplikację z listy dostarczonych aplikacji.  |
| Wbudowana aplikacja systemu Android  | Aplikacja wbudowana | Wybierz pozycję **Aplikacja wbudowana** jako **typ aplikacji**, a następnie wybierz wbudowaną aplikację z listy dostarczonych aplikacji.  |
| Aplikacje internetowe  | Aplikacja internetowa  | Wybierz **Link internetowy** jako **typ aplikacji**, a następnie wprowadź prawidłowy adres URL wskazujący aplikację internetową.  |

Aby dodać aplikację w usłudze Microsoft Intune, wybierz kolejno pozycje **Aplikacje mobilne** > **Aplikacje** > **Dodaj**. Zostanie wyświetlone okienko **Dodaj aplikację**, w którym możesz wybrać **Typ aplikacji**. 

>[!TIP]
> Aplikacja biznesowa (LOB) to aplikacja dodawana za pomocą pliku instalacyjnego aplikacji. Aby na przykład zainstalować aplikację LOB systemu iOS, należy dodać tę aplikację, wybierając pozycję **Aplikacja biznesowa** jako **Typ aplikacji** w okienku **Dodaj aplikację**. Następnie należy wybrać plik pakietu aplikacji (z rozszerzeniem ipa). Aplikacje tego typu są zwykle pisane w firmie.

## <a name="assess-app-requirements"></a>Ocena wymagań dotyczących aplikacji
Jako administrator IT określasz nie tylko aplikacje, które mają być używane przez Twoją grupę, ale także możliwości wymagane przez każdą grupę i podgrupę. Dla każdej aplikacji określasz wymagane platformy, grupy użytkowników, które potrzebują aplikacji, zasady konfiguracji, które mają zostać zastosowane dla tych grup, oraz zasady ochrony do zastosowania.  

Ponadto musisz określić, czy będziesz się koncentrować na zarządzaniu urządzeniami przenośnymi (MDM), czy tylko na zarządzaniu aplikacjami mobilnymi (MAM). 

Korzystanie z usługi Intune do zarządzania urządzeniami (MDM) jest przydatne w następujących przypadkach:
- Do wydajnej pracy użytkownicy potrzebują profilu łączności firmowej (Wi-Fi lub VPN).
- Użytkownicy potrzebują zestawu aplikacji, który ma zostać wypchnięty na ich urządzenia.
- Twoja organizacja musi zapewnić zgodność z przepisami lub innymi zasadami, które wymagają użycia określonych kontrolek MDM, na przykład na potrzeby bezpieczeństwa lub szyfrowania.

Używanie usługi Intune do zarządzania aplikacjami przy użyciu usługi MAM bez konieczności zarządzania urządzeniami jest przydatne w następujących przypadkach:
- Chcesz, aby użytkownicy mogli używać swoich własnych urządzeń (BYOD).
- Aby powiadomić użytkowników, że włączono zabezpieczenia MAM, chcesz udostępnić im jednorazowe wyskakujące okienko, zamiast wysyłać im ciągłe powiadomienia na poziomie urządzenia.
- Chcesz zapewnić zgodność z zasadami, które na urządzeniach osobistych wymagają mniejszych możliwości zarządzania. Na przykład chcesz zarządzać danymi firmowymi dla aplikacji, a nie dla całego urządzenia.

Aby uzyskać więcej informacji, zobacz [Porównanie zarządzania urządzeniami przenośnymi i zarządzania aplikacjami mobilnymi](byod-technology-decisions.md).

### <a name="determine-who-will-use-the-app"></a>Określanie osób mogących korzystać z aplikacji

Gdy chcesz określić, które aplikacje są potrzebne Twoim pracownikom, uwzględnij różne grupy użytkowników i oceń, jakich aplikacji używają. Znajomość tych grup jest przydatna również podczas dodawania aplikacji. Po dodaniu aplikacji możesz przypisać grupę użytkowników, którzy będą mogli z niej korzystać. 

Najpierw na podstawie stopnia poufności danych zawartych w aplikacji musisz określić, która grupa powinna mieć dostęp do aplikacji. Konieczne może być uwzględnienie lub wykluczenie niektórych rodzajów ról w organizacji. Na przykład dla grupy sprzedaży mogą być wymagane tylko niektóre aplikacje biznesowe, a osobom pracującym w dziale technicznym, finansowym, prawniczym lub w księgowości aplikacje biznesowe mogą nie być w ogóle potrzebne. Ponadto grupa sprzedaży może potrzebować dodatkowej ochrony danych oraz dostępu do wewnętrznych usług firmowych na swoich urządzeniach przenośnych. Należy określić, w jaki sposób ta grupa będzie łączyć się z zasobami przy użyciu aplikacji. Czy dane, do których uzyskuje dostęp aplikacja, znajdują się w chmurze, czy na komputerze lokalnym? Trzeba również wiedzieć, jak użytkownicy będą łączyć się z zasobami przy użyciu aplikacji. 

Ponadto usługa Intune obsługuje umożliwianie dostępu do aplikacji mobilnych, które wymagają bezpiecznego dostępu do danych lokalnych, takich jak serwery aplikacji biznesowych. Ten typ dostępu jest zazwyczaj oferowany przy użyciu [zarządzanych przez usługę Intune certyfikatów](certificates-configure.md) kontroli dostępu w połączeniu ze standardową bramą sieci VPN lub serwerem proxy w sieci obwodowej, takim jak serwer proxy aplikacji usługi Azure Active Directory. [Narzędzie opakowujące aplikacje i zestaw SDK aplikacji](apps-prepare-mobile-application-management.md) usługi Intune może pomóc w zamknięciu udostępnianych danych wewnątrz aplikacji biznesowej, aby nie mogła przekazywać danych firmowych do aplikacji lub usług konsumenckich.

W [przewodniku planowania, projektowania i implementowania wdrożenia usługi Intune](planning-guide.md) znajdują się informacje pomocne przy określaniu sposobu identyfikowania grup organizacyjnych powiązanych z poszczególnymi scenariuszami aplikacji przypadków użycia i podrzędnych przypadków użycia. Aby uzyskać informacje dotyczące przypisywania aplikacji do grup, zobacz temat [Przypisywanie aplikacji do grup w usłudze Microsoft Intune](apps-deploy.md).

### <a name="determine-the-type-of-app-for-your-solution"></a>Określanie typu aplikacji dla rozwiązania

Można wybrać następujące typy aplikacji:
- **Aplikacje ze sklepu**: aplikacje, które zostały przekazane do sklepu Microsoft Store, sklepu dla systemu iOS lub sklepu dla systemu Android. Dostawca aplikacji ze sklepu obsługuje i udostępnia jej aktualizacje. Administrator wybiera aplikację z listy w sklepie i przy użyciu usługi Intune dodaje ją jako aplikację dostępną dla użytkowników.
- **Aplikacje napisane w firmie (biznesowe)**: aplikacje tworzone w firmie to aplikacje biznesowe (LOB). Funkcje aplikacji tego typu zostały zaprojektowane dla jednej z obsługiwanych przez usługę Intune platform, takich jak Windows, iOS lub Android. Aktualizacje są tworzone i dostarczane przez organizację w postaci oddzielnych plików. Aby dostarczyć aktualizacje aplikacji do użytkowników, należy je dodać i wdrożyć za pomocą usługi Intune.
- **Aplikacje w Internecie**: aplikacje internetowe to aplikacje typu klient/serwer. Serwer udostępnia aplikację internetową, która obejmuje interfejs użytkownika, zawartość i funkcje. Ponadto nowoczesne internetowe platformy hostingowe często oferują zabezpieczenia, równoważenie obciążenia i inne korzyści. Aplikacje tego typu są oddzielnie obsługiwane w Internecie. Usługa Intune umożliwia wskazanie tego typu aplikacji. Można także przypisać grupy użytkowników, które będą mogły uzyskiwać dostęp do takiej aplikacji. Należy pamiętać, że system Android nie obsługuje aplikacji internetowych.

Podczas określania, które aplikacje są wymagane w organizacji, należy uwzględnić, w jaki sposób integrują się one z usługami w chmurze, do jakich danych mają dostęp, czy są dostępne dla użytkowników korzystających z własnych urządzeń oraz czy wymagają dostępu do Internetu.

Aby uzyskać więcej informacji na temat typów aplikacji potrzebnych w organizacji, zobacz temat „Aplikacje” w sekcji „Wymagania dotyczące funkcji” w artykule [Tworzenie projektu](planning-guide-design.md#feature-requirements).

### <a name="understanding-app-management-and-protection-policies"></a>Zarządzanie aplikacjami i zasady ich ochrony
Usługa Intune umożliwia modyfikowanie funkcji wdrażanych aplikacji w taki sposób, aby były zgodne z firmowymi zasadami dotyczącymi zgodności i zabezpieczeń. Dzięki temu możesz określić, w jaki sposób są chronione dane firmowe. Aplikacje zarządzane przez usługę Intune zawierają bogaty zestaw zasad ochrony aplikacji mobilnych, takich jak:

- Ograniczanie funkcji kopiowania i wklejania oraz zapisywania jako.
- Konfigurowanie linków internetowych na potrzeby otwierania w aplikacji Intune Managed Browser.
- Włączanie użycia wielu tożsamości i dostępu warunkowego na poziomie aplikacji.

W aplikacjach zarządzanych przez usługę Intune można również włączyć ochronę aplikacji bez konieczności rejestrowania się, co daje możliwość zastosowania zasad zapobiegania utracie danych z pominięciem zarządzania urządzeniem użytkownika. Dodatkowo istnieje możliwość dołączania funkcji zarządzania aplikacjami mobilnymi do aplikacji mobilnych i biznesowych za pomocą zestawu SDK aplikacji usługi Intune i narzędzia opakowującego aplikacje. Aby uzyskać więcej informacji o tych narzędziach, zobacz [Omówienie zestawu SDK aplikacji usługi Intune](app-sdk.md).

### <a name="understanding-licensed-apps"></a>Licencjonowane aplikacje
Oprócz zapoznania się z aplikacjami internetowymi, aplikacjami ze sklepu i aplikacjami biznesowymi należy także znać miejsca docelowe aplikacji programu zakupów zbiorczych i aplikacji licencjonowanych, takich jak: 
- **Apple Volume Purchasing Program for Business (iOS i MacOS)**: ten sklep z aplikacjami systemu iOS umożliwia zakup wielu licencji dla aplikacji, które mają być uruchamiane w firmie. Zakup wielu kopii ułatwia efektywne zarządzanie aplikacjami w firmie. Aby uzyskać więcej informacji, zobacz [Zarządzanie aplikacjami dla systemu iOS nabytymi w ramach zakupów zbiorczych](vpp-apps-ios.md).
- **Profil służbowy systemu Android**: przypisywanie aplikacji do urządzeń z profilem służbowym systemu Android przebiega inaczej niż przypisywanie aplikacji do urządzeń ze standardową wersją systemu Android. Wszystkie aplikacje, które instalujesz dla profilów służbowych Android, pochodzą z zarządzanego sklepu Google Play. Proces obejmuje zalogowanie się do sklepu, wyszukanie odpowiednich aplikacji, a następnie ich zatwierdzenie. Następnie aplikacja zostaje wyświetlona w węźle **Licencjonowane aplikacje** w witrynie Azure Portal i można zarządzać przypisaniem aplikacji w taki sam sposób, jak w przypadku wszystkich innych.
- **Microsoft Store dla Firm (Windows 10)**: Microsoft Store dla Firm to miejsce, w którym można znaleźć i zakupić aplikacje dla całej organizacji, pojedynczo lub zbiorczo. Łącząc sklep z usługą Microsoft Intune, aplikacjami nabytymi w ramach zakupów zbiorczych można zarządzać bezpośrednio w witrynie Azure Portal. Aby uzyskać więcej informacji, zobacz [Zarządzanie aplikacjami zakupionymi w Sklepie Microsoft dla Firm](windows-store-for-business.md).

## <a name="before-you-add-apps"></a>Przed dodaniem aplikacji
Przed rozpoczęciem dodawania i przypisywania aplikacji należy wziąć pod uwagę poniższe kwestie:

- W przypadku dodawania i przypisywania aplikacji ze sklepu użytkownicy muszą mieć konto w danym sklepie, aby móc zainstalować daną aplikację.
- Niektóre przypisywane aplikacje lub elementy mogą być zależne od wbudowanych aplikacji systemu iOS. Na przykład, jeśli przypisujesz książkę ze sklepu iOS, w urządzeniu musi być zainstalowana aplikacja iBooks. W przypadku usunięcia wbudowanej aplikacji iBooks nie ma możliwości użycia usługi Intune do jej przywrócenia.

## <a name="cloud-storage-space"></a>Miejsce do magazynowania w chmurze
Wszystkie aplikacje tworzone przy użyciu instalatora oprogramowania (na przykład aplikacje biznesowe) zostają spakowane i przekazane do magazynu w chmurze usługi Intune. Subskrypcja próbna usługi Intune obejmuje 2 GB magazynu opartego na chmurze, który jest używany do przechowywania zarządzanych aplikacji i aktualizacji. Pełna subskrypcja nie ogranicza łącznej ilości miejsca do magazynowania.

Wymagania dotyczące miejsca do magazynowania w chmurze są następujące:

- Wszystkie pliki instalacyjne aplikacji muszą znajdować się w tym samym folderze.
- Maksymalny rozmiar dowolnego przekazywanego pliku wynosi 2 GB.

## <a name="create-and-edit-categories-for-apps"></a>Tworzenie i edytowanie kategorii aplikacji

Kategorie aplikacji mogą ułatwić ich sortowanie, aby użytkownicy mogli je łatwiej znaleźć w portalu firmy. Do aplikacji można przypisać jedną lub więcej kategorii, na przykład *Aplikacje dla programistów* lub *Aplikacje komunikacji*.

Po dodaniu aplikacji do usługi Intune istnieje możliwość wybrania dowolnej kategorii. Tematy dotyczące określonych platform zawierają informacje o dodawaniu aplikacji i przypisywaniu kategorii. Do tworzenia i edytowania własnych kategorii użyj następującej procedury:

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Aplikacje mobilne**.
4. W okienku obciążeń **Aplikacje mobilne** w obszarze **Instalacja** wybierz pozycję **Kategorie aplikacji**.  
    W okienku **Kategorie aplikacji** zostanie wyświetlona lista bieżących kategorii. 
5. Wykonaj jedną z następujących czynności:
    - Aby dodać kategorię, w okienku **Utwórz kategorię** wybierz pozycję **Dodaj**, a następnie wprowadź nazwę kategorii.  
    Nazwy można wprowadzić tylko w jednym języku i nie są one tłumaczone przez usługę Intune.
    - Aby edytować kategorię, wybierz wielokropek (**...** ) obok kategorii, a następnie wybierz pozycję **Przypnij do pulpitu nawigacyjnego** lub **Usuń**.
6. Wybierz przycisk **Utwórz**.

## <a name="apps-that-are-added-automatically-by-intune"></a>Aplikacje dodawane automatycznie przez usługę Intune

Wcześniej usługa Intune zawierała kilka wbudowanych aplikacji, które można było szybko przypisać. Ze względu na opinie klientów dotyczące usługi Intune firma Microsoft usunęła tę listę i wbudowane aplikacje nie są już wyświetlane. Jeśli jednak przypisano już jakiekolwiek wbudowane aplikacje, będą one nadal widoczne na liście aplikacji. W razie potrzeby można dalej przypisywać aplikacje.

> [!NOTE]
> Do zainstalowania wymaganej aplikacji innej niż biznesowa usługa Intune podejmie próbę zainstalowania aplikacji przez wysłanie polecenia instalacji za każdym razem, gdy urządzenie zostanie zaewidencjonowane, zakładając, że aplikacja nie została wykryta, a stan instalacji jest inny niż *Oczekująca instalacja*.

## <a name="installing-updating-or-removing-required-apps"></a>Instalowanie, aktualizowanie lub usuwanie wymaganych aplikacji

Usługa Intune automatycznie zainstaluje ponownie, zaktualizuje lub usunie wymaganą aplikację w ciągu 24 godzin, nie czekając na zakończenie 7-dniowego cyklu ponownej oceny.

Usługa Intune automatycznie zainstaluje ponownie, zaktualizuje lub usunie wymaganą aplikację w następujących sytuacjach:
- Jeśli użytkownik końcowy odinstaluje aplikację, której zainstalowanie na urządzeniu użytkownika końcowego jest wymagane, usługa Intune automatycznie zainstaluje ponownie aplikację po upływie tego terminu.
- Jeśli instalacja wymaganej aplikacji nie powiedzie się lub aplikacja nie będzie znajdować się na urządzeniu z innego powodu, usługa Intune oceni zgodność i ponownie zainstaluje aplikację po upływie tego terminu.  
- Administrator określa aplikację jako dostępną dla grupy użytkowników, a następnie użytkownik końcowy instaluje aplikację z poziomu Portalu firmy na urządzeniu. Później administrator aktualizuje aplikację z wersji 1 do wersji 2. Usługa Intune zaktualizuje tę aplikację po upływie tego terminu, o ile na urządzeniu nadal znajduje się dowolna wcześniejsza wersja tej aplikacji.
- Jeśli administrator wdroży opcję odinstalowania, a odinstalowanie aplikacji znajdującej się na urządzeniu zakończy się niepowodzeniem, usługa Intune oceni zgodność i odinstaluje aplikację po upływie tego terminu.   

## <a name="next-steps"></a>Następne kroki

Aby dowiedzieć się, jak dodawać aplikacje dla poszczególnych platform do usługi Intune, zobacz:

- [Aplikacje ze sklepu dla systemu Android](store-apps-android.md)
- [Aplikacje LOB dla systemu Android](lob-apps-android.md)
- [Aplikacje ze sklepu dla systemu iOS](store-apps-ios.md)
- [Aplikacje LOB dla systemu iOS](lob-apps-ios.md)
- [Aplikacje internetowe (dla wszystkich platform)](web-app.md)
- [Aplikacje ze sklepu dla systemu Windows Phone 8.1](store-apps-windows-phone-8-1.md)
- [Aplikacje LOB dla systemu Windows Phone](lob-apps-windows-phone.md)
- [Aplikacje ze sklepu Microsoft Store](store-apps-windows.md)
- [Aplikacja LOB dla systemu Windows](lob-apps-windows.md)
- [Aplikacje pakietu Office 365 dla systemu Windows 10](apps-add-office365.md)
- [Aplikacje pakietu Office 365 dla systemu macOS](apps-add-office365-macos.md)
- [Aplikacje wbudowane](apps-add-built-in.md)
