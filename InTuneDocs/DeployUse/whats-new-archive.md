---
# required metadata

title: Archiwum nowości | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ed2db991-4729-49a7-a1e6-be2ffa0d03d1

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


## Wrzesień 2015
### Aktualizacje zarządzania urządzeniami przenośnymi i aplikacjami
**Wszystkie funkcje zarządzania systemem w usłudze Intune obsługują teraz system iOS 9**
Aby uzyskać szczegółowe informacje o możliwościach zarządzania systemem iOS 9, zobacz [ten wpis w blogu](http://blogs.technet.com/b/microsoftintune/archive/2015/09/09/day-zero-support-for-ios-9-with-intune.aspx)..

**Nowe zasady konfigurowania aplikacji mobilnych dla systemu iOS**
Użyj nowych zasad konfigurowania aplikacji mobilnych, aby automatycznie określić ustawienia, których aplikacja systemu iOS może potrzebować w przypadku jej uruchomienia. Na przykład możesz podać port sieci lub nazwę użytkownika. Aby uzyskać więcej informacji, zobacz [Konfigurowanie aplikacji przy użyciu zasad konfiguracji aplikacji mobilnych w usłudze Microsoft Intune](https://technet.microsoft.com/library/mt481447.aspx)..

**Łatwiejsze zarządzanie aplikacjami dla użytkowników systemu iOS 9**
 W tej wersji można obejmować już wdrożone aplikacje zarządzaniem użytkownikami systemu iOS 9 w ramach usługi Intune. W przypadku wcześniejszych wersji systemu iOS po wdrożeniu aplikacji, gdy jej niezarządzana wersja jest już zainstalowana na urządzeniu, nadal jest konieczne monitowanie użytkownika o ręczne odinstalowanie aplikacji, aby usługa Intune mogła zainstalować zarządzaną aplikację.

 Począwszy jednak od tej wersji usługi Intune możesz monitować użytkowników urządzeń z systemem iOS 9 o zezwolenie na przejęcie przez usługę Intune zarządzania aplikacją i zastosowanie przez tę usługę wszelkich odpowiednich zasad zarządzania aplikacjami mobilnymi.

 **Zarządzanie systemem Windows 10** — użyj nowych [ogólnych zasad konfiguracji systemu Windows 10](https://technet.microsoft.com/library/mt404697.aspx), aby skonfigurować hasło, urządzenie, przeglądarkę i inne ustawienia zarejestrowanych urządzeń z systemem Windows 10 i Windows 10 Mobile

 **Tworzenie i wdrażanie aplikacji na zarejestrowanych urządzeniach z systemem Windows 10** — nowy typ instalatora oprogramowania, Instalator Windows korzystający z zarządzania urządzeniami przenośnymi (&#42;.msi), umożliwia tworzenie i wdrażanie aplikacji Instalatora Windows na zarejestrowanych urządzeniach z systemem Windows 10. Szczegółowe informacje zawiera temat [Wprowadzenie do wdrażania aplikacji w usłudze Microsoft Intune](https://technet.microsoft.com/library/dn646955.aspx).

### Zmiany i aktualizacje aplikacji Portalu firmy oferowanych przez firmę Microsoft
W aplikacjach Portalu firmy w tej wersji wprowadzono następujące zmiany:

**iOS**
* Firma Microsoft automatycznie zbiera anonimowe dane dotyczące wydajności i korzystania z portalu firmy w celu ulepszania swoich produktów i usług. Użytkownicy końcowi mogą wyłączyć zbieranie danych za pomocą ustawienia Użycie danych na urządzeniu, lecz administratorzy nie kontrolują gromadzenia danych i nie mogą zmienić tego ustawienia określonego przez użytkownika końcowego.
* Obsługa pełnej rozdzielczości ekranu na telefonach iPhone 6 i 6 Plus.
* Wprowadzono poprawki błędów zwiększające bezpieczeństwo

### Co nowego w dokumentacji usługi Intune — wrzesień 2015
**Nowe tematy**

|Nazwa|Szczegóły|
|----|--------|
|[Ustawienia zasad konfiguracji systemu Windows 10 w usłudze Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx)|Są to nowe zasady konfiguracji, które umożliwiają zarządzanie ustawieniami i funkcjami na urządzeniach z systemem Windows 10 i Windows 10 Mobile.
| [Konfigurowanie aplikacji przy użyciu zasad konfiguracji aplikacji mobilnych w usłudze Microsoft Intune](https://technet.microsoft.com/library/mt481447.aspx)|To nowy typ zasad, który pozwala na automatyczne określanie ustawień, które mogą być wymagane, gdy użytkownik uruchomi aplikację systemu iOS. |

**Zaktualizowane tematy**

|Nazwa|Szczegóły|
|----|-------|
|[Używanie zasad do zarządzania komputerami i urządzeniami przenośnymi w usłudze Microsoft Intune](https://technet.microsoft.com/library/dn743712.aspx)|Zaktualizowano o najnowsze informacje ułatwiające poznanie i tworzenie zasad.|

## Sierpień 2015
### Aktualizacje zarządzania urządzeniami przenośnymi i aplikacjami
* **Warunki i postanowienia** dotyczące rejestracji w usłudze Intune i dostępu do firmy są [teraz zarządzane za pomocą zasad](https://technet.microsoft.com/library/mt405893.aspx). Możesz zastosować różne zestawy warunków i postanowień w celu spełnienia wymagań konkretnej grupy użytkowników. Na przykład możesz wdrożyć warunki i postanowienia w różnych językach dla grup użytkowników zdefiniowanych za pomocą lokalizacji geograficznych. Możesz także [zmodyfikować warunki i postanowienia](https://technet.microsoft.com/library/mt405893.aspx#BKMK_TCVers) , określając, czy numer wersji ma zostać zwiększony, co powoduje, że użytkownicy będą musieli się zgodzić na nowe warunki i postanowienia zanim będą mogli używać portalu firmy.
* **Nazwy pewnej liczby zasad usługi Intune zostały zmienione** , aby zwiększyć ich spójność w ramach produktu i ułatwić wyszukiwanie. Listę wszystkich dostępnych zasad usługi Intune zawiera temat [Używanie zasad do zarządzania komputerami i urządzeniami przenośnymi w usłudze Microsoft Intune](https://technet.microsoft.com/library/dn743712.aspx).
* **Profile certyfikatu PKCS #12 (PFX)** są dostępne dla systemu Android 4.0 lub nowszych oraz systemu Windows 10 (Desktop i Mobile) lub nowszych. Użycie pliku .PFX nie wymaga serwera NDES. Informacje na temat sposobów użycia profilów certyfikatu PFX zawiera temat [Zapewnianie dostępu do zasobów firmy przy użyciu profilów certyfikatów w usłudze Microsoft Intune](http://technet.microsoft.com/library/dn818904.aspx)
* **Ustawienia granic firmowych w systemie Windows 10 Desktop i Mobile** umożliwia szczegółowe konfigurowanie ustawień VPN, zgodnie z opisem w temacie [Pomaganie użytkownikom w nawiązywaniu połączenia z siecią firmową za pomocą profilów sieci VPN](https://technet.microsoft.com/library/dn818905.aspx).
* **Aplikacja usługi OneDrive dla systemu Android teraz obsługuje wiele tożsamości**. Ta i inne aktualizacje zasad zarządzania aplikacjami mobilnymi są opisane na [liście zarządzalnych aplikacji firmy Microsoft](https://technet.microsoft.com/library/dn708489.aspx).
* **Obejście funkcji blokady aktywacji w systemie iOS**. Jeśli urządzenia z systemem iOS należące do firmy są chronione przy użyciu funkcji blokady aktywacji, to przed wymazaniem lub ponownym uaktywnieniem urządzenia będzie konieczne podanie identyfikatora Apple ID i hasła. Może to stanowić problem, gdy użytkownicy odchodzą z firmy i zwracają urządzenia należące do firmy bez wyłączania blokady aktywacji. Aby rozwiązać ten problem, można użyć [obejścia blokady aktywacji w usłudze Intune](https://technet.microsoft.com/library/mt414176.aspx).

### Dostęp warunkowy dla komputerów
Teraz możesz skonfigurować zasady dostępu warunkowego dla komputerów. Umożliwia to aplikacjom komputerowym pakietu Office dostęp do usług Exchange Online i SharePoint Online.
Aby włączyć zasady dostępu warunkowego dla komputerów, komputer musi być przyłączony do domeny lub zgodny.
* Aby uzyskać pełną listę wymagań dotyczących włączania dostępu warunkowego dla komputerów, zobacz sekcję **Wprowadzenie** w temacie [Zarządzanie dostępem do poczty e-mail i programu SharePoint w usłudze Microsoft Intune](http://technet.microsoft.com/library/dn818907).aspx).
* Artykuł [Zarządzanie dostępem do poczty e-mail za pomocą usługi Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx) zawiera opcje, które można skonfigurować, aby włączyć dostęp warunkowy do poczty e-mail.
* Artykuł [Zarządzanie dostępem do usługi SharePoint Online za pomocą usługi Microsoft Intune](https://technet.microsoft.com/library/dn705844.aspx) zawiera opcje, które można skonfigurować, aby włączyć dostęp warunkowy do poczty e-mail.

### Zmiany i aktualizacje aplikacji Portalu firmy oferowanych przez firmę Microsoft
W aplikacjach Portalu firmy w tej wersji wprowadzono następujące zmiany:

**Android**

Użytkownicy teraz będą widzieć instrukcje dotyczące rejestracji po zalogowaniu, jeśli jeszcze nie zarejestrowali swoich urządzeń w funkcji zarządzania.

### Co nowego w dokumentacji usługi Intune — sierpień 2015
**Nowe tematy**

|Tytuł|Szczegóły|
|-----|-------|
|[Ochrona urządzeń z systemem iOS przez obejście blokady aktywacji w usłudze Microsoft Intune](https://technet.microsoft.com/library/mt414176.aspx)|Informacje o sposobie korzystania z usługi Intune do obejścia blokady aktywacji systemu iOS, gdy użytkownik opuści firmę i zwróci zablokowane urządzenie.|

**Zaktualizowane tematy**

|Tytuł|Szczegóły|
|-----|-------|
|[Aplikacje firmy Microsoft, których można używać z zasadami zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune](https://technet.microsoft.com/library/dn708489.aspx)|Zaktualizowano o najnowsze informacje o aplikacjach, które mogą być zarządzane za pomocą zasad zarządzania aplikacjami mobilnymi.
|[Używanie zasad do zarządzania komputerami i urządzeniami przenośnymi w usłudze Microsoft Intune](http://technet.microsoft.com/library/dn743712.aspx)|Zaktualizowano o najnowsze zasady dodane do usługi Intune.|
<!---
## July 2015
July updates for Intune are limited to behind-the-scenes enhancements that allow us to continue providing you with a high-quality service experience. New features are not included in this service update.

### Intune Onboarding benefit
Microsoft offers the Intune Onboarding benefit for eligible plans. The Onboarding benefit lets you work remotely with Microsoft specialists to get your Intune environment ready for use. For more information, see [Microsoft Intune Onboarding benefit description](https://technet.microsoft.com/library/mt228266.aspx)
### Changes and updates to Microsoft Company Portal apps
The following changes have been made to the company portal apps in this release.

**Android**

Microsoft automatically collects anonymous data about the performance and use of the company portal to improve Microsoft products and services. End users can turn off data collection by using the Usage Data setting on their device, but administrators have no control over the data collection and cannot change the end user’s selection for this setting.--->


<!--HONumber=May16_HO1-->


