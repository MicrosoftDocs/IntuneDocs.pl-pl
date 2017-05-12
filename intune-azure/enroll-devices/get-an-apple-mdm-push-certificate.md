---
title: Uzyskiwanie certyfikatu wypychania MDM firmy Apple
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: opis czynności niezbędnych w celu uzyskania certyfikatu wypychania Apple MDM przeznaczonego do zarządzania urządzeniami z systemem iOS za pomocą usługi Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 3758df744311392528be01c826527c2a9d879975
ms.openlocfilehash: 91c6b063fbc17cf92aab50c4911e4bb33b76deb9
ms.contentlocale: pl-pl
ms.lasthandoff: 05/10/2017


---

# <a name="get-an-apple-mdm-push-certificate"></a>Uzyskiwanie certyfikatu wypychania MDM firmy Apple

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Usługa Intune umożliwia zarządzanie urządzeniami przenośnymi typu iPad, iPhone oraz komputerami Mac i zapewnia użytkownikom dostęp do poczty e-mail oraz aplikacji firmy. Aby zarządzać urządzeniami z systemem iOS i komputerami Mac, wymagany jest certyfikat usługi wypychania MDM. Po dodaniu certyfikatu do usługi Intune użytkownicy mogą zainstalować aplikację Portal firmy, aby zarejestrować swoje urządzenia. Możesz również skonfigurować zarządzanie urządzeniami iOS należącymi do firmy za pomocą programu rejestracji urządzeń firmy Apple lub zarejestrować urządzenia, na przykład przy użyciu programu Apple Configurator. Aby uzyskać więcej informacji o opcjach rejestracji, zobacz [Wybieranie sposobu rejestracji urządzenia z systemem iOS](choose-ios-enrollment-method.md).

## <a name="steps-to-get-your-certificate"></a>Procedura uzyskiwania certyfikatu
W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**. W bloku Intune wybierz kolejno pozycje **Zarejestruj urządzenia** > **Rejestracja urządzeń Apple** **Certyfikat wypychania Apple MDM**, a następnie wykonaj w witrynie Azure Portal kroki wymienione poniżej.

**Krok 1. Pobierz żądanie podpisania certyfikatu usługi Intune wymagane do utworzenia certyfikatu wypychania MDM firmy Apple.**<br>
Wybierz pozycję **Pobierz żądanie CSR**, aby pobrać plik .csr i zapisać go lokalnie. Plik CSR jest używany na potrzeby żądania certyfikatu relacji zaufania w portalu Apple Push Certficates.

**Krok 2. Tworzenie certyfikatu wypychania MDM firmy Apple**<br>
Wybierz pozycję **Utwórz swój certyfikat push MDM**, aby przejść do portalu Apple Push Certificates. Zaloguj się przy użyciu firmowego identyfikatora Apple ID, aby utworzyć certyfikat wypychania z użyciem pliku csr. Po kliknięciu przycisku **Upload** (Przekaż) w witrynie Apple Push Certificates Portal otrzymasz plik z rozszerzeniem .json. Użyj tego pliku w odniesieniu do certyfikatu wypychania. Ukończ pobieranie, wróć do portalu wypychania certyfikatu firmy Apple, przejdź do obszaru Certificates for Third-Party Servers (Certyfikaty dla serwerów innych firm) i wybierz polecenie **Download** (Pobierz). Pobierz certyfikat wypychania (plik pem) i zapisz plik lokalnie.
Uwaga

**Krok 3. Wprowadź identyfikator firmy Apple użyty do utworzenia certyfikatu wypychania MDM firmy Apple.**

**Krok 4. Przejdź do pliku certyfikatu wypychania MDM firmy Apple, aby go przekazać.**<br>
Przejdź do pliku certyfikatu (.pem) i wybierz pozycję **Otwórz**, a następnie wybierz pozycję **Przekaż**. Dzięki certyfikatowi wypychania usługa Intune może rejestrować urządzenia z systemem iOS i zarządzać nimi, wypychając zasady do zarejestrowanych urządzeń przenośnych.

