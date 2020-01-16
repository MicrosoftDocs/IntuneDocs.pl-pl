---
title: Rejestrowanie komputera Mac przy użyciu Intune — Portal firmy | Microsoft Docs
description: Rejestrowanie urządzenia z systemem macOS w usłudze Intune przy użyciu aplikacji Portal firmy
keywords: Mac OS X, macOS, OS X
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 12/16/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: 3bb659cc-9b57-4d19-8631-2c26749fa71c
searchScope:
- User help
ROBOTS: ''
ms.reviewer: kakyker
ms.suite: ems
ms.custom: intune-enduser
ms.collection: ''
ms.openlocfilehash: e04950a67938d883b0762c03efa371fcb74d0731
ms.sourcegitcommit: caee3c3fa77586314aa8040b0caf32a0527b669e
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 01/10/2020
ms.locfileid: "75855480"
---
# <a name="enroll-your-macos-device-using-the-company-portal-app"></a>Rejestrowanie urządzenia z systemem macOS przy użyciu aplikacji Portal firmy  

Zarejestruj urządzenie z systemem macOS przy użyciu aplikacji Portal firmy w usłudze Intune, aby uzyskać bezpieczny dostęp do służbowej poczty e-mail, plików i aplikacji.

Organizacje zwykle wymagają zarejestrowania urządzenia, aby można było uzyskać dostęp do danych własnościowych. Zarejestrowane urządzenie staje się urządzeniem *zarządzanym*. Organizacja może przypisywać zasady i aplikacje do urządzenia za pośrednictwem dostawcy zarządzania urządzeniami przenośnymi (MDM), takiego jak usługa Intune. Aby uzyskać ciągły dostęp do danych służbowych na urządzeniu, musisz skonfigurować urządzenie, aby dopasować je do ustawień zasad w organizacji.  

W tym artykule opisano, jak aplikacja Portal firmy dla systemu macOS umożliwia rejestrowanie, konfigurowanie i utrzymywanie urządzenia zgodnie z wymaganiami organizacji.  


## <a name="what-to-expect-from-the-company-portal-app"></a>Czego można oczekiwać od aplikacji Portal firmy

Podczas konfiguracji początkowej aplikacja Portal firmy wymaga zalogowania się i uwierzytelnienia w organizacji. Następnie Portal firmy informuje o ustawieniach urządzenia, które należy skonfigurować, aby spełniały wymagania organizacji. Na przykład organizacje często ustawiają wymagania dotyczące minimalnej i maksymalnej długości haseł, które trzeba spełnić.    

Po zarejestrowaniu urządzenia Portal firmy zawsze upewnij się, że urządzenie jest chronione zgodnie z wymaganiami organizacji. Na przykład jeśli zainstalujesz aplikację z niezaufanego źródła, Portal firmy będzie alertować i może ograniczyć dostęp do zasobów organizacji. Zasady ochrony aplikacji, takie jak te, są typowe dla organizacji. W celu odzyskania dostępu prawdopodobnie trzeba będzie odinstalować niezaufaną aplikację. 

Jeśli po zarejestrowaniu organizacja wymusi nowe wymagania dotyczące zabezpieczeń, np. uwierzytelnianie wieloskładnikowe, Portal firmy powiadomi użytkownika. Będziesz mieć szansę na dostosowanie ustawień, aby nadal kontynuować pracę z urządzenia.  

Aby uzyskać więcej informacji o rejestracji, zobacz [Co się stanie, jeśli zainstaluję aplikację Portal firmy i zarejestruję swoje urządzenie?](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-macos.md).  

## <a name="get-your-macos-device-managed"></a>Zapoznaj się z urządzeniem macOS zarządzanym  
Wykonaj poniższe kroki, aby zarejestrować urządzenie z programem macOS w organizacji. Na urządzeniu musi być uruchomiony program macOS 10,12 lub nowszy.   

> [!NOTE]
> W trakcie tego procesu może zostać wyświetlony monit o zezwolenie Portal firmy na używanie poufnych informacji przechowywanych w łańcuchu kluczy. Te monity są częścią zabezpieczeń firmy Apple. Po wyświetleniu monitu wpisz hasło do łańcucha kluczy logowania i wybierz opcję **zawsze Zezwalaj na**. Jeśli naciśniesz klawisz **wprowadzić** lub **zwrócić** na klawiaturze, w wierszu polecenia zostanie wybrana opcja **Zezwalaj na**, co może spowodować wyświetlenie dodatkowych monitów.  

