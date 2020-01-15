---
title: Scenariusze dostępu warunkowego
titleSuffix: Microsoft Intune
description: Dowiedz się, w jaki sposób dostęp warunkowy usługi Intune jest powszechnie używany w celu uzyskiwania dostępu warunkowego opartego na urządzeniach i dostępu warunkowego na podstawie aplikacji.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/23/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a0b8e55e-c3d8-4599-be25-dc10c1027b62
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 92e6aa1a66429c6407556444e903c158aff9dfa0
ms.sourcegitcommit: 2506cdbfccefd42587a76f14ee50c3849dad1708
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/11/2020
ms.locfileid: "75885997"
---
# <a name="what-are-common-ways-to-use-conditional-access-with-intune"></a>Jakie są typowe sposoby korzystania z dostępu warunkowego przy użyciu usługi Intune?

[!INCLUDE [azure_portal](../includes/azure_portal.md)]


Istnieją dwa typy dostępu warunkowego w usłudze Intune: dostęp warunkowy oparty na urządzeniu i dostęp warunkowy na podstawie aplikacji. Musisz skonfigurować powiązane zasady zgodności, aby sterować dostępem warunkowym w swojej organizacji. Dostęp warunkowy jest najczęściej używany do wykonywania takich czynności jak zezwalanie na dostęp lub blokowanie dostępu do programu Exchange, kontrola dostępu do sieci lub integracja z rozwiązaniem Mobile Threat Defense.
 
Informacje przedstawione w tym artykule pomagają zrozumieć sposób korzystania z możliwości zapewnienia zgodności *urządzenia* przenośnego w usłudze Intune i możliwości zarządzania *aplikacjami* mobilnymi (MAM) w usłudze Intune. 

> [!NOTE]
> Dostęp warunkowy jest funkcją usługi Azure Active Directory dostępną po uzyskaniu licencji na wersję Premium licencji tej usługi. Usługa Intune rozszerza tę funkcję, dodając do rozwiązania zgodność urządzeń przenośnych oraz zarządzanie aplikacjami mobilnymi. Węzeł Dostęp warunkowy dostępny z usługi *Intune* jest tym samym węzłem, do którego dostęp jest uzyskiwany z usługi *Azure AD*.  

## <a name="device-based-conditional-access"></a>Dostęp warunkowy oparty na urządzeniach

Usługi Intune i Azure Active Directory działają razem w celu zapewnienia, że tylko zarządzane i zgodne urządzenia mogą uzyskiwać dostęp do poczty e-mail, usług Office 365, aplikacji typu oprogramowanie jako usługa (SaaS) i [aplikacji lokalnych](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started). Ponadto w usłudze Azure Active Directory można ustawić zasady zezwalające na dostęp do usług Office 365 tylko komputerom dołączonym do domeny lub urządzeniom mobilnym zarejestrowanym w usłudze Intune.

Usługa Intune zapewnia możliwości zasad zgodności urządzenia, które służą do oceny stanu zgodności urządzeń. Stan zgodności jest zgłaszany do usługi Azure Active Directory w celu zastosowania do wymuszania zasad dostępu warunkowego utworzonych w usłudze Azure Active Directory, gdy użytkownik próbuje uzyskać dostęp do zasobów firmy.

Zasady dostępu warunkowego opartego na urządzeniach dla usługi Exchange Online oraz pozostałych produktów Office 365 są konfigurowane za pośrednictwem witryny [Azure Portal](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune).  

- Dowiedz się więcej na temat [wymagania urządzeń zarządzanych z dostępem warunkowym w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/require-managed-devices).

- Dowiedz się więcej o [zgodności urządzenia w usłudze Intune](device-compliance-get-started.md).

