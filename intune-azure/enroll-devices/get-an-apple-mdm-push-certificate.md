---
title: "Uzyskiwanie certyfikatu wypychania Apple MDM | Wersja zapoznawcza usługi Intune Azure | Dokumentacja firmy Microsoft"
description: "Wersja zapoznawcza usługi Intune Azure: opis czynności niezbędnych w celu uzyskania certyfikatu wypychania Apple MDM przeznaczonego do zarządzania urządzeniami z systemem iOS za pomocą usługi Intune."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: c0884ded1c8c55bb1b7968e483864b42f5bd6bde


---

# <a name="get-an-apple-mdm-push-certificate"></a>Uzyskiwanie certyfikatu wypychania MDM firmy Apple 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Usługa Intune umożliwia zarządzanie urządzeniami przenośnymi typu iPad, iPhone oraz urządzeniami z systemem Mac OS X i zapewnia użytkownikom dostęp do poczty e-mail oraz aplikacji firmy. Aby zarządzać urządzeniami z systemem iOS i komputerami Mac, wymagany jest certyfikat usługi Apple Push Notification service (APNs). Po dodaniu certyfikatu do usługi Intune użytkownicy mogą zainstalować aplikację Portal firmy, aby zarejestrować swoje urządzenia, lub administrator może skonfigurować zarządzanie urządzeniami z systemem iOS należącymi do firmy.

**W celu uzyskania certyfikatu wypychania MDM firmy Apple:**<br>

W witrynie Azure Portal wybierz pozycję **Więcej usług**, w polu tekstowym wprowadź nazwę **Intune**, a następnie wybierz kolejno pozycje **Inne** > **Intune**. W bloku Intune wybierz kolejno pozycje **Zarejestruj urządzenia** > **Certyfikat wypychania Apple MDM**, a następnie wykonaj w witrynie Azure Portal kroki wymienione poniżej.

**Krok 1. Pobierz żądanie podpisania certyfikatu usługi Intune wymagane do utworzenia certyfikatu wypychania MDM firmy Apple.**<br>
Wybierz pozycję **Pobierz żądanie CSR**, aby pobrać plik .csr i zapisać go lokalnie. Plik CSR jest używany na potrzeby żądania certyfikatu relacji zaufania w portalu Apple Push Certficates.

**Krok 2. Tworzenie certyfikatu wypychania MDM firmy Apple**<br>
Wybierz pozycję **Utwórz swój certyfikat push MDM**, aby przejść do portalu Apple Push Certificates. Zaloguj się przy użyciu firmowego identyfikatora Apple ID, aby utworzyć certyfikat wypychania z użyciem pliku .csr. Po kliknięciu przycisku **Upload** (Przekaż) w witrynie Apple Push Certificates Portal otrzymasz plik z rozszerzeniem .json. Użyj tego pliku w odniesieniu do certyfikatu wypychania. Ukończ pobieranie, wróć do portalu wypychania certyfikatu firmy Apple, przejdź do obszaru Certificates for Third-Party Servers (Certyfikaty dla serwerów innych firm) i wybierz polecenie **Download** (Pobierz). Pobierz certyfikat wypychania (plik .pem) i zapisz plik lokalnie.
Uwaga

**Krok 3. Wprowadź identyfikator firmy Apple użyty do utworzenia certyfikatu wypychania MDM firmy Apple.**

**Krok 4. Przejdź do pliku certyfikatu wypychania MDM firmy Apple, aby go przekazać.**<br>
Przejdź do pliku certyfikatu (.pem) i wybierz pozycję **Otwórz**, a następnie wybierz pozycję **Przekaż**. Dzięki certyfikatowi wypychania usługa Intune może rejestrować urządzenia z systemem iOS i zarządzać nimi, wypychając zasady do zarejestrowanych urządzeń przenośnych.



<!--HONumber=Feb17_HO1-->


