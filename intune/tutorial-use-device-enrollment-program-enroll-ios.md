---
title: Samouczek — rejestrowanie urządzeń z systemem iOS w usłudze Intune przy użyciu programu Device Enrollment Program
titleSuffix: Microsoft Intune
description: W tym samouczku skonfigurujesz program DEP firmy Apple do rejestrowania urządzeń z systemem iOS w usłudze Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/30/2019
ms.topic: tutorial
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
Customer intent: As an Intune admin, I want to set up the Device Enrollment Program so that users can automatically enroll in Intune.
ms.collection: M365-identity-device-management
ms.openlocfilehash: 17258ce2bd671dba091fa7206e599858e5ec7a93
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55841542"
---
# <a name="tutorial-use-the-device-enrollment-program-to-enroll-ios-devices-in-intune"></a>Samouczek: rejestrowanie urządzeń z systemem iOS w usłudze Intune przy użyciu programu Device Enrollment Program
Program Device Enrollment Program (DEP) firmy Apple ułatwia rejestrowanie urządzeń. Dzięki usłudze Microsoft Intune i programowi DEP urządzenia są automatycznie rejestrowane przy pierwszym uruchomieniu urządzenia przez użytkownika. Umożliwia to dostarczanie urządzeń wielu użytkownikom bez konieczności indywidualnego konfigurowania każdego urządzenia. 

Z tego samouczka dowiesz się, jak wykonywać następujące czynności:
> [!div class="checklist"]
> * Uzyskiwanie tokenu DEP od firmy Apple
> * Tworzenie grupy urządzeń rozwiązania Autopilot
> * Tworzenie profilu wdrażania rozwiązania Autopilot
> * Przypisywanie profilu wdrażania rozwiązania Autopilot do grupy urządzeń
> * Przekazywanie urządzeń z systemem Windows użytkownikom

Jeśli nie masz subskrypcji usługi Intune, [utwórz konto bezpłatnej wersji próbnej](free-trial-sign-up.md).

