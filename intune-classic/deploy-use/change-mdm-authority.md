---
title: "Zmiana urzędu MDM na program Configuration Manager (rozwiązanie hybrydowe MDM)"
description: "Dowiedz się, jak zmienić urząd MDM z autonomicznej usługi Intune na program Configuration Manager (rozwiązanie hybrydowe MDM)."
keywords: 
author: dougeby
manager: angrobe
ms.date: 10/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f1b4bce3-7932-4a0d-aa92-6dacc7060f42
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: 
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 64e79da53aec646fc65285e41f86541ecdf6d804
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2017
---
# <a name="change-the-mdm-authority"></a>Zmiana urzędu MDM
Począwszy od programu Configuration Manager w wersji 1610, można zmienić urząd MDM bez konieczności kontaktowania się z pomocą techniczną firmy Microsoft oraz wyrejestrowywania i ponownego rejestrowania istniejących urządzeń zarządzanych. Ten temat zawiera instrukcje dotyczące zmiany istniejącego dzierżawcy usługi Microsoft Intune skonfigurowanego w usłudze Intune i zmiany ustawienia urzędu MDM z usługi **Microsoft Intune** (autonomicznej) na program **Configuration Manager** (rozwiązanie hybrydowe) bez konieczności wyrejestrowywania i ponownej rejestracji istniejących zarządzanych urządzeń.

