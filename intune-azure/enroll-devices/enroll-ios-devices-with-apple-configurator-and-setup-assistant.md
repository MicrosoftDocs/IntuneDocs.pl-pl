---
title: "Rejestracja urządzeń z systemem iOS przy użyciu programu Apple Configurator i Asystenta ustawień"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: informacje dotyczące korzystania z programu Apple Configurator w celu rejestrowania firmowych urządzeń z systemem iOS przy użyciu Asystenta ustawień."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d384cd0-b662-41e7-94f5-0c96790ab20a
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: b2d2e4e0210526ff70b86526bd0b2e17bab0286b
ms.lasthandoff: 02/18/2017


---

# <a name="enroll-ios-devices-with-apple-configurator-and-setup-assistant"></a>Rejestracja urządzeń z systemem iOS przy użyciu programu Apple Configurator i Asystenta ustawień 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Usługa Intune obsługuje rejestrowanie firmowych urządzeń z systemem iOS przy użyciu narzędzia [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) działającego na komputerze Mac. Ten proces przywraca ustawienia fabryczne urządzenia i przygotowuje je do uruchomienia Asystenta ustawień, a także instaluje zasady firmy dla nowego użytkownika urządzenia.

>[!NOTE]
>Tej metody rejestracji nie można używać z metodą korzystającą z [menedżera rejestracji urządzeń](enroll-devices-using-device-enrollment-manager.md).

Za pomocą narzędzia Apple Configurator można przywrócić ustawienia fabryczne na urządzeniu z systemem iOS i przygotować je do konfiguracji dla nowego użytkownika urządzenia. Ta metoda wymaga podłączenia urządzenia z systemem iOS do komputera Mac przy użyciu połączenia USB w celu skonfigurowania rejestracji firmowej. Przyjęto założenie, że używany jest program Apple Configurator 2.0. Większość scenariuszy wymaga, aby zasady zastosowane w urządzeniu z systemem iOS uwzględniały koligację użytkownika, co umożliwia korzystanie z aplikacji Portal firmy usługi Intune.

Inne metody rejestracji urządzeń z systemem iOS zostały opisane w temacie [Choose how to enroll iOS devices in Intune](choose-ios-enrollment-method.md) (Wybieranie sposobu rejestrowania urządzeń z systemem iOS w usłudze Intune).

## <a name="prerequisites"></a>Wymagania wstępne

Przed rozpoczęciem konfigurowania rejestracji urządzeń z systemem iOS należy spełnić następujące wymagania wstępne:

