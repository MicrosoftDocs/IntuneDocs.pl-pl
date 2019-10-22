---
title: Szyfrowanie urządzenia z systemem Android w usłudze Intune | Microsoft Docs
description: Kroki umożliwiające włączenie szyfrowania urządzeń z systemem Android w razie potrzeby usługi Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/19/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: d4430e92-04cc-48e9-a77a-81b95a90b6b3
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: d2965d6a017d92bd4535a29a2257c0cac5e6deaf
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72506365"
---
# <a name="encrypting-your-android-device"></a>Szyfrowanie urządzenia z systemem Android

Szyfrowanie urządzenia chroni pliki i foldery przed nieautoryzowanym dostępem w przypadku zgubienia lub kradzieży urządzenia. Po włączeniu szyfrowania urządzenia tylko osoby z poprawnym hasłem lub numerem PIN będą mogły zalogować się na urządzeniu. 

Aby można było uzyskać dostęp do szkoły lub zasobów służbowych, organizacja może wymagać zaszyfrowania urządzenia z systemem Android. Niektóre nowsze urządzenia z systemem Android są domyślnie szyfrowane.  

## <a name="turn-on-encryption"></a>Włącz szyfrowanie

Jeśli Portal firmy lub aplikacja Microsoft Intune poprosi Cię o zaszyfrowanie urządzenia, wykonaj następujące czynności. 

> [!Note]
> Nie można zaszyfrować niektórych urządzeń z systemem Android z kartami Huawei, vivo i OPPO. Dowiedz się więcej [tutaj](your-device-appears-encrypted-but-cp-says-otherwise-android.md).  

1. Ustaw blokadę ekranu urządzenia.  
    a. Przejdź kolejno do pozycji **Ustawienia** > **Ekran blokady i zabezpieczenia** > **Typ blokady ekranu**.  
    b. Wybierz opcję **kod PIN**, **hasło**lub **wzorzec**.  
    c. Postępuj zgodnie z instrukcjami na ekranie, aby skonfigurować blokadę ekranu.  

2. Wróć do **ekranu blokady i zabezpieczeń** , a następnie wybierz pozycję **bezpieczne uruchamianie**.
3. Wybierz pozycję **Wymagaj numeru PIN po włączeniu urządzenia**  > **OK**.
4. Wprowadź numer PIN, aby potwierdzić i zaszyfrować urządzenie.
5. Otwórz aplikację Portal firmy lub Microsoft Intune.
    * Użytkownicy aplikacji Portal firmy: wybierz urządzenie i wybierz pozycję **Sprawdź ustawienia urządzenia**. 
    * Microsoft Intune użytkownicy: należy poczekać, aż strona zostanie zaktualizowana, ale gdy tak się stanie, stan szyfrowania powinien zmienić się na zgodny.  

W przypadku urządzeń z systemem Android 4,4 i wcześniejszymi może nie być dostępna opcja **bezpiecznego uruchamiania** . W takim przypadku wykonaj następujące kroki, aby zaszyfrować urządzenie.

1. Przejdź do pozycji **ustawienia**  > **zabezpieczenia**  > **szyfrowanie urządzenia**. Etykiety na ekranie różnią się w zależności od urządzeń z systemem Android. Jeśli nie widzisz opcji **Szyfruj urządzenie** , Zaewidencjonuj:
    * **Szyfrowanie magazynu** ** >  Storage**
    *  > **ustawień zabezpieczeń** **magazynu** >  **i zabezpieczeń** 

2. Wykonaj instrukcje wyświetlane na ekranie. Podczas szyfrowania urządzenie może być kilka razy ponownie uruchamiane.
3. Otwórz aplikację Portal firmy lub Microsoft Intune.
    * Użytkownicy aplikacji Portal firmy: wybierz urządzenie i wybierz pozycję **Sprawdź ustawienia urządzenia**.  
    * Microsoft Intune użytkownicy: należy poczekać, aż strona zostanie zaktualizowana, ale gdy tak się stanie, stan szyfrowania powinien zmienić się na zgodny.

## <a name="troubleshoot"></a>Rozwiązywanie problemów  
**Problem**: urządzenie zostało już zaszyfrowane i

- Przycisk szyfrowania jest wyłączony.
- Został wyświetlony komunikat informujący o tym, że szyfrowanie jest w dalszym ciągu wymagane.
- Wystąpią błędy podczas próby użycia aplikacji Portal firmy lub Microsoft Intune.

**Co należy zrobić**

- Upewnij się, że urządzenie jest naładowane i podłączone do zasilania.  
- Upewnij się, że ustawiono numer PIN lub hasło na urządzeniu.  

Nadal potrzebujesz pomocy? Skontaktuj się z działem pomocy technicznej Twojej firmy (sprawdź [witrynę internetową Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980), aby uzyskać informacje kontaktowe) lub napisz do <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with encryption on my Android device&body=Describe the issue you're experiencing here.">zespołu ds. systemu Android w firmie Microsoft</a>.  
