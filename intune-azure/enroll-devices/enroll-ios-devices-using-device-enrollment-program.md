---
title: "Rejestrowanie urządzeń z systemem iOS — Device Enrollment Program | Wersja zapoznawcza usługi Intune Azure | Dokumentacja firmy Microsoft"
description: "Wersja zapoznawcza usługi Intune Azure: informacje na temat rejestrowania firmowych urządzeń z systemem iOS przy użyciu programu Device Enrollment Program."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: adb2fd27d7f2b3f0ef4dce6b26fcb20d74b69a00
ms.openlocfilehash: 2986e659d384eaa67b64af1ce3ae48a1ac81a600


---

# <a name="enroll-ios-devices-using-device-enrollment-program"></a>Rejestrowanie urządzeń z systemem iOS przy użyciu programu Device Enrollment Program

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Usługa Microsoft Intune może wdrożyć profil rejestracji, który będzie bezprzewodowo rejestrować urządzenia z systemem iOS zakupione w ramach programu Device Enrollment Program (DEP). Profil zawiera ustawienia zarządzania, które mają być zastosowane do urządzeń. Pakiet rejestracyjny może obejmować opcje Asystenta ustawień dla urządzenia. Użytkownicy nie mogą wyrejestrowywać urządzeń zarejestrowanych w programie DEP.

>[!NOTE]
>Tej metody rejestracji nie można używać z metodą korzystającą z [menedżera rejestracji urządzeń](enroll-devices-using-device-enrollment-manager.md).

