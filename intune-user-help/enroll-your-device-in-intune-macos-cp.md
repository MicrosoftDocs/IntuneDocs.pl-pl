---
title: Rejestrowanie komputera Mac przy użyciu Intune — Portal firmy | Microsoft Docs
description: Dowiedz się, jak zarejestrować komputer Mac w usłudze Intune za pomocą aplikacji Portal firmy.
keywords: Mac OS X, macOS, OS X
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 11/14/2019
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
ms.collection: M365-identity-device-management
ms.openlocfilehash: ba285fc9de58b3fb739a16722e0e05e36e840e87
ms.sourcegitcommit: 76ae5aea5deee7a590e24c3b2bb52f88125943e5
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2019
ms.locfileid: "74098149"
---
# <a name="enroll-your-macos-device-using-the-company-portal-app"></a>Rejestrowanie urządzenia z macOS za pomocą aplikacji Portal firmy  

Zarejestruj urządzenie z systemem macOS przy użyciu aplikacji Portal firmy w usłudze Intune, aby uzyskać bezpieczny dostęp do służbowej poczty e-mail, plików i aplikacji.

Organizacje zwykle wymagają zarejestrowania urządzenia, aby można było uzyskać dostęp do danych własnościowych. Zarejestrowane urządzenie staje się urządzeniem *zarządzanym*. Organizacja może przypisywać zasady i aplikacje do urządzenia za pośrednictwem dostawcy zarządzania urządzeniami przenośnymi (MDM), takiego jak usługa Intune. Aby uzyskać ciągły dostęp do danych służbowych na urządzeniu, musisz skonfigurować urządzenie, aby dopasować je do ustawień zasad w organizacji.  

W tym artykule opisano, jak aplikacja Portal firmy dla systemu macOS umożliwia rejestrowanie, konfigurowanie i utrzymywanie urządzenia zgodnie z wymaganiami organizacji.  


## <a name="what-to-expect-from-the-company-portal-app"></a>Czego można oczekiwać od aplikacji Portal firmy

Podczas konfiguracji początkowej aplikacja Portal firmy wymaga zalogowania się i uwierzytelnienia w organizacji. Następnie Portal firmy informuje o ustawieniach urządzenia, które należy skonfigurować, aby spełniały wymagania organizacji. Na przykład organizacje często ustawiają wymagania dotyczące minimalnej i maksymalnej długości haseł, które trzeba spełnić.    

Po zarejestrowaniu urządzenia Portal firmy zawsze upewnij się, że urządzenie jest chronione zgodnie z wymaganiami organizacji. Na przykład jeśli zainstalujesz aplikację z niezaufanego źródła, Portal firmy będzie alertować i może ograniczyć dostęp do zasobów organizacji. Zasady ochrony aplikacji, takie jak ta, są wspólne. W celu odzyskania dostępu prawdopodobnie trzeba będzie odinstalować niezaufaną aplikację. 

Jeśli po zarejestrowaniu organizacja wymusi nowe wymagania dotyczące zabezpieczeń, np. uwierzytelnianie wieloskładnikowe, Portal firmy powiadomi użytkownika. Będziesz mieć szansę na dostosowanie ustawień, aby nadal kontynuować pracę z urządzenia.  

Aby uzyskać więcej informacji o rejestracji, zobacz [Co się stanie, jeśli zainstaluję aplikację Portal firmy i zarejestruję swoje urządzenie?](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-macos.md).  

## <a name="get-your-macos-device-managed"></a>Zapoznaj się z urządzeniem macOS zarządzanym  
Wykonaj poniższe kroki, aby zarejestrować urządzenie z programem macOS w organizacji. Na urządzeniu musi być uruchomiony program macOS 10,12 lub nowszy.   

> [!NOTE]
> W trakcie tego procesu może zostać wyświetlony monit o zezwolenie Portal firmy na używanie poufnych informacji przechowywanych w łańcuchu kluczy. Te monity są częścią zabezpieczeń firmy Apple. Po wyświetleniu monitu wpisz hasło do łańcucha kluczy logowania i wybierz pozycję **zawsze Zezwalaj**. Po naciśnięciu klawisza **Enter** lub **Return** na klawiaturze zamiast tego zostanie wyświetlony monit " **Zezwalaj**", co może spowodować wyświetlenie dodatkowych monitów.  

