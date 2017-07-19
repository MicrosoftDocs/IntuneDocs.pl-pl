---
title: "Dostęp warunkowy przy użyciu usługi Intune"
titleSuffix: Intune on Azure
description: "Typowe sposoby korzystania z dostępu warunkowego przy użyciu usługi Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a0b8e55e-c3d8-4599-be25-dc10c1027b62
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0ba1f12d762a6288fc2e7a3bfdae637f8ae13a94
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2017
---
# <a name="common-ways-to-use-conditional-access-with-intune"></a>Typowe sposoby korzystania z dostępu warunkowego przy użyciu usługi Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Aby umożliwić zachowanie zgodności z dostępem warunkowym w organizacji należy skonfigurować zasady zgodności urządzeń mobilnych w usłudze Intune oraz możliwości zarządzania aplikacjami mobilnymi usługi Intune (MAM). Poniżej omówiono typowe sposoby korzystania z dostępu warunkowego przy użyciu usługi Intune.

## <a name="device-based-conditional-access"></a>Dostęp warunkowy oparty na urządzeniach

Usługi Intune i Azure Active Directory działają razem w celu zapewnienia, że tylko zarządzane i zgodne urządzenia mają możliwość uzyskania dostępu do poczty e-mail, usług Office 365, aplikacji typu oprogramowanie jako usługa (SaaS) i [aplikacji lokalnych](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started). Ponadto w usłudze Azure Active Directory można ustawić zasady zezwalające na dostęp do usług Office 365 tylko komputerom dołączonym do domeny lub urządzeniom mobilnym zarejestrowanym w usłudze Intune.

Usługa Intune zapewnia możliwości zasad zgodności urządzenia, które służą do oceny stanu zgodności urządzeń. Stan zgodności jest zgłaszany do usługi Azure Active Directory w celu zastosowania do wymuszania zasad dostępu warunkowego utworzonych w usłudze Azure Active Directory, gdy użytkownik próbuje uzyskać dostęp do zasobów firmy.

Od wprowadzenia [nowego portalu Azure Portal](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune) zasady dostępu warunkowego opartego na urządzeniach dla usługi Exchange Online oraz pozostałych produktów usług Office 365 są konfigurowane za pośrednictwem portalu Azure Portal.

-   Dowiedz się więcej na temat [dostępu warunkowego w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).

-   Więcej informacji o tym, [czym jest zgodność urządzenia w usłudze Intune](device-compliance.md).

