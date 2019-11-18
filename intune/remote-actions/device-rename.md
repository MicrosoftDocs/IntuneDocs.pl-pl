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
ms.openlocfilehash: 0f5ee9a0fe27c3cf9de758fd7155dbd127fb1e5e
ms.sourcegitcommit: 28622c5455adfbce25a404de4d0437fa2b5370be
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/07/2019
ms.locfileid: "73712217"
---
# <a name="rename-a-device-in-intune"></a>Zmienianie nazwy urządzenia w usłudze Intune

Akcja **Zmienianie nazwy urządzenia** pozwala zmienić nazwę urządzenia, które zostało zarejestrowane w usłudze Intune. Nazwa urządzenia jest zmieniana w usłudze Intune i na urządzeniu.

Można zmieniać nazwy następujących typów urządzeń:
- należących do firmy z systemem Windows 
- nadzorowanych z systemem iOS
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
