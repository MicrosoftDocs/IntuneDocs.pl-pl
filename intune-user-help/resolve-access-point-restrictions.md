---
title: Rozwiązywanie ograniczeń punktu dostępu w usłudze Intune
description: Zapoznaj się z 3 typowymi komunikatami dotyczącymi zasad ograniczeń punktu dostępu w usłudze Intune i sposobami ich rozwiązywania
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 05/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
searchScope:
- User help
ROBOTS: ''
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: aefde274ec7ca925d45dd101ee0ebef1083f7f19
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 03/14/2019
ms.locfileid: "55851274"
---
# <a name="resolve-access-point-restrictions"></a>Rozwiązywanie ograniczeń punktu dostępu

Organizacje mogą ograniczyć lokalizacje, z których urządzenia będą uzyskiwać dostęp do danych firmowych.
Aby skonfigurować te *ograniczenia punktu dostępu*, muszą one określić i ustawić zatwierdzone lokalizacje sieciowe.  

Podczas próby nawiązania połączenia z nierozpoznaną lub niezatwierdzoną siecią może zostać wyświetlony co najmniej jeden z następujących komunikatów:

* Nie skonfigurowano ograniczeń punktu dostępu.
* Nie połączono z zatwierdzoną siecią.
* Wystąpił błąd i nie można wymusić ograniczeń punktu dostępu.

 W poniższych tabelach przedstawiono poszczególne komunikaty, wyjaśnienia ich znaczenia i opis sposobu ponownego uzyskania dostępu do zasobów roboczych.

## <a name="access-point-restrictions-not-set-up"></a>Nie skonfigurowano ograniczeń punktu dostępu  
| Komunikat Portalu firmy | Co oznacza ten komunikat | Co należy zrobić:                                                               
|------------------------|--------------------------|--------------------------|
| **Nie skonfigurowano ograniczeń punktu dostępu — ograniczenia punktu dostępu są aktywne i muszą zostać skonfigurowane.** | Firma zastosowała ograniczenia punktu dostępu na urządzeniu. To ustawienie wymaga zweryfikowania przez aplikację Portal firmy kilku ustawień sieci na urządzeniu. | Wybierz pozycję **Rozwiąż**. Aplikacja Portal firmy sprawdzi, czy masz połączenie z zatwierdzoną siecią firmową. |

## <a name="not-connected-to-an-approved-network"></a>Nie połączono z zatwierdzoną siecią  

| Komunikat Portalu firmy | Co oznacza ten komunikat | Co należy zrobić:                                                                   
|------------------------|-----------------------------------|--------------------------|
| **Urządzenie nie zostało połączone z zatwierdzoną siecią — nawiąż połączenie z zatwierdzoną siecią bezprzewodową.** | Nawiązano połączenie z siecią, która nie została zatwierdzona na potrzeby dostępu z miejsca pracy. Tak długo, jak połączenie z tą siecią będzie nawiązane, nie będzie dostępu do służbowej poczty e-mail, aplikacji ani innych chronionych zasobów firmowych. | Połącz się z zatwierdzoną siecią firmową. Wybierz pozycję **Rozwiąż**, aby ponowić próbę. |

## <a name="restrictions-couldnt-be-enforced"></a>Nie można wymusić ograniczeń  

| Komunikat Portalu firmy | Co oznacza ten komunikat | Co należy zrobić:                                                                      
|------------------------|-----------------------------------|--------------------------|
| **Nie można wymusić ograniczeń punktu dostępu — Portal firmy napotkał błąd.** | Usługa Intune nie może określić, czy nawiązano połączenie z zatwierdzoną siecią. Ten błąd może być wynikiem niskiej jakości łączności sieciowej, niskiego poziomu naładowania baterii, trybu oszczędzania baterii lub błędu Portalu firmy. | Sprawdź, czy masz wystarczająco silny sygnał sieci. Wyłącz tryb oszczędzania baterii i upewnij się, że pozostało co najmniej 30% czasu pracy baterii. Wybierz pozycję **Rozwiąż**, aby ponowić próbę. 

Nadal potrzebujesz pomocy? Zalecamy skontaktowanie się z działem pomocy technicznej Twojej firmy. Informacje kontaktowe są dostępne w [witrynie internetowej Portalu firmy](https://portal.manage.microsoft.com/#HelpDeskDialog).
