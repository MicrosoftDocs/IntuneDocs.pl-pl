---
title: "Co to są zasady ochrony aplikacji"
titleSuffix: Intune on Azure
description: "Informacje dotyczące ochrony danych firmowych przy użyciu zasad ochrony aplikacji w usłudze Microsoft Intune."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 01/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1c086943-84a0-4d99-8295-490a2bc5be4b
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 13b3199108c34a61d117e4d89d118bdd05d7d20f
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/03/2017
---
# <a name="what-are-app-protection-policies"></a>Co to są zasady ochrony aplikacji?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Zasady ochrony aplikacji w usłudze Microsoft Intune wspomagają ochronę danych firmowych i zapobiegają utracie danych.

## <a name="how-you-can-protect-app-data"></a>Jak możesz chronić dane aplikacji
Pracownicy używają urządzeń przenośnych zarówno do celów służbowych, jak i prywatnych.  Zatem umożliwiając pracownikom wydajną pracę, warto również zapobiegać nieumyślnej lub umyślnej utracie danych.  Ponadto chcesz mieć możliwość ochrony danych firmowych, do których dostęp jest uzyskiwany za pomocą urządzeń, nawet w przypadku, gdy nie są zarządzane przez Ciebie.

Aby lepiej chronić dane firmy, możesz skorzystać z zasad ochrony aplikacji w usłudze Intune. Ponieważ zasady ochrony aplikacji w usłudze Intune są **niezależne od jakichkolwiek rozwiązań do zarządzania urządzeniami mobilnymi (MDM, mobile device management)**, możesz używać ich do ochrony danych firmy bez względu na to, czy urządzenia zostały zarejestrowane w rozwiązaniach do zarządzania urządzeniami. Wdrażając **zasady na poziomie aplikacji**, można ograniczyć dostęp do zasobów firmy i objęcia danych kontrolą działu IT.

Zasady ochrony aplikacji można skonfigurować dla aplikacji uruchamianych na urządzeniach, które są:

- **Zarejestrowane w usłudze Microsoft Intune:** urządzenia w tej kategorii są przeważnie urządzeniami należącymi do firmy.

-   **Zarejestrowane w rozwiązaniu do zarządzania urządzeniami mobilnymi (MDM) innej firmy:** urządzenia w tej kategorii są przeważnie urządzeniami należącymi do firmy.

  > [!NOTE]
  > Zasady zarządzania aplikacjami mobilnymi nie powinny być stosowane z rozwiązaniami bezpiecznego kontenera ani rozwiązaniami do zarządzania aplikacjami mobilnymi innych firm.

-   **Niezarejestrowane w żadnym rozwiązaniu do zarządzania urządzeniami mobilnymi :** urządzenia w tej kategorii są zazwyczaj należącymi do pracowników urządzeniami, które nie są zarządzane lub nie zostały zarejestrowane w usłudze Intune ani innych rozwiązań MDM.

> [!IMPORTANT]
> Możesz tworzyć zasady zarządzania aplikacjami mobilnymi dla aplikacji mobilnych pakietu Office łączących się z usługą Office 365. Zasady ochrony aplikacji nie są obsługiwane przez aplikacje, które łączą się z lokalnymi usługami Exchange, Skype dla firm lub SharePoint.

**Do istotnych korzyści zapewnianych przez zasady ochrony aplikacji należą:**

-   Ochrona danych firmy na poziomie aplikacji.  Ponieważ zarządzanie aplikacjami mobilnymi nie wymaga zarządzania urządzeniami, można chronić dane firmy zarówno na urządzeniach zarządzanych, jak i niezarządzanych. Zarządzanie skupia się na tożsamości użytkownika, co eliminuje konieczność zarządzania urządzeniem.

-   Zasady nie mają wpływu na produktywność użytkownika końcowego i nie są stosowane podczas korzystania z aplikacji w kontekście prywatnym.  Zasady są stosowane wyłącznie w kontekście służbowym, dzięki czemu możesz chronić dane firmowe, nie ingerując w dane prywatne.

Dodatkowe korzyści można uzyskać, używając jednocześnie rozwiązań MDM i zasad ochrony aplikacji. Firmy mogą w tym samym czasie korzystać z zasad ochrony aplikacji łącznie z rozwiązaniem MDM lub bez niego. Na przykład pracownik może używać telefonu otrzymanego od firmy oraz prywatnego tabletu.  W takiej sytuacji telefon firmowy jest zarejestrowany w rozwiązaniu MDM i chroniony przez zasady ochrony aplikacji, natomiast urządzenie prywatne jest chronione tylko przez zasady ochrony aplikacji.

- **Rozwiązanie MDM zapewnia ochronę urządzenia**.  Możesz na przykład zastosować zabezpieczenie dostępu do urządzenia numerem PIN lub wdrożyć na urządzeniu aplikacje zarządzane. Możesz również wdrażać aplikacje na urządzeniach za pośrednictwem rozwiązania MDM, aby mieć lepszą kontrolę nad zarządzaniem aplikacjami.

- **Zasady ochrony aplikacji zapewniają stosowanie zabezpieczeń warstwy aplikacji**. Możesz na przykład zastosować wymaganie numeru PIN w celu otwarcia aplikacji w kontekście służbowym lub, jeśli dane mogą być udostępniane innym aplikacjom, uniemożliwić zapisywanie firmowych danych aplikacji w prywatnej lokalizacji magazynu.


### <a name="supported-platforms-for-app-protection-polices"></a>Platformy obsługiwane przez zasady ochrony aplikacji
-   System iOS 8.1 lub nowszy

-   System Android 4 lub nowszy

