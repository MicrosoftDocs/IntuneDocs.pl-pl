---
title: Uzyskiwanie certyfikatu wypychania MDM firmy Apple
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: opis czynności niezbędnych w celu uzyskania certyfikatu wypychania Apple MDM przeznaczonego do zarządzania urządzeniami z systemem iOS za pomocą usługi Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 26991bd0c7632d04b75ecbec023d96c1045f337a
ms.lasthandoff: 02/18/2017


---

# <a name="get-an-apple-mdm-push-certificate"></a>Uzyskiwanie certyfikatu wypychania MDM firmy Apple 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Usługa Intune umożliwia zarządzanie urządzeniami przenośnymi typu iPad, iPhone oraz urządzeniami z systemem Mac OS X i zapewnia użytkownikom dostęp do poczty e-mail oraz aplikacji firmy. Aby zarządzać urządzeniami z systemem iOS i komputerami Mac, wymagany jest certyfikat usługi Apple Push Notification service (APNs). Po dodaniu certyfikatu do usługi Intune użytkownicy mogą zainstalować aplikację Portal firmy, aby zarejestrować swoje urządzenia, lub administrator może skonfigurować zarządzanie urządzeniami z systemem iOS należącymi do firmy.

## <a name="steps-to-get-your-certificate"></a>Procedura uzyskiwania certyfikatu
W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**. W bloku Intune wybierz kolejno pozycje **Zarejestruj urządzenia** > **Certyfikat wypychania Apple MDM**, a następnie wykonaj w witrynie Azure Portal kroki wymienione poniżej.

**Krok 1. Pobierz żądanie podpisania certyfikatu usługi Intune wymagane do utworzenia certyfikatu wypychania MDM firmy Apple.**<br>
Wybierz pozycję **Pobierz żądanie CSR**, aby pobrać plik .csr i zapisać go lokalnie. Plik CSR jest używany na potrzeby żądania certyfikatu relacji zaufania w portalu Apple Push Certficates.

**Krok 2. Tworzenie certyfikatu wypychania MDM firmy Apple**<br>
Wybierz pozycję **Utwórz swój certyfikat push MDM**, aby przejść do portalu Apple Push Certificates. Zaloguj się przy użyciu firmowego identyfikatora Apple ID, aby utworzyć certyfikat wypychania z użyciem pliku csr. Po kliknięciu przycisku **Upload** (Przekaż) w witrynie Apple Push Certificates Portal otrzymasz plik z rozszerzeniem .json. Użyj tego pliku w odniesieniu do certyfikatu wypychania. Ukończ pobieranie, wróć do portalu wypychania certyfikatu firmy Apple, przejdź do obszaru Certificates for Third-Party Servers (Certyfikaty dla serwerów innych firm) i wybierz polecenie **Download** (Pobierz). Pobierz certyfikat wypychania (plik pem) i zapisz plik lokalnie.
Uwaga

**Krok 3. Wprowadź identyfikator firmy Apple użyty do utworzenia certyfikatu wypychania MDM firmy Apple.**

**Krok 4. Przejdź do pliku certyfikatu wypychania MDM firmy Apple, aby go przekazać.**<br>
Przejdź do pliku certyfikatu (.pem) i wybierz pozycję **Otwórz**, a następnie wybierz pozycję **Przekaż**. Dzięki certyfikatowi wypychania usługa Intune może rejestrować urządzenia z systemem iOS i zarządzać nimi, wypychając zasady do zarejestrowanych urządzeń przenośnych.

