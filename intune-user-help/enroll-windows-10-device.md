---
title: Rejestrowanie urządzenia z systemem Windows 10 w aplikacji Intune — Portal firmy | Microsoft Docs
description: Instrukcje dotyczące rejestrowania urządzeń z systemem Windows 10 w aplikacji Intune — Portal firmy
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 05/21/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: 812e82df-76df-402b-bfe9-29302838f40e
searchScope:
- User help
ROBOTS: ''
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: ca8b24a1e8d0da4386ab185533fec38d9b34eb21
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72506260"
---
# <a name="enroll-windows-10-devices-with-intune-company-portal"></a>Rejestrowanie urządzenia z systemem Windows 10 w aplikacji Intune — Portal firmy

Aplikacja Intune — Portal firmy umożliwia zarejestrowanie urządzenia z systemem Windows 10 na potrzeby zarządzania przez organizację. W tym artykule opisano sposób rejestrowania urządzeń z systemem Windows 10 w wersjach 1607 i nowszych oraz systemem Windows 10 w wersjach 1511 i starszych. Przed rozpoczęciem [sprawdź, jaką masz wersję na swoim urządzeniu](windows-enrollment-company-portal.md#find-windows-10-version-number), aby wykonać odpowiednie kroki.  

System Windows 10 jest obsługiwany na urządzeniach różnego typu, w tym na komputerach, telefonach i tabletach. Kroki rejestracji są takie same, niezależnie od używanego urządzenia. Twój ekran może jednak różnić się od ilustracji przedstawionych w tym artykule.  
</br>
> [!VIDEO https://www.youtube.com/embed/TKQxEckBHiE?rel=0]

## <a name="enroll-windows-10-version-1607-and-later-device"></a>Rejestrowanie urządzenia z systemem Windows 10 w wersjach 1607 i nowszych 
Opisano tutaj kroki umożliwiające zarejestrowanie urządzenia, na którym działa system Windows 10 w wersji 1607 lub nowszej.  

1. Przejdź do pozycji **Start**. Jeśli masz urządzenie z systemem Windows 10 Mobile, przejdź do listy **Wszystkie aplikacje**.

2. Otwórz aplikację **Ustawienia**. Jeśli ta aplikacja nie jest wymieniona na liście aplikacji, przejdź do paska wyszukiwania i wpisz „ustawienia”.

3. Wybierz kolejno pozycje **Konta** > **Uzyskaj dostęp do miejsca pracy lub nauki** > **Połącz**.  


    ![Wybieranie pozycji Uzyskaj dostęp do miejsca pracy lub nauki](./media/w10-enroll-rs1-connect-to-work-or-school.png)  

4. Aby przejść do strony logowania do usługi Intune w organizacji, wprowadź służbowy adres e-mail. Następnie wybierz pozycję **Dalej**.  


   ![Wprowadź dane konta służbowego](./media/w10-enroll-rs1-set-up-work-or-school-account.png)  

5. Zaloguj się do usługi Intune przy użyciu konta służbowego.  


    ![Dodaj konto służbowe](./media/w10-enroll-rs1-enter-your-credentials.png)  

    W końcu pojawi się komunikat informujący o tym, że firma lub szkoła rejestruje urządzenie.

6. Jeśli Twoja organizacja wymaga skonfigurowania numeru PIN dla systemu Windows Hello, zostanie wyświetlony monit o podanie kodu weryfikacyjnego. Wprowadź kod i postępuj według wskazówek na ekranie, aby utworzyć kod PIN.  

7. Na ekranie **Wszystko jest gotowe!** wybierz pozycję **Gotowe**. Urządzenie jest teraz zarejestrowane.  

8. Aby dokładnie sprawdzić połączenie, wróć do obszaru **Ustawienia** > **Konta** > **Uzyskaj dostęp do miejsca pracy lub nauki**.  Teraz Twoje konto powinno znajdować się na liście.  


    ![Sprawdź, czy połączenie zostało poprawnie skonfigurowane](./media/w10-enroll-rs1-validate-successful-enrollment.png)  

Wciąż nie możesz uzyskać dostępu do swoich plików lub poczty służbowej albo innych danych? Dowiedz się, jak [rozwiązywać problemy z kontem](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-access-work-or-school).  

## <a name="enroll-windows-10-version-1511-and-earlier-device"></a>Rejestrowanie urządzenia z systemem Windows 10 w wersjach 1511 i starszych  
Opisano tutaj kroki umożliwiające zarejestrowanie urządzenia, na którym działa system Windows 10 w wersji 1511 lub starszej.  

1. Przejdź do pozycji **Start**. Jeśli masz urządzenie z systemem Windows 10 Mobile, przejdź do listy **Wszystkie aplikacje**.

2. Otwórz aplikację **Ustawienia**. Jeśli ta aplikacja nie jest wymieniona na liście aplikacji, przejdź do paska wyszukiwania i wpisz „ustawienia”.

3. Wybierz pozycję **Konta** > **Twoje konto**.  


    ![Wybieranie konta](./media/W10-enroll-2-accounts-your-account.png)  

5. Wybierz pozycję **Dodaj konto służbowe**.  


    ![Wybieranie pozycji Dodaj konto służbowe](./media/w10-enroll-3-add-work-school-acct.png)  

6. Zaloguj się przy użyciu poświadczeń konta służbowego.  


    ![Zaloguj się](./media/W10-enroll-4-sign-in.png)  

Wciąż nie możesz uzyskać dostępu do swoich plików lub poczty służbowej albo innych danych? Dowiedz się, jak [rozwiązywać problemy związane z kontem](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-your-account) podczas rejestracji.  

## <a name="it-administrator-support"></a>Pomoc techniczna dla administratora IT   

Jeśli jako administrator IT napotkasz problemy podczas rejestrowania urządzeń, zobacz [Troubleshooting Windows device enrollment problems in Microsoft Intune (Rozwiązywanie problemów z rejestrowaniem urządzeń z systemem Windows w usłudze Microsoft Intune)](https://support.microsoft.com/help/4469913). W tym artykule wymieniono typowe błędy, ich przyczyny i kroki prowadzące do ich usunięcia. 

## <a name="next-steps"></a>Następne kroki  
Jeśli potrzebujesz pomocy dotyczącej portalu firmy lub procesu rejestracji, skontaktuj się z zespołem pomocy technicznej IT w Twojej organizacji. Odpowiednie informacje kontaktowe znajdziesz w [witrynie internetowej Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980). Zaloguj się do witryny przy użyciu konta służbowego.  

 

