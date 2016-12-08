---
title: Ochrona aplikacji i danych | Microsoft Intune
description: "W tym temacie opisano różne funkcje usługi Intune i możliwości, które są dostępne, aby chronić aplikacje i dane firmy."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5c46e188-87eb-4ce2-b184-24809e8bf783
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b36e3fb4eda81a39a1ccdae97d74959e879a9acc
ms.openlocfilehash: 3e302c50d931bd2545116dc510ddf2f1d7aa4f93


---

# <a name="protect-apps-and-data-with-microsoft-intune"></a>Ochrona aplikacji i danych w usłudze Microsoft Intune


Usługa Intune chroni dane firmowe dzięki zastosowaniu wielu warstw technologicznych. W warstwie tożsamości funkcja dostępu warunkowego chroni dostęp do usług, zezwalając jedynie na dostęp z urządzeń zarządzanych i zgodnych. W warstwie aplikacji klienta funkcja zarządzania aplikacjami mobilnymi (MAM) chroni przed utratą danych, uniemożliwiając przenoszenie danych do niechronionych aplikacji lub lokalizacji magazynu oraz czyszcząc dane w przypadku utraty lub kradzieży urządzenia. Zaleca się używanie tych dwóch warstw ochrony jednocześnie, aby ułatwić zabezpieczanie danych przy jednoczesnym zachowaniu produktywności pracowników mobilnych.

Pierwszym ważnym krokiem do ochrony danych firmy jest zaimplementowanie dostępu warunkowego. W tym celu należy się upewnić, że urządzenia, które są używane do dostępu do tych danych, korzystają z takich zabezpieczeń, jak silne hasła i szyfrowanie, i nie mają zdjętych zabezpieczeń systemu. Usługa Intune umożliwia określenie warunków, które urządzenia muszą spełnić przed uzyskaniem dostępu do firmowej poczty e-mail i danych.

[Dostęp warunkowy](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) jest określany przez dwa typy zasad, które można ustawić w usłudze Intune:
- Do określenia zgodności urządzenia można użyć [zasad zgodności](introduction-to-device-compliance-policies-in-microsoft-intune.md). Umożliwiają podawanie wartości ustawień i warunków, takich jak:
  - Numery PIN i hasła: można utworzyć reguły wymagające wprowadzenia hasła przed odblokowaniem urządzenia, reguły określające wymagania dotyczące złożoności hasła i inne ustawienia haseł.
  - Szyfrowanie: można ograniczyć dostęp do szyfrowanych urządzeń.
  - Gdy urządzenie nie ma zdjętych zabezpieczeń ani nie ma dostępu do konta root: usługa Intune może wykryć, czy z zarejestrowanego urządzenia zdjęto zabezpieczenia. Można ustawić zasady blokujące dostęp na tych urządzeniach.
- Można skonfigurować [zasady dostępu warunkowego](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) pod kątem określonej usługi, takiej jak Exchange Online lub SharePoint Online. Dla każdej usługi można określić, do której grupy użytkowników te zasady będą stosowane. Można na przykład upewnić się, że wszyscy pracownicy działu finansów mogą uzyskiwać dostęp do firmowych wiadomości e-mail z urządzeń zarejestrowanych i zgodnych.

Zabezpieczanie dostępu do zasobów firmy to tylko pierwszy krok do ochrony danych firmowych. Po uzyskaniu dostępu do danych na urządzeniu nadal należy mieć możliwość ich ochrony. Dane można teraz kopiować, przenosić, zapisywać w innej lokalizacji lub udostępniać. Usługa Intune rozwiązuje ten problem, udostępniając możliwość ograniczenia przepływu danych dzięki utworzeniu zestawu reguł, takich jak:
- Blokowanie kopiowania i wklejania lub uniemożliwianie przesyłania danych poza kontekstem służbowym.
- Uniemożliwianie tworzenia kopii zapasowej w osobistym magazynie w chmurze i blokowanie operacji „Zapisz jako”.
- Zabezpieczanie dostępu do aplikacji przez wymaganie kodu PIN/hasła dostępu lub firmowych poświadczeń.
- Otwieranie wszystkich linków sieci Web w programie Intune Managed Browser.

Te zestawy reguł są nazywane [zasadami zarządzania aplikacjami mobilnymi (MAM)](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md). Można stosować zasady zarządzania aplikacjami mobilnymi do aplikacji uruchomionych na urządzeniach, które mogą, ale nie muszą być zarządzane przez użytkownika.  

Dane firmowe można chronić przy użyciu zasad MAM dla urządzeń **zarejestrowanych w usłudze Intune**, urządzeń **zarejestrowanych i zarządzanych przez rozwiązanie do zarządzania urządzeniami przenośnymi (MDM) innej firmy** lub urządzeń, które **nie są zarejestrowane w żadnym rozwiązaniu MDM**, takich jak urządzenia należące do pracowników.

Aby skojarzyć aplikację z zasadami MAM, aplikacja musi uwzględniać zestaw SDK (Software Development Kit) aplikacji w usłudze Microsoft Intune. Można też skorzystać z narzędzia opakowującego aplikacje.

Aplikacje takie jak należące do pakietu Microsoft Office mają wbudowany zestaw SDK w usłudze Intune. Pełna lista obsługiwanych aplikacji jest dostępna w [galerii aplikacji mobilnych usługi Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps) na stronie partnerów aplikacji usługi Microsoft Intune. Wybierz aplikację, aby wyświetlić obsługiwane scenariusze i platformy oraz aby sprawdzić, czy obsługuje ona wiele tożsamości.

Możesz również [umożliwić własnym niestandardowym aplikacjom biznesowym](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md) korzystanie z zasad MAM.

Oprócz ograniczania przepływu danych, jeśli urządzanie zostanie utracone lub skradzione albo jeśli użytkownik nie jest już pracownikiem firmy, można [selektywnie wyczyścić dane firmowe](wipe-managed-company-app-data-with-microsoft-intune.md), pozostawiając tylko dane osobiste.



<!--HONumber=Nov16_HO5-->