## <a name="prerequisites"></a>Wymagania wstępne
- Urządzenia zakupione za pośrednictwem [programu Device Enrollment firmy Apple](http://deploy.apple.com)
- Ustawianie [urzędu zarządzania urządzeniem przenośnym](mdm-authority-set.md)
- Uzyskiwanie [certyfikatu wypychania MDM firmy Apple](apple-mdm-push-certificate-get.md)

## <a name="get-an-apple-dep-token"></a>Uzyskiwanie tokenu DEP od firmy Apple
Przed zarejestrowaniem urządzeń z systemem iOS w programie DEP będzie potrzebny plik tokenu (pem) programu DEP firmy Apple. Ten token umożliwia usłudze Intune synchronizację informacji dotyczących urządzeń korzystających z programu DEP należących do firmy. Umożliwia on również usłudze Intune przekazywanie profilów rejestracji do firmy Apple i przypisywanie urządzeń do tych profilów.

W portalu Apple DEP Portal można utworzyć token programu DEP. W tym portalu można również przypisać urządzenia do funkcji zarządzania usługi Intune.

1. W usłudze [Intune w witrynie Azure Portal](https://aka.ms/intuneportal) wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu rejestracji** > **Dodaj**.

2. Udziel firmie Microsoft uprawnień do wysyłania informacji o użytkowniku i urządzeniu do firmy Apple, wybierając pozycję **Zgadzam się**.

   ![Zrzut ekranu przedstawiający okienko tokenu programu Enrollment Program w obszarze roboczym certyfikatów firmy Apple umożliwiające pobranie klucza publicznego.](./media/device-enrollment-program-enroll-ios-newui/add-enrollment-program-token-pane.png)

3. Wybierz pozycję **Pobierz klucz publiczny**, aby pobrać i zapisać lokalnie plik klucza szyfrowania (PEM). Plik PEM jest używany na potrzeby żądania certyfikatu relacji zaufania z portalu programu Device Enrollment Program firmy Apple.

4. Wybierz pozycję **Utwórz token programu Device Enrollment Program firmy Apple**, aby otworzyć portal programu wdrażania firmy Apple i zalogować się przy użyciu firmowego konta Apple ID. Tego identyfikatora firmy Apple możesz użyć do odnowienia tokenu DEP.

5.  W [portalu programów wdrażania](https://deploy.apple.com) firmy Apple wybierz pozycję **Get Started** (Rozpocznij) dla opcji **Device Enrollment Program**.

4. Na stronie **Manage Servers** (Zarządzanie serwerami) wybierz pozycję **Add MDM Server** (Dodaj serwer MDM).

5. W polu **MDM Server Name** (Nazwa serwera MDM) wpisz *TestMDMServer*, a następnie wybierz pozycję **Next** (Dalej). Nazwa serwera służy użytkownikowi do identyfikowania serwera MDM. Nie jest to nazwa ani adres URL serwera usługi Microsoft Intune.

6. Zostanie otwarte okno dialogowe **Add &lt;nazwa_serwera&gt;** (Dodawanie serwera <nazwa_serwera>) z widocznym komunikatem **Upload Your Public Key** (Przekaż klucz publiczny). Kliknij pozycję **Choose File…** (Wybierz plik...) w celu przekazania pliku PEM, a następnie kliknij przycisk **Next** (Dalej).

6. Wybierz pozycję **Deployment Programs** (Programy wdrażania)  > **Device Enrollment Program** > **Manage Devices** (Zarządzaj urządzeniami).
7. W obszarze **Choose Devices By** (Wybierz urządzenia według) wybierz pozycję **Serial Number** (Numer seryjny). <!--ask Tiffany about this-->

8. W kroku **Choose Action** (Wybierz akcję) wybierz pozycję **Assign to Server** (Przypisz do serwera), wybierz &lt;nazwę serwera&gt; określoną dla usługi Microsoft Intune, a następnie kliknij przycisk **OK**. Portal firmy Apple przypisze wskazane urządzenia do funkcji zarządzania na serwerze Intune, a następnie wyświetli komunikat **Assignment Complete** (Przypisanie zostało ukończone).

   W portalu firmy Apple wybierz pozycję **Deployment Programs** (Programy wdrażania) &gt; **Device Enrollment Program** &gt; **View Assignment History** (Wyświetl historię przypisania), aby wyświetlić listę urządzeń i ich przypisania do serwera MDM.

9. W usłudze Intune w witrynie Azure Portal podaj identyfikator Apple ID do użytku w przyszłości.

    ![Zrzut ekranu przedstawiający wprowadzanie identyfikatora Apple ID używanego do utworzenia tokenu programu rejestracji i przechodzenie do tokenu programu rejestracji.](./media/device-enrollment-program-enroll-ios/image03.png)

10. W polu **Token Apple** przejdź do pliku certyfikatu (.pem), wybierz pozycję **Otwórz**, a następnie kliknij **Utwórz**. 

## <a name="create-an-apple-enrollment-profile"></a>Tworzenie profilu rejestracji firmy Apple
Teraz, po zainstalowaniu tokenu, możesz utworzyć profil rejestracji dla urządzeń korzystających z programu DEP. Profil rejestracji urządzeń określa ustawienia stosowane do grupy urządzeń podczas rejestracji.

1. W usłudze Intune w witrynie Azure Portal wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu Enrollment Program**.

2. Wybierz właśnie zainstalowany token i wybierz pozycję **Profile** > **Utwórz profil**.

3. W obszarze **Tworzenie profilu** wprowadź wartość *TestDEPProfile* w polu **Nazwa** oraz *Testowanie programu DEP dla urządzeń z systemem iOS* w polu **Opis**. Te szczegóły nie są widoczne dla użytkowników.

4. W polu **Koligacja użytkownika** wybierz pozycję **Zarejestruj z użyciem koligacji użytkowników**. Ta opcja dotyczy urządzeń należących do użytkowników, którzy chcą korzystać z portalu firmy na potrzeby usług takich jak instalowanie aplikacji.

5. Wybierz pozycję **Nie** w obszarze **Uwierzytelnij za pomocą aplikacji Portal firmy zamiast Asystenta konfiguracji firmy Apple**.

6. Wybierz pozycję **Ustawienia zarządzania urządzeniami** i wybierz pozycję **Nie** w obszarze **Nadzorowane**. Urządzenia nadzorowane zapewniają więcej opcji zarządzania, ale ten samouczek nie obejmuje korzystania z nich.

7. Wybierz przycisk **OK**.

8. Wybierz pozycję **Dostosowywanie Asystenta ustawień** i wpisz *Dział samouczka* w polu **Nazwa działu**. To właśnie ten ciąg zobaczą użytkownicy, gdy wybiorą pozycję **Informacje o konfiguracji** podczas aktywacji urządzenia.

9. Wprowadź numer telefonu w obszarze **Telefon działu**. Ten numer jest wyświetlany, gdy użytkownicy wybiorą pozycję **Potrzebna pomoc** podczas aktywacji.

10. Możesz **pokazać** lub **ukryć** różne ekrany podczas aktywacji urządzenia. Na potrzeby tego samouczka ustaw wartość właściwości **Kod dostępu** na **Pokaż**, a dla wszystkich pozostałych wartość **Ukryj**.

11. Wybierz pozycję **OK** > **Utwórz**.

## <a name="sync-managed-devices"></a>Synchronizowanie urządzeń zarządzanych

Możesz teraz zobaczyć, które urządzenia są przypisane do tego tokenu.

1. W usłudze Intune w witrynie Azure Portal wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu rejestracji** > wybierz token z listy > **Urządzenia** > **Synchronizuj**.

## <a name="assign-an-enrollment-profile-to-ios-devices"></a>Przypisywanie profilu rejestracji do urządzeń z systemem iOS

Zanim możliwe będzie rejestrowanie urządzeń, należy przypisać profil programu rejestracji.

1. W usłudze Intune w witrynie Azure Portal wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu rejestracji** > wybierz swój token z listy.
2. Wybierz **Urządzenia** > wybierz urządzenia na liście > **Przypisz profil**.
3. W obszarze **Przypisz profil** wybierz profil dla urządzeń > **Przypisz**.

## <a name="distribute-devices-to-users"></a>Przekazywanie urządzeń użytkownikom

Skonfigurowano zarządzanie i synchronizację między danymi firmy Apple i usługą Intune oraz przypisano profil umożliwiający rejestrowanie urządzeń korzystających z programu DEP. Możesz teraz przekazać urządzenia użytkownikom. W przypadku urządzeń z koligacją użytkownika wymagane jest, aby poszczególni użytkownicy mieli przypisane licencje na korzystanie z usługi Intune.

## <a name="clean-up-resources"></a>Oczyszczanie zasobów

Jeśli nie chcesz już używać urządzeń rozwiązania Autopilot, możesz je usunąć.

- Jeśli urządzenia są zarejestrowane w usłudze Intune, musisz najpierw [usunąć je z portalu usługi Azure Active Directory](devices-wipe.md#delete-devices-from-the-azure-active-directory-portal).

<!--ask tiffany how to do this-->

## <a name="next-steps"></a>Następne kroki

Możesz zapoznać się z dalszymi informacjami na temat innych opcji dostępnych dla rejestrowania urządzeń z systemem iOS.

> [!div class="nextstepaction"]
> [Szczegółowy artykuł dotyczący rejestracji programu DEP dla systemu iOS](device-enrollment-program-enroll-ios.md)
