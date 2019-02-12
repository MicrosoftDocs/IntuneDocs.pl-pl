---
title: Urządzenie z systemem Android wydaje się być szyfrowane | Microsoft Docs
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 11/14/2017
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
ms.openlocfilehash: af53739574a5ae7087b59d72bacd866e132a19ac
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55843225"
---
# <a name="your-android-device-seems-to-be-encrypted-but-company-portal-says-otherwise"></a>Urządzenie z systemem Android wydaje się być szyfrowane, ale Portal firmy informuje, że jest inaczej

Zaszyfrowanie urządzenia polega na zakodowaniu znajdujących się na nim informacji przy użyciu klucza tajnego znanego tylko jego posiadaczowi. Chroni to urządzenie przed dostępem nieautoryzowanych osób. Wiele organizacji wymaga od użytkowników zaszyfrowania swoich urządzeń z systemem Android przed uzyskaniem dostępu do plików, wiadomości e-mail i danych firmy.

## <a name="common-issues"></a>Typowe problemy

Nowsze wersje systemu Android, szczególnie od wersji 7.0, wymagają kodu dostępu umożliwiającego uruchomienie, aby zagwarantować, że urządzenie jest w pełni szyfrowane. Różni producenci urządzeń oferują różne opisy i lokalizacje kodu dostępu umożliwiającego uruchomienie. W większości przypadków to ustawienie nazywane jest „Bezpieczne uruchamianie”. 

## <a name="solutions"></a>Rozwiązania

### <a name="add-a-startup-pin"></a>Dodaj numer PIN uruchomienia

Aby zagwarantować bezpieczeństwo urządzenia, niektóre urządzenia z systemem Android wymagają utworzenia numeru PIN uruchomienia. Istnieje wiele wersji systemu Android oferowanych przez wielu różnych producentów. Można spróbować rozwiązać ten problem, wyszukując tę opcję w aplikacji Ustawienia. Na przykład na urządzeniu Samsung Galaxy S7 bezpieczne uruchamianie włącza się przy użyciu opcji **Ustawienia** > **Ekran blokady i zabezpieczenia** > **Bezpieczne uruchamianie**.  

### <a name="encrypt-the-entire-device"></a>Zaszyfruj całe urządzenie

Niektóre urządzenia umożliwiają wybór między szyfrowaniem całego urządzenia i szyfrowaniem tylko używanego miejsca. Wybierz opcję szyfrowania całego urządzenia zamiast opcji „tylko używane miejsce”. Jeśli masz już zaszyfrowane tylko używane miejsce:

1. [Usuń to urządzenie z Portalu firmy](unenroll-your-device-from-intune-android.md)
2. Odszyfruj używane miejsce
3. Zaszyfruj całe urządzenie
4. Zarejestruj ponownie urządzenie

### <a name="downgrade-your-version-of-android"></a>Zmień wersję systemu Android na starszą

Jeśli Twoje urządzenie umożliwia przeprowadzenie zmiany na wersję Android 6.0+, należy to zrobić. Zmiana wersji urządzenia może wiązać się z ryzykiem utraty danych. W przeciwnym razie zalecane jest skontaktowanie się z działem pomocy technicznej Twojej firmy, aby rozwiązać ten problem. Informacje kontaktowe działu pomocy technicznej Twojej firmy znajdziesz w [witrynie internetowej Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).

## <a name="specific-manufacturer-issues"></a>Problemy z urządzeniami niektórych producentów

Niektóre urządzenia z systemem Android w wersji 7.0+ szyfrują dane metodami, które są niezgodne z pewnymi standardami platformy systemu Android. Te urządzenia mogą wydawać się zaszyfrowane, nawet gdy są całkowicie nowe. Usługa Intune rozpoznaje, że metody szyfrowania używane przez te urządzenia narażają informacje w nich zawarte na zagrożenia. Zagrożenia te są związane głównie ze złośliwymi użytkownikami, którzy mają fizyczny dostęp do urządzenia.

> [!Note]
> Firma Microsoft współpracuje z producentami w celu rozwiązania problemów znalezionych podczas testowania lub zgłoszonych nam przez użytkowników. Gdy pojawiają się nowe informacje, aktualizujemy ten artykuł. 

## <a name="known-devices"></a>Znane urządzenia

### <a name="known-devices-that-can-be-updated-to-fix-this-issue"></a>Znane urządzenia, które można zaktualizować w celu rozwiązania tego problemu

W przypadku wymienionych poniżej urządzeń problem może wystąpić, jeśli urządzenie nie zostało zaktualizowane do najnowszej wersji systemu Android. Aktualizacje można zainstalować przy użyciu opcji **Ustawienia** > **Aktualizuj**. 

- [Huawei Honor 8](https://consumer.huawei.com/us/support/phones/honor-8/)
- [Huawei P9](http://consumer.huawei.com/en/phones/p9/)

### <a name="known-devices-that-currently-cannot-be-updated-to-fix-this-issue"></a>Znane urządzenia, których obecnie nie można zaktualizować w celu rozwiązania tego problemu

Nie można rozwiązać tego problemu w przypadku urządzeń wymienionych poniżej. Konieczne może być użycie innego urządzenia w celu uzyskania dostępu do zasobów firmy. 

- [Huawei Mate 8](https://consumer.huawei.com/en/mobile-phones/mate8/index.htm)
- [Urządzenia OPPO](http://www.oppo.com/en/smartphones)
- [Urządzenia Vivo](https://www.vivo.co.in)
- [Smartfony Xiaomi Mi](https://xiaomi-mi.com/mi-smartphones/)