### <a name="install-company-portal-app"></a>Instalowanie aplikacji Portal firmy  
1. Przejdź do [strony rejestracja mojego komputera Mac](https://go.microsoft.com/fwlink/?linkid=853070).  
2. Plik Instalatora Portal firmy. pkg zostanie pobrany. Otwórz instalatora i wykonaj kroki opisane w sekcji. 
3. Wyrażanie zgody na umowę licencyjną na oprogramowanie. 
4. Wprowadź hasło urządzenia lub zarejestrowany odcisk palca, aby zainstalować oprogramowanie.  
5. Otwórz Portal firmy. 

> [!IMPORTANT]
> Program Microsoft AutoUpdate może zostać otwarty w celu zaktualizowania oprogramowania firmy Microsoft. Po zainstalowaniu wszystkich aktualizacji Otwórz aplikację Portal firmy. Aby uzyskać najlepsze czynności konfiguracyjne, należy zainstalować najnowsze wersje programu Microsoft AutoUpdate i Portal firmy.  


### <a name="enroll-your-mac"></a>Rejestrowanie komputera Mac  


1. Zaloguj się do Portalu firmy przy użyciu konta służbowego.  
2. Gdy aplikacja zostanie otwarta, wybierz pozycję **Rozpocznij**.  
3. Zapoznaj się z informacjami o tym [, co Twoja organizacja może zobaczyć](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md) na Twoim zarejestrowanym urządzeniu. Następnie wybierz pozycję **Kontynuuj**.  
4. Na ekranie **Instalowanie profilu zarządzania** wybierz pozycję **Pobierz profil**.   

    ![Przykładowy zrzut ekranu Portal firmy, zainstaluj profil zarządzania ekranu, wyróżnij przycisk "Pobierz profil".](./media/install-mgmt-profile-mac-1911.PNG)   
5. Zostaną otwarte Preferencje systemu Twojego urządzenia. Wybierz pozycję **Zainstaluj** , a następnie ponownie wybierz pozycję **Zainstaluj** . Jeśli zostanie wyświetlony monit, wprowadź hasło urządzenia.  

    ![Przykład zrzutu ekranu preferencji systemu macOS, monitu instalacji i wyróżnienia przycisku "Zainstaluj".](./media/system-preference-install-1911.PNG)  
6. Po zainstalowaniu profilu zostanie on wyświetlony na liście Profile w obszarze **profil zarządzania.**  

   ![Przykładowy zrzut ekranu przedstawiający Preferencje systemu macOS, ekran profile, wyróżnienie zainstalowanego profilu zarządzania.](./media/system-preference-verify-1911.PNG)   
7. Wróć do Portal firmy.   
8. Organizacja może wymagać aktualizacji ustawień urządzenia. Po zakończeniu aktualizowania ustawień wybierz pozycję **Sprawdź ustawienia**.  

    ![Przykładowy zrzut ekranu przedstawiający Portal firmy, aktualizowanie ekranu ustawień urządzenia, wyróżnienie przycisku "Sprawdź ustawienia".](./media/update-settings-mac-1911.PNG)  
9. Po zakończeniu instalacji wybierz pozycję **gotowe**.  


 ## <a name="troubleshooting-and-feedback"></a>Rozwiązywanie problemów i opinie   

Jeśli wystąpią problemy podczas rejestracji, przejdź do **pomocy** > **wysłać raport diagnostyczny** , aby zgłosić problem do deweloperów aplikacji firmy Microsoft. Te informacje służą do ulepszania aplikacji. Te informacje będą również pomocne w rozwiązaniu problemu, jeśli osoba odpowiedzialna za pomoc techniczną nie dotrze do nich w celu uzyskania pomocy.  

Po zgłoszeniu problemu do firmy Microsoft można wysłać szczegóły dotyczące środowiska użytkownika do działu pomocy technicznej IT. Wybierz pozycję **szczegóły wiadomości e-mail**. Wpisz tekst w treści wiadomości e-mail. Aby znaleźć adres e-mail osoby pomocy technicznej, przejdź do pozycji Portal firmy App > **Contact**. Lub sprawdź [witrynę sieci web Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).  
 

Ponadto Microsoft Intune zespół Portal firmy może poznać Twoją opinię. Przejdź do **pomocy** , > **Prześlij opinię** , aby podzielić się swoimi pomysłami i pomysłami.  

## <a name="unverified-profiles"></a>Profile niezweryfikowane  
W przypadku wyświetlania zainstalowanych profilów zarządzania urządzeniami przenośnymi (MDM) dla urządzenia w obszarze **Preferencje systemowe** > **Profile** niektóre profile mogą mieć stan niezweryfikowany. Tak długo, jak w obszarze profilu zarządzania jest pokazywany stan zweryfikowany, nie musisz się martwić.  

Profil zarządzania definiuje połączenia kanału zarządzania urządzeniami przenośnymi. Tak długo, jak profil zarządzania jest zweryfikowany, inne profile dostarczane do maszyny za pośrednictwem tego kanału dziedziczą cechy zabezpieczeń profilu zarządzania.  

## <a name="updating-the-company-portal-app"></a>Aktualizowanie aplikacji Portal firmy

Aktualizowanie aplikacji Portal firmy odbywa się tak samo, jak w przypadku każdej innej aplikacji pakietu Office, za pomocą programu Microsoft AutoUpdate dla systemu macOS. Dowiedz się więcej o [aktualizowaniu aplikacji firmy Microsoft dla systemu macOS](https://support.office.com/article/Check-for-Office-for-Mac-updates-automatically-bfd1e497-c24d-4754-92ab-910a4074d7c1).  

## <a name="next-steps"></a>Następne kroki  
Nadal potrzebujesz pomocy? Skontaktuj się z pomocą techniczną Twojej firmy. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).  


