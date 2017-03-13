---
title: "Konfigurowanie zarządzania systemem iOS i komputerami Mac | Microsoft Docs"
description: "Włącz w usłudze Microsoft Intune zarządzanie urządzeniami mobilnymi (MDM) dla urządzeń z systemem iOS, w tym urządzeń iPad i iPhone, a także urządzeń z systemem Mac OS X."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc451224-1372-4b84-b641-cfa67cb3849b
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: afca2af0b07b939adc66c8804f04a1125e12001b
ms.openlocfilehash: 9c71a83f9514187753360fa9c2085584d1b76711
ms.lasthandoff: 02/18/2017


---

# <a name="set-up-ios-and-mac-device-management"></a>Konfigurowanie zarządzania systemem iOS i komputerami Mac

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Usługa Intune umożliwia zarządzanie urządzeniami przenośnymi typu iPad, iPhone oraz urządzeniami z systemem macOS i zapewnia użytkownikom dostęp do poczty e-mail oraz aplikacji firmy. Aby zarządzać urządzeniami z systemem iOS i komputerami Mac, wymagany jest certyfikat usługi Apple Push Notification service (APNs). Po dodaniu certyfikatu do usługi Intune użytkownicy mogą zainstalować aplikację Portal firmy, aby zarejestrować swoje urządzenia, lub administrator może skonfigurować [zarządzanie urządzeniami z systemem iOS należącymi do firmy](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

1.  **Skonfiguruj usługę**<br>
    Jeśli usługa ta nie została jeszcze skonfigurowana, przygotuj się do zarządzania urządzeniami przenośnymi, [ustawiając urząd zarządzania urządzeniami przenośnymi](prerequisites-for-enrollment.md#step-2-set-mdm-authority) na usługę **Microsoft Intune** i konfigurując zarządzanie urządzeniami przenośnymi.

2.  **Pobierz żądanie podpisania certyfikatu**<br>
    Jako administrator otwórz [konsolę administracyjną usługi Microsoft Intune](http://manage.microsoft.com), przejdź do obszaru **Administracja** &gt; **Zarządzanie urządzeniami przenośnymi** &gt; **iOS i Mac OS X** &gt; **Prześlij certyfikat APNs**, a następnie wybierz polecenie **Pobierz żądanie certyfikatu usługi APNs**. Zapisz lokalnie plik żądania podpisania certyfikatu (CSR). Plik CSR jest używany na potrzeby żądania certyfikatu relacji zaufania w portalu Apple Push Certficates.

    ![Okno dialogowe przekazywania certyfikatu APNs](../media/Intune-iOS-enrollment-with-apns.png)

3.  **Pobierz certyfikat usługi Apple Push Notification**<br>
    Przejdź do obszaru [Portal Apple Push Certificates](http://go.microsoft.com/fwlink/?LinkId=269844) i zaloguj się przy użyciu firmowego identyfikatora Apple ID, aby utworzyć certyfikat usługi APNs za pomocą pliku CSR. Po kliknięciu przycisku **Upload** (Przekaż) w witrynie Apple Push Certificates Portal otrzymasz plik JSON, którego nie można użyć dla usługi APNs. Ukończ pobieranie, wróć do witryny Apple Push Certificates Portal, przejdź do obszaru **Certificates for Third-Party Servers** (Certyfikaty dla serwerów innych firm) i wybierz polecenie **Download** (Pobierz).

    Pobierz certyfikat usługi APNs (PEM) i zapisz plik lokalnie.

    > [!NOTE]
    > Co roku musisz odnowić (nie zastąpić) ten certyfikat usługi APNs. Użyj tego samego identyfikatora Apple ID do logowania do portalu wypychania certyfikatu firmy Apple w celu odnowienia certyfikatu, a następnie użyj instrukcji z tego tematu w celu pobrania certyfikatu i przekazania go do usługi Intune.

4.  **Dodaj certyfikat usługi APNs do usługi Intune**<br>
    W [konsoli administracyjnej usługi Microsoft Intune](http://manage.microsoft.com) przejdź do obszaru **Administracja** &gt; **Zarządzanie urządzeniami przenośnymi** &gt; **iOS i Mac OS X** &gt; **Prześlij certyfikat usługi APNs**, a następnie wybierz polecenie **Prześlij certyfikat usługi APNs**. Przejdź do pliku certyfikatu (PEM) i wybierz pozycję **Otwórz**, a następnie wprowadź identyfikator **Apple ID**. Dzięki certyfikatowi usługi APN usługa Intune może rejestrować urządzenia z systemem iOS i zarządzać nimi, wypychając zasady do zarejestrowanych urządzeń przenośnych.

5.  **Poinformuj użytkowników, jak mogą zarejestrować swoje urządzenia w celu uzyskania dostępu do zasobów firmy.**

    Aby uzyskać instrukcje dla użytkowników końcowych dotyczące rejestrowania, zobacz tematy [Rejestrowanie urządzenia z systemem iOS w usłudze Intune](../enduser/enroll-your-device-in-intune-ios.md) i [Rejestrowanie urządzenia z systemem macOS w usłudze Intune](../enduser/enroll-your-device-in-intune-macos.md). W trakcie procesu rejestracji użytkownicy są informowani, czego mogą oczekiwać, a także co administratorzy IT mogą i czego nie mogą wyświetlać na swoich urządzeniach.

    Aby uzyskać informacje o innych zadaniach użytkownika końcowego, zobacz następujące artykuły:
    - [Zasoby dotyczące środowiska użytkownika końcowego w usłudze Microsoft Intune](how-to-educate-your-end-users-about-microsoft-intune.md)
    - [Wskazówki dla użytkowników końcowych korzystających z urządzeń z systemami iOS i Mac](../enduser/using-your-ios-or-macOS-device-with-intune.md)

Jeśli Twoja firma lub organizacja zakupi dla użytkowników urządzenia z systemem iOS, te urządzenia również będzie można zarejestrować do zarządzania jako [urządzenia z systemem iOS należące do firmy](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

### <a name="see-also"></a>Zobacz też
[Wymagania wstępne dotyczące rejestracji w usłudze Microsoft Intune](prerequisites-for-enrollment.md)

