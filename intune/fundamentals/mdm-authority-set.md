---
title: Ustawianie źródła zarządzania urządzeniem przenośnym
titleSuffix: Microsoft Intune
description: Konfigurowanie urzędu zarządzania urządzeniami przenośnymi w usłudze Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: damionw
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 19d02694ab5e53dc43e0861c6a427a044bf50648
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72502638"
---
# <a name="set-the-mobile-device-management-authority"></a>Ustawianie źródła zarządzania urządzeniem przenośnym

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Ustawienie urzędu zarządzania urządzeniami przenośnymi (MDM) określa metodę zarządzania urządzeniami. Jako administrator systemów informatycznych, musisz ustawić urząd MDM, aby użytkownicy mogli zarejestrować urządzenia do zarządzania.

Możliwe są następujące konfiguracje:

- **Autonomiczna usługa Intune** — zarządzanie tylko w chmurze konfigurowane przy użyciu witryny Azure Portal. Ta konfiguracja zawiera pełny zestaw funkcji oferowanych przez usługę Intune. [Ustaw urząd MDM w konsoli usługi Intune](#set-mdm-authority-to-intune).

- **Współzarządzanie usługą Intune** — integracja rozwiązania usługi Intune w chmurze z programem System Center Configuration Manager dla urządzeń z systemem Windows 10. Konfigurowanie usługi Intune odbywa się przy użyciu konsoli programu Configuration Manager. [Konfigurowanie automatycznej rejestracji urządzeń w usłudze Intune](https://docs.microsoft.com/sccm/comanage/tutorial-co-manage-clients#configure-auto-enrollment-of-devices-to-intune). 

    > [!Important]
    >Funkcja dołączania nowych klientów hybrydowego rozwiązania MDM jest przestarzała. Aby uzyskać więcej informacji, zobacz wpis w blogu [Move from Hybrid Mobile Device Management to Intune on Azure](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Move-from-Hybrid-Mobile-Device-Management-to-Intune-on-Azure/ba-p/280150) (Przechodzenie z hybrydowego zarządzania urządzeniami przenośnymi do usługi Intune na platformie Azure).

- **Zarządzanie urządzeniami przenośnymi w usłudze Office 365** — integracja usługi Office 365 z rozwiązaniem usługi Intune w chmurze. Konfigurowanie usługi Intune odbywa się przy użyciu centrum administracyjnego platformy Microsoft 365. Ta konfiguracja zawiera podzbiór możliwości dostępnych w ramach autonomicznej usługi Intune. Ustaw urząd MDM przy użyciu centrum administracyjnego platformy Microsoft 365.

- **Współistnienie z MDM w pakiecie Office 365** Możesz aktywować u dzierżawcy i stosować zarówno zarządzanie urządzeniami mobilnymi w pakiecie Office 365, jak i usługę Intune. Ponadto dla każdego użytkownika jako urząd zarządzający w pakiecie Office 365 możesz ustawić MDM lub Intune. W ten sposób określisz, która z tych usług będzie używana do zarządzania urządzeniami przenośnymi użytkowników. Urząd zarządzający użytkownika jest definiowany na podstawie przypisanej do niego licencji. Aby uzyskać więcej informacji, zobacz [Współistnienie Microsoft Intune z MDM w pakiecie Office 365](https://blogs.technet.microsoft.com/configmgrdogs/2016/01/04/microsoft-intune-co-existence-with-mdm-for-office-365).

## <a name="set-mdm-authority-to-intune"></a>Ustawianie urzędu MDM na usługę Intune

Jeśli jeszcze nie ustawiono urzędu MDM, wykonaj poniższe kroki. Aby zastąpić rozwiązanie SCCM, zobacz [Migrowanie użytkowników i urządzeń hybrydowego zarządzania urządzeniami przenośnymi do autonomicznej usługi Intune](https://docs.microsoft.com/sccm/mdm/deploy-use/migrate-hybridmdm-to-intunesa).

1. Wybierz pomarańczowy baner w obszarze usługi [Intune w portalu Azure](https://aka.ms/intuneportal), aby otworzyć ustawienia **urzędu zarządzania urządzeniami przenośnymi**. Pomarańczowy baner jest wyświetlany tylko wtedy, gdy nie ustawiono jeszcze urzędu MDM.
2. W obszarze **Urząd zarządzania urządzeniami przenośnymi** wybierz swój urząd MDM spośród następujących opcji:
   - **Urząd MDM w usłudze Intune**
   - **Brak**

   ![Zrzut ekranu usługi Intune przeznaczonego do ustawiania urzędu zarządzania urządzeniami przenośnymi](./media/mdm-authority-set/set-mdm-auth.png)

   Zostanie wyświetlony komunikat z potwierdzeniem pomyślnego ustawienia urzędu certyfikacji MDM na usługę Intune.

### <a name="workflow-of-intune-administration-ui"></a>Przepływ pracy interfejsu użytkownika administrowania usługą Intune
Gdy zarządzanie urządzeniami firmy Apple i urządzeniami z systemem Android jest włączone, usługa Intune wysyła informacje o urządzeniu i użytkowniku w celu integracji z usługami innych firm i zarządzania urządzeniami.

Dodanie zgody na udostępnianie danych ma miejsce:
- Podczas włączania profilów służbowych systemu Android.
- Podczas włączania i przekazywania certyfikatów wypychania MDM firmy Apple.
- Podczas włączania dowolnych usługi firmy Apple takich jak Device Enrollment Program, School Manager czy Volume Purchasing Program (program zakupów zbiorczych).

W każdym przypadku zgoda jest ściśle powiązana z uruchamianiem usługi zarządzania urządzeniami przenośnymi. Będzie to na przykład potwierdzenie, że administrator IT autoryzował urządzenia firmy Apple lub Google do zarejestrowania. Dokumentacja opisująca, jakie informacje są udostępniane po wprowadzeniu nowych przepływów pracy, jest dostępna w następujących lokalizacjach:
- [Dane wysyłane przez usługę Intune do firmy Google](https://aka.ms/Data-intune-sends-to-google)
- [Dane wysyłane przez usługę Intune do firmy Apple](https://aka.ms/data-intune-sends-to-apple)

## <a name="key-considerations"></a>Zagadnienia dotyczące kluczy
Po zmianie na nowy urząd MDM prawdopodobnie wystąpi czas przejścia (maksymalnie osiem godzin), zanim urządzenie zostanie zaewidencjonowane i zsynchronizowane z usługą. Wymagane jest skonfigurowanie ustawień w nowym urzędzie MDM (rozwiązanie hybrydowe), aby upewnić się, że zarejestrowane urządzenia będą nadal zarządzane i chronione po zmianie. 
- Urządzenia muszą połączyć się z usługą po zmianie, aby ustawienia z nowego urzędu MDM (autonomicznej usługi Intune) zastąpiły istniejące ustawienia na urządzeniu.
- Po zmianie urzędu MDM niektóre podstawowe ustawienia (takie jak profile) z poprzedniego urzędu MDM (autonomicznej usługi Intune) pozostaną na urządzeniu przez maksymalnie siedem dni lub dopóki urządzenie nie połączy się z usługą po raz pierwszy. Zaleca się jak najszybsze skonfigurowanie aplikacji i ustawień (zasad, profilów, aplikacji itd.) w nowym urzędzie MDM (rozwiązanie hybrydowe) i wdrożenie ustawienia w grupach użytkowników, które zawierają użytkowników posiadających istniejące zarejestrowane urządzenia. Kiedy tylko urządzenie połączy się z usługą po zmianie urzędu MDM, odbierze nowe ustawienia z nowego urzędu MDM, co zapobiegnie przerwom w zarządzaniu i ochronie.
- Jeśli te same kategorie urządzeń istnieją zarówno w usłudze Intune, jak i w programie Configuration Manager, żadne przypisania kategorii urządzeń dla urządzeń nie są przenoszone po przejściu do nowego urzędu MDM. Aby nadal używać kategorii urządzeń, należy zmigrowane urządzenia ręcznie dodać do odpowiedniej kolekcji po zmianie urzędu MDM i wyświetleniu urządzeń w konsoli programu Configuration Manager.
- Urządzenia, które nie mają skojarzonych użytkowników (zazwyczaj jeśli masz urządzenia z systemem iOS w programie Device Enrollment Program lub scenariusze rejestracji zbiorczej) nie są migrowane do nowego urzędu MDM. W przypadku tych urządzeń musisz skontaktować się z działem pomocy technicznej, aby przenieść je do nowego urzędu MDM.

## <a name="change-mdm-authority-to-office-365"></a>Zmiana urzędu MDM na usługę Office 365

Aby aktywować zarządzanie urządzeniami przenośnymi usługi Office 365 (lub włączyć współistnienie MDM z usługą Intune), przejdź na stronę [https://protection.office.com](https://protection.office.com) i wybierz pozycję **Ochrona przed utratą danych** > **Zasady zabezpieczeń urządzeń** > **Wyświetl listę urządzeń zarządzanych** > **Zaczynamy**.

Aby uzyskać więcej informacji, zobacz [Konfigurowanie zarządzania urządzeniami przenośnymi (MDM) w usłudze Office 365](https://support.office.com/en-us/article/Set-up-Mobile-Device-Management-MDM-in-Office-365-dd892318-bc44-4eb1-af00-9db5430be3cd).

Jeśli chcesz, aby użytkownicy końcowi byli zarządzani tylko przez usługę zarządzania urządzeniami mobilnymi w usłudze Office 365, to po aktywowaniu tej usługi usuń wszystkie licencje przypisane do usługi Intune i/lub pakietu EMS.

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Czyszczenie urządzenia przenośnego po wygaśnięciu certyfikatu MDM

Certyfikat MDM jest odnawiany automatycznie, gdy urządzenia przenośne komunikują się z usługą Intune. W przypadku wyczyszczenia urządzeń przenośnych lub jeśli przez pewien czas nie komunikują się one z usługą Intune, certyfikat MDM nie zostanie odnowiony. Urządzenie zostanie usunięte z portalu Azure 180 dni po wygaśnięciu certyfikatu MDM.

## <a name="remove-mdm-authority"></a>Usuwanie urzędu MDM

Urzędu MDM nie można zmienić z powrotem na Nieznany. Usługa korzysta z urzędu MDM w celu określenia portalu, do którego mają raportować urządzenia zarejestrowane w portalu (urząd MDM usługi Microsoft Intune lub Office 365).

## <a name="what-to-expect-after-changing-the-mdm-authority"></a>Czego można się spodziewać po zmianie urzędu MDM

- Kiedy usługa Intune wykryje zmianę urzędu MDM dzierżawy, wysyła komunikat z powiadomieniem do wszystkich zarejestrowanych urządzeń w celu ich zameldowania i przeprowadzenia synchronizacji z usługą (to powiadomienie jest wykonywane poza zaplanowanym regularnym zaewidencjonowaniem). W związku z tym po zmianie urzędu MDM dla dzierżawy z autonomicznej usługi Intune na rozwiązanie hybrydowe wszystkie urządzenia, które są włączone i online, połączą się z usługą, otrzymają nowy urząd MDM i będą zarządzane przez rozwiązanie hybrydowe. Nie ma żadnych zakłóceń w zarządzaniu tymi urządzeniami i ich ochronie.
- Nawet w przypadku urządzeń, które są włączone i w trybie online podczas zmiany urzędu MDM (lub wkrótce po niej), nastąpi opóźnienie do ośmiu godzin (w zależności od czasu następnego zaplanowanego regularnego ewidencjonowania), zanim urządzenia zostaną zarejestrowane w usłudze z nowym urzędem MDM.    

  > [!IMPORTANT]    
  > W czasie między zmianą urzędu MDM a przekazaniem odnowionego certyfikatu usługi APNs do nowego urzędu rejestracje nowych urządzeń i meldowanie urządzeń z systemem iOS zakończy się niepowodzeniem. Dlatego ważne jest przejrzenie i przekazanie certyfikatu usługi APNs do nowego urzędu jak najszybciej po zmianie urzędu MDM.

- Użytkownicy mogą szybko zmienić nowy urząd MDM, ręcznie uruchamiając ewidencjonowanie z poziomu urządzenia do usługi. Mogą oni łatwo wprowadzić tę zmianę, używając aplikacji Portal firmy i inicjując sprawdzenie zgodności urządzenia.
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

- Po zmianie urzędu MDM wykonaj następujące kroki, aby sprawdzić, czy nowe urządzenia zostały pomyślnie zarejestrowane w nowym urzędzie:   
  - Rejestrowanie nowego urządzenia
  - Upewnij się, że nowo zarejestrowane urządzenie jest wyświetlane w konsoli programu Configuration Manager.
  - Za pomocą konsoli administracyjnej wykonaj akcję, na przykład zdalne blokowanie, na urządzeniu. Jeśli wykonanie akcji zakończy się powodzeniem, urządzenie jest zarządzane przez nowy urząd MDM.
- Jeśli masz problemy z określonymi urządzeniami, musisz jak najszybciej wyrejestrować i zarejestrować ponownie urządzenia, aby połączyć je z nowym urzędem certyfikacji i zarządzać nimi.

## <a name="next-steps"></a>Następne kroki

Po ustawieniu urzędu MDM można rozpocząć [rejestrowanie urządzeń](../enrollment/device-enrollment.md).