Urządzenia z systemem Windows nie są obecne obsługiwane. Jednak podczas rejestrowania urządzeń z systemem Windows 10 w usłudze Intune możesz użyć rozwiązania Windows Information Protection, które oferuje podobne funkcje. Aby uzyskać szczegółowe informacje, zobacz [Protect your enterprise data using Windows Information Protection](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip) (Chronienie danych przedsiębiorstwa przy użyciu rozwiązania Windows Information Protection).
##  <a name="how-app-protection-policies-protect-app-data"></a>W jaki sposób zasady ochrony aplikacji chronią dane aplikacji

####  <a name="apps-without-app-protection-policies"></a>Aplikacje bez zasad ochrony aplikacji

![Obraz przedstawiający swobodne przemieszczanie się danych między aplikacjami w sytuacji, gdy zasady ochrony aplikacji nie zostały wdrożone](./media/apps-without-protection-policies.png)

W przypadku korzystania z aplikacji bez ograniczeń dane firmowe i prywatne mogą ulec wymieszaniu.  Dane firmowe mogą więc trafić na przykład do magazynu osobistego albo do aplikacji pozostających poza Twoją kontrolą, co grozi utratą danych. Strzałki na rysunku oznaczają nieograniczone przemieszczanie się danych między aplikacjami (firmowymi i prywatnymi) oraz do lokalizacji magazynu.

### <a name="data-protection-with-app-protection-policies"></a>Ochrona danych za pomocą zasad ochrony aplikacji

![Obraz przedstawiający sposób ochrony danych firmowych po zastosowaniu zasad ochrony aplikacji ](./media/apps-with-protection-policies.png)


Zasady ochrony aplikacji pozwalają zapobiegać zapisywaniu danych firmy w lokalnym magazynie urządzenia. Ponadto ograniczają ruch danych do innych aplikacji, które nie są chronione przy użyciu zasad ochrony aplikacji. Ustawienia zasad ochrony aplikacji obejmują:
- Zasady przenoszenia danych, takie jak **Nie zezwalaj na używanie polecenia Zapisz jako** i **Ogranicz wycinanie, kopiowanie i wklejanie**.
- Ustawienia zasad dostępu, takie jak **Wymagaj prostego numeru PIN w celu udzielenia dostępu**, **Blokuj uruchamianie aplikacji zarządzanych na urządzeniach ze zdjętymi zabezpieczeniami systemu lub odblokowanym dostępem do konta administratora**.

### <a name="data-protection-with-app-protection-policies-on-devices-managed-by-a-mdm-solution"></a>Ochrona danych za pomocą zasad ochrony aplikacji na urządzeniach zarządzanych przez rozwiązanie MDM

![Obraz przedstawiający sposób działania zasad ochrony aplikacji na urządzeniach BYOD](./media/app-protection-policies-with-mdm.png)

**W przypadku urządzeń zarejestrowanych w rozwiązaniu MDM**-

Ilustracja powyżej przedstawia warstwy ochrony zapewniane łącznie przez rozwiązanie MDM i zasady ochrony aplikacji.

Rozwiązanie MDM:

-   Rejestruje urządzenie

-   Wdraża aplikacje na urządzeniu

-   Na bieżąco zapewnia zgodność urządzenia i zarządza nim

**Zasady ochrony aplikacji zapewniają następujące korzyści:**

-   Chronią dane firmy przed wyciekiem do aplikacji i usług dla konsumentów

-   Stosują ograniczenia (zapisz jako, schowek, numer PIN itp.) do aplikacji mobilnych

-   Wymazują dane firmowe z aplikacji, nie usuwając tych aplikacji z urządzenia


### <a name="data-protection-with-app-protection-policies-for-devices-without-enrollment"></a>Ochrona danych za pomocą zasad ochrony aplikacji na urządzeniach bez rejestracji

![Obraz przedstawiający sposób działania zasad ochrony aplikacji na urządzeniach zarządzanych](./media/app-protection-policies-without-mdm.png)

Powyższy rysunek przedstawia sposób działania zasad ochrony danych na poziomie aplikacji bez rozwiązania MDM.

W przypadku urządzeń BYOD niezarejestrowanych w rozwiązaniu MDM zasady ochrony aplikacji wspomagają ochronę danych firmowych na poziomie aplikacji.
Należy jednak wziąć pod uwagę następujące ograniczenia:

-   Na tym urządzeniu nie można wdrażać aplikacji.  Użytkownik końcowy musi uzyskać aplikacje ze sklepu.

-   Na tych urządzeniach nie można dostarczać profilów certyfikatów.

-   Na tych urządzeniach nie można dostarczać ustawień firmowych sieci Wi-Fi i VPN.


## <a name="multi-identity"></a>Wiele tożsamości

Aplikacje, które obsługują wiele tożsamości, umożliwiają uzyskiwanie dostępu do tych samych aplikacji przy użyciu różnych kont (służbowych i osobistych), podczas gdy zasady ochrony aplikacji są stosowane tylko wtedy, gdy aplikacje są używane w kontekście służbowym.

Jeśli na przykład użytkownik uruchamia aplikację OneDrive przy użyciu konta służbowego, nie może przenieść plików do lokalizacji magazynu osobistego. Jeśli jednak użytkownik korzysta z usługi OneDrive przy użyciu konta osobistego, może bez ograniczeń kopiować i przenosić dane z usługi OneDrive w wersji do użytku osobistego.

- Dowiedz się więcej o aplikacjach, które obsługują [zarządzanie aplikacjami mobilnymi (MAM) i wiele tożsamości](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) za pomocą usługi Intune.

##  <a name="next-steps"></a>Następne kroki

[Sposoby tworzenia i wdrażania zasad ochrony aplikacji w usłudze Microsoft Intune](app-protection-policies.md)
