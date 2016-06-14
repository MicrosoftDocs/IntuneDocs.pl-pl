---
# required metadata

title: Zarządzanie programem DEP firmy Apple dla systemu iOS przy użyciu usługi Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8ff9d9e7-eed8-416c-8508-efc20fca8578

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Rejestrowanie firmowych urządzeń z systemem iOS przy użyciu Device Enrollment Program
Usługa Microsoft Intune może wdrożyć profil rejestracji, który będzie rejestrować urządzenia z systemem iOS zakupione w ramach programu Device Enrollment Program (DEP) „bez udziału użytkownika”. Pakiet rejestracyjny może obejmować opcje Asystenta ustawień dla urządzenia. Urządzenia zarejestrowane w programie DEP nie mogą zostać wyrejestrowane przez użytkowników.

## Zarządzanie programem DEP firmy Apple dla systemu iOS przy użyciu usługi Microsoft Intune
W celu zarządzania firmowymi urządzeniami z systemem iOS przy użyciu programu Device Enrollment Program (DEP) firmy Apple organizacja musi dołączyć do programu DEP firmy Apple i zakupić urządzenia w ramach tego programu. Szczegóły tego procesu są dostępne pod adresem:  [https://deploy.apple.com](https://deploy.apple.com). Zalety programu obejmują funkcje bezobsługowego konfigurowania urządzeń bez konieczności podłączania poszczególnych urządzeń do komputera przy użyciu połączenia USB.

Aby zarejestrować firmowe urządzenia z systemem iOS w programie DEP, należy uzyskać token programu DEP od firmy Apple. Token umożliwia usłudze Intune synchronizację informacji dotyczących urządzeń uczestniczących w programie DEP należących do firmy. Umożliwia on również usłudze Intune przekazywanie profilów rejestracji do firmy Apple i przypisywanie urządzeń do tych profilów.

1.  **Rozpoczynanie zarządzania urządzeniami z systemem iOS w usłudze Microsoft Intune**
    Aby móc rejestrować urządzenia z systemem iOS w programie Device Enrollment Program (DEP), musisz włączyć zarządzanie systemem iOS dla usługi Intune.

2.  **Pobieranie klucza szyfrowania**
    Jako administrator otwórz [konsolę administracyjną usługi Microsoft Intune](http://manage.microsoft.com), wybierz pozycje **Administracja** &gt; **Zarządzanie urządzeniami przenośnymi** &gt; **iOS** &gt; **Device Enrollment Program** i kliknij pozycję **Pobierz klucz szyfrowania**. Zapisz lokalnie plik klucza szyfrowania (PEM) Plik PEM jest używany na potrzeby żądania certyfikatu relacji zaufania z portalu programu Device Enrollment Program firmy Apple.

      ![Aktualizacja tokenu programu Device Enrollment Program](../media/dev-sa-ios-dep.png)

3.  **Pobieranie tokenu programu Device Enrollment Program**
    Przejdź do [portalu Device Enrollment Program](https://deploy.apple.com) (https://deploy.apple.com) i zaloguj się przy użyciu identyfikatora Apple ID swojej firmy. Tego identyfikatora firmy Apple należy używać w przyszłości do odnawiania tokenu programu DEP.

    1.  W [portalu programu Device Enrollment Program](https://deploy.apple.com) wybierz kolejno pozycje **Device Enrollment Program** &gt; **Manage Servers (Zarządzanie serwerami)**, a następnie kliknij pozycję **Add MDM Server (Dodaj serwer MDM)**..

    2.  Wprowadź nazwę serwera w polu **MDM Server Name** (Nazwa serwera MDM), a następnie kliknij przycisk **Next**(Dalej). Nazwa serwera służy użytkownikowi do identyfikowania serwera MDM. Nie jest to nazwa ani adres URL serwera usługi Microsoft Intune.

    3.  Zostanie otwarte okno dialogowe **Add &lt;nazwa_serwera&gt;** (Dodawanie serwera <nazwa_serwera>). Kliknij przycisk **Wybierz plik...** w celu przekazania pliku PEM, a następnie kliknij przycisk **Next** (Dalej)..

    4.  W oknie dialogowym **Add&lt; <nazwa_serwera>&gt;** (Dodawanie serwera <nazwa_serwera>) zostanie wyświetlony link **Your Server Token** (Token serwera). Pobierz plik tokenu serwera (p7m) na komputer, a następnie kliknij przycisk **Done**(Gotowe)..

    Ten plik certyfikatu (p7m) służy do ustanawiania relacji zaufania między serwerami usługi Intune i programu Device Enrollment Program firmy Apple.

4.  **Dodawanie tokenu programu DEP do usługi Intune**
    W [konsoli administracyjnej Microsoft Intune](http://manage.microsoft.com), przejdź do pozycji **Administracja** &gt; **Zarządzanie urządzeniami przenośnymi** &gt; **iOS** &gt; **Device Enrollment Program** i kliknij przycisk **Przekaż token DEP**. **Przeglądaj**, aby znaleźć lokalizację pliku certyfikatu (p7m), wprowadź swój **identyfikator Apple ID** i kliknij pozycję **Przekaż**.

5.  **Dodawanie zasad rejestracji urządzeń firmowych**
    W [konsoli administracyjnej usługi Microsoft Intune](http://manage.microsoft.com) wybierz kolejno pozycje **Zasady** &gt; **Rejestracja urządzeń firmowych**, a następnie kliknij przycisk **Dodaj**. Podaj informacje w obszarze **Ogólne** , takie jak **Nazwa** i **Opis**, określ, czy urządzenia przypisane do tego profilu pozostają w koligacji z użytkownikiem, czy też należą do grupy, a następnie wybierz opcję **Skonfiguruj ustawienia programu rejestracji urządzeń dla tych zasad** w celu obsługi programu DEP. **Okienka asystenta ustawień** służą do definiowania ustawień urządzenia z systemem iOS konfigurowanych podczas instalacji.

      ![Okienko Asystenta ustawień](../media/pol-sa-corp-enroll.png)

6.  **Przypisywanie urządzeń programu DEP do zarządzania**
    Przejdź do [portalu Device Enrollment Program](https://deploy.apple.com) (https://deploy.apple.com) i zaloguj się przy użyciu identyfikatora Apple ID swojej firmy. Wybierz kolejno pozycje **Deployment Program (Program wdrażania)** &gt; **Device Enrollment Program** &gt; **Manage Devices (Zarządzanie urządzeniami)**. Określ sposób **wyboru urządzeń**, podaj informacje o urządzeniach i określ szczegóły według numeru seryjnego ( **Serial Number**) urządzenia, numeru zamówienia ( **Order Number**) lub przekaż plik CSV ( **Upload CSV File**). Następnie wybierz pozycję **Assign to Server** (Przypisz do serwera), wybierz nazwę serwera &lt;nazwa_serwera&gt; określoną dla usługi Microsoft Intune i kliknij przycisk **OK**..

7.  **Synchronizowanie urządzeń zarządzanych w programie DEP**
    Jako administrator otwórz [konsolę administracyjną usługi Microsoft Intune](http://manage.microsoft.com), wybierz kolejno pozycje **Administracja** &gt; **Zarządzanie urządzeniami przenośnymi** &gt; **iOS** &gt; **Device Enrollment Program** i kliknij pozycję **Synchronizuj teraz**. Żądanie synchronizacji zostanie wysłane do firmy Apple. Aby wyświetlić urządzenia zarządzane przez program DEP po synchronizacji, w [konsoli administracyjnej usługi Microsoft Intune](http://manage.microsoft.com) przejdź do pozycji **Grupy** &gt; **Wszystkie urządzenia należące do firmy**. W obszarze roboczym **Urządzenia należące do firmy** dla zarządzanych urządzeń wyświetlany jest **stan** „Nie nawiązano komunikacji”, dopóki urządzenie nie zostanie włączone i Asystent ustawień nie zostanie uruchomiony w celu zarejestrowania urządzenia.

    Aby spełnić warunki ruchu programu DEP firmy Apple, usługa Intune nakłada następujące ograniczenia:
     -  Pełną synchronizację programu DEP można uruchamiać nie częściej niż co 7 dni. Podczas pełnej synchronizacji usługa Intune odświeża każdy numer seryjny Apple przypisany do usługi Intune, niezależnie od tego, czy numer seryjny był już wcześniej synchronizowany. W przypadku próby przeprowadzenia pełnej synchronizacji przed upływem 7 dni od poprzedniej pełnej synchronizacji usługa Intune odświeża tylko numery seryjne, które jeszcze nie zostały przypisane do usługi Intune.
     -  Każde żądanie synchronizacji ma przydzielone 10 minut na zakończenie. W tym czasie lub do momentu zakończenia żądania powodzeniem przycisk synchronizacji jest wyłączony.

8.  **Przekazywanie urządzeń użytkownikom**
    Urządzenia firmowe mogą zostać teraz przekazane użytkownikom. Po włączeniu urządzenia z systemem iOS zostanie ono zarejestrowane na potrzeby zarządzania przez usługę Intune.



### Zobacz także
[Przygotowanie do rejestracji urządzeń](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


