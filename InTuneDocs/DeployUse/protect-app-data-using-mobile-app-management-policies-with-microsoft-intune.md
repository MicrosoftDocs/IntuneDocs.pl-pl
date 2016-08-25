---
# required metadata

title: Ochrona danych aplikacji przy użyciu zasad zarządzania aplikacjami mobilnymi | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ab6cd622-b738-4a63-9c91-56044aaafa6d

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: joglocke
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Ochrona danych aplikacji przy użyciu zasad zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune

## Jak możesz chronić dane aplikacji
Pracownicy używają urządzeń przenośnych zarówno do celów służbowych, jak i prywatnych.  Zatem umożliwiając pracownikom wydajną pracę, warto również zapobiegać nieumyślnej lub umyślnej utracie danych.  Ponadto chcesz mieć możliwość ochrony danych firmowych, do których dostęp jest uzyskiwany za pomocą urządzeń, nawet w przypadku, gdy nie są zarządzane przez Ciebie.

Aby lepiej chronić dane firmy, możesz skorzystać z zasad zarządzania aplikacjami mobilnymi (MAM, mobile app management) w usłudze Intune. Ponieważ zasady MAM w usłudze Intune są niezależne od wszelkich rozwiązań do zarządzania urządzeniami przenośnymi (MDM, mobile device management), możesz użyć jej do ochrony danych firmy bez względu na to, czy urządzenia zostały zarejestrowane w rozwiązaniach do zarządzania urządzeniami. Wdrażając **zasady na poziomie aplikacji**, można ograniczyć dostęp do zasobów firmy i objęcia danych kontrolą działu IT.

Zasady MAM obsługują aplikacje działające na:

