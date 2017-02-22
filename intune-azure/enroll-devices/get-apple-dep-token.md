---
title: "Pobieranie certyfikatu DEP firmy Apple dla usługi Intune | Wersja zapoznawcza usługi Intune Azure | Dokumentacja firmy Microsoft"
description: "Wersja zapoznawcza usługi Intune Azure: instrukcje dotyczące skonfigurowania i przekazania certyfikatu wypychania MDM stanowiącego wymaganie wstępne dla zarządzania urządzeniami firmy Apple w usłudze Intune. "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/03/17
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e5c79c5-2883-4841-9be6-74cba16ee447
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 65a6b2e22359bdcb9b0c15a84c6b3586dafe4d6c
ms.openlocfilehash: c740dedebdc4afd909a8c38447f698c2724de5a1

---

# <a name="get-an-apple-dep-certificate"></a>Pobieranie certyfikatu programu DEP firmy Apple 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Aby zarejestrować firmowe urządzenia z systemem iOS w programie DEP, należy uzyskać token programu DEP od firmy Apple. Token umożliwia usłudze Intune synchronizację informacji dotyczących urządzeń uczestniczących w programie DEP należących do firmy. Umożliwia on również usłudze Intune przekazywanie profilów rejestracji do firmy Apple i przypisywanie urządzeń do tych profilów.

W celu zarządzania firmowymi urządzeniami z systemem iOS przy użyciu programu Device Enrollment Program (DEP) firmy Apple organizacja musi dołączyć do programu DEP firmy Apple i zakupić urządzenia w ramach tego programu. Szczegóły tego procesu są dostępne pod adresem https://deploy.apple.com. Zalety programu obejmują funkcje bezobsługowego konfigurowania urządzeń bez konieczności podłączania poszczególnych urządzeń do komputera przy użyciu kabla USB.

> [!NOTE]
> Przeczytaj tę uwagę tylko, jeśli jesteś klientem, którego poddano migracji z konsoli administracyjnej usługi Intune do witryny Azure Portal. Jeśli token DEP firmy Apple został usunięty z konsoli administracyjnej usługi Intune w czasie migracji, może się okazać, że token ten został przywrócony do konta usługi Intune. W takim przypadku wystarczy usunąć token DEP z witryny Azure Portal. 

**Pobieranie certyfikatu programu DEP firmy Apple**</br>
W witrynie Azure Portal wybierz pozycję **Więcej usług**, w polu tekstowym wprowadź nazwę **Intune**, a następnie wybierz kolejno pozycje **Inne** > **Intune**. W bloku Intune wybierz kolejno pozycje **Zarejestruj urządzenia** > **Token DEP firmy Apple**, a następnie wykonaj w witrynie Azure Portal kroki wymienione poniżej.

**Krok 1. Pobierz certyfikat klucza publicznego usługi Intune wymagany do utworzenia tokenu DEP firmy Apple.**<br>
Wybierz pozycję **Pobierz klucz publiczny**, aby pobrać i zapisać lokalnie plik klucza szyfrowania (.pem). Plik PEM jest używany na potrzeby żądania certyfikatu relacji zaufania z portalu programu Device Enrollment Program firmy Apple.

**Krok 2. Pobierz token DEP firmy Apple z odpowiedniej witryny internetowej firmy Apple.**<br>
Wybierz pozycję [Utwórz token DEP za pomocą programów wdrażania firmy Apple](https://deploy.apple.com) (https://deploy.apple.com) i zaloguj się przy użyciu identyfikatora Apple swojej firmy. Tego identyfikatora firmy Apple należy użyć do odnowienia tokenu DEP.

   1.  W [portalu Device Enrollment Program](https://deploy.apple.com) wybierz pozycje **Device Enrollment Program** &gt; **Manage Servers** (Zarządzanie serwerami), a następnie wybierz pozycję **Add MDM Server** (Dodaj serwer MDM).

   2.  Wprowadź nazwę serwera w polu **MDM Server Name** (Nazwa serwera MDM), a następnie wybierz przycisk **Next**(Dalej). Nazwa serwera służy użytkownikowi do identyfikowania serwera MDM. Nie jest to nazwa ani adres URL serwera usługi Microsoft Intune.

   3.  Zostanie otwarte okno dialogowe **Add &lt;nazwa_serwera&gt;** (Dodawanie serwera <nazwa_serwera>). Kliknij pozycję **Choose File…** (Wybierz plik...) w celu przekazania pliku PEM, a następnie kliknij przycisk **Next** (Dalej).

   4.  W oknie dialogowym **Add&lt; <nazwa_serwera>&gt;** (Dodawanie serwera <nazwa_serwera>) zostanie wyświetlony link **Your Server Token** (Token serwera). Pobierz plik tokenu serwera (p7m) na komputer, a następnie wybierz pozycję **Done**(Gotowe).

    Ten plik certyfikatu (p7m) służy do ustanawiania relacji zaufania między serwerami usługi Intune i programu Device Enrollment Program firmy Apple.

**Krok 3. Wprowadź identyfikator firmy Apple użyty do utworzenia tokenu DEP firmy Apple. Tego identyfikatora można użyć do odnowienia tokenu DEP firmy Apple.**

**Krok 4. Przejdź do lokalizacji tokenu DEP firmy Apple do przekazania. Usługa Intune przeprowadzi automatyczną synchronizację z kontem DEP.**<br>
Przejdź do pliku certyfikatu (.pem) i wybierz pozycję **Otwórz**, a następnie wybierz pozycję **Przekaż**. Dzięki certyfikatowi wypychania usługa Intune może rejestrować urządzenia z systemem iOS i zarządzać nimi, wypychając zasady do zarejestrowanych urządzeń przenośnych.



<!--HONumber=Feb17_HO1-->


