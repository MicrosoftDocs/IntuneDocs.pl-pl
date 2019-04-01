---
title: Rejestrowanie urządzenia z systemem Windows 10 w aplikacji Portal firmy usługi Intune | Dokumentacja firmy Microsoft
description: Instrukcje dotyczące rejestrowania urządzeń z systemem Windows 10 w aplikacji Portal firmy usługi Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/11/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 812e82df-76df-402b-bfe9-29302838f40e
searchScope:
- User help
ROBOTS: ''
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4eb5dbb150559de7ad30a598fb78a4fa78033c42
ms.sourcegitcommit: fdc6261f4ed695986e06d18353c10660a4735362
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2019
ms.locfileid: "58069165"
---
# <a name="enroll-windows-10-devices-with-intune-company-portal"></a>Rejestrowanie urządzeń z systemem Windows 10 przy użyciu portalu firmy usługi Intune

Portal firmy usługi Intune umożliwia rejestrowanie urządzenia z systemem Windows 10 w ramach zarządzania Twojej organizacji. W tym artykule opisano sposób rejestrowania urządzeń z systemem Windows 10 w wersji 1607 i nowszych oraz systemu Windows 10 w wersji 1511 lub wcześniejszej. Przed rozpoczęciem upewnij się, że [sprawdź wersję na urządzeniu z systemem](windows-enrollment-company-portal.md#find-windows-10-version-number) tak, aby wykonać odpowiednie kroki.  

Windows 10 są obsługiwane w różnych typów urządzeń, w tym pulpit, telefony i tablety. Instrukcje dotyczące rejestracji są takie same, niezależnie od urządzenia używasz. Jednak ekranu mogą różnić się nieco od obrazów przedstawione w tym artykule.  

> [!VIDEO https://channel9.msdn.com/Series/IntuneEnrollment/Windows-Enrollment/player]  

## <a name="enroll-windows-10-version-1607-and-later-device"></a>Rejestrowanie systemu Windows 10 w wersji 1607 i nowszych urządzenia 
Poniższe kroki opisują sposób rejestrowania urządzenia, na które jest uruchamiane w systemie Windows 10 w wersji 1607 i nowszych.  

1. Przejdź do pozycji **Start**. Jeśli na urządzeniu z systemem Windows 10 Mobile, w dalszym ciągu **wszystkie aplikacje** listy.

2. Otwórz aplikację **Ustawienia**. Jeśli aplikacja nie jest łatwo dostępne na liście aplikacji, przejdź do paska wyszukiwania i wpisz "ustawienia".

3. Wybierz kolejno pozycje **Konta** > **Uzyskaj dostęp do miejsca pracy lub nauki** > **Połącz**.  


    ![Wybieranie pozycji Uzyskaj dostęp do miejsca pracy lub nauki](./media/w10-enroll-rs1-connect-to-work-or-school.png)  

4. Wprowadź służbowy adres e-mail, a następnie wybierz przycisk **Dalej**.  


   ![Wprowadź dane konta służbowego](./media/w10-enroll-rs1-set-up-work-or-school-account.png)  

5. Zaloguj się do usługi Intune przy użyciu konta służbowego.  


    ![Dodaj konto służbowe](./media/w10-enroll-rs1-enter-your-credentials.png)  

    W końcu pojawi się komunikat informujący o tym, że firma lub szkoła rejestruje urządzenie.

6. Jeśli Twoja organizacja wymaga skonfigurować numer PIN dla Windows Hello, możesz wyświetlony monit o podanie kodu weryfikacyjnego. Wprowadź kod i kontynuuj pracę na ekranie kroki umożliwiające utworzenie kodu PIN.  

7. Na ekranie **Wszystko jest gotowe!** wybierz pozycję **Gotowe**. Urządzenie jest teraz zarejestrowane.  

8. Aby dokładnie sprawdzić połączenie, wróć do obszaru **ustawienia** > **kont** > **dostęp do zasobów służbowych**.  Teraz powinny być wymienione na koncie.  


    ![Sprawdź, czy połączenie zostało poprawnie skonfigurowane](./media/w10-enroll-rs1-validate-successful-enrollment.png)  

Wciąż nie możesz uzyskać dostępu do swoich plików lub poczty służbowej albo innych danych? Dowiedz się, jak [Rozwiązywanie problemów z kontem](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-access-work-or-school).  

## <a name="enroll-windows-10-version-1511-and-earlier-device"></a>Rejestrowanie systemu Windows 10 w wersji 1511 i starszych urządzeń  
Poniższe kroki opisują sposób zarejestrować urządzenie, które jest uruchamiane w systemie Windows 10 w wersji 1511 lub wcześniejszej.  

1. Przejdź do pozycji **Start**. Jeśli na urządzeniu z systemem Windows 10 Mobile, w dalszym ciągu **wszystkie aplikacje** listy.

2. Otwórz aplikację **Ustawienia**. Jeśli aplikacja nie jest łatwo dostępne na liście aplikacji, przejdź do paska wyszukiwania i wpisz "ustawienia".

3. Wybierz **kont** > **konta**.  


    ![Wybieranie konta](./media/W10-enroll-2-accounts-your-account.png)  

5. Wybierz pozycję **Dodaj konto służbowe**.  


    ![Wybieranie pozycji Dodaj konto służbowe](./media/w10-enroll-3-add-work-school-acct.png)  

6. Zaloguj się przy użyciu poświadczeń konta służbowego.  


    ![Zaloguj się](./media/W10-enroll-4-sign-in.png)  

Wciąż nie możesz uzyskać dostępu do swoich plików lub poczty służbowej albo innych danych? Dowiedz się, jak [Rozwiązywanie problemów z kontem](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-your-account).   

## <a name="next-steps"></a>Następne kroki  

Aby uzyskać pomoc, skontaktuj się z działem pomocy technicznej Twojej firmy. Można znaleźć w organizacji IT informacji na temat [witryny internetowej Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980). Zaloguj się do witryny przy użyciu konta służbowego.  

 

