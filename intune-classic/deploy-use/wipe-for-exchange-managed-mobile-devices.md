---
title: Czyszczenie urządzeń mobilnych zarządzanych przez program Exchange
description: Usługa Microsoft Intune umożliwia czyszczenie lub resetowanie urządzeń przenośnych zarządzanych przy użyciu programu Exchange ActiveSync (EAS) za pomocą programu Intune Exchange Connector.
keywords: ''
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e116b620-1e12-4b5c-9905-2f7acf2ae530
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: lancecra
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 753e5e9dac7199dff18d110808524f05aa669036
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="wipe-for-exchange-managed-mobile-devices"></a>Wipe for Program Exchange-managed mobile devices

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Usługa Microsoft Intune umożliwia czyszczenie lub resetowanie urządzeń przenośnych zarządzanych przy użyciu programu Exchange ActiveSync (EAS) za pomocą programu Intune Exchange Connector. W poniższej tabeli opisano możliwości czyszczenia dostępne za pośrednictwem programu Exchange ActiveSync:


|      Typ czyszczenia       |              Windows 8.1 i Windows RT 8.1              |                            iOS                             |                          Android                          |
|-------------------------|----------------------------------------------------------|------------------------------------------------------------|-----------------------------------------------------------|
|        Pełne czyszczenie danych        |          Usuwa konto e-mail i buforowaną pocztę e-mail.           |                      XResetowanie do ustawień fabrycznych.                       |                      Resetowanie do ustawień fabrycznych.                       |
|  Czyszczenie selektywne/poczta e-mail   |                  Usuwa konto e-mail.                  |                       Nieobsługiwane.                       |                      Nieobsługiwane.                       |
| Czyszczenie selektywne/zasady | Wymuszanie zasad zostaje wyłączone, lecz ustawienia nie są zmieniane | XWymuszanie zasad zostaje wyłączone, lecz ustawienia nie są zmieniane. | Wymuszanie zasad zostaje wyłączone, ale ustawienia nie są zmieniane. |

