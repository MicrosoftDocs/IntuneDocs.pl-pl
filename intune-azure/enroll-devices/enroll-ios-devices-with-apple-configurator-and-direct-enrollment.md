---
title: "Rejestracja urządzeń z systemem iOS przy użyciu programu Apple Configurator i rejestracji bezpośredniej"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: informacje dotyczące rejestrowania firmowych urządzeń z systemem iOS przy użyciu programu Apple Configurator i rejestracji bezpośredniej."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6c0a430-1851-4108-812a-87e0fc2623b5
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 3758df744311392528be01c826527c2a9d879975
ms.openlocfilehash: 02675b6fe9872cb634d0515172f696cedc7e6463
ms.contentlocale: pl-pl
ms.lasthandoff: 05/10/2017


---

# <a name="enroll-ios-devices-with-apple-configurator-and-direct-enrollment"></a>Rejestracja urządzeń z systemem iOS przy użyciu programu Apple Configurator i rejestracji bezpośredniej 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Usługa Intune obsługuje rejestrowanie firmowych urządzeń z systemem iOS przy użyciu narzędzia [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) działającego na komputerze Mac. Ten proces nie powoduje przywrócenia ustawień fabrycznych urządzenia i powoduje zarejestrowanie urządzenia przy użyciu wstępnie zdefiniowanych zasad. Ta metoda jest przeznaczona dla urządzeń, których przynależność do użytkowników została ustawiona na wartość **brak koligacji użytkownika**, i wymaga podłączenia urządzenia z systemem iOS do komputera Mac przy użyciu połączenia USB w celu skonfigurowania rejestracji firmowej.

>[!NOTE]
>Tej metody rejestracji nie można używać z metodą korzystającą z [menedżera rejestracji urządzeń](enroll-devices-using-device-enrollment-manager.md).

W przypadku bezpośredniego rejestrowania urządzeń z systemem iOS możesz zarejestrować urządzenie bez uzyskiwania jego numeru seryjnego. Możesz też nazwać urządzenie w celach identyfikacyjnych, zanim usługa Intune przechwyci nazwę urządzenia podczas rejestracji. Aplikacja Portal firmy nie jest obsługiwana w przypadku urządzeń, które zostały zarejestrowane bezpośrednio. W tych wskazówkach przyjęto założenie, że używany jest program Apple Configurator 2.0 na komputerze Mac.

Inne metody rejestracji urządzeń z systemem iOS zostały opisane w temacie [Choose how to enroll iOS devices in Intune](choose-ios-enrollment-method.md) (Wybieranie sposobu rejestrowania urządzeń z systemem iOS w usłudze Intune).


## <a name="prerequisites"></a>Wymagania wstępne

Przed rozpoczęciem konfigurowania rejestracji urządzeń z systemem iOS należy spełnić następujące wymagania wstępne:

