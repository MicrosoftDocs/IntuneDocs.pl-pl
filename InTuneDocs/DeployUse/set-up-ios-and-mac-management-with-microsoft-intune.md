---
# required metadata

title: Konfigurowanie zarządzania systemem iOS i komputerami Mac przez usługę Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: dc451224-1372-4b84-b641-cfa67cb3849b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Konfigurowanie zarządzania systemem iOS i komputerami Mac
Usługa Microsoft Intune umożliwia rejestrację urządzeń z systemami iOS i Mac OS X zgodnie z modelem „Przynieś własne urządzenie” (BYOD, Bring Your Own Device) w celu udzielenia dostępu użytkownikom telefonów iPhone, tabletów iPad i komputerów Mac do aplikacji i poczty e-mail firmy. Zarejestrowani użytkownicy mogą zainstalować aplikację Portal firmy usługi Intune, a ustawianie zasad dla ich urządzeń będzie możliwe przy użyciu konsoli administracyjnej usługi Intune.

Aby można było zarządzać urządzeniami z systemem iOS w usłudze Intune, urządzenia muszą być w stanie nawiązać połączenia z usługą Intune. Firma Apple wymaga relacji zaufania z usługą Intune, którą należy ustanowić przez zaimportowanie certyfikatu usługi Apple Push Notification service (APNs).

1.  **Konfigurowanie usługi Intune**<br>
    Jeśli usługa ta nie została jeszcze skonfigurowana, przygotuj się do zarządzania urządzeniami przenośnymi, [ustawiając urząd zarządzania urządzeniami przenośnymi](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority) na usługę **Microsoft Intune** i konfigurując zarządzanie urządzeniami przenośnymi.

2.  **Pobieranie żądania podpisania certyfikatu**<br>
    Jako administrator otwórz [konsolę administracyjną usługi Microsoft Intune](http://manage.microsoft.com), wybierz pozycje **Administracja** &gt; **Zarządzanie urządzeniami przenośnymi** &gt; **iOS i Mac OS X** &gt; **Przekaż certyfikat APNs**, a następnie kliknij pozycję **Pobierz żądanie certyfikatu APNs**. Zapisz lokalnie plik żądania podpisania certyfikatu (CSR). Plik CSR jest używany na potrzeby żądania certyfikatu relacji zaufania w portalu Apple Push Certficates.

    ![Okno dialogowe przekazywania certyfikatu APNs](../media/Intune-iOS-enrollment-with-apns.png)

3.  **Pobieranie certyfikatu usługi Apple Push Notification service**<br>
    Przejdź do pozycji [Portal Apple Push Certificates](http://go.microsoft.com/fwlink/?LinkId=269844) i zaloguj się przy użyciu firmowego identyfikatora Apple ID, aby utworzyć certyfikat usługi APNs za pomocą pliku CSR. Po kliknięciu przycisku **Upload** (Przekaż) w portalu Apple Push Certificates otrzymasz plik JSON, którego nie można użyć dla usługi APNs. Ukończ pobieranie i powróć do portalu Apple Push Certificates do obszaru **Certificates for Third-Party Servers** (Certyfikaty serwerów innych firm) i kliknij przycisk **Download** (Pobierz)..

    Pobierz certyfikat usługi APN (PEM) i zapisz plik lokalnie. Ten identyfikator Apple ID musi być w przyszłości używany do odnawiania certyfikatu usługi APN.

4.  **Dodawanie certyfikatu usługi APNs do usługi Intune**<br>
    W [konsoli administracyjnej usługi Microsoft Intune](http://manage.microsoft.com)wybierz pozycje **Administracja** &gt; **Zarządzanie urządzeniami przenośnymi** &gt; **iOS i Mac OS X** &gt; **Przekaż certyfikat APNs**, a następnie kliknij pozycje **Przekaż certyfikat APNs**. **Przeglądaj** aby znaleźć plik certyfikatu (PEM). Następnie kliknij pozycję **Otwórz** i wprowadź swój identyfikator **Apple ID**. Dzięki certyfikatowi usługi APN usługa Intune może rejestrować urządzenia z systemem iOS i zarządzać nimi, wypychając zasady do zarejestrowanych urządzeń przenośnych.

5.  **Informowanie użytkowników, jak uzyskać dostęp do zasobów firmy za pomocą Portalu firmy**<br>
    Użytkownicy muszą dowiedzieć się, jak zarejestrować swoje urządzenia i czego oczekiwać po rozpoczęciu zarządzania nimi. [Co mówić użytkownikom końcowym na temat korzystania z usługi Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)

Jeśli Twoja firma lub organizacja zakupi dla użytkowników urządzenia z systemem iOS, te urządzenia również będzie można zarejestrować do zarządzania jako [urządzenia z systemem iOS należące do firmy](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)..

### Zobacz też
[Przygotowanie do rejestracji urządzeń w usłudze Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


