---
# required metadata

title: Rozpoczynanie pracy z wersją próbną usługi Microsoft Intune i wdrażanie zasad dotyczących numeru PIN w systemie iOS | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 06cb9a73-0f17-44b3-b334-86c98020316e

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Rozpoczynanie pracy z wersją próbną usługi Microsoft Intune i wdrażanie zasad dotyczących numeru PIN w systemie iOS
Te szczegółowe instrukcje pomogą Ci skonfigurować wersję próbną usługi Intune i zasady dotyczące numeru PIN dla urządzeń z systemem iOS. Listę innych typowych zadań dotyczących oceny w usłudze Intune do wypróbowania można znaleźć w temacie [Typowe zadania oceny usługi Microsoft Intune](common-microsoft-intune-evaluation-tasks.md)..



## Przeglądanie wymagań wstępnych dotyczących tego zadania

-   Komputer z systemem Windows i programem Internet Explorer — do wykonywania zadań administracyjnych

-   Urządzenie z systemem iOS 7.1 lub nowszym na potrzeby weryfikowania zasad testowania użytkowników

-   Telefon do uwierzytelniania osoby podczas tworzenia konta wersji próbnej

## Tworzenie bezpłatnego konta wersji próbnej usługi Intune
> [!NOTE]
> Jeśli masz już subskrypcję usługi Intune, pomiń tę sekcję i przejdź do następnej.

1.  Na komputerze z systemem Windows kliknij prawym przyciskiem myszy program **Internet Explorer** (IE) i wybierz pozycję **Przeglądanie InPrivate**..

    ![Rozpoczynanie przeglądania InPrivate](../media/30-day-trial-walkthrus/30day-start-trial-1-InPrivate.png)

2.  Przejdź do [portalu tworzenia konta usługi Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1), podaj wymagane informacje i kliknij przycisk **Dalej**..

    ![Rejestrowanie się w celu utworzenia konta](../media/30-day-trial-walkthrus/30day-start-trial-2-abt-you.png)

3.  Wprowadź identyfikator użytkownika i hasło do konta administratora, a następnie kliknij przycisk **Dalej**. Ten identyfikator będzie używany podczas logowania do portalu Intune w celu wykonania zadań administracyjnych.

    ![Tworzenie identyfikatora](../media/30-day-trial-walkthrus/30day-start-trial-3-createID.png)

4.  Wprowadź numer telefonu komórkowego, a następnie kliknij pozycję **Wyślij do mnie SMS-a**, aby zweryfikować swój numer.

    ![Sprawdzanie poprawności informacji](../media/30-day-trial-walkthrus/30day-start-trial-4-textme.png)

5.  Zapisz informacje wyświetlone na ekranie, a następnie kliknij pozycję oznaczającą, że **wszystko jest gotowe**..

    ![Gotowość](../media/30-day-trial-walkthrus/30day-start-trial-5-ReadyToGo.png)

## Tworzenie użytkownika testowego

1.  Na komputerze z systemem Windows kliknij przycisk **Start**, aby przejść do strony zarządzania użytkownikami.

    ![Przechodzenie do strony zarządzania użytkownikami](../media/30-day-trial-walkthrus/30day-crt-user-6-click-start.png)

2.  Kliknij przycisk **+**, aby dodać użytkownika.

    ![Dodawanie użytkownika](../media/30-day-trial-walkthrus/30day-crt-user-7-click-plus.png)

3.  Na stronie **Tworzenie nowego konta użytkownika**:

    1.  Podaj informacje o użytkowniku testowym.

    2.  Wybierz opcję **Wpisz hasło**.

    3.  Usuń zaznaczenie pola wyboru **Nakłoń tę osobę do zmiany hasła przy następnym logowaniu**.

    4.  Kliknij przycisk **Utwórz**..

    ![Tworzenie nowego konta użytkownika](../media/30-day-trial-walkthrus/30day-crt-user-8-add-user-info.png)

4.  Na stronie potwierdzenia utworzenia użytkownika kliknij przycisk **Zamknij**..

    ![Strona potwierdzenia utworzenia użytkownika](../media/30-day-trial-walkthrus/30day-crt-user-9-close-confirm.png)

5.  Kliknij przycisk **Odśwież**, aby wyświetlić dane utworzonego użytkownika.

    ![Potwierdzenie konta](../media/30-day-trial-walkthrus/30day-crt-user-10-refresh-user.png)

## Konfigurowanie zasad dotyczących numeru PIN systemu iOS dla użytkownika testowego