- [Skonfigurowanie domen](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [Ustawienie urzędu zarządzania urządzeniami przenośnymi](set-mdm-authority.md)
- [Tworzenie grup](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [Skonfigurowanie aplikacji Portal firmy](../manage-apps/company-portal-app.md)
- Przypisanie licencji użytkowników w [portalu usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Uzyskiwanie certyfikatu wypychania MDM firmy Apple](get-an-apple-mdm-push-certificate.md)
- Potwierdzenie fizycznego dostępu do urządzeń z systemem iOS
- Przygotowanie numerów seryjnych urządzeń — zobacz artykuł [How to get an iOS serial number](https://support.apple.com//HT204308) (Jak uzyskać numer seryjny urządzenia z systemem iOS)
- Kable połączenia USB
- Upewnienie się, że na komputerze Mac jest zainstalowany program [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)

## <a name="create-an-apple-configurator-profile-for-devices"></a>Tworzenie profilu programu Apple Configurator dla urządzeń

Profil rejestracji urządzeń określa ustawienia stosowane do grupy urządzeń. Poniższe kroki pokazują, jak utworzyć profil rejestracji dla urządzeń z systemem iOS rejestrowanych przy użyciu programu Apple Configurator.

1. W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.

2. W bloku Intune wybierz pozycję **Zarejestruj urządzenia**, a następnie pozycję **Rejestracja Apple**.

3. W obszarze **Zarządzaj ustawieniami rejestracji programu Apple Configurator** wybierz pozycję **Profile programu AC**.

4. W bloku **Profile rejestracji programu Apple Configurator** wybierz pozycję **Utwórz**.

5. W bloku **Utwórz profil rejestracji** wprowadź nazwę i opis profilu.

6. Dla pozycji **Koligacja użytkownika** wybierz opcję **Zarejestruj bez koligacji użytkownika**, aby mieć pewność, że urządzenie nie jest powiązane z użytkownikiem. Tego typu przynależności należy użyć w przypadku urządzeń wykonujących zadania bez uzyskiwania dostępu do danych użytkowników lokalnych. Aplikacje wymagające koligacji użytkownika (w tym aplikacja Portal firmy używana do instalowania aplikacji biznesowych) nie będą działać.

7. Wybierz pozycję **Utwórz**, aby zapisać profil.

## <a name="export-the-profile-as-mobileconfig-to-ios-devices"></a>Eksportowanie profilu jako pliku .mobileconfig do urządzeń z systemem iOS

1. W bloku **Eksportuj profil** pobierz profil rejestracji do programu [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) w celu bezpośredniego wypchnięcia go jako profilu zarządzania do połączonego urządzenia z systemem iOS. Użycie tej metody nie powoduje zresetowania urządzenia do ustawień fabrycznych.

2. Przygotuj urządzenie z zainstalowanym programem Apple Configurator, wykonując kroki opisane poniżej.

   a. Na komputerze Mac otwórz program Apple Configurator 2.0.

   b. Podłącz urządzenia z systemem iOS do komputera Mac przy użyciu kabla USB. Zamknij aplikacje Photos (Zdjęcia), iTunes i inne aplikacje otwarte na urządzeniu po jego wykryciu.

   c. W programie Apple Configurator wybierz podłączone urządzenie z systemem iOS, a następnie wybierz przycisk **Add** (Dodaj). Opcje, które można dodać do urządzenia, są wyświetlane na liście rozwijanej. Wybierz pozycję **Profiles** (Profile).

   d. Użyj selektora plików w celu wybrania pliku mobileconfig wyeksportowanego za pomocą usługi Intune, a następnie wybierz pozycję **Add** (Dodaj). Profil zostanie dodany do urządzenia. Jeśli urządzenie jest nienadzorowane, instalacja będzie wymagać akceptacji na urządzeniu.

3. Wykonaj poniższe kroki w celu zainstalowania profilu na urządzeniu z systemem iOS. Na urządzeniu musi zostać zakończona praca Asystenta ustawień i musi być one gotowe do użycia. Jeśli rejestracja wiąże się z wdrożeniami aplikacji, urządzenie powinno mieć ustawiony identyfikator firmy Apple, ponieważ wdrożenia aplikacji będą wymagać posiadania identyfikatora Apple ID powiązanego ze sklepem App Store.

   a. Odblokuj urządzenie z systemem iOS.

   b. W oknie dialogowym **Zainstaluj profil** wybierz dla pozycji **Profil zarządzania** opcję **Zainstaluj**.

   c. W razie potrzeby podaj kod dostępu urządzenia lub identyfikator Apple ID.

   d. Zaakceptuj **ostrzeżenie** i wybierz pozycję **Zainstaluj**.

   e. Zaakceptuj **ostrzeżenie zdalne** i wybierz pozycję **Ufaj**.

   f. Wyświetlenie okna dialogowego **Profil został zainstalowany** oznacza, że profil został zainstalowany. Wybierz pozycję **Gotowe**.

4. Na urządzeniu z systemem iOS otwórz pozycję **Ustawienia** i przejdź do pozycji **Ogólne** > **Zarządzanie urządzeniem** > **Profil zarządzania**. Upewnij się, że instalacja profilu jest wymieniona na liście, a następnie sprawdź ograniczenia zasad systemu iOS i zainstalowane aplikacje. Wyświetlenie ograniczeń zasad i aplikacji na urządzeniu może potrwać do 10 minut.

5. Rozdystrybuuj urządzenia. Urządzenie z systemem iOS jest teraz zarejestrowane w usłudze Intune i zarządzane przez tę usługę.

