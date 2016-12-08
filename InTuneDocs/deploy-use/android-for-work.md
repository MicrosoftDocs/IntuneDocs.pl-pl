---
title: "Program Android for Work — informacje | Microsoft Intune"
description: "Zarządzany przez usługę Intune program Android for Work udostępnia dodatkowe funkcje zarządzania i ochrony prywatności, które ułatwiają użytkownikom korzystanie z urządzeń z systemem Android w celach służbowych."
keywords: 
author: nathbarn
manager: angrobe
ms.date: 11/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aa0002d9-f5a0-466e-98ac-3970cb77e3a2
translationtype: Human Translation
ms.sourcegitcommit: 83914246bde673b188ca3f7d9cf50b4d0de2edd4
ms.openlocfilehash: 127db326fc96625c719b8136964bae014a904b3d


---

# <a name="manage-android-for-work-devices-with-intune"></a>Zarządzanie urządzeniami z programem Android for Work za pomocą usługi Intune

Program Android for Work zawiera zestaw funkcji i usług dostępnych na urządzeniach z systemem Android. Umożliwiają one korzystanie z dodatkowych funkcji zarządzania i ochrony prywatności osobom, które używają urządzeń z systemem Android w celach służbowych. Usługa Intune ułatwia wdrażanie aplikacji i zasobów firmowych na urządzeniach z programem Android for Work, co zapewnia oddzielenie informacji osobistych od danych służbowych. Po pomyślnym wdrożeniu aplikacje oraz dane, z których korzystają te aplikacje, są używane wyłącznie w środowisku programu Android for Work zaimplementowanym na danym urządzeniu.

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

## <a name="supported-devices"></a>Obsługiwane urządzenia

