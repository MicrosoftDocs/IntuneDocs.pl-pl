---
title: "Zarządzanie aplikacjami systemu iOS nabytymi w ramach zakupów zbiorczych"
description: "Usługa Intune umożliwia zarządzanie aplikacjami zakupionymi w ramach zakupów zbiorczych od firmy Apple przez zaimportowanie informacji o licencji ze sklepu z aplikacjami, śledzenie, ile licencji jest używanych, i zapobieganie instalacji większej liczby kopii aplikacji niż posiadana."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 09/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1dafc28a-7f8b-4fe0-8619-f977c93d1140
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5da29dceb5308eab72e5b24e220586aa739982ea
ms.sourcegitcommit: 1afff0fd464ece84ffea6bc0c71c78215d59e696
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2017
---
# <a name="manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>Zarządzanie aplikacjami dla systemu iOS, które zostały zakupione w ramach programu zakupów zbiorczych, w usłudze Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Sklep z aplikacjami systemu iOS umożliwia zakup wielu licencji dla aplikacji, które mają być uruchamiane w firmie. Dzięki temu można zmniejszyć koszty administracyjne śledzenia wielu zakupionych kopii aplikacji.

Usługa Microsoft Intune ułatwia zarządzanie aplikacjami zakupionymi za pośrednictwem tego programu przez zaimportowanie informacji o licencji ze sklepu z aplikacjami, śledzenie, ile licencji jest używanych, i zapobieganie instalacji większej liczby kopii aplikacji niż posiadana.

> [!Important]
> Obecnie usługa Intune przypisuje licencje aplikacji z systemem iOS zakupionymi w ramach programu zakupów zbiorczych Apple Volume Purchase Program for Business (VPP) do użytkowników, nie urządzeń. W związku z tym użytkownicy muszą wprowadzić hasło identyfikatora Apple ID, aby zainstalować aplikację.
> Program Apple Volume Purchase Program for Education oraz aplikacje B2B nie są obsługiwane w tym wydaniu.

## <a name="manage-volume-purchased-apps-for-ios-devices"></a>Zarządzanie zbiorczo zakupionymi aplikacjami dla urządzeń z systemem iOS
Wiele licencji dla aplikacji z systemem iOS można zakupić za pośrednictwem programu [Apple Volume Purchase Program for Business (VPP)](http://www.apple.com/business/vpp/). Obejmuje to skonfigurowanie konta VPP w witrynie sieci Web firmy Apple i przekazanie tokenu VPP firmy Apple do usługi Intune.  Następnie można zsynchronizować dane zakupu zbiorczego z usługą Intune i śledzić użycie aplikacji nabytych w ramach zakupu zbiorczego.

## <a name="before-you-start"></a>Przed rozpoczęciem
Przed rozpoczęciem należy uzyskać token VPP od firmy Apple i przekazać go do konta usługi Intune. Ponadto należy zrozumieć następujące kwestie:

* Usługa Intune obsługuje dodawanie maksymalnie 256 tokenów usługi VPP.
* Jeśli poprzednio korzystano z tokenu VPP w ramach innego produktu, należy wygenerować nowy, aby korzystać z usługi Intune.
* Każdy token jest ważny przez jeden rok.
* Domyślnie usługa Intune przeprowadza synchronizację z usługą Apple VPP dwa razy dziennie. W dowolnym momencie można uruchomić ręczną synchronizację.
* Po zaimportowaniu tokenu VPP do usługi Intune nie należy importować tego samego tokenu do żadnego innego rozwiązania do zarządzania urządzeniami. Może to spowodować utratę przypisania licencji i rekordów użytkowników.
* Przed rozpoczęciem korzystania z programu VPP dla systemu iOS przy użyciu usługi Intune należy usunąć wszystkie istniejące konta usługi VPP utworzone przy użyciu innych dostawców zarządzania urządzeniami przenośnymi. Usługa Intune nie będzie synchronizować tych kont użytkowników z usługą Intune ze względów bezpieczeństwa. Usługa Intune będzie tylko synchronizować dane z usługi VPP firmy Apple, która została utworzona przez usługę Intune.
* Aplikacje usługi VPP systemu iOS można wdrażać tylko na urządzeniach użytkowników, które zostały zarejestrowane za pomocą protokołu Device Enrollment Protocol (DEP), jeśli została skonfigurowana koligacja użytkownika dla urządzenia.

## <a name="to-get-and-upload-an-apple-vpp-token"></a>Aby uzyskać i przekazać token usługi VPP firmy Apple

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) wybierz pozycję **Administrator** &gt; **iOS i Mac OS X** &gt; **Volume Purchase Program**.

