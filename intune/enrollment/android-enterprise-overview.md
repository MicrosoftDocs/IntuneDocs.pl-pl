---
title: Zarządzanie urządzeniami z profilem służbowym systemu Android Enterprise w usłudze Microsoft Intune
titleSuffix: ''
description: Zarządzanie urządzeniami z profilem służbowym Android Enterprise przez usługę Microsoft Intune udostępnia dodatkowe funkcje zarządzania i ochrony prywatności, które ułatwiają użytkownikom korzystanie z osobistych urządzeń z systemem Android w celach służbowych.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2cc3c960-1fdd-47ca-a693-420d47b403de
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1a5c980b3f9ababaf94aa7b279e533679ed74b0e
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72503365"
---
# <a name="manage-android-work-profile-devices-with-intune"></a>Zarządzanie urządzeniami z profilem służbowym systemu Android za pomocą usługi Intune

System Android Enterprise oferuje zestaw opcji rejestracji, które zapewniają użytkownikom najbardziej aktualne i bezpieczne funkcje. Rejestrowanie przy użyciu profilu służbowego systemu Android Enterprise udostępnia zestaw funkcji i usług, które oddzielają osobiste aplikacje i dane od służbowych aplikacji i danych. Udostępnia również dodatkowe funkcje zarządzania i ochrony prywatności, które ułatwiają użytkownikom korzystanie z osobistych urządzeń z systemem Android w celach służbowych. 

## <a name="supported-devices"></a>Obsługiwane urządzenia

