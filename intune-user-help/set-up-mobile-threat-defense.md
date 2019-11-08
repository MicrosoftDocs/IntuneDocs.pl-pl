---
title: Instalowanie aplikacji Mobile Threat Defense na urządzeniu przenośnym
description: Dowiedz się, jak zainstalować ochronę przed zagrożeniami mobilnymi na urządzeniu przenośnym.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/25/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: ''
searchScope:
- User help
ROBOTS: ''
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7f395a9cedc72a8184cfe3e29d6fcd3117a1473d
ms.sourcegitcommit: 259462591835f3607392aa6b179882dbac830a89
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2019
ms.locfileid: "72980361"
---
# <a name="install-mobile-threat-defense"></a>Instalowanie aplikacji Mobile Threat Defense   

W ramach wymagań dotyczących zabezpieczeń organizacji może być wymagane zainstalowanie aplikacji dostawcy programu Mobile Threat obron (MTD). Ten typ aplikacji wykrywa zagrożenia na urządzeniu, takie jak podejrzane aplikacje, sieci lub luki w zabezpieczeniach systemu operacyjnego, i ostrzega o nich.  

Jeśli nie masz wymaganej aplikacji MTD, będziesz mieć możliwość logowania się do chronionych aplikacji przy użyciu konta służbowego. W tym artykule dowiesz się, [jak zainstalować aplikację MTD](set-up-mobile-threat-defense.md#install-app) , aby uzyskać Odblokowywanie.  

Dostępne są różne aplikacje dostawcy MTD do zainstalowania; Twoja organizacja powiadomi użytkownika o tym, który z nich ma być używany. 


## <a name="information-your-organization-can-see"></a>Informacje, które organizacja może zobaczyć   

Twoja organizacja nie może zobaczyć żadnych danych, takich jak teksty, wiadomości e-mail i obrazy, w aplikacjach osobistych. Aplikacja MTD umożliwia raportowanie informacji o aplikacjach, takich jak nazwa i wersja, w organizacji. Raportowane informacje są zależne od dostawcy MTD używanego przez firmę. Twoja organizacja może zobaczyć:   

* Nazwa aplikacji  
* Identyfikator aplikacji: unikatowa nazwa identyfikująca aplikację w sklepie Google Play.  
* Wersja aplikacji i krótki numer wersji: numery określonej wersji aplikacji.  
* Zbiór aplikacji i rozmiar dynamiczny: ilość miejsca na urządzeniu używanego przez aplikację. 


## <a name="install-app"></a>Zainstaluj aplikację    
Po zalogowaniu się do chronionej aplikacji zostanie automatycznie wyświetlony monit o zainstalowanie aplikacji MTD. Postępuj zgodnie z instrukcjami na ekranie, aby zakończyć instalację. Aby uzyskać dodatkową pomoc, wykonaj kroki opisane w tej sekcji.  
 
Może również zostać wyświetlony monit o zarejestrowanie urządzenia. Rejestracja jest konieczna do potwierdzenia tożsamości i połączenia Twojego konta służbowego z Twoim urządzeniem. Jeśli nie jesteś zarejestrowanym, przed zainstalowaniem aplikacji MTD automatycznie przejdziesz do tej konfiguracji. Po wyświetleniu ekranu **uzyskaj dostęp** można rozpocząć kroki instalacji.  

Aby uzyskać więcej informacji na temat rejestracji urządzeń, zobacz temat [Rejestrowanie urządzenia osobistego w sieci organizacji](https://docs.microsoft.com/azure/active-directory/user-help/user-help-register-device-on-network).  

### <a name="ios-setup"></a>Konfiguracja systemu iOS  

1. Na ekranie **pobieranie dostępu** postępuj zgodnie z instrukcjami, aby zainstalować aplikację MTD, która jest wymagana przez organizację.   
2. Wróć do ekranu **uzyskiwania dostępu** i wybierz pozycję **Otwórz**.  
3. Aplikacja MTD prosi o zezwolenie na otwarcie Microsoft Authenticator. Wybierz pozycję **Open** (Otwórz). 
4. Wybierz swoje konto służbowe, aby się zalogować. 
5. Zaczekaj, aż aplikacja MTD skanuje urządzenie pod kątem zagrożeń bezpieczeństwa. 
6. Wróć do aplikacji szkolnej lub roboczej, do której próbowano uzyskać dostęp. W tym momencie organizacja może monitować o skonfigurowanie innych wymagań dotyczących zabezpieczeń aplikacji, takich jak tworzenie numeru PIN.   
7. Powinieneś mieć teraz dostęp do aplikacji. Jeśli nadal masz zablokowany:  
    * Na ekranie **pobieranie dostępu** wybierz pozycję **Sprawdź**ponownie.  
    * Przejdź do aplikacji MTD i Sprawdź istniejące zagrożenia. Wykonaj zalecane kroki w celu rozwiązania problemu i odzyskania dostępu.    

### <a name="android-setup"></a>Konfiguracja systemu Android 

1. Na ekranie **pobieranie dostępu** postępuj zgodnie z instrukcjami, aby zainstalować aplikację MTD, która jest wymagana przez organizację.  
2. Wróć do ekranu **uzyskiwania dostępu** i wybierz pozycję **Otwórz**.  
3. Aplikacja MTD prosi o zezwolenie na dostęp do określonych obszarów urządzenia. Aby ta aplikacja działała prawidłowo, musisz **zezwolić** na dostęp do kontaktów. Żądane uprawnienia będą się różnić w zależności od dostawców MTD.  
4. Wybierz swoje konto służbowe, aby się zalogować.  
5. Zaczekaj, aż aplikacja MTD skanuje urządzenie pod kątem zagrożeń bezpieczeństwa.  
6. Wróć do aplikacji szkolnej lub roboczej, do której próbowano uzyskać dostęp. W tym momencie organizacja może monitować o skonfigurowanie innych wymagań dotyczących zabezpieczeń aplikacji, takich jak tworzenie numeru PIN.  
7. Powinieneś mieć teraz dostęp do aplikacji. Jeśli nadal masz zablokowany:  
    * Na ekranie **pobieranie dostępu** wybierz pozycję **Sprawdź**ponownie.  
    * Przejdź do aplikacji MTD i Sprawdź istniejące zagrożenia. Wykonaj zalecane kroki w celu rozwiązania problemu i odzyskania dostępu.  

### <a name="installation-failed"></a>Niepowodzenie instalacji  

Jeśli instalacja nie powiedzie się, skontaktuj się z osobą odpowiedzialną za pomoc techniczną IT. Przejdź do [witryny internetowej Portalu firmy](https://go.microsoft.com/fwlink/?linkid=2010980), w której możesz znaleźć informacje kontaktowe organizacji.  

Możesz również wysłać dzienniki aplikacji do osoby odpowiedzialnej za pomoc techniczną IT, aby zapewnić im więcej kontekstu instalacji.  
* Użytkownicy systemu Android: [przekazywanie dzienników i wysyłanie ich pocztą e-mail](https://docs.microsoft.com/intune-user-help/send-logs-to-your-it-admin-by-email-android) z Portal firmy.   

* Użytkownicy urządzeń z systemem iOS: [pobieranie i wysyłanie dzienników](https://docs.microsoft.com/intune/apps/manage-microsoft-edge#use-microsoft-edge-on-ios-to-access-managed-app-logs) z przeglądarki Microsoft Edge dla systemu iOS.  

## <a name="resolve-a-threat"></a>Rozwiązywanie problemu zagrożenia  
Jeśli zagrożenie przekroczy określony poziom zagrożenia w organizacji, organizacja będzie:  
   
* Blokuj dostęp: uniemożliwia korzystanie z aplikacji chronionych przez organizację podczas logowania do konta służbowego.  
* Wyczyść dane: usuwa dane służbowe z jednej lub kilku aplikacji chronionych w organizacji.  

Aby rozwiązać zagrożenie i odzyskać dostęp, Otwórz aplikację MTD na urządzeniu. Zapoznaj się z podanymi informacjami, aby dowiedzieć się, jak zagrożenie może wpłynąć na Twoje urządzenie i jak rozwiązać ten problem. Po wykonaniu kroków w celu rozwiązania problemu Wróć do aplikacji MTD i zainicjuj nowe skanowanie. Odzyskanie dostępu do organizacji może potrwać kilka minut.  

## <a name="next-steps"></a>Następne kroki  

Nadal potrzebujesz pomocy? Skontaktuj się z pomocą techniczną Twojej firmy. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).

