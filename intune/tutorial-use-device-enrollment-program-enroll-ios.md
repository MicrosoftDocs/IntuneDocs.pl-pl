---
title: Samouczek — używanie usługi Apple Business Manager lub programu Device Enrollment Program do rejestrowania urządzeń z systemem iOS w usłudze Intune
titleSuffix: Microsoft Intune
description: W tym samouczku skonfigurujesz funkcje rejestracji firmowych urządzeń firmy Apple z usługą ABM do rejestrowania urządzeń z systemem iOS w usłudze Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/30/2019
ms.topic: tutorial
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
Customer intent: As an Intune admin, I want to set up the Apple's corporate device enrollment features so that corporate devices can automatically enroll in Intune.
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1fda4268e66703c8bd2132c9af22fed52f1791b1
ms.sourcegitcommit: bccfbf1e3bdc31382189fc4489d337d1a554e6a1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/03/2019
ms.locfileid: "67548952"
---
# <a name="tutorial-use-apples-corporate-device-enrollment-features-in-apple-business-manager-abm-to-enroll-ios-devices-in-intune"></a>Samouczek: Użyj funkcji rejestracji urządzeń firmowych firmy Apple w usłudze Apple Business Manager (ABM) do rejestrowania urządzeń z systemem iOS w usłudze Intune
Funkcje rejestracji urządzeń w usłudze Apple Business Manager ułatwiają rejestrowanie urządzeń. Usługa Intune obsługuje również starszy portal programu Device Enrollment Program (DEP) firmy Apple, ale zachęcamy, aby zacząć od zera za pomocą usługi Apple Business Manager. Za pomocą usługi Microsoft Intune i rejestracji urządzeń firmowych firmy Apple urządzenia są automatycznie bezpiecznie rejestrowane za pierwszym razem, gdy użytkownik włączy urządzenie. Umożliwia to dostarczanie urządzeń wielu użytkownikom bez konieczności indywidualnego konfigurowania każdego urządzenia. 

Z tego samouczka dowiesz się, jak wykonywać następujące czynności:
> [!div class="checklist"]
> * Pobieranie tokenu rejestracji urządzeń firmy Apple
> * Synchronizowanie urządzeń zarządzanych w usłudze Intune
> * Tworzenie profilu rejestracji
> * Przypisywanie profilu rejestracji do urządzeń

Jeśli nie masz subskrypcji usługi Intune, [utwórz konto bezpłatnej wersji próbnej](free-trial-sign-up.md).

