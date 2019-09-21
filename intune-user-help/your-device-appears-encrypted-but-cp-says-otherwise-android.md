---
title: Urządzenie z systemem Android wydaje się być szyfrowane | Microsoft Docs
description: Rozwiązywanie stanu szyfrowania w aplikacji Portal firmy i Microsoft Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/14/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ba593c08-1a78-4013-8525-b45a948772ec
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0ec52069c4c53c464cfe5a1e17718ba6725fd0b5
ms.sourcegitcommit: 1494ff4b33c13a87f20e0f3315da79a3567db96e
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 09/20/2019
ms.locfileid: "71167429"
---
# <a name="device-encrypted-but-apps-say-otherwise"></a>Urządzenie zaszyfrowane, ale aplikacje mówią inaczej

Jeśli Portal firmy lub aplikacja Microsoft Intunea mówi, że urządzenie nie jest zaszyfrowane, ale masz pewność, że jest to możliwe, wypróbuj kroki opisane w tym artykule.  

## <a name="add-a-startup-pin"></a>Dodaj numer PIN uruchomienia

Aby zagwarantować bezpieczeństwo urządzenia, niektóre urządzenia z systemem Android wymagają utworzenia numeru PIN uruchomienia. Lokalizacja tego ustawienia będzie znajdować się w aplikacji **ustawień** urządzenia. Nazwa i lokalizacja ustawienia mogą się różnić. Na przykład w przypadku urządzeń z systemem Samsung Galaxy S7 ustawienie to jest nazywane **bezpiecznym uruchamianiem**. Aby włączyć tę funkcję i utworzyć kod dostępu, przejdź do pozycji **Ustawienia** > **ekran blokady i zabezpieczenia** > **bezpieczne uruchamianie**.  

## <a name="encrypt-the-entire-device"></a>Zaszyfruj całe urządzenie

Ta sekcja dotyczy tylko aplikacji Portal firmy. Niektóre urządzenia umożliwiają wybór między szyfrowaniem całego urządzenia i szyfrowaniem tylko używanego miejsca. Wybierz opcję szyfrowania całego urządzenia. Jeśli wybrano szyfrowanie tylko zajętego miejsca:

1. [Usuń to urządzenie z Portalu firmy](unenroll-your-device-from-intune-android.md).
2. Odszyfruj używane miejsce.  
3. Zaszyfruj całe urządzenie.  
4. Zarejestruj ponownie urządzenie.  

## <a name="downgrade-your-version-of-android"></a>Zmień wersję systemu Android na starszą

Ta sekcja dotyczy tylko aplikacji Portal firmy. Jeśli Twoje urządzenie umożliwia przeprowadzenie zmiany na wersję Android 6.0 nowszą, należy to zrobić. Zmiana wersji urządzenia na starszą może wiązać się z ryzykiem utraty danych. W przeciwnym razie zalecane jest skontaktowanie się z działem pomocy technicznej Twojej firmy, aby rozwiązać ten problem. Uzyskaj informacje kontaktowe działu pomocy technicznej Twojej firmy w [witrynie internetowej Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).  

## <a name="specific-manufacturer-issues"></a>Problemy z urządzeniami niektórych producentów

Niektóre urządzenia z systemem Android w wersji 7.0 lub nowszej szyfrują dane metodami, które są niezgodne z pewnymi standardami platformy systemu Android. Te metody szyfrowania powodują, że informacje o urządzeniu są zagrożone. W związku z tym urządzenia te nie są obsługiwane.

Aby zapoznać się z niekompletną listą obsługiwanych urządzeń z systemem Android, zobacz artykuł [obsługiwane systemy operacyjne i przeglądarki w usłudze Intune](https://docs.microsoft.com/intune/supported-devices-browsers.md#supported-samsung-knox-standard-devices). Jeśli urządzenie nie jest wyświetlane na liście, zapoznaj się z producentem urządzenia lub skontaktuj się z pomocą techniczną.

> [!Note]
> Firma Microsoft współpracuje z producentami w celu rozwiązania problemów znalezionych podczas testowania lub zgłoszonych nam przez użytkowników. Gdy pojawiają się nowe informacje, aktualizujemy ten artykuł.

## <a name="update-devices"></a>Aktualizowanie urządzeń

Jeśli urządzenie nie zostało zaktualizowane do najnowszej wersji systemu Android, przejdź do aplikacji **Ustawienia** urządzenia i wybierz pozycję **Aktualizuj**.  

## <a name="next-steps"></a>Następne kroki

Nadal potrzebujesz pomocy? Skontaktuj się z działem pomocy technicznej Twojej firmy (sprawdź [witrynę internetową Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980), aby uzyskać informacje kontaktowe) lub napisz do <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with enrolling my Android device&body=Describe the issue you're experiencing here.">zespołu ds. systemu Android w firmie Microsoft</a>.  