1.  Na komputerze z systemem Windows ustaw urząd zarządzania urządzeniami przenośnymi na usługę Intune:

    1.  Przejdź do [konsoli zarządzania usługą Intune](http://manage.microsoft.com/), zaloguj się przy użyciu konta administratora i kliknij pozycję **Rozpocznij zarządzanie urządzeniami przenośnymi**. Zostanie otwarta strona urzędu zarządzania urządzeniami przenośnymi.

        ![Wprowadzenie do konsoli usługi Intune](../media/30-day-trial-walkthrus/30day-cfg-pol-11-start-mg-mobl-dev.png)

    2.  Kliknij link **Ustaw urząd zarządzania urządzeniami przenośnymi**.

        ![Ustawianie źródła zarządzania urządzeniem przenośnym](../media/30-day-trial-walkthrus/30day-cfg-pol-12-link-set-mdm.png)

2.  Włączanie rejestracji urządzeń z systemem iOS. Ten proces powoduje ustawienie zaufanego certyfikatu między usługą Apple Push Notification Service (APNs) i subskrypcją usługi Intune.

    1.  Kliknij pozycję **Włącz platformę systemów iOS i Mac OS X**..

        ![Włączanie rejestracji systemu iOS i Mac OS X](../media/30-day-trial-walkthrus/30day-cfg-pol-13-enbl-ios-plat.png)

    2.  Kliknij pozycję **Pobierz żądanie certyfikatu APNs**..

        ![Pobieranie certyfikatu APNs](../media/30-day-trial-walkthrus/30day-cfg-pol-14-dwnld-cert-reqst.png)

    3.  Określ nazwę pliku i lokalizację żądania podpisania certyfikatu (CSR, Certificate Signing Request), a następnie kliknij przycisk **Zapisz**. Ten plik zawiera klucz publiczny odpowiadający kluczowi prywatnemu przechowywanemu w ramach subskrypcji usługi Intune.

        ![Określanie żądania podpisania certyfikatu](../media/30-day-trial-walkthrus/30day-cfg-pol-15-cert-name-loc.png)

    4.  Kliknij **portal certyfikatów Apple Push**, aby utworzyć nową kartę.

        ![Przechodzenie do strony certyfikatów APNs](../media/30-day-trial-walkthrus/30day-cfg-pol-16-cert-portl-link.png)

    5.  Wprowadź identyfikator Apple ID i hasło, a następnie kliknij pozycję **Zaloguj się**. Ten identyfikator może być używany na urządzeniu z systemem iOS w celu pobrania aplikacji ze sklepu iOS App Store.

        ![Logowanie się w portalu certyfikatów Apple Push](../media/30-day-trial-walkthrus/30day-cfg-pol-17-id-passw-signin.png)

    6.  Kliknij pozycję **Utwórz certyfikat**..

        ![Tworzenie certyfikatu APNs](../media/30-day-trial-walkthrus/30day-cfg-pol-18-create-cert.png)

    7.  Przeczytaj warunki użytkowania produktów firmy Apple, zaznacz pole wyboru, a następnie kliknij pozycję **Akceptuj**..

        ![Akceptowanie warunków](../media/30-day-trial-walkthrus/30day-cfg-pol-19-TOU.png)

    8.  Kliknij pozycję **Przeglądaj**..

        ![Przechodzenie do lokalizacji, w której zapisano certyfikat](../media/30-day-trial-walkthrus/30day-cfg-pol-20-browse.png)

    9. Wybierz zapisany wcześniej plik CSR, a następnie kliknij pozycję **Otwórz**..

        ![Otwieranie certyfikatu](../media/30-day-trial-walkthrus/30day-cfg-pol-21-CSRfile-open.png)

    10. Kliknij przycisk **Przekaż**.

        ![Przekazywanie certyfikatu](../media/30-day-trial-walkthrus/30day-cfg-pol-22-upld-reqst.png)

    11. Gdy zostanie wyświetlony monit o pobranie pliku JSON, kliknij pozycję **Zapisz jako**..

        ![Zapisywanie pliku JSON](../media/30-day-trial-walkthrus/30day-cfg-pol-23-json-saveas.png)

    12. Określ lokalizację pliku JSON, a następnie kliknij pozycję **Zapisz**..

        ![Określanie lokalizacji zapisu pliku JSON](../media/30-day-trial-walkthrus/30day-cfg-pol-24-json-save-loc.png)

        Jeśli po kilku sekundach nie nastąpi automatyczne przekierowanie ze strony, kliknij pozycję **Anuluj**..

        ![Anulowanie w przypadku braku przekierowania ze strony](../media/30-day-trial-walkthrus/30day-cfg-pol-25-json-pg-cancel.png)

    13. Aby pobrać nowo utworzony plik certyfikatu, kliknij pozycję **Pobierz**..

        ![Pobieranie certyfikatu](../media/30-day-trial-walkthrus/30day-cfg-pol-26-dwnld-retrv-cert.png)

    14. Gdy zostanie wyświetlony monit o pobranie pliku PEM, kliknij pozycję **Zapisz jako**..

        ![Pobieranie pliku PEM](../media/30-day-trial-walkthrus/30day-cfg-pol-27-pem-saveas.png)

    15. Określ lokalizację pliku PEM, a następnie kliknij pozycję **Zapisz**..

        ![Zapisywanie pliku PEM](../media/30-day-trial-walkthrus/30day-cfg-pol-28-pem-save-loc.png)

    16. Wróć do karty konsoli zarządzania usługą Intune, a następnie kliknij pozycję **Prześlij certyfikat APNs**..

        ![Przekazywanie certyfikatu APNs](../media/30-day-trial-walkthrus/30day-cfg-pol-29-upld-cert.png)

    17. Wprowadź identyfikator Apple ID, a następnie kliknij pozycję **Przeglądaj**..

        ![Wprowadzanie identyfikatora Apple ID](../media/30-day-trial-walkthrus/30day-cfg-pol-30-app-id-browse.png)

    18. Wybierz zapisany plik PEM, a następnie kliknij pozycję **Otwórz**..

        ![Otwieranie pliku PEM](../media/30-day-trial-walkthrus/30day-cfg-pol-31-sel-pem-open.png)

    19. Kliknij pozycję **Przekaż**..

        ![Przekazywanie pliku PEM](../media/30-day-trial-walkthrus/30day-cfg-pol-32-pem-upload.png)

        Certyfikat usługi APNs został skonfigurowany.

        ![Ukończenie konfiguracji certyfikatu APNs](../media/30-day-trial-walkthrus/30day-cfg-pol-33-apns-confgd.png)

3.  Tworzenie testowej grupy użytkowników do użycia z zasadami:

    1.  W lewym okienku kliknij pozycję **Grupy**..

        ![Otwieranie obszaru roboczego Grupy](../media/30-day-trial-walkthrus/30day-cfg-pol-34-clk-groups.png)

    2.  Kliknij pozycję **Utwórz grupę** po prawej stronie..

        ![Tworzenie grupy](../media/30-day-trial-walkthrus/30day-cfg-pol-35-crt-group.png)

    3.  Podaj nazwę grupy, wybierz grupę **Wszyscy użytkownicy** jako nadrzędną, a następnie kliknij przycisk **Dalej**..

        ![Wybieranie grupy Wszyscy użytkownicy jako grupy nadrzędnej](../media/30-day-trial-walkthrus/30day-cfg-pol-36-name-group.png)

    4.  W polu **Uruchom członkostwo grupy w** wybierz pozycję **Wszyscy użytkownicy w grupie nadrzędnej** i kliknij przycisk **Zakończ**..

        ![Uruchamianie członkostwa grupy w grupie nadrzędnej](../media/30-day-trial-walkthrus/30day-cfg-pol-37-all-users-group.png)

4.  Tworzenie zasad numeru PIN w systemie iOS i stosowanie ich w testowej grupie użytkowników:

    1.  W lewym okienku kliknij pozycję **Zasady**..

        ![Otwieranie obszaru roboczego zasad](../media/30-day-trial-walkthrus/30day-cfg-pol-38-clk-policy.png)

    2.  Kliknij pozycję **Dodaj zasady** po prawej stronie..

        ![Dodawanie zasad](../media/30-day-trial-walkthrus/30day-cfg-pol-39-add-policy.png)

    3.  Rozwiń węzeł systemu iOS, wybierz wiersz **Konfiguracja ogólna**, a następnie kliknij pozycję **Utwórz zasady**..

        ![Tworzenie ogólnych zasad konfiguracji systemu iOS](../media/30-day-trial-walkthrus/30day-cfg-pol-40-gen_cfg_pol.png)

    4.  Wpisz nazwę zasad, włącz opcję **Wymagaj hasła do odblokowania urządzeń przenośnych** i ustaw wartość **Minimalna długość hasła** na **4**..

        ![Konfigurowanie ustawień haseł](../media/30-day-trial-walkthrus/30day-cfg-pol-41-name-policy.png)

    5.  Kliknij przycisk **Tak**, aby wdrożyć zasady.

        ![Wdrażanie zasad](../media/30-day-trial-walkthrus/30day-cfg-pol-42-yes-deploy-pol.png)

    6.  Kliknij utworzoną wcześniej grupę użytkowników, kliknij przycisk **Dodaj**, a następnie kliknij przycisk **OK**..

        ![Wybieranie grupy dla zasad](../media/30-day-trial-walkthrus/30day-cfg-pol-43-add-pol-to-grp.png)

        Utworzono zasady numeru PIN w systemie iOS związane z testową grupą użytkowników.

        ![Ukończenie konfigurowania zasad](../media/30-day-trial-walkthrus/30day-cfg-pol-44-policy-applied.png)

## Sprawdzanie, czy zasady są wymuszane na urządzeniu z systemem iOS

1.  Na urządzeniu iPad uruchom sklep iOS App Store, zainstaluj bezpłatną aplikację **Portal firmy usługi Microsoft Intune** i otwórz ją.

    ![Instalowanie portalu firmy](../media/30-day-trial-walkthrus/30day-cfg-pol-45-cportal-installed.png)

2.  Wprowadź nazwę konta i hasło użytkownika testowego, a następnie naciśnij pozycję **Zaloguj się**..

    ![Wprowadzanie poświadczeń](../media/30-day-trial-walkthrus/30day-cfg-pol-46-cportal-signin.png)

3.  Naciśnij pozycję **Zarejestruj**, aby rozpocząć rejestrowanie urządzenia w usłudze Intune.

    ![Rozpoczynanie rejestrowania](../media/30-day-trial-walkthrus/30day-cfg-pol-47-tap-enroll.jpg)

4.  Na ekranie **Instalowanie profilu** naciśnij pozycję **Zainstaluj**..

    ![Instalowanie profilu](../media/30-day-trial-walkthrus/30day-cfg-pol-48-profile-install-1.jpg)

5.  W oknie dialogowym **Instalowanie profilu** naciśnij pozycję **Zainstaluj**..

    ![Kontynuowanie instalowania profilu](../media/30-day-trial-walkthrus/30day-cfg-pol-49-profile-install-2.jpg)

6.  Na ekranie **Ostrzeżenie** naciśnij pozycję **Zainstaluj**..

    ![Akceptowanie komunikatu ostrzegawczego](../media/30-day-trial-walkthrus/30day-cfg-pol-50-warning-install-3.png)

7.  W oknie dialogowym **Zdalne zarządzanie** naciśnij pozycję **Ufaj**..

    ![Pozycja Ufaj w oknie dialogowym Zdalne zarządzanie](../media/30-day-trial-walkthrus/30day-cfg-pol-51-remt-mgmt-trust.jpg)

8.  Po zakończeniu instalowania profilu zarządzania naciśnij pozycję **Gotowe**. Rejestracja została zakończona.

    ![Ukończenie rejestracji](../media/30-day-trial-walkthrus/30day-cfg-pol-52-profile-done.jpg)

9. Po zakończeniu rejestracji naciśnij przycisk **OK**, a następnie zamknij aplikację Portal firmy.

    ![Naciśnięcie pozycji OK w celu zamknięcia aplikacji Portal firmy](../media/30-day-trial-walkthrus/30day-cfg-pol-53-devc-enrolled-ok.png)

10. Po wyświetleniu monitu o skonfigurowanie kodu dostępu naciśnij pozycję **Kontynuuj**..

    ![Akceptowanie monitu o skonfigurowanie kodu dostępu](../media/30-day-trial-walkthrus/30day-cfg-pol-54-passcode-req-cont.png)

11. Wprowadź kod dostępu, naciśnij pozycję **Kontynuuj**, wprowadź ponownie kod dostępu i naciśnij pozycję **Zapisz**..

    ![Podawanie kodu dostępu](../media/30-day-trial-walkthrus/30day-cfg-pol-55-passcode-enter.jpg)

12. Naciśnij przycisk zasilania, aby zablokować urządzenie iPad, przesuń, aby je odblokować, i zobaczysz, że teraz musisz wprowadzić kod dostępu w celu odblokowania urządzenia.

### Zobacz także
[Przewodnik dotyczący oceny usługi Intune](get-started-with-a-30-day-trial-of-microsoft-intune.md)


<!--HONumber=May16_HO1-->


