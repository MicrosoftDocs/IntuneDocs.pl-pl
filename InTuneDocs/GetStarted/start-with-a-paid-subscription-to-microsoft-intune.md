---
title: "Przewodnik Szybki start dotyczący usługi Intune | Microsoft Intune"
description: "Wymogi i wymagania wstępne dotyczące korzystania z subskrypcji usługi Intune"
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d158503c-1276-422b-ab81-5f66c1cd7e7a
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 13ff2feb5918725306ebee96cdbf8e5212066ddc
ms.openlocfilehash: c8984d37296fc79eb67b5604ab735b1be47d4e11


---


# Przewodnik Szybki start dotyczący usługi Intune
Ten przewodnik Szybki start zawiera opis etapów konfigurowania płatnej subskrypcji usługi Microsoft Intune w celu szybkiego i łatwego zarządzania urządzeniami przenośnymi oraz komputerami z systemem Windows używanymi przez organizację. Można wykonać kolejno poszczególne kroki lub pominąć kroki, które nie mają zastosowania do określonego środowiska lub potrzeb biznesowych.

>[!NOTE]
>Ten artykuł koncentruje się na konfigurowaniu usługi Intune jako usługi autonomicznej. Alternatywnie, jeśli używasz obecnie programu Microsoft System Center Configuration Manager do zarządzania komputerami i serwerami, możesz [rozszerzyć program Configuration Manager, aby zarządzał urządzeniami mobilnymi](https://technet.microsoft.com/library/jj884158.aspx). Można to zrobić, łącząc usługę Intune z programem Configuration Manager w ramach hybrydowego wdrożenia zarządzania urządzeniami przenośnymi (MDM).

W tym przewodniku Szybki start uwzględniono wiele kroków, które zostały opisane w [przewodniku dotyczącym oceny usługi Intune](/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune). Jednak po ukończeniu oceny i przygotowaniu się do rozpoczęcia zarządzania urządzeniami przenośnymi należy spełnić kilka dodatkowych wymagań:

-   Zsynchronizowanie lokalnych kont usługi Active Directory z usługami Intune i Azure Active Directory.

-   Zaktualizowanie domeny publicznej i rekordów usługi DNS u rejestratora domen.

-   Dostosowywanie funkcji usługi Intune do użytku produkcyjnego.

>[!TIP]
>W przypadku zakupu co najmniej 150 licencji na usługę Microsoft Intune w uprawniającym planie można skorzystać z asysty *centrum rozwiązania FastTrack* — usługi współpracy ze specjalistami firmy Microsoft w celu przygotowania środowiska usługi Intune. Zobacz [Opis asysty serwisowej dla usługi Microsoft Intune](https://technet.microsoft.com/library/mt228265.aspx).


## Przed rozpoczęciem
Użyj tego podręcznika, gdy rozpoczynasz korzystanie z subskrypcji płatnej, po przygotowaniu się do wdrożenia usługi Intune i wprowadzenia zmian w istniejącej infrastrukturze sieci. Zadania te mogą obejmować tylko dodanie lub zaktualizowanie wewnętrznych i zewnętrznych rekordów DNS, jak i synchronizowanie istniejących kont użytkowników usługi Active Directory z usługą Azure Active Directory. Niezależnie od tego, z których narzędzi do zarządzania urządzeniami przenośnymi usługi Intune korzystasz, musisz starannie zaplanować interakcję usługi Intune z istniejącymi elementami sieci i usługami sieciowymi. W szczególności należy sprawdzić następujące kwestie:

-   **Metoda zarządzania tożsamościami użytkowników**: w przypadku większości średnich i dużych organizacji najlepsza i najwygodniejsza metoda zarządzania tożsamościami użytkowników w usłudze Intune to połączenie istniejących usług katalogowych z usługą Intune za pośrednictwem usługi Azure Active Directory. Dotyczy to zwłaszcza przypadków korzystania z innych usług firmy Microsoft w chmurze, takich jak Office 365 lub Exchange Online. Synchronizacja istniejących kont użytkowników przy użyciu narzędzia [Microsoft Azure Active Directory Connect](https://www.microsoft.com/download/details.aspx?id=47594) to szybka i łatwa metoda łączenia lokalnej usługi Active Directory z usługą Azure Active Directory oraz konfigurowania logowania jednokrotnego użytkowników.

-   **Wpływ na system DNS**: jeśli chcesz korzystać z własnej nazwy domeny zamiast domyślnej domeny onmicrosoft.com otrzymanej podczas rejestrowania się w celu skorzystania z usługi Intune, musisz zaktualizować niektóre rekordy publiczne DNS. Rekordy DNS należy zaktualizować, aby umożliwić urządzeniom przenośnym odnalezienie usługi Intune, zapewnić prawidłowe funkcjonowanie usługi zarządzania dla subskrypcji i poprawnie zarządzać wszystkimi urządzeniami używanymi przez organizację.

## Należy przygotować następujące zasoby
Możemy zaczynać? Do rozpoczęcia pracy z subskrypcją płatną usługi Intune potrzebne są następujące zasoby:

### Urządzenie z przeglądarką sieci Web obsługującą program Silverlight
To urządzenie będzie niezbędne do uzyskania dostępu do konsoli administracyjnej usługi Intune, w której można zarządzać urządzeniami, aplikacjami i zasadami. Przeglądarka sieci Web będzie również niezbędna do uzyskania dostępu do internetowego portalu firmy usługi Intune, jeśli dostęp do aplikacji portalu firmy nie będzie uzyskiwany przy użyciu urządzenia przenośnego. Aby ułatwić korzystanie z przeglądarki, można użyć ustawienia „tryb prywatny” w tej samej przeglądarce, która jest używana do administrowania usługą Intune (na przykład w przeglądarce Internet Explorer można kliknąć opcje **Narzędzia** &gt; **Przeglądanie InPrivate**).

>[!TIP]
>Ze względu na to wymaganie nie można uzyskać dostępu do konsoli administracyjnej usługi Intune przy użyciu przeglądarki Microsoft Edge.


### Certyfikaty dla urządzeń przenośnych
Jeśli przy użyciu usługi Intune będziesz zarządzać urządzeniami z systemem iOS lub Windows Phone, potrzebujesz certyfikatów i kont umożliwiających pobranie tych certyfikatów. Dodatkowe certyfikaty nie są wymagane do zarządzania urządzeniami z systemem Android.

- Żaden certyfikat nie jest wymagany w przypadku użytkowników systemu **Windows Phone 8.1**, którzy instalują aplikację Portal firmy pobraną ze Sklepu. Jednak [certyfikat Symantec podpisywania kodu](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do) jest wymagany w przypadku systemu **Windows Phone 8.0** oraz w przypadku wdrażania aplikacji portalu firmy za pośrednictwem usługi Intune na urządzeniach z systemem Windows Phone 8.1.

>[!NOTE]
>W tym przewodniku Szybki start założono, że użytkownicy pobierają aplikację Portal firmy ze Sklepu na urządzeniach z systemem Windows Phone 8.1 lub nowszym. Aby uzyskać informacje na temat obsługi systemu Windows Phone 8.0, zobacz [Konfigurowanie zarządzania systemem Windows Phone 8.0 przy użyciu usługi Microsoft Intune](/Intune/deploy-use/set-up-windows-phone-8.0-management-with-microsoft-intune).

- Żaden certyfikat nie jest wymagany dla **komputerów z systemem Windows** lub **urządzeń z systemem Windows RT** w przypadku rejestrowania komputerów z systemem Windows jako urządzeń lub [instalowania klienta komputera z systemem Windows dla usługi Microsoft Intune](/intune/deploy-use/install-the-windows-pc-client-with-microsoft-intune).

- W przypadku urządzeń z systemem **iOS** lub **Mac OS X** należy uzyskać certyfikat usługi Apple Push Notification Service od firmy Apple w sposób opisany w kroku 3 w artykule [Konfigurowanie zarządzania systemem iOS i komputerami Mac przy użyciu usługi Microsoft Intune](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).

## Następne kroki
Teraz możesz skorzystać z przewodnika Szybki start dotyczącego usługi Intune!

>[!div class="step-by-step"]
[**Logowanie się do usługi Intune** &rarr;](start-with-a-paid-subscription-to-microsoft-intune-step-1.md)



<!--HONumber=Aug16_HO2-->


