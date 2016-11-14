---
title: "Wycofywanie urządzeń | Microsoft Intune"
description: "Usługa Intune obsługuje zarówno selektywne czyszczenie, jak i pełne czyszczenie na potrzeby usunięcia urządzenia z zarządzania w usłudze Intune przez usunięcie jego zasad i Portalu firmy."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3dbec400-5d8a-47be-b892-7745811d9de2
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f2ecd0c90df60dce3a610c00fa0bc35ea7c3a7d3
ms.openlocfilehash: c96f320856270281772cc3abc891d142eab97ac7


---

# Wycofywanie urządzeń z zarządzania przy użyciu usługi Microsoft Intune

Bez względu na to, czy urządzenia są osobiste, czy firmowe, w którymś momencie konieczne jest wycofanie zarządzanego urządzenia z zarządzania w usłudze Intune. Wycofanie urządzenia może być konieczne z różnych powodów:

-   Użytkownik opuszcza firmę w sposób planowany („zarządzane” opuszczenie firmy)
-   Użytkownik opuszcza firmę w sposób nagły (zwolnienie, odejście itp.).
-   Utrata urządzenia
-   Zmiana zastosowania urządzenia (przeniesienie na innego użytkownika, ponowne użycie do innego celu itp.)

Można przeprowadzić selektywne lub pełne czyszczenie urządzenia zarządzanego jako urządzenie przenośne lub zablokować urządzenie i zresetować jego hasło. Przez wyczyszczenie urządzenia zwalnia się subskrypcję użytkownika, co pozwala dodać inne urządzenie. Można również wycofać komputery zarządzane przy użyciu oprogramowania klienckiego usługi Intune.

## Czyszczenie danych i aplikacji z urządzeń
Zarówno selektywne czyszczenie, jak i pełne czyszczenie powodują usunięcie urządzenia z zarządzania w usłudze Intune przez usunięcie jego zasad i Portalu firmy. W wyniku tego urządzenie nie dysponuje już poświadczeniami niezbędnymi w celu zalogowania się do zasobów firmy, takich jak program Microsoft SharePoint, poczta e-mail lub usługa Office 365.

[Selektywne czyszczenie](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe) jest preferowane w przypadku pracowników, którzy zarejestrowali własne urządzenia w usłudze Intune, ponieważ nie ma to wpływu na informacje osobiste przechowywane na urządzeniu. Zostaną usunięte tylko dane firmowe.

W przypadku urządzeń wymagających zmiany przeznaczenia można także wykonać [pełne czyszczenie](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe), które przywraca ustawienia fabryczne urządzenia.

## Aby usunąć urządzenia w portalu usługi Azure Active Directory

1.  Zaloguj się przy użyciu poświadczeń swojej organizacji w witrynie [http://aka.ms/accessaad](http://aka.ms/accessaad) lub [https://portal.office.com](https://portal.office.com), a następnie wybierz pozycje **Centra administracji** &gt; **Azure AD**.

2.  Utwórz subskrypcję platformy Azure, jeśli jej nie masz. Jeśli masz płatne konto, ta operacja nie powinna wymagać uiszczenia płatności ani podania danych karty kredytowej. Wybierz link do subskrypcji **Zarejestruj bezpłatny katalog Azure Active Directory**.

4.  Wybierz pozycję **Active Directory**, a następnie wybierz organizację.

5.  Wybierz kartę **Użytkownicy**.

6.  Wybierz użytkownika, którego urządzenia chcesz usunąć.

7.  Wybierz pozycję **Urządzenia**.

8.  Wybierz odpowiednie urządzenia, a następnie wybierz polecenie **Usuń urządzenie**. Urządzenia zostaną usunięte przy następnym synchronizowaniu ich z usługą Active Directory. Zwykle nastąpi to w ciągu 4 godzin. Po wykonaniu synchronizacji urządzenie zostanie usunięte z zarządzania. Spowoduje to usunięcie urządzenia z limitu urządzeń dla tego użytkownika.

## Wycofywanie zarządzanych komputerów
Komputery zarządzane przez oprogramowanie klienckie usługi Intune można usunąć z zarządzania w konsoli administracyjnej usługi Intune. Spowoduje to również odinstalowanie oprogramowania klienckiego i usunięcie zasad usługi Intune z komputera. Zobacz informacje na temat [wycofywania komputerów zarządzanych przy użyciu oprogramowania klienckiego usługi Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#retire-a-computer.md).

## Blokowanie dostępu do urządzenia
W przypadku zagubienia urządzenia lub konieczności wycofania urządzenia z powodu odejścia pracownika z firmy i nie zwrócenia przez niego sprzętu należącego do firmy można także [zresetować kod dostępu i zdalnie zablokować](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) urządzenie. Pozwala to zapobiec niewłaściwemu użyciu informacji firmowych, chociaż może to oznaczać utratę urządzenia.

Warto też odwołać licencję z konta użytkownika usługi Intune pracownika. Spowoduje to zwolnienie licencji i umożliwi jej przypisanie do nowego konta użytkownika.

## Wycofanie sprzętu
Czasami może dojść do zużycia urządzenia. W takiej sytuacji [zresetowanie urządzenia do ustawień fabrycznych](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md) wraz z pełnym czyszczeniem powoduje usunięcie wszystkich danych i usunięcie urządzenia z usługi Intune. Następnie można pozbyć się urządzenia zgodnie z zasadami firmy.

### Zobacz także
[Zapewnianie lepszej ochrony danych dzięki funkcji pełnego lub selektywnego czyszczenia](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md)



<!--HONumber=Oct16_HO3-->


