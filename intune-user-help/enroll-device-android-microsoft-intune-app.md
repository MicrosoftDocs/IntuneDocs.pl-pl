---
title: Rejestrowanie urządzenia firmowego w aplikacji Microsoft Intune | Microsoft Docs
description: Opis sposobu rejestrowania urządzenia firmowego z systemem Android w usłudze Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/07/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: 0ed3a002-7533-4001-ae24-e10b64b66620
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 81c842eb27b1b9131c164ced5aeed86a78a37353
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72506296"
---
# <a name="enroll-your-corporate-device-with-the-microsoft-intune-app"></a>Rejestrowanie urządzenia firmowego w aplikacji Microsoft Intune

Zarejestruj należące do firmy urządzenie z systemem Android, aby mieć bezpieczny dostęp do firmowej poczty e-mail, aplikacji i innych danych udostępnianych przez organizację. Aplikacja Microsoft Intune obsługuje należące do firmy urządzenia z systemem Android 6.0 lub nowszym. Zostanie ona automatycznie zainstalowana podczas rejestracji na nowych urządzeniach i urządzeniach, na których przywrócono ustawienia fabryczne. 

Istnieją cztery sposoby rejestrowania. Twoja organizacja powinna poinformować Cię, którego sposobu użyć.
 
* Komunikacja zbliżeniowa (NFC)  
* Token  
* Kod QR   
* Google Zero Touch  

## <a name="enroll-device"></a>Rejestrowanie urządzenia 
Wykonaj następujące kroki, aby skonfigurować i zarejestrować urządzenie.  

> [!NOTE]
> W zależności od wersji systemu Android lub producenta urządzenia może być wymagane wykonanie dodatkowych kroków, które nie są uwzględnione w tej procedurze. Kolory i tekst widoczne na zrzutach ekranu również mogą wyglądać inaczej na urządzeniu.  

