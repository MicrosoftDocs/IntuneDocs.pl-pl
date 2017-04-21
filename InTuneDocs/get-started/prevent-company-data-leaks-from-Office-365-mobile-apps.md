---
title: "Zapobieganie wyciekom danych firmowych z aplikacji mobilnych usługi Office 365 | Microsoft Docs"
description: "Korzystanie z usługi Intune umożliwia zabezpieczanie danych organizacji przy użyciu zasad zarządzania aplikacjami mobilnymi, które pomagają zapobiegać przeciekom danych firmowych z aplikacji mobilnych usługi Office 365 lub innych aplikacji biznesowych."
keywords: 
author: jeffgilb
ms.author: jeffgilb
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 19be3de7-539c-49f5-8c46-5363b987fef9
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: 4c13eb3149ea0cc21604a5a05445cfccdc984293
ms.lasthandoff: 04/14/2017


---

# <a name="quick-start-guide-prevent-company-data-leaks-from-office-365-mobile-apps"></a>Przewodnik Szybki Start: zapobieganie wyciekom danych firmowych z aplikacji mobilnych usługi Office 365

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Korzystając z usługi Microsoft Intune, można zabezpieczyć dane organizacji przy użyciu zasad zarządzania aplikacjami mobilnymi (MAM), które pomagają zapobiec przeciekom danych firmowych z aplikacji mobilnych usługi Office 365 lub innych aplikacji biznesowych. Używanie zasad zarządzania aplikacjami mobilnymi usługi Intune nie wymaga od użytkowników końcowych zarejestrowania swoich urządzeń w rozwiązaniu do zarządzania urządzeniami przenośnymi (rozwiązaniu MDM) w usłudze Intune. Jeśli zatem masz użytkowników, którzy nie chcą rejestrować swoich własnych urządzeń przenośnych BYOD z systemem iOS lub Android w rozwiązaniu MDM firmy Microsoft (usługi Intune, programu Configuration Manager lub EAS), chcesz chronić dane firmowe bez zarządzania urządzeniami użytkowników końcowych lub korzystasz już z rozwiązania MDM firmy innej niż Microsoft, usługa Intune może pomóc Ci zwiększyć bezpieczeństwo danych firmy.   

## <a name="is-this-quick-start-guide-right-for-me"></a>Czy ten przewodnik Szybki start jest dla mnie odpowiedni?
Czy chcesz umożliwić użytkownikom końcowym dostęp do usługi Office 365 i danych aplikacji biznesowych na ich urządzeniach z systemem iOS i Android bez wymagania rejestracji urządzeń w rozwiązaniu do zarządzania urządzeniami przenośnymi (MDM), ale nadal mieć kontrolę na tym, co użytkownicy mogą lub czego nie mogą robić z tymi danymi, na przykład jeśli chodzi o kopiowanie ich i wklejanie w aplikacjach osobistych?

Jeśli tak, usługa Microsoft Intune pozwala ustawić zasady zarządzania aplikacjami mobilnymi dla aplikacji mobilnych usługi Office 365 na urządzeniach z systemami iOS i Android, w tym ograniczenia wycinania/kopiowania/wklejania, uniemożliwianie korzystania z funkcji „Zapisz jako”, ustawienie wymagania numeru PIN oraz możliwość zdalnego czyszczenia danych chronionych przez zasady zarządzania aplikacjami mobilnymi.  W ten sposób można zapewnić ochronę danych firmowych, nie wymagając rejestracji urządzeń użytkowników końcowych w rozwiązaniu MDM i zachowując doskonałe środowisko użytkownika końcowego do pracy z aplikacjami mobilnymi pakietu Office.

## <a name="how-do-i-do-it"></a>Jak to zrobić?
1.    Uzyskaj podstawową wiedzę na temat [sposobu działania zarządzania aplikacjami mobilnymi w usłudze Intune](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune).
2.    Dowiedz się, [co należy zrobić przed rozpoczęciem tworzenia zasad zarządzania aplikacjami mobilnymi (MAM)](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) w portalu Azure.
3.    [Tworzenie i wdrażanie zasad MAM](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) przy użyciu usługi Intune.

### <a name="additional-information"></a>Informacje dodatkowe:
- [Środowisko użytkownika końcowego](/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune) (korzystanie z aplikacji objętych zarządzaniem aplikacjami mobilnymi).
- [Przygotowanie aplikacji biznesowych do zarządzania aplikacjami mobilnymi za pomocą usługi Intune](/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune)
- <a href="https://www.microsoft.com/cloud-platform/microsoft-intune-partners" target="_blank"> Lista partnerów aplikacji usługi Microsoft Intune &rarr;</a> (dostarczanie aplikacji z włączoną obsługą zarządzania aplikacjami mobilnymi).

## <a name="what-should-i-do-next"></a>Co teraz zrobić?
[Migracja do usługi Microsoft Intune z rozwiązania do zarządzania urządzeniami przenośnymi innego niż firmy Microsoft](/intune/deploy-use/migrate-to-intune)

[Rejestrowanie urządzeń w rozwiązaniu do zarządzania urządzeniami przenośnymi usługi Intune](/intune/deploy-use/enroll-devices-in-microsoft-intune)

