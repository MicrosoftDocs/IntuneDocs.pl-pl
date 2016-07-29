---
title: "Konfigurowanie zarządzania systemem iOS i komputerami Mac | Microsoft Intune"
description: "Włącz w usłudze Microsoft Intune zarządzanie urządzeniami mobilnymi (MDM) dla urządzeń z systemem iOS, w tym urządzeń iPad i iPhone, a także urządzeń z systemem Mac OS X."
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 07/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc451224-1372-4b84-b641-cfa67cb3849b
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 26ac7d52c0ad3e37e517b60d448a94849c0f4b30
ms.openlocfilehash: f393f2f34658d9c4c341f1c961e9dd527fcec4b1


---

# Konfigurowanie zarządzania systemem iOS i komputerami Mac
Zarządzanie urządzeniami przenośnymi iPad, iPhone oraz urządzeniami z systemem Mac OS X w usłudze Intune zapewnia dostęp do poczty e-mail i aplikacji firmy. Aby zarządzać urządzeniami z systemem iOS i komputerami Mac, wymagany jest certyfikat usługi Apple Push Notification service (APNs). Po dodaniu certyfikatu do usługi Intune użytkownicy mogą zainstalować aplikację Portal firmy, aby zarejestrować swoje urządzenia, lub administrator może skonfigurować [zarządzanie urządzeniami z systemem iOS należącymi do firmy](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

1.  **Konfigurowanie usługi Intune**<br>
    Jeśli usługa ta nie została jeszcze skonfigurowana, przygotuj się do zarządzania urządzeniami przenośnymi, [ustawiając urząd zarządzania urządzeniami przenośnymi](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority) na usługę **Microsoft Intune** i konfigurując zarządzanie urządzeniami przenośnymi.

2.  **Pobieranie żądania podpisania certyfikatu**<br>
    Jako administrator otwórz [konsolę administracyjną usługi Microsoft Intune](http://manage.microsoft.com), wybierz pozycje **Administracja** &gt; **Zarządzanie urządzeniami przenośnymi** &gt; **iOS i Mac OS X** &gt; **Prześlij certyfikat APNs**, a następnie kliknij pozycję **Pobierz żądanie certyfikatu usługi APNs**. Zapisz lokalnie plik żądania podpisania certyfikatu (CSR). Plik CSR jest używany na potrzeby żądania certyfikatu relacji zaufania w portalu Apple Push Certficates.

    ![Okno dialogowe przekazywania certyfikatu APNs](../media/Intune-iOS-enrollment-with-apns.png)

3.  **Pobieranie certyfikatu usługi Apple Push Notification service**<br>
    Przejdź do pozycji [Portal Apple Push Certificates](http://go.microsoft.com/fwlink/?LinkId=269844) i zaloguj się przy użyciu firmowego identyfikatora Apple ID, aby utworzyć certyfikat usługi APNs za pomocą pliku CSR. Po kliknięciu przycisku **Upload** (Przekaż) w portalu Apple Push Certificates otrzymasz plik JSON, którego nie można użyć dla usługi APNs. Ukończ pobieranie i powróć do portalu Apple Push Certificates do obszaru **Certificates for Third-Party Servers** (Certyfikaty serwerów innych firm) i kliknij przycisk **Download** (Pobierz).

    Pobierz certyfikat usługi APN (PEM) i zapisz plik lokalnie. Ten identyfikator Apple ID musi być w przyszłości używany do odnawiania certyfikatu usługi APN.

4.  **Dodawanie certyfikatu usługi APNs do usługi Intune**<br>
    W [konsoli administracyjnej usługi Microsoft Intune](http://manage.microsoft.com) wybierz pozycje **Administracja** &gt; **Zarządzanie urządzeniami przenośnymi** &gt; **iOS i Mac OS X** &gt; **Prześlij certyfikat usługi APNs**, a następnie kliknij pozycję **Prześlij certyfikat usługi APNs**. **Przejdź** do pliku certyfikatu (PEM) i kliknij przycisk **Otwórz** , a następnie wprowadź identyfikator **Apple ID**. Dzięki certyfikatowi usługi APN usługa Intune może rejestrować urządzenia z systemem iOS i zarządzać nimi, wypychając zasady do zarejestrowanych urządzeń przenośnych.

5.  **Informowanie użytkowników, jak uzyskać dostęp do zasobów firmy za pomocą Portalu firmy**<br>
    Użytkownicy muszą dowiedzieć się, jak zarejestrować swoje urządzenia i czego oczekiwać po rozpoczęciu zarządzania nimi. [Co mówić użytkownikom końcowym na temat korzystania z usługi Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)

Jeśli Twoja firma lub organizacja zakupi dla użytkowników urządzenia z systemem iOS, te urządzenia również będzie można zarejestrować do zarządzania jako [urządzenia z systemem iOS należące do firmy](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

### Zobacz też
[Przygotowanie do rejestracji urządzeń w usłudze Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Jul16_HO3-->


