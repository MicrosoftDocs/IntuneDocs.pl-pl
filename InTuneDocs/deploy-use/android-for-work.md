---
title: "Program Android for Work — informacje | Microsoft Docs"
description: "Zarządzany przez usługę Intune program Android for Work udostępnia dodatkowe funkcje zarządzania i ochrony prywatności, które ułatwiają użytkownikom korzystanie z urządzeń z systemem Android w celach służbowych."
keywords: 
author: nathbarn
manager: angrobe
ms.date: 03/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aa0002d9-f5a0-466e-98ac-3970cb77e3a2
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e76d66768ac58df25313e102b7f60d2bc7bbc59b
ms.openlocfilehash: e04ab9c14ea6e7cc38430ec6a4d478a65e23ba96
ms.lasthandoff: 03/22/2017


---

# <a name="manage-android-for-work-devices-with-intune"></a>Zarządzanie urządzeniami z programem Android for Work za pomocą usługi Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Android for Work to zestaw funkcji i usług dostępnych na urządzeniach z systemem Android, które oddzielają osobiste aplikacje i dane od profilu służbowego zawierającego służbowe aplikacje i dane. Program Android for Work udostępnia dodatkowe funkcje zarządzania i ochrony prywatności, które ułatwiają użytkownikom korzystanie z urządzeń z systemem Android w celach służbowych. Usługa Intune ułatwia wdrażanie aplikacji i zasobów firmowych na urządzeniach z programem Android for Work, co zapewnia oddzielenie informacji osobistych od danych służbowych. Po pomyślnym wdrożeniu aplikacje oraz dane, z których korzystają te aplikacje, są używane wyłącznie w środowisku programu Android for Work zaimplementowanym na danym urządzeniu.

## <a name="supported-devices"></a>Obsługiwane urządzenia