- [Skonfigurowanie domen](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [Ustawienie urzędu zarządzania urządzeniami przenośnymi](set-mdm-authority.md)
- [Tworzenie grup](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [Skonfigurowanie aplikacji Portal firmy](/intune-azure/manage-apps/company-portal-app.md)
- Przypisanie licencji użytkowników w [portalu usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Uzyskiwanie certyfikatu wypychania MDM firmy Apple](get-an-apple-mdm-push-certificate.md)
- Potwierdzenie fizycznego dostępu do urządzeń z systemem iOS
- Przygotowanie numerów seryjnych urządzeń — zobacz artykuł [How to get an iOS serial number](https://support.apple.com//HT204308) (Jak uzyskać numer seryjny urządzenia z systemem iOS)
- Kable połączenia USB
- Upewnienie się, że na komputerze Mac jest zainstalowany program [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)
- [Dodawanie numerów seryjnych programu Apple Configurator](add-apple-configurator-serial-numbers.md)


## <a name="create-an-apple-configurator-profile-for-devices"></a>Tworzenie profilu programu Apple Configurator dla urządzeń

Profil rejestracji urządzeń określa ustawienia stosowane do grupy urządzeń. Poniższe kroki pokazują, jak utworzyć profil rejestracji dla urządzeń z systemem iOS rejestrowanych przy użyciu programu Apple Configurator.

1. W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.

2. W bloku Intune wybierz pozycję **Zarejestruj urządzenia**, a następnie pozycję **Rejestracja Apple**.

3. W obszarze **Zarządzaj ustawieniami rejestracji programu Apple Configurator** wybierz pozycję **Profile programu AC**.

4. W bloku **Profile rejestracji programu Apple Configurator** wybierz pozycję **Utwórz**.

5. W bloku **Utwórz profil rejestracji** wprowadź nazwę i opis profilu.

6. Dla pozycji **Koligacja użytkownika** wskaż, czy urządzenia z tym profilem będą rejestrowane z koligacją użytkownika, czy bez niej.

   - **Zarejestruj z koligacją użytkownika** — podczas początkowej konfiguracji należy określić przynależność urządzenia do użytkownika, a następnie zezwolić na dostęp tego urządzenia do firmowych danych i poczty e-mail. Koligację użytkownika należy skonfigurować dla urządzeń zarządzanych w programie DEP, które należą do użytkowników i muszą korzystać z portalu firmy na potrzeby usług takich jak instalowania aplikacji.

   - **Zarejestruj bez koligacji użytkownika** — przynależność urządzenia do użytkownika nie jest określana. Tego typu przynależności należy użyć w przypadku urządzeń wykonujących zadania bez uzyskiwania dostępu do danych użytkowników lokalnych. Aplikacje wymagające koligacji użytkownika (w tym aplikacja Portal firmy używana do instalowania aplikacji biznesowych) nie będą działać.

7. Wybierz pozycję **Utwórz**, aby zapisać profil.

## <a name="assign-serial-numbers-to-an-apple-configurator-profile"></a>Przypisywanie numerów seryjnych do profilu programu Apple Configurator

Po utworzeniu profilów programu Apple Configurator możesz przypisać do nich numery seryjne urządzeń. Aby można było przypisać numery seryjne, należy najpierw dodać je do usługi Intune, wykonując czynności opisane w artykule [Add Apple Configurator serial numbers](add-apple-configurator-serial-numbers.md) (Dodawanie numerów seryjnych programu Apple Configurator).

### <a name="assign-serial-numbers-to-apple-configurator-profiles"></a>Przypisywanie numerów seryjnych do profilów programu Apple Configurator

1. W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.

2. W bloku **Profile rejestracji programu Apple Configurator** wybierz profil, do którego chcesz przypisać numery seryjne.

3. W bloku o nazwie profilu wybierz kolejno pozycje **Numery seryjne** > **Przypisz**.

4. Wybierz numery seryjne, które chcesz przypisać do tego profilu, a następnie kliknij przycisk **Przypisz**.

## <a name="export-the-profile-to-ios-devices"></a>Eksportowanie profilu do urządzeń z systemem iOS

Po utworzeniu profilu i przypisaniu numerów seryjnych należy wyeksportować profil z usługi Intune jako adres URL lub jako plik w formacie opisanym poniżej. Następnie należy zaimportować go ręcznie do programu Apple Configurator zainstalowanego na komputerze Mac; po wykonaniu tej czynności program Apple Configurator wdroży go na urządzeniach.

### <a name="export-a-profile-using-setup-assistant-enrollment"></a>Eksportowanie profilu przy użyciu rejestracji Asystenta ustawień

1. W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.

2. W bloku **Profile rejestracji programu Apple Configurator** wybierz profil przeznaczony do wyeksportowania.

3. W bloku odpowiedniego profilu zaznacz pozycję **Eksportuj profil**.

4. Skopiuj adres URL profilu do programu [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) po podłączeniu urządzenia z systemem iOS. Możesz przekazać go później przy użyciu narzędzia Apple Configurator, aby określić profil usługi Intune używany przez urządzenia z systemem iOS.

  Aby umożliwić obsługę programu Apple Configurator 2, należy edytować adres URL profilu 2.0. Aby to zrobić, zastąp poniższy kod:
    ```
    https://manage.microsoft.com/EnrollmentServer/Discovery.svc/iOS/ESProxy?id=
    ```
    tym kodem:

    ```
    https://appleconfigurator2.manage.microsoft.com/MDMServiceConfig?id=
    ```

   Możesz przekazać ten adres URL profilu do programu Apple DEP za pomocą narzędzia Apple Configurator, aby zdefiniować profil usługi Intune używany przez urządzenia z systemem iOS, używając poniższej procedury.

5. Przekaż ten adres URL profilu do programu Apple DEP za pomocą programu Apple Configurator, aby zdefiniować profil usługi Intune używany przez urządzenia z systemem iOS.


    1.  Na komputerze Mac otwórz narzędzie **Apple Configurator 2**. Na pasku menu wybierz pozycję **Apple Configurator 2**, a następnie wybierz pozycję **Preferences** (Preferencje).

         > [!WARNING]
         > Podczas procesu rejestracji urządzenia zostaną zresetowane do konfiguracji fabrycznych. Jako najlepsze rozwiązanie zalecane jest zresetowanie urządzenia i włączenie go. Zalecane jest również, aby podczas podłączania na urządzeniach był wyświetlany ekran **powitalny**.

    2. W okienku **preferencji** wybierz pozycję **Servers** (Serwery), a następnie wybierz symbol „+”, aby uruchomić kreatora serwera MDM. Wybierz pozycję **Next** (Dalej).

    3. Wprowadź **nazwę** i **adres URL rejestracji** dla serwera MDM z kroku 6 procesu rejestrowania urządzeń z systemem iOS przy użyciu Asystenta ustawień w usłudze Microsoft Intune. W polu adresu URL rejestracji wprowadź adres URL profilu rejestracji wyeksportowany z usługi Intune. Wybierz pozycję **Next** (Dalej).  

       Możesz bezpiecznie zignorować ostrzeżenie informujące, że adres URL serwera nie został zweryfikowany. Aby kontynuować, wybieraj pozycję **Next** (Dalej), aż do ukończenia pracy kreatora.

    4.  Podłącz urządzenia przenośne z systemem iOS do komputera Mac przy użyciu adaptera USB.

        > [!WARNING]
        > Podczas procesu rejestracji urządzenia zostaną zresetowane do konfiguracji fabrycznych. Jako najlepsze rozwiązanie zalecane jest zresetowanie urządzenia i włączenie go. Podczas uruchamiania Asystenta ustawień na urządzeniach powinien być wyświetlany ekran **powitalny**.

    5.  Wybierz pozycję **Prepare**(Przygotuj). W okienku **Prepare iOS Device** (Przygotowywanie urządzenia z systemem iOS) wybierz pozycję **Manual** (Ręcznie), a następnie wybierz pozycję **Next** (Dalej).

    6. W okienku **Enroll in MDM Server** (Rejestrowanie na serwerze MDM) wybierz utworzoną nazwę serwera, a następnie wybierz pozycję **Next** (Dalej).

    7. W okienku **Supervise Devices** (Nadzorowanie urządzeń) wybierz poziom nadzoru, a następnie wybierz pozycję **Next** (Dalej).

    8. W okienku **Create an Organization** (Tworzenie organizacji) wybierz pozycję **Organization** (Organizacja) lub utwórz nową organizację, a następnie wybierz pozycję **Next** (Dalej).

    9. W okienku **Configure iOS Setup Assistant** (Konfigurowanie Asystenta ustawień systemu iOS) wybierz czynności, które mają zostać wyświetlone użytkownikowi, a następnie wybierz pozycję **Prepare** (Przygotuj). Jeśli zostanie wyświetlony monit, uwierzytelnij się w celu zaktualizowania ustawień zaufania.  

    10. Po zakończeniu przygotowywania urządzenia z systemem iOS odłącz kabel USB.  

6.  **Rozdystrybuuj urządzenia**.
    Urządzenia są teraz gotowe do rejestracji w firmie. Wyłącz urządzenia i przekaż je użytkownikom. Po włączeniu urządzeń przez użytkowników zostanie uruchomiony Asystent ustawień.

## <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Jak użytkownicy instalują aplikację Portal firmy i używają jej na urządzeniach

Na urządzeniach skonfigurowanych z koligacją użytkownika można zainstalować aplikację Portal firmy i używać jej do pobierania aplikacji i zarządzania urządzeniami. Po otrzymaniu urządzeń użytkownicy muszą wykonać dodatkowe czynności, które zostały opisane poniżej, w celu ukończenia działania Asystenta ustawień i zainstalowania aplikacji Portal firmy.

### <a name="how-users-enroll-corporate-owned-ios-devices-with-user-affinity"></a>Jak użytkownicy rejestrują urządzenia firmowe z systemem iOS z koligacją użytkownika

1. Po włączeniu urządzenia użytkownicy są monitowani o ukończenie działania Asystenta ustawień. Podczas instalacji użytkownicy są monitowani o podanie swoich poświadczeń. Muszą oni korzystać z poświadczeń (tj. unikatowej kombinacji imienia i nazwiska lub nazwy UPN) skojarzonych z ich subskrypcją w usłudze Intune.

2. Podczas instalacji użytkownicy są monitowani o podanie identyfikatora Apple ID. Muszą podać identyfikator Apple ID, aby umożliwić zainstalowanie aplikacji Portal firmy na urządzeniu. Mogą także podać identyfikator z menu ustawień systemu iOS po zakończeniu konfiguracji.

3. Po ukończeniu konfiguracji na urządzeniu iOS trzeba zainstalować aplikację Portal firmy ze sklepu App Store.

4. Użytkownik może się teraz zalogować do Portalu firmy przy użyciu nazwy UPN użytej podczas konfigurowania urządzenia.

5. Po zalogowaniu użytkownicy otrzymują monit o zarejestrowanie urządzenia. Pierwszym krokiem jest zidentyfikowanie urządzenia. Aplikacja wyświetla listę urządzeń z systemem iOS, które zostały już zarejestrowane przez firmę i przypisane do konta użytkownika w usłudze Intune. Użytkownicy powinni wybrać odpowiednie urządzenie. Jeśli to urządzenie nie zostało jeszcze zarejestrowane przez firmę, użytkownicy powinni wybrać pozycję „Nowe urządzenie”, aby kontynuować standardową procedurę rejestracji.

6. Na następnym ekranie użytkownicy muszą potwierdzić numer seryjny nowego urządzenia. Użytkownik może nacisnąć link „Potwierdź numer seryjny”, aby uruchomić aplikację Ustawienia w celu zweryfikowania numeru seryjnego. Użytkownik musi następnie wprowadzić cztery ostatnie znaki numeru seryjnego do aplikacji Portal firmy.

    Ten krok umożliwia zweryfikowanie, że urządzenie zostało zarejestrowane przez firmę w usłudze Intune. Jeśli numer seryjny urządzenia nie jest zgodny, oznacza to, że wybrano niewłaściwe urządzenie. Użytkownik powinien wrócić do poprzedniego ekranu i wybrać inne urządzenie.

7. Po zweryfikowaniu numeru seryjnego aplikacja Portal firmy wykonuje przekierowanie do witryny internetowej Portalu firmy w celu sfinalizowania rejestracji. Następnie w witrynie pojawia się monit o powrót użytkownika do aplikacji.

Stanowi to zakończenie procesu rejestracji. Użytkownicy mogą od tego momentu używać tego urządzenia z pełnym zestawem funkcji.

