---
title: Rozwiązywanie problemów z zasadami w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Typowe trudności i problemy występujące w przypadku korzystania z zasad w usłudze Microsoft Intune oraz ich rozwiązania
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 99fb6db6-21c5-46cd-980d-50f063ab8ab8
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: bb55ddc283ce4633b5057d5b96ae2ed6973dcf8a
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52181772"
---
# <a name="troubleshoot-policies-in-intune"></a>Rozwiązywanie problemów z zasadami w usłudze Intune

Jeśli masz problemy z wdrażaniem zasad usługi Intune i zarządzaniem nimi, zacznij tutaj. W tym artykule opisano niektóre typowe problemy, które mogą wystąpić, oraz ich ewentualne rozwiązania.

## <a name="general-issues"></a>Ogólne problemy

### <a name="was-a-deployed-policy-applied-to-the-device"></a>Czy wdrożone zasady zostały zastosowane do urządzenia?
**Problem:** nie wiesz, czy poprawnie zastosowano zasady.

W obszarze usługi Intune > **Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenie > **Konfiguracja urządzenia** znajduje się lista zasad dla poszczególnych urządzeń. Wszystkie zasady mają **stan**. Stan jest stosowany, gdy wszystkie zasady dotyczące urządzenia, a także ograniczenia i wymagania sprzętowe oraz system operacyjny, są rozważane razem. Dostępne są następujące stany:

- **Zgodne**: urządzenie odebrało zasady i zgłasza usłudze, że działa zgodnie z ich ustawieniem.

- **Nie dotyczy**: ustawienie zasad nie ma zastosowania. Na przykład ustawienia poczty e-mail dla urządzeń z systemem iOS nie będą miały zastosowania do urządzenia z systemem Android.

- **Oczekujące**: zasady zostały wysłane do urządzenia, ale nie zgłosiło ono stanu usłudze. Na przykład szyfrowanie w systemie Android wymaga od użytkownika końcowego włączenia szyfrowania, dlatego może być wyświetlany stan Oczekujące.

> [!NOTE]
> Jeśli dwie zasady z różnymi poziomami ograniczeń dotyczą tego samego urządzenia lub użytkownika, zostaną zastosowane zasady bardziej restrykcyjne.

## <a name="issues-with-enrolled-devices"></a>Problemy z zarejestrowanymi urządzeniami

### <a name="alert-saving-of-access-rules-to-exchange-has-failed"></a>Alert: zapisywanie reguł dostępu do programu Exchange nie powiodło się
**Problem**: w konsoli administracyjnej odebrano alert **Zapisywanie reguł dostępu w programie Exchange nie powiodło się**  .

Jeśli zasady utworzono w obszarze roboczym Zasady lokalnej instalacji programu Exchange w konsoli administracyjnej, ale jest używana usługa Office 365, skonfigurowane ustawienia zasad nie są wymuszane przez usługę Intune. Zanotuj źródło zasad wymienione w alercie.  W obszarze roboczym Zasady lokalnej instalacji programu Exchange usuń starsze reguły. Starsze reguły to globalne reguły programu Exchange w usłudze Intune dla lokalnego programu Exchange i nie są odpowiednie w przypadku usługi O365. Następnie utwórz nowe zasady dla usługi Office 365.

### <a name="cannot-change-security-policy-for-various-enrolled-devices"></a>Nie można zmienić zasad zabezpieczeń dla różnych zarejestrowanych urządzeń
Urządzenia z systemem Windows Phone nie zezwalają na obniżenie bezpieczeństwa zasad zabezpieczeń ustawionych wcześniej za pośrednictwem usługi MDM lub EAS. Na przykład po ustawieniu dla zasady **Minimalna liczba znaków hasła** wartości 8 nastąpiła próba jej zmniejszenia do 4. Bardziej restrykcyjne zasady zostały już zastosowane do urządzenia.

W zależności od platformy urządzenia jeśli chcesz zmienić zasady na wartość mniej bezpieczną, może być konieczne zresetowanie zasad zabezpieczeń.

Na przykład w systemie Windows na pulpicie przesuń palcem z prawej strony, aby otworzyć pasek **Panele funkcji**. Wybierz kolejno pozycje **Ustawienia** > **Panel sterowania**, a następnie wybierz pozycję **Konta użytkowników**. Po lewej stronie wybierz link **Resetuj zasady zabezpieczeń** i wybierz pozycję **Resetuj zasady**.

W przypadku innych urządzeń MDM, takich jak urządzenia z systemami Android, Windows Phone 8.1 lub nowszym oraz iOS, zastosowanie mniej restrykcyjnych zasad może wymagać wycofania i ponownego zarejestrowania urządzenia w usłudze.

## <a name="issues-with-pcs-that-run-the-intune-software-client"></a>Problemy związane z komputerami z oprogramowaniem klienckim usługi Intune

Dotyczy portalu klasycznego.

### <a name="microsoft-intune-policy-related-errors-in-policyplatformlog"></a>Błędy związane z zasadami usługi Microsoft Intune w pliku policyplatform.log
W przypadku komputerów z systemem Windows zarządzanych przy użyciu oprogramowania klienckiego usługi Intune błędy zasad w pliku policyplatform.log mogą wynikać z innych niż domyślne ustawień w Kontroli konta użytkownika (UAC) systemu Windows na urządzeniu. Niektóre inne niż domyślne ustawienia funkcji Kontroli konta użytkownika mogą wpływać na instalacje klienta usługi Microsoft Intune i wykonywanie zasad.

#### <a name="resolve-uac-issues"></a>Rozwiązywanie problemów z Kontrolą konta użytkownika

1. Wycofaj komputer. Zobacz [Usuwanie urządzeń](devices-wipe.md).

2. Zaczekaj 20 minut na usunięcie oprogramowania klienckiego.

    > [!NOTE]
    > Nie należy próbować usuwać klienta z poziomu opcji Programy i funkcje.

3. W menu start wpisz wartość **Kontrola konta użytkownika**, aby otworzyć ustawienia Kontroli konta użytkownika.

4. Przesuń suwak powiadomień na ustawienie domyślne.

### <a name="error-cannot-obtain-the-value-from-the-computer-0x80041013"></a>BŁĄD: Nie można uzyskać wartości z komputera, 0x80041013
Występuje, jeśli godzina w systemie lokalnym różni się o pięć lub więcej minut. Jeśli godzina na komputerze lokalnym nie jest zsynchronizowana, zabezpieczone transakcje zakończą się niepowodzeniem ze względu na nieprawidłowe sygnatury czasowe.

Aby rozwiązać ten problem, ustaw czas w systemie lokalnym jak najbardziej zbliżony do czasu z Internetu lub czasu ustawionego na kontrolerach domeny w sieci.

### <a name="next-steps"></a>Następne kroki
Jeśli te informacje dotyczące rozwiązywania problemów nie pomogły, skontaktuj się z pomocą techniczną firmy Microsoft zgodnie z opisem w temacie [Get support for Microsoft Intune](get-support.md) (Uzyskiwanie pomocy technicznej dotyczącej usługi Microsoft Intune).
