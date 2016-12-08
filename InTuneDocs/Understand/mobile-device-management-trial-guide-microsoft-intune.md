---
title: "Ocena zarządzania urządzeniami przenośnymi za pomocą usługi Microsoft Intune | Microsoft Docs"
description: "Ocena oprogramowania MDM w bezpłatnej wersji próbnej usługi Intune."
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 11/29/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47806f69-303d-41d9-9b0e-9b9445ea24ac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c6b027be273fc074c4ca2836511e65a0dd89654f
ms.openlocfilehash: 4133c64d283682f0be37cd6ac69164ef872a5026


---

# <a name="evaluate-mobile-device-management-in-microsoft-intune"></a>Ocena zarządzania urządzeniami przenośnymi za pomocą usługi Microsoft Intune
Ten przewodnik oceny pokazuje, jak zarządzanie urządzeniami przenośnymi działa w usłudze Intune. Obejmuje on:
- Rejestrowanie urządzenia przeznaczonego do zarządzania przez usługę Intune.
- Tworzenie grup w celu zorganizowania użytkowników i urządzeń.
- Tworzenie i wdrażanie zasad zarządzania niektórych urządzeń do grup.
- Publikowanie aplikacji, umożliwiające użytkownikom zainstalowanie jej na swoim urządzeniu za pomocą zarejestrowanych urządzeń.
<!--- - Monitor the device? View a report of compliant devices?--->
<!--- - Remove the device from management--->

## <a name="assumptions"></a>Założenia
W przewodniku założono, że korzystasz z wersji próbnej wyłącznie do celów oceny i po dokonaniu subskrypcji planujesz rozpocząć od czystego środowiska.

Aby ułatwić rozpoczęcie pracy z wersją próbną, skonfigurowane zostało bardzo proste środowisko, które używa tylko usługi Intune. Założono, że będzie to używana przez Ciebie metoda zarządzania urządzeniami. W różnych miejscach przewodnika wskazujemy jednak bardziej rozbudowaną zawartość techniczną, pomocną w dokładniejszym zapoznaniu się z tematem.

W wersji próbnej można wykonać wszystkie czynności, które można wykonać za pomocą wersji subskrypcyjnej. Jedyną różnicą jest ograniczenie liczby kont użytkowników w wersji próbnej do 100.

