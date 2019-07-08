---
title: Szyfrowanie urządzenia z systemem Android w usłudze Intune | Dokumentacja firmy Microsoft
description: Kroki, aby włączyć szyfrowanie urządzenia z systemem Android, gdy jest to wymagane przez usługę Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/19/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d4430e92-04cc-48e9-a77a-81b95a90b6b3
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: cfc17c60412a1cfe90693216caa69ada3d2d2c9a
ms.sourcegitcommit: bccfbf1e3bdc31382189fc4489d337d1a554e6a1
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 07/03/2019
ms.locfileid: "67545261"
---
# <a name="encrypting-your-android-device"></a>Szyfrowanie urządzenia z systemem Android

Szyfrowanie urządzenia chroni pliki i foldery przed nieautoryzowanym dostępem, w przypadku utraty lub kradzieży urządzenia. Po włączeniu szyfrowania urządzenia tylko osoby, które mają poprawne hasło lub kod pin będzie można logować się do urządzenia. 

Przed uzyskujesz dostęp do zasobów służbowych lub firmowe, Twoja organizacja może wymagać zaszyfrowania urządzenia z systemem Android. Niektórych nowszych urządzeniach z systemem Android są domyślne szyfrowanie przekazywanego materiału, out-of--box.  

## <a name="turn-on-encryption"></a>Włącz szyfrowanie

Jeśli Portal firmy lub aplikacji Microsoft Intune monituje o zaszyfrować urządzenie, wykonaj następujące czynności. 

> [!Note]
> Niektóre urządzenia z systemem Android z Huawei, Vivo i OPPO, nie mogą być szyfrowane. Dowiedz się więcej [tutaj](your-device-appears-encrypted-but-cp-says-otherwise-android.md).  

1. Ustawianie blokady ekranu urządzenia.  
    a. Przejdź kolejno do pozycji **Ustawienia** > **Ekran blokady i zabezpieczenia** > **Typ blokady ekranu**.  
    b. Wybierz opcję **numeru PIN**, **hasło**, lub **wzorzec**.  
    c. Postępuj zgodnie z instrukcjami wyświetlanymi na ekranie, aby skonfigurować blokadę ekranu.  

2. Wróć do **blokada ekranu i zabezpieczenia** i wybierz **bezpieczne uruchamianie**.
3. Wybierz **Wymagaj numeru PIN, gdy urządzenie włączy** > **OK**.
4. Wprowadź numer PIN, aby potwierdzić i zaszyfrować urządzenie z systemem.
5. Otwórz aplikację Portal firmy lub Microsoft Intune.
    * Użytkownicy aplikacji Portal firmy: wybierz urządzenie i wybierz pozycję **Sprawdź ustawienia urządzenia**. 
    * Microsoft Intune, użytkownicy: musisz czekać do momentu aktualizacji stron, ale gdy tak się stanie, Twój status szyfrowania należy zmienić na zgodne.  

Urządzenia z systemem Android 4.4 lub wcześniej może nie mieć **bezpiecznego uruchamiania** opcji. W takiej sytuacji wykonaj poniższe kroki, aby zaszyfrować urządzenie.

1. Przejdź do **ustawienia** > **zabezpieczeń** > **szyfrowania urządzenia**. Na ekranie etykietami różnią się między urządzeniami z systemem Android. Jeśli nie widzisz **Zaszyfruj urządzenie** opcji, sprawdź plik w folderze:
    * **Magazyn** > **szyfrowanie magazynu**
    * **Magazyn** > **blokada ekranu i zabezpieczenia** > **inne ustawienia zabezpieczeń** 

2. Wykonaj instrukcje wyświetlane na ekranie. Podczas szyfrowania urządzenie może być kilka razy ponownie uruchamiane.
3. Otwórz aplikację Portal firmy lub Microsoft Intune.
    * Użytkownicy aplikacji Portal firmy: wybierz urządzenie i wybierz pozycję **Sprawdź ustawienia urządzenia**.  
    * Microsoft Intune, użytkownicy: musisz czekać do momentu aktualizacji stron, ale gdy tak się stanie, Twój status szyfrowania należy zmienić na zgodne.

## <a name="troubleshoot"></a>Rozwiązywanie problemów  
**Problem**: urządzenie zostało już zaszyfrowane i

- Przycisk szyfrowania jest wyłączony.
- Został wyświetlony komunikat informujący o tym, że szyfrowanie jest w dalszym ciągu wymagane.
- Wystąpiły błędy podczas próby użycia aplikacji Portal firmy lub Microsoft Intune.

**Co należy zrobić**

- Upewnij się, że urządzenie jest naładowane i podłączone do zasilania.  
- Upewnij się, że ustawiono numer PIN lub hasło na urządzeniu.  

Nadal potrzebujesz pomocy? Skontaktuj się z działem pomocy technicznej Twojej firmy (sprawdź [witrynę internetową Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980), aby uzyskać informacje kontaktowe) lub napisz do <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with encryption on my Android device&body=Describe the issue you're experiencing here.">zespołu ds. systemu Android w firmie Microsoft</a>.  