-   Dowiedz się więcej o [ochronie poczty e-mail, usług Office 365 oraz pozostałych usług przy użyciu dostępu warunkowego w usłudze Intune](https://docs.microsoft.com/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).

### <a name="conditional-access-for-exchange-on-premises"></a>Dostęp warunkowy do lokalnego programu Exchange

Funkcji dostępu warunkowego można użyć do zezwalania lub blokowania dostępu do **lokalnego programu Exchange** na podstawie zasad zgodności urządzenia i stanu rejestracji. Jeśli funkcja dostępu warunkowego jest stosowana w połączeniu z zasadami zgodności urządzenia, tylko zgodne urządzenia będą miały dostęp do lokalnego programu Exchange.

Można skonfigurować ustawienia zaawansowane dostępu warunkowego, aby uzyskać większą kontrolę, np.:

-   Zezwolić na dostęp z określonych platform lub je zablokować.

-   Natychmiast zablokować urządzenia, które nie są zarządzane przez usługę Intune.

Każde urządzenie używane do dostępu do lokalnego programu Exchange jest sprawdzane pod kątem zgodności, gdy stosowane są zasady zgodności urządzenia i dostępu warunkowego.

Jeśli urządzenia nie spełniają warunków, użytkownik jest przeprowadzany przez procedurę rejestracji urządzenia w celu rozwiązania problemu powodującego jego niezgodność.

#### <a name="how-conditional-access-for-exchange-on-premises-works"></a>Jak działa dostęp warunkowy do lokalnego programu Exchange

Program Intune Exchange Connector pobiera wszystkie rekordy Exchange Active Sync (EAS) znajdujące się na serwerze programu Exchange, by usługa Intune mogła pobrać te rekordy EAS i zamapować je na rekordy urządzeń usługi Intune. Rekordami tymi są urządzenia zarejestrowane w usłudze Intune i przez nią rozpoznane. Ten proces zezwala na dostęp do poczty e-mail lub go blokuje.

Jeśli rekord EAS jest całkowicie nowy i usługa Intune nie została o tym powiadomiona, usługa Intune uruchamia polecenie cmdlet, które blokuje dostęp do poczty e-mail. Poniżej przedstawiono bardziej szczegółowe informacje dotyczące tego procesu:

![Schemat blokowy lokalnego programu Exchange z urzędem certyfikacji](./media/ca-intune-common-ways-1.png)

1.  Użytkownik próbuje uzyskać dostęp do firmowej poczty e-mail, która jest hostowana w lokalnym programie Exchange 2010 SP1 lub w jego nowszej wersji.

2.  Jeśli urządzenie nie jest zarządzane przez usługę Intune, dostęp do poczty e-mail zostaje zablokowany. Usługa Intune wysyła powiadomienie o zablokowaniu do klienta EAS.

3.  Program EAS odbiera powiadomienie o zablokowaniu, przenosi urządzenie do kwarantanny i wysyła wiadomość e-mail informującą o kwarantannie z krokami korygującymi zawierającymi linki pozwalające użytkownikom zarejestrować urządzenia.

4.  Odbywa się proces dołączania w miejscu pracy, który stanowi pierwszy krok do zarządzania urządzeniem przy użyciu usługi Intune.

5.  Urządzenie zostaje zarejestrowane w usłudze Intune.

6.  Usługa Intune mapuje rekord EAS na rekord urządzenia i zapisuje stan zgodności urządzenia.

7.  Identyfikator klienta EAS zostaje zarejestrowany w procesie rejestracji urządzenia w usłudze Azure AD, który tworzy relację między rekordem urządzenia w usłudze Intune oraz identyfikatorem klienta EAS.

8.  Rejestracja urządzenia w usłudze Azure AD zapisuje informacje o stanie urządzenia.

9.  Jeśli użytkownik zachowuje zgodność z zasadami dostępu warunkowego, usługa Intune uruchamia polecenie cmdlet za pośrednictwem łącznika Intune Exchange Connector, co umożliwia synchronizację skrzynki pocztowej.

10. Serwer programu Exchange wysyła powiadomienie do klienta EAS, dzięki czemu użytkownik może uzyskać dostęp do poczty e-mail.

#### <a name="whats-the-intune-role"></a>Jaka jest rola usługi Intune?

Usługa Intune ocenia stan urządzenia oraz nim zarządza.

#### <a name="whats-the-exchange-server-role"></a>Jaka jest rola serwera programu Exchange?

Serwer programu Exchange zapewnia interfejs API oraz infrastrukturę, aby przenieść urządzenia do kwarantanny.

> [!IMPORTANT] 
> Należy pamiętać, że użytkownik używający urządzenia musi mieć przypisany do niego profil, aby urządzenie mogło zostać ocenione pod kątem zgodności. Jeśli na urządzeniu nie wdrożono żadnych zasad zgodności dla użytkownika, będzie ono traktowane jako zgodne i nie będą stosowane żadne ograniczenia dostępu.

### <a name="conditional-access-based-on-network-access-control"></a>Dostęp warunkowy w oparciu o kontrolę dostępu do sieci

Usługa Intune została zintegrowana z partnerami, takimi jak Cisco ISE, Aruba Clear Pass oraz Citrix NetScaler w celu zapewnienia kontroli dostępu na podstawie rejestracji w usłudze Intune oraz stanu zgodności urządzenia.

Gdy użytkownicy próbują uzyskać dostęp do firmowej sieci Wi-Fi lub zasobów VPN, zezwolenie na dostęp lub odmowa dostępu następuje w zależności od tego, czy urządzenie jest zarządzane przy użyciu zasad zgodności urządzeń w usłudze Intune oraz z nimi zgodne.

-   Dodatkowe informacje o [integracji kontroli dostępu do sieci z usługą Intune](network-access-control-integrate.md).

### <a name="conditional-access-based-on-device-risk"></a>Dostęp warunkowy w oparciu o ryzyko dotyczące urządzenia

Usługa Intune współpracuje z dostawcami usługi Mobile Threat Defense, która zapewnia rozwiązanie zabezpieczeń do wykrywania złośliwego oprogramowania, koni trojańskich oraz innych zagrożeń na urządzeniach mobilnych.

#### <a name="how-the-intune-and-mobile-threat-defense-integration-works"></a>Jak działa usługa Intune oraz integracja z usługą Mobile Threat Defense

Gdy na urządzeniu mobilnym zainstalowano agenta usługi Mobile Threat Defense, agent może wysyłać komunikaty o stanie zgodności do usługi Intune z powiadomieniem, czy wykryto zagrożenie bezpośrednio na urządzeniu mobilnym.

Usługa Intune oraz integracja z usługą Mobile Threat Defense stanowią czynnik decydujący w zakresie dostępu warunkowego w oparciu o ryzyko dotyczące urządzenia.

-   Dowiedz się więcej na temat usługi [Intune Mobile Threat Defense](https://docs.microsoft.com/intune-classic/deploy-use/mobile-threat-defense).

### <a name="conditional-access-for-windows-pcs"></a>Dostęp warunkowy dla komputerów z systemem Windows

Dostęp warunkowy dla komputerów zapewnia możliwości podobne do tych dostępnych dla urządzeń mobilnych. Poniżej omówiono sposoby korzystania z dostępu warunkowego podczas zarządzania komputerami przy użyciu usługi Intune.

#### <a name="corporate-owned"></a>Urządzenia należące do firmy

-   **Przyłączone do domeny w lokalnej usłudze AD:** była to najbardziej typowa i uzasadniona opcja wdrażania dostępu warunkowego dla organizacji, które zarządzały one już komputerami przy użyciu zasad grupy usługi AD i/lub programu System Center Configuration Manager.

-   **Przyłączone do domeny w usłudze Azure AD oraz zarządzane w usłudze Intune:** ten scenariusz jest zwykle dostosowany do modelu „Wybierz swoje własne urządzenie” (CYOD) i scenariusza wykorzystania laptopów, które są rzadko podłączane do sieci firmowej. Urządzenie łączy się z usługą Azure AD i zostaje zarejestrowane w usłudze Intune, która usuwa wszystkie zależności od lokalnej usługi AD oraz kontrolerów domeny. Może to pełnić rolę kryteriów dostępu warunkowego podczas uzyskiwania dostępu do zasobów firmowych.

-   **Przyłączone do domeny w usłudze AD oraz System Center Configuration Manager:** począwszy od bieżącej gałęzi, program System Center Configuration Manager zapewnia możliwości dostępu warunkowego, dzięki którym można ocenić określone kryteria zgodności oprócz kwestii przyłączenia komputera do domeny:

    -   Czy komputer jest szyfrowany?

    -   Czy ma zainstalowane złośliwe oprogramowanie? Czy oprogramowanie jest aktualne?

    -   Czy urządzenie ma złamane zabezpieczenia lub ma odblokowany dostęp do konta administratora?

#### <a name="bring-your-own-device-byod"></a>„Przynieś własne urządzenie” (BYOD)

-   **Dołączanie w miejscu pracy i zarządzanie usługą Intune:** użytkownik może dołączać własne urządzenia do dostępu do zasobów oraz usług firmowych. Można użyć dołączania w miejscu pracy oraz rejestrowania urządzeń w usłudze Intune w celu otrzymywania zasad na poziomie urządzenia, co stanowi również kolejną opcję oceny kryteriów dostępu warunkowego.

## <a name="app-based-conditional-access"></a>Dostęp warunkowy na podstawie aplikacji

Usługi Intune i Azure Active Directory współdziałają ze sobą, co pozwala zagwarantować, że tylko zarządzane aplikacje będą mogły uzyskać dostęp do firmowej poczty e-mail lub innych usług Office 365.

-   Dowiedz się więcej o [dostępie warunkowym na podstawie aplikacji przy użyciu usługi Intune](app-based-conditional-access-intune.md).

## <a name="next-steps"></a>Następne kroki

[Konfigurowanie dostępu warunkowego w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

[Instalowanie programu Intune On-premises Exchange Connector](https://docs.microsoft.com/intune/exchange-connector-install).

[Tworzenie zasad dostępu warunkowego do lokalnego programu Exchange](conditional-access-exchange-create.md)
