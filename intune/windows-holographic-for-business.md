---
title: Zarządzanie urządzeniami z systemem Windows Holographic przy użyciu usługi Microsoft Intune — Azure | Microsoft Docs
description: Przy użyciu usługi Microsoft Intune możesz wykonywać różne zadania wobec urządzeń z systemem Windows Holographic for Business, w tym konfigurować aplikację Portal firmy, tworzyć zasady zgodności, dostosowywać ustawienia identyfikatora URI OMA, wdrażać aplikacje, kategoryzować urządzenia w grupach, tworzyć profile, ograniczać urządzenia, włączać aktualizacje oprogramowania, ustawiać warunki i postanowienia, konfigurować ustawienia sieci VPN i Wi-Fi, a także używać funkcji Hello dla firm.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 4/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 45d8f5051d9663273c6515717b7930145ff8a964
ms.sourcegitcommit: 2773f388f50654366197a95a6838306f70fc18b8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/18/2018
---
# <a name="customize-devices-running-windows-holographic-with-intune"></a>Dostosowywanie urządzeń z systemem Windows Holographic przy użyciu usługi Intune

Usługa Microsoft Intune obsługuje urządzenia z systemem Windows Holographic for Business, takie jak [Microsoft HoloLens](https://docs.microsoft.com/en-us/hololens/).

Aby zarządzać urządzeniami z systemem Windows Holographic przy użyciu usługi Microsoft Intune, musisz utworzyć profil uaktualniania wersji. Ten profil uaktualniania zapewnia uaktualnienie urządzeń z systemem Windows Holographic do systemu Windows Holographic for Business. W przypadku urządzeń Microsoft HoloLens możesz kupić wersję Commercial Suite, aby uzyskać wymaganą licencję na uaktualnienie. Aby uzyskać więcej informacji, zobacz [Uaktualnianie urządzeń z systemem Windows Holographic do systemu Windows Holographic for Business](holographic-upgrade.md).

Aby uzyskać pomoc w zarządzaniu i dostosowywaniu urządzeń z systemem Windows Holographic for Business, możesz użyć zadań opisanych w tym artykule. Na przykład możesz zarządzać aktualizacjami oprogramowania, konfigurować ustawienia sieci VPN i inne.

## <a name="company-portal"></a>Portal firmy
**[Konfigurowanie aplikacji Portal firmy](company-portal-app.md)**

Usługa Intune zawiera aplikację Portal firmy, w której użytkownicy uzyskują dostęp do danych firmy, rejestrują urządzenia, instalują aplikacje, łączą się z działem IT i wykonują inne czynności. Możesz dostosować aplikację Portal firmy dla urządzeń z systemem Windows Holographic for Business.

## <a name="compliance-policy"></a>Zasady zgodności
**[Tworzenie zasad zgodności urządzenia](compliance-policy-create-windows.md)**

Zasady zgodności to reguły i ustawienia, które urządzenia muszą spełnić, aby były zgodne. Możesz użyć tych zasad z dostępem warunkowym, aby zablokować dostęp do zasobów firmy dla urządzeń, które nie są zgodne. W usłudze Intune możesz utworzyć zasady zgodności, aby umożliwić lub zablokować dostęp dla urządzeń z systemem Windows Holographic for Business. Na przykład możesz utworzyć zasady wymagające włączenia funkcji Bitlocker.

Zobacz też **[Wprowadzenie do zasad zgodności](device-compliance-get-started.md)**.

## <a name="deploy-and-manage-apps"></a>Wdrażanie aplikacji i zarządzanie nimi
**[Dodawanie aplikacji do usługi Intune](apps-add.md)**

Przy użyciu usługi Intune możesz dodawać aplikacje do urządzeń z systemem Windows Holographic for Business. Istnieje wiele sposobów wdrażania aplikacji, w tym:

- [Dodawanie aplikacji ze sklepu Microsoft Store](store-apps-windows.md)
- [Dodawanie utworzonej aplikacji](lob-apps-windows.md)
- [Przypisywanie aplikacji do grup](apps-deploy.md)

Usługa Microsoft Intune może wdrażać aplikacje uniwersalne systemu Windows na urządzeniach Microsoft HoloLens z systemem Windows Holographic for Business. Możesz bezpośrednio przekazać pakiety aplikacji w witrynie Intune Azure Portal lub wdrożyć je ze sklepu Microsoft Store dla Firm. Aby uzyskać więcej informacji o związanych z tym obszarach, zobacz następujące tematy:
- Jeśli chcesz wdrażać aplikacje biznesowe (LOB, Line-of-Business) za pomocą witryny Intune Azure Portal, zobacz temat [Sposób dodawania aplikacji biznesowych systemu Windows do usługi Microsoft Intune](lob-apps-windows.md).
- Jeśli chcesz wdrażać aplikacje za pomocą portalu Microsoft Store dla Firm, zobacz temat [Jak zarządzać aplikacjami zakupionymi w sklepie Microsoft Store dla Firm za pomocą usługi Microsoft Intune](windows-store-for-business.md). 
- Aby dowiedzieć się więcej o zarządzaniu aplikacjami za pomocą usługi Microsoft Intune, zobacz temat [Co to jest zarządzanie aplikacjami w usłudze Microsoft Intune](app-management.md).
- Aby dowiedzieć się więcej na temat tworzenia aplikacji dla urządzeń Microsoft HoloLens, zobacz temat [Aplikacje rzeczywistości mieszanej dla urządzeń Microsoft HoloLens](https://www.microsoft.com/hololens/apps). 

> [!NOTE]
> Urządzenia HoloLens z systemem Windows 10 Holographic dla firm 1607 nie obsługują aplikacji licencjonowanych online ze sklepu Microsoft Store dla Firm. Aby dowiedzieć się więcej, zobacz temat [Instalowanie aplikacji na urządzeniach HoloLens](https://docs.microsoft.com/en-us/hololens/hololens-install-apps).


## <a name="device-categories-and-groups"></a>Kategorie i grupy urządzeń
**[Kategoryzowanie urządzeń do grup](device-group-mapping.md)**

Przy użyciu usługi Intune możesz utworzyć kategorie urządzeń, aby automatycznie dodawać urządzenia do grup w oparciu o utworzone kategorie, np. Sprzedaż, Księgowość, Zasoby ludzkie itd. Koncepcja ta ma na celu ułatwienie zarządzania urządzeniami z systemem Windows Holographic for Business.

## <a name="device-configuration-profiles"></a>Profile konfiguracji urządzeń 
**[Wprowadzenie do profilów konfiguracji](device-profiles.md) i [Tworzenie własnego profilu](device-profile-create.md)**

Usługa Intune obejmuje ustawienia i funkcje, które można włączać lub wyłączać na różnych urządzeniach w organizacji. Te ustawienia i funkcje są zarządzane przy użyciu profilów. Na przykład możesz utworzyć profil włączający Cortanę lub używający usługi Windows Defender Smart Screen na urządzeniach z systemem Windows Holographic for Business.

W profilach możesz użyć identyfikatora URI OMA, aby dostosować wybrane ustawienia, utworzyć ograniczenia urządzeń i skonfigurować wirtualną sieć prywatną (VPN) oraz sieć Wi-Fi.

#### <a name="custom-device-settingscustom-settings-windows-holographicmd"></a>[Niestandardowe ustawienia urządzenia](custom-settings-windows-holographic.md)

Aby skonfigurować ustawienia identyfikatora URI OMA (Open Mobile Alliance Uniform Resource Identifier), możesz utworzyć profil niestandardowy w usłudze Intune. Użyj ustawień identyfikatora URI OMA, aby kontrolować różne funkcje urządzeń z systemem Windows Holographic for Business, np. włączać sieć VPN lub sprawdzać aktualizacje w witrynie Microsoft Update.

#### <a name="device-restrictionsdevice-restrictions-windows-holographicmd"></a>[Ograniczenia dotyczące urządzeń](device-restrictions-windows-holographic.md)

Ograniczenia dotyczące urządzeń umożliwiają kontrolowanie różnych ustawień i funkcji na urządzeniach, w tym wymagania hasła, instalowania aplikacji ze sklepu [Microsoft Store](https://www.microsoft.com/store/apps/windows?icid=CNavAppsWindowsApps), włączania funkcji Bluetooth i innych. Ograniczenia te są tworzone w profilu usługi Intune. Profil ten można zastosować do wielu urządzeń z systemem Windows Holographic for Business.

#### <a name="configure-vpnvpn-settings-configuremd"></a>[Konfigurowanie sieci VPN](vpn-settings-configure.md)

Wirtualne sieci prywatne (VPN) zapewniają użytkownikom bezpieczny dostęp zdalny do sieci firmowej. W usłudze Intune możesz utworzyć profil sieci VPN, który obejmuje konkretne ustawienia dla urządzeń z systemem Windows Holographic for Business. Na przykład możesz utworzyć profil sieci VPN, aby wszystkie urządzenia z systemem Windows Holographic for Business używały sieci VPN firmy Citrix jako typu połączenia.

#### <a name="configure-wi-fiwi-fi-settings-configuremd"></a>[Konfigurowanie sieci Wi-Fi](wi-fi-settings-configure.md)

Możesz też utworzyć profil sieci Wi-Fi w usłudze Intune, aby przypisać ustawienia sieci bezprzewodowej do urządzeń z systemem Windows Holographic for Business. Jeśli przypiszesz profil sieci Wi-Fi, użytkownicy końcowi otrzymają dostęp do sieci firmowej bez żadnej konfiguracji sieci. Na przykład możesz utworzyć sieć Wi-Fi przeznaczoną wyłącznie dla urządzeń z systemem Windows Holographic for Business.

## <a name="software-updates"></a>Aktualizacje oprogramowania
**[Zarządzanie aktualizacjami oprogramowania](windows-update-for-business-configure.md)**

Usługa Intune obejmuje funkcję zwaną strefami aktualizacji dla urządzeń z systemem Windows 10. Te strefy aktualizacji obejmują grupę ustawień, które określają sposób instalacji aktualizacji. Na przykład możesz utworzyć okno obsługi, aby zainstalować aktualizacje lub wybrać opcję ponownego uruchomienia po zainstalowaniu aktualizacji. Strefę aktualizacji można zastosować do wielu urządzeń z systemem Windows Holographic for Business.

## <a name="terms-and-conditions"></a>Warunki i postanowienia
**[Ustawianie warunków i postanowień obowiązujących w firmie na potrzeby dostępu użytkowników](terms-and-conditions-create.md)**

Zanim użytkownicy będą mogli zarejestrować urządzenia i uzyskać dostęp do aplikacji firmowych, w tym poczty e-mail, możesz wymagać od użytkowników akceptacji warunków i postanowień obowiązujących w firmie. W usłudze Intune możesz zdefiniować sposób wyświetlania warunków i postanowień w aplikacji Portal firmy, a także przypisać te warunki i postanowienia do urządzeń z systemem Windows Holographic for Business.

## <a name="windows-hello-for-business"></a>Windows Hello for Business
**[Korzystanie z usługi Windows Hello dla firm](windows-hello.md)**

Usługa Hello dla firm to alternatywna metoda logowania korzystająca z konta usługi Azure Active Directory w celu zastąpienia hasła, karty inteligentnej lub wirtualnej karty inteligentnej. Dzięki usłudze Hello dla firm urządzenia z systemem Windows Holographic for Business mogą logować się przy użyciu numeru PIN o ustawionej minimalnej długości.
