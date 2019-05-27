---
title: Rozwiązywanie problemów dotyczących rejestrowania urządzeń z systemem Windows 10 | Microsoft Docs
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/11/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4ab630b6-47ff-443b-a2a5-be23388bcea7
searchScope:
- User help
ROBOTS: ''
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2fe8a765bdb11d0b94dbbb7519360c6e7a01e8ce
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "61501242"
---
# <a name="troubleshoot-your-windows-10-device-enrollment"></a>Rozwiązywanie problemów dotyczących rejestrowania urządzeń z systemem Windows 10
Jeśli urządzenie zostało zarejestrowane, ale nadal nie można uzyskać dostępu do służbowego konta e-mail i plików, wykonaj następujące czynności w celu rozwiązania tego problemu.  

1.  Przyjrzyj się obu ekranom i zastanów się, który z nich przypomina zawartość ekranu urządzenia. Wykonaj kroki odnoszące się do ekranu przypominającego ekran urządzenia.

    Jeśli widzisz ten ekran, postępuj zgodnie z instrukcjami opisanymi w artykule [Rozwiązywanie problemów w przypadku wyświetlenia ekranu Dostęp do zasobów służbowych](#troubleshooting-steps-to-follow-if-you-see-access-work-or-school).

    ![settings-accounts-access-work-or-school](./media/w10-enroll-rs1-connect-to-work-or-school.png)

    Jeśli widzisz ten ekran, postępuj zgodnie z instrukcjami opisanymi w artykule [Rozwiązywanie problemów w przypadku wyświetlenia ekranu Konto użytkownika](#troubleshooting-steps-to-follow-if-you-see-your-account).

    ![settings-accounts-your-account](./media/W10-enroll-2-accounts-your-account.png)

## <a name="troubleshooting-steps-to-follow-if-you-see-access-work-or-school"></a>Rozwiązywanie problemów w przypadku pozycji „Uzyskaj dostęp do miejsca pracy lub nauki”

1. Jeśli powyższe kroki zostały wykonane, ale nadal nie można uzyskać dostępu do służbowej poczty e-mail i plików, wróć do pozycji **Dostęp do zasobów służbowych**.

2. Wykonaj jedną z następujących czynności:

   - Jeśli widzisz połączenie, które wygląda podobnie do poniższego obrazu, wybierz je, a następnie sprawdź, czy widzisz opcje Zarządzanie, Informacje i Rozłącz. Jeśli widzisz te opcje, oznacza to, że nastąpiła rejestracja i zostało nawiązane połączenie.

     ![validate-successful-enrollment](./media/w10-enroll-rs1-validate-successful-enrollment.png)

   - Jeśli nie widzisz informacji o połączeniu pokazanych powyżej lub jeśli są one wyświetlane, ale brakuje niektórych opcji, naciśnij przycisk **Połącz**. Następnie zaloguj się przy użyciu poświadczeń konta służbowego, aby nawiązać połączenie.  

## <a name="troubleshooting-steps-to-follow-if-you-see-your-account"></a>Rozwiązywanie problemów w przypadku pozycji „Konto”

Jeśli powyższe kroki zostały wykonane, ale nadal nie można uzyskać dostępu do służbowej poczty e-mail, plików i innych danych, wróć do pozycji **Konta**, a następnie naciśnij pozycję **Dostęp z miejsca pracy**.

- Jeśli Twoje konto służbowe jest widoczne, oznacza to, że połączenie zostało nawiązane.  

- Jeśli nie widzisz konta służbowego, naciśnij pozycję **Połącz**, a następnie zaloguj się przy użyciu poświadczeń konta służbowego.

## <a name="troubleshooting-steps-to-follow-if-you-see-set-up-a-work-or-school-account"></a>Rozwiązywanie problemów w przypadku pozycji „Konfigurowanie konta służbowego”

Jeśli zostanie wyświetlony komunikat <strong>Nie można automatycznie odnaleźć punktu końcowego zarządzania zgodnego z podaną nazwą użytkownika. Sprawdź nazwę użytkownika i spróbuj ponownie. Jeśli znasz adres URL punktu końcowego zarządzania, wpisz go.</strong> Następnie należy ponownie wprowadzić nazwę użytkownika i hasło. Jeśli to nie zadziała, skontaktuj się z działem pomocy technicznej Twojej firmy w celu sprawdzenia witryny internetowej, którą musisz podać w polu tekstowym <strong>Punkt końcowy zarządzania</strong>. To jest witryna, której adres prawdopodobnie wygląda podobnie do tego: <strong>www.twojafirma.onmicrosoft.com</strong>.

Nadal potrzebujesz pomocy? Skontaktuj się z pomocą techniczną Twojej firmy. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).