W celu zarządzania firmowymi urządzeniami z systemem iOS przy użyciu programu Device Enrollment Program (DEP) firmy Apple organizacja musi dołączyć do programu DEP firmy Apple i zakupić urządzenia w ramach tego programu. Szczegóły tego procesu są dostępne pod adresem: [https://deploy.apple.com](https://deploy.apple.com). Zalety programu obejmują funkcje bezobsługowego konfigurowania urządzeń bez konieczności podłączania poszczególnych urządzeń do komputera przy użyciu kabla USB.

Aby zarejestrować firmowe urządzenia z systemem iOS w programie DEP, należy [uzyskać token programu DEP](get-apple-dep-token.md) od firmy Apple. Token umożliwia usłudze Intune synchronizację informacji dotyczących urządzeń uczestniczących w programie DEP należących do firmy. Umożliwia on również usłudze Intune przekazywanie profilów rejestracji do firmy Apple i przypisywanie urządzeń do tych profilów.

Inne metody rejestracji urządzeń z systemem iOS zostały opisane w temacie [Choose how to enroll iOS devices in Intune](choose-ios-enrollment-method.md) (Wybieranie sposobu rejestrowania urządzeń z systemem iOS w usłudze Intune).

## <a name="prerequisites"></a>Wymagania wstępne

Przed rozpoczęciem konfigurowania rejestracji urządzeń z systemem iOS należy spełnić następujące wymagania wstępne:

- [Skonfigurowanie domen](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [Ustawienie urzędu zarządzania urządzeniami przenośnymi](set-mdm-authority.md)
- [Tworzenie grup](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- Przypisanie licencji użytkowników w [portalu usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Uzyskiwanie certyfikatu wypychania MDM firmy Apple](get-an-apple-mdm-push-certificate.md)
- [Pobieranie tokenu DEP firmy Apple](get-apple-dep-token.md)

## <a name="create-an-apple-dep-profile-for-devices"></a>Utworzenie profilu programu Apple DEP dla urządzeń

Profil rejestracji urządzeń określa ustawienia stosowane do grupy urządzeń. Poniższe kroki pokazują, jak utworzyć profil rejestracji dla urządzeń z systemem iOS rejestrowanych przy użyciu programu DEP.

1. W witrynie Azure Portal wybierz pozycję **Więcej usług**, w polu tekstowym wprowadź nazwę **Intune**, a następnie wybierz kolejno pozycje **Inne** > **Intune**.

2. W bloku Intune wybierz pozycję **Zarejestruj urządzenia**, a następnie pozycję **Rejestracja Apple**.

3. W obszarze **Zarządzaj ustawieniami rejestracji programu DEP (Device Enrollment Program) firmy Apple** wybierz pozycję **Profile usługi DEP**.

4. W bloku **Profile usługi DEP firmy Apple** wybierz pozycję **Utwórz**.

5. W bloku **Utwórz profil rejestracji** wprowadź nazwę i opis profilu.

6. Dla pozycji **Koligacja użytkownika** wskaż, czy urządzenia z tym profilem będą rejestrowane z koligacją użytkownika, czy bez niej.

 - **Zarejestruj z koligacją użytkownika** — podczas początkowej konfiguracji należy określić przynależność urządzenia do użytkownika, a następnie zezwolić na dostęp tego urządzenia do firmowych danych i poczty e-mail. Określ koligację użytkownika dla urządzeń zarządzanych w programie DEP, które należą do użytkowników i muszą korzystać z portalu firmy na potrzeby usług takich jak instalowanie aplikacji. Uwaga: uwierzytelnianie wieloskładnikowe (MFA) nie działa podczas rejestracji urządzeń za pomocą programu DEP, gdy jest używana koligacja użytkownika. Po zarejestrowaniu tych urządzeń uwierzytelnianie wieloskładnikowe działa zgodnie z oczekiwaniami.

    >[!NOTE]
    >Program DEP z koligacją użytkownika wymaga nazwy użytkownika protokołu WS-Trust 1.3/mieszanego punktu końcowego, aby móc żądać tokenu użytkownika.

 - **Zarejestruj bez koligacji użytkownika** — przynależność urządzenia do użytkownika nie jest określana. Tego typu przynależności należy użyć w przypadku urządzeń wykonujących zadania bez uzyskiwania dostępu do danych użytkowników lokalnych. Aplikacje wymagające koligacji użytkownika (w tym aplikacja Portal firmy używana do instalowania aplikacji biznesowych) nie będą działać.

7. Wybierz pozycję **Ustawienia zarządzania urządzeniami**, skonfiguruj następujące ustawienia profilu, a następnie wybierz pozycję **Zapisz**:

    - **Nadzorowane** — tryb zarządzania, w ramach którego następuje włączenie większej liczby opcji zarządzania i domyślne wyłączenie blokady aktywacji. Jeśli pole pozostanie puste, użytkownik będzie mieć ograniczone możliwości w zakresie zarządzania.

    - **Rejestracja zablokowana** — (wymaga zastosowania ustawienia Tryb zarządzania = Nadzorowane) wyłącza ustawienia systemu iOS, które umożliwiają usunięcie profilu zarządzania. W przypadku pozostawienia tego pola pustego istnieje możliwość usunięcia profilu zarządzania z poziomu menu Ustawienia. To ustawienie zostaje skonfigurowane podczas aktywacji i nie ma możliwości jego zmiany bez zresetowania urządzenia do ustawień fabrycznych.

    - **Zezwalaj na parowanie** — określa, czy urządzenia z systemem iOS można synchronizować z komputerami. W przypadku wybrania pozycji **Zezwalaj programowi Apple Configurator według certyfikatów** należy wybrać certyfikat w obszarze **Certyfikaty programu Apple Configurator**.

    - **Certyfikaty programu Apple Configurator** — w przypadku wyboru pozycji **Zezwalaj programowi Apple Configurator według certyfikatów** w obszarze **Zezwalaj na parowanie** należy wybrać certyfikat programu Apple Configurator do zaimportowania.

8. Wybierz pozycję **Ustawienia Asystenta ustawień**, skonfiguruj następujące ustawienia profilu, a następnie wybierz pozycję **Zapisz**:

    - **Nazwa działu** — jest wyświetlana, gdy użytkownik dotknie pozycji **Informacje o konfiguracji** podczas aktywacji.

    - **Telefon działu** — jest wyświetlany, gdy użytkownik kliknie podczas aktywacji przycisk Potrzebna pomoc.
    - **Opcje Asystenta ustawień** — te opcjonalne ustawienia mogą być później konfigurowane z poziomu menu **Ustawienia** systemu iOS.
        - **Kod dostępu** — wyświetla monit o podanie kodu dostępu podczas aktywacji. Zawsze należy wymagać kodu dostępu, chyba że urządzenie zostanie zabezpieczone lub dostęp do niego będzie kontrolowany w inny sposób (tj. tryb kiosku, który ogranicza możliwość użycia urządzenia do jednej aplikacji).
        - **Usługi lokalizacji** — jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący usługi podczas aktywacji
        - **Przywracanie** — jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit o kopię zapasową w programie iCloud podczas aktywacji
        - **Apple ID** — jeśli to ustawienie zostało włączone, system iOS wyświetla monit o podanie identyfikatora Apple ID, gdy usługa Intune będzie podejmowała próbę zainstalowania aplikacji bez tego identyfikatora. Identyfikator Apple ID jest wymagany do pobierania aplikacji ze sklepu iOS App Store, w tym aplikacji zainstalowanych przez usługę Intune.
        - **Warunki i postanowienia** — jeśli to ustawienie zostało włączone, Asystent ustawień monituje użytkowników o zaakceptowanie warunków i postanowień firmy Apple podczas aktywacji
        - **Touch ID** — jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący tej usługi podczas aktywacji
        - **Apple Pay** — jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący tej usługi podczas aktywacji
        - **Zoom** — jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący tej usługi podczas aktywacji
        - **Siri** — jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący tej usługi podczas aktywacji
        - **Dane diagnostyczne** — jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący tej usługi podczas aktywacji

9. Aby zapisać ustawienia profilu, wybierz pozycję **Utwórz** w bloku **Utwórz profil rejestracji**.

## <a name="assign-apple-dep-serial-numbers-to-your-mdm-server"></a>Przypisywanie numerów seryjnych programu DEP firmy Apple do serwera MDM

1. Przejdź do [portalu Device Enrollment Program](https://deploy.apple.com) (https://deploy.apple.com) i zaloguj się przy użyciu identyfikatora Apple ID swojej firmy. 

2. Wybierz kolejno pozycje **Deployment Program** (Program wdrażania) &gt; **Device Enrollment Program** (Program rejestracji urządzeń) &gt; **Manage Devices** (Zarządzanie urządzeniami). 

3. Określ sposób **wybierania urządzeń**, a następnie podaj informacje o urządzeniach i określ szczegóły według numeru seryjnego (**Serial Number**) urządzenia, numeru zamówienia (**Order Number**) lub przekaż plik CSV (**Upload CSV File**). 

4. Wybierz pozycję **Assign to Server** (Przypisz do serwera), wybierz nazwę serwera &lt;nazwa_serwera&gt; określoną dla usługi Microsoft Intune, a następnie kliknij przycisk **OK**.

## <a name="synchronize-dep-managed-devices"></a>Synchronizowanie urządzeń zarządzanych w programie DEP

1. W bloku Intune portalu Azure Portal wybierz pozycję **Zarejestruj urządzenia**, a następnie wybierz pozycję **Rejestracja Apple**.

2. W obszarze **Zarządzaj ustawieniami rejestracji programu DEP (Device Enrollment Program) firmy Apple** wybierz pozycję **Numery seryjne DEP**.

4. W bloku **Numery seryjne Apple DEP** wybierz przycisk **Synchronizuj**.

5. W bloku **Synchronizuj** wybierz pozycję **Żądaj synchronizacji**. Pasek postępu pokazuje, ile czasu minie przed ponownym przesłaniem żądania synchronizacji.

    Aby spełnić warunki ruchu programu DEP firmy Apple, usługa Intune nakłada następujące ograniczenia:
     -  Pełną synchronizację programu DEP można uruchamiać nie częściej niż co siedem dni. Podczas pełnej synchronizacji usługa Intune odświeża każdy numer seryjny Apple przypisany do usługi Intune, niezależnie od tego, czy numer seryjny był już wcześniej synchronizowany. W przypadku próby przeprowadzenia pełnej synchronizacji przed upływem siedmiu dni od poprzedniej pełnej synchronizacji usługa Intune odświeża tylko numery seryjne, które jeszcze nie zostały przypisane do usługi Intune.
     -  Każde żądanie synchronizacji ma przydzielone 10 minut na zakończenie. W tym czasie lub do momentu zakończenia żądania powodzeniem przycisk **synchronizacji** jest wyłączony.

>[!NOTE]
>Możesz także przypisać numery seryjne DEP do profilów z bloku **Numery seryjne Apple DEP**.

## <a name="distribute-devices-to-users"></a>Przekazywanie urządzeń użytkownikom

Urządzenia firmowe mogą zostać teraz przekazane użytkownikom. Po włączeniu urządzenia z systemem iOS zostanie ono zarejestrowane na potrzeby zarządzania przez usługę Intune.


## <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Jak użytkownicy instalują aplikację Portal firmy i używają jej na urządzeniach

Na urządzeniach skonfigurowanych z koligacją użytkownika można zainstalować aplikację Portal firmy i używać jej do pobierania aplikacji i zarządzania urządzeniami. Po otrzymaniu urządzeń użytkownicy muszą wykonać dodatkowe czynności, które zostały opisane poniżej, w celu ukończenia działania Asystenta ustawień i zainstalowania aplikacji Portal firmy.

### <a name="how-users-enroll-corporate-owned-ios-devices-with-user-affinity"></a>Jak użytkownicy rejestrują urządzenia firmowe z systemem iOS z koligacją użytkownika 

1. Po włączeniu urządzenia użytkownicy są monitowani o ukończenie działania Asystenta ustawień. Podczas instalacji użytkownicy są monitowani o podanie swoich poświadczeń. Muszą oni korzystać z poświadczeń (tj. unikatowej kombinacji imienia i nazwiska lub nazwy UPN) skojarzonych z ich subskrypcją w usłudze Intune.

2. Podczas instalacji użytkownicy są monitowani o podanie identyfikatora Apple ID. Muszą podać identyfikator Apple ID, aby umożliwić zainstalowanie aplikacji Portal firmy na urządzeniu. Mogą także podać identyfikator z menu ustawień systemu iOS po zakończeniu konfiguracji.

3. Po ukończeniu konfiguracji użytkownicy muszą zainstalować aplikację Portal firmy ze sklepu App Store.

4. Użytkownicy mogą się teraz zalogować do Portalu firmy przy użyciu nazwy UPN użytej podczas konfigurowania urządzenia.

5. Po zalogowaniu użytkownicy otrzymują monit o zarejestrowanie urządzenia. Pierwszym krokiem jest zidentyfikowanie urządzenia. Aplikacja wyświetla listę urządzeń z systemem iOS, które zostały już zarejestrowane przez firmę i przypisane do konta użytkownika w usłudze Intune. Użytkownicy powinni wybrać odpowiednie urządzenie. Jeśli to urządzenie nie zostało jeszcze zarejestrowane przez firmę, użytkownicy powinni wybrać pozycję „Nowe urządzenie”, aby kontynuować standardową procedurę rejestracji.

6. Na następnym ekranie użytkownicy potwierdzają numer seryjny nowego urządzenia. W tym celu użytkownicy wybierają wyświetlone łącze. Kliknięcie łącza uruchamia aplikację Ustawienia, która z kolei pozwala użytkownikom zweryfikować ich numer seryjny. Użytkownik musi następnie wprowadzić cztery ostatnie znaki numeru seryjnego do aplikacji Portal firmy.

   Ten krok umożliwia zweryfikowanie, że urządzenie zostało zarejestrowane przez firmę w usłudze Intune. Jeśli numer seryjny urządzenia nie jest zgodny, oznacza to, że użytkownik wybrał niewłaściwe urządzenie. Użytkownik musi powrócić do poprzedniego ekranu i wybrać inne urządzenie.

7. Po zweryfikowaniu numeru seryjnego aplikacja Portal firmy wykonuje przekierowanie do witryny internetowej Portalu firmy w celu sfinalizowania rejestracji. Następnie w witrynie pojawia się monit o powrót użytkownika do aplikacji.

Stanowi to zakończenie procesu rejestracji. Użytkownicy mogą od tego momentu używać tego urządzenia z pełnym zestawem funkcji.



<!--HONumber=Feb17_HO1-->