-   **Urządzeniach zarządzanych i zarejestrowanych** w usłudze [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. Urządzenia w tej kategorii są przeważnie urządzeniami należącymi do firmy.

  > [!IMPORTANT]
  > Jeśli używasz usługi Intune do zarządzania urządzeniami z systemem Android i iOS, możesz tworzyć zasady zarządzania aplikacjami mobilnymi dla aplikacji mobilnych pakietu Office łączących się z usługą Office 365. Zasady MAM nie są obsługiwane w przypadku aplikacji łączących się z lokalnymi usługami Exchange lub SharePoint.

-   **Urządzeniach zarządzanych i zarejestrowanych w rozwiązaniu do zarządzania urządzeniami przenośnymi innej firmy**.   Urządzenia w tej kategorii są przeważnie urządzeniami należącymi do firmy.

  > [!NOTE] Zasady zarządzania aplikacjami mobilnymi nie powinny być stosowane z rozwiązaniami do zabezpieczania kontenerów ani rozwiązaniami do zarządzania aplikacjami mobilnymi innych firm.

-   **Urządzenia niezarządzane**.  Urządzenia w tej kategorii są zazwyczaj należącymi do pracowników urządzeniami, które nie są zarządzane lub nie zostały zarejestrowane w usłudze Intune ani innych rozwiązań MDM.

**Istotne zalety stosowania zasad MAM to:**

-   Ochrona danych firmy na poziomie aplikacji.  Ponieważ zarządzanie aplikacjami mobilnymi nie wymaga zarządzania urządzeniami, można chronić dane firmy zarówno na urządzeniach zarządzanych, jak i niezarządzanych. Zarządzanie skupia się na tożsamości użytkownika, co eliminuje konieczność zarządzania urządzeniem.

-   Zasady nie mają wpływu na produktywność użytkownika końcowego i nie są stosowane podczas korzystania z aplikacji w kontekście prywatnym.  Zasady są stosowane wyłącznie w kontekście służbowym, dzięki czemu możesz chronić dane firmowe, nie ingerując w dane prywatne.

Stosowanie rozwiązań MDM jednocześnie z zasadami MAM jest możliwe i daje dodatkowe korzyści. Firmy mogą równocześnie korzystać z rozwiązania MAM z rozwiązaniem MDM lub bez niego. Na przykład pracownik może używać telefonu otrzymanego od firmy oraz prywatnego tabletu.  W takiej sytuacji telefon firmowy jest zarejestrowany w rozwiązaniu MDM i chroniony przez zasady MAM, natomiast urządzenie prywatne jest chronione tylko przez zasady MAM.

- **Rozwiązanie MDM zapewnia ochronę urządzenia**.  Możesz na przykład zastosować zabezpieczenie dostępu do urządzenia numerem PIN lub wdrożyć na urządzeniu aplikacje zarządzane. Możesz również wdrażać aplikacje na urządzeniach za pośrednictwem rozwiązania MDM, aby mieć lepszą kontrolę nad zarządzaniem aplikacjami.

- **Zasady MAM zapewniają ochronę warstwy aplikacji**. Możesz na przykład zastosować wymaganie numeru PIN w celu otwarcia aplikacji w kontekście służbowym lub, jeśli dane mogą być udostępniane innym aplikacjom, uniemożliwić zapisywanie firmowych danych aplikacji w prywatnej lokalizacji magazynu.


### Zasady MAM są obecnie obsługiwane na:
-   System iOS 8.1 lub nowszy

-   System Android 4 lub nowszy

Urządzenia z systemem Windows nie są obecne obsługiwane.
##  Jak zasady MAM chronią dane aplikacji

####  Aplikacje bez zasad MAM:

![Obraz pokazujący, że dane mogą swobodnie przemieszczać się między aplikacjami, jeśli nie wdrożono zasad MAM](../media/Apps_without_MAM_policies.png)

W przypadku korzystania z aplikacji bez ograniczeń dane firmowe i prywatne mogą ulec wymieszaniu.  Dane firmowe mogą więc trafić na przykład do magazynu osobistego albo do aplikacji pozostających poza Twoją kontrolą, co grozi utratą danych. Strzałki na rysunku oznaczają nieograniczone przemieszczanie się danych między aplikacjami (firmowymi i prywatnymi) oraz do lokalizacji magazynu.

### Ochrona danych za pomocą zasad MAM:

![Obraz pokazujący sposób ochrony danych firmowych po zastosowaniu zasad MAM ](../media/Apps_with_mobile_app_policies.png)

Zasady MAM umożliwiają zapobieganie zapisywaniu danych firmy w lokalnym magazynie urządzenia i ograniczanie ruchu danych do innych aplikacji, które nie są chronione przy użyciu zasad MAM. Ustawienia zasad MAM to:
- Zasady przenoszenia danych, takie jak **Nie zezwalaj na używanie polecenia Zapisz jako** i **Ogranicz wycinanie, kopiowanie i wklejanie**.
- Ustawienia zasad dostępu, takie jak **Wymagaj prostego numeru PIN w celu udzielenia dostępu**, **Blokuj uruchamianie aplikacji zarządzanych na urządzeniach ze zdjętymi zabezpieczeniami systemu lub odblokowanym dostępem do konta administratora**.

### Ochrona danych za pomocą zasad MAM na urządzeniach zarządzanych przez rozwiązanie MDM:

![Obraz pokazujący sposób działania zasad MAM na urządzeniach BYOD](../media/MAM_BYOD_November.png)

**W przypadku urządzeń zarejestrowanych w rozwiązaniu MDM**-

Powyższy rysunek przedstawia warstwy ochrony zapewniane przez rozwiązanie MDM i zasady MAM.

Rozwiązanie MDM:

-   Rejestruje urządzenie

-   Wdraża aplikacje na urządzeniu

-   Na bieżąco zapewnia zgodność urządzenia i zarządza nim

**Zasady MAM dodają następujące korzyści:**

-   Chronią dane firmy przed wyciekiem do aplikacji i usług dla konsumentów

-   Stosują ograniczenia (zapisz jako, schowek, numer PIN itp.) do aplikacji mobilnych

-   Wymazują dane firmowe z aplikacji, nie usuwając tych aplikacji z urządzenia


### Ochrona danych za pomocą zasad MAM dla urządzeń bez rejestracji

![Obraz pokazujący sposób działania zasad MAM na urządzeniach zarządzanych](../media/MAM_ManagedDevices_November.png)

Powyższy rysunek przedstawia sposób działania zasad ochrony danych na poziomie aplikacji bez rozwiązania MDM.

W przypadku urządzeń BYOD niezarejestrowanych w żadnym rozwiązaniu MDM zasady MAM mogą pomóc w ochronie danych firmowych na poziomie aplikacji.
Należy jednak wziąć pod uwagę następujące ograniczenia:

-   Na tym urządzeniu nie można wdrażać aplikacji.  Użytkownik końcowy musi uzyskać aplikacje ze sklepu.

-   Na tych urządzeniach nie można dostarczać profilów certyfikatów.

-   Na tych urządzeniach nie można dostarczać ustawień firmowych sieci Wi-Fi i VPN.


## Wiele tożsamości

Aplikacje, które obsługują wiele tożsamości, umożliwiają używanie różnych kont — służbowych i osobistych — do uzyskiwania dostępu do tych samych aplikacji, podczas gdy zasady MAM są stosowane, gdy jeśli aplikacje są używane w kontekście służbowym.  

Jeśli na przykład użytkownik końcowy uruchamia aplikację OneDrive przy użyciu konta służbowego, nie może przenieść plików do lokalizacji magazynu osobistego. Jeśli jednak użytkownik korzysta z usługi OneDrive na koncie osobistym, może bez ograniczeń kopiować i przenosić dane z usługi OneDrive w wersji do użytku osobistego.  

Szczegółowe informacje na temat korzystania z aplikacji skojarzonych z zasadami MAM oraz tego, jak aplikacje z włączoną obsługą wielu tożsamości umożliwiają stosowanie zasad MAM tylko w kontekście służbowym, można znaleźć w temacie dotyczącym [korzystania z aplikacji z obsługą wielu tożsamości](end-user-experience-for-mam-enabled-apps-with-microsoft-intune.md#using-apps-with-multi-identity-support)

Wszystkie aplikacje mobilne pakietu Office obsługują wiele tożsamości.

##  Następne kroki
[Przygotowywanie się do konfigurowania zasad zarządzania aplikacjami mobilnymi](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)

[Tworzenie i wdrażanie zasad zarządzania aplikacjami mobilnymi przy użyciu usługi Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)


<!--HONumber=Jun16_HO2-->