Funkcje zarządzania rozwiązania Android Enterprise korzystają z możliwości zapewnianych przez nowsze systemy operacyjny Android. W przypadku urządzeń, które nie zapewniają obsługi rozwiązania Android Enterprise, dostępne są konwencjonalne funkcje zarządzania systemem Android. Aby uzyskać więcej informacji, zobacz [wymagania dotyczące rozwiązania Android Enterprise](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

## <a name="onboarding"></a>Dołączanie

Aby zarejestrować urządzenia z profilem służbowym systemu Android Enterprise, należy wykonać pewne kroki dołączania. Umożliwiają one nawiązanie połączenia między dzierżawą usługi Intune i zarządzanym sklepem Google Play. Aby uzyskać więcej informacji, zobacz [Włączanie rejestracji urządzeń z profilem służbowym systemu Android Enterprise](android-work-profile-enroll.md).

## <a name="work-profile-management"></a>Zarządzanie profilami służbowymi

Zarządzanie urządzeniem z profilem służbowym systemu Android Enterprise przy użyciu usługi Intune nie obejmuje zarządzania całym urządzeniem. Zarządzanie dotyczy tylko profilu służbowego utworzonego na urządzeniu podczas rejestracji. Wszystkie aplikacje wdrażane na urządzeniu za pomocą usługi Intune zostają zainstalowane w profilu służbowym. Ikony aplikacji w profilu służbowym są odróżniane od aplikacji osobistych na urządzeniu. Wszystkie aplikacje i dane, które nie są objęte rozwiązaniem Android enterprise, są zarządzane przez użytkownika końcowego i przeznaczone do użytku osobistego. Użytkownicy mogą instalować dowolne aplikacje po stronie osobistej urządzenia. Administratorzy mogą monitorować aplikacje i akcje należące do zakresu profilu służbowego oraz zarządzać nimi.

Usługa Intune udostępnia szereg wbudowanych ustawień ogólnych, które można skonfigurować na urządzeniach z profilem służbowym systemu Android. Aby uzyskać więcej informacji, zobacz [ustawienia zasad urządzeń z profilem służbowym systemu Android](../protect/compliance-policy-create-android-for-work.md).

## <a name="app-publishing-and-distribution"></a>Publikowanie i dystrybucja aplikacji

Zarządzany sklep Google Play jest integralną częścią procesu dystrybucji aplikacji i zarządzania nimi w ramach rozwiązania Android Enterprise. Wszystkie aplikacje należące do profilu służbowego wdrożone na urządzeniach z profilem służbowym systemu Android Enterprise pochodzą z usługi Zarządzany sklep Google Play. W celu zarządzania aplikacjami i ich wdrażania w Sklepie Play musisz zalogować się do witryny Google Play przy użyciu poświadczeń administratora w Twojej firmie odpowiednich do zarządzania kontem Google. Możesz zatwierdzać wdrożenia aplikacji dla rozwiązania Android Enterprise, które będą pojawiać się w profilach służbowych urządzeń. Aplikacje te są synchronizowane z konsolą usługi Intune, która umożliwia ich wdrożenie i zarządzanie nimi. Aplikacje biznesowe opracowane w organizacji muszą zostać opublikowane w zarządzanym sklepie Google Play przy użyciu konsoli firmy Google służącej do publikowania aplikacji systemu Android. Za pomocą konsoli publikowania aplikacji systemu Android należy skonfigurować aplikacje biznesowe pod kątem ograniczenia dostępu do danej organizacji.

Aplikacje można instalować bez udziału użytkownika i bez wymagania zezwolenia na **instalację z nieznanych źródeł**. Aby przeglądać oraz instalować opcjonalne lub dostępne aplikacje, użytkownicy mogą przeglądać na swoim urządzeniu zasoby sklepu Play for Work. Aby uzyskać więcej informacji, zobacz [Przypisywanie aplikacji do urządzeń z profilem służbowym systemu Android Enterprise za pomocą usługi Intune](../apps/apps-add-android-for-work.md).

## <a name="app-configuration"></a>Konfiguracja aplikacji

Rozwiązanie Android Enterprise zapewnia infrastrukturę pozwalającą wdrażać parametry konfiguracji aplikacji w aplikacjach, które to obsługują. Określenie wartości konfiguracji dla aplikacji służbowych gwarantuje poprawność ustawień podczas pierwszego uruchamiania aplikacji przez użytkowników. Obsługa konfiguracji aplikacji wymaga od deweloperów aplikacji dla systemu Android projektowania swoich aplikacji w sposób umożliwiający korzystanie z zarządzanych wartości konfiguracji. Pozwala to określać i stosować ustawienia konfiguracji przy użyciu usługi Intune. Aby uzyskać więcej informacji, zobacz [Dodawanie zasad konfiguracji aplikacji dla zarządzanych urządzeń z systemem Android](../apps/app-configuration-policies-use-android.md).

## <a name="email-configuration"></a>Konfiguracja poczty e-mail

Inaczej niż w systemie iOS, rozwiązanie Android Enterprise nie udostępnia domyślnej aplikacji poczty e-mail ani natywnego obiektu profilu poczty e-mail. Zamiast tego konfigurację poczty e-mail można ustawić, stosując ustawienia konfiguracji aplikacji do obsługujących je aplikacji poczty e-mail. W Sklepie Play są dostępne dwie aplikacje klienckie Exchange ActiveSync (EAS) obsługujące konfigurację aplikacji rozwiązania Android Enterprise: Gmail i Nine Work.

Usługa Intune udostępnia szablony konfiguracji dla aplikacji Gmail i Nine Work, gdy są one zarządzane jako aplikacje robocze. Pozostałe aplikacje poczty e-mail, które obsługują profile konfiguracji aplikacji, można konfigurować przy użyciu zasad konfiguracji aplikacji mobilnych.

Jeśli na urządzeniu z profilem służbowym systemu Android Enterprise korzystasz z dostępu warunkowego programu Exchange ActiveSync, do obsługi poczty e-mail warto używać aplikacji Gmail lub Nine Work. Obsługiwana jest również aplikacja Microsoft Outlook dla systemu Android, a także wszystkie inne aplikacje poczty e-mail, które używają nowoczesnego uwierzytelniania za pośrednictwem biblioteki ADAL. Aby uzyskać więcej informacji, zobacz [Jak skonfigurować ustawienia poczty e-mail w usłudze Microsoft Intune](../configuration/email-settings-configure.md).

## <a name="app-protection-policies"></a>Zasady ochrony aplikacji

Stosowane zasady ochrony aplikacji są w pełni obsługiwane w profilu służbowym i w profilu osobistym. Aplikacje biznesowe można opublikować przy użyciu konsoli publikowania aplikacji systemu Android dostępnej pod adresem https://play.google.com/apps/publish. Konsola ta pozwala określić aplikacje jako prywatne w obrębie organizacji. Aby uzyskać więcej informacji, zobacz [Dodawanie zasad zgodności dla urządzeń z profilem służbowym systemu Android Enterprise w usłudze Intune](../protect/compliance-policy-create-android-for-work.md). Aby uzyskać ogólne informacje na temat zasad ochrony aplikacji, zobacz [Co to są zasady ochrony aplikacji?](../apps/app-protection-policy.md)

## <a name="vpn-profiles"></a>profile sieci VPN,

Obsługa sieci VPN działa podobnie do profilów sieci VPN systemu Android. Na potrzeby zarządzania rozwiązaniem Android Enterprise dostępni są ci sami dostawcy sieci VPN oraz takie same podstawowe opcje konfiguracji z dwiema różnicami:

- **Połączenia VPN ograniczone do profilu służbowego** — połączenia w sieci VPN są ograniczone tylko do aplikacji wdrożonych w profilu służbowym. Z połączenia VPN mogą korzystać tylko aplikacje zarządzane przez rozwiązanie Android Enterprise. Aplikacje osobiste zainstalowane na urządzeniu nie mogą używać zarządzanego połączenia VPN. Aby uzyskać więcej informacji, zobacz [Ustawienia sieci VPN dla rozwiązania Android Enterprise](../configuration/vpn-settings-android-enterprise.md).

- **Sieć VPN specyficzna dla aplikacji** — sieć VPN specyficzną dla aplikacji można skonfigurować w usłudze Intune, jeśli dostawca sieci VPN zapewnia obsługę następujących funkcji:
  - Konfiguracja sieci VPN specyficznej dla aplikacji.
  - Możliwość skonfigurowania sieci VPN dla aplikacji za pomocą profilu konfiguracji aplikacji rozwiązania Android Enterprise.
  Aby uzyskać więcej informacji, zobacz [Korzystanie z niestandardowego profilu usługi Microsoft Intune w celu tworzenia profilu sieci VPN dla aplikacji dla urządzeń z systemem Android](../configuration/android-pulse-secure-per-app-vpn.md).

## <a name="certificate-profiles"></a>Profile certyfikatów

Opcje konfiguracji profilów certyfikatów, które są dostępne w funkcji zarządzania systemem Android, są również dostępne dla urządzeń z profilem służbowym systemu Android Enterprise. Rozwiązanie Android Enterprise umożliwia korzystanie z rozszerzonych interfejsów API zarządzania certyfikatami. Rozszerzone zarządzanie certyfikatami pozwala korzystać z następujących funkcji:

- Zapewnia dyskretne i bezproblemowe wdrożenie certyfikatu z perspektywy użytkownika.
- Zapewnia usunięcie wdrożonych certyfikatów w przypadku wycofania urządzenia z usługi Intune i usunięcia profilu służbowego.
- Usprawnia obsługę komunikatów, co pozwala poinformować użytkowników o wdrożeniu certyfikatu i skonfigurowaniu go przez dział IT za pomocą usługi zarządzania.

Aby uzyskać więcej informacji, zobacz [Konfigurowanie profilu certyfikatu dla urządzeń w usłudze Microsoft Intune](../protect/certificates-configure.md).

## <a name="wi-fi-profiles"></a>Profile sieci Wi-Fi

Profile sieci Wi-Fi zarządzane przez rozwiązanie Android Enterprise są usuwane po wycofaniu urządzenia z usługi Intune i usunięciu profilu służbowego. Aby uzyskać więcej informacji, zobacz [Jak skonfigurować ustawienia sieci Wi-Fi w usłudze Microsoft Intune](../configuration/wi-fi-settings-configure.md).

## <a name="next-steps"></a>Następne kroki
- [Rejestrowanie urządzeń z systemem Android](android-enroll.md)
- [Przypisywanie aplikacji do urządzeń z profilem służbowym systemu Android Enterprise za pomocą usługi Intune](../apps/apps-add-android-for-work.md)