> [!Note]    
> Jeśli chcesz zmienić istniejącą dzierżawę usługi Microsoft Intune skonfigurowaną w konsoli programu Configuration Manager (rozwiązanie hybrydowe) i zmienić ustawienie urzędu MDM z programu **Configuration Manager** (rozwiązanie hybrydowe) na autonomiczną usługę **Microsoft Intune**, zobacz artykuł [Change the MDM authority from Configuration Manager (hybrid MDM) to Intune standalone](https://docs.microsoft.com/sccm/mdm/deploy-use/change-mdm-authority) (Zmiana urzędu MDM z programu Configuration Manager [hybrydowe zarządzanie urządzeniami przenośnymi] na autonomiczną usługę Intune). 


## <a name="key-considerations"></a>Zagadnienia dotyczące kluczy
Po zmianie na nowy urząd MDM prawdopodobnie wystąpi czas przejścia (maksymalnie osiem godzin), zanim urządzenie zostanie zaewidencjonowane i zsynchronizowane z usługą. Wymagane jest skonfigurowanie ustawień w nowym urzędzie MDM (rozwiązanie hybrydowe), aby upewnić się, że zarejestrowane urządzenia będą nadal zarządzane i chronione po zmianie. 
- Urządzenia muszą połączyć się z usługą po zmianie, aby ustawienia z nowego urzędu MDM (autonomicznej usługi Intune) zastąpiły istniejące ustawienia na urządzeniu.
- Po zmianie urzędu MDM niektóre podstawowe ustawienia (takie jak profile) z poprzedniego urzędu MDM (autonomicznej usługi Intune) pozostaną na urządzeniu przez maksymalnie siedem dni lub dopóki urządzenie nie połączy się z usługą po raz pierwszy. Zaleca się jak najszybsze skonfigurowanie aplikacji i ustawień (zasad, profilów, aplikacji itd.) w nowym urzędzie MDM (rozwiązanie hybrydowe) i wdrożenie ustawienia w grupach użytkowników, które zawierają użytkowników posiadających istniejące zarejestrowane urządzenia. Kiedy tylko urządzenie połączy się z usługą po zmianie urzędu MDM, odbierze nowe ustawienia z nowego urzędu MDM, co zapobiegnie przerwom w zarządzaniu i ochronie.
- Jeśli te same kategorie urządzeń istnieją zarówno w usłudze Intune, jak i w programie Configuration Manager, żadne przypisania kategorii urządzeń dla urządzeń nie są przenoszone po przejściu do nowego urzędu MDM. Aby nadal używać kategorii urządzeń, należy zmigrowane urządzenia ręcznie dodać do odpowiedniej kolekcji po zmianie urzędu MDM i wyświetleniu urządzeń w konsoli programu Configuration Manager.
- Urządzenia, które nie mają skojarzonych użytkowników (zazwyczaj jeśli masz urządzenia z systemem iOS w programie Device Enrollment Program lub scenariusze rejestracji zbiorczej) nie są migrowane do nowego urzędu MDM. W przypadku tych urządzeń musisz skontaktować się z działem pomocy technicznej, aby przenieść je do nowego urzędu MDM.

## <a name="prepare-to-change-the-mdm-authority-to-configuration-manager-hybrid"></a>Przygotowanie do zmiany urzędu MDM na program Configuration Manager (rozwiązanie hybrydowe)
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
Proces zmiany urzędu MDM na program Configuration Manager (rozwiązanie hybrydowe) obejmuje następujące kroki ogólne:  
- W konsoli programu Configuration Manager dodaj subskrypcję usługi Microsoft Intune.
- Skonfiguruj certyfikat usługi Apple APNs przy użyciu odnowionego certyfikatu usługi APNs.
- W konsoli programu Configuration Manager skonfiguruj i wdróż nowe ustawienia i aplikacje z nowego urzędu MDM (rozwiązanie hybrydowe).
- Kiedy następnym razem urządzenia połączą się z usługą, zsynchronizuje ona i odbierze nowe ustawienia z nowego urzędu MDM.

#### <a name="to-change-the-mdm-authority-to-configuration-manager"></a>Aby zmienić urząd MDM na program Configuration Manager
1. W konsoli programu Configuration Manager przejdź do pozycji **Administracja** &gt; **Przegląd** &gt; **Usługi w chmurze** &gt; **Subskrypcje usługi Microsoft Intune** i wybierz subskrypcję usługi Intune.
2. Zaloguj się do dzierżawy usługi Intune, której pierwotnie użyto podczas ustawiania urzędu MDM w usłudze Intune, a następnie kliknij przycisk **Dalej**.
3. Wybierz pozycję **Zmień moje źródło zarządzania MDM na program Configuration Manager** i kliknij przycisk **Dalej**.
4. Wybierz kolekcję użytkowników tak, aby zawierała wszystkich użytkowników, którzy będą w dalszym ciągu zarządzani przez nowy hybrydowy urząd MDM.
5. Kliknij przycisk **Dalej** i ukończ pracę kreatora. Urząd MDM został zmieniony na **program Configuration Manager**.
6. Zaloguj się w [konsoli administracyjnej usługi Microsoft Intune](http://manage.microsoft.com) przy użyciu tej samej dzierżawy usługi Intune i upewnij się, że urząd MDM został zmieniony na opcję **Ustaw Menedżera konfiguracji**.


## <a name="enable-ios-enrollment"></a>Włączanie rejestracji systemu iOS
Jeśli masz urządzenia z systemem iOS, musisz skonfigurować certyfikat usługi APNs w programie Configuration Manager.

#### <a name="to-enable-ios-enrollment-and-configure-the-apns-certificate"></a>Aby włączyć rejestrację urządzeń z systemem iOS i skonfigurować certyfikat APNs

1. **Pobierz żądanie podpisania certyfikatu**

    1. W konsoli programu Configuration Manager przejdź do pozycji**Administracja** &gt; **Usługi w chmurze** &gt; **Subskrypcje usługi Microsoft Intune** i wybierz pozycję **Utwórz żądanie certyfikatu APNs**, aby otworzyć okno dialogowe **Zgłoś żądanie podpisania certyfikatu usługi wypychania powiadomień firmy Apple**.  
    2. Kliknij przycisk**Przeglądaj** i przejdź do ścieżki, w której ma zostać zapisany plik nowego żądania podpisania certyfikatu (csr). Zapisz lokalnie plik żądania podpisania certyfikatu (CSR).  
    3. Kliknij przycisk **Pobierz**. Nowy plik .csr usługi Microsoft Intune zostanie pobrany i zapisany przez program Configuration Manager.   

    > [!IMPORTANT]
    > Musisz pobrać nowe żądanie podpisania certyfikatu. Nie używaj istniejącego pliku, w przeciwnym razie operacja zakończy się niepowodzeniem.  

2.  Przejdź do [portalu Apple Push Certificates](http://go.microsoft.com/fwlink/?LinkId=269844) i zaloguj się przy użyciu **tego samego** identyfikatora Apple ID, który został wcześniej użyty do utworzenia i odnowienia certyfikatu usługi APNs używanego w autonomicznej usłudze Intune.

    ![Strona logowania portalu Apple Push Certificates](../media/mdm-change-apns-portal.png)

3. Wybierz certyfikat usługi APNs używany w autonomicznej usłudze Intune, a następnie kliknij pozycję**Odnów**.

    ![Okno dialogowe Odnawianie usługi APNs](../media/mdm-change-renew-apns.png)

4. Wybierz plik żądania podpisania certyfikatu (CSR) usługi APNs pobrany lokalnie, a następnie kliknij pozycję **Przekaż**.

    ![Strona logowania portalu Apple Push Certificates](../media/mdm-change-renew-apns-upload.png)
 
5. Wybierz tę samą usługę APNs, a następnie kliknij przycisk **Pobierz**. Pobierz certyfikat usługi APNs (PEM) i zapisz plik lokalnie.  

    ![Strona logowania portalu Apple Push Certificates](../media/mdm-change-renew-apns-download.png)

6. Przekaż odnowiony certyfikat usługi APNs do dzierżawy hybrydowej przy użyciu tego samego identyfikatora Apple ID co wcześniej.

    1.  W konsoli programu Configuration Manager przejdź do pozycji **Administracja** &gt; **Usługi w chmurze** &gt; **Subskrypcje usługi Microsoft Intune**, a następnie wybierz pozycję **Konfiguruj platformy** &gt; **iOS**.  
    2.  W oknie dialogowym **Właściwości subskrypcji usługi Microsoft Intune** wybierz kartę **Certyfikat usługi APNs** i kliknij, aby zaznaczyć pole wyboru **Włącz rejestrowanie dla systemu iOS i MAC OS X (MDM)**.  
    3.  Kliknij polecenie **Przeglądaj**i przejdź do pliku certyfikatu (cer) usługi APNs, który został pobrany od firmy Apple. Program Configuration Manager wyświetli informacje o certyfikacie usługi APNs. Kliknij przycisk **OK** , aby zapisać certyfikat APNs w usłudze Intune.  

        ![Strona właściwości subskrypcji usługi Intune — system iOS](../media/mdm-change-subscription-properties-ios.png)

## <a name="enable-android-enrollment"></a>Włączanie rejestracji w systemie Android
1. W konsoli programu Configuration Manager przejdź do pozycji **Administracja** &gt; **Usługi w chmurze** &gt; **Subskrypcje usługi Microsoft Intune**, a następnie wybierz pozycję **Konfiguruj platformy** &gt; **Android**.  
2. Wybierz pozycję **Włącz rejestrację w systemie Android** i kliknij przycisk **OK**.

### <a name="enable-windows-enrollment"></a>Włączanie rejestracji w systemie Windows
1. W konsoli programu Configuration Manager przejdź do pozycji **Administracja** &gt; **Usługi w chmurze** &gt; **Subskrypcje usługi Microsoft Intune**, a następnie wybierz pozycję **Konfiguruj platformy** &gt; **Windows**.  
2. Wybierz pozycję **Włącz rejestrację w systemie Windows** i kliknij przycisk **OK**.

### <a name="enable-windows-phone-enrollment"></a>Włączanie rejestracji w systemie Windows Phone
1. W konsoli programu Configuration Manager przejdź do pozycji **Administracja** &gt; **Usługi w chmurze** &gt; **Subskrypcje usługi Microsoft Intune**, a następnie wybierz pozycję **Konfiguruj platformy** &gt; **Windows Phone**.  
2. Wybierz platformę, którą chcesz włączyć, a następnie kliknij przycisk **OK**.


## <a name="next-steps"></a>Następne kroki
Po zakończeniu zmiany urzędu MDM przejrzyj poniższe kroki:
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