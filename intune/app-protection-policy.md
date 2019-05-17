---
title: Co to są zasady ochrony aplikacji
titleSuffix: Microsoft Intune
description: Dowiedz się, w jaki sposób zasady ochrony aplikacji w usłudze Microsoft Intune wspomagają ochronę danych firmowych i zapobiegają utracie danych.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/08/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 1c086943-84a0-4d99-8295-490a2bc5be4b
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, get-started, seoapril2019
ms.collection: M365-identity-device-management
ms.openlocfilehash: 45e9f50881ff7da0554a4731712441b5fedb01d8
ms.sourcegitcommit: 364a7dbc7eaa414c7a9c39cf53eb4250e1ad3151
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/09/2019
ms.locfileid: "59569418"
---
# <a name="what-are-app-protection-policies"></a>Co to są zasady ochrony aplikacji?


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Zasady ochrony aplikacji w usłudze Microsoft Intune wspomagają ochronę danych firmowych i zapobiegają utracie danych.

## <a name="how-you-can-protect-app-data"></a>Jak możesz chronić dane aplikacji
Pracownicy używają urządzeń przenośnych zarówno do celów służbowych, jak i prywatnych. Zatem umożliwiając pracownikom wydajną pracę, warto zapobiegać nieumyślnej lub umyślnej utracie danych. Należy również chronić dane firmowe, do których można uzyskać dostęp z urządzeń, które nie są zarządzane przez firmę.

Zasad ochrony aplikacji usługi Intune można użyć **niezależnie od wszelkich rozwiązań do zarządzania urządzeniami przenośnymi (MDM)**. Ta niezależność pomaga w ochronie danych firmy bez konieczności zarejestrowania urządzenia w rozwiązaniu do zarządzania urządzeniami. Wdrażając **zasady na poziomie aplikacji**, można ograniczyć dostęp do zasobów firmy i objęcia danych kontrolą działu IT.

Zasady ochrony aplikacji można skonfigurować dla aplikacji uruchamianych na urządzeniach, które są:

- **Zarejestrowane w usłudze Microsoft Intune:** te urządzenia są przeważnie urządzeniami należącymi do firmy.

- **Zarejestrowane w rozwiązaniu do zarządzania urządzeniami mobilnymi (MDM) innej firmy:** te urządzenia są przeważnie urządzeniami należącymi do firmy.

  > [!NOTE]
  > Zasady zarządzania aplikacjami mobilnymi nie powinny być stosowane z rozwiązaniami bezpiecznego kontenera ani rozwiązaniami do zarządzania aplikacjami mobilnymi innych firm.

- **Niezarejestrowane w żadnym rozwiązaniu do zarządzania urządzeniami mobilnymi:** te urządzenia są zazwyczaj należącymi do pracowników urządzeniami, które nie są zarządzane lub nie zostały zarejestrowane w usłudze Intune ani innych rozwiązaniach MDM.

