---
title: Korzystanie z urządzeń z systemem Windows Holographic przy użyciu usługi Microsoft Intune — Azure | Microsoft Docs
description: Przy użyciu usługi Microsoft Intune możesz wykonywać różne zadania dotyczące urządzeń HoloLens i urządzeń z systemem Windows Holographic for Business oraz nimi zarządzać, w tym konfigurować aplikację Portal firmy, tworzyć zasady zgodności, dostosowywać ustawienia identyfikatora URI OMA, wdrażać aplikacje, kategoryzować urządzenia w grupach, tworzyć profile, ograniczać urządzenia, włączać aktualizacje oprogramowania, ustawiać warunki i postanowienia, konfigurować ustawienia sieci VPN i Wi-Fi, a także używać funkcji Hello dla firm.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/18/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 98d4608864512ae437441bf144e17fce4545a921
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57390566"
---
# <a name="manage-and-use-different-device-management-features-on-windows-holographic-and-hololens-devices-with-intune"></a>Zarządzanie urządzeniami z systemem Windows Holographic i urządzeniami HoloLens oraz korzystanie z różnych funkcji zarządzania urządzeniami przy użyciu usługi Intune

Usługa Microsoft Intune oferuje wiele funkcji ułatwiających zarządzanie urządzeniami z systemem Windows Holographic for Business, takimi jak [Microsoft HoloLens](https://docs.microsoft.com/hololens/). Przy użyciu usługi Intune można potwierdzić, że urządzenia są zgodne z zasadami Twojej organizacji, a urządzenie można dostosować, dodając profil sieci VPN lub Wi-Fi. Kolejną istotną funkcją jest korzystanie z urządzenia jak z kiosku i uruchamianie określonej aplikacji lub określonego zestawu aplikacji.

Zadania przedstawione w tym artykule ułatwiają zarządzanie urządzeniami z systemem Windows Holographic for Business, ich dostosowywanie oraz zabezpieczanie, z uwzględnieniem aktualizacji oprogramowania i korzystania z funkcji Windows Hello dla firm.

Aby korzystać z urządzeń z systemem Windows Holographic przy użyciu usługi Intune, utwórz profil uaktualniania wersji. Ten profil uaktualniania zapewnia uaktualnienie urządzeń z systemem Windows Holographic do systemu Windows Holographic for Business. W przypadku urządzeń Microsoft HoloLens możesz kupić wersję Commercial Suite, aby uzyskać wymaganą licencję na uaktualnienie. Aby uzyskać więcej informacji, zobacz [Uaktualnianie urządzeń z systemem Windows Holographic do systemu Windows Holographic for Business](holographic-upgrade.md).

## <a name="azure-active-directory"></a>Azure Active Directory

Usługa Azure Active Directory (AD) jest bardzo pomocna w zarządzaniu i sterowaniu urządzeniami z systemem Windows Holographic for Business. Usługi Intune i Azure AD umożliwiają: 

- **[Dołączanie urządzeń do usługi Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan)**: w usłudze Azure Active Directory (AD) możesz dodawać służbowe urządzenia z systemem Windows 10, w tym urządzenia z systemem Windows Holographic for Business. Ta funkcja umożliwia usłudze Azure AD sterowanie urządzeniem. Pomaga ona potwierdzić, że użytkownicy uzyskują dostęp do zasobów firmy z urządzeń, które spełniają Twoje standardy zabezpieczeń i zgodności.

  Artykuł [Zarządzanie urządzeniami w usłudze Azure AD](https://docs.microsoft.com/azure/active-directory/devices/overview) zawiera więcej szczegółowych informacji.

- **[Rejestrację zbiorczą urządzeń z systemem Windows](windows-bulk-enroll.md)**: możesz dołączyć dużą liczbę nowych urządzeń z systemem Windows do usługi Azure Active Directory (AD) i Intune. W ramach tej funkcji, nazywanej rejestrowaniem zbiorczym, są używane pakiety aprowizacji. Te pakiety umożliwiają dołączenie urządzeń z systemem Windows Holographic for Business do dzierżawy usługi Azure AD i zarejestrowanie ich w usłudze Intune.

## <a name="company-portal"></a>Portal firmy
**[Konfigurowanie aplikacji Portal firmy](company-portal-app.md)**

Usługa Intune udostępnia aplikację Portal firmy pozwalającą użytkownikom uzyskać dostęp do danych firmy, zarejestrować urządzenia, zainstalować aplikacje, skontaktować się z działem IT w organizacji i wykonywać inne zadania. Możesz dostosować aplikację Portal firmy dla urządzeń z systemem Windows Holographic for Business.

Przy użyciu aplikacji Portal firmy możesz również uruchomić następujące akcje:

- [Usuwanie urządzenia z usługi Intune](/intune-user-help/unenroll-your-device-from-intune-windows) przy użyciu aplikacji Ustawienia lub Portal firmy
- [Zmienianie nazwy urządzenia](/intune-user-help/rename-your-device-cpapp)
- [Instalowanie aplikacji](/intune-user-help/install-apps-cpapp-windows) na urządzeniu
- [Ręczne synchronizowanie urządzeń](/intune-user-help/sync-your-device-manually-windows) z aplikacji Ustawienia lub aplikacji Portal firmy

## <a name="compliance-policy"></a>Zasady zgodności
**[Tworzenie zasad zgodności urządzenia](compliance-policy-create-windows.md)**

Zasady zgodności to reguły i ustawienia, które urządzenia muszą spełnić, aby były zgodne. Użyj tych zasad z dostępem warunkowym, aby zablokować dostęp do zasobów firmy dla urządzeń, które nie są zgodne. W usłudze Intune utwórz zasady zgodności, aby umożliwić lub zablokować dostęp dla urządzeń z systemem Windows Holographic for Business. Na przykład możesz utworzyć zasady wymagające włączenia funkcji Bitlocker.

Zobacz też **[Wprowadzenie do zasad zgodności](device-compliance-get-started.md)**.

## <a name="deploy-and-manage-apps"></a>Wdrażanie aplikacji i zarządzanie nimi
**[Dodawanie aplikacji do usługi Intune](apps-add.md)**

Przy użyciu usługi Intune możesz dodawać aplikacje do urządzeń z systemem Windows Holographic for Business. Istnieje wiele sposobów wdrażania aplikacji, w tym:

- [Dodawanie aplikacji ze sklepu Microsoft Store](store-apps-windows.md)
- [Dodawanie utworzonej aplikacji](lob-apps-windows.md)
- [Przypisywanie aplikacji do grup](apps-deploy.md)

Usługa Microsoft Intune może wdrażać aplikacje uniwersalne systemu Windows na urządzeniach Microsoft HoloLens z systemem Windows Holographic for Business. Możesz bezpośrednio przekazać pakiety aplikacji w witrynie Intune Azure Portal lub wdrożyć je ze sklepu Microsoft Store dla Firm. Aby uzyskać więcej informacji o związanych z tym obszarach, zobacz następujące artykuły:
- Jeśli chcesz wdrażać aplikacje biznesowe (LOB, Line-of-Business) za pomocą witryny Intune Azure Portal, zobacz temat [Sposób dodawania aplikacji biznesowych systemu Windows do usługi Microsoft Intune](lob-apps-windows.md).

    > [!NOTE]
    > Maksymalny rozmiar pakietu dozwolony przez usługę Intune to 8 GB. Ten rozmiar pakietu jest dostępny tylko dla aplikacji biznesowych przekazanych do usługi Intune.

- Jeśli chcesz wdrażać aplikacje za pomocą portalu Microsoft Store dla Firm, zobacz temat [Jak zarządzać aplikacjami zakupionymi w sklepie Microsoft Store dla Firm za pomocą usługi Microsoft Intune](windows-store-for-business.md). 
- Aby dowiedzieć się więcej o zarządzaniu aplikacjami za pomocą usługi Microsoft Intune, zobacz temat [Co to jest zarządzanie aplikacjami w usłudze Microsoft Intune](app-management.md).
- Aby dowiedzieć się więcej na temat tworzenia aplikacji dla urządzeń Microsoft HoloLens, zobacz temat [Aplikacje rzeczywistości mieszanej dla urządzeń Microsoft HoloLens](https://www.microsoft.com/hololens/apps). 

> [!NOTE]
> Urządzenia HoloLens z systemem Windows 10 Holographic dla firm 1607 nie obsługują aplikacji licencjonowanych online ze sklepu Microsoft Store dla Firm. Aby dowiedzieć się więcej, zobacz temat [Instalowanie aplikacji na urządzeniach HoloLens](https://docs.microsoft.com/hololens/hololens-install-apps).

## <a name="device-actions"></a>Działania na urządzeniach
Usługa Intune oferuje pewne wbudowane działania umożliwiające administratorom IT wykonywanie różnorodnych zadań lokalnie na urządzeniu lub zdalnie za pośrednictwem usługi Intune w witrynie Azure Portal. Użytkownicy mogą też w aplikacji Portal firmy usługi Intune wydać polecenie zdalne do urządzeń będących własnością prywatną i zarejestrowanych w usłudze Intune.

W przypadku urządzeń z systemem Windows Holographic for Business można korzystać z następujących działań: 

- **[Czyszczenie](devices-wipe.md#wipe)**: działanie **Czyszczenie** usuwa urządzenie z usługi Intune i przywraca na nim domyślne ustawienia fabryczne. Można zastosować to działanie przed przekazaniem urządzenia nowemu użytkownikowi albo w przypadku kradzieży lub utraty urządzenia.

- **[Wycofaj](devices-wipe.md#retire)**: działanie **Wycofaj** powoduje usunięcie urządzenia z usługi Intune. Powoduje ono również usunięcie z zarządzanej aplikacji danych, ustawień i profilów poczty e-mail przypisanych przez usługę Intune. Dane osobiste użytkownika pozostają na urządzeniu.

- **[Synchronizacja urządzeń w celu pobrania najnowszych zasad i akcji](device-sync.md)**: działanie **Synchronizacja** wymusza natychmiastowe zaewidencjonowanie urządzenia w usłudze Intune. Zaewidencjonowane urządzenie natychmiast odbiera wszelkie przypisane oczekujące akcje lub zasady. Ta funkcja ułatwia weryfikowanie przypisanych zasad i rozwiązywanie dotyczących ich problemów bez konieczności czekania na następne zaplanowane zaewidencjonowanie.

Artykuł **[Co to jest zarządzanie urządzeniami w usłudze Microsoft Intune?](device-management.md)** to dobre źródło informacji na temat zarządzania urządzeniami w witrynie Azure Portal. 

## <a name="device-categories-and-groups"></a>Kategorie i grupy urządzeń
**[Kategoryzowanie urządzeń do grup](device-group-mapping.md)**

Przy użyciu usługi Intune możesz utworzyć kategorie urządzeń, aby automatycznie dodawać urządzenia do grup w oparciu o utworzone kategorie, np. Sprzedaż, Księgowość, Zasoby ludzkie itd. Koncepcja ta ma na celu ułatwienie zarządzania urządzeniami z systemem Windows Holographic for Business.

## <a name="device-configuration-profiles"></a>Profile konfiguracji urządzeń 
**[Wprowadzenie do profilów konfiguracji](device-profiles.md) i [Tworzenie własnego profilu](device-profile-create.md)**

Usługa Intune obejmuje ustawienia i funkcje, które można włączać lub wyłączać na różnych urządzeniach w organizacji. Te ustawienia i funkcje są zarządzane przy użyciu profilów. Na przykład możesz utworzyć profil włączający Cortanę lub używający usługi Windows Defender Smart Screen na urządzeniach z systemem Windows Holographic for Business.

W profilach możesz użyć identyfikatora URI OMA, aby dostosować wybrane ustawienia, utworzyć ograniczenia urządzeń i skonfigurować wirtualną sieć prywatną (VPN) oraz sieć Wi-Fi.

#### <a name="custom-device-settingscustom-settings-windows-holographicmd"></a>[Niestandardowe ustawienia urządzenia](custom-settings-windows-holographic.md)

Aby skonfigurować ustawienia identyfikatora URI OMA (Open Mobile Alliance Uniform Resource Identifier), możesz utworzyć profil niestandardowy w usłudze Intune. Użyj ustawień identyfikatora URI OMA, aby kontrolować różne funkcje urządzeń z systemem Windows Holographic for Business, np. włączać sieć VPN lub sprawdzać aktualizacje w witrynie Microsoft Update.

#### <a name="configure-kiosk-modekiosk-settings-holographicmd"></a>[Konfigurowanie trybu kiosku](kiosk-settings-holographic.md)

Za pomocą udostępnionych funkcji lub funkcji komputera gościa usługi Intune możesz skonfigurować urządzenia z systemem Windows Holographic for Business, aby były uruchamiane jako kiosk. Na tych urządzeniach może działać jedna aplikacja (tryb kiosku z jedną aplikacją) lub wiele aplikacji (tryb kiosku z wieloma aplikacjami).

#### <a name="device-restrictionsdevice-restrictions-windows-holographicmd"></a>[Ograniczenia dotyczące urządzeń](device-restrictions-windows-holographic.md)

Ograniczenia dotyczące urządzeń umożliwiają kontrolowanie różnych ustawień i funkcji na urządzeniach, w tym wymagania hasła, instalowania aplikacji ze sklepu [Microsoft Store](https://www.microsoft.com/store/apps/windows?icid=CNavAppsWindowsApps), włączania funkcji Bluetooth i innych. Ograniczenia te są tworzone w profilu usługi Intune. Profil ten można zastosować do wielu urządzeń z systemem Windows Holographic for Business.

#### <a name="configure-vpnvpn-settings-configuremd"></a>[Konfigurowanie sieci VPN](vpn-settings-configure.md)

Wirtualne sieci prywatne (VPN) zapewniają użytkownikom bezpieczny dostęp zdalny do sieci firmowej. W usłudze Intune możesz utworzyć profil sieci VPN, który obejmuje konkretne ustawienia dla urządzeń z systemem Windows Holographic for Business. Na przykład możesz utworzyć profil sieci VPN, aby wszystkie urządzenia z systemem Windows Holographic for Business używały sieci VPN firmy Citrix jako typu połączenia.

#### <a name="configure-wi-fiwi-fi-settings-configuremd"></a>[Konfigurowanie sieci Wi-Fi](wi-fi-settings-configure.md)

Możesz też utworzyć profil sieci Wi-Fi w usłudze Intune, aby przypisać ustawienia sieci bezprzewodowej do urządzeń z systemem Windows Holographic for Business. Jeśli przypiszesz profil sieci Wi-Fi, użytkownicy końcowi otrzymają dostęp do sieci firmowej bez żadnej konfiguracji sieci. Na przykład możesz utworzyć sieć Wi-Fi przeznaczoną wyłącznie dla urządzeń z systemem Windows Holographic for Business.

## <a name="shared-multi-user-devices"></a>Urządzenia udostępnione używane przez wielu użytkowników
[Urządzenia udostępnione](shared-user-device-settings-windows-holographic.md)

Urządzenia z systemem Windows Holographic for Business, takie jak Microsoft HoloLens, mogą mieć wielu użytkowników. Usługa Intune obejmuje ustawienia do kontrolowania różnych funkcji tych urządzeń udostępnionych, takich jak zarządzanie zasilaniem, użycie magazynu lokalnego i zarządzanie kontami. Profile konfiguracji można również zastosować do urządzeń z różnymi systemami operacyjnymi. Na przykład jedna grupa urządzeń może zawierać urządzenia z systemami RS2 i RS3.

## <a name="software-updates"></a>Aktualizacje oprogramowania
**[Zarządzanie aktualizacjami oprogramowania](windows-update-for-business-configure.md)**

Usługa Intune obejmuje funkcję zwaną strefami aktualizacji dla urządzeń z systemem Windows 10. Te strefy aktualizacji obejmują grupę ustawień, które określają sposób instalacji aktualizacji. Na przykład możesz utworzyć okno obsługi, aby zainstalować aktualizacje lub wybrać opcję ponownego uruchomienia po zainstalowaniu aktualizacji. Strefę aktualizacji można zastosować do wielu urządzeń z systemem Windows Holographic for Business.

## <a name="terms-and-conditions"></a>Warunki i postanowienia
**[Ustawianie warunków i postanowień obowiązujących w firmie na potrzeby dostępu użytkowników](terms-and-conditions-create.md)**

Zanim użytkownicy zarejestrują urządzenia i uzyskają dostęp do aplikacji firmowych, w tym poczty e-mail, możesz wymagać od użytkowników akceptacji warunków i postanowień obowiązujących w firmie. W usłudze Intune definiujesz sposób wyświetlania warunków i postanowień w aplikacji Portal firmy, a także przypisywania tych warunków i postanowień do urządzeń z systemem Windows Holographic for Business.

## <a name="windows-hello-for-business"></a>Windows Hello for Business
**[Korzystanie z usługi Windows Hello dla firm](windows-hello.md)**

Usługa Hello dla firm to alternatywna metoda logowania korzystająca z konta usługi Azure Active Directory w celu zastąpienia hasła, karty inteligentnej lub wirtualnej karty inteligentnej. Dzięki usłudze Hello dla firm urządzenia z systemem Windows Holographic for Business mogą logować się przy użyciu numeru PIN o ustawionej minimalnej długości.
