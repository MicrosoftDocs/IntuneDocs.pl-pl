---
title: Co to jest Microsoft Intune
description: Dowiedz się, w jaki sposób usługa Intune pełni rolę składnika zarządzania urządzeniami przenośnymi (MDM, mobile device management) i zarządzania aplikacjami mobilnymi (MAM, mobile app management) rozwiązania Enterprise Mobility + Security oraz jak pomaga w ochronie danych firmy.
keywords: co to jest usługa Intune
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 03/01/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3b4e778d-ac13-4c23-974f-5122f74626bc
ms.reviewer: pmay
ms.suite: ems
ms.custom: ''
ms.openlocfilehash: 6f92cb350a69aeb600f1d48e9bdb0b22a623cb52
ms.sourcegitcommit: 401cedcd7acc6cb3a6f18d4679bdadb0e0cdf443
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/28/2018
ms.locfileid: "32046405"
---
# <a name="what-is-intune"></a>Co to jest usługa Intune?

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Usługa Intune to oparta na chmurze usługa z zakresu zarządzania mobilnością w przedsiębiorstwie (EMM, enterprise mobility management) ułatwiająca pracownikom utrzymanie produktywności przy jednoczesnej ochronie danych firmy. Usługa Intune umożliwia:
* zarządzanie urządzeniami przenośnymi używanymi przez pracowników do uzyskiwania dostępu do danych firmowych,
* zarządzanie aplikacjami mobilnymi używanymi przez pracowników,
* chronienie danych firmowych poprzez kontrolowanie sposobu, w jaki pracownicy uzyskują do nich dostęp i udostępniają je,
* zapewnienie zgodności urządzeń i aplikacji z wymaganiami firmy dotyczącymi bezpieczeństwa.

## <a name="common-business-problems-that-intune-helps-solve"></a>Typowe problemy biznesowe, które pomaga rozwiązywać usługa Intune

