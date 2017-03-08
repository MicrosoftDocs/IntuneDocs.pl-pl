---
title: "Pobieranie certyfikatu programu DEP firmy Apple dla usługi Intune"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: instrukcje dotyczące skonfigurowania i przekazania certyfikatu wypychania MDM stanowiącego wymaganie wstępne dla zarządzania urządzeniami firmy Apple w usłudze Intune. "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/03/17
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e5c79c5-2883-4841-9be6-74cba16ee447
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 8edc42bb86e3856ac6568cc3c1acc5d757978e79
ms.lasthandoff: 02/18/2017

---

# <a name="get-an-apple-dep-certificate"></a>Pobieranie certyfikatu programu DEP firmy Apple

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Aby zarejestrować firmowe urządzenia z systemem iOS w programie Device Enrollment Program (DEP) firmy Apple, należy uzyskać token programu DEP od firmy Apple. Token umożliwia usłudze Intune synchronizację informacji dotyczących urządzeń uczestniczących w programie DEP należących do firmy. Umożliwia on również usłudze Intune przekazywanie profilów rejestracji do firmy Apple i przypisywanie urządzeń do tych profilów.

W celu zarządzania firmowymi urządzeniami z systemem iOS przy użyciu programu DEP organizacja musi dołączyć do programu DEP firmy Apple i zakupić urządzenia w ramach tego programu. Szczegóły tego procesu są dostępne pod adresem https://deploy.apple.com. Zalety programu obejmują funkcje bezobsługowego konfigurowania urządzeń bez konieczności podłączania poszczególnych urządzeń do komputera przy użyciu kabla USB.

> [!NOTE]
> Ta uwaga dotyczy tylko klientów usługi Intune, których poddano migracji z konsoli administracyjnej usługi Intune do witryny Azure Portal. Jeśli token DEP firmy Apple został usunięty z konsoli administracyjnej usługi Intune w czasie migracji, może się okazać, że token ten został przywrócony do konta usługi Intune. W takim przypadku wystarczy usunąć token DEP z witryny Azure Portal.

## <a name="steps-to-get-the-apple-dep-certificate"></a>Procedura pobierania certyfikatu programu DEP firmy Apple
W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**. W bloku Intune wybierz kolejno pozycje **Zarejestruj urządzenia** > **Token DEP firmy Apple**, a następnie wykonaj w witrynie Azure Portal kroki wymienione poniżej.

**Krok 1. Pobierz certyfikat klucza publicznego usługi Intune wymagany do utworzenia tokenu DEP firmy Apple.**<br>
Wybierz pozycję **Pobierz klucz publiczny**, aby pobrać i zapisać lokalnie plik klucza szyfrowania (.pem). Plik PEM jest używany na potrzeby żądania certyfikatu relacji zaufania z portalu programu Device Enrollment Program firmy Apple.

**Krok 2. Pobierz token DEP firmy Apple z odpowiedniej witryny internetowej firmy Apple.**<br>
Wybierz pozycję [Utwórz token DEP za pomocą programów wdrażania firmy Apple](https://deploy.apple.com) (https://deploy.apple.com) i zaloguj się przy użyciu identyfikatora Apple swojej firmy. Tego identyfikatora firmy Apple należy użyć do odnowienia tokenu DEP.

   a.  W [portalu Device Enrollment Program](https://deploy.apple.com) wybierz pozycje **Device Enrollment Program** &gt; **Manage Servers** (Zarządzanie serwerami), a następnie wybierz pozycję **Add MDM Server** (Dodaj serwer MDM).

   b.  Wprowadź nazwę serwera w polu **MDM Server Name** (Nazwa serwera MDM), a następnie wybierz przycisk **Next**(Dalej). Nazwa serwera służy użytkownikowi do identyfikowania serwera MDM. Nie jest to nazwa ani adres URL serwera usługi Microsoft Intune.

   c.  Zostanie otwarte okno dialogowe **Add &lt;nazwa_serwera&gt;** (Dodawanie serwera <nazwa_serwera>). Kliknij pozycję **Choose File…** (Wybierz plik...) w celu przekazania pliku PEM, a następnie kliknij przycisk **Next** (Dalej).

   d.  W oknie dialogowym **Add&lt; <nazwa_serwera>&gt;** (Dodawanie serwera <nazwa_serwera>) zostanie wyświetlony link **Your Server Token** (Token serwera). Pobierz plik tokenu serwera (p7m) na komputer, a następnie wybierz pozycję **Done**(Gotowe).

    This certificate (.p7m) file is used to establish a trust relationship between Intune and Apple’s Device Enrollment Program servers.

**Krok 3. Wprowadź identyfikator firmy Apple użyty do utworzenia tokenu DEP firmy Apple. Tego identyfikatora można użyć do odnowienia tokenu DEP firmy Apple.**

**Krok 4. Przejdź do lokalizacji tokenu DEP firmy Apple do przekazania. Usługa Intune przeprowadzi automatyczną synchronizację z kontem DEP.**<br>
Przejdź do pliku certyfikatu (.pem) i wybierz pozycję **Otwórz**, a następnie wybierz pozycję **Przekaż**. Dzięki certyfikatowi wypychania usługa Intune może rejestrować urządzenia z systemem iOS i zarządzać nimi, wypychając zasady do zarejestrowanych urządzeń przenośnych.

