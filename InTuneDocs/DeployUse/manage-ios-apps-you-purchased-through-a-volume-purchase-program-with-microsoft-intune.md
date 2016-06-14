---
# required metadata

title: Zarządzanie aplikacjami dla systemu iOS, które zostały zakupione w ramach programu zakupów zbiorczych | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 1dafc28a-7f8b-4fe0-8619-f977c93d1140

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Zarządzanie aplikacjami dla systemu iOS, które zostały zakupione w ramach programu zakupów zbiorczych, w usłudze Microsoft Intune
Niektóre sklepy z aplikacjami umożliwiają zakup wielu licencji dla aplikacji, które mają być uruchamiane w firmie. Dzięki temu można zmniejszyć koszty administracyjne śledzenia wielu zakupionych kopii aplikacji.

Usługa Microsoft Intune ułatwia zarządzanie aplikacjami zakupionymi za pośrednictwem takiego programu przez zaimportowanie informacji o licencji ze sklepu z aplikacjami, śledzenie, ile licencji jest używanych, i zapobieganie instalacji większej liczby kopii aplikacji niż posiadana.

> [!Important]
> Obecnie usługa Intune przypisuje licencje aplikacji iOS VPP do użytkowników, nie urządzeń. W związku z tym użytkownicy końcowi muszą wprowadzić hasło identyfikatora Apple ID, aby zainstalować aplikację.

## Zarządzanie zbiorczo zakupionymi aplikacjami dla urządzeń z systemem iOS
Wiele licencji dla aplikacji z systemem iOS można zakupić za pośrednictwem programu [Apple Volume Purchase Program for Business (VPP)](http://www.apple.com/business/vpp/). Obejmuje to skonfigurowanie konta VPP w witrynie sieci Web firmy Apple i tokenu VPP firmy Apple do usługi Intune.  Następnie można zsynchronizować dane zakupu zbiorczego z usługą Intune i śledzić użycie aplikacji nabytych w ramach zakupu zbiorczego.

## Przed rozpoczęciem
Przed rozpoczęciem należy uzyskać token VPP od firmy Apple i przekazać go do konta usługi Intune. Ponadto należy zrozumieć następujące kwestie:

* Każda organizacja może mieć tylko jedno konto i token VPP.
* Po skojarzeniu konta Apple VPP z usługą Intune nie można już utworzyć skojarzenia kolejnego konta. Z tego powodu bardzo ważne jest, aby więcej niż jedna osoba znała szczegóły używanego konta.
* Jeśli poprzednio korzystano z tokenu VPP w ramach innego produktu, należy wygenerować nowy, aby korzystać z usługi Intune.
* Każdy token jest ważny przez jeden rok.
* Domyślnie usługa Intune przeprowadza synchronizację z usługą Apple VPP dwa razy dziennie. Można jednak w dowolnym momencie zainicjować ręczną synchronizację.
* Po zaimportowaniu tokenu usługi VPP do usługi Intune nie należy importować tego samego tokenu do żadnego innego rozwiązania do zarządzania urządzeniami. Może to spowodować utratę przypisania licencji i rekordów użytkowników.
* Przed rozpoczęciem korzystania z programu VPP dla systemu iOS przy użyciu usługi Intune należy usunąć wszystkie istniejące konta usługi VPP utworzone przy użyciu innych dostawców zarządzania urządzeniami przenośnymi. Usługa Intune nie będzie synchronizować tych kont użytkowników z usługą Intune ze względów bezpieczeństwa. Usługa Intune będzie tylko synchronizować dane z usługą VPP firmy Apple, która została utworzona przez usługę Intune. 

## Aby uzyskać i przekazać token usługi VPP firmy Apple

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) kliknij pozycję **Administrator** &gt; **iOS i Mac OS X** &gt;  **Program zakupów zbiorczych**.

2.  Kliknij link **Konto w usłudze VPP firmy Apple**, a jeśli jeszcze tego nie zrobiono, zarejestruj się w programie Volume Purchase Program for Business. Po utworzeniu nowego konta pobierz odpowiedni token Apple VPP.

3.  Na stronie **Zarządzaj programem VPP (ang. Volume Purchase Program — Program zakupów zbiorczych) firmy Apple** w konsoli usługi Intune i kliknij pozycję **Przekaż token VPP**.

4.  W oknie dialogowym **Przekazywanie tokenu VPP** wpisz lub wklej nazwę tokenu VPP oraz identyfikator Apple ID, a następnie kliknij przycisk **Przekaż**.

5.  W oknie dialogowym ostrzeżenia kliknij pole wyboru, aby wskazać, że rozumiesz, że nie można później zmienić konta na inne konto VPP, a następnie kliknij pozycję **Tak**.

Na stronie **Program zakupów zbiorczych** możesz teraz przeglądać informacje związane z tokenem Apple VPP, w tym datę jego ostatniej aktualizacji, datę wygaśnięcia oraz datę ostatniej synchronizacji z usługą Intune.

Dane przechowywane przez firmę Apple można w dowolnym momencie zsynchronizować z usługą Intune, klikając pozycję **Synchronizuj teraz**.

## Aby przekazać i wdrożyć aplikację nabytą w ramach zakupów zbiorczych

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) kliknij pozycję **Aplikacje** &gt; **Zarządzane oprogramowanie** &gt; **Aplikacje nabyte zbiorczo**.

2.  Postępuj zgodnie z instrukcjami w temacie [Dodawanie aplikacji dla urządzeń przenośnych w usłudze Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md), aby zakończyć przekazywanie, tworzenie i wdrażanie aplikacji.

Podczas wdrażania aplikacji jako **wymaganej** instalacji licencja jest używana przez każdego użytkownika, który instaluje aplikację.

Aby odzyskać licencję, należy zmienić akcję wdrażania na **Odinstaluj**. Licencja zostanie odzyskana po odinstalowaniu aplikacji.

Gdy użytkownik mający kwalifikujące się urządzenie spróbuje zainstalować aplikację VPP po raz pierwszy, zostanie poproszony o dołączenie do programu zakupów zbiorczych firmy Apple. Jest to konieczne, aby instalacja aplikacji mogła być kontynuowana.

> [!TIP]
> W kolumnie **Stan warunków VPP** sprawdź stan akceptacji dla poszczególnych użytkowników aplikacji, dla których wdrożono aplikację.

Jeśli dodatkowe licencje nie są dostępne, wdrożenie zakończy się niepowodzeniem.

## Aby monitorować aplikacje programu VPP firmy Apple
Możesz monitorować, które aplikacje programu VPP zostały wdrożone, oraz liczbę używanych licencji w obszarze roboczym **Aplikacje** w węźle **Zarządzane oprogramowanie** &gt; **Zbiorczo zakupione aplikacje**.

> [!TIP]
> Możesz również sprawdzać stan poszczególnych instalacji aplikacji przy użyciu **filtrów** aplikacji.

### Zobacz też
[Dodawanie aplikacji dla urządzeń przenośnych w usłudze Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md)



<!--HONumber=May16_HO1-->


