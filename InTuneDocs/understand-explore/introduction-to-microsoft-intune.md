---
title: "Co to jest usługa Microsoft Intune | Microsoft Docs"
description: "Dowiedz się, w jaki sposób usługa Intune pełni rolę składnika zarządzania urządzeniami przenośnymi rozwiązania Enterprise Mobility + Security oraz jak pomaga w ochronie danych firmowych."
keywords: "co to jest usługa Intune"
author: Lindavr
ms.author: lindavr
manager: angrobe
ms.date: 11/15/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b4e778d-ac13-4c23-974f-5122f74626bc
ms.reviewer: pmay
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: d0057f1e3d2ead729c2143587571fa4b16a3dd2f
ms.openlocfilehash: 9b4eed086853c0feeb8266a8087a275f2b70e40f
ms.lasthandoff: 01/11/2017


---

# <a name="what-is-intune"></a>Co to jest usługa Intune?

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Usługa Intune to oparta na chmurze usługa zarządzania mobilnością w przedsiębiorstwie (EMM, enterprise mobility management) ułatwiająca pracownikom utrzymanie produktywności przy jednoczesnej ochronie danych firmowych. Usługa Intune umożliwia:
* zarządzanie urządzeniami przenośnymi używanymi przez pracowników do uzyskiwania dostępu do danych firmowych,
* zarządzanie aplikacjami mobilnymi używanymi przez pracowników,
* chronienie danych firmowych poprzez kontrolowanie sposobu, w jaki pracownicy uzyskują do nich dostęp i udostępniają je,
* zapewnienie zgodności urządzeń i aplikacji z wymaganiami firmy dotyczącymi bezpieczeństwa.

Usługa Intune jest ściśle zintegrowana z usługą Azure Active Directory (Azure AD), co umożliwia kontrolowanie tożsamości i dostępu, a także z usługą Azure Rights Management (Azure RMS) na potrzeby ochrony danych. Stanowi ona *ramię zarządzania* pakietu Microsoft Enterprise Mobility + Security (EMS), podczas gdy usługa Office 365 stanowi *ramię produktywności* rozwiązania zapewniającego mobilność firmy Microsoft.  

Współdziałając, usługa Office 365 i pakiet EMS zapewniają pracownikom produktywność na wszystkich urządzeniach, z których korzystają, przy jednoczesnym zachowaniu bezpieczeństwa informacji należących do organizacji. Usługa Office 365 wraz z pakietem EMS stanowi kompletny, zintegrowany pakiet rozwiązań zapewniających mobilność w przedsiębiorstwie obejmujący rozwiązania do kontroli dostępu, zarządzania, potwierdzania tożsamości, zapewniania produktywności i ochrony danych. Udostępnia efektywny sposób wdrażania i obsługi rozwiązania zapewniającego mobilność.

## <a name="how-does-intune-work"></a>Jak działa usługa Intune?
Usługa Intune umożliwia zarządzanie urządzeniami przenośnymi (MDM, mobile device management) oraz zarządzanie aplikacjami mobilnymi (MAM, mobile app management). Funkcje MDM oraz MAM wchodzą w skład pakietu EMS scenariuszy zgodności i ochrony danych.  

