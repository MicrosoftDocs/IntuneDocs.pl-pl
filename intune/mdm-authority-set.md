---
title: Ustawianie źródła zarządzania urządzeniem przenośnym
titlesuffix: Microsoft Intune
description: Konfigurowanie urzędu zarządzania urządzeniami przenośnymi w usłudze Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4c1902e319a862c9ffcda5068753f917bf8f4c3f
ms.sourcegitcommit: ada99fefe9a612ed753420116f8c801ac4bf0934
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/19/2018
ms.locfileid: "36232922"
---
# <a name="set-the-mobile-device-management-authority"></a>Ustawianie źródła zarządzania urządzeniem przenośnym

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ustawienie urzędu zarządzania urządzeniami przenośnymi (MDM) określa metodę zarządzania urządzeniami. Jako administrator systemów informatycznych, musisz ustawić urząd MDM, aby użytkownicy mogli zarejestrować urządzenia do zarządzania.

Możliwe są następujące konfiguracje:

- **Autonomiczna usługa Intune** — zarządzanie tylko w chmurze konfigurowane przy użyciu witryny Azure Portal. Ta konfiguracja zawiera pełny zestaw funkcji oferowanych przez usługę Intune. [Ustaw urząd MDM w konsoli usługi Intune](#set-mdm-authority-to-intune).

- **Hybrydowa usługa Intune** — integracja rozwiązania usługi Intune w chmurze z programem System Center Configuration Manager. Konfigurowanie usługi Intune odbywa się przy użyciu konsoli programu Configuration Manager. [Ustaw urząd MDM w programie Configuration Manager](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-intune-subscription).

- **Zarządzanie urządzeniami przenośnymi w usłudze Office 365** — integracja usługi Office 365 z rozwiązaniem usługi Intune w chmurze. Konfigurowanie usługi Intune odbywa się przy użyciu centrum administracyjnego usługi Office 365. Ta konfiguracja zawiera podzbiór możliwości dostępnych w ramach autonomicznej usługi Intune. Ustaw urząd MDM przy użyciu centrum administracyjnego usługi Office 365.

> [!IMPORTANT]
> W programie Configuration Manager w wersji 1610 lub nowszej i w usłudze Microsoft Intune w wersji 1705 można zmienić urząd certyfikacji MDM bez konieczności kontaktowania się Pomocą techniczną firmy Microsoft oraz wyrejestrowywania i ponownego rejestrowania istniejących urządzeń zarządzanych. Szczegółowe informacje można znaleźć w sekcji [Co należy zrobić, jeśli wybrano błędne ustawienie urzędu MDM](/intune-classic/deploy-use/prerequisites-for-enrollment#what-to-do-if-you-choose-the-wrong-mdm-authority-setting).

## <a name="set-mdm-authority-to-intune"></a>Ustawianie urzędu MDM na usługę Intune

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. Wybierz pomarańczowy transparent, aby otworzyć ustawienie **Urząd zarządzania urządzeniami przenośnymi**.
4. W obszarze **Urząd zarządzania urządzeniami przenośnymi** wybierz swój urząd MDM spośród następujących opcji:
   - **Urząd MDM w usłudze Intune**
   - **Urząd MDM w programie Configuration Manager**
   - **Brak**

   ![Zrzut ekranu usługi Intune przeznaczonego do ustawiania urzędu zarządzania urządzeniami przenośnymi](media/set-mdm-auth.png)

   Zostanie wyświetlony komunikat z potwierdzeniem pomyślnego ustawienia urzędu certyfikacji MDM na usługę Intune.

### <a name="workflow-of-intune-administration-ui"></a>Przepływ pracy interfejsu użytkownika administrowania usługą Intune
Gdy zarządzanie urządzeniami firmy Apple i urządzeniami z systemem Android jest włączone, usługa Intune wysyła informacje o urządzeniu i użytkowniku w celu integracji z usługami innych firm i zarządzania urządzeniami.

Dodanie zgody na udostępnianie danych ma miejsce:
- Podczas włączania programu Android for Work.
- Podczas włączania i przekazywania certyfikatów wypychania MDM firmy Apple.
- Podczas włączania dowolnych usługi firmy Apple takich jak Device Enrollment Program, School Manager czy Volume Purchasing Program (program zakupów zbiorczych).

W każdym przypadku zgoda ściśle dotyczy uruchamiania usługi zarządzania urządzeniami przenośnymi. Może to być na przykład potwierdzenie, że administrator IT zezwolił na rejestrację urządzeń firmy Google lub Apple. Dokumentacja opisująca, jakie informacje są udostępniane po wprowadzeniu nowych przepływów pracy, jest dostępna w następujących lokalizacjach:
- [Dane wysyłane przez usługę Intune do firmy Google](https://aka.ms/Data-intune-sends-to-google)
- [Dane wysyłane przez usługę Intune do firmy Apple](https://aka.ms/data-intune-sends-to-apple)

## <a name="key-considerations"></a>Zagadnienia dotyczące kluczy
Po zmianie na nowy urząd MDM prawdopodobnie wystąpi czas przejścia (maksymalnie osiem godzin), zanim urządzenie zostanie zaewidencjonowane i zsynchronizowane z usługą. Wymagane jest skonfigurowanie ustawień w nowym urzędzie MDM (rozwiązanie hybrydowe), aby upewnić się, że zarejestrowane urządzenia będą nadal zarządzane i chronione po zmianie. 
- Urządzenia muszą połączyć się z usługą po zmianie, aby ustawienia z nowego urzędu MDM (autonomicznej usługi Intune) zastąpiły istniejące ustawienia na urządzeniu.
- Po zmianie urzędu MDM niektóre podstawowe ustawienia (takie jak profile) z poprzedniego urzędu MDM (autonomicznej usługi Intune) pozostaną na urządzeniu przez maksymalnie siedem dni lub dopóki urządzenie nie połączy się z usługą po raz pierwszy. Zaleca się jak najszybsze skonfigurowanie aplikacji i ustawień (zasad, profilów, aplikacji itd.) w nowym urzędzie MDM (rozwiązanie hybrydowe) i wdrożenie ustawienia w grupach użytkowników, które zawierają użytkowników posiadających istniejące zarejestrowane urządzenia. Kiedy tylko urządzenie połączy się z usługą po zmianie urzędu MDM, odbierze nowe ustawienia z nowego urzędu MDM, co zapobiegnie przerwom w zarządzaniu i ochronie.
- Jeśli te same kategorie urządzeń istnieją zarówno w usłudze Intune, jak i w programie Configuration Manager, żadne przypisania kategorii urządzeń dla urządzeń nie są przenoszone po przejściu do nowego urzędu MDM. Aby nadal używać kategorii urządzeń, należy zmigrowane urządzenia ręcznie dodać do odpowiedniej kolekcji po zmianie urzędu MDM i wyświetleniu urządzeń w konsoli programu Configuration Manager.
- Urządzenia, które nie mają skojarzonych użytkowników (zazwyczaj jeśli masz urządzenia z systemem iOS w programie Device Enrollment Program lub scenariusze rejestracji zbiorczej) nie są migrowane do nowego urzędu MDM. W przypadku tych urządzeń musisz skontaktować się z działem pomocy technicznej, aby przenieść je do nowego urzędu MDM.

## <a name="prepare-to-change-the-mdm-authority-to-configuration-manager"></a>Przygotowanie do zmiany urzędu MDM na program Configuration Manager

Przejrzyj następujące informacje w celu przygotowania do zmiany urzędu MDM:
- Musisz mieć program Configuration Manager w wersji 1610 lub nowszej, aby opcja zmiany urzędu MDM była dostępna.
- Połączenie się urządzenia z usługą może potrwać do ośmiu godzin po zmianie urzędu MDM.
- Utwórz kolekcję użytkowników programu Configuration Manager zawierającą wszystkich użytkowników obecnie zarządzanych przez autonomiczną usługę Intune, która będzie używana podczas konfigurowania subskrypcji usługi Intune w konsoli programu Configuration Manager. Ułatwia to zapewnienie, że użytkownik i jego urządzenia będą mieć przypisaną licencję programu Configuration Manager i będą zarządzani w środowisku hybrydowym po zastosowaniu zmiany urzędu MDM.
- Upewnij się, że administrator IT również należy do tej kolekcji użytkowników.  
- Przed zmianą urząd MDM będzie wyświetlany jako **Ustaw na usługę Microsoft Intune** (autonomiczną) w konsoli administracyjnej usługi Intune.
- Przed zmianą urzędu MDM urząd MDM powinien być wyświetlany jako **Ustaw na usługę Microsoft Intune** (autonomiczny dzierżawca) w konsoli administracyjnej usługi Microsoft Intune.
    > [!NOTE]    
    > Jeśli Twój urząd MDM wyświetla się jako **Zarządzane przez usługę Intune i Office 365**, urządzenia MDM zarządzane przez usługę Office 365 nie będą już zarządzane, gdy zmienisz swój urząd MDM na **program Configuration Manager** (rozwiązanie hybrydowe). Zalecamy przypisanie tym użytkownikom licencji usługi Intune lub pakietu Enterprise Mobility Suite, zanim zmienisz urząd MDM.   

- W [konsoli administracyjnej usługi Microsoft Intune](http://manage.microsoft.com) usuń rolę Menedżer rejestracji urządzeń. Aby uzyskać szczegółowe informacje, zobacz [Usuwanie menedżera rejestracji urządzeń z usługi Intune](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune#delete-a-device-enrollment-manager-from-intune).
- Wyłącz wszystkie skonfigurowane mapowania grupy urządzeń. Aby uzyskać szczegółowe informacje, zobacz [Kategoryzowanie urządzeń za pomocą mapowania grup urządzeń w usłudze Microsoft Intune](/intune-classic/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune).
- Zmiana urzędu MDM powinna przebiec bez zauważalnego wpływu na użytkowników końcowych. Można jednak zakomunikować tę zmianę użytkownikom, aby upewnić się, że ich urządzenia są włączone i połączą się z usługą wkrótce po zmianie. Dzięki temu najwięcej urządzeń połączy się i zarejestruje w usłudze za pomocą nowego urzędu najszybciej, jak to możliwe.
- Jeśli przed zmianą urzędu MDM używasz autonomicznej usługi Intune do zarządzania urządzeniami z systemem iOS, musisz się upewnić, że ten sam certyfikat usługi Apple Push Notification service (APNs), który był wcześniej używany w usłudze Intune, zostanie odnowiony i użyty do ponownego skonfigurowania dzierżawy w programie Configuration Manager (rozwiązaniu hybrydowym).    

    > [!IMPORTANT]  
    > Jeśli dla rozwiązania hybrydowego użyty zostanie inny certyfikat usługi APNs, wszystkie wcześniej zarejestrowane urządzenia z systemem iOS staną się niezarejestrowane i będą musiały przejść przez proces ponownej rejestracji. Przed wykonaniem zmiany urzędu MDM upewnij się, że dokładnie wiesz, który certyfikat usługi APNs był używany do zarządzania urządzeniami z systemem iOS w usłudze Intune. Znajdź ten sam certyfikat wyświetlany na liście w portalu Apple Push Certificates (https://identity.apple.com) i upewnij się, że użytkownik, którego identyfikator Apple ID został użyty do utworzenia oryginalnego certyfikatu usługi APNs, jest zidentyfikowany i dostępny na potrzeby odnowienia tego certyfikatu usługi APNs w ramach zmiany na nowy urząd MDM.

## <a name="change-the-mdm-authority-to-configuration-manager"></a>Zmiana urzędu MDM na program Configuration Manager

1. W konsoli programu Configuration Manager przejdź do pozycji **Administracja** &gt; **Przegląd** &gt; **Usługi w chmurze** &gt; **Subskrypcje usługi Microsoft Intune** i wybierz subskrypcję usługi Intune.
2. Zaloguj się do dzierżawy usługi Intune, której pierwotnie użyto podczas ustawiania urzędu MDM w usłudze Intune, a następnie kliknij przycisk **Dalej**.
3. Wybierz pozycję **Zmień moje źródło zarządzania MDM na program Configuration Manager** i kliknij przycisk **Dalej**.
4. Wybierz kolekcję użytkowników tak, aby zawierała wszystkich użytkowników, którzy będą w dalszym ciągu zarządzani przez nowy hybrydowy urząd MDM.
5. Kliknij przycisk **Dalej** i ukończ pracę kreatora. Urząd MDM został zmieniony na **program Configuration Manager**.
6. Zaloguj się w [konsoli administracyjnej usługi Microsoft Intune](http://manage.microsoft.com) przy użyciu tej samej dzierżawy usługi Intune i upewnij się, że urząd MDM został zmieniony na opcję **Ustaw Menedżera konfiguracji**.
7. Po zmianie urzędu MDM na program Configuration Manager możesz skonfigurować [rejestrowanie dla systemu iOS](https://docs.microsoft.com/en-us/sccm/mdm/deploy-use/enroll-hybrid-ios-mac) i [rejestrowanie dla systemu Android](https://docs.microsoft.com/en-us/sccm/mdm/deploy-use/enroll-hybrid-android).
8. W konsoli programu Configuration Manager skonfiguruj i wdróż nowe ustawienia i aplikacje z nowego urzędu MDM (rozwiązanie hybrydowe).

Kiedy następnym razem urządzenia połączą się z usługą, zsynchronizuje ona i odbierze nowe ustawienia z nowego urzędu MDM.

## <a name="change-mdm-authority-to-office-365"></a>Zmiana urzędu MDM na usługę Office 365

Aby poza istniejącą usługą Intune aktywować zarządzanie urządzeniami mobilnymi usługi Office 365, przejdź na stronę [https://protection.office.com](https://protection.office.com) i wybierz pozycję **Ochrona przed utratą danych** > **Zasady zabezpieczeń urządzeń** > **Wyświetl listę urządzeń zarządzanych** > **Zacznijmy**.

Aby uzyskać więcej informacji, zobacz [Konfigurowanie zarządzania urządzeniami przenośnymi (MDM) w usłudze Office 365](https://support.office.com/en-us/article/Set-up-Mobile-Device-Management-MDM-in-Office-365-dd892318-bc44-4eb1-af00-9db5430be3cd).

Jeśli chcesz, aby użytkownicy końcowi byli zarządzani tylko przez usługę zarządzania urządzeniami mobilnymi w usłudze Office 365, to po aktywowaniu tej usługi usuń wszystkie licencje przypisane do usługi Intune i/lub pakietu EMS.

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Czyszczenie urządzenia przenośnego po wygaśnięciu certyfikatu MDM

Certyfikat MDM jest odnawiany automatycznie, gdy urządzenia przenośne komunikują się z usługą Intune. W przypadku wyczyszczenia urządzeń przenośnych lub jeśli przez pewien czas nie komunikują się one z usługą Intune, certyfikat MDM nie zostanie odnowiony. Urządzenie zostanie usunięte z portalu Azure 180 dni po wygaśnięciu certyfikatu MDM.

## <a name="remove-mdm-authority"></a>Usuwanie urzędu MDM

Urzędu MDM nie można zmienić z powrotem na Nieznany. Urząd MDM jest używany przez serwery firmy Microsoft do określenia serwera, któremu podlegają zarejestrowane urządzenia (ConfigMGR, Azure Intune, Office 365 MDM).

## <a name="what-to-expect-after-changing-the-mdm-authority"></a>Czego można się spodziewać po zmianie urzędu MDM

- Kiedy usługa Intune wykryje zmianę urzędu MDM dzierżawy, wysyła komunikat z powiadomieniem do wszystkich zarejestrowanych urządzeń w celu ich zameldowania i przeprowadzenia synchronizacji z usługą (jest to wykonywane poza zaplanowanym regularnym meldowaniem). W związku z tym po zmianie urzędu MDM dla dzierżawy z autonomicznej usługi Intune na rozwiązanie hybrydowe wszystkie urządzenia, które są włączone i online, połączą się z usługą, otrzymają nowy urząd MDM i będą zarządzane przez rozwiązanie hybrydowe. Nie ma żadnych zakłóceń w zarządzaniu tymi urządzeniami i ich ochronie.
- Nawet w przypadku urządzeń, które są włączone i w trybie online podczas zmiany urzędu MDM (lub wkrótce po niej), nastąpi opóźnienie do ośmiu godzin (w zależności od czasu następnego zaplanowanego regularnego ewidencjonowania), zanim urządzenia zostaną zarejestrowane w usłudze z nowym urzędem MDM.    

  > [!IMPORTANT]    
  > W czasie między zmianą urzędu MDM a przekazaniem odnowionego certyfikatu usługi APNs do nowego urzędu rejestracje nowych urządzeń i meldowanie urządzeń z systemem iOS zakończy się niepowodzeniem. Dlatego ważne jest przejrzenie i przekazanie certyfikatu usługi APNs do nowego urzędu jak najszybciej po zmianie urzędu MDM.

- Użytkownicy mogą szybko zmienić nowy urząd MDM, ręcznie uruchamiając ewidencjonowanie z poziomu urządzenia do usługi. Mogą to łatwo zrobić, używając aplikacji Portal firmy i inicjując sprawdzenie zgodności urządzenia.
- Aby sprawdzić, czy wszystko działa prawidłowo po zaewidencjonowaniu urządzeń i zsynchronizowaniu ich z usługą po zmianie urzędu MDM, wyszukaj urządzenia w konsoli programu Configuration Manager. Urządzenia, które wcześniej były zarządzane przez usługę Intune, są teraz wyświetlane jako urządzenia zarządzane w konsoli programu Configuration Manager.    
- Istnieje okres przejściowy, gdy urządzenie jest w trybie offline podczas zmiany urzędu MDM, do czasu zaewidencjonowania tego urządzenia w usłudze. Aby zagwarantować, że urządzenie pozostanie chronione i w pełni funkcjonalne w tym okresie przejściowym, poniższe profile pozostaną na urządzeniu przez siedem dni (lub dopóki urządzenie nie połączy się z nowym urzędem MDM i nie odbierze nowych ustawień, które zastąpią istniejące):
    - Profil poczty e-mail
    - Profil sieci VPN
    - Profil certyfikatu
    - Profil sieci Wi-Fi
    - Profile konfiguracji
- Po zmianie na nowy urząd MDM może upłynąć tydzień, zanim dane zgodności w konsoli administracyjnej usługi Microsoft Intune będą dokładnie raportowane. Jednak stany zgodności w usłudze Azure Active Directory i na urządzeniu będą właściwe, a więc urządzenie będzie nadal chronione.
- Upewnij się, że nowe ustawienia używane do zastąpienia istniejących ustawień mają taką samą nazwę jak poprzednie, aby zagwarantować, że stare ustawienia zostaną zastąpione. W przeciwnym razie na urządzeniach mogą wystąpić nadmiarowe profile i zasady.    

  > [!TIP]    
  > Najlepszym rozwiązaniem jest utworzenie wszystkich ustawień zarządzania i konfiguracji, a także wdrożeń, zaraz po zakończeniu zmiany urzędu MDM. Dzięki temu urządzenia są na pewno chronione i aktywnie zarządzane w okresie przejściowym.

-  Po zmianie urzędu MDM wykonaj następujące kroki, aby sprawdzić, czy nowe urządzenia zostały pomyślnie zarejestrowane w nowym urzędzie:   
    - Rejestrowanie nowego urządzenia
    - Upewnij się, że nowo zarejestrowane urządzenie jest wyświetlane w konsoli programu Configuration Manager.
    - Za pomocą konsoli administracyjnej wykonaj akcję, na przykład zdalne blokowanie, na urządzeniu. Jeśli wykonanie akcji zakończy się powodzeniem, urządzenie jest zarządzane przez nowy urząd MDM.
- Jeśli masz problemy z określonymi urządzeniami, musisz jak najszybciej wyrejestrować i zarejestrować ponownie urządzenia, aby połączyć je z nowym urzędem certyfikacji i zarządzać nimi.

## <a name="next-steps"></a>Następne kroki

Po ustawieniu urzędu MDM można rozpocząć [rejestrowanie urządzeń](device-enrollment.md).