* [Zabezpieczanie lokalnej poczty e-mail i danych na potrzeby uzyskiwania dostępu przez urządzenia przenośne](common-scenarios.md#protecting-your-on-premises-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices)
* [Zabezpieczanie poczty e-mail i danych w usłudze Office 365 na potrzeby uzyskiwania bezpiecznego dostępu przez urządzenia przenośne](common-scenarios.md#protecting-your-office-365-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices)
* [Wydawanie firmowych telefonów pracownikom](common-scenarios.md#issue-corporate-owned-phones-to-your-employees)
* [Oferowanie programu „Przynieś własne urządzenie” (BYOD, bring your own device) lub urządzeń osobistych wszystkim pracownikom](common-scenarios.md#offer-a-bring-your-own-device-program-to-all-employees)
* [Umożliwianie pracownikom bezpiecznego dostępu do usługi Office 365 z niezarządzanego kiosku publicznego](common-scenarios.md#enable-your-employees-to-securely-access-office-365-from-an-unmanaged-public-kiosk)
* [Wydawanie wspólnych tabletów do ograniczonego użytku pracownikom wykonującym zadania](common-scenarios.md#issue-limited-use-shared-tablets-to-your-employees)


## <a name="how-does-intune-work"></a>Jak działa usługa Intune?
Usługa Intune jest składnikiem pakietu Enterprise Mobility + Security (EMS), który zarządza urządzeniami przenośnymi i aplikacjami. Usługa ta jest ściśle zintegrowana z innymi składnikami pakietu EMS, np. usługą Azure Active Directory (Azure AD), która umożliwia kontrolowanie tożsamości i dostępu, oraz usługą Azure Information Protection na potrzeby ochrony danych. Używając jej wraz z usługą Office 365, możesz zapewnić produktywność pracowników na wszystkich urządzeniach, z których korzystają, przy jednoczesnym zachowaniu bezpieczeństwa informacji należących do organizacji.

![Obraz architektury usługi Intune](./media/intunearch_sm.png)

Wyświetl [powiększony](./media/intunearchitecture.svg) diagram architektury usługi Intune.

Sposób użycia funkcji zarządzania urządzeniami i aplikacjami usługi Intune oraz ochrony danych pakietu EMS zależy od [problemu biznesowego, który próbujesz rozwiązać](#common-business-problems-that-intune-helps-solve). Przykład:
* Funkcja zarządzania urządzeniami znajdzie zastosowanie przy tworzeniu puli urządzeń współdzielonych przez pracowników zmianowych w sklepie detalicznym.
* Funkcja zarządzania aplikacjami i ochrona danych jest przydatna w sytuacji, gdy pracownicy uzyskują dostęp do danych firmowych za pomocą urządzeń osobistych (Przynieś własne urządzenie).  
* Będziesz polegać na wszystkich tych technologiach, jeśli wydajesz telefony firmowe pracownikom przetwarzającym informacje.

## <a name="intune-device-management-explained"></a>Objaśnienie funkcji zarządzania urządzeniami usługi Intune
Funkcja zarządzania urządzeniami usługi Intune działa przy użyciu protokołów lub interfejsów API, które są dostępne w systemach operacyjnych urządzeń przenośnych. Obejmuje takie zadania jak:
* Rejestrowanie urządzeń do zarządzania, aby dział IT miał spis urządzeń uzyskujących dostęp do usług firmowych
* Konfigurowanie urządzeń w celu upewnienia się, że spełniają standardy firmy dotyczące kondycji i zabezpieczeń
* Dostarczanie certyfikatów i profilów sieci Wi-Fi/VPN w celu uzyskania dostępu do usług firmowych
* Raportowanie i pomiar zgodności urządzenia ze standardami firmy
* Usuwanie danych firmowych z zarządzanych urządzeń  

Niektórzy sądzą, że **kontrolowanie dostępu do danych firmowych** jest funkcją zarządzania urządzeniami. Nie należy myśleć o tym w ten sposób, ponieważ to nie jest funkcja dostarczana przez system operacyjny urządzeń przenośnych. Jest to raczej funkcja dostarczana przez dostawcę tożsamości. W tym przypadku dostawcą tożsamości jest usługa Azure Active Directory (Azure AD) — system zarządzania dostępem i tożsamością firmy Microsoft.  

Usługa Intune integruje się z usługą Azure AD, aby udostępnić szeroką gamę scenariuszy kontroli dostępu. Na przykład można wymagać, aby przed uzyskaniem dostępu do usług firmowych, takich jak program Exchange, urządzenie przenośne spełniało standardy firmy zdefiniowane w usłudze Intune. Podobnie można zablokować dostęp do usług firmowych określonemu zestawowi aplikacji mobilnych. Na przykład można zablokować usługę Exchange Online tak, aby dostęp do niej był możliwy tylko za pomocą programu Outlook lub Outlook Mobile.

## <a name="intune-app-management-explained"></a>Objaśnienie funkcji zarządzania aplikacjami usługi Intune
Zarządzanie aplikacjami obejmuje następujące możliwości:
* Przypisywanie aplikacji mobilnych dla pracowników
* Konfigurowanie standardowych ustawień aplikacji, które są używane po jej uruchomieniu
* Kontrolowanie sposobu używania i udostępniania danych firmowych w aplikacjach mobilnych
* Usuwanie danych firmowych z aplikacji mobilnych   
* Aktualizowanie aplikacji
* Raportowanie dotyczące spisu aplikacji mobilnych
* Śledzenie użycia aplikacji mobilnej

Termin „zarządzanie aplikacjami mobilnymi” jest często używany jako oznaczenie jednej z powyższych czynności lub konkretnej ich kombinacji. Szczególnie powszechne jest łączenie koncepcji konfiguracji aplikacji z koncepcją zabezpieczania danych firmowych w aplikacjach mobilnych. Wynika to z faktu, że niektóre aplikacje mobilne uwidaczniają ustawienia, które umożliwiają skonfigurowanie funkcji zabezpieczeń danych.

Omawiając konfigurację aplikacji i usługę Intune, odnosimy się w szczególności do technologii takich jak [konfiguracja aplikacji zarządzanych w systemie iOS](https://developer.apple.com/library/content/samplecode/sc2279/Introduction/Intro.html).

Korzystając z usługi Intune w połączeniu z innymi usługami pakietu EMS, możesz zapewnić swojej organizacji lepsze bezpieczeństwo aplikacji mobilnych niż to dostarczane przez system operacyjny urządzeń przenośnych i same aplikacje mobilne za pośrednictwem konfiguracji aplikacji. Aplikacja zarządzana za pomocą pakietu EMS ma dostęp do szerszego zakresu zabezpieczeń aplikacji mobilnych i danych, który obejmuje:

* [Logowanie jednokrotne](https://docs.microsoft.com/azure/active-directory/active-directory-appssoaccess-whatis)  
*   [Uwierzytelnianie wieloskładnikowe](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication)
* [Warunkowy dostęp do aplikacji — dostęp jest możliwy, jeśli aplikacja mobilna zawiera dane firmy](app-based-conditional-access-intune.md)
* [Izolowanie danych firmowych od danych osobistych w ramach tej samej aplikacji](app-protection-policy.md)
* [Zasady ochrony aplikacji (numer PIN, szyfrowanie, funkcja „Zapisz jako”, schowek itp.)](app-protection-policies.md)
* [Czyszczenie danych firmowych z aplikacji mobilnej](apps-selective-wipe.md)
* [Obsługę usługi Rights Management](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)

![Obraz zawierający poziomy zabezpieczeń danych zarządzania aplikacją](./media/managing-mobile-apps.png)

### <a name="intune-app-security"></a>Bezpieczeństwo aplikacji w usłudze Intune
Zapewnianie bezpieczeństwa aplikacji stanowi element zarządzania aplikacjami. Omawiając bezpieczeństwo aplikacji mobilnych w usłudze Intune, odnosimy się do następujących czynności:
* Przechowywanie informacji osobistych z dala od informatycznych danych firmowych
* Ograniczanie działań, jakie mogą podjąć użytkownicy wobec informacji firmowych, na przykład kopiowania, wycinania, wklejania, zapisywania i wyświetlania
* Usuwanie danych firmy z aplikacji mobilnych, nazywane również selektywnym czyszczeniem lub czyszczeniem firmowym

Jednym ze sposobów zapewniania bezpieczeństwa aplikacji mobilnych przez usługę Intune jest użycie funkcji **zasad ochrony aplikacji**. Zasady ochrony aplikacji wykorzystują tożsamość usługi Azure AD do izolowania danych firmowych od danych osobistych. Dane, do których dostęp uzyskiwany jest za pomocą poświadczeń firmowych, zostaną objęte dodatkowymi firmowymi zabezpieczeniami.

Gdy na przykład użytkownik loguje się do swojego urządzenia za pomocą poświadczeń firmowych, jego tożsamość firmowa umożliwia mu uzyskanie dostępu do danych, do których dostęp przy użyciu tożsamości osobistej nie jest możliwy. Podczas używania danych firmowych zasady ochrony aplikacji kontrolują sposób ich zapisywania i udostępniania. Te zabezpieczenia nie są stosowane względem danych, do których użytkownik uzyskuje dostęp, logując się do urządzenia za pomocą tożsamości osobistej. W ten sposób dział IT sprawuje kontrolę nad danymi firmowymi, a użytkownik końcowy kontroluje dane osobiste i utrzymuje ich prywatność.

## <a name="emm-with-and-without-device-enrollment"></a>Usługa EMM z rejestracją urządzenia i bez niej
Większość rozwiązań do zarządzania mobilnością w przedsiębiorstwie obsługuje podstawowe technologie związane z urządzeniami przenośnymi i aplikacjami mobilnymi. Są one zazwyczaj powiązane z urządzeniami, które zostały zarejestrowane w rozwiązaniu do zarządzania urządzeniami przenośnymi organizacji. Usługa Intune obsługuje te scenariusze, a dodatkowo obsługuje wiele scenariuszy „bez rejestracji”.  

Organizacje różnią się pod względem zakresu, w jakim przyjmują scenariusze „bez rejestracji”. Niektóre organizacje standaryzują ten scenariusz. Niektóre dopuszczają go na urządzeniach towarzyszących, takich jak tablety osobiste. Inne w ogóle go nie obsługują. Nawet w ostatnim przypadku, w którym organizacja wymaga, aby wszystkie urządzenia pracownicze były zarejestrowane w rozwiązaniu MDM, zwykle obsługują one scenariusze „bez rejestracji” w przypadku wykonawców, dostawców i innych urządzeń, które mają specjalne zwolnienie.

Technologia „bez rejestracji” usługi Intune może być nawet używana na zarejestrowanych urządzeniach. Urządzenie zarejestrowane w rozwiązaniu MDM może mieć na przykład zabezpieczenia typu „Otwórz w” dostarczone przez system operacyjny urządzenia przenośnego. W systemie iOS stosowana jest ochrona z użyciem funkcji „Otwórz w”, która uniemożliwia otwarcie dokumentu z jednej aplikacji, takiej jak program Outlook, w innej aplikacji, takiej jak Word. Wyjątek stanowi sytuacja, w której obie aplikacje są zarządzane przez dostawcę rozwiązania MDM. Ponadto dział IT może stosować zasady ochrony aplikacji względem aplikacji mobilnych zarządzanych przez pakiet EMS w celu kontrolowania funkcji „Zapisz jako” oraz zapewnienia uwierzytelniania wieloskładnikowego.

Niezależnie od stanowiska organizacji względem zarejestrowanych i niezarejestrowanych urządzeń przenośnych oraz aplikacji mobilnych usługa Intune, jako część pakietu EMS, dysponuje narzędziami, które pomagają zwiększyć produktywność pracowników przy jednoczesnej ochronie danych firmowych.



### <a name="next-steps"></a>Następne kroki
* Przeczytaj o pewnych [typowych sposobach korzystania z usługi Intune](common-scenarios.md).
* Zapoznaj się z produktem, korzystając [z 30-dniowej wersji próbnej usługi Intune](free-trial-sign-up.md).
* Poznaj [wymagania techniczne i możliwości](supported-devices-browsers.md) usługi Intune.
