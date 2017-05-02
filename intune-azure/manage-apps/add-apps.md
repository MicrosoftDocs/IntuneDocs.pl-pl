---
title: "Jak dodawać aplikacje do usługi Microsoft Intune"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: te procedury ułatwiają przygotowanie aplikacji do usługi Intune do przypisania do użytkowników i urządzeń. "
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: d85544bdfaa3a369e1d2d03e5454ff7aa2d75467
ms.lasthandoff: 04/19/2017

---

# <a name="how-to-add-an-app-to-microsoft-intune"></a>Jak dodawać aplikacje do usługi Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Aby można było zarządzać aplikacjami oraz przypisać je do użytkowników, należy dodać je do usługi Intune. Usługa Intune obsługuje szeroką gamę różnych typów aplikacji i opcje dla poszczególnych typów mogą się różnić.

Usługa Intune pozwala dodawać i przypisywać następujące typy aplikacji:

![Typy aplikacji obsługiwane przez usługę Intune](./media/app-types.png)

Obsługiwane są następujące platformy: Klikaj tematy, aby uzyskać więcej informacji o dodawaniu poszczególnych typów aplikacji.

- [Aplikacje ze sklepu dla systemu Android](/intune-azure/manage-apps/android-store-app)
- [Aplikacje LOB dla systemu Android](/intune-azure/manage-apps/android-lob-app)
- [Aplikacje ze sklepu dla systemu iOS](/intune-azure/manage-apps/ios-store-app)
- [Aplikacje LOB dla systemu iOS](/intune-azure/manage-apps/ios-lob-app)
- [Aplikacje sieci Web (dla wszystkich platform)](/intune-azure/manage-apps/web-app)
- [Aplikacje ze sklepu dla systemu Windows Phone 8.1](/intune-azure/manage-apps/windows-phone-8-1-store-app)
- [Aplikacje ze sklepu dla systemu Windows](/intune-azure/manage-apps/windows-store-app)

Ponadto niektóre aplikacje firmy Microsoft są dodawane automatycznie przez usługę Intune podczas konfigurowania dzierżawy. Lista tych aplikacji znajduje się w dalszej części tego tematu.

## <a name="before-you-start"></a>Przed rozpoczęciem

Przed rozpoczęciem dodawania i przypisywania aplikacji należy wziąć pod uwagę poniższe kwestie.

- Kiedy dodajesz i wdrażasz aplikację ze sklepu, użytkownicy końcowi muszą mieć konto w danym sklepie, aby móc zainstalować daną aplikację.
- Niektóre wdrażane aplikacje lub elementy mogą być zależne od wbudowanych aplikacji systemu iOS. Na przykład, aby wdrożyć książkę ze sklepu iOS, w urządzeniu musi być zainstalowana aplikacja iBooks. W przypadku usunięcia wbudowanej aplikacji iBooks nie ma możliwości użycia usługi Intune do jej przywrócenia.

## <a name="cloud-storage-space"></a>Miejsce do magazynowania w chmurze
Wszystkie aplikacje tworzone przy użyciu instalatora oprogramowania (na przykład aplikacje biznesowe) zostają spakowane i przekazane do magazynu w chmurze usługi Microsoft Intune. Subskrypcja próbna usługi Intune obejmuje 2 GB magazynu opartego na chmurze, który jest używany do przechowywania zarządzanych aplikacji i aktualizacji. Pełna subskrypcja obejmuje 20 GB miejsca do magazynowania.

Możesz kupić dodatkowy magazyn dla usługi Intune przy użyciu pierwotnej metody zakupu.  Jeśli zakupu dokonano przy użyciu faktury lub karty kredytowej, odwiedź [portal zarządzania subskrypcją](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions).  W przeciwnym razie skontaktuj się ze swoim partnerem lub współpracownikiem ds. sprzedaży.

Wymagania dotyczące miejsca do magazynowania w chmurze są następujące:

-   Wszystkie pliki instalacyjne aplikacji muszą znajdować się w tym samym folderze.
-   Maksymalny rozmiar dowolnego przekazywanego pliku wynosi 2 GB.