Sposób użycia funkcji MDM i MAM usługi Intune i ochrony danych pakietu EMS zależy od [problemu biznesowego, który próbujesz rozwiązać](#common-business-problems-that-intune-helps-solve). Na przykład:
* Funkcja MDM znajdzie zastosowanie przy tworzeniu puli urządzeń współdzielonych przez pracowników zmianowych w sklepie detalicznym.
* Funkcja MAM i ochrona danych jest przydatna w sytuacji, gdy pracownicy uzyskują dostęp do danych firmowych za pomocą urządzeń osobistych (BYOD).  
* W dużym stopniu możesz polegać na wszystkich technologiach, jeśli wydajesz telefony firmowe pracownikom przetwarzającym informacje.

## <a name="intune-mobile-device-management-mdm-explained"></a>Zarządzanie urządzeniami przenośnymi (MDM) w usłudze Intune — objaśnienie
Funkcja MDM działa przy użyciu protokołów lub interfejsów API, które są dostępne w systemach operacyjnych urządzeń przenośnych. Obejmuje takie zadania jak:
* Rejestrowanie urządzeń do zarządzania, aby dział IT miał spis urządzeń uzyskujących dostęp do usług firmowych
* Konfigurowanie urządzeń w celu upewnienia się, że spełniają standardy firmy dotyczące kondycji i zabezpieczeń
* Dostarczanie certyfikatów i profilów sieci Wi-Fi/VPN w celu uzyskania dostępu do usług firmowych
* Raportowanie i pomiar zgodności urządzenia ze standardami firmy
* Usuwanie danych firmowych z zarządzanych urządzeń  

Niektórzy sądzą, że **kontrolowanie dostępu do danych firmowych** jest funkcją rozwiązania MDM. Nie należy myśleć o tym w ten sposób, ponieważ to nie jest funkcja dostarczana przez system operacyjny urządzeń przenośnych. Jest to raczej funkcja dostarczana przez dostawcę tożsamości. W tym przypadku dostawcą tożsamości jest usługa Azure Active Directory (Azure AD) — system zarządzania dostępem i tożsamością firmy Microsoft.  

Usługa Intune integruje się z usługą Azure AD, aby udostępnić szeroką gamę scenariuszy kontroli dostępu. Na przykład można wymagać, aby przed uzyskaniem dostępu do usług firmowych, takich jak program Exchange, urządzenie przenośne spełniało standardy firmy określone w usłudze Intune. Podobnie można zablokować dostęp do usług firmowych określonemu zestawowi aplikacji mobilnych. Na przykład można zablokować usługę Exchange Online tak, aby dostęp do niej był możliwy tylko za pomocą programu Outlook lub Outlook Mobile.

## <a name="intune-mobile-app-management-mam-explained"></a>Zarządzanie aplikacjami mobilnymi (MAM) w usłudze Intune — objaśnienie
Funkcja MAM — za pomocą naszych rozwiązań — umożliwia specjalistom IT wykonywanie szeregu zadań związanych z aplikacjami mobilnymi, na przykład:
* Publikowanie aplikacji mobilnych dla pracowników
* Konfigurowanie aplikacji
* Kontrolowanie sposobu używania i udostępniania danych firmowych w aplikacjach mobilnych
* Usuwanie danych firmowych z aplikacji mobilnych   
* Aktualizowanie aplikacji mobilnych
* Raportowanie dotyczące spisu aplikacji mobilnych
* Śledzenie użycia aplikacji mobilnej

Termin zarządzania aplikacjami mobilnymi jest często używany jako oznaczenie jednej z powyższych czynności lub konkretnej ich kombinacji. Szczególnie powszechne jest łączenie koncepcji konfiguracji aplikacji (czyli używania technologi takich jak usługa [Managed App Configuration w systemie iOS](https://developer.apple.com/library/content/samplecode/sc2279/Introduction/Intro.html)) z koncepcją zabezpieczania danych firmowych w aplikacjach mobilnych. Wynika to z faktu, że niektóre aplikacje mobilne uwidaczniają ustawienia, które umożliwiają skonfigurowanie funkcji zabezpieczeń danych.

To — w połączeniu z funkcjami ochrony danych systemu operacyjnego (na przykład funkcjami MDM, takimi jak rozwiązanie Windows Information Protection w systemie Windows 10) — zapewnia wysoki poziom ochrony danych na urządzeniach przenośnych.

Korzystając z usługi Intune w połączeniu z innymi usługami pakietu EMS, możesz zapewnić swojej organizacji lepsze bezpieczeństwo aplikacji mobilnych niż to dostarczane przez system operacyjny urządzeń przenośnych i same aplikacje mobilne za pośrednictwem konfiguracji aplikacji. Aplikacja zarządzana za pomocą pakietu EMS ma dostęp do szerszego zakresu zabezpieczeń aplikacji mobilnych i danych, który obejmuje:

* [Logowanie jednokrotne](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-appssoaccess-whatis)  
*    [Uwierzytelnianie wieloskładnikowe](https://docs.microsoft.com/en-us/multi-factor-authentication/multi-factor-authentication)
* [Warunkowy dostęp do aplikacji (dostęp jest umożliwiony, jeśli aplikacja mobilna zawiera dane firmy)](https://docs.microsoft.com/en-us/intune/deploy-use/allow-policy-managed-apps-access-to-o365)
* [Izolowanie danych firmowych od danych osobistych w ramach tej samej aplikacji](https://docs.microsoft.com/en-us/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)
* [Zasady ochrony aplikacji (numer PIN, szyfrowanie, funkcja „Zapisz jako”, schowek itp.)](https://docs.microsoft.com/en-us/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)
* [Czyszczenie danych firmowych z aplikacji mobilnej](https://docs.microsoft.com/en-us/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)
* [Obsługę usługi Rights Management](https://docs.microsoft.com/en-us/information-protection/understand-explore/what-is-azure-rms)

![Obraz zawierający poziomy zabezpieczeń danych zarządzania aplikacją](./media/managing-mobile-apps.png)

### <a name="intune-mobile-app-security"></a>Bezpieczeństwo aplikacji mobilnych w usłudze Intune
Zapewnianie bezpieczeństwa aplikacji stanowi część funkcji MAM. Mówiąc o bezpieczeństwie aplikacji mobilnych w usłudze Intune, mamy na myśli:
* Przechowywanie informacji osobistych z dala od informatycznych danych firmowych
* Ograniczanie działań, jakie mogą podjąć użytkownicy wobec informacji firmowych, na przykład kopiowania, wycinania, wklejania, zapisywania i wyświetlania
* Usuwanie danych firmy z aplikacji mobilnych, nazywane również selektywnym czyszczeniem lub czyszczeniem firmowym

Jednym ze sposobów zapewniania bezpieczeństwa aplikacji mobilnych przez usługę Intune jest użycie funkcji **zasad ochrony aplikacji**. Zasady ochrony aplikacji wykorzystują tożsamość usługi Azure AD do izolowania danych firmowych od danych osobistych. Dane, do których dostęp uzyskiwany jest za pomocą poświadczeń firmowych, zostaną objęte dodatkowymi firmowymi zabezpieczeniami.

Gdy użytkownik loguje się do swojego urządzenia za pomocą poświadczeń firmowych, jego tożsamość firmowa umożliwia mu uzyskanie dostępu do danych, do których dostęp przy użyciu tożsamości osobistej nie jest możliwy. Gdy dane firmowe są używane, usługa Intune wraz z innymi technologiami pakietu EMS kontroluje sposób ich zapisu i udostępniania. Te zabezpieczenia nie są stosowane względem danych, do których użytkownik uzyskuje dostęp, logując się do urządzenia za pomocą tożsamości osobistej. W ten sposób dział IT sprawuje kontrolę nad danymi firmowymi, a użytkownik końcowy kontroluje dane osobiste i utrzymuje ich prywatność.

## <a name="emm-with-and-without-device-enrollment"></a>Usługa EMM z rejestracją urządzenia i bez niej
Większość rozwiązań do zarządzania mobilnością w przedsiębiorstwie obsługuje podstawowe technologie związane z urządzeniami przenośnymi i aplikacjami mobilnymi. Są zazwyczaj powiązane z urządzeniami, które zostały zarejestrowane w rozwiązaniu MDM organizacji. Usługa Intune obsługuje te scenariusze, a dodatkowo obsługuje wiele scenariuszy „bez rejestracji”.  

Organizacje różnią się pod względem zakresu, w jakim przyjmują scenariusze „bez rejestracji”. Niektóre organizacje standaryzują ten scenariusz. Niektóre dopuszczają go na urządzeniach towarzyszących, takich jak tablety osobiste. Inne w ogóle go nie obsługują. Nawet w ostatnim przypadku, w którym organizacja wymaga, aby wszystkie urządzenia pracownicze były zarejestrowane w rozwiązaniu MDM, organizacje te zwykle obsługują scenariusze „bez rejestracji” w przypadku wykonawców, dostawców i innych urządzeń, które mają specjalne zwolnienie.

Technologia „bez rejestracji” usługi Intune może być nawet używana na zarejestrowanych urządzeniach. Urządzenie zarejestrowane w rozwiązaniu MDM może mieć na przykład zabezpieczenia typu „Otwórz w” dostarczone przez system operacyjny urządzenia przenośnego. (W systemie iOS stosowana jest ochrona z użyciem funkcji „Otwórz w”, która uniemożliwia otwarcie dokumentu z jednej aplikacji, takiej jak program Outlook, w innej aplikacji, takiej jak Word; wyjątek stanowi sytuacja, w które obie aplikacje są zarządzane przez dostawcę rozwiązania MDM). Ponadto dział IT może stosować zasady ochrony aplikacji względem aplikacji mobilnych zarządzanych przez pakiet EMS w celu kontrolowania funkcji „Zapisz jako” oraz zapewnienia uwierzytelniania wieloskładnikowego.

Niezależnie od stanowiska organizacji względem zarejestrowanych i niezarejestrowanych urządzeń przenośnych oraz aplikacji mobilnych usługa Intune, jako część pakietu EMS, dysponuje narzędziami, które pomagają zwiększyć produktywność pracowników przy jednoczesnej ochronie danych firmowych.

## <a name="common-business-problems-that-intune-helps-solve"></a>Typowe problemy biznesowe, które pomaga rozwiązywać usługa Intune
Poniższa lista problemów biznesowych zawiera linki do bardziej szczegółowych informacji o dostarczanych rozwiązaniach. Tylko ostatni element wymaga rejestracji w rozwiązaniu MDM w ramach rozwiązania:

* [Zabezpieczanie lokalnej poczty e-mail i danych na potrzeby uzyskiwania dostępu przez urządzenia przenośne](common-ways-to-use-intune.md#protecting-your-on-premises-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices)
* [Zabezpieczanie poczty e-mail i danych w usłudze Office 365 na potrzeby uzyskiwania bezpiecznego dostępu przez urządzenia przenośne](common-ways-to-use-intune.md#protecting-your-office-365-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices)
* [Wydawanie firmowych telefonów pracownikom](common-ways-to-use-intune.md#issue-corporate-owned-phones-to-your-information-workers)
* [Oferowanie programu „Przynieś własne urządzenie” (BYOD, bring your own device) lub urządzeń osobistych wszystkim pracownikom](common-ways-to-use-intune.md#offer-a-bring-your-own-device-program-to-all-employees)
* [Umożliwianie pracownikom bezpiecznego dostępu do usługi Office 365 z niezarządzanego kiosku publicznego](common-ways-to-use-intune.md#enable-your-employees-to-securely-access-office-365-from-an-unmanaged-public-kiosk)
* [Wydawanie wspólnych tabletów do ograniczonego użytku pracownikom wykonującym zadania](common-ways-to-use-intune.md#issue-limited-use-shared-tablets-to-your-task-workers)

### <a name="next-steps"></a>Następne kroki
* Przeczytaj o pewnych [typowych sposobach korzystania z usługi Intune](common-ways-to-use-intune.md).
* Zapoznaj się z produktem, korzystając [z 30-dniowej wersji próbnej usługi Intune](get-started-with-a-30-day-trial-of-microsoft-intune.md).
* Poznaj [wymagania techniczne i możliwości](/intune/get-started/what-to-know-before-you-start-microsoft-intune) usługi Intune.

