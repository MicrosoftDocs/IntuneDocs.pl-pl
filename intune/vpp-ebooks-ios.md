---
title: "Zarządzanie książkami elektronicznymi dla systemu iOS nabytymi w ramach zakupów zbiorczych"
titleSuffix: Intune on Azure
description: "Informacje o synchronizowaniu książek zakupionych w ramach zakupów zbiorczych w sklepie z aplikacjami dla systemu iOS z usługą Intune oraz o zarządzaniu ich użyciem i jego śledzeniu."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/17/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5617074-2384-4812-b913-dc94f64c0818
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 43ab9e906f05a069b1399ab53a4861d7289b7024
ms.sourcegitcommit: 6a089eb45ea3fb18ae0b2dac96683466f52f95bf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/18/2017
---
# <a name="how-to-manage-ios-ebooks-you-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>Jak zarządzać w usłudze Microsoft Intune książkami elektronicznymi dla systemu iOS, które zostały zakupione w ramach programu zakupów zbiorczych


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Program Apple Volume Purchase Program (VPP) umożliwia zakup wielu licencji dla książki, którą chcesz rozpowszechnić wśród użytkowników w firmie. Możesz rozpowszechniać książki ze sklepu dla firm i sklepu dla instytucji edukacyjnych.

Usługa Microsoft Intune wspomaga synchronizację, zarządzanie i przypisywanie książek, które zostały zakupione w ramach tego programu. Można zaimportować informacje o licencjach ze sklepu i śledzić, ile licencji jest używanych.

Procedury służące do zarządzania książkami są podobne do [zarządzania aplikacjami programu VPP](vpp-apps-ios.md).

## <a name="manage-volume-purchased-books-for-ios-devices"></a>Zarządzanie zbiorczo zakupionymi książkami dla urządzeń z systemem iOS
Wiele licencji dla książek z systemem iOS można zakupić za pośrednictwem programu [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/) lub [Apple Volume Purchase Program for Education](http://volume.itunes.apple.com/us/store). Ten proces obejmuje skonfigurowanie konta programu VPP firmy Apple w witrynie sieci Web firmy Apple i przekazanie tokenu VPP firmy Apple do usługi Intune.  Następnie można zsynchronizować dane zakupu zbiorczego z usługą Intune i śledzić użycie książek nabytych w ramach zakupu zbiorczego.

## <a name="before-you-start"></a>Przed rozpoczęciem
Przed rozpoczęciem należy uzyskać token VPP od firmy Apple i przekazać go do konta usługi Intune. Dodatkowo:

* Z Twoim kontem usługi Intune można skojarzyć maksymalnie 256 tokenów VPP.
* Jeśli poprzednio korzystano z tokenu VPP w ramach innego produktu, należy wygenerować nowy, aby korzystać z usługi Intune.
* Każdy token jest ważny przez jeden rok.
* Domyślnie usługa Intune przeprowadza synchronizację z usługą Apple VPP dwa razy dziennie. W dowolnym momencie można uruchomić ręczną synchronizację.
* Po zaimportowaniu tokenu VPP do usługi Intune nie należy importować tego samego tokenu do żadnego innego rozwiązania do zarządzania urządzeniami. Może to spowodować utratę przypisania licencji i rekordów użytkowników.
* Przed rozpoczęciem korzystania z książek dla systemu iOS przy użyciu usługi Intune należy usunąć wszystkie istniejące konta użytkowników programu VPP utworzone przy użyciu innych dostawców zarządzania urządzeniami mobilnymi. Usługa Intune nie synchronizuje tych kont użytkowników z usługą Intune ze względów bezpieczeństwa. Usługa Intune synchronizuje tylko dane z usługi VPP firmy Apple, która została utworzona przez usługę Intune.
* Aby możliwe było przypisanie książki do urządzenia, musi na nim być zainstalowana wbudowana aplikacja iBooks. Jeśli tak nie jest, użytkownik końcowy musi ponownie zainstalować aplikację w celu czytania książki. Obecnie nie jest możliwe przywracanie usuniętych wbudowanych aplikacji przy użyciu usługi Intune.
* Można przypisywać tylko książki z witryny programu Apple Volume Purchase Program. Nie można przekazać, a następnie przypisać książek utworzonych w swojej firmie.
* Obecnie nie można przypisywać książek do kategorii użytkownika końcowego w taki sam sposób, jak przypisuje się aplikacje.
* Nie można odzyskać licencji, gdy książka została już przypisana.
* Gdy użytkownik mający kwalifikujące się urządzenie spróbuje zainstalować książkę VPP po raz pierwszy, zostanie poproszony o dołączenie do programu Apple Volume Purchase Program. Licencje można również przypisać do grup zabezpieczeń z zarządzanymi identyfikatorami Apple ID. Jeśli to zrobisz, to podczas instalacji książki użytkownicy nie będą monitowani o podanie identyfikatorów Apple ID.

## <a name="to-get-and-upload-an-apple-vpp-token"></a>Aby uzyskać i przekazać token usługi VPP firmy Apple

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz pozycję **Aplikacje mobilne**.
1.  W obciążeniu **Aplikacje mobilne** wybierz kolejno pozycje **Konfiguracja** > **Tokeny programu VPP dla systemu iOS**.
2.  W bloku listy tokenów programu VPP kliknij pozycję **Dodaj**.
3.  W bloku **Nowy token programu VPP** określ następujące informacje:
    - **Plik tokenu programu VPP** — zapewnia, że jesteś zarejestrowanym uczestnikiem programu Volume Purchase Program for Business lub Volume Purchase Program for Education. Następnie pobierz token VPP firmy Apple dla swojego konta i wybierz go tutaj.
    - **Identyfikator firmy Apple** — wprowadź identyfikator firmy Apple dla konta skojarzonego z programem zakupów zbiorczych.
    - **Typ konta programu VPP** — wybierz opcję **Biznes** lub **Edukacja**.
4. Gdy wszystko będzie gotowe, kliknij pozycję **Przekaż**.

Token zostanie wyświetlony na liście w bloku tokenów.


Dane przechowywane przez firmę Apple można w dowolnym momencie zsynchronizować z usługą Intune, wybierając pozycję **Synchronizuj teraz**.

## <a name="to-assign-a-volume-purchased-app"></a>Wdrażanie aplikacji nabytej w ramach programu zakupów zbiorczych

1. W obciążeniu **Książki elektroniczne** wybierz opcję **Zarządzaj** > **Wszystkie książki elektroniczne**.
2. W bloku listy książek wybierz książkę, którą chcesz przypisać, a następnie wybierz kolejno opcje „**...**” > **Przypisz grupy**.
3. W bloku <*nazwa książki*> — **Przypisane grupy** wybierz kolejno pozycje **Zarządzaj** > **Przypisane grupy**.
4. Wybierz pozycję **Przypisz grupy**, a następnie w bloku **Wybierz grupy** wybierz grupy użytkowników usługi Azure AD, do których chcesz przypisać książkę. Grupy urządzeń nie są obecnie obsługiwane.
Wybierz akcję przypisania **Dostępne** lub **Wymagane**. 
5. Gdy wszystko będzie gotowe, wybierz pozycję **Zapisz**.

## <a name="next-steps"></a>Następne kroki

Informacje przydatne do monitorowania przypisań książek znajdują się w artykule [Monitorowanie informacji o aplikacji ](apps-monitor.md).






