---
# required metadata

title: Wycofywanie urządzeń | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3dbec400-5d8a-47be-b892-7745811d9de2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Wycofywanie urządzeń z zarządzania przy użyciu usługi Microsoft Intune

Bez względu na to, czy urządzenia są osobiste, czy firmowe, w którymś momencie konieczne jest wycofanie ich z zarządzania przy użyciu usługi Intune. Wycofanie urządzenia jest względnie proste — można przeprowadzić selektywne czyszczenie lub pełne czyszczenie.
## Czyszczenie danych i aplikacji z urządzeń
Zarówno selektywne czyszczenie, jak i pełne czyszczenie powoduje usunięcie urządzenia z zarządzania przy użyciu usługi Intune przez usunięcie jego zasad i Portalu firmy, co oznacza, że urządzenie nie będzie już miało poświadczeń niezbędnych do logowania się do zasobów firmy, takich jak program Microsoft SharePoint, poczta e-mail czy usługa Office 365.

[Selektywne czyszczenie](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe) jest preferowane w przypadku pracowników, którzy zarejestrowali własne urządzenia w usłudze Intune, ponieważ nie ma to wpływu na informacje osobiste przechowywane na urządzeniu. Zostaną usunięte tylko dane firmowe.

W przypadku urządzeń należących do firmy można także wykonać [pełne czyszczenie](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe), które przywraca ustawienia fabryczne urządzenia.

## Odwołanie dostępu do sieci firmowej
W przypadku wycofywania urządzenia z powodu odejścia pracownika z firmy i nie zwrócenia przez niego sprzętu należącego do firmy można także [zdalnie zablokować](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) urządzenie. Pozwala to zapobiec niewłaściwemu użyciu sprzętu firmowego i informacji dotyczących firmy, chociaż może to oznaczać utratę urządzenia.

Warto też odwołać licencję z konta użytkownika usługi Intune pracownika. Spowoduje to zwolnienie licencji i umożliwi jej przypisanie do nowego konta użytkownika.

## Wycofanie sprzętu
Czasami może dojść do zużycia urządzenia. W takiej sytuacji [zresetowanie urządzenia do ustawień fabrycznych](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md) wraz z pełnym czyszczeniem powoduje usunięcie wszystkich danych i usunięcie urządzenia z usługi Intune. Następnie można pozbyć się urządzenia zgodnie z zasadami firmy.

### Zobacz także
[Zapewnianie lepszej ochrony danych dzięki funkcji pełnego lub selektywnego czyszczenia](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md)


<!--HONumber=May16_HO1-->


