---
title: Zasady ochrony aplikacji — przegląd
titleSuffix: Microsoft Intune
description: Dowiedz się, w jaki sposób zasady ochrony aplikacji w usłudze Microsoft Intune wspomagają ochronę danych firmowych i zapobiegają utracie danych.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/06/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 1c086943-84a0-4d99-8295-490a2bc5be4b
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, get-started, seoapril2019
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3f1563c092d8dd4c34e4a18caea56910267eb623
ms.sourcegitcommit: de663ef5f3e82e0d983899082a7f5b62c63f24ef
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2020
ms.locfileid: "75956337"
---
# <a name="app-protection-policies-overview"></a>Zasady ochrony aplikacji — przegląd

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Zasady ochrony aplikacji (APP) to reguły, które zapewniają, że dane organizacji będą bezpiecznie przechowywane w aplikacji zarządzanej. Zasady mogą być regułą, która jest wymuszana w przypadku próby uzyskania dostępu do danych firmowych lub ich przeniesienia przez użytkownika albo zestawem akcji, które są zabronione lub monitorowane, gdy użytkownik korzysta z aplikacji. Zarządzana aplikacja to taka, dla której zastosowano zasady ochrony aplikacji i która może być zarządzana przez usługę Intune.

Zasady ochrony aplikacji w ramach zarządzania aplikacjami mobilnymi (MAM) umożliwiają zarządzanie danymi organizacji w aplikacji oraz ich ochronę. Funkcja **MAM bez rejestracji** (MAM-WE) umożliwia zarządzanie aplikacją służbową, która zawiera dane poufne, z prawie każdego [urządzenia](app-management.md#app-management-capabilities-by-platform) — w tym z urządzenia osobistego w scenariuszach **BYOD** (przynieś własne urządzenie). Zarządzanie aplikacjami mobilnymi usługi Intune można stosować do wielu aplikacji użytkowych, takich jak aplikacje pakietu Microsoft Office. Zobacz oficjalną listę [aplikacji chronionych przez usługę Microsoft Intune](apps-supported-intune-apps.md) dostępnych do użytku publicznego.

## <a name="how-you-can-protect-app-data"></a>Jak możesz chronić dane aplikacji
Pracownicy używają urządzeń przenośnych zarówno do celów służbowych, jak i prywatnych. Zatem umożliwiając pracownikom wydajną pracę, warto zapobiegać nieumyślnej lub umyślnej utracie danych. Należy również chronić dane firmowe, do których można uzyskać dostęp z urządzeń, które nie są zarządzane przez firmę.

Zasad ochrony aplikacji usługi Intune można użyć **niezależnie od wszelkich rozwiązań do zarządzania urządzeniami przenośnymi (MDM)** . Ta niezależność pomaga w ochronie danych firmy bez konieczności zarejestrowania urządzenia w rozwiązaniu do zarządzania urządzeniami. Wdrażając **zasady na poziomie aplikacji**, można ograniczyć dostęp do zasobów firmy i objęcia danych kontrolą działu IT.

### <a name="app-protection-policies-on-devices"></a>Zasady ochrony aplikacji na urządzeniach

Zasady ochrony aplikacji można skonfigurować dla aplikacji uruchamianych na urządzeniach, które są:

- **Zarejestrowane w usłudze Microsoft Intune:** te urządzenia są przeważnie urządzeniami należącymi do firmy.

- **Zarejestrowane w rozwiązaniu do zarządzania urządzeniami mobilnymi (MDM) innej firmy:** te urządzenia są przeważnie urządzeniami należącymi do firmy.

  > [!NOTE]
  > Zasady zarządzania aplikacjami mobilnymi nie powinny być stosowane z rozwiązaniami bezpiecznego kontenera ani rozwiązaniami do zarządzania aplikacjami mobilnymi innych firm.

- **Niezarejestrowane w żadnym rozwiązaniu do zarządzania urządzeniami mobilnymi:** Te urządzenia to zazwyczaj urządzenia należące do pracowników, które nie są zarządzane lub nie zostały zarejestrowane w usłudze Intune ani innych rozwiązaniach MDM.

> [!IMPORTANT]
> Możesz tworzyć zasady zarządzania aplikacjami mobilnymi dla aplikacji mobilnych pakietu Office łączących się z usługą Office 365. Możesz także chronić dostęp do lokalnych skrzynek pocztowych programu Exchange, tworząc zasady ochrony aplikacji usługi Intune dla aplikacji Outlook dla systemów iOS i Android, obsługiwane przez hybrydowe nowoczesne uwierzytelnianie. Przed użyciem tej funkcji upewnij się, że spełnione są [Wymagania dotyczące programu Outlook dla systemów iOS i Android](https://technet.microsoft.com/library/mt846639(v=exchg.160).aspx). Zasady ochrony aplikacji nie są obsługiwane w przypadku innych aplikacji łączących się z lokalnymi usługami Exchange lub SharePoint.

## <a name="benefits-of-using-app-protection-policies"></a>Zalety stosowania zasad ochrony aplikacji

Do istotnych korzyści zapewnianych przez zasady ochrony aplikacji należą:

- **Ochrona danych firmy na poziomie aplikacji.** Ponieważ zarządzanie aplikacjami mobilnymi nie wymaga zarządzania urządzeniami, dane firmowe można chronić zarówno na urządzeniach zarządzanych, jak i niezarządzanych. Zarządzanie skupia się na tożsamości użytkownika, co eliminuje konieczność zarządzania urządzeniem.

- **Zasady nie mają wpływu na produktywność użytkownika końcowego i nie są stosowane podczas korzystania z aplikacji w kontekście prywatnym.** Zasady są stosowane wyłącznie w kontekście służbowym, co daje możliwość ochrony danych firmowych bez ingerowania w dane prywatne.

- **Zasady ochrony aplikacji zapewniają stosowanie zabezpieczeń w warstwie aplikacji.** Możesz na przykład:
  - Wymagać numeru PIN w celu otwarcia aplikacji w kontekście służbowym 
  - Kontrolować udostępnianie danych między aplikacjami 
  - Uniemożliwić zapisywanie danych aplikacji firmowej w osobistej lokalizacji przechowywania

- **Rozwiązanie MDM, stosowane razem z rozwiązaniem MAM, zapewnia ochronę urządzenia**. Możesz na przykład zastosować zabezpieczenie dostępu do urządzenia numerem PIN lub wdrożyć na urządzeniu aplikacje zarządzane. Możesz również wdrażać aplikacje na urządzeniach za pośrednictwem rozwiązania MDM, aby mieć lepszą kontrolę nad zarządzaniem aplikacjami.

Dodatkowe korzyści można uzyskać, używając jednocześnie rozwiązań MDM i zasad ochrony aplikacji. Firmy mogą w tym samym czasie korzystać z zasad ochrony aplikacji łącznie z rozwiązaniem MDM lub bez niego. Przypuśćmy na przykład, że pracownik używa zarówno telefonu otrzymanego od firmy jak i własnego prywatnego tabletu. Telefon firmowy jest zarejestrowany w rozwiązaniu MDM i chroniony przez zasady ochrony aplikacji, natomiast urządzenie prywatne jest chronione tylko przez zasady ochrony aplikacji.

Jeśli zasady zarządzania aplikacjami mobilnymi są stosowane do użytkownika bez ustawiania stanu urządzenia, te zasady będą działać dla użytkownika zarówno w przypadku użycia własnych urządzeń (BYOD), jak i urządzeń zarządzanych przez usługę Intune. Można także zastosować zasady zarządzania aplikacjami mobilnymi w oparciu o stan zarządzany. W tym celu podczas tworzenia zasad ochrony aplikacji dla pozycji **Dotyczy wszystkich typów aplikacji** należy wybrać opcję **Nie**. Następnie należy wykonać jedną z następujących czynności:
- Zastosowanie mniej rygorystycznych zasad zarządzania aplikacjami mobilnymi do urządzeń zarządzanych przez usługę Intune oraz bardziej rygorystycznych zasad zarządzania aplikacjami mobilnymi do urządzeń niezarejestrowanych w usłudze MDM.
- Zastosowanie zasad zarządzania aplikacjami mobilnymi tylko do niezarejestrowanych urządzeń.

## <a name="supported-platforms-for-app-protection-policies"></a>Platformy obsługiwane przez zasady ochrony aplikacji

Usługa Intune oferuje szeroką gamę możliwości, które pomogą Ci uzyskać dostęp do potrzebnych aplikacji na urządzeniach, na których chcesz je uruchamiać. Aby uzyskać więcej informacji, zobacz [Możliwości zarządzania aplikacjami według platformy](app-management.md#app-management-capabilities-by-platform).

Obsługa platformy zasad ochrony aplikacji usługi Intune jest powiązana z obsługą platformy aplikacji mobilnych pakietu Office dla urządzeń z systemem Android i iOS. Aby uzyskać szczegółowe informacje, zobacz sekcję **Aplikacje mobilne** w temacie [Wymagania systemowe pakietu Office](https://products.office.com/office-system-requirements#coreui-contentrichblock-9r05pwg).

> [!IMPORTANT]
> Urządzenie musi mieć zainstalowaną aplikację Intune — Portal firmy, aby otrzymywać zasady ochrony aplikacji w systemie Android. Aby uzyskać więcej informacji, zobacz [Wymagania dotyczące aplikacji z dostępem do aplikacji Intune — Portal firmy](../fundamentals/end-user-mam-apps-android.md#access-apps).

## <a name="how-app-protection-policies-protect-app-data"></a>W jaki sposób zasady ochrony aplikacji chronią dane aplikacji

### <a name="apps-without-app-protection-policies"></a>Aplikacje bez zasad ochrony aplikacji

W przypadku korzystania z aplikacji bez ograniczeń dane firmowe i prywatne mogą ulec wymieszaniu. Dane firmowe mogą więc trafić na przykład do magazynu osobistego albo do aplikacji pozostających poza Twoją kontrolą, co grozi utratą danych. Strzałki na poniższym rysunku oznaczają nieograniczone przenoszenie danych między aplikacjami zarówno firmowymi, jak i prywatnymi, oraz do lokalizacji magazynu.

![Obraz koncepcyjny przedstawiający przenoszenie danych między aplikacjami, dla których nie są wymuszane żadne zasady](./media/app-protection-policy/apps-without-protection-policies.png)

### <a name="data-protection-with-app-protection-policies-app"></a>Ochrona danych za pomocą zasad ochrony aplikacji (APP)

Zasady ochrony aplikacji pozwalają zapobiec zapisywaniu danych firmowych w magazynie lokalnym urządzenia (patrz poniższy obraz). Można również ograniczyć przenoszenie danych do innych aplikacji, które nie są chronione przez zasady ochrony aplikacji. Ustawienia zasad ochrony aplikacji obejmują:
- Zasady relokacji danych, takie jak **Zapisz kopie danych organizacji** i **Ogranicz wycinanie, kopiowanie i wklejanie**.
- Ustawienia zasad dostępu, takie jak **Wymagaj prostego numeru PIN w celu udzielenia dostępu** i **Blokuj uruchamianie aplikacji zarządzanych na urządzeniach ze zdjętymi zabezpieczeniami systemu lub odblokowanym dostępem do konta administratora**.

![Obraz koncepcyjny przedstawiający dane firmy chronione za pomocą zasad](./media/app-protection-policy/apps-with-protection-policies.png)

### <a name="data-protection-with-app-on-devices-managed-by-an-mdm-solution"></a>Ochrona danych za pomocą zasad ochrony aplikacji (APP) na urządzeniach zarządzanych przez rozwiązanie MDM

Poniższa ilustracja przedstawia warstwy ochrony zapewniane łącznie przez rozwiązanie MDM i zasady ochrony aplikacji.

![Obraz przedstawiający sposób działania zasad ochrony aplikacji na urządzeniach BYOD](./media/app-protection-policy/app-protection-policies-with-mdm.png)

Rozwiązanie MDM zwiększa wartość, zapewniając następujące korzyści:

- Rejestruje urządzenie
- Wdraża aplikacje na urządzeniu
- Na bieżąco zapewnia zgodność urządzenia i zarządza nim

Zasady ochrony aplikacji zwiększają wartość, zapewniając następujące korzyści:

- Wspomagają ochronę danych firmy przed wyciekiem do aplikacji i usług dla konsumentów
- Stosują ograniczenia, takie jak *zapisz jako*, *schowek*, *numer PIN*, do aplikacji klienckich
- W razie potrzeby wymazują dane firmowe z aplikacji, nie usuwając tych aplikacji z urządzenia

### <a name="data-protection-with-app-for-devices-without-enrollment"></a>Ochrona danych za pomocą zasad ochrony aplikacji dla urządzeń bez rejestracji

Poniższy rysunek przedstawia sposób działania zasad ochrony danych na poziomie aplikacji bez rozwiązania MDM.

![Obraz przedstawiający sposób działania zasad ochrony aplikacji na urządzeniach bez rejestracji (urządzeniach niezarządzanych)](./media/app-protection-policy/app-protection-policies-without-mdm.png)

W przypadku urządzeń BYOD niezarejestrowanych w rozwiązaniu MDM zasady ochrony aplikacji wspomagają ochronę danych firmowych na poziomie aplikacji.
Należy jednak wziąć pod uwagę następujące ograniczenia:

- Na urządzeniach nie można wdrażać aplikacji. Użytkownik końcowy musi uzyskać aplikacje ze sklepu.
- Na urządzeniach nie można dostarczać profili certyfikatów.
- Na tych urządzeniach nie można dostarczać ustawień firmowych sieci Wi-Fi i VPN.

## <a name="apps-you-can-manage-with-app-protection-policies"></a>Aplikacje, którymi można zarządzać za pomocą zasad ochrony aplikacji

Każdą aplikacją zintegrowaną z zestawem [Intune SDK](../developer/app-sdk.md) lub opakowaną za pomocą [Narzędzia opakowującego aplikacje usługi Intune](../developer/apps-prepare-mobile-application-management.md) można zarządzać przy użyciu zasad ochrony aplikacji usługi Intune. Zapoznaj się z oficjalną listą [aplikacji chronionych przez usługę Microsoft Intune](apps-supported-intune-apps.md), które zostały skompilowane przy użyciu tych narzędzi i są dostępne do użytku publicznego.

Zespół programistyczny zajmujący się zestawem Intune SDK aktywnie przeprowadza testy i zapewnia obsługę aplikacji z natywnych platform Android, iOS (Obj-C, Swift), Xamarin, Xamarin.Forms i Cordova. Niektórym klientom udało się zintegrować zestaw Intune SDK z innymi platformami (takimi jak React Native i NativeScript), ale nie udostępniamy deweloperom żadnych wskazówek ani wtyczek dotyczących nieobsługiwanych przez nas platform.

[Zestaw Intune SDK](../developer/app-sdk.md) korzysta z zaawansowanych funkcji nowoczesnego uwierzytelniania z [bibliotek uwierzytelniania usługi Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) (ADAL) dla własnej wersji zestawu SDK i wersji zestawu SDK innych firm. W efekcie biblioteka [Microsoft Authentication Library](https://docs.microsoft.com/azure/active-directory/develop/reference-v2-libraries) (MSAL) nie działa dobrze w przypadku wielu naszych podstawowych scenariuszy, takich jak uwierzytelnianie w usłudze Intune App Protection i uruchamianie warunkowe. Biorąc pod uwagę, że zgodnie z ogólnymi wytycznymi nasz zespół ds. tożsamości zaleca przejście na bibliotekę MSAL dla wszystkich aplikacji pakietu Microsoft Office, zestaw [Intune SDK](../developer/app-sdk.md) usługi Intune będzie musiał w końcu ją obsługiwać — obecnie nie ma jednak konkretnego planu.

## <a name="end-user-requirements-to-use-app-protection-policies"></a>Wymagania dla użytkowników końcowych dotyczące korzystania z zasad ochrony aplikacji

Poniższa lista zawiera podstawowe wymagania dla użytkowników końcowych dotyczące użycia zasad ochrony aplikacji w aplikacji zarządzanej przez usługę Intune:

- Użytkownik końcowy musi mieć konto usługi Azure Active Directory (AAD). Zobacz temat [Dodawanie użytkowników i przyznawanie uprawnień administracyjnych do usługi Intune](../fundamentals/users-add.md), aby dowiedzieć się, jak utworzyć użytkowników usługi Intune w usłudze Azure Active Directory.

- Użytkownik końcowy musi mieć licencję usługi Microsoft Intune przypisaną do swojego konta usługi Azure Active Directory. Zobacz temat [Zarządzanie licencjami usługi Intune](../fundamentals/licenses-assign.md), aby dowiedzieć się, jak przypisać licencje usługi Intune użytkownikom końcowym.

- Użytkownik końcowy musi należeć do grupy zabezpieczeń objętej zasadami ochrony aplikacji. Te same zasady ochrony aplikacji muszą obejmować określoną używaną aplikację. Zasady ochrony aplikacji można tworzyć i wdrażać w konsoli usługi Intune w [portalu Azure](https://portal.azure.com). Grupy zabezpieczeń można obecnie tworzyć w [centrum administracyjnym platformy Microsoft 365](https://admin.microsoft.com).

- Użytkownik końcowy musi zalogować się do aplikacji przy użyciu konta usługi AAD.

## <a name="app-protection-policies-for-microsoft-office-apps"></a>Zasady ochrony aplikacji dla aplikacji pakietu Microsoft Office

Istnieje kilka dodatkowych wymagań, które należy uwzględnić podczas używania zasad ochrony aplikacji z aplikacjami pakietu Microsoft Office.

### <a name="outlook-mobile-app"></a>Aplikacja mobilna Outlook
Dodatkowe wymagania dotyczące użycia [aplikacji mobilnej Outlook](https://products.office.com/outlook) są następujące:

- Użytkownik końcowy musi mieć na urządzeniu aplikację mobilną Outlook.
- Użytkownik końcowy musi mieć skrzynkę pocztową usługi [Office 365 Exchange Online](https://products.office.com/exchange/exchange-online) oraz licencję powiązaną z kontem usługi Azure Active Directory.

  >[!NOTE]
  > Aplikacja mobilna Outlook aktualnie obsługuje tylko usługę Intune App Protection dla usługi Microsoft Exchange Online oraz [program Exchange Server z nowoczesnym uwierzytelnianiem hybrydowym](https://technet.microsoft.com/library/mt846639(v=exchg.160).aspx), a nie obsługuje programu Exchange w ramach usługi Office 365 Dedicated.

### <a name="word-excel-and-powerpoint"></a>Word, Excel i PowerPoint
Dodatkowe wymagania dotyczące korzystania z aplikacji [Word, Excel i PowerPoint](https://products.office.com/business/office) są następujące:

- Użytkownik końcowy musi mieć licencję usługi [Office 365 Business lub Enterprise](https://products.office.com/business/compare-more-office-365-for-business-plans) przypisaną do swojego konta usługi Azure Active Directory. Subskrypcja musi obejmować aplikacje pakietu Office na urządzeniach przenośnych i może uwzględniać konto magazynu w chmurze w ramach usługi [OneDrive dla Firm](https://onedrive.live.com/about/business/). Licencje usługi Office 365 można przypisać w [centrum administracyjnym platformy Microsoft 365](https://admin.microsoft.com), wykonując te [instrukcje](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).

- Użytkownik końcowy musi mieć zarządzaną lokalizację skonfigurowaną przy użyciu funkcji szczegółowego zapisywania jako — w ramach ustawienia „Zapisz kopie danych organizacji” w zasadach ochrony aplikacji. Przykładowo — jeśli zarządzana lokalizacja to OneDrive, aplikację [OneDrive](https://onedrive.live.com/about/) należy skonfigurować w aplikacji Word, Excel lub PowerPoint użytkownika końcowego.

- Jeśli zarządzana lokalizacja to OneDrive, aplikacja musi być objęta zasadami ochrony aplikacji wdrożonymi dla użytkownika końcowego.

  >[!NOTE]
  > Aplikacje mobilne pakietu Office obsługują obecnie tylko usługę SharePoint Online, a nie lokalny program SharePoint.

### <a name="managed-location-needed-for-office"></a>Lokalizacja zarządzana wymagana dla pakietu Office
Pakiet Office wymaga lokalizacji zarządzanej (np. usługi OneDrive). Usługa Intune oznacza wszystkie dane w aplikacji jako „firmowe” lub „osobiste”. Dane są uznawane za „firmowe”, jeśli pochodzą z lokalizacji firmowej. W przypadku aplikacji pakietu Office usługa Intune uznaje za lokalizacje firmowe: adres e-mail (Exchange) lub magazyn w chmurze (aplikacja OneDrive z kontem usługi OneDrive dla Firm).

### <a name="skype-for-business"></a>Skype dla firm
Istnieją dodatkowe wymagania dotyczące korzystania z aplikacji Skype dla firm. Zobacz wymagania licencyjne usługi [Skype dla firm](https://products.office.com/skype-for-business/it-pros). Dla konfiguracji hybrydowych i lokalnych usługi Skype dla firm zobacz odpowiednio artykuły [Hybrid Modern Auth for SfB and Exchange goes GA](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Hybrid-Modern-Auth-for-SfB-and-Exchange-goes-GA/ba-p/134756) (Nowoczesne uwierzytelnianie hybrydowe dla usługi Skype dla firm i programu Exchange jest ogólnie dostępne) lub [Modern Auth for SfB OnPrem with AAD](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Modern-Auth-for-SfB-OnPrem-with-AAD/ba-p/180910) (Nowoczesne uwierzytelnianie dla lokalnej usługi Skype dla firm za pomocą usługi AAD).

## <a name="app-protection-global-policy"></a>Zasady globalne ochrony aplikacji

Administrator usługi OneDrive może przejść do witryny **admin.office.com** i wybrać dostęp **Urządzenia**, aby skonfigurować mechanizmy kontroli **zarządzania aplikacjami mobilnymi** dla aplikacji klienckich usługi OneDrive i programu SharePoint. 

Te ustawienia dostępne w konsoli administratora usługi OneDrive pozwalają skonfigurować specjalne zasady ochrony aplikacji usługi Intune nazywane zasadami **globalnymi**. Te zasady globalne mają zastosowanie do wszystkich użytkowników w dzierżawie i nie umożliwiają sterowania kierowaniem zasad do odbiorców docelowych. 

Po ich włączeniu aplikacje usługi OneDrive i programu SharePoint dla systemów iOS i Android będą domyślnie chronione przy użyciu wybranych ustawień. Informatyk może edytować te zasady w konsoli usługi Intune, aby dodawać więcej aplikacji docelowych i modyfikować wszelkie ustawienia zasad. 

Domyślnie dla danej dzierżawy mogą istnieć tylko jedne zasady **globalne**. [Interfejsy API programu Graph usługi Intune](../developer/intune-graph-apis.md) umożliwiają tworzenie dodatkowych zasad globalnych dla poszczególnych dzierżaw, jednak nie jest to zalecane. Tworzenie dodatkowych zasad globalnych nie jest zalecane, ponieważ rozwiązywanie problemów z implementacją takich zasad może być bardzo złożone.

Chociaż zasady **globalne** mają zastosowanie do wszystkich użytkowników w dzierżawie, ustawienia te są zastępowane przez dowolne standardowe zasady ochrony aplikacji usługi Intune.

## <a name="app-protection-features"></a>Funkcje ochrony aplikacji

### <a name="multi-identity"></a>Wiele tożsamości

Obsługa wielu tożsamości umożliwia aplikacji obsługę wielu odbiorców. Ci odbiorcy mogą być użytkownikami „firmowymi” i „prywatnymi”. Konta służbowe są używane przez odbiorców „firmowych”, natomiast konta osobiste są używane przez konsumentów, takich jak użytkownicy pakietu Microsoft Office. Aplikacja obsługująca wiele tożsamości może zostać wydana publicznie, a zasady ochrony aplikacji są stosowane tylko wtedy, gdy aplikacja jest używana w kontekście służbowym („firmowym”). Obsługa wielu tożsamości korzysta z [zestawu Intune SDK](../developer/app-sdk.md) w celu przypisywania zasad ochrony aplikacji tylko do konta służbowego zarejestrowanego w aplikacji. Jeśli w aplikacji zostanie zarejestrowane konto osobiste , dane pozostaną bez zmian.

Przykładem kontekstu „prywatnego” będzie sytuacja, w której użytkownik uruchamia nowy dokument programu Word — ponieważ jest ona uznawana za kontekst prywatny, nie są stosowane zasady rozwiązania Intune App Protection. Gdy dokument zostanie zapisany na koncie „firmowym” w usłudze OneDrive, będzie to uznawane za kontekst „firmowy” i będą stosowane zasady rozwiązania Intune App Protection.

Przykładem kontekstu służbowego lub „firmowego” będzie sytuacja, w której użytkownik uruchamia aplikację OneDrive za pomocą konta służbowego. W kontekście służbowym nie może przenieść plików do osobistej lokalizacji przechowywania. Później, jeśli użytkownik korzysta z usługi OneDrive przy użyciu konta osobistego, może bez ograniczeń kopiować i przenosić dane z usługi OneDrive w wersji do użytku osobistego.

W programie Outlook jest dostępny połączony widok wiadomości e-mail, który zawiera „osobiste” i „firmowe” wiadomości e-mail. W takiej sytuacji aplikacja Outlook wyświetli monit o wprowadzenie numeru PIN usługi Intune podczas uruchamiania.

Aby uzyskać więcej informacji na temat obsługi wielu tożsamości w usłudze Intune, zobacz [Zarządzanie aplikacjami mobilnymi i obsługa wielu tożsamości](apps-supported-intune-apps.md).

### <a name="intune-app-pin"></a>Numer PIN aplikacji usługi Intune

Osobisty numer identyfikacyjny (PIN) jest kodem dostępu służącym do weryfikacji, czy właściwy użytkownik uzyskuje dostęp do danych organizacji w aplikacji.

**Monit o wprowadzenie numeru PIN**<br>
Monit o podanie numeru PIN aplikacji użytkownika jest wyświetlany w usłudze Intune tylko wtedy, gdy użytkownik chce uzyskać dostęp do danych „firmowych”. W aplikacjach z obsługą wielu tożsamości, np. Word, Excel lub PowerPoint, monit o wprowadzenie numeru PIN jest wyświetlany, gdy użytkownik próbuje otworzyć dokument lub plik „firmowy”. W aplikacjach z obsługą jednej tożsamości, np. aplikacjach biznesowych zarządzanych przy użyciu [Narzędzia opakowującego aplikacje dostępnego w usłudze Intune](../developer/apps-prepare-mobile-application-management.md), monit o podanie numeru PIN wyświetla się podczas uruchamiania, ponieważ [zestaw Intune SDK](../developer/app-sdk.md) wie, że środowisko użytkownika w aplikacji jest zawsze „firmowe”.

**Częstotliwość monitowania o numer PIN lub poświadczenia firmowe**<br>
Administrator IT może zdefiniować ustawienie zasad ochrony aplikacji usługi Intune **Ponownie sprawdź wymagania dostępu po (w minutach)** w konsoli administracyjnej usługi Intune. To ustawienie określa czas, po którym na urządzeniu są sprawdzane wymagania dotyczące dostępu i ponownie jest wyświetlany ekran numeru PIN lub monit poświadczeń firmowych aplikacji. Jednak wpływ na częstotliwość monitowania użytkownika mają następujące ważne informacje o numerze PIN:

- **Numer PIN jest udostępniany w aplikacjach tego samego wydawcy w celu zwiększenia użyteczności:**<br> w systemie iOS numer PIN danej aplikacji jest udostępniany we wszystkich aplikacjach **tego samego wydawcy aplikacji**. Na przykład wszystkie aplikacje firmy Microsoft mają ten sam numer PIN. W systemie Android numer PIN danej aplikacji jest współużytkowany przez wszystkie aplikacje.
- **Zachowanie *Ponownie sprawdź wymagania dostępu po (w minutach)* po ponownym uruchomieniu urządzenia:**<br> Czasomierz śledzi liczbę minut nieaktywności, określając, kiedy należy ponownie wyświetlić monit numeru PIN lub poświadczeń firmowych aplikacji usługi Intune. W systemie iOS na czasomierz nie ma wpływu ponowne uruchomienie urządzenia. W związku z tym ponowne uruchomienie urządzenia nie ma wpływu na liczbę minut, przez które użytkownik jest nieaktywny w aplikacji systemu iOS objętej zasadami numeru PIN (lub poświadczeń firmowych) usługi Intune. W systemie Android czasomierz jest resetowany przy ponownym uruchomieniu urządzenia. Dlatego aplikacje systemu Android z zasadami numeru PIN (lub poświadczeń firmowych) usługi Intune prawdopodobnie wyświetlą monit o numer PIN lub poświadczenia firmowe aplikacji **po ponownym uruchomieniu urządzenia** niezależnie od wartości ustawienia „Ponownie sprawdź wymagania dostępu po (w minutach)”.  
- **Ciągłe działanie czasomierza skojarzonego z numerem PIN:**<br> gdy numer PIN zostanie podany w celu uzyskania dostępu do aplikacji (aplikacji A) i aplikacja opuści pierwszy plan (utraci główny fokus wprowadzania) na urządzeniu, czasomierz zostanie zresetowany dla tego numeru PIN. Monit dla użytkownika o podanie numeru PIN nie będzie wyświetlany w żadnej aplikacji (aplikacji B), która współużytkuje ten numer PIN, ponieważ czasomierz został zresetowany. Monit pojawi się znowu po ponownym osiągnięciu odpowiedniej wartości ustawienia „Ponownie sprawdź wymagania dostępu po (w minutach)”.

W przypadku urządzeń z systemem iOS, nawet jeśli numer PIN jest współużytkowany pomiędzy aplikacjami od różnych dostawców, zostanie ponownie wyświetlony monit, jeśli ponownie osiągnięto wartość **Sprawdź ponownie wymagania dostępu po (minuty)** dla aplikacji, która nie jest głównym elementem fokusu wprowadzania danych. Przykładowo użytkownik ma aplikację _A_ od wydawcy _X_ oraz aplikację _B_ od wydawcy _Y_; obie aplikacje współdzielą ten sam numer PIN. Użytkownik skupia się na aplikacji _A_ (na pierwszym planie), a aplikacja _B_ jest zminimalizowana. Po osiągnięciu wartości **Sprawdź ponownie wymagania dostępu po (minuty)** i przełączeniu się przez użytkownika na aplikację _B_ będzie wymagany numer PIN.

  >[!NOTE]
  > Aby częściej sprawdzać wymagania dostępu użytkownika (tj. monit o podanie numeru PIN), szczególnie w przypadku często używanej aplikacji, zaleca się zmniejszenie wartości ustawienia „Ponownie sprawdź wymagania dostępu po (w minutach)”.

**Wbudowane numery PIN aplikacji Outlook i OneDrive**<br>
Numer PIN usługi Intune działa na podstawie czasomierza bazującego na braku aktywności, który znany jest również jako wartość **Ponownie sprawdź wymagania dostępu po (w minutach)** . W efekcie monity o numer PIN usługi Intune są wyświetlane niezależnie od monitów o numer PIN wbudowanej aplikacji dla programu Outlook i OneDrive, które często są domyślnie powiązane z uruchomieniem aplikacji. Jeśli użytkownik jednocześnie otrzymuje obydwa monity o numer PIN, oczekiwane zachowanie powinno określać, że numer PIN usługi Intune ma pierwszeństwo.

**Zabezpieczanie numerem PIN usługi Intune**<br>
Dzięki numerowi PIN tylko właściwy użytkownik uzyskuje dostęp do danych organizacji w aplikacji. W związku z tym przed ustawieniem lub zresetowaniem numeru PIN aplikacji usługi Intune użytkownik końcowy musi zalogować się przy użyciu swojego konta służbowego lub szkolnego. To uwierzytelnianie jest obsługiwane przez usługę Azure Active Directory za pośrednictwem zabezpieczonej wymiany tokenów i nie jest transparentne dla [zestawu Intune SDK](../developer/app-sdk.md). Z punktu widzenia zabezpieczeń najlepszym sposobem na ochronę danych służbowych jest ich zaszyfrowanie. Szyfrowanie nie jest powiązane z numerem PIN aplikacji, ale stanowi jej zasady ochrony aplikacji.

**Ochrona przed atakami siłowymi i numer PIN usługi Intune**<br>
W ramach zasad numeru PIN aplikacji administrator IT może ustawić maksymalną liczbę prób uwierzytelniania numeru PIN przez użytkownika przed zablokowaniem aplikacji. Po wykonaniu pewnej liczby prób [zestaw Intune SDK](../developer/app-sdk.md) może wyczyścić dane „firmowe” z aplikacji.

**Numer PIN usługi Intune i selektywne czyszczenie danych**<br>
W systemie iOS informacje o numerze PIN na poziomie aplikacji są przechowywane w pęku kluczy udostępnionym w aplikacjach tego samego wydawcy, na przykład wszystkich aplikacjach firmy Microsoft. Informacje o tym numerze PIN są również powiązane z kontem użytkownika końcowego. Selektywne czyszczenie jednej aplikacji nie powinno mieć wpływu na inną aplikację. 

Na przykład numer PIN ustawiony dla programu Outlook dla zalogowanego użytkownika jest przechowywany w udostępnionym pęku kluczy. Gdy użytkownik zaloguje się do usługi OneDrive (również opublikowanej przez firmę Microsoft), zobaczy ten sam numer PIN co w programie Outlook, ponieważ używa tego samego udostępnionego pęku kluczy. Podczas wylogowywania się z programu Outlook lub czyszczenia danych użytkownika w programie Outlook zestaw Intune SDK nie czyści tego pęku kluczy, ponieważ usługa OneDrive może nadal korzystać z tego numeru PIN. Z tego powodu operacje czyszczenia selektywnego nie powodują wyczyszczenia udostępnionego pęku kluczy, w tym numeru PIN. Takie zachowanie nie zmienia się, nawet jeśli na urządzeniu istnieje tylko jedna aplikacja wydawcy. 

Ponieważ numer PIN jest współużytkowany przez aplikacje z tym samym wydawcą, jeśli operacja czyszczenia przejdzie do pojedynczej aplikacji, zestaw Intune SDK nie wie, czy na urządzeniu znajdują się inne aplikacje tego samego wydawcy. W związku z tym zestaw Intune SDK nie czyści numeru PIN, ponieważ może być on nadal używany dla innych aplikacji. Oczekuje się, że numer PIN aplikacji powinien zostać wyczyszczony, gdy ostatnia aplikacja danego wydawcy zostanie ostatecznie usunięta w ramach niektórych operacji czyszczących systemu operacyjnego.
 
Jeśli zauważysz, że numer PIN jest czyszczony na niektórych urządzeniach, prawdopodobnie występują następujące sytuacje: Ponieważ numer PIN jest powiązany z tożsamością, jeśli użytkownik zalogował się przy użyciu innego konta po wyczyszczeniu, zostanie wyświetlony monit o wprowadzenie nowego numeru PIN. Jeśli jednak zaloguje się on przy użyciu wcześniej istniejącego konta, do logowania można użyć numeru PIN przechowywanego już w pęku kluczy.

**Dlaczego konieczne jest dwukrotne ustawianie numeru PIN w aplikacjach tego samego wydawcy?**<br>
Zarządzanie aplikacjami mobilnymi (w systemie iOS) umożliwia obecnie korzystanie z numeru PIN na poziomie aplikacji ze znakami alfanumerycznymi i specjalnymi („kod dostępu”). Wymaga to udziału aplikacji (np.WXP, Outlook, Managed Browser, Yammer) w celu zintegrowania [zestawu Intune SDK dla systemu iOS](../developer/app-sdk-ios.md). Bez tego ustawienia kodu dostępu nie są prawidłowo wymuszane w aplikacjach docelowych. Ta funkcja została dołączona do zestawu SDK usługi Intune dla systemu iOS w wersji 7.1.12.

Aby zapewnić jej obsługę i zgodność z poprzednimi wersjami zestawu SDK usługi Intune dla systemu iOS, wszystkie kody PIN (numeryczne lub kody dostępu) w wersji 7.1.12 oraz nowszych są obsługiwane niezależnie od numerycznego kodu PIN w poprzednich wersjach zestawu SDK. W związku z tym jeśli na urządzeniu znajdują się aplikacje z zestawem SDK usługi Intune dla systemu iOS w wersji wcześniejszej niż 7.1.12 oraz późniejszej niż 7.1.12 tego samego wydawcy, konieczne będzie skonfigurowanie dwóch kodów PIN. Oba kody PIN (po jednym dla każdej aplikacji) nie są ze sobą w żaden sposób powiązane, tj. muszą być zgodne z zasadami ochrony aplikacji, które mają do niej zastosowanie. W efekcie użytkownik może skonfigurować dwa razy ten sam kod PIN *tylko* w przypadku, gdy aplikacje A i B są objęte tymi samymi zasadami (w zakresie kodu PIN). 

Takie rozwiązanie jest charakterystyczne dla numeru PIN w aplikacjach systemu iOS, które są uruchamiane przy użyciu funkcji zarządzania aplikacjami mobilnymi usługi Intune. Z czasem, gdy aplikacje przyjmują nowsze wersje zestawu SDK usługi INTUNE dla systemu iOS, konieczność dwukrotnego ustawiania kodu PIN dla aplikacji tego samego wydawcy nie stanowi takiego problemu. Poniżej przedstawiono przykład.

  >[!NOTE]
  > Na przykład jeśli aplikacja A została utworzona przy użyciu wersji wcześniejszej niż 7.1.12, a aplikacja B tego samego wydawcy została utworzona za pomocą wersji 7.1.12 lub nowszej, użytkownik końcowy będzie musiał skonfigurować numery PIN oddzielnie dla aplikacji A i B, jeśli obie są zainstalowane na urządzeniu z systemem iOS.
  > Jeśli na urządzeniu jest zainstalowana aplikacja C, która zawiera zestaw SDK w wersji 7.1.9, będzie ona korzystać z tego samego kodu PIN, co aplikacja A. Aplikacja D skompilowana przy użyciu wersji 7.1.14 będzie mieć ten sam kod PIN, co aplikacja B.  
  > Jeśli na urządzeniu są zainstalowane tylko aplikacje A i C, trzeba ustawić jeden kod PIN. Ta sama zasada ma zastosowanie, jeśli na urządzeniu są zainstalowane tylko aplikacje B i D.

### <a name="app-data-encryption"></a>Szyfrowanie danych aplikacji
Administratorzy IT mogą wdrażać zasady ochrony aplikacji, które wymagają szyfrowania danych aplikacji. W ramach zasad administrator IT może również określić, kiedy zawartość będzie szyfrowana.

**Proces szyfrowania danych usługi Intune**<br> Zobacz tematy [Android app protection policy settings](app-protection-policy-settings-android.md) (Ustawienia zasad ochrony aplikacji systemu Android) i [iOS app protection policy settings](app-protection-policy-settings-ios.md) (Ustawienia zasad ochrony aplikacji systemu iOS), aby uzyskać szczegółowe informacje dotyczące ustawień zasad ochrony aplikacji dotyczących szyfrowania.

**Dane, które są szyfrowane**<br>
Szyfrowane są tylko dane oznaczone jako „firmowe” zgodnie z zasadami ochrony aplikacji administratora IT. Dane są uznawane za „firmowe”, jeśli pochodzą z lokalizacji firmowej. W przypadku aplikacji pakietu Office usługa Intune traktuje następujące lokalizacje jako biznesowe:

- Poczta e-mail (Exchange) 
- Magazyn w chmurze (aplikacja OneDrive z kontem usługi OneDrive dla firm)

W przypadku aplikacji biznesowych zarządzanych przy użyciu [Narzędzia opakowującego aplikacje dostępnego w usłudze Intune](../developer/apps-prepare-mobile-application-management.md) wszystkie dane aplikacji uznaje się za „firmowe”.

### <a name="selective-wipe"></a>Selektywne czyszczenie danych

**Zdalne czyszczenie danych**<br>
Usługa Intune umożliwia czyszczenie danych aplikacji na trzy różne sposoby: 
- Pełne czyszczenie urządzenia
- Selektywne czyszczenie na potrzeby zarządzania urządzeniami mobilnymi 
- Selektywne czyszczenie danych na potrzeby zarządzania aplikacjami mobilnymi

Aby uzyskać więcej informacji o zdalnym czyszczeniu w usłudze MDM, zobacz [Usuwanie urządzeń za pomocą czyszczenia lub wycofywania](../remote-actions/devices-wipe.md). Aby dowiedzieć się więcej o czyszczeniu selektywnym za pomocą usługi MAM, zobacz sekcję [Akcja Wycofaj](../remote-actions/devices-wipe.md#retire) i temat [Jak czyścić z aplikacji tylko dane firmowe](apps-selective-wipe.md).

[Pełne czyszczenie urządzenia](../remote-actions/devices-wipe.md) usuwa wszystkie dane użytkownika i ustawienia z **urządzenia** przez przywrócenie jego domyślnych ustawień fabrycznych. Urządzenie jest usuwane z usługi Intune.

  >[!NOTE]
  > Pełne czyszczenie urządzenia oraz czyszczenie selektywne w oprogramowaniu MDM może odbyć się tylko na urządzeniach zarejestrowanych w usłudze zarządzania urządzeniami przenośnymi (MDM) usługi Intune.

**Selektywne czyszczenie na potrzeby zarządzania urządzeniami mobilnymi**<br>
Aby przeczytać o usuwaniu danych firmowych, zobacz temat [Usuwanie urządzeń — wycofywanie](../remote-actions/devices-wipe.md#retire).

**Selektywne czyszczenie na potrzeby zarządzania aplikacjami mobilnymi**<br>
Selektywne czyszczenie pod kątem zarządzania aplikacjami mobilnymi po prostu usuwa dane aplikacji firmowych z aplikacji. Żądanie jest inicjowane z użyciem usługi Intune w ramach witryny Azure Portal. Aby dowiedzieć się, jak zainicjować żądanie czyszczenia, zobacz temat [Jak czyścić z aplikacji usługi Intune tylko dane firmowe](apps-selective-wipe.md).

Jeśli użytkownik używa aplikacji po zainicjowaniu selektywnego czyszczenia danych, [zestaw Intune SDK](../developer/app-sdk.md) sprawdza co 30 minut, czy wysłano żądanie selektywnego czyszczenia danych w ramach usługi Intune MAM. Sprawdzenie takie odbywa się również, gdy użytkownik uruchamia aplikację po raz pierwszy i loguje się przy użyciu swojego konta służbowego lub szkolnego.

**Brak obsługi usług lokalnych w aplikacjach chronionych przy użyciu usługi Intune**<br>
Ochrona aplikacji usługi Intune zależy od zgodności tożsamości użytkownika między aplikacją i [zestawem Intune SDK](../developer/app-sdk.md). Można to zagwarantować tylko przez nowoczesne uwierzytelnianie. Istnieją scenariusze, w których aplikacje mogą działać w konfiguracji lokalnej, ale nie są one ani zgodne, ani gwarantowane.

**Bezpieczny sposób otwierania linków internetowych z aplikacji zarządzanych**<br>
Administrator IT może wdrożyć i ustawić zasady ochrony aplikacji dla [aplikacji Intune Managed Browser](app-configuration-managed-browser.md), przeglądarki sieci Web opracowanej przez Microsoft Intune, którą można łatwo zarządzać za pomocą usługi Intune. Administrator IT może wymagać, aby wszystkie linki internetowe w aplikacjach zarządzanych przez usługę Intune były otwierane przy użyciu aplikacji Managed Browser.

## <a name="app-protection-experience-for-ios-devices"></a>Środowisko ochrony aplikacji dla urządzeń z systemem iOS

### <a name="device-fingerprint-or-face-ids"></a>Identyfikacja przy użyciu odcisku palca lub funkcji Face ID na urządzeniach 
Zasady ochrony aplikacji w usłudze Intune umożliwiają ograniczenie dostępu do aplikacji tylko do użytkowników mających licencję usługi Intune. Jednym ze sposobów kontrolowania dostępu do aplikacji jest wymaganie korzystania z funkcji Touch ID lub Face ID firmy Apple na obsługiwanych urządzeniach. Usługa Intune implementuje zachowanie, w którym po jakiejkolwiek zmianie w bazie danych biometrycznych urządzenia usługa monituje użytkownika o podanie numeru PIN przy najbliższym osiągnięciu wartości limitu czasu bezczynności. Zmiany w danych biometrycznych obejmują dodawanie i usuwanie odcisku palca lub twarzy. Jeśli użytkownik usługi Intune nie ma ustawionego numer PIN, zostanie poprowadzony przez procedurę konfigurowania numeru PIN usługi Intune.
 
Intencją tego procesu jest zapewnienie utrzymywania bezpieczeństwa i ochrony danych organizacji na poziomie aplikacji. Ta funkcja jest dostępna tylko dla systemów iOS i wymaga udziału aplikacji, w których zintegrowany jest zestaw Intune SDK dla systemu iOS w wersji 9.0.1 lub nowszej. Integracja zestawu SDK jest konieczna, aby można było wymusić to zachowanie w aplikacjach docelowych. Ta integracja jest przeprowadzana w sposób ciągły i zależy od zespołów zajmujących się określonymi aplikacjami. Dotyczy to między innymi aplikacji WXP, Outlook, Managed Browser i Yammer.
  
### <a name="ios-share-extension"></a>Rozszerzenie udostępniania systemu iOS
Możesz otwierać dane służbowe w aplikacjach niezarządzanych przy użyciu rozszerzenia udostępniania systemu iOS nawet wtedy, gdy zasady transferu danych mają wartość **tylko aplikacje zarządzane** lub **brak aplikacji**. Zasady ochrony aplikacji usługi Intune nie mogą kontrolować rozszerzenia udostępniania systemu iOS bez zarządzania danym urządzeniem. W związku z tym usługa Intune _**szyfruje dane „firmowe” przed ich udostępnieniem poza aplikację**_ . Aby sprawdzić poprawność szyfrowania, spróbuj otworzyć plik „firmowy” poza zarządzaną aplikacją. Plik powinien być zaszyfrowany i jego otwarcie poza zarządzaną aplikacją nie powinno być możliwe.

### <a name="multiple-intune-app-protection-access-settings-for-same-set-of-apps-and-users"></a>Wiele ustawień dostępu ochrony aplikacji usługi Intune dla tego samego zestawu aplikacji i użytkowników
Zasady ochrony aplikacji usługi Intune dla dostępu będą stosowane w określonej kolejności na urządzeniach użytkowników końcowych, kiedy będą próbowali uzyskać dostęp do aplikacji docelowej ze swojego konta firmowego. Ogólnie rzecz biorąc, pierwszeństwo miałoby czyszczenie, następnie blokada, a następnie ostrzeżenie z możliwością odrzucenia. Na przykład jeśli ma zastosowanie do określonego użytkownika/aplikacji, ustawienie minimalnej wersji systemu operacyjnego iOS, które ostrzega użytkownika o konieczności uaktualnienia wersji systemu iOS, zostanie zastosowane po ustawieniu minimalnej wersji systemu operacyjnego iOS, które blokuje dostęp użytkownika. Dlatego w scenariuszu, w którym administrator IT skonfigurował minimalną wersję systemu operacyjnego iOS na 11.0.0.0 i minimalną wersję systemu operacyjnego iOS (tylko ostrzeżenie) na 11.1.0.0, a urządzenie próbujące uzyskać dostęp do aplikacji ma system operacyjny iOS 10, użytkownik końcowy zostałby zablokowany na podstawie bardziej restrykcyjnego ustawienia minimalnej wersji systemu operacyjnego iOS, które powoduje zablokowanie dostępu.

Podczas pracy z różnymi typami ustawień pierwszeństwo ma wymaganie dotyczące wersji zestawu Intune SDK, następnie wymaganie dotyczące wersji aplikacji, a potem wymaganie dotyczące wersji systemu operacyjnego iOS. Następnie sprawdzane są ostrzeżenia dla wszystkich typów ustawień w tej samej kolejności. Zaleca się, aby wymaganie dotyczące wersji zestawu Intune SDK było konfigurowane tylko na podstawie wskazówek od zespołu produktu usługi Intune dla podstawowych scenariuszy blokowania.

## <a name="app-protection-experience-for-android-devices"></a>Środowisko ochrony aplikacji dla urządzeń z systemem Android

### <a name="company-portal-app-and-intune-app-protection"></a>Aplikacja Portal firmy i ochrona aplikacji usługi Intune
Większość funkcji ochrony aplikacji jest wbudowanych w aplikacji Portal firmy. Rejestracja urządzeń _nie jest konieczna_, mimo że aplikacja Portal firmy jest zawsze wymagana. Aby korzystać z zarządzania aplikacjami mobilnymi bez rejestracji (MAM-WE), użytkownik końcowy musi mieć zainstalowaną aplikację Portal firmy na urządzeniu.

### <a name="multiple-intune-app-protection-access-settings-for-same-set-of-apps-and-users"></a>Wiele ustawień dostępu ochrony aplikacji usługi Intune dla tego samego zestawu aplikacji i użytkowników
Zasady ochrony aplikacji usługi Intune dla dostępu będą stosowane w określonej kolejności na urządzeniach użytkowników końcowych, kiedy będą próbowali uzyskać dostęp do aplikacji docelowej ze swojego konta firmowego. Ogólnie rzecz biorąc, pierwszeństwo ma blokada, następnie ostrzeżenie z możliwością odrzucenia. Na przykład jeśli ma zastosowanie do określonego użytkownika/aplikacji, ustawienie minimalnej wersji poprawki zabezpieczeń systemu Android, które ostrzega użytkownika o konieczności uaktualnienia poprawki, zostanie zastosowane po ustawieniu minimalnej wersji poprawki zabezpieczeń systemu Android, które blokuje dostęp użytkownika. Dlatego w scenariuszu, w którym administrator IT skonfigurował minimalną wersję poprawki zabezpieczeń systemu Android na 2018-03-01 i minimalną wersję poprawki zabezpieczeń systemu Android (tylko ostrzeżenie) na 2018-02-01, a urządzenie próbujące uzyskać dostęp do aplikacji ma wersję poprawki 2018-01-01, użytkownik końcowy zostałby zablokowany na podstawie bardziej restrykcyjnego ustawienia minimalnej wersji poprawki systemu Android, które powoduje zablokowanie dostępu. 

Podczas pracy z różnymi typami ustawień pierwszeństwo ma wymaganie dotyczące wersji aplikacji, a następnie wymaganie dotyczące wersji systemu operacyjnego Android i wymaganie dotyczące wersji poprawki zabezpieczeń systemu Android. Następnie sprawdzane są ostrzeżenia dla wszystkich typów ustawień w tej samej kolejności.

### <a name="intune-app-protection-policies-and-googles-safetynet-attestation-for-android-devices"></a>Zasady ochrony aplikacji usługi Intune i zaświadczanie przy użyciu rozwiązania SafetyNet firmy Google dla urządzeń z systemem Android 
Dzięki zasadom ochrony aplikacji usługi Intune administratorzy mogą wymagać, aby urządzenia użytkowników końcowych przechodziły pomyślnie testy zaświadczeń rozwiązania SafetyNet firmy Google dla urządzeń z systemem Android. Nowe określenia usługi Google Play będą zgłaszane do administratora IT w odstępach czasu określonych przez usługę Intune. Częstotliwość wywołań usługi jest ograniczana ze względu na obciążenie, dlatego ta wartość jest przechowywana wewnętrznie i nie można jej konfigurować. Wszelkie akcje skonfigurowane przez administratora IT względem ustawienia zaświadczeń rozwiązania SafetyNet firmy Google będą podejmowane na podstawie ostatniego wyniku zgłoszonego do usługi Intune w czasie warunkowego uruchamiania. W przypadku braku danych dostęp będzie udzielany w zależności od tego, czy zakończyły się niepowodzeniem jakieś inne sprawdzania uruchomienia warunkowego. „Komunikacja dwukierunkowa” usługi Google Play mająca na celu określenie wyników zaświadczania rozpocznie się na zapleczu i będzie monitować użytkownika asynchronicznie, jeśli urządzenie ulegnie awarii. Jeśli dane są przestarzałe, dostęp zostanie zablokowany lub udzielony w zależności od ostatniego zgłoszonego wyniku. Podobnie jak w poprzednim przypadku „komunikacja dwukierunkowa” usługi Google Play mająca na celu określenie wyników zaświadczania rozpocznie się i będzie monitować użytkownika asynchronicznie, jeśli urządzenie ulegnie awarii.

### <a name="intune-app-protection-policies-and-googles-verify-apps-api-for-android-devices"></a>Zasady ochrony aplikacji usługi Intune i interfejs API weryfikowania aplikacji firmy Google dla urządzeń z systemem Android
Dzięki zasadom ochrony aplikacji usługi Intune administratorzy mogą wymagać, aby urządzenia użytkowników końcowych wysyłały sygnały za pomocą interfejsu API Verify Apps firmy Google dla urządzeń z systemem Android. Instrukcje wykonania tego zadania różnią się nieznacznie między urządzeniami. Ogólnie należy przejść do sklepu Google Play i kliknąć pozycję **Moje gry i aplikacje**. Następnie kliknięcie wyniku ostatniego skanowania aplikacji spowoduje wyświetlenie menu Play Protect. Upewnij się, że włączono przełącznik **Skanuj urządzenie pod kątem zagrożeń**.

### <a name="googles-safetynet-attestation-api"></a>Interfejs API zaświadczania rozwiązania SafetyNet firmy Google 
Usługa Intune wykorzystuje interfejsy API SafetyNet usługi Google Play Protect do dodania sprawdzeń dotyczących wykrywania rootingu dla urządzeń niezarejestrowanych. Firma Google opracowała ten zestaw interfejsów API dla aplikacji systemu Android i obsługuje go w celu stwierdzenia, czy aplikacje nie są uruchamiane na urządzeniach z odblokowanym dostępem. Ten zestaw został na przykład wprowadzony w aplikacji Android Pay. Ponieważ firma Google nie udostępnia publicznie wszystkich informacji dotyczących procesów zachodzących podczas wykrywania rootingu, oczekujemy, że te interfejsy API wykrywają użytkowników, którzy odblokowali dostęp do konta root na swoich urządzeniach. Dostęp tych użytkowników można następnie zablokować lub wyczyścić ich konta firmowe z aplikacji obsługujących zasady. Opcja **Sprawdź podstawową integralność** informuje o ogólnej integralności urządzenia. W przypadku urządzeń z odblokowanym dostępem do konta root, emulatorów, urządzeń wirtualnych i urządzeń z oznakami naruszenia podstawowa integralność kończy się niepowodzeniem. Opcja **Sprawdź podstawową integralność i certyfikowane urządzenia** informuje o zgodności urządzenia z usługami Google. Tylko sprawdzanie niemodyfikowanych urządzeń, które były certyfikowane przez firmę Google, może zakończyć się powodzeniem. Sprawdzanie zakończy się niepowodzeniem w przypadku następujących urządzeń:

- Urządzenia, w przypadku których test podstawowej integralności kończy się niepowodzeniem
- Urządzenia z odblokowanym programem rozruchowym
- Urządzenia z niestandardowym obrazem systemu/pamięcią ROM
- Urządzenia, w przypadku których producent nie zwrócił się do firmy Google o przeprowadzenie procesu certyfikacji, lub urządzenia, które takiej certyfikacji nie przeszły
- Urządzenia z obrazem systemu skompilowanym bezpośrednio na podstawie plików źródłowych programu Android Open Source
- Urządzenia z obrazem systemu w wersji beta lub deweloperskiej wersji zapoznawczej

Aby poznać szczegóły techniczne, zobacz [dokumentację firmy Google dotyczącą zaświadczania SafetyNet](https://developer.android.com/training/safetynet/attestation).

### <a name="safetynet-device-attestation-setting-and-the-jailbrokenrooted-devices-setting"></a>Ustawienia „Zaświadczanie urządzeń SafetyNet” i „Urządzenia ze złamanymi ograniczeniami lub z odblokowanym dostępem”
Sprawdzania wykonywane przez interfejs API SafetyNet usługi Google Play Protect wymagają, aby użytkownik końcowy był w trybie online co najmniej przez czas wykonywania „komunikacji dwukierunkowej” podczas określania wyników zaświadczania. Jeśli użytkownik końcowy jest w trybie offline, administrator IT może nadal oczekiwać, że wynik będzie egzekwowany dzięki ustawieniu **Urządzenia ze złamanymi ograniczeniami lub z odblokowanym dostępem**. Jak już wspomniano, jeśli użytkownik końcowy będzie zbyt długo w trybie offline, zacznie obowiązywać opcja **Okres karencji w trybie offline**. Po osiągnięciu wartości czasomierza zostanie zablokowany dostęp do wszystkich danych służbowych do czasu uzyskania dostępu do sieci. Włączenie obu tych ustawień umożliwia utrzymanie w dobrej kondycji urządzeń użytkowników w rozwiązaniu warstwowym, co jest szczególnie ważne, kiedy użytkownicy końcowi uzyskują dostęp do danych służbowych za pomocą urządzeń przenośnych.

### <a name="google-play-protect-apis-and-google-play-services"></a>Interfejsy API usługi Google Play Protect i usługi Google Play
Ustawienia zasad ochrony aplikacji korzystających z interfejsów API usługi Google Play Protect wymagają działających usług Google Play. Zarówno ustawienie **Zaświadczanie urządzeń SafetyNet**, jak i ustawienie **Skanowanie aplikacji pod kątem zagrożeń**, do poprawnego działania wymaga określonej przez firmę Google wersji usług Google Play. Ponieważ te ustawienia dotyczą zabezpieczeń, to po ich włączeniu użytkownik końcowy zostanie zablokowany, jeśli nie będzie miał odpowiedniej wersji usług Google Play lub nie będzie miał do nich dostępu.

## <a name="next-steps"></a>Następne kroki

[Sposoby tworzenia i wdrażania zasad ochrony aplikacji w usłudze Microsoft Intune](app-protection-policies.md)

[Dostępne ustawienia zasad ochrony aplikacji systemu Android przy użyciu usługi Microsoft Intune](app-protection-policy-settings-android.md)

[Dostępne ustawienia zasad ochrony aplikacji systemu iOS przy użyciu usługi Microsoft Intune](app-protection-policy-settings-ios.md)

## <a name="see-also"></a>Zobacz także
Aplikacje innych firm, takie jak aplikacja mobilna Salesforce, współpracują w określony sposób z usługą Intune, aby chronić dane firmowe. Aby dowiedzieć się więcej o tym, jak aplikacja Salesforce współpracuje w szczególności z usługą Intune (z uwzględnieniem ustawień konfiguracji aplikacji MDM), zobacz temat [(Aplikacja Salesforce i usługa Microsoft Intune](https://gallery.technet.microsoft.com/Salesforce-App-and-Intune-c47d44ee/file/188000/1/Salesforce%20App%20and%20Intune%20for%20external.pdf).