Funkcje zarządzania programu Android for Work korzystają z możliwości zapewnianych przez nowszy system operacyjny Android. Program Android for Work jest obecnie obsługiwany na urządzeniach z systemem Android 5.0 Lollipop lub nowszym, które umożliwiają używanie profilów służbowych. W przypadku urządzeń, które nie zapewniają obsługi programu Android for Work, dostępne są konwencjonalne funkcje zarządzania systemem Android. Dowiedz się więcej o [wymaganiach programu Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

## <a name="onboarding"></a>Dołączanie

Aby zarejestrować urządzenia z programem Android for Work, należy wykonać pewne czynności w zakresie dołączenia. Umożliwiają one nawiązanie połączenia między dzierżawą usługi Intune a usługą Play for Work firmy Google, które jest integralną częścią procesu dystrybucji aplikacji Android for Work i zarządzania nią. Dowiedz się więcej o [włączaniu rejestrowania w programie Android for Work](https://docs.microsoft.com/intune/deploy-use/set-up-android-for-work).

## <a name="work-profile-management"></a>Zarządzanie profilami służbowymi

Zarządzanie urządzeniem z programem Android for Work przy użyciu usługi Intune nie obejmuje administrowania całego urządzenia. Zarządzanie dotyczy tylko profilu służbowego utworzonego na urządzeniu podczas rejestracji. Wszystkie aplikacje wdrażane na urządzeniu za pomocą usługi Intune zostają zainstalowane w profilu służbowym. Ikony aplikacji należących do profilu służbowego są oznaczone pomarańczową aktówką, co pozwala odróżnić je od znajdujących się na urządzeniu aplikacji osobistych. Wszystkie aplikacje i dane, które nie są objęte działaniem programu Android for Work, są zarządzane przez użytkownika końcowego i przeznaczone do użytku osobistego. Użytkownicy mogą instalować na urządzeniu dowolne wybrane przez siebie aplikacje jako osobiste, natomiast administratorzy mogą zarządzać aplikacjami i akcjami wchodzącymi w zakres profilu służbowego i monitorować je.

Usługa Intune udostępnia szereg wbudowanych ustawień ogólnych, które można skonfigurować na urządzeniach z programem Android for Work. Dowiedz się więcej o [ustawieniach zasad programu Android for Work](android-for-work-policy-settings-in-microsoft-intune.md)

## <a name="app-publishing-and-distribution"></a>Publikowanie i dystrybucja aplikacji

Usługa Google Play for Work jest integralną częścią procesu dystrybucji aplikacji i zarządzania nimi w ramach programu Android for Work. Wszystkie aplikacje należące do profilu służbowego, które zostały wdrożone na urządzeniach z programem Android for Work, pochodzą z usługi Play for Work. W celu zarządzania aplikacjami i ich wdrażania w Sklepie Play musisz zalogować się do witryny Google Play przy użyciu poświadczeń administratora w Twojej firmie odpowiednich do zarządzania w Google. Możesz zatwierdzać wdrożenia aplikacji dla systemu Android for Work, które będą pojawiać się w profilach służbowych urządzeń. Aplikacje te są synchronizowane z konsolą usługi Intune, która umożliwia ich wdrożenie i zarządzanie nimi. Aplikacje biznesowe opracowane w organizacji muszą zostać opublikowane w usłudze Play for Work przy użyciu konsoli firmy Google służącej do publikowania aplikacji systemu Android. Za pomocą konsoli publikowania aplikacji systemu Android należy skonfigurować aplikacje biznesowe pod kątem ograniczenia dostępu do danej organizacji.

Aplikacje można instalować bez udziału użytkownika i bez wymagania zezwolenia na **instalację z nieznanych źródeł**. Aby przeglądać oraz instalować opcjonalne lub dostępne aplikacje, użytkownicy mogą przeglądać na swoim urządzeniu zasoby sklepu Play for Work. Dowiedz się więcej o [wdrażaniu aplikacji dla programu Android for Work](https://docs.microsoft.com/intune/deploy-use/android-for-work-apps).

## <a name="app-configuration"></a>Konfiguracja aplikacji

Program Android for Work zapewnia infrastrukturę, która pozwala wdrażać parametry konfiguracji aplikacji w aplikacjach, które to umożliwiają. Określenie wartości konfiguracji dla aplikacji służbowych gwarantuje poprawność ustawień podczas pierwszego uruchamiania aplikacji przez użytkowników. Obsługa konfiguracji aplikacji wymaga od deweloperów aplikacji dla systemu Android projektowania swoich aplikacji w sposób umożliwiający korzystanie z zarządzanych wartości konfiguracji. Pozwala to określać i stosować ustawienia konfiguracji przy użyciu usługi Intune. Dowiedz się więcej o [ustawieniach konfiguracji aplikacji Android for Work](afw-app-configuration-policy.md).

## <a name="email-configuration"></a>Konfiguracja poczty e-mail

Inaczej niż w systemie iOS program Android for Work nie udostępnia domyślnej aplikacji poczty e-mail ani natywnego obiektu profilu poczty e-mail. Zamiast tego konfigurację poczty e-mail można ustawić, stosując ustawienia konfiguracji aplikacji do obsługujących je aplikacji poczty e-mail. W Sklepie Play są dostępne dwie aplikacje klienckie Exchange ActiveSync (EAS) obsługujące konfigurację aplikacji Android for Work: Gmail i Nine Work.

Usługa Intune udostępnia szablony konfiguracji dla aplikacji Gmail i Nine Work, gdy są one zarządzane jako aplikacje robocze. Pozostałe aplikacje poczty e-mail, które obsługują profile konfiguracji aplikacji, można konfigurować przy użyciu zasad konfiguracji aplikacji mobilnych.

Jeśli na urządzeniach z programem Android for Work korzystasz z dostępu warunkowego programu Exchange ActiveSync, do obsługi poczty e-mail musisz używać aplikacji Gmail lub Nine Work. Obsługiwana jest również aplikacja Microsoft Outlook dla systemu Android, a także wszystkie inne aplikacje poczty e-mail, które używają nowoczesnego uwierzytelniania za pośrednictwem biblioteki ADAL. Dowiedz się więcej o [profilach firmowej poczty e-mail](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).

## <a name="app-protection-policies"></a>Zasady ochrony aplikacji

Stosowane zasady ochrony aplikacji są w pełni obsługiwane w profilu służbowym i w profilu osobistym. Aplikacje biznesowe można opublikować przy użyciu konsoli publikowania aplikacji systemu Android, dostępnej pod adresem https://play.google.com/apps/publish. Konsola ta pozwala określić aplikacje jako prywatne w obrębie organizacji. Dowiedz się więcej o [ustawieniach zasad zgodności programu Android for Work](afw-compliance-policy-settings-in-microsoft-intune.md). Aby uzyskać ogólne informacje o zasadach ochrony aplikacji, zobacz [zasady aplikacji](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).

## <a name="vpn-profiles"></a>profile sieci VPN,

Obsługa sieci VPN działa podobnie do profilów sieci VPN systemu Android. Na potrzeby zarządzania w programie Android for Work dostępni są ci sami dostawcy sieci VPN oraz takie same podstawowe opcje konfiguracji z dwiema różnicami:

-  **Połączenia VPN ograniczone do profilu służbowego** — połączenia w sieci VPN są ograniczone tylko do aplikacji wdrożonych w profilu służbowym. Z połączenia VPN mogą korzystać tylko aplikacje zarządzane przez program Android for Work. Aplikacje osobiste zainstalowane na urządzeniu nie mogą używać zarządzanego połączenia VPN.

-  **Sieci VPN specyficzne dla aplikacji** — jeśli dostawca sieci VPN obsługuje konfigurację sieci VPN specyficznej dla aplikacji oraz umożliwia konfigurowanie sieci VPN dla aplikacji za pośrednictwem profilu konfiguracji aplikacji Android for Work, w usłudze Intune można skonfigurować sieć VPN specyficzną dla aplikacji. Informacje dotyczące obsługi tej funkcji można uzyskać u dostawcy sieci VPN. Dowiedz się więcej o [profilach połączeń VPN](vpn-connections-in-microsoft-intune.md).

## <a name="certificate-profiles"></a>Profile certyfikatów

Opcje konfiguracji profilów certyfikatów, które są dostępne w zarządzaniu systemem Android, są również dostępne dla urządzeń z programem Android for Work. Program Android for Work umożliwia korzystanie z rozszerzonych interfejsów API zarządzania certyfikatami. Rozszerzone zarządzanie certyfikatami pozwala korzystać z następujących funkcji:

- Zapewnia dyskretne i bezproblemowe wdrożenie certyfikatu z perspektywy użytkownika.
-  Zapewnia całkowite usunięcie wdrożonych certyfikatów w przypadku wycofania urządzenia z usługi Intune i usunięcia profilu służbowego.
-  Usprawnia obsługę komunikatów, co pozwala poinformować użytkowników o wdrożeniu certyfikatu i skonfigurowaniu go przez dział IT za pomocą usługi zarządzania.

Dowiedz się więcej o [profilach certyfikatów](secure-resource-access-with-certificate-profiles.md).

## <a name="wi-fi-profiles"></a>Profile sieci Wi-Fi

Profile sieci Wi-Fi zarządzane przez program Android for Work są usuwane po wycofaniu urządzenia z usługi Intune i usunięciu profilu służbowego. Dowiedz się więcej o [profilach sieci Wi-Fi](wi-fi-connections-in-microsoft-intune.md).

## <a name="next-steps"></a>Następne kroki
[Włączanie rejestrowania w programie Android for Work](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-android-for-work)

[Wdrażanie aplikacji dla programu Android for Work](https://docs.microsoft.com/en-us/intune/deploy-use/android-for-work-apps)