## <a name="prerequisites"></a>Wymagania wstępne
- Urządzenia zakupione za pośrednictwem usługi [Apple Business Manager](https://business.apple.com) lub programu [Device Enrollment Program firmy Apple](http://deploy.apple.com)
- Ustawianie [urzędu zarządzania urządzeniem przenośnym](mdm-authority-set.md)
- Uzyskiwanie [certyfikatu wypychania MDM firmy Apple](apple-mdm-push-certificate-get.md)

## <a name="get-an-apple-device-enrollment-token"></a>Pobieranie tokenu rejestracji urządzeń firmy Apple
Przed zarejestrowaniem urządzeń z systemem iOS za pomocą funkcji rejestracji firmowej firmy Apple będzie potrzebny plik tokenu (pem) rejestracji urządzeń firmy Apple. Ten token umożliwia usłudze Intune synchronizację informacji dotyczących urządzeń firmy Apple należących do Twojej firmy. Umożliwia on również usłudze Intune przekazywanie profilów rejestracji do firmy Apple i przypisywanie urządzeń do tych profilów.

Użyj usługi ABM lub portalu DEP, aby utworzyć token rejestracji urządzenia. W tych portalach można również przypisać urządzenia do funkcji zarządzania usługi Intune.

1. W usłudze [Intune w witrynie Azure Portal](https://aka.ms/intuneportal) wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu rejestracji** > **Dodaj**.

2. Udziel firmie Microsoft uprawnień do wysyłania informacji o użytkowniku i urządzeniu do firmy Apple, wybierając pozycję **Zgadzam się**.

   ![Zrzut ekranu przedstawiający okienko tokenu programu Enrollment Program w obszarze roboczym certyfikatów firmy Apple umożliwiające pobranie klucza publicznego.](./media/device-enrollment-program-enroll-ios-newui/add-enrollment-program-token-pane.png)

3. Wybierz pozycję **Pobierz klucz publiczny**, aby pobrać i zapisać lokalnie plik klucza szyfrowania (PEM). Plik pem jest używany na potrzeby żądania certyfikatu relacji zaufania z usługi ABM lub portalu DEP.

4. Wybierz pozycję **Utwórz token programu Device Enrollment Program firmy Apple**, aby otworzyć portal programu wdrażania firmy Apple i zalogować się przy użyciu firmowego konta Apple ID. Tego identyfikatora firmy Apple możesz użyć do odnowienia tokenu DEP.

5. W [portalu programów wdrażania](https://deploy.apple.com) firmy Apple wybierz pozycję **Get Started** (Rozpocznij) dla opcji **Device Enrollment Program**. Twój proces może się nieco różnić od poniższych kroków w usłudze [Apple Business Manager](https://business.apple.com).

4. Na stronie **Manage Servers** (Zarządzanie serwerami) wybierz pozycję **Add MDM Server** (Dodaj serwer MDM).

5. W polu **MDM Server Name** (Nazwa serwera MDM) wpisz *TestMDMServer*, a następnie wybierz pozycję **Next** (Dalej). Nazwa serwera służy użytkownikowi do identyfikowania serwera MDM. Nie jest to nazwa ani adres URL serwera usługi Microsoft Intune.

6. Zostanie otwarte okno dialogowe **Add &lt;nazwa_serwera&gt;** (Dodawanie serwera <nazwa_serwera>) z widocznym komunikatem **Upload Your Public Key** (Przekaż klucz publiczny). Wybierz pozycję **Choose File…** (Wybierz plik...) w celu przekazania pliku PEM, a następnie kliknij przycisk **Next** (Dalej).

6. Wybierz pozycję **Deployment Programs** (Programy wdrażania)  > **Device Enrollment Program** > **Manage Devices** (Zarządzaj urządzeniami).
7. W obszarze **Choose Devices By** (Wybierz urządzenia według) wybierz pozycję **Serial Number** (Numer seryjny). <!--ask Tiffany about this-->

8. W kroku **Choose Action** (Wybierz akcję) wybierz pozycję **Assign to Server** (Przypisz do serwera), wybierz &lt;nazwę serwera&gt; określoną dla usługi Microsoft Intune, a następnie kliknij przycisk **OK**. Portal firmy Apple przypisze wskazane urządzenia do funkcji zarządzania na serwerze Intune, a następnie wyświetli komunikat **Assignment Complete** (Przypisanie zostało ukończone).

   W portalu firmy Apple wybierz pozycję **Deployment Programs** (Programy wdrażania) &gt; **Device Enrollment Program** &gt; **View Assignment History** (Wyświetl historię przypisania), aby wyświetlić listę urządzeń i ich przypisania do serwera MDM.

9. W usłudze Intune w witrynie Azure Portal podaj identyfikator Apple ID do użytku w przyszłości.

    ![Zrzut ekranu przedstawiający wprowadzanie identyfikatora Apple ID używanego do utworzenia tokenu programu rejestracji i przechodzenie do tokenu programu rejestracji.](./media/device-enrollment-program-enroll-ios/image03.png)

10. W polu **Token Apple** przejdź do pliku certyfikatu (.pem), wybierz pozycję **Otwórz**, a następnie kliknij **Utwórz**. 

11. Jeśli chcesz zastosować tagi zakresu w celu ograniczenia tego, którzy administratorzy mają dostęp do tego tokenu, wybierz zakresy.

## <a name="create-an-apple-enrollment-profile"></a>Tworzenie profilu rejestracji firmy Apple
Teraz, po zainstalowaniu tokenu, możesz utworzyć profil rejestracji dla należących do firmy urządzeń z systemem iOS. Profil rejestracji urządzeń określa ustawienia stosowane do grupy urządzeń podczas rejestracji.

1. W usłudze Intune w witrynie Azure Portal wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu Enrollment Program**.

2. Wybierz właśnie zainstalowany token i wybierz pozycję **Profile** > **Utwórz profil**.

3. W obszarze **Tworzenie profilu** wprowadź wartość *TestDEPProfile* w polu **Nazwa** oraz *Testowanie programu DEP dla urządzeń z systemem iOS* w polu **Opis**. Te szczegóły nie są widoczne dla użytkowników.

4. Wybierz pozycję **iOS** w obszarze **Platforma**.

5. Określ, czy chcesz, aby Twoje urządzenia rejestrowały się z **koligacją użytkownika**, czy bez niej. Koligacja użytkownika jest przeznaczona dla urządzeń, które będą używane przez określonych użytkowników. Jeśli użytkownicy będą chcieli używać Portalu firmy na przykład do instalowania aplikacji, wybierz polecenie **Zarejestruj z użyciem koligacji użytkowników**. Jeśli użytkownicy nie potrzebują Portalu firmy lub jeśli chcesz aprowizować urządzenie dla wielu użytkowników, wybierz polecenie **Zarejestruj bez koligacji użytkowników**.

6. Jeśli wybierzesz opcję rejestracji z użyciem koligacji użytkowników, określ, czy chcesz przeprowadzać uwierzytelnianie za pomocą Portalu firmy, czy też asystenta ustawień firmy Apple. Jeśli chcesz używać uwierzytelniania Multi-Factor Authentication, zezwól użytkownikom na zmianę hasła podczas pierwszego logowania lub monituj użytkowników o zresetowanie ich wygasłych haseł podczas rejestracji oraz wybierz pozycję **Tak** w obszarze **Uwierzytelnianie za pomocą portalu firmy zamiast asystenta ustawień firmy Apple**. Jeśli odpowiada Ci korzystanie z dostarczanego przez firmę Apple podstawowego uwierzytelniania za pomocą protokołu HTTP i asystenta ustawień firmy Apple, wybierz pozycję **Nie**.

7. Jeśli wybierzesz rejestrację przy użyciu koligacji użytkownika i uwierzytelnianie za pomocą Portalu firmy, określ, czy chcesz zainstalować Portal firmy przy użyciu programu Volume Purchase Program (VPP) firmy Apple. Jeśli zainstalujesz Portal firmy przy użyciu tokenu programu VPP, użytkownik nie będzie musiał wprowadzać identyfikatora Apple ID i hasła, aby pobrać Portal firmy ze sklepu App Store podczas rejestracji. Wybierz pozycję **Użyj tokenu:** w obszarze **Instalowanie portalu firmy przy użyciu programu VPP**, aby wybrać token programu VPP, który ma dostępne bezpłatne licencje portalu firmy. Jeśli nie chcesz używać programu VPP do wdrażania Portalu firmy, wybierz pozycję **Nie używaj programu VPP** w obszarze **Instalowanie portalu firmy przy użyciu programu VPP**. 

8. Jeśli wybierzesz rejestrację z koligacją użytkownika, uwierzytelnianie za pomocą Portalu firmy i instalowanie Portalu firmy przy użyciu programu VPP, musisz zdecydować, czy chcesz uruchomić portal firmy w trybie pojedynczej aplikacji do chwili uwierzytelnienia. To ustawienie da Ci pewność, że użytkownik nie będzie miał dostępu do innych aplikacji do czasu zakończenia rejestracji w firmie. Jeśli chcesz, aby do czasu ukończenia rejestracji użytkownik miał dostęp tylko do tego przepływu, wybierz pozycję **Tak** w obszarze **Uruchom portal firmy w trybie pojedynczej aplikacji do momentu uwierzytelnienia**. 

9. Wybierz pozycję **Ustawienia zarządzania urządzeniami** i wybierz pozycję **Tak** w obszarze **Nadzorowane**. Nadzorowane urządzenia udostępniają najwięcej opcji zarządzania dla firmowych urządzeń z systemem iOS.

10. Wybierz pozycję **Tak** w obszarze **Zablokowana rejestracja**, aby upewnić się, że użytkownicy nie mogą usunąć zarządzania urządzeniami firmowymi. 

11. Wybierz opcję w obszarze **Synchronizacja z komputerami**, aby ustalić, czy urządzenia z systemem iOS będą mogły synchronizować się z komputerami.

12. Domyślnie firma Apple nazywa urządzenia po ich typie (np. iPad). Jeśli chcesz podać inny szablon nazwy, wybierz pozycję **Tak** w obszarze **Zastosuj szablon nazwy urządzenia**. Wprowadź nazwę, którą chcesz zastosować do urządzeń, gdzie ciągi *{{SERIAL}}* i *{{DEVICETYPE}}* zostaną zastąpione przez numer seryjny i typ każdego urządzenia. W przeciwnym razie wybierz pozycję **Nie** w obszarze **Zastosuj szablon nazwy urządzenia**.

13. Wybierz przycisk **OK**.

14. Wybierz pozycję **Dostosowywanie Asystenta ustawień** i wpisz *Dział samouczka* w polu **Nazwa działu**. To właśnie ten ciąg zobaczą użytkownicy, gdy wybiorą pozycję **Informacje o konfiguracji** podczas aktywacji urządzenia.

15. Wprowadź numer telefonu w obszarze **Telefon działu**. Ten numer jest wyświetlany, gdy użytkownicy wybiorą pozycję **Potrzebna pomoc** podczas aktywacji.

16. Możesz **pokazać** lub **ukryć** różne ekrany podczas aktywacji urządzenia. Aby uzyskać najbardziej bezproblemowe środowisko rejestracji, wybierz dla wszystkich ekranów pozycję **Ukryj**.

17. Wybierz pozycję **OK** > **Utwórz**.

## <a name="sync-managed-devices-to-intune"></a>Synchronizowanie urządzeń zarządzanych w usłudze Intune

Po skonfigurowaniu tokenu programu rejestracji za pomocą usługi ABM, funkcji ASM lub portalu DEP i przypisaniu tam urządzeń do serwera MDM możesz poczekać na zsynchronizowanie tych urządzeń z usługą Intune lub ręcznie wypchnąć synchronizację. Bez ręcznej synchronizacji pokazanie urządzenia w witrynie Azure Portal może zająć nawet do 24 godzin.

1. W usłudze Intune w witrynie Azure Portal wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu rejestracji** > wybierz token z listy > **Urządzenia** > **Synchronizuj**.

## <a name="assign-an-enrollment-profile-to-ios-devices"></a>Przypisywanie profilu rejestracji do urządzeń z systemem iOS

Zanim możliwe będzie rejestrowanie urządzeń, należy przypisać profil programu rejestracji. Urządzenia te są synchronizowane z usługą Intune z firmy Apple i muszą zostać przypisane do odpowiednich tokenów serwera MDM w usłudze ABM, funkcji ASM lub portalu DEP.

1. W usłudze Intune w witrynie Azure Portal wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu rejestracji** > wybierz swój token z listy.
2. Wybierz **Urządzenia** > wybierz urządzenia na liście > **Przypisz profil**.
3. W obszarze **Przypisz profil** wybierz profil dla urządzeń > **Przypisz**.

## <a name="distribute-devices-to-users"></a>Przekazywanie urządzeń użytkownikom

Skonfigurowano zarządzanie i synchronizację między danymi firmy Apple i usługą Intune oraz przypisano profil umożliwiający rejestrowanie urządzeń korzystających z programu DEP. Możesz teraz przekazać urządzenia użytkownikom. W przypadku urządzeń z koligacją użytkownika wymagane jest, aby poszczególni użytkownicy mieli przypisane licencje na korzystanie z usługi Intune.

## <a name="next-steps"></a>Następne kroki

Możesz zapoznać się z dalszymi informacjami na temat innych opcji dostępnych dla rejestrowania urządzeń z systemem iOS.

> [!div class="nextstepaction"]
> [Szczegółowy artykuł dotyczący rejestracji programu DEP dla systemu iOS](device-enrollment-program-enroll-ios.md)

<!--commenting out because inaccurate>
## Clean up resources
<!--If you don't want to use iOS corporate enrolled devices anymore, you can delete them.>
<!--- If the devices are enrolled in Intune, you must first [delete them from the Azure Active Directory portal](devices-wipe.md#delete-devices-from-the-azure-active-directory-portal).>