- Dowiedz się więcej na temat [obsługiwanych przeglądarek z dostępem warunkowym w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#supported-browsers).

> [!NOTE]
> Na urządzeniach z systemem Android w przypadku włączenia dostępu opartego na urządzeniach dla usługi SharePoint Online lub dostępu opartego na przeglądarce do usługi Exchange Online użytkownicy muszą włączyć opcję **Włącz dostęp za pomocą przeglądarki** na zarejestrowanym urządzeniu w następujący sposób:
> 1. Uruchomić **aplikację Portal firmy**.
> 2. Przejść do strony **Ustawienia** za pomocą przycisku wielokropka (...) lub przycisku menu sprzętu.
> 3. Nacisnąć przycisk **Włącz dostęp za pomocą przeglądarki**. 
> 4. W przeglądarce Chrome wylogować się z usługi Office 365 i ponownie uruchomić przeglądarkę Chrome.

### <a name="conditional-access-based-on-network-access-control"></a>Dostęp warunkowy w oparciu o kontrolę dostępu do sieci

Usługa Intune została zintegrowana z partnerami, takimi jak Cisco ISE, Aruba Clear Pass oraz Citrix NetScaler w celu zapewnienia kontroli dostępu na podstawie rejestracji w usłudze Intune oraz stanu zgodności urządzenia.

Zezwolenie użytkownikom na dostęp lub odmowa dostępu do firmowej sieci Wi-Fi lub zasobów VPN następuje w zależności od tego, czy urządzenie jest zarządzane przy użyciu zasad zgodności urządzeń w usłudze Intune oraz z nimi zgodne.

- Dodatkowe informacje o [integracji kontroli dostępu do sieci z usługą Intune](network-access-control-integrate.md).

### <a name="conditional-access-based-on-device-risk"></a>Dostęp warunkowy w oparciu o ryzyko dotyczące urządzenia

Usługa Intune współpracuje z dostawcami usługi Mobile Threat Defense, która zapewnia rozwiązanie zabezpieczeń do wykrywania złośliwego oprogramowania, koni trojańskich oraz innych zagrożeń na urządzeniach przenośnych.

#### <a name="how-the-intune-and-mobile-threat-defense-integration-works"></a>Jak działa usługa Intune oraz integracja z usługą Mobile Threat Defense

Gdy na urządzeniu mobilnym zainstalowano agenta usługi Mobile Threat Defense, wysyła on komunikaty o stanie zgodności do usługi Intune z powiadomieniem o wykryciu zagrożenia bezpośrednio na urządzeniu mobilnym.

Usługa Intune oraz integracja z usługą Mobile Threat Defense stanowią czynnik decydujący w zakresie dostępu warunkowego w oparciu o ryzyko dotyczące urządzenia.

- Dowiedz się więcej na temat usługi [Intune Mobile Threat Defense](mobile-threat-defense.md).

### <a name="conditional-access-for-windows-pcs"></a>Dostęp warunkowy dla komputerów z systemem Windows

Dostęp warunkowy dla komputerów zapewnia możliwości podobne do tych dostępnych dla urządzeń przenośnych. Poniżej omówiono sposoby korzystania z dostępu warunkowego podczas zarządzania komputerami przy użyciu usługi Intune.

#### <a name="corporate-owned"></a>Urządzenia należące do firmy

- **Przyłączone do domeny w lokalnej usłudze AD:** Ta opcja jest często używana przez organizacje zadowolone z tego, jak obecnie zarządzają komputerami przy użyciu zasad grupy usługi AD lub programu Configuration Manager.

- **Przyłączone do domeny w usłudze Azure AD oraz zarządzane w usłudze Intune:** Ten scenariusz jest przeznaczony dla organizacji, które chcą korzystać przede wszystkim z chmury (czyli przede wszystkim korzystają z usług w chmurze z myślą o ograniczeniu użycia infrastruktury lokalnej) lub tylko z chmury (w przypadku braku infrastruktury lokalnej). Usługa Azure AD Join działa dobrze w środowisku hybrydowym, umożliwiając dostęp do aplikacji i zasobów w chmurze oraz lokalnych. Urządzenie zostaje przyłączone do usługi Azure AD i zarejestrowane w usłudze Intune, co może zostać wykorzystane jako kryterium dostępu warunkowego w przypadku uzyskiwania dostępu do zasobów firmy.

#### <a name="bring-your-own-device-byod"></a>„Przynieś własne urządzenie” (BYOD)

- **Dołączanie w miejscu pracy i zarządzanie za pomocą usługi Intune:** Użytkownik może dołączać własne urządzenia do dostępu do firmowych zasobów i usług. Można użyć dołączania w miejscu pracy oraz rejestrowania urządzeń w funkcji zarządzania urządzeniami przenośnymi usługi Intune w celu otrzymywania zasad na poziomie urządzenia, co stanowi kolejną opcję oceny kryteriów dostępu warunkowego.

Dowiedz się więcej o [zarządzania urządzeniami w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/overview).

## <a name="app-based-conditional-access"></a>Dostęp warunkowy na podstawie aplikacji

Usługi Intune i Azure Active Directory współdziałają ze sobą, co pozwala zagwarantować, że tylko zarządzane aplikacje będą mogły uzyskać dostęp do firmowej poczty e-mail lub innych usług Office 365.

- Dowiedz się więcej o [dostępie warunkowym na podstawie aplikacji przy użyciu usługi Intune](app-based-conditional-access-intune.md).

### <a name="intune-conditional-access-for-exchange-on-premises"></a>Dostęp warunkowy usługi Intune do lokalnego programu Exchange

Funkcji dostępu warunkowego można użyć do zezwalania lub blokowania dostępu do **lokalnego programu Exchange** na podstawie zasad zgodności urządzenia i stanu rejestracji. Jeśli funkcja dostępu warunkowego jest stosowana w połączeniu z zasadami zgodności urządzenia, tylko zgodne urządzenia będą miały dostęp do lokalnego programu Exchange.

Można skonfigurować ustawienia zaawansowane dostępu warunkowego, aby uzyskać większą kontrolę, np.:

- Zezwolić na dostęp z określonych platform lub je zablokować.

- Natychmiast zablokować urządzenia niezarządzane przez usługę Intune.

Każde urządzenie używane do dostępu do lokalnego programu Exchange jest sprawdzane pod kątem zgodności, gdy stosowane są zasady zgodności urządzenia i dostępu warunkowego.

Jeśli urządzenia nie spełniają warunków, użytkownik jest przeprowadzany przez procedurę rejestracji urządzenia w celu rozwiązania problemu powodującego jego niezgodność.

#### <a name="how-conditional-access-for-exchange-on-premises-works"></a>Jak działa dostęp warunkowy do lokalnego programu Exchange

Dostęp warunkowy do lokalnego wystąpienia programu Exchange działa inaczej niż zasady oparte na dostępie warunkowym platformy Azure. Łącznik lokalnego wystąpienia programu Exchange w usłudze Intune jest instalowany w celu bezpośredniej współpracy z serwerem programu Exchange. Program Intune Exchange Connector pobiera wszystkie rekordy Exchange Active Sync (EAS) znajdujące się na serwerze programu Exchange, by usługa Intune mogła pobrać te rekordy EAS i zamapować je na rekordy urządzeń usługi Intune. Rekordami tymi są urządzenia zarejestrowane w usłudze Intune i przez nią rozpoznane. Ten proces zezwala na dostęp do poczty e-mail lub go blokuje.

Jeśli rekord EAS jest nowy i usługa Intune nie została o tym powiadomiona, uruchamia ona polecenie cmdlet (wymowa: „command-let”), które nakazuje serwerowi programu Exchange blokowanie dostępu do poczty e-mail. Poniżej przedstawiono bardziej szczegółowe informacje dotyczące tego procesu:

![Schemat blokowy lokalnego programu Exchange z urzędem certyfikacji](./media/conditional-access-intune-common-ways-use/ca-intune-common-ways-1.png)

1. Użytkownik próbuje uzyskać dostęp do firmowej poczty e-mail, która jest hostowana w lokalnym programie Exchange 2010 SP1 lub w jego nowszej wersji.

2. Jeśli urządzenie nie jest zarządzane przez usługę Intune, dostęp do poczty e-mail zostanie zablokowany. Usługa Intune wysyła powiadomienie o zablokowaniu do klienta EAS.

3. Program EAS odbiera powiadomienie o zablokowaniu, przenosi urządzenie do kwarantanny i wysyła wiadomość e-mail informującą o kwarantannie z krokami korygującymi zawierającymi linki pozwalające użytkownikom na zarejestrowanie urządzeń.

4. Odbywa się proces dołączania w miejscu pracy, który stanowi pierwszy krok do zarządzania urządzeniem przy użyciu usługi Intune.

5. Urządzenie zostaje zarejestrowane w usłudze Intune.

6. Usługa Intune mapuje rekord EAS na rekord urządzenia i zapisuje stan zgodności urządzenia.

7. Identyfikator klienta EAS zostaje zarejestrowany w procesie rejestracji urządzenia w usłudze Azure AD, który tworzy relację między rekordem urządzenia w usłudze Intune oraz identyfikatorem klienta EAS.

8. Rejestracja urządzenia w usłudze Azure AD zapisuje informacje o stanie urządzenia.

9. Jeśli użytkownik zachowuje zgodność z zasadami dostępu warunkowego, usługa Intune uruchamia polecenie cmdlet za pośrednictwem łącznika Intune Exchange Connector, co umożliwia synchronizację skrzynki pocztowej.

10. Serwer programu Exchange wysyła powiadomienie do klienta EAS, dzięki czemu użytkownik może uzyskać dostęp do poczty e-mail.


#### <a name="whats-the-intune-role"></a>Jaka jest rola usługi Intune?

Usługa Intune ocenia stan urządzenia oraz nim zarządza.

#### <a name="whats-the-exchange-server-role"></a>Jaka jest rola serwera programu Exchange?

Serwer programu Exchange zapewnia interfejs API oraz infrastrukturę, aby przenieść urządzenia do kwarantanny.

> [!IMPORTANT]
> Należy pamiętać, że użytkownik używający urządzenia musi mieć przypisany do niego profil zgodności i licencję usługi Intune, aby urządzenie mogło zostać ocenione pod kątem zgodności. Jeśli na urządzeniu nie wdrożono żadnych zasad zgodności dla użytkownika, będzie ono traktowane jako zgodne i nie będą stosowane żadne ograniczenia dostępu.

## <a name="next-steps"></a>Następne kroki

[Konfigurowanie dostępu warunkowego w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

[Konfigurowanie zasad dostępu warunkowego opartego na aplikacji](app-based-conditional-access-intune-create.md)

[Instalowanie programu Intune On-premises Exchange Connector](exchange-connector-install.md).

[Tworzenie zasad dostępu warunkowego do lokalnego programu Exchange](conditional-access-exchange-create.md)
