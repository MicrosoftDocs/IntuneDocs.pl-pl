---
title: "Podczas próby zarejestrowania urządzenia z systemem iOS w usłudze Intune występuje błąd | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 92a8d06d-0ecb-4912-898b-993e8eaf4e58
searchScope:
- Company Portal
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 9da632e906a1486ac705a0af99179ce9669c8a24


---

# <a name="you-see-errors-while-trying-to-enroll-your-ios-device-in-intune"></a>Podczas próby zarejestrowania urządzenia z systemem iOS w usłudze Intune występuje błąd

Poniższa tabela zawiera listę błędów, które mogą występować podczas rejestrowania urządzeń z systemem iOS w usłudze Intune. Udostępnij ten link administratorowi IT. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](http://portal.manage.microsoft.com).

|Komunikat o błędzie|Problem|Co powiedzieć administratorowi IT|
|-----------------|---------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|NoEnrollmentPolicy|Brak zasad rejestracji|Sprawdź, czy skonfigurowane zostały wszystkie wymagania wstępne rejestracji, takie jak certyfikat usługi Apple Push Notification Service (APNs), i czy opcja „iOS jako platforma” jest włączona. Aby uzyskać instrukcje, zobacz [Konfigurowanie zarządzania systemem iOS i komputerami Mac](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).|
|DeviceCapReached|Zarejestrowano już zbyt wiele urządzeń przenośnych.|Aby można było zarejestrować kolejne urządzenie przenośne, użytkownik musi usunąć jedno z obecnie zarejestrowanych urządzeń przenośnych z Portalu firmy. Zapoznaj się z instrukcjami dotyczącymi odpowiedniego typu urządzenia: [Android](unenroll-your-device-from-intune-android.md), [iOS](unenroll-your-device-from-intune-ios.md) lub [Windows](unenroll-your-device-from-intune-windows.md).|
|APNSCertificateNotValid|Występuje problem z certyfikatem umożliwiającym urządzeniu przenośnemu komunikowanie się z siecią firmową.<br /><br />Skontaktuj się z administratorami IT i poinformuj ich o pojawieniu się komunikatu **APNSCertificateNotValid** podczas próby zarejestrowania urządzenia przenośnego oraz poproś o zapoznanie się z rozwiązaniem w tej tabeli.|Usługa Apple Push Notification Service (APNs) udostępnia kanał dostępu do zarejestrowanych urządzeń z systemem iOS. Jeśli nie wykonano procedury uzyskiwania certyfikatu usługi APNs lub certyfikat usługi APNs wygasł, próby rejestracji zakończą się niepowodzeniem oraz zostanie wyświetlony ten komunikat.<br /><br />Przejrzyj informacje na temat sposobu konfigurowania użytkowników w sekcjach [Synchronizacja usługi Active Directory i dodawanie użytkowników do usługi Intune](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-3) oraz [Organizowanie użytkowników i urządzeń](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5).|
|AccountNotOnboarded|Występuje problem z certyfikatem umożliwiającym urządzeniu przenośnemu komunikowanie się z siecią firmową.<br /><br />Skontaktuj się z administratorami IT i poinformuj ich o pojawieniu się komunikatu **APNSNotOnboarded** podczas próby zarejestrowania urządzenia przenośnego oraz poproś o zapoznanie się z rozwiązaniem w tej tabeli.|Usługa Apple Push Notification Service (APNs) udostępnia kanał dostępu do zarejestrowanych urządzeń z systemem iOS. Jeśli nie wykonano procedury uzyskiwania certyfikatu usługi APNs lub certyfikat usługi APNs wygasł, próby rejestracji zakończą się niepowodzeniem oraz zostanie wyświetlony ten komunikat.<br /><br />Aby uzyskać więcej informacji, zobacz [Konfigurowanie zarządzania systemem iOS i komputerami Mac przez usługę Microsoft Intune](/Intune/Deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).|
|DeviceTypeNotSupported|Prawdopodobnie podjęto próbę zarejestrowania urządzenia z systemem innym niż iOS. Typ urządzenia przenośnego, które próbujesz zarejestrować, nie jest obsługiwany.<br /><br />Upewnij się, że na urządzeniu działa system iOS w wersji 8.0 lub nowszej.<br /><br />Skontaktuj się z administratorami IT i poinformuj ich o pojawieniu się komunikatu **DeviceTypeNotSupported** podczas próby zarejestrowania urządzenia przenośnego oraz poproś o zapoznanie się z rozwiązaniem w tej tabeli.|Upewnij się, że na urządzeniu użytkownika działa system iOS w wersji 8.0 lub nowszej.|
|UserLicenseTypeInvalid|Nie można zarejestrować urządzenia przenośnego, ponieważ konto użytkownika nie należy jeszcze do wymaganej grupy użytkowników.<br /><br />Skontaktuj się z administratorami IT i poinformuj ich o pojawieniu się komunikatu **UserLicenseTypeInvalid** podczas próby zarejestrowania urządzenia przenośnego oraz poproś o zapoznanie się z rozwiązaniem w tej tabeli.|Aby użytkownicy mogli rejestrować urządzenia, muszą należeć do odpowiedniej grupy użytkowników. Ten komunikat oznacza, że użytkownik ma niewłaściwy typ licencji dla wyznaczonego źródła zarządzania urządzeniami przenośnymi. Ten błąd wystąpi, jeśli na przykład jako źródło zarządzania urządzeniami przenośnymi zostanie wyznaczona usługa Intune, a użytkownik będzie korzystać z licencji programu System Center 2012 R2 Configuration Manager.<br /><br />Więcej informacji zawierają następujące sekcje:<br /><br />Zobacz [Konfigurowanie zarządzania systemem iOS i komputerami Mac przez usługę Microsoft Intune](/Intune/Deploy-use/set-up-ios-and-mac-management-with-microsoft-intune), a także informacje o sposobie konfigurowania użytkowników w temacie [Synchronizacja usługi Active Directory i dodawanie użytkowników do usługi Intune](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-3) oraz [Organizowanie użytkowników i urządzeń](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5).|
|MdmAuthorityNotDefined|Administrator IT musi skonfigurować sposób zarządzania urządzeniami przenośnymi w firmie.<br /><br />Skontaktuj się z administratorami IT i poinformuj ich o pojawieniu się komunikatu **MdmAuthorityNotDefined** podczas próby zarejestrowania urządzenia przenośnego oraz poproś o zapoznanie się z rozwiązaniem w tej tabeli.|Nie wyznaczono źródła zarządzania urządzeniami przenośnymi w usłudze Intune.<br /><br />Zapoznaj się z pozycją 1 w sekcji „Krok 6. Rejestrowanie urządzeń przenośnych i instalowanie aplikacji” w temacie [Rozpoczynanie pracy z 30-dniową wersją próbną usługi Microsoft Intune](/Intune/Understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune).|



<!--HONumber=Dec16_HO2-->