### <a name="install-company-portal-app"></a>Instalowanie aplikacji Portal firmy  
1. Przejdź do [zarejestrować moje](https://go.microsoft.com/fwlink/?linkid=853070)na komputerze Mac.  
2. Plik Instalatora Portal firmy. pkg zostanie pobrany. Otwórz instalatora i wykonaj kroki opisane w sekcji. 
3. Wyrażanie zgody na umowę licencyjną na oprogramowanie. 
4. Wprowadź hasło urządzenia lub zarejestrowany odcisk palca, aby zainstalować oprogramowanie.  
5. Otwórz aplikację Portal firmy. 

> [!IMPORTANT]
> Program Microsoft AutoUpdate może zostać otwarty w celu zaktualizowania oprogramowania firmy Microsoft. Po zainstalowaniu wszystkich aktualizacji Otwórz aplikację Portal firmy. Aby uzyskać najlepsze czynności konfiguracyjne, należy zainstalować najnowsze wersje programu Microsoft AutoUpdate i Portal firmy.  


### <a name="enroll-your-mac"></a>Rejestrowanie komputera Mac  


1. Zaloguj się do Portalu firmy przy użyciu konta służbowego.  
2. Po otwarciu aplikacji wybierz pozycję **Rozpocznij**.  
3. Zapoznaj się z informacjami o tym, co Twoja organizacja może zobaczyć na Twoim zarejestrowanym urządzeniu. Następnie wybierz pozycję **Kontynuuj**.
4.  Jeśli zostanie wyświetlony monit, wprowadź hasło urządzenia na ekranie **Zainstaluj profil zarządzania**.

    ![Przykład zrzutu ekranu Portal firmy, instalacji ekranu profilu zarządzania, wyróżniania monitu o hasło.](./media/install-management-profile-macos-1912.PNG)   
5. Na ekranie **Potwierdź zarządzanie urządzeniem** wybierz pozycję **Otwórz aplet Preferencje systemu**.  

    ![Przykład zrzut ekranu przedstawiający ekran Potwierdź zarządzanie urządzeniem, wyróżnij przycisk "Otwórz Preferencje systemu".](./media/confirm-device-management-macos-1912.PNG)  
6. Zostaną otwarte Preferencje systemu Twojego urządzenia. Wybierz pozycję **profil zarządzania** z listy Profile urządzeń, a następnie wybierz pozycję **Zatwierdź** > **zatwierdzić**.  
    ![Przykładowy zrzut ekranu z preferencjami systemowymi, na ekranie profil zarządzania, wyróżnij przycisk "Zatwierdź".](./media/management-profile-approve-macos-1912.PNG)   
1. Wróć do Portal firmy i wybierz **Kontynuuj**.    
2. Organizacja może wymagać aktualizacji ustawień urządzenia. Po zakończeniu aktualizowania ustawień wybierz pozycję **Sprawdź ustawienia**.  

    ![Przykładowy zrzut ekranu przedstawiający Portal firmy, aktualizowanie ekranu ustawień urządzenia, wyróżnienie przycisku "Sprawdź ustawienia".](./media/update-settings-mac-1911.PNG)  
9. Po zakończeniu instalacji wybierz pozycję **gotowe**.  


 ## <a name="troubleshooting-and-feedback"></a>Rozwiązywanie problemów i opinie   

Jeśli wystąpią problemy podczas rejestracji, przejdź do **pomoc** > **Wyślij raport diagnostyczny**, aby zgłosić problem do deweloperów aplikacji firmy Microsoft. Te informacje służą do ulepszania aplikacji. Te informacje będą również pomocne w rozwiązaniu problemu, jeśli osoba odpowiedzialna za pomoc techniczną nie dotrze do nich w celu uzyskania pomocy.  

Po zgłoszeniu problemu do firmy Microsoft można wysłać szczegóły dotyczące środowiska użytkownika do działu pomocy technicznej IT. Pobierz szczegóły wiadomości e-mail Wpisz tekst w treści wiadomości e-mail. Aby znaleźć adres e-mail osoby pomocy technicznej, przejdź do pozycji Portal firmy App > **kontakt**. Lub przejdź do [witryny internetowej Portalu firmy](https://go.microsoft.com/fwlink/?linkid=2010980).  
 

Ponadto Microsoft Intune zespół Portal firmy może poznać Twoją opinię. Przejdź do **pomocy** > **Prześlij opinię**, aby podzielić się swoimi pomysłami i pomysłami.  

## <a name="unverified-profiles"></a>Profile niezweryfikowane  
W przypadku wyświetlania zainstalowanych profilów zarządzania urządzeniami przenośnymi (MDM) dla urządzenia w obszarze **Preferencje systemowe** > **Profile** niektóre profile mogą mieć stan niezweryfikowany. Tak długo, jak w obszarze profilu zarządzania jest pokazywany stan zweryfikowany, nie musisz się martwić.  

Profil zarządzania definiuje połączenia kanału zarządzania urządzeniami przenośnymi. Tak długo, jak profil zarządzania jest zweryfikowany, inne profile dostarczane do maszyny za pośrednictwem tego kanału dziedziczą cechy zabezpieczeń profilu zarządzania.  

## <a name="updating-the-company-portal-app"></a>Aktualizowanie aplikacji Portal firmy

Aktualizowanie aplikacji Portal firmy odbywa się tak samo, jak w przypadku każdej innej aplikacji pakietu Office, za pomocą programu Microsoft AutoUpdate dla systemu macOS. Dowiedz się więcej o [aktualizowaniu aplikacji firmy Microsoft dla systemu macOS](https://support.office.com/article/Check-for-Office-for-Mac-updates-automatically-bfd1e497-c24d-4754-92ab-910a4074d7c1).  

## <a name="next-steps"></a>Następne kroki  
Nadal potrzebujesz pomocy? Skontaktuj się z pomocą techniczną Twojej firmy. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).  


