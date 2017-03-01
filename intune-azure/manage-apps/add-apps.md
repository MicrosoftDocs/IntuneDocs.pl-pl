---
title: "Jak dodać aplikacje do usługi Microsoft Intune | Wersja zapoznawcza usługi Intune Azure | Dokumentacja firmy Microsoft"
description: "Wersja zapoznawcza usługi Intune Azure: te procedury ułatwiają przygotowanie aplikacji do usługi Intune do przypisania do użytkowników i urządzeń. "
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 472e65be196d1090e89b46271bb97a82b6fb1a9c
ms.lasthandoff: 02/16/2017

---

# <a name="how-to-add-an-app-to-microsoft-intune"></a>Jak dodawać aplikacje do usługi Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Aby można było zarządzać aplikacjami oraz przypisać je do użytkowników, należy dodać je do usługi Intune. Usługa Intune obsługuje szeroką gamę różnych typów aplikacji i opcje dla poszczególnych typów mogą się różnić.

Usługa Intune obsługuje dodawanie i przypisywanie aplikacji następujących typów:

![Typy aplikacji obsługiwane przez usługę Intune](./media/app-types.png)

Obsługiwane są następujące platformy: Klikaj tematy, aby uzyskać więcej informacji o dodawaniu poszczególnych typów aplikacji.

- [Aplikacje biznesowe dla systemu Android](/intune-azure/manage-apps/android-lob-app)
- [Aplikacje ze sklepu dla systemu Android](/intune-azure/manage-apps/android-store-app)
- [Aplikacje biznesowe dla systemu iOS](/intune-azure/manage-apps/ios-lob-app)
- [Aplikacje ze sklepu dla systemu iOS](/intune-azure/manage-apps/ios-store-app)
- [Aplikacje sieci Web (dla wszystkich platform)](/intune-azure/manage-apps/web-app)
- [Aplikacje ze sklepu dla systemu Windows Phone 8.1](/intune-azure/manage-apps/windows-phone-8-1-store-app)
- [Aplikacje ze sklepu dla systemu Windows](/intune-azure/manage-apps/windows-store-app)

> [!NOTE]
> Kiedy dodajesz i wdrażasz aplikację ze sklepu, użytkownicy końcowi muszą mieć konto w danym sklepie, aby móc zainstalować daną aplikację.

## <a name="cloud-storage-space"></a>Miejsce do magazynowania w chmurze
Wszystkie aplikacje tworzone przy użyciu instalatora oprogramowania (na przykład aplikacje biznesowe) zostają spakowane i przekazane do magazynu w chmurze usługi Microsoft Intune. Subskrypcja próbna usługi Intune obejmuje 2 GB magazynu opartego na chmurze, który jest używany do przechowywania zarządzanych aplikacji i aktualizacji. Pełna subskrypcja obejmuje 20 GB miejsca do magazynowania.

Możesz kupić dodatkowy magazyn dla usługi Intune przy użyciu pierwotnej metody zakupu.  Jeśli zakupu dokonano przy użyciu faktury lub karty kredytowej, odwiedź [portal zarządzania subskrypcją](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions).  W przeciwnym razie skontaktuj się ze swoim partnerem lub współpracownikiem ds. sprzedaży.

Wymagania dotyczące miejsca do magazynowania w chmurze są następujące:

-   Wszystkie pliki instalacyjne aplikacji muszą znajdować się w tym samym folderze.
-   Maksymalny rozmiar dowolnego przekazywanego pliku wynosi 2 GB.

## <a name="how-to-create-and-edit-categories-for-apps"></a>Jak tworzyć i edytować kategorie aplikacji 

Kategorie aplikacji mogą ułatwić ich sortowanie, aby użytkownicy końcowi mogli je łatwiej znaleźć w portalu firmy. Do aplikacji można przypisać jedną lub więcej kategorii, na przykład **Aplikacje dla programistów** lub **Aplikacje komunikacji**. Po dodaniu aplikacji do usługi Intune istnieje możliwość wybrania dowolnej kategorii. Tematy dotyczące określonych platform zawierają informacje o dodawaniu aplikacji i przypisywaniu kategorii. Do tworzenia i edytowania własnych kategorii użyj następującej procedury: 

1. Zaloguj się do portalu Azure Portal. 
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**. 
3. W bloku **Intune** wybierz opcję **Zarządzaj aplikacjami**. 
4. W obciążeniu **Aplikacje mobilne** wybierz kolejno opcje **Instalacja** > **Kategorie aplikacji**. 
5. W bloku **Kategorie aplikacji** zostanie wyświetlona lista bieżących kategorii. Wybierz jedno z następujących działań: 
    - **Tworzenie kategorii** — w bloku **Tworzenie kategorii** wprowadź nazwę nowej kategorii. Nazwy można wprowadzić tylko w jednym języku i nie są one tłumaczone przez usługę Intune. Po zakończeniu kliknij przycisk **Utwórz**.
    - **Edytuj kategorię** — dla kategorii na liście wybierz opcję „**...**”. W bloku **Właściwości** można wprowadzić nową nazwę kategorii lub usunąć kategorię.