> [!IMPORTANT]
> Możesz tworzyć zasady zarządzania aplikacjami mobilnymi dla aplikacji mobilnych pakietu Office łączących się z usługą Office 365. Możesz także chronić dostęp do lokalnych skrzynek pocztowych programu Exchange, tworząc zasady ochrony aplikacji usługi Intune dla aplikacji Outlook dla systemów iOS i Android, obsługiwane przez hybrydowe nowoczesne uwierzytelnianie. Przed użyciem tej funkcji upewnij się, że spełnione są [Wymagania dotyczące programu Outlook dla systemów iOS i Android](https://technet.microsoft.com/library/mt846639(v=exchg.160).aspx). Zasady ochrony aplikacji nie są obsługiwane w przypadku innych aplikacji łączących się z lokalnymi usługami Exchange lub SharePoint.

**Do istotnych korzyści zapewnianych przez zasady ochrony aplikacji należą**:

-   Ochrona danych firmy na poziomie aplikacji. Ponieważ zarządzanie aplikacjami mobilnymi nie wymaga zarządzania urządzeniami, dane firmowe można chronić zarówno na urządzeniach zarządzanych, jak i niezarządzanych. Zarządzanie skupia się na tożsamości użytkownika, co eliminuje konieczność zarządzania urządzeniem.

-   Zasady nie mają wpływu na produktywność użytkownika końcowego i nie są stosowane podczas korzystania z aplikacji w kontekście prywatnym. Zasady są stosowane wyłącznie w kontekście służbowym, co daje możliwość ochrony danych firmowych bez ingerowania w dane prywatne.

Dodatkowe korzyści można uzyskać, używając jednocześnie rozwiązań MDM i zasad ochrony aplikacji. Firmy mogą w tym samym czasie korzystać z zasad ochrony aplikacji łącznie z rozwiązaniem MDM lub bez niego. Przypuśćmy na przykład, że pracownik używa zarówno telefonu otrzymanego od firmy jak i własnego prywatnego tabletu. Telefon firmowy jest zarejestrowany w rozwiązaniu MDM i chroniony przez zasady ochrony aplikacji, natomiast urządzenie prywatne jest chronione tylko przez zasady ochrony aplikacji.

- **Rozwiązanie MDM zapewnia ochronę urządzenia**. Możesz na przykład zastosować zabezpieczenie dostępu do urządzenia numerem PIN lub wdrożyć na urządzeniu aplikacje zarządzane. Możesz również wdrażać aplikacje na urządzeniach za pośrednictwem rozwiązania MDM, aby mieć lepszą kontrolę nad zarządzaniem aplikacjami.

- **Zasady ochrony aplikacji zapewniają stosowanie zabezpieczeń warstwy aplikacji**. Możesz na przykład:
  - Wymagać numeru PIN w celu otwarcia aplikacji w kontekście służbowym 
  - Kontrolować udostępnianie danych między aplikacjami 
  - Uniemożliwić zapisywanie danych aplikacji firmowej w osobistej lokalizacji przechowywania


### <a name="supported-platforms-for-app-protection-policies"></a>Platformy obsługiwane przez zasady ochrony aplikacji
Obsługa platformy zasad ochrony aplikacji usługi Intune jest powiązana z obsługą platformy aplikacji mobilnych pakietu Office dla urządzeń z systemem Android i iOS. Aby uzyskać szczegółowe informacje, zobacz sekcję **Aplikacje mobilne** w temacie [Wymagania systemowe pakietu Office](https://products.office.com/office-system-requirements#coreui-contentrichblock-9r05pwg).

> [!IMPORTANT]
> Urządzenie musi mieć zainstalowaną aplikację Intune — Portal firmy, aby otrzymywać zasady ochrony aplikacji w systemie Android. Aby uzyskać więcej informacji, zobacz [Intune Company Portal access apps requirements](end-user-mam-apps-android.md#access-apps) (Wymagania dotyczące aplikacji z dostępem do aplikacji Intune — Portal firmy).

## <a name="how-app-protection-policies-protect-app-data"></a>W jaki sposób zasady ochrony aplikacji chronią dane aplikacji

#### <a name="apps-without-app-protection-policies"></a>Aplikacje bez zasad ochrony aplikacji

![Obraz koncepcyjny przedstawiający przenoszenie danych między aplikacjami, dla których nie są wymuszane żadne zasady](./media/apps-without-protection-policies.png)

W przypadku korzystania z aplikacji bez ograniczeń dane firmowe i prywatne mogą ulec wymieszaniu. Dane firmowe mogą więc trafić na przykład do magazynu osobistego albo do aplikacji pozostających poza Twoją kontrolą, co grozi utratą danych. Strzałki na poprzednim rysunku oznaczają nieograniczone przemieszczanie się danych między aplikacjami zarówno firmowymi, jak i prywatnymi oraz do lokalizacji magazynu.


### <a name="data-protection-with-app-protection-policies"></a>Ochrona danych za pomocą zasad ochrony aplikacji

![Obraz koncepcyjny przedstawiający dane firmy chronione za pomocą zasad](./media/apps-with-protection-policies.png)


Zasady ochrony aplikacji pozwalają zapobiec zapisywaniu danych firmowych w magazynie lokalnym urządzenia. Można również ograniczyć przenoszenie danych do innych aplikacji, które nie są chronione przez zasady ochrony aplikacji. Ustawienia zasad ochrony aplikacji obejmują:
- Zasady relokacji danych, takie jak **Nie zezwalaj na używanie polecenia Zapisz jako** i **Ogranicz wycinanie, kopiowanie i wklejanie**.
- Ustawienia zasad dostępu, takie jak **Wymagaj prostego numeru PIN w celu udzielenia dostępu** i **Blokuj uruchamianie aplikacji zarządzanych na urządzeniach ze zdjętymi zabezpieczeniami systemu lub odblokowanym dostępem do konta administratora**.

### <a name="data-protection-with-app-protection-policies-on-devices-managed-by-a-mobile-device-management-solution"></a>Ochrona danych za pomocą zasad ochrony aplikacji na urządzeniach zarządzanych przez rozwiązanie zarządzania urządzeniami mobilnymi

![Obraz przedstawiający sposób działania zasad ochrony aplikacji na urządzeniach BYOD](./media/app-protection-policies-with-mdm.png)

**W przypadku urządzeń zarejestrowanych w rozwiązaniu MDM**-

Powyższa ilustracja przedstawia warstwy ochrony zapewniane łącznie przez rozwiązanie MDM i zasady ochrony aplikacji.

Rozwiązanie MDM:

-   Rejestruje urządzenie

-   Wdraża aplikacje na urządzeniu

-   Na bieżąco zapewnia zgodność urządzenia i zarządza nim

**Zasady ochrony aplikacji zapewniają następujące korzyści:**

-   Chronią dane firmy przed wyciekiem do aplikacji i usług dla konsumentów

-   Stosują ograniczenia, takie jak *zapisz jako*, *schowek*, *numer PIN*, do aplikacji klienckich

-   Wymazują dane firmowe z aplikacji, nie usuwając tych aplikacji z urządzenia


### <a name="data-protection-with-app-protection-policies-for-devices-without-enrollment"></a>Ochrona danych za pomocą zasad ochrony aplikacji na urządzeniach bez rejestracji

![Obraz przedstawiający sposób działania zasad ochrony aplikacji na urządzeniach zarządzanych](./media/app-protection-policies-without-mdm.png)

Powyższy rysunek przedstawia sposób działania zasad ochrony danych na poziomie aplikacji bez rozwiązania MDM.

W przypadku urządzeń BYOD niezarejestrowanych w rozwiązaniu MDM zasady ochrony aplikacji wspomagają ochronę danych firmowych na poziomie aplikacji.
Należy jednak wziąć pod uwagę następujące ograniczenia:

-   Na urządzeniach nie można wdrażać aplikacji. Użytkownik końcowy musi uzyskać aplikacje ze sklepu.

-   Na urządzeniach nie można dostarczać profili certyfikatów.

-   Na tych urządzeniach nie można dostarczać ustawień firmowych sieci Wi-Fi i VPN.

## <a name="app-protection-global-policy"></a>Zasady globalne ochrony aplikacji

Administrator usługi OneDrive może przejść do witryny **admin.office.com** i wybrać dostęp **Urządzenia**, aby skonfigurować mechanizmy kontroli **zarządzania aplikacjami mobilnymi** dla aplikacji klienckich usługi OneDrive i programu SharePoint. 

Te ustawienia dostępne w konsoli administratora usługi OneDrive pozwalają skonfigurować specjalne zasady ochrony aplikacji usługi Intune nazywane zasadami **globalnymi**. Te zasady globalne mają zastosowanie do wszystkich użytkowników w dzierżawie i nie umożliwiają sterowania kierowaniem zasad do odbiorców docelowych. 

Po ich włączeniu aplikacje usługi OneDrive i programu SharePoint dla systemów iOS i Android będą domyślnie chronione przy użyciu wybranych ustawień. Informatyk może edytować te zasady w konsoli usługi Intune, aby dodawać więcej aplikacji docelowych i modyfikować wszelkie ustawienia zasad. 

Domyślnie dla danej dzierżawy mogą istnieć tylko jedne zasady **globalne**. [Interfejsy API programu Graph usługi Intune](intune-graph-apis.md) umożliwiają tworzenie dodatkowych zasad globalnych dla poszczególnych dzierżaw, jednak nie jest to zalecane. Tworzenie dodatkowych zasad globalnych nie jest zalecane, ponieważ rozwiązywanie problemów z implementacją takich zasad może być bardzo złożone.

Chociaż zasady **globalne** mają zastosowanie do wszystkich użytkowników w dzierżawie, ustawienia te są zastępowane przez dowolne standardowe zasady ochrony aplikacji usługi Intune.


## <a name="multi-identity"></a>Wiele tożsamości

Aplikacje, które obsługują wiele tożsamości, umożliwiają uzyskiwanie dostępu do tych samych aplikacji przy użyciu różnych kont (służbowych i osobistych), podczas gdy zasady ochrony aplikacji są stosowane tylko wtedy, gdy aplikacje są używane w kontekście służbowym.

Przykładem kontekstu prywatnego będzie sytuacja, w której użytkownik uruchamia nowy dokument programu Word. Ponieważ jest ona uznawana za kontekst prywatny, nie są stosowane zasady rozwiązania Intune App Protection. Gdy dokument zostanie zapisany na koncie firmowym w usłudze OneDrive, będzie uznawany za kontekst służbowy i zasady rozwiązania Intune App Protection będą stosowane.

Przykładem kontekstu służbowego będzie sytuacja, w której użytkownik uruchamia aplikację OneDrive za pomocą konta służbowego. W kontekście służbowym nie może przenieść plików do osobistej lokalizacji przechowywania. Później, jeśli użytkownik korzysta z usługi OneDrive przy użyciu konta osobistego, może bez ograniczeń kopiować i przenosić dane z usługi OneDrive w wersji do użytku osobistego.

- Dowiedz się więcej o aplikacjach, które obsługują [zarządzanie aplikacjami mobilnymi (MAM) i wiele tożsamości](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) za pomocą usługi Intune.

## <a name="next-steps"></a>Następne kroki

[Sposoby tworzenia i wdrażania zasad ochrony aplikacji w usłudze Microsoft Intune](app-protection-policies.md)

## <a name="see-also"></a>Zobacz także
Aplikacje innych firm, takie jak aplikacja mobilna Salesforce, współpracują w określony sposób z usługą Intune, aby chronić dane firmowe. Aby dowiedzieć się więcej o tym, jak aplikacja Salesforce współpracuje w szczególności z usługą Intune (z uwzględnieniem ustawień konfiguracji aplikacji MDM), zobacz temat [Salesforce App and Microsoft Intune](https://gallery.technet.microsoft.com/Salesforce-App-and-Intune-c47d44ee/file/188000/1/Salesforce%20App%20and%20Intune%20for%20external.pdf) (Aplikacja Salesforce i usługa Microsoft Intune).
