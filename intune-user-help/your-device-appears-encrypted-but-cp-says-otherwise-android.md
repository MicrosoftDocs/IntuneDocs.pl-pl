---
title: "Urządzenie z systemem Android wydaje się być szyfrowane"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 05/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ba593c08-1a78-4013-8525-b45a948772ec
searchScope: User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 269ad7968242f8f5ce7095c9c73347987675e846
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2017
---
# <a name="your-android-device-seems-to-be-encrypted-but-company-portal-says-otherwise"></a>Urządzenie z systemem Android wydaje się być szyfrowane, ale Portal firmy informuje, że jest inaczej

Zaszyfrowanie urządzenia polega na zakodowaniu znajdujących się na nim informacji przy użyciu klucza tajnego znanego tylko jego posiadaczowi. Chroni to urządzenie przed dostępem nieautoryzowanych osób. W ramach zabezpieczania informacji użytkowników organizacja wymaga szyfrowania urządzenia z systemem Android w celu uzyskania dostępu do firmowych plików, poczty e-mail lub danych.

## <a name="common-issues"></a>Typowe problemy

Nowsze wersje systemu Android, szczególnie od wersji 7.0, wymagają kodu dostępu umożliwiającego uruchomienie, aby zagwarantować, że urządzenie jest w pełni szyfrowane. Różni producenci urządzeń oferują różne opisy i lokalizacje kodu dostępu umożliwiającego uruchomienie. W większości przypadków używa się nazwy „Bezpieczne uruchamianie”. 

## <a name="solutions"></a>Rozwiązania

### <a name="add-a-startup-pin"></a>Dodaj numer PIN uruchomienia

Aby zagwarantować bezpieczeństwo urządzenia, niektóre urządzenia z systemem Android będą wymagać utworzenia numeru PIN uruchomienia. Istnieje wiele wersji systemu Android oferowanych przez wielu różnych producentów. Można spróbować rozwiązać ten problem, wyszukując tę opcję w aplikacji Ustawienia. Na przykład na urządzeniu Samsung Galaxy S7 bezpieczne uruchamianie włącza się przy użyciu opcji **Ustawienia** > **Ekran blokady i zabezpieczenia** > **Bezpieczne uruchamianie**.  

### <a name="downgrade-your-version-of-android"></a>Zmień wersję systemu Android na starszą
Jeśli Twoje urządzenie umożliwia przeprowadzenie zmiany na wersję Android 6.0+, należy to zrobić. Zmiana wersji urządzenia może wiązać się z ryzykiem utraty danych. W przeciwnym razie zalecane jest skontaktowanie się z administratorem IT, aby rozwiązać ten problem. Informacje kontaktowe administratora IT znajdziesz w [witrynie sieci Web Portal firmy](http://portal.manage.microsoft.com).

## <a name="specific-manufacturer-issues"></a>Problemy z urządzeniami niektórych producentów

Niektóre urządzenia z systemem Android w wersji 7.0+ szyfrują dane metodami, które są niezgodne z niektórymi standardami platformy systemu Android. Te urządzenia mogą sprawiać wrażenie zaszyfrowanych, ale usługa Intune interpretuje użyte metody jako narażenie znajdujących się na urządzeniu informacji na działania ze strony złośliwych użytkowników, którzy mają dostęp fizyczny do tego urządzenia.

> [!Note]
> Firma Microsoft współpracuje z producentami w celu rozwiązania problemów znalezionych podczas testowania lub zgłoszonych nam przez użytkowników. Gdy będą dostępne nowe informacje, zaktualizujemy ten artykuł. 

## <a name="known-devices"></a>Znane urządzenia

### <a name="known-devices-that-can-be-updated-to-fix-this-issue"></a>Znane urządzenia, które można zaktualizować w celu rozwiązania tego problemu

W przypadku wymienionych poniżej urządzeń problem może wystąpić, jeśli urządzenie nie zostało zaktualizowane do najnowszej wersji systemu Android. Aktualizacje można zainstalować przy użyciu opcji **Ustawienia** > **Aktualizuj**. 

- [Huawei Honor 8](http://consumer.huawei.com/en/support/mobile-phones/honor8_en-sup.htm)
- [Huawei P9](http://consumer.huawei.com/mobile-phones/p9/index.html)

### <a name="known-devices-that-currently-cannot-be-updated-to-fix-this-issue"></a>Znane urządzenia, których obecnie nie można zaktualizować w celu rozwiązania tego problemu

- [Huawei Mate 8](http://consumer.huawei.com/en/mobile-phones/mate8/index.htm)
- [Smartfony Xiaomi Mi](https://xiaomi-mi.com/mi-smartphones/)
