---
title: Znane problemy w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Informacje o znanych problemach w usłudze Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 04/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 388c9f69b6cbee1353b0e21121a47576b58b3ba6
ms.sourcegitcommit: 407191a92ef356a3d196b6f9959b9b033190ca2c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2018
---
# <a name="known-issues-in-microsoft-intune"></a>Znane problemy w usłudze Microsoft Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Zapoznaj się z tym artykułem, aby dowiedzieć się więcej o wszelkich znanych problemach w usłudze Intune.

Aby zgłosić błąd, którego nie ma na tej liście, [otwórz żądanie pomocy technicznej](get-support.md).

Możesz poprosić o dodanie nowej funkcji do usługi Intune, wysyłając raport z witryny [UserVoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console).

## <a name="migration"></a>Migracja

### <a name="intune-legacy-pc-client-features-are-only-available-in-the-silverlight-console"></a>Funkcje starszej wersji klienta usługi Intune są dostępne tylko w konsoli programu Silverlight

Możliwość zarządzania systemem Windows 10 w usłudze Intune w witrynie Azure Portal jest dostępna za pośrednictwem funkcji zarządzania urządzeniami mobilnymi systemu Windows. Aby uzyskać więcej informacji, zobacz [Usługa Intune w konsoli platformy Azure i starszej wersji klienta usługi Intune](https://docs.microsoft.com/intune-classic/deploy-use/intune-on-azure).

### <a name="groups-created-by-intune-during-migration-might-affect-functionality-of-other-microsoft-products"></a>Grupy utworzone przez usługę Intune podczas migracji mogą mieć wpływ na funkcjonalność innych produktów firmy Microsoft

W przypadku migracji z usługi Intune do witryny Azure Portal może zostać wyświetlona nowa grupa o nazwie **Wszyscy użytkownicy — b0b08746-4dbe-4a37-9adf-9e7652c0b421**. Ta grupa zawiera wszystkich użytkowników usługi Azure Active Directory, nie tylko licencjonowanych użytkowników usługi Intune. Jeśli planujesz, że niektórzy bieżący lub nowi użytkownicy nie będą członkami żadnych grup, może to spowodować problemy z pozostałymi produktami firmy Microsoft.

### <a name="status-blades-for-migrated-policies-do-not-work"></a>Bloki stanu zmigrowanych zasad nie działają

Nie można wyświetlić informacji o stanie zasad, które zostały zmigrowane z klasycznej witryny Azure Portal do witryny Azure Portal. Można jednak nadal wyświetlać raporty dla tych zasad w portalu klasycznym. Aby wyświetlić informacje o stanie zmigrowanych zasad konfiguracji, utwórz je ponownie w witrynie Azure Portal.

## <a name="apps"></a>Aplikacje

### <a name="ios-volume-purchased-apps-only-available-in-default-intune-tenant-language"></a>Aplikacje dla systemu iOS nabyte w ramach zakupów zbiorczych dostępne tylko w domyślnym języku dzierżawy usługi Intune
Aplikacje dla systemu iOS nabyte w ramach zakupów zbiorczych są wyświetlane i mogą zostać przypisane tylko w przypadku kodu kraju określonego dla konta usługi Intune. Usługa Intune synchronizuje tylko aplikacje z ustawieniami regionalnymi usługi iTunes zgodnymi z kodem kraju konta dzierżawy usługi Intune. Jeśli na przykład zakupisz aplikację dostępną tylko w sklepie dla Stanów Zjednoczonych, a Twoje konto usługi Intune ma niemieckie ustawienia regionalne, usługa Intune nie wyświetli tej aplikacji.

### <a name="multiple-copies-of-the-same-ios-volume-purchase-program-are-uploaded"></a>Przekazywanych jest wiele kopii tego samego programu dla systemu iOS nabytego w ramach zakupów zbiorczych
Nie klikaj wielokrotnie przycisku **Przekaż** dla tego samego tokenu VPP. Spowoduje to, że przekazywane będą zduplikowane tokeny VPP, a aplikacje będą synchronizowane wiele razy dla tego samego tokenu VPP.


<!-- ## Groups -->

## <a name="device-configuration"></a>Konfiguracja urządzenia

### <a name="you-cannot-save-a-windows-information-protection-policy-for-some-devices"></a>W przypadku niektórych urządzeń nie można zapisać zasad funkcji Windows Information Protection

W przypadku urządzeń, które nie zostały zarejestrowane w usłudze Intune, można określić tylko domenę główną w polu **Identyfikacja firmowa** w ustawieniach zasad funkcji Windows Information Protection.
Jeśli dodasz dodatkowe domeny (przy użyciu opcji **Zaawansowane ustawienia** > **Sieć obwodowa** > **Dodaj domenę chronioną**), nie można będzie zapisać zasad. Komunikat o błędzie, który zostanie wyświetlony w tej sytuacji, zostanie wkrótce zmieniony na bardziej precyzyjny.

### <a name="cisco-anyconnect-and-cisco-legacy-anyconnect-vpn-client-support---ios"></a>Obsługa klientów sieci VPN Cisco AnyConnect i Cisco Legacy AnyConnect — iOS

Na urządzeniach z systemem iOS integracja kontroli dostępu do sieci (NAC, Network Access Control) nie współpracuje z nowym klientem Cisco AnyConnect. Wraz z firmą Cisco pracujemy nad umożliwieniem integracji NAC.

Temat [Tworzenie profilów sieci VPN w usłudze Intune](vpn-settings-ios.md) zawiera więcej szczegółowych informacji dotyczących klientów Cisco AnyConnect i Cisco Legacy AnyConnect.

### <a name="using-the-numeric-password-type-with-macos-sierra-devices"></a>Użycie hasła liczbowego na urządzeniach z systemem macOS Sierra

Obecnie w przypadku wybrania pozycji **Liczbowy** w opcji **Wymagany typ hasła** w profilu ograniczeń urządzenia dla urządzeń z systemem macOS Sierra zostanie on wymuszony jako **Alfanumeryczny**. Jeśli chcesz używać hasła liczbowego na tych urządzeniach, nie konfiguruj tego ustawienia.
Ten problem może zostać poprawiony w przyszłej wersji systemu macOS.

Aby uzyskać więcej informacji o tych ustawieniach, zobacz temat [Ustawienia ograniczeń urządzenia z systemem macOS w usłudze Microsoft Intune](device-restrictions-macos.md).

## <a name="compliance"></a>Zgodność

### <a name="compliance-policies-from-intune-do-not-show-up-in-new-console"></a>Zasady zgodności pochodzące z usługi Intune nie będą wyświetlane w nowej konsoli

Zasady zgodności utworzone w klasycznym portalu zostaną objęte migracją, ale nie będą wyświetlane w witrynie Azure Portal z powodu zmian projektowych w tej witrynie. Zasady zgodności utworzone w klasycznym portalu usługi Intune są mimo to wymuszane, ale trzeba je wyświetlać i edytować w portalu klasycznym.

Ponadto nowe zasady zgodności tworzone w witrynie Azure Portal nie są widoczne w portalu klasycznym.

Więcej informacji znajduje się w artykule [Co to jest zgodność urządzeń](device-compliance.md).

<!-- ## Enrollment -->


## <a name="data-protection"></a>Ochrona danych

### <a name="ios-app-protection-policies"></a>Zasady ochrony aplikacji systemu iOS

Możesz zdefiniować [zasady ochrony aplikacji systemu iOS](app-protection-policy-settings-ios.md) dostępne dla użytkowników na urządzeniach zarządzanych za pomocą funkcji zarządzania aplikacjami mobilnymi bez rejestracji. Ze względu na tymczasowy błąd można te zasady definiować dla wersji systemu iOS z jednym miejscem dziesiętnym, a nie wieloma miejscami dziesiętnymi. Zamiast ustawiać minimalną wersję systemu iOS na 10.3.1, ustaw ją na system iOS 10.3. Ten problem zostanie rozwiązany w przyszłej aktualizacji zestawu iOS SDK.


## <a name="administration-and-accounts"></a>Administracja i konta

Administratorzy globalni (określani także jako administratorzy dzierżawy) mogą w dalszym ciągu wykonywać codzienne zadania administracyjne, nie korzystając z oddzielnej licencji usługi Intune ani pakietu Enterprise Mobility Suite (EMS). Jednak do korzystania z tej usługi, na przykład w celu zarejestrowania swoich własnych urządzeń lub urządzeń firmowych albo korzystania z Portalu firmy w usłudze Intune, będą potrzebować licencji na usługę Intune lub pakiet EMS.

<!-- ## Additional items -->