Program Android for Work wymaga nowszego sprzętu, ponieważ wiele funkcji zarządzania korzysta z możliwości zapewnianych przez nowszy system operacyjny Android. Program Android for Work jest obecnie obsługiwany na urządzeniach z systemem Android 5.0 Lollipop lub nowszym, które umożliwiają używanie profilów służbowych. W przypadku urządzeń, które nie zapewniają natywnej obsługi programu Android for Work, dostępne są konwencjonalne funkcje zarządzania systemem Android. Dowiedz się więcej o [wymaganiach programu Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

## <a name="onboarding"></a>Dołączanie

Aby zarejestrować urządzenia z programem Android for Work, należy wykonać pewne czynności w zakresie dołączenia. Umożliwiają one nawiązanie połączenia między dzierżawą usługi Intune a usługą Play for Work firmy Google, które jest integralną częścią procesu dystrybucji aplikacji Android for Work i zarządzania nią. Dowiedz się więcej o [włączaniu rejestrowania w programie Android for Work](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-android-for-work).

## <a name="work-profile-management"></a>Zarządzanie profilami służbowymi

Zarządzanie urządzeniem z programem Android for Work przy użyciu usługi Intune nie obejmuje administrowania całego urządzenia. Zarządzanie dotyczy tylko profilu służbowego utworzonego podczas rejestracji. Wszystkie aplikacje, które są wdrażane na urządzeniu za pomocą usługi Intune, są częścią profilu służbowego. Aplikacje należące do profilu służbowego są oznaczone ikoną pomarańczowej aktówki. Pozwala to odróżnić aplikacje firmowe od aplikacji osobistych zainstalowanych na urządzeniu. Wszystkie aplikacje i dane, które nie są objęte działaniem programu Android for Work, są zarządzane przez użytkownika końcowego i przeznaczone do użytku osobistego. Użytkownicy mogą instalować na urządzeniu dowolne wybrane przez siebie aplikacje jako osobiste, natomiast administratorzy mogą zarządzać akcjami wchodzącymi w zakres profilu służbowego i monitorować je.

## <a name="app-publishing-and-distribution"></a>Publikowanie i dystrybucja aplikacji

Usługa Google Play for Work jest integralną częścią procesu dystrybucji aplikacji i zarządzania nimi. Wszystkie aplikacje należące do profilu służbowego, które zostały wdrożone na urządzeniach z programem Android for Work, pochodzą z usługi Play for Work. Aby wdrażać aplikacje ze Sklepu Play i zarządzać nimi, należy zalogować się w witrynie sieci Web usługi Play for Work jako administrator usługi Intune i zatwierdzić aplikacje dla dzierżawy usługi Intune. Aplikacje te są synchronizowane z konsolą usługi Intune, która umożliwia ich wdrożenie i zarządzanie nimi. Aplikacje biznesowe opracowane w organizacji muszą zostać opublikowane w usłudze Play for Work przy użyciu konsoli firmy Google służącej do publikowania aplikacji systemu Android. Za pomocą konsoli publikowania aplikacji systemu Android należy skonfigurować aplikacje biznesowe pod kątem ograniczenia dostępu do danej organizacji.

Instalowanie aplikacji przebiega bez udziału użytkownika i nie wymaga zezwolenia na **instalację z nieznanych źródeł**. Odpowiednia aplikacja, pochodząca ze Sklepu Play, umożliwia użytkownikom przeglądanie oraz instalowanie opcjonalnych, dostępnych aplikacji. Dowiedz się więcej o [wdrażaniu aplikacji dla programu Android for Work](https://docs.microsoft.com/en-us/intune/deploy-use/android-for-work-apps).

## <a name="app-configuration"></a>Konfiguracja aplikacji

Program Android for Work zapewnia infrastrukturę, która pozwala wdrażać parametry konfiguracji aplikacji w aplikacjach, które to umożliwiają. Określenie wartości konfiguracji dla aplikacji służbowych gwarantuje poprawność ustawień podczas pierwszego uruchamiania aplikacji przez użytkowników. Obsługa konfiguracji aplikacji wymaga od deweloperów aplikacji dla systemu Android projektowania swoich aplikacji w sposób umożliwiający korzystanie z zarządzanych wartości konfiguracji. Pozwala to określać i stosować ustawienia konfiguracji przy użyciu usługi Intune. Dowiedz się więcej o [ustawieniach konfiguracji aplikacji Android for Work](afw-app-configuration-policy.md).

## <a name="email-configuration"></a>Konfiguracja poczty e-mail

Inaczej niż w systemie iOS program Android for Work nie udostępnia domyślnej aplikacji poczty e-mail ani natywnego obiektu profilu poczty e-mail. Zamiast tego konfigurację poczty e-mail można ustawić, stosując ustawienia konfiguracji aplikacji do obsługujących je aplikacji poczty e-mail. W Sklepie Play są dostępne dwie aplikacje klienckie Exchange ActiveSync (EAS) obsługujące konfigurację aplikacji Android for Work: Gmail i Nine Work.

Usługa Intune udostępnia szablony konfiguracji dla aplikacji Gmail i Nine Work. Pozostałe aplikacje poczty e-mail, które obsługują profile konfiguracji aplikacji, można konfigurować przy użyciu zasad konfiguracji aplikacji mobilnych.

Jeśli na urządzeniach z programem Android for Work korzystasz z dostępu warunkowego programu EAS, do obsługi poczty e-mail musisz używać aplikacji Gmail lub Nine Work. Obsługiwana jest również aplikacja Microsoft Outlook dla systemu Android, a także wszystkie inne aplikacje poczty e-mail, które używają nowoczesnego uwierzytelniania za pośrednictwem biblioteki ADAL. Dowiedz się więcej o [profilach firmowej poczty e-mail](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).

## <a name="mobile-app-management-policies"></a>Zasady zarządzania aplikacjami mobilnymi

Profile służbowy i osobisty zapewniają pełną obsługę zasad ograniczeń stosowanych do aplikacji objętych zarządzaniem aplikacjami mobilnymi. Aplikacje biznesowe można opublikować przy użyciu konsoli publikowania aplikacji systemu Android, dostępnej pod adresem https://play.google.com/apps/publish. Konsola ta pozwala określić aplikacje jako prywatne w obrębie organizacji. Dowiedz się więcej o [ustawieniach zasad zgodności](afw-compliance-policy-settings-in-microsoft-intune.md). Aby uzyskać więcej informacji, zobacz [Zasady zarządzania aplikacjami mobilnymi](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).

## <a name="vpn-profiles"></a>profile sieci VPN,

Obsługa sieci VPN działa podobnie do profilów sieci VPN systemu Android. Dostępni są ci sami dostawcy sieci VPN i te same opcje konfiguracji podstawowej. Istnieją dwie podstawowe różnice:

1.  **Połączenia VPN ograniczone do profilu służbowego** — połączenia w sieci VPN obejmują tylko aplikacje wdrożone w profilu służbowym. Z połączenia VPN mogą korzystać tylko aplikacje zarządzane przez program Android for Work. Aplikacje osobiste zainstalowane na urządzeniu nie mogą używać zarządzanego połączenia VPN.

2.  **Sieci VPN specyficzne dla aplikacji** — jeśli dostawca sieci VPN obsługuje konfigurację sieci VPN specyficznej dla aplikacji oraz umożliwia konfigurowanie sieci VPN dla aplikacji za pośrednictwem profilu konfiguracji aplikacji Android for Work, w usłudze Intune można skonfigurować sieć VPN specyficzną dla aplikacji. Informacje dotyczące obsługi tej funkcji można uzyskać u dostawcy sieci VPN. Dowiedz się więcej o [profilach połączeń VPN](vpn-connections-in-microsoft-intune.md).

## <a name="certificate-profiles"></a>Profile certyfikatów

Opcje konfiguracji profilów certyfikatów, które są dostępne w tradycyjnym zarządzaniu systemem Android, są również dostępne dla urządzeń z programem Android for Work. Program Android for Work umożliwia korzystanie z rozszerzonych interfejsów API zarządzania certyfikatami. Rozszerzone zarządzanie certyfikatami pozwala korzystać z następujących funkcji:

1.  Zapewnia dyskretne i bezproblemowe wdrożenie certyfikatu z perspektywy użytkownika.

2.  Zapewnia całkowite usunięcie wdrożonych certyfikatów w przypadku wycofania urządzenia z usługi Intune i usunięcia profilu służbowego.

3.  Usprawnia obsługę komunikatów, co pozwala poinformować użytkowników o wdrożeniu certyfikatu i skonfigurowaniu go przez dział IT za pomocą usługi zarządzania.

Dowiedz się więcej o [profilach certyfikatów](secure-resource-access-with-certificate-profiles.md).

## <a name="wi-fi-profiles"></a>Profile sieci Wi-Fi

W przypadku zarządzania profilami sieci Wi-Fi przez program Android for Work gwarantowane jest usunięcie tych profilów po wycofaniu urządzenia z usługi Intune i usunięciu profilu służbowego. Dowiedz się więcej o [profilach sieci Wi-Fi](wi-fi-connections-in-microsoft-intune.md).

## <a name="next-steps"></a>Następne kroki
[Włączanie rejestrowania w programie Android for Work](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-android-for-work)
[Wdrażanie aplikacji dla programu Android for Work](https://docs.microsoft.com/en-us/intune/deploy-use/android-for-work-apps)



<!--HONumber=Nov16_HO5-->


