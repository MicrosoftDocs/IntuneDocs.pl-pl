---
title: "Konfigurowanie zarządzania systemem iOS i komputerami Mac | Microsoft Intune"
description: "Włącz w usłudze Microsoft Intune zarządzanie urządzeniami mobilnymi (MDM) dla urządzeń z systemem iOS, w tym urządzeń iPad i iPhone, a także urządzeń z systemem Mac OS X."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc451224-1372-4b84-b641-cfa67cb3849b
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b3f6323912707d56d23380217a07e6474593d83f
ms.openlocfilehash: f93f7bfe99e878691dccd24c124a781c8607e7c6


---

# Konfigurowanie zarządzania systemem iOS i komputerami Mac
Pomoc dotyczącą konfigurowania urządzenia z systemem iOS lub Mac znajdziesz w temacie [Using your iOS or Mac OS X device with Intune](../enduser/using-your-ios-or-mac-os-x-device-with-intune.md) (Korzystanie z urządzenia z systemem iOS lub Mac OS X w usłudze Intune).

Usługa Intune umożliwia zarządzanie urządzeniami przenośnymi typu iPad, iPhone oraz urządzeniami z systemem Mac OS X i zapewnia użytkownikom dostęp do poczty e-mail oraz aplikacji firmy. Aby zarządzać urządzeniami z systemem iOS i komputerami Mac, wymagany jest certyfikat usługi Apple Push Notification service (APNs). Po dodaniu certyfikatu do usługi Intune użytkownicy mogą zainstalować aplikację Portal firmy, aby zarejestrować swoje urządzenia, lub administrator może skonfigurować [zarządzanie urządzeniami z systemem iOS należącymi do firmy](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

1.  **Konfigurowanie usługi Intune**<br>
    Jeśli usługa ta nie została jeszcze skonfigurowana, przygotuj się do zarządzania urządzeniami przenośnymi, [ustawiając urząd zarządzania urządzeniami przenośnymi](prerequisites-for-enrollment.md#set-mobile-device-management-authority) na usługę **Microsoft Intune** i konfigurując zarządzanie urządzeniami przenośnymi.

2.  **Pobieranie żądania podpisania certyfikatu**<br>
    Jako administrator otwórz [konsolę administracyjną usługi Microsoft Intune](http://manage.microsoft.com), przejdź do obszaru **Administracja** &gt; **Zarządzanie urządzeniami przenośnymi** &gt; **iOS i Mac OS X** &gt; **Prześlij certyfikat APNs**, a następnie wybierz polecenie **Pobierz żądanie certyfikatu usługi APNs**. Zapisz lokalnie plik żądania podpisania certyfikatu (CSR). Plik CSR jest używany na potrzeby żądania certyfikatu relacji zaufania w portalu Apple Push Certficates.

    ![Okno dialogowe przekazywania certyfikatu APNs](../media/Intune-iOS-enrollment-with-apns.png)

3.  **Pobieranie certyfikatu usługi Apple Push Notification service**<br>
    Przejdź do obszaru [Portal Apple Push Certificates](http://go.microsoft.com/fwlink/?LinkId=269844) i zaloguj się przy użyciu firmowego identyfikatora Apple ID, aby utworzyć certyfikat usługi APNs za pomocą pliku CSR. Po kliknięciu przycisku **Upload** (Przekaż) w witrynie Apple Push Certificates Portal otrzymasz plik JSON, którego nie można użyć dla usługi APNs. Ukończ pobieranie, wróć do witryny Apple Push Certificates Portal, przejdź do obszaru **Certificates for Third-Party Servers** (Certyfikaty dla serwerów innych firm) i wybierz polecenie **Download** (Pobierz).

    Pobierz certyfikat usługi APNs (PEM) i zapisz plik lokalnie. Ten identyfikator Apple ID musi zostać użyty później w celu odnowienia certyfikatu usługi APNs.

4.  **Dodawanie certyfikatu usługi APNs do usługi Intune**<br>
    W [konsoli administracyjnej usługi Microsoft Intune](http://manage.microsoft.com) przejdź do obszaru **Administracja** &gt; **Zarządzanie urządzeniami przenośnymi** &gt; **iOS i Mac OS X** &gt; **Prześlij certyfikat usługi APNs**, a następnie wybierz polecenie **Prześlij certyfikat usługi APNs**. Przejdź do pliku certyfikatu (PEM) i wybierz pozycję **Otwórz**, a następnie wprowadź identyfikator **Apple ID**. Dzięki certyfikatowi usługi APN usługa Intune może rejestrować urządzenia z systemem iOS i zarządzać nimi, wypychając zasady do zarejestrowanych urządzeń przenośnych.

5.  **Informowanie użytkowników, jak uzyskać dostęp do zasobów firmy za pomocą Portalu firmy**<br>
    Użytkownicy muszą dowiedzieć się, jak zarejestrować swoje urządzenia i czego oczekiwać po rozpoczęciu zarządzania nimi.
    - [Co mówić użytkownikom końcowym na temat korzystania z usługi Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
    - [Wskazówki dla użytkowników końcowych urządzeń z systemami iOS i Mac](../enduser/using-your-ios-or-mac-os-x-device-with-intune.md)

Jeśli Twoja firma lub organizacja zakupi dla użytkowników urządzenia z systemem iOS, te urządzenia również będzie można zarejestrować do zarządzania jako [urządzenia z systemem iOS należące do firmy](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

### Zobacz też
[Wymagania wstępne dotyczące rejestrowania w usłudze Microsoft Intune](prerequisites-for-enrollment.md)



<!--HONumber=Oct16_HO3-->