2.  Wybierz link **Konto w usłudze VPP firmy Apple**. Jeśli jeszcze tego nie zrobiono, zarejestruj się w programie Volume Purchase Program for Business. Po zarejestrowaniu się pobierz token Apple VPP dla swojego konta.

3.  Na stronie **Zarządzaj programem VPP (ang. Volume Purchase Program — Program zakupów zbiorczych) firmy Apple** w konsoli usługi Intune wybierz pozycję **Przekaż token VPP**.

4.  W oknie dialogowym **Przekazywanie tokenu VPP** wpisz lub wklej nazwę tokenu VPP oraz identyfikator Apple ID, a następnie wybierz pozycję **Przekaż**.

5.  W oknie dialogowym ostrzeżenia zaznacz pole wyboru, aby wskazać, że rozumiesz, że nie można później zmienić konta na inne konto VPP, a następnie wybierz pozycję **Tak**.

Na stronie **Program zakupów zbiorczych** możesz teraz przeglądać informacje związane z tokenem Apple VPP, w tym datę jego ostatniej aktualizacji, datę wygaśnięcia oraz datę ostatniej synchronizacji z usługą Intune.

Dane przechowywane przez firmę Apple można w dowolnym momencie zsynchronizować z usługą Intune, wybierając pozycję **Synchronizuj teraz**.

## <a name="to-deploy-a-volume-purchased-app"></a>Aby wdrożyć aplikację nabytą w ramach zakupów zbiorczych

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) wybierz kolejno pozycje **Aplikacje** &gt; **Aplikacje** &gt; **Aplikacje kupione w ramach zakupów zbiorczych**. Ta lista zawiera wszystkie aplikacje, które zostały zsynchronizowane z poziomu usługi VPP firmy Apple.

2.  Wybierz aplikację, którą chcesz wdrożyć, wybierz pozycję **Zarządzaj wdrożeniem**, a następnie postępuj zgodnie z instrukcjami w temacie [Wdrażanie aplikacji w usłudze Microsoft Intune](deploy-apps-in-microsoft-intune.md), aby zakończyć przekazywanie, tworzenie i wdrażanie aplikacji.

> [!TIP]
> Musisz wybrać akcję wdrożenia **Wymagane**. Instalacje Dostępne nie są obecnie obsługiwane. Ponadto aplikację można wdrażać tylko dla grup użytkowników.

Podczas wdrażania aplikacji jako instalacji **wymaganej** licencja jest używana przez każdego użytkownika, który instaluje aplikację.

Aby odzyskać licencję, należy zmienić akcję wdrażania na **Odinstaluj**. Licencja zostanie odzyskana po odinstalowaniu aplikacji.

Gdy użytkownik mający kwalifikujące się urządzenie spróbuje zainstalować aplikację VPP po raz pierwszy, zostanie poproszony o dołączenie do programu zakupów zbiorczych firmy Apple. Jest to konieczne, aby instalacja aplikacji mogła być kontynuowana.

Jeśli dodatkowe licencje nie są dostępne, wdrożenie zakończy się niepowodzeniem.

## <a name="to-monitor-apple-vpp-apps"></a>Aby monitorować aplikacje programu VPP firmy Apple
W obszarze roboczym **Aplikacje** w węźle **Aplikacje kupione w ramach zakupów zbiorczych** możesz monitorować, które aplikacje programu VPP zostały wdrożone oraz ile licencji jest używanych.

> [!TIP]
> Możesz również sprawdzać stan poszczególnych instalacji aplikacji przy użyciu **filtrów** aplikacji.

### <a name="see-also"></a>Zobacz także
[Wdrażanie aplikacji w usłudze Microsoft Intune](deploy-apps-in-microsoft-intune.md)
