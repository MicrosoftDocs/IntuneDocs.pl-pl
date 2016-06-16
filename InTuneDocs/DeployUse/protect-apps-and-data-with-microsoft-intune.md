---
# required metadata

title: Ochrona aplikacji i danych | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 5c46e188-87eb-4ce2-b184-24809e8bf783

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisgre
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Ochrona aplikacji i danych w usłudze Microsoft Intune


Usługa Intune chroni dane firmowe dzięki zastosowaniu wielu warstw technologicznych.  W warstwie tożsamości funkcja dostępu warunkowego chroni dostęp do usług, zezwalając jedynie na dostęp z urządzeń zarządzanych i zgodnych.  W warstwie aplikacji klienta funkcja zarządzania aplikacjami mobilnymi (MAM) chroni przed utratą danych, uniemożliwiając przenoszenie danych do niechronionych aplikacji lub lokalizacji magazynu danych oraz czyszcząc dane w przypadku utraty lub kradzieży urządzenia.  Te dwie warstwy ochrony powinny być używane razem w celu zabezpieczania danych przy jednoczesnym zachowaniu produktywności pracowników mobilnych.

Pierwszy ważny krok do ochrony danych firmy to zaimplementowanie dostępu warunkowego. Należy przy tym upewnić się, że urządzenia używane do uzyskiwania dostępu do danych korzystają z ochrony zabezpieczeń, takiej jak silne hasło i szyfrowanie, oraz że nie zdjęto z nich zabezpieczeń systemu. Usługa Microsoft Intune daje możliwość określenia warunków, z którymi urządzenia muszą być zgodne przed uzyskaniem dostępu do firmowej poczty e-mail i danych.

[Dostęp warunkowy](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) jest określany przez dwa typy zasad, które można ustawić w usłudze Intune:
- [Zasady zgodności](introduction-to-device-compliance-policies-in-microsoft-intune.md) określają zgodność urządzenia. Umożliwiają podawanie wartości ustawień i warunków, takich jak:
  - Numery PIN i hasła: można utworzyć reguły wymagające wprowadzenia hasła przed odblokowaniem urządzenia, a także określić wymagania dotyczące złożoności hasła i inne ustawienia haseł.
  - Szyfrowanie: można ograniczyć dostęp do szyfrowanych urządzeń.
  - Urządzenie ma zdjęte zabezpieczenia lub odblokowany dostęp do konta root: usługa Intune może wykryć, czy z zarejestrowanego urządzenia zdjęto zabezpieczenia, a użytkownik może ustawić zasady blokujące dostęp do tych urządzeń.
- [Zasady dostępu warunkowego](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) są konfigurowane pod kątem określonej usługi, takiej jak Exchange Online lub SharePoint Online. Dla każdej usługi można określić, do której grupy użytkowników te zasady będą stosowane. Można na przykład upewnić się, że wszyscy pracownicy działu finansów mogą uzyskiwać dostęp do firmowych wiadomości e-mail z urządzeń zarejestrowanych i zgodnych.

Zabezpieczanie dostępu do zasobów firmy to tylko pierwszy krok do ochrony danych firmowych. Nadal konieczny będzie dostęp do możliwości ochrony danych po uzyskaniu do nich dostępu na urządzeniu. Dane można teraz kopiować, przenosić, zapisywać w innej lokalizacji lub udostępniać. Usługa Intune rozwiązuje ten problem, udostępniając możliwość ograniczenia przepływu danych dzięki utworzeniu zestawu reguł, takich jak:
- Blokowanie kopiowania i wklejania lub uniemożliwianie przesyłania danych poza kontekstem służbowym.
- Uniemożliwianie tworzenia kopii zapasowej w osobistym magazynie w chmurze, blokowanie operacji Zapisz jako.
- Zabezpieczanie dostępu do aplikacji przez wymaganie kodu PIN/dostępu lub firmowych poświadczeń.
- Otwieranie wszystkich linków sieci Web w programie Intune Managed Browser.

Te zestawy reguł są określane jako [zasady zarządzania aplikacjami mobilnymi (MAM)](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).  Zasady MAM można stosować do aplikacji działających na urządzeniach, które mogą być zarządzane lub niezarządzane przez użytkownika.  Dane firmowe można chronić przy użyciu zasad MAM dla urządzeń zarejestrowanych w Intune, urządzeń zarejestrowanych i zarządzanych przez funkcję MDM innej firmy lub urządzeń, które mogą być zarządzane przez użytkownika, takich jak urządzenia należące do pracownika.

Aby skojarzyć aplikację z zasadami MAM, aplikacja musi uwzględniać zestaw SDK aplikacji w usłudze Microsoft Intune lub korzystać z narzędzia opakowującego aplikacje.

Aplikacje, takich jak aplikacje pakietu Microsoft Office, mają wbudowany odpowiedni zestaw SDK. Pełną listę obsługiwanych aplikacji można znaleźć w [galerii aplikacji mobilnych usługi Microsoft Intune](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) na stronie partnerów aplikacji usługi Microsoft Intune. Wybierz aplikację, aby wyświetlić obsługiwane scenariusze i platformy, a także sprawdzić, czy aplikacja obsługuje wiele tożsamości.

Można również [umożliwić własnym niestandardowym aplikacjom biznesowym](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md) korzystanie z zasad MAM.

Oprócz ograniczania przepływu danych, jeśli urządzanie zostanie utracone lub skradzione albo jeśli użytkownik nie jest już pracownikiem firmy, można [selektywnie wyczyścić dane firmowe](wipe-managed-company-app-data-with-microsoft-intune.md), pozostawiając tylko dane osobiste.


<!--HONumber=Jun16_HO2-->