1. Włącz nowe urządzenie lub urządzenia zresetowane do ustawień fabrycznych.  
2. Na ekranie **powitalnym** wybierz swój język.   Jeśli poproszono Cię o zarejestrowanie się za pomocą kodu QR lub komunikacji NFC, wykonaj opisane poniżej kroki odpowiadające wybranej metodzie.  
     * NFC: zbliż urządzenie obsługujące komunikację NFC do programatora, aby nawiązać połączenie z siecią organizacji. Postępuj zgodnie z monitami wyświetlanymi na ekranie. Po wyświetleniu ekranu z warunkami korzystania z przeglądarki Chrome przejdź do kroku 5.  

     * Kod QR: wykonaj kroki opisane w sekcji [Rejestracja za pomocą kodu QR](#qr-code-enrollment).  

     Jeśli poproszono Cię o skorzystanie z innej metody, przejdź do kroku 3.    

3. Nawiąż połączenie z siecią Wi-Fi i naciśnij pozycję **DALEJ**. Wykonaj kroki odpowiadające wybranej metodzie rejestracji. 

    * Token: po wyświetleniu ekranu logowania Google wykonaj kroki opisane w sekcji [Rejestracja za pomocą tokenu](#token-enrollment).  
    * Google Zero Touch: po nawiązaniu połączenia z siecią Wi-Fi Twoje urządzenie zostanie rozpoznane przez Twoją organizację. Przejdź do kroku 4 i postępuj zgodnie z instrukcjami wyświetlanymi na ekranie aż do zakończenia instalacji.    
 
       ![Przykładowy obraz przedstawiający ekran postanowień firmy Google, który zostanie wyświetlony w przypadku korzystania z funkcji Google Zero Touch. Wyróżniono przycisk Akceptuj i kontynuuj.](./media/google-zero-touch-intune-app-01.png)   
   
4. Przejrzyj postanowienia firmy Google. Następnie naciśnij przycisk **AKCEPTUJ I KONTYNUUJ**.  

      ![Przykładowy obraz przedstawiający ekran postanowień firmy Google z wyróżnionym przyciskiem Akceptuj i kontynuuj.](./media/fully-managed-intune-app-04.png)   

6. Przejrzyj warunki użytkowania przeglądarki Chrome. Następnie naciśnij przycisk **AKCEPTUJ I KONTYNUUJ**.  

   ![Przykładowy obraz przedstawiający ekran warunków użytkowania przeglądarki Chrome z wyróżnionym przyciskiem Akceptuj i kontynuuj.](./media/fully-managed-intune-app-06.png)   

7. Na ekranach logowania zaloguj się przy użyciu konta służbowego.   

    a. Wprowadź swój adres e-mail, a następnie naciśnij przycisk **Dalej**.      
    b. Wprowadź hasło, a następnie naciśnij przycisk **Zaloguj się**.  

8. W zależności od wymagań organizacji może zostać wyświetlony monit o zaktualizowanie ustawień, takich jak blokada ekranu lub szyfrowanie. Jeśli zobaczysz takie monity, naciśnij przycisk **USTAW** i postępuj zgodnie z instrukcjami wyświetlanymi na ekranie.  

   ![Przykładowy obraz przedstawiający ekran konfigurowania telefonu służbowego z wyróżnionym przyciskiem Ustaw.](./media/fully-managed-intune-app-10.png)   

9. Aby zainstalować aplikacje służbowe na urządzeniu, naciśnij przycisk **ZAINSTALUJ**. Po zakończeniu instalacji naciśnij przycisk **DALEJ**.  

   ![Przykładowy obraz przedstawiający ekran konfigurowania telefonu służbowego z wyróżnionym przyciskiem Zainstaluj.](./media/fully-managed-intune-app-11.png)   

10. Naciśnij przycisk **Start** , aby otworzyć aplikację Microsoft Intune i zarejestrować urządzenie. 

    ![Przykładowy obraz przedstawiający ekran konfigurowania telefonu służbowego z wyróżnionym przyciskiem Start.](./media/fully-managed-intune-app-17.png)   

11. Naciśnij pozycję **Zaloguj** , a następnie naciśnij pozycję **dalej** , aby rozpocząć rejestrację. Gdy zobaczysz komunikat, że rejestracja została zakończona, naciśnij pozycję **gotowe**.  

    ![Przykładowy obraz konfigurowania dostępu, rejestrowania ekranu urządzenia, wyróżniania przycisku Gotowe.](./media/fully-managed-intune-app-19.png)   

10. Po wyświetleniu komunikatu z informacją, że urządzenie jest gotowe, naciśnij przycisk **GOTOWE**.  

    ![Przykładowy obraz przedstawiający ekran konfigurowania telefonu służbowego z wyróżnionym przyciskiem Gotowe.](./media/fully-managed-intune-app-18.png)   

Jeśli masz problemy z uzyskaniem dostępu do zasobów organizacji, może być konieczne zaktualizowanie dodatkowych ustawień na urządzeniu. Zaloguj się do aplikacji Microsoft Intune, aby sprawdzić, czy są wymagane aktualizacje.   


## <a name="qr-code-enrollment"></a>Rejestracja za pomocą kodu QR  
W tej sekcji zeskanujesz dostarczony przez firmę kod QR.  Gdy wszystko będzie gotowe, nastąpi przekierowanie z powrotem do kroków rejestracji urządzenia.     
  
1. Na ekranie **powitalnym** naciśnij ekran pięć razy, aby rozpocząć konfigurowanie kodu QR.  

   ![Przykładowy obraz przedstawiający ekran powitalny konfiguracji urządzenia z wyróżnionymi instrukcjami naciśnięcia ekranu.](./media/qr-code-intune-app-01.png)  

2. Postępuj zgodnie z instrukcjami wyświetlanymi na ekranie, aby nawiązać połączenie z siecią Wi-Fi.  
3. Jeśli urządzenie nie ma skanera kodów QR, na ekranach konfiguracji będzie wyświetlany postęp instalowania skanera. Zaczekaj na ukończenie instalacji.  
4. Po wyświetleniu monitu zeskanuj kod QR profilu rejestracji przekazany przez organizację.  
5. Wróć do kroku 4. [Rejestrowanie urządzenia](#enroll-device), aby kontynuować konfigurację.  

## <a name="token-enrollment"></a>Rejestracja za pomocą tokenu  
W tej sekcji wprowadzisz token dostarczony przez firmę. Gdy wszystko będzie gotowe, nastąpi przekierowanie z powrotem do kroków rejestracji urządzenia.  

1. Na ekranie logowania Google w polu **Adres e-mail lub telefon** wpisz **afw#setup**. Naciśnij opcję **Dalej**. 

   ![Przykładowy obraz ekranu logowania Google z wpisanym w polu ciągiem „afw#setup”.](./media/token-intune-app-01.png)   

2. Wybierz pozycję **Zainstaluj** dla aplikacji **Android Device Policy**. Kontynuuj proces instalacji. W zależności od urządzenia może być konieczne przejrzenie i zaakceptowanie dodatkowych postanowień.    

3. Na ekranie **Zarejestruj to urządzenie** wybierz przycisk **Dalej**.  

4. Wybierz pozycję **Wprowadź kod**.  

5. Na ekranie **Zeskanuj lub wprowadź kod** wpisz kod dostarczony przez organizację.  Następnie kliknij przycisk **Dalej**.  

   ![Przykładowy obraz przedstawiający ekran Zeskanuj lub wprowadź kod z wyróżnionym przyciskiem Dalej.](./media/token-intune-app-04.png)  

6. Wróć do kroku 4. [Rejestrowanie urządzenia](#enroll-device), aby kontynuować konfigurację.  



## <a name="next-steps"></a>Następne kroki   
Nadal potrzebujesz pomocy? Skontaktuj się z działem pomocy technicznej Twojej firmy (sprawdź [witrynę internetową Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980), aby uzyskać informacje kontaktowe) lub napisz do <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with enrolling my Android device&body=Describe the issue you're experiencing here.">zespołu ds. systemu Android w firmie Microsoft</a>.  