## <a name="whats-not-covered"></a>Czego nie zawiera przewodnik
|Jeśli interesują Cię |Przeczytaj to |
|------------------------|----------|
|Program MDM w środowisku nietestowym | [Wprowadzenie](https://docs.microsoft.com/en-us/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune) |
|Program MDM z usługą Intune i programem System Center Configuration Manager | [Hybrydowe zarządzanie urządzeniami przenośnymi](https://docs.microsoft.com/en-us/sccm/mdm/understand/hybrid-mobile-device-management) |

Ponieważ powyższe przewodniki ułatwiają konfigurowanie usługi Intune w środowiskach produkcyjnych, w porównaniu z przewodnikiem oceny są one dłuższe i zawierają o wiele więcej punktów decyzyjnych wymagających rozważenia.

W celu szybkiego zapoznania się z usługą Intune zaleca się rozpoczęcie od przewodnika oceny i późniejsze przejście do innych przewodników.

## <a name="prerequisites-for-this-evaluation"></a>Wymagania wstępne dotyczące tej oceny
- Internet Explorer 10 lub nowsza wersja
- Urządzenie, które będzie używane do testowania, w jaki sposób użytkownicy usługi Intune będą rejestrować swoje urządzenia i zarządzać nimi za pomocą aplikacji Portal firmy. Na potrzeby tego przewodnika firma Microsoft korzysta z urządzenia iPad i telefonu z systemem Android.
- Aby zarządzać urządzeniem iPad lub innym urządzeniem z systemem iOS, potrzebny będzie [certyfikat usługi Apple Push Notification](https://docs.microsoft.com/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).
- [Subskrypcja wersji próbnej usługi Intune](sign-up-for-30-day-trial-microsoft-intune.md)

## <a name="set-your-mdm-authority"></a>Ustawianie urzędu MDM
Pierwszym krokiem, jaki trzeba wykonać, aby zarządzać urządzeniami przenośnymi za pomocą usługi Intune, jest ustawienie **urzędu zarządzania urządzeniami przenośnymi (MDM)**.

Jeśli używasz autonomicznej usługi Intune, zgodnie z założeniem wersji próbnej, lub jeśli korzystasz z usługi Intune jako części subskrypcji Enterprise Mobility + Security (EMS), musisz ustawić usługę Intune jako urząd zarządzania urządzeniami przenośnymi. Oznacza to wyznaczenie Intune jako usługi używanej do zarządzania urządzeniami przenośnymi w Twojej organizacji.

Klienci, którzy chcą korzystać z usługi Intune z programem System Center Configuration Manager do zarządzania urządzeniami przenośnymi, muszą podjąć decyzję, czy rolę urzędu zarządzania urządzeniami przenośnymi ma pełnić usługa Intune czy program Configuration Manager. W środowisku produkcyjnym jest to decyzja ważna, ponieważ aktualnie zmiana tego ustawienia po wprowadzeniu go jest bardzo trudna i wykracza poza zakres tego podręcznika oceny. Aby uzyskać więcej informacji na temat wpływu ustawienia usługi Intune lub programu Configuration Manager w roli urzędu zarządzania urządzeniami przenośnymi, zobacz temat [Wybierz między autonomiczną usługą Intune i hybrydowym zarządzaniem urządzeniami przenośnymi](https://docs.microsoft.com/en-us/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management).

W wersji próbnej firma Microsoft ustawi w roli urzędu zarządzania urządzeniami przenośnymi usługę Intune; nie dotyczy to środowiska produkcyjnego, chyba że zdecydujesz o użyciu wersji próbnej w środowisku produkcyjnym.

1. W [konsoli administracyjnej usługi Intune](https://manage.microsoft.com/) wybierz pozycję **Administracja** &gt; **Zarządzanie urządzeniami przenośnymi**.
2. Na liście **Zadania** wybierz pozycję **Ustaw urząd MDM**. Zostanie otwarte okno dialogowe **Ustawianie urzędu zarządzania urządzeniami przenośnymi** . <!---screen shot--->
3. Usługa Intune zażąda potwierdzenia zamiaru ustawienia usługi Intune jako urzędu zarządzania urządzeniami przenośnymi. Zaznacz pole wyboru, a następnie wybierz przycisk **Tak**, aby zarządzać urządzeniami przenośnymi przy użyciu usługi Intune.

## <a name="enroll-your-test-devices-into-intune"></a>Rejestrowanie urządzeń testowych w usłudze Intune

Na potrzeby tego przewodnika firma Microsoft zarejestruje telefon z systemem Android i urządzenie iPad firmy Apple, ale udostępnia linki do tematu [Dowiedz się więcej o rejestracji urządzenia w usłudze Intune](#Learn-more-about-device-enrollment) na końcu tej sekcji.
### <a name="android"></a>Android
Zainstaluj aplikację **Portal firmy usługi Intune** firmy Microsoft Corporation, dostępną w sklepie [Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612), i zaloguj się przy użyciu [poświadczeń użytkownika usługi Intune dodanych przez Ciebie](sign-up-for-30-day-trial-microsoft-intune.md#add-users) podczas rejestracji do bezpłatnej wersji próbnej.

### <a name="ios"></a>iOS
Aby użytkownicy mogli rejestrować urządzenia z systemem iOS, należy skonfigurować usługę Intune do zarządzania tymi urządzeniami.

1. **Pobierz żądanie podpisania certyfikatu**<br/>
Zaloguj się do usługi Intune za pomocą konta administracyjnego i przejdź do opcji **Administracja** > **Zarządzanie urządzeniami przenośnymi** > **iOS i Mac OS X** > **Przekaż certyfikat usługi APNs**, a następnie wybierz opcję **Pobierz żądanie certyfikatu APNs**. Zapisz lokalnie plik żądania podpisania certyfikatu (CSR). Plik CSR jest używany na potrzeby żądania certyfikatu relacji zaufania w portalu Apple Push Certficates. <!--- screen shot--->
2.  **Pobierz certyfikat usługi Apple Push Notification**<BR/>
Przejdź do obszaru [Portal Apple Push Certificates](https://idmsa.apple.com/IDMSWebAuth/login?appIdKey=3fbfc9ad8dfedeb78be1d37f6458e72adc3160d1ad5b323a9e5c5eb2f8e7e3e2&rv=2) i zaloguj się przy użyciu firmowego identyfikatora Apple ID, aby utworzyć certyfikat usługi APNs za pomocą pliku CSR. Po kliknięciu przycisku **Upload (Przekaż) w portalu wypychania certyfikatu firmy Apple** otrzymasz plik JSON, którego nie można użyć dla usługi APNs. Ukończ pobieranie, wróć do portalu wypychania certyfikatu firmy Apple, przejdź do obszaru Certificates for Third-Party Servers (Certyfikaty dla serwerów innych firm) i wybierz polecenie **Download** (Pobierz).

 Pobierz certyfikat usługi APNs (PEM) i zapisz plik lokalnie. Ten identyfikator Apple ID musi zostać użyty później w celu odnowienia certyfikatu usługi APNs.
3.  **Dodaj certyfikat usługi APNs do usługi Intune**<BR/>
W konsoli administracyjnej usługi Microsoft Intune przejdź do obszaru **Administracja** > **Zarządzanie urządzeniami przenośnymi** > **iOS i Mac OS X** > **Prześlij certyfikat usługi APNs**, a następnie wybierz polecenie **Prześlij certyfikat usługi APNs**. Przejdź do pliku certyfikatu (PEM) i wybierz pozycję **Otwórz**, a następnie wprowadź identyfikator Apple ID. Z certyfikatem APNs. Usługa Intune może rejestrować urządzenia z systemem iOS i zarządzać nimi, wypychając zasady do zarejestrowanych urządzeń przenośnych.
4.  **Poinformuj użytkowników, jak mogą zarejestrować swoje urządzenia w celu uzyskania dostępu do zasobów firmy.**<br/>
Aby uzyskać instrukcje dla użytkowników końcowych dotyczące rejestrowania, zobacz tematy [Rejestrowanie urządzenia z systemem iOS w usłudze Intune](https://docs.microsoft.com/en-us/Intune/enduser/enroll-your-device-in-intune-ios) i [Rejestrowanie urządzenia z systemem Mac OS X w usłudze Intune](https://docs.microsoft.com/en-us/Intune/enduser/enroll-your-device-in-intune-mac-os-x). W trakcie procesu rejestracji użytkownicy są informowani, czego mogą oczekiwać, a także co administratorzy IT mogą i czego nie mogą wyświetlać na swoich urządzeniach.


### <a name="learn-more-about-device-enrollment"></a>Dowiedz się więcej o rejestracji urządzeń

Usługa Intune obsługuje następujące platformy urządzeń:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

Wymagania umożliwiające zarządzanie urządzeniami zależą od platformy, którą chcesz zarządzać.
- Urządzenia przenośne z systemem **Android** umożliwiają użytkownikom [rejestrację przy użyciu aplikacji portalu firmy](/intune/deploy-use/set-up-android-management-with-microsoft-intune) dostępnej w sklepie Google Play. Nie jest wymagana dodatkowa konfiguracja w usłudze Intune.
- [Wymagania konfiguracji dla systemów **iOS i Mac OS X**](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)
- [Wymagania konfiguracji dla **systemu Windows Phone**](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune).

<!--- ## Verify enrollment--->
<!--- START HERE

### iOS and Mac OS X
Install the **Microsoft Intune Company Portal** app from Microsoft Corporation available in the App Store and sign in with Intune user credentials added above. View **Enrolled devices** to add your device.



### Windows Phone 8.1
Users install the **Company Portal** app from Microsoft Corporation, available in the Windows Phone store, and sign in with the Intune user credentials added above.  View **Enrolled devices** to add your device.

## Install the previously deployed app
Open the Company Portal on the mobile device, choose **Apps**, and then install **Microsoft Skype**.--->



## <a name="next-steps"></a>Następne kroki
[Tworzenie grup w celu zorganizowania użytkowników i urządzeń](get-started-with-a-30-day-trial-of-microsoft-intune-step-3.md)



<!--HONumber=Nov16_HO5-->


