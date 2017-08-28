---
title: "Jak dodawać aplikacje do usługi Microsoft Intune"
titleSuffix: Intune on Azure
description: "Te procedury ułatwiają przygotowanie aplikacji do usługi Intune w celu przypisania do użytkowników i urządzeń. \""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/17/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 14f2ac5b25cfe3e688363a21775872baaa9ff89a
ms.sourcegitcommit: 4034ac474bfed358270a32459a2cf2fe02f44e45
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/15/2017
---
# <a name="how-to-add-an-app-to-microsoft-intune"></a>Jak dodawać aplikacje do usługi Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Aby można było zarządzać aplikacjami oraz przypisać je do użytkowników, należy dodać je do usługi Intune. Usługa Intune obsługuje szeroką gamę różnych typów aplikacji i opcje dla poszczególnych typów mogą się różnić.

Usługa Intune pozwala dodawać i przypisywać następujące typy aplikacji:

![Typy aplikacji obsługiwane przez usługę Intune](./media/app-types.png)

Obsługiwane są następujące platformy:

- Aplikacje ze sklepu dla systemu Android
- Aplikacje biznesowe (LOB) dla systemu Android
- Aplikacje ze sklepu dla systemu iOS
- Aplikacje biznesowe (LOB) dla systemu iOS
- Aplikacje sieci Web
- Aplikacje ze sklepu dla systemu Windows Phone 8.1
- Aplikacje biznesowe dla systemu Windows Phone (pliki .xap)
- Aplikacje ze sklepu dla systemu Windows
- Aplikacje biznesowe dla systemu Windows (tylko pliki .msi)

>[!TIP]
> Aplikacja biznesowa (lub LOB) to aplikacja, która nie jest instalowana ze sklepu z aplikacjami, ale z pliku instalacyjnego aplikacji. Na przykład w celu zainstalowania aplikacji LOB dla systemu iOS należy dodać plik archiwalny aplikacji (z rozszerzeniem .ipa). Zazwyczaj są to aplikacje, które zostały napisane we własnym zakresie.

## <a name="before-you-start"></a>Przed rozpoczęciem

Przed rozpoczęciem dodawania i przypisywania aplikacji należy wziąć pod uwagę poniższe kwestie.

- Kiedy dodajesz i przypisujesz aplikację ze sklepu, użytkownicy końcowi muszą mieć konto w danym sklepie, aby móc zainstalować daną aplikację.
- Niektóre przypisywane aplikacje lub elementy mogą być zależne od wbudowanych aplikacji systemu iOS. Na przykład, jeśli przypisujesz książkę ze sklepu iOS, w urządzeniu musi być zainstalowana aplikacja iBooks. W przypadku usunięcia wbudowanej aplikacji iBooks nie ma możliwości użycia usługi Intune do jej przywrócenia.

## <a name="cloud-storage-space"></a>Miejsce do magazynowania w chmurze
Wszystkie aplikacje tworzone przy użyciu instalatora oprogramowania (na przykład aplikacje biznesowe) zostają spakowane i przekazane do magazynu w chmurze usługi Intune. Subskrypcja próbna usługi Intune obejmuje 2 GB magazynu opartego na chmurze, który jest używany do przechowywania zarządzanych aplikacji i aktualizacji. Pełna subskrypcja obejmuje 20 GB miejsca do magazynowania.

Możesz kupić dodatkowy magazyn dla usługi Intune przy użyciu pierwotnej metody zakupu.  Jeśli zakupu dokonano przy użyciu faktury lub karty kredytowej, odwiedź [portal zarządzania subskrypcją](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions).  W przeciwnym razie skontaktuj się ze swoim partnerem lub współpracownikiem ds. sprzedaży.

Wymagania dotyczące miejsca do magazynowania w chmurze są następujące:

-   Wszystkie pliki instalacyjne aplikacji muszą znajdować się w tym samym folderze.
-   Maksymalny rozmiar dowolnego przekazywanego pliku wynosi 2 GB.

## <a name="how-to-create-and-edit-categories-for-apps"></a>Jak tworzyć i edytować kategorie aplikacji

Kategorie aplikacji mogą ułatwić ich sortowanie, aby użytkownicy mogli je łatwiej znaleźć w portalu firmy. Do aplikacji można przypisać jedną lub więcej kategorii, na przykład **Aplikacje dla programistów** lub **Aplikacje komunikacji**.
Po dodaniu aplikacji do usługi Intune istnieje możliwość wybrania dowolnej kategorii. Tematy dotyczące określonych platform zawierają informacje o dodawaniu aplikacji i przypisywaniu kategorii. Do tworzenia i edytowania własnych kategorii użyj następującej procedury:

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz pozycję **Aplikacje mobilne**.
4. W obciążeniu **Aplikacje mobilne** wybierz kolejno opcje **Instalacja** > **Kategorie aplikacji**.
5. W bloku **Kategorie aplikacji** zostanie wyświetlona lista bieżących kategorii. Wybierz jedno z następujących działań:
    - **Tworzenie kategorii** — w bloku **Tworzenie kategorii** wprowadź nazwę nowej kategorii. Nazwy można wprowadzić tylko w jednym języku i nie są one tłumaczone przez usługę Intune. Po zakończeniu kliknij przycisk **Utwórz**.
    - **Edytuj kategorię** — dla kategorii na liście wybierz opcję „**...**”. W bloku **Właściwości** można wprowadzić nową nazwę kategorii lub usunąć kategorię.


## <a name="apps-added-automatically-by-intune"></a>Aplikacje dodawane automatycznie przez usługę Intune

Wcześniej usługa Intune zawierała kilka wbudowanych aplikacji, które można było szybko przypisać. Na podstawie Twojej opinii usunęliśmy tę listę, a wbudowane aplikacje nie będą już dla Ciebie widoczne.
Jeśli jednak przypisano już jakiekolwiek wbudowane aplikacje, będą one nadal widoczne na liście aplikacji. W razie potrzeby te aplikacje mogą pozostać przypisane.
W nowszej wersji planujemy dodać łatwiejszy sposób wybierania i przypisywania wbudowanych aplikacji z portalu usługi Intune.

## <a name="next-steps"></a>Następne kroki

Wybierz jeden z poniższych tematów, aby dowiedzieć się, jak dodawać aplikacje dla każdej platformy w usłudze Intune:

- [Aplikacje ze sklepu dla systemu Android](store-apps-android.md)
- [Aplikacje LOB dla systemu Android](lob-apps-android.md)
- [Aplikacje ze sklepu dla systemu iOS](store-apps-ios.md)
- [Aplikacje LOB dla systemu iOS](lob-apps-ios.md)
- [Aplikacje sieci Web (dla wszystkich platform)](web-app.md)
- [Aplikacje ze sklepu dla systemu Windows Phone 8.1](store-apps-windows-phone-8-1.md)
- [Aplikacje LOB dla systemu Windows Phone](lob-apps-windows-phone.md)
- [Aplikacje ze sklepu dla systemu Windows](store-apps-windows.md)
- [Aplikacja LOB dla systemu Windows](lob-apps-windows.md)
- [Aplikacje pakietu Office 365 dla systemu Windows 10](apps-add-office365.md)

