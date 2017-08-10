---
title: "Rozwiązywanie problemów dotyczących rejestrowania urządzeń z systemem Windows 10 | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 07/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4ab630b6-47ff-443b-a2a5-be23388bcea7
searchScope: User help
ROBOTS: 
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 701ee2081d8f696a1c37eaa2857ab92942d79f48
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/03/2017
---
# <a name="troubleshoot-your-windows-10-device-enrollment"></a>Rozwiązywanie problemów dotyczących rejestrowania urządzeń z systemem Windows 10
Jeśli po wykonaniu kroków opisanych w artykule [Rejestrowanie urządzenia z systemem Windows 10 Mobile lub Windows 10 Desktop w usłudze Intune](enroll-your-w10-phone-or-w10-pc-windows.md) nadal nie możesz uzyskać dostępu do służbowego adresu e-mail i plików, wykonaj następujące czynności.

1.  Przyjrzyj się obu ekranom i zastanów się, który z nich przypomina zawartość ekranu urządzenia. Wykonaj kroki odnoszące się do ekranu przypominającego ekran urządzenia.

    Jeśli widzisz ten ekran, postępuj zgodnie z instrukcjami opisanymi w artykule [Rozwiązywanie problemów w przypadku wyświetlenia ekranu Dostęp do zasobów służbowych](#troubleshooting-steps-to-follow-if-you-see-access-work-or-school).

    ![settings-accounts-access-work-or-school](./media/w10-enroll-rs1-connect-to-work-or-school.png)

    Jeśli widzisz ten ekran, postępuj zgodnie z instrukcjami opisanymi w artykule [Rozwiązywanie problemów w przypadku wyświetlenia ekranu Konto użytkownika](#troubleshooting-steps-to-follow-if-you-see-your-account).

    ![settings-accounts-your-account](./media/W10-enroll-2-accounts-your-account.png)

## <a name="troubleshooting-steps-to-follow-if-you-see-access-work-or-school"></a>Rozwiązywanie problemów w przypadku pozycji „Uzyskaj dostęp do miejsca pracy lub nauki”

1.  Jeśli powyższe kroki zostały wykonane, ale nadal nie można uzyskać dostępu do służbowej poczty e-mail i plików, wróć do pozycji **Dostęp do zasobów służbowych**.

2. Wykonaj jedną z następujących czynności:

    - Jeśli widzisz połączenie, które wygląda podobnie do poniższego obrazu, wybierz je, a następnie sprawdź, czy widzisz opcje Zarządzanie, Informacje i Rozłącz. Jeśli widzisz te opcje, oznacza to, że nastąpiła rejestracja i zostało nawiązane połączenie.

    ![validate-successful-enrollment](./media/w10-enroll-rs1-validate-successful-enrollment.png)

    - Jeśli nie widzisz informacji o połączeniu pokazanych powyżej lub jeśli są one wyświetlane, ale brakuje niektórych opcji, naciśnij przycisk **Połącz**, a następnie zaloguj się przy użyciu swoich poświadczeń służbowych. Na tym etapie powinno zostać nawiązane połączenie.

## <a name="troubleshooting-steps-to-follow-if-you-see-your-account"></a>Rozwiązywanie problemów w przypadku pozycji „Konto”

Jeśli powyższe kroki zostały wykonane, ale nadal nie można uzyskać dostępu do służbowej poczty e-mail, plików i innych danych, wróć do pozycji **Konta**, a następnie naciśnij pozycję **Dostęp z miejsca pracy**.

- Jeśli widzisz konto służbowe, gratulujemy. Połączenie zostało nawiązane.

- Jeśli nie widzisz konta służbowego, naciśnij pozycję **Połącz**, a następnie zaloguj się przy użyciu poświadczeń konta służbowego.

## <a name="troubleshooting-steps-to-follow-if-you-see-set-up-a-work-or-school-account"></a>Rozwiązywanie problemów w przypadku pozycji „Konfigurowanie konta służbowego”

Jeśli zostanie wyświetlony komunikat __Nie można automatycznie odnaleźć punktu końcowego zarządzania zgodnego z podaną nazwą użytkownika. Sprawdź nazwę użytkownika i spróbuj ponownie. Jeśli znasz adres URL punktu końcowego zarządzania, wpisz go.__ Następnie należy ponownie wprowadzić nazwę użytkownika i hasło. Jeśli to nie zadziała, skontaktuj się z administratorem IT w celu sprawdzenia witryny internetowej, którą musisz podać w polu tekstowym **Punkt końcowy zarządzania**. To jest witryna, której adres prawdopodobnie wygląda podobnie do tego: **www.twojafirma.onmicrosoft.com**. 

Nadal potrzebujesz pomocy? Skontaktuj się z administratorem IT. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](http://portal.manage.microsoft.com).
