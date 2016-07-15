---
# required metadata

title: Wdrażanie aplikacji | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ad5ea85c-aa2e-4110-a184-172cd0b8f270

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Wdrażanie aplikacji w usłudze Microsoft Intune

W tym temacie omówiono pojęcia, które należy zrozumieć przed rozpoczęciem wdrażania aplikacji w usłudze Microsoft Intune.

## Wydawca oprogramowania usługi Intune
**Wydawca oprogramowania usługi Microsoft Intune** jest uruchamiany podczas dodawania lub modyfikowania aplikacji w konsoli administratora usługi Microsoft Intune. Za pomocą wydawcy należy wybrać i skonfigurować typ instalatora oprogramowania, który przekaże aplikacje (programy dla komputerów lub aplikacje dla urządzeń przenośnych) do przechowywania w magazynie w chmurze usługi Intune albo utworzy link do aplikacji w sklepie online lub aplikacji internetowej.

### Wymagania
Przed rozpoczęciem korzystania z Wydawcy oprogramowania usługi Microsoft Intune należy zainstalować pełną wersję programu [Microsoft .NET Framework 4.0](https://www.microsoft.com/download/details.aspx?id=17851). Po zainstalowaniu może być konieczne ponowne uruchomienie komputera, aby Wydawca oprogramowania został poprawnie otwarty.

## Miejsce do magazynowania w chmurze
Wszystkie aplikacje wdrażane przy użyciu instalatora oprogramowania muszą być spakowane i przekazane do magazynu w chmurze usługi Microsoft Intune. Subskrypcja próbna usługi Intune obejmuje 2 GB magazynu opartego na chmurze, który jest używany do przechowywania zarządzanych aplikacji i aktualizacji. Subskrypcja płatna obejmuje 20 GB z możliwością zakupu dodatkowego magazynu.

Sprawdzenia ilości wykorzystanego miejsca i zakupu dodatkowego magazynu można dokonać w węźle **Użycie magazynu** w obszarze roboczym **Administrator**.

Przy zakupie dodatkowego magazynu w chmurze dla usługi Intune mają zastosowanie następujące reguły:

-   Aby kupić dodatkowy magazyn, trzeba mieć aktywną subskrypcję płatną.

-   Możliwość zakupu dodatkowego magazynu za pośrednictwem portalu zarządzania usługi Office 365 mają tylko administratorzy rozliczeń lub administratorzy globalni usług Microsoft Online Services. Aby dodać lub usunąć tych administratorów i zarządzać nimi, musisz być administratorem globalnym i zalogować się w portalu zarządzania usługi Office 365.

-   Klienci objęci licencjonowaniem zbiorowym, którzy nabyli usługę Intune lub dodatek usługi Microsoft Intune w ramach umowy Enterprise Agreement, powinni skontaktować się z menedżerem ds. klientów firmy Microsoft lub partnerem firmy Microsoft w celu uzyskania informacji o cenach i zakupu dodatkowego magazynu.

#### Wymagania dotyczące miejsca do magazynowania w chmurze

-   Wszystkie pliki skojarzone z aplikacją muszą znajdować się w tej samej lokalizacji i być dostępne dla usługi Intune.

-   Maksymalny rozmiar dowolnego przekazywanego pliku wynosi 2 GB.

-   Do przekazywania plików jest niezbędne połączenie internetowe o szybkości co najmniej 768 kb/s.

## Akcje wdrażania aplikacji
Podczas wdrażania aplikacji można wybrać jedną z następujących akcji wdrażania:

-   **Wymagana instalacja** — aplikacja jest instalowana na urządzeniu bez potrzeby interwencji użytkownika końcowego.

    > [!TIP] W przypadku urządzeń z systemem iOS niebędących w trybie nadzorowanym oraz wszystkich urządzeń z systemem Android użytkownik musi zaakceptować ofertę aplikacji, zanim zostanie ona zainstalowana.
    >
    > Nie można już tworzyć nowych wdrożeń aplikacji na urządzeniach z systemem operacyjnym iOS w wersji starszej niż iOS 7.1. Wszystkie istniejące wdrożenia aplikacji na urządzeniach z systemem operacyjnym starszym niż iOS 7.1 będą w dalszym ciągu działać i będą zarządzane za pomocą usługi Intune.
    > 
    >  Jeśli użytkownik odinstaluje aplikację, która została wdrożona jako instalacja wymagana, usługa Intune automatycznie ponownie zainstaluje aplikację po następnym cyklu spisu, który ma miejsce zazwyczaj co 7 dni.

-   **Dostępna instalacja** — aplikacja jest wyświetlana w portalu firmy i użytkownicy końcowi mogą zainstalować ją na żądanie.

-   **Odinstaluj** — aplikacja zostanie odinstalowana z urządzenia.

-   **Nie dotyczy** — aplikacja nie jest wyświetlana w portalu firmy i nie jest instalowana na żadnych urządzeniach.

#### Opis akcji wdrażania dostępnych dla poszczególnych typów instalatora

|Typ instalatora|Wymagana instalacja|Dostępna instalacja|Odinstaluj|Nie dotyczy|
|------------------|--------------------|---------------------|-------------|------------------|
|Pakiet aplikacji systemu Windows (wdrożenie w grupie użytkowników)|Tak|Tak|Tak|Tak|
|Pakiet aplikacji systemu Windows (wdrożenie w grupie urządzeń)|Tak|Nie|Tak|Tak|
|Pakiet aplikacji dla urządzeń przenośnych (wdrożenie w grupie użytkowników)|Tak|Tak|Tak|Tak|
|Pakiet aplikacji dla urządzeń przenośnych (wdrożenie w grupie urządzeń)|Tak|Nie|Tak|Tak|
|Instalator systemu Windows (wdrożenie w grupie użytkowników)|Nie|Tak|Nie|Tak|
|Instalator systemu Windows (wdrożenie w grupie urządzeń)|Tak|Nie|Tak|Tak|
|Link zewnętrzny (wdrożenie w grupie użytkowników)|Nie|Tak|Nie|Tak|
|Link zewnętrzny (wdrożenie w grupie urządzeń)|Nie|Nie|Nie|Nie|
|Zarządzana aplikacja systemu iOS ze sklepu App Store (wdrożenie w grupie użytkowników)|Tak|Tak|Tak|Tak|
|Zarządzana aplikacja systemu iOS ze sklepu App Store (wdrożenie w grupie urządzeń)|Tak|Nie|Tak|Tak|
> [!TIP] Jeśli podczas wdrażania aplikacji wybierzesz zarówno grupę użytkowników, jak i grupę urządzeń, możesz wdrożyć aplikację jedynie przy użyciu ustawienia **Dostępna instalacja**.

## Konflikty wdrażania
W przypadku gdy urządzenie otrzymuje dwa wdrożenia z tą samą akcją wdrażania, stosowane są następujące reguły:

-   Wdrożenia w grupie urządzeń mają pierwszeństwo przed wdrożeniami w grupie użytkowników. Jednak jeśli ta sama aplikacja jest wdrożona dla grupy użytkowników przy użyciu akcji wdrażania **Dostępne** i wdrożona dla grupy urządzeń przy użyciu akcji wdrażania **Nie dotyczy**, aplikacja zostanie udostępniona w portalu firmy, aby użytkownicy mogli ją zainstalować.

-   Zamiar administratora IT ma pierwszeństwo przed użytkownikiem.

-   Akcja instalacji ma pierwszeństwo przed akcją dezinstalacji.

-   Jeśli urządzenie otrzymuje zarówno wymaganą, jak i dostępną instalację, akcje zostają połączone (aplikacja jest wymagana i dostępna).


## Następne kroki

Dowiedz się, jak [wdrażać aplikacje w usłudze Microsoft Intune](deploy-apps-in-microsoft-intune.md).

<!--HONumber=Jun16_HO2-->