## <a name="how-to-create-and-edit-categories-for-apps"></a>Jak tworzyć i edytować kategorie aplikacji

Kategorie aplikacji mogą ułatwić ich sortowanie, aby użytkownicy końcowi mogli je łatwiej znaleźć w portalu firmy. Do aplikacji można przypisać jedną lub więcej kategorii, na przykład **Aplikacje dla programistów** lub **Aplikacje komunikacji**.
Po dodaniu aplikacji do usługi Intune istnieje możliwość wybrania dowolnej kategorii. Tematy dotyczące określonych platform zawierają informacje o dodawaniu aplikacji i przypisywaniu kategorii. Do tworzenia i edytowania własnych kategorii użyj następującej procedury:

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Zarządzaj aplikacjami**.
4. W obciążeniu **Aplikacje mobilne** wybierz kolejno opcje **Instalacja** > **Kategorie aplikacji**.
5. W bloku **Kategorie aplikacji** zostanie wyświetlona lista bieżących kategorii. Wybierz jedno z następujących działań:
    - **Tworzenie kategorii** — w bloku **Tworzenie kategorii** wprowadź nazwę nowej kategorii. Nazwy można wprowadzić tylko w jednym języku i nie są one tłumaczone przez usługę Intune. Po zakończeniu kliknij przycisk **Utwórz**.
    - **Edytuj kategorię** — dla kategorii na liście wybierz opcję „**...**”. W bloku **Właściwości** można wprowadzić nową nazwę kategorii lub usunąć kategorię.


## <a name="apps-added-automatically-by-intune"></a>Aplikacje dodawane automatycznie przez usługę Intune

Poniższe aplikacje wydane przez firmę Microsoft stanowią wbudowane elementy usługi Intune gotowe do przypisywania:

|||
|-|-|
|Nazwa|Platforma|Typ aplikacji|
|Azure Information Protection|Android|Zarządzana aplikacja w sklepie dla systemu Android|
|Dynamics CRM na telefony|Android|Zarządzana aplikacja w sklepie dla systemu Android|
|Dynamics CRM na tablety|Android|Zarządzana aplikacja w sklepie dla systemu Android|
|Excel|iOS|Zarządzana aplikacja w sklepie dla systemu iOS|
|Excel|Android|Zarządzana aplikacja w sklepie dla systemu Android|
|Managed Browser|Android|Zarządzana aplikacja w sklepie dla systemu Android|
|Managed Browser|iOS|Zarządzana aplikacja w sklepie dla systemu iOS|
|Microsoft Dynamics CRM na telefony|iOS|Zarządzana aplikacja w sklepie dla systemu iOS|
|Microsoft Dynamics CRM na tablety|iOS|Zarządzana aplikacja w sklepie dla systemu iOS|
|Microsoft Power BI|iOS|Zarządzana aplikacja w sklepie dla systemu iOS|
|Microsoft Power BI|Android|Zarządzana aplikacja w sklepie dla systemu Android|
|Microsoft SharePoint|iOS|Zarządzana aplikacja w sklepie dla systemu iOS|
|Microsoft SharePoint|Android|Zarządzana aplikacja w sklepie dla systemu Android|
|Microsoft Teams|Android|Zarządzana aplikacja w sklepie dla systemu Android|
|Microsoft Teams|iOS|Zarządzana aplikacja w sklepie dla systemu iOS|
|OneDrive|iOS|Zarządzana aplikacja w sklepie dla systemu iOS|
|OneDrive|Android|Zarządzana aplikacja w sklepie dla systemu Android|
|OneNote|iOS|Zarządzana aplikacja w sklepie dla systemu iOS|
|Outlook|Android|Zarządzana aplikacja w sklepie dla systemu Android|
|Outlook|iOS|Zarządzana aplikacja w sklepie dla systemu iOS|
|Outlook Groups|Android|Zarządzana aplikacja w sklepie dla systemu Android|
|Outlook Groups|iOS|Zarządzana aplikacja w sklepie dla systemu iOS|
|PowerPoint|iOS|Zarządzana aplikacja w sklepie dla systemu iOS|

