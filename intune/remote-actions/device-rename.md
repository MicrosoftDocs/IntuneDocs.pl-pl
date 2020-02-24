---
title: Zmienianie nazwy urządzenia za pomocą usługi Microsoft Intune — Azure | Microsoft Docs
description: Zmienianie nazwy urządzenia za pomocą usługi Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/05/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 11b339a3e94e60db43e8237d9f3d2c729b48a57d
ms.sourcegitcommit: 51591b862d97904291af7aa53a6eb341b11a761e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2020
ms.locfileid: "77413609"
---
# <a name="rename-a-device-in-intune"></a>Zmienianie nazwy urządzenia w usłudze Intune

Akcja **Zmienianie nazwy urządzenia** pozwala zmienić nazwę urządzenia, które zostało zarejestrowane w usłudze Intune. Nazwa urządzenia jest zmieniana w usłudze Intune i na urządzeniu.

Można zmieniać nazwy następujących typów urządzeń:
- należących do firmy z systemem Windows 
- Tryb nadzorowany dla systemów iOS/iPadOS
- należących do firmy z systemem MacOS 10

Ta funkcja nie obsługuje obecnie zmiany nazw urządzeń z systemem Windows dołączonych hybrydowo do usługi Azure AD.

## <a name="rename-a-device"></a>Zmienianie nazwy urządzenia

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Wybierz kolejno pozycje **Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenie > **Więcej** > **Zmień nazwę urządzenia**.
4. W bloku **Zmienianie nazwy urządzenia** wpisz nową nazwę w polu tekstowym. Możesz użyć liter, cyfr i łączników. Nazwa musi zawierać co najmniej jedną literę lub łącznik.
5. Jeśli chcesz ponownie uruchomić urządzenie po zmianie jego nazwy, wybierz pozycję **Tak** obok pozycji **Uruchom ponownie po zmianie nazwy**.
6. Wybierz pozycję **Zmień nazwę**.

## <a name="windows-device-rename-rules"></a>Reguły zmiany nazw urządzeń z systemem Windows
Podczas zmieniania nazwy urządzenia z systemem Windows nowa nazwa musi być zgodna z następującymi regułami:
- Może mieć maksymalnie 15 znaków (nie może zajmować więcej niż 63 bajty i na końcu nie może być znaku null)
- Nie może mieć wartości null ani być pustym ciągiem
- Dozwolone znaki ASCII: Litery (a–z, A–Z), cyfry (0–9) i łączniki
- Dozwolone znaki Unicode: znaki muszą mieć wartość co najmniej 0x80, muszą być prawidłowymi znakami UTF8, musi dać się je zamapować na nazwę IDN (tzn. funkcja RtlIdnToNameprepUnicode musi je pomyślnie przetworzyć; zobacz RFC 3492)
- Nazwy nie mogą zawierać samych cyfr
- W nazwie nie może być spacji
- Niedozwolone znaki: { | } ~ [ \ ] ^ ' : ; < = > ? & @ ! " # $ % ` ( ) + / , . _ *)


## <a name="next-steps"></a>Następne kroki

Aby wyświetlić stan akcji **Zmienianie nazwy** dotyczącej urządzenia, przejdź na stronę **Omówienie** urządzenia.
