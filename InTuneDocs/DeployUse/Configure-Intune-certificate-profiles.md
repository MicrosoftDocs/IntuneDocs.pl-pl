---
title: "Konfigurowanie profilów certyfikatów | Microsoft Intune"
description: "Dowiedz się, jak utworzyć profil certyfikatu usługi Intune."
keywords: 
author: nbigman
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 679a20a1-e66f-4b6b-bd8f-896daf1f8175
ms.reviewer: kmyrup
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6a7f2eeb0114f525890d1dcb61344d60a19943d1
ms.openlocfilehash: 14419092edc77b2229cf980a74e81048941a2c28


---

# Konfigurowanie profilów certyfikatów usługi Intune
Po skonfigurowaniu infrastruktury oraz certyfikatów zgodnie z opisem w sekcji [Konfigurowanie infrastruktury certyfikatów dla profilu SCEP](configure-certificate-infrastructure-for-scep.md) lub [Konfigurowanie infrastruktury certyfikatów dla profilu PFX](configure-certificate-infrastructure-for-pfx.md) można skonfigurować profile certyfikatów:

**Zadanie 1** — Eksportowanie certyfikatu zaufanego głównego urzędu certyfikacji **Zadanie 2** — Tworzenie profilów certyfikatów zaufanego urzędu certyfikacji **Zadanie 3** — Jedno z następujących zadań:

Tworzenie profilów certyfikatów protokołu SCEP

Tworzenie profilów certyfikatów PFX

### Zadanie 1 — Eksportowanie certyfikatu zaufanego głównego urzędu certyfikacji
Wyeksportuj certyfikat zaufanego głównego urzędu certyfikacji w formacie pliku **.cer** z wystawiającego urzędu certyfikacji lub dowolnego urządzenia traktującego wystawiający urząd certyfikacji jako zaufany. Klucz prywatny nie jest eksportowany.

Ten certyfikat zostanie zaimportowany podczas konfiguracji profilu certyfikatu zaufanego.

### Zadanie 2 — Tworzenie profilów certyfikatów zaufanych
Należy utworzyć **profil certyfikatu zaufanego**, aby móc utworzyć profil certyfikatu SCEP lub PFX. Wymaga się profilu certyfikatu zaufanego oraz profilu SCEP lub PFS dla każdej platformy urządzeń przenośnych.

##### Aby utworzyć profil zaufanego certyfikatu

1.  Otwórz [konsolę administracyjną usługi Intune](https://manage.microsoft.com) i kliknij pozycje **Zasady** &gt; **Dodaj zasady**.

2.  Skonfiguruj jeden z następujących typów zasad:

    **Android &gt; Profil zaufanego certyfikatu (system Android 4 i nowsze)**

    **iOS &gt; Profil zaufanego certyfikatu (system iOS 7.1 i nowsze)**

    **Mac OS X &gt; Profil zaufanego certyfikatu (system Mac OS X 10.9 i nowsze)**

    **Windows &gt; Profil zaufanego certyfikatu (system Windows 8.1 i nowsze)**

    **Windows &gt; Profil zaufanego certyfikatu (system Windows Phone 8.1 i nowsze)**

    Dowiedz się więcej: [Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Podaj wymagane informacje, aby skonfigurować ustawienia profilu zaufanego certyfikatu dla systemów Android, iOS, Mac OS X, Windows 8.1 lub Windows Phone 8.1. 

    - W ustawieniu **Plik certyfikatu** zaimportuj certyfikat zaufanego głównego urzędu certyfikacji (plik **cer**) wyeksportowany z urzędu wystawiającego certyfikaty. Ustawienie **Magazyn docelowy** dotyczy tylko urządzeń z systemem Windows 8.1 oraz nowszymi i tylko wtedy, gdy urządzenie ma więcej niż jeden magazyn certyfikatów.

    
    - W obszarze **Format nazwy podmiotu** wybierz opcję **Niestandardowy**, aby podać niestandardowy format nazwy podmiotu.  

        Aktualnie są obsługiwane dwie zmienne dla formatu niestandardowego: **Nazwa pospolita (CN)** i **Adres e-mail (E)**. Przy użyciu kombinacji tych zmiennych i statycznych ciągów można utworzyć niestandardowy format nazwy podmiotu, na przykład taki, jaki podano w tym przykładzie:  

        `CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US`  

        W tym przykładzie administrator utworzył format nazwy podmiotu, który oprócz zmiennych CN i E używa ciągów dla jednostki organizacyjnej, organizacji, lokalizacji, stanu i kraju. Lista obsługiwanych ciągów znajduje się w temacie [Funkcja CertStrToName](https://msdn.microsoft.com/en-us/library/windows/desktop/aa377160.aspx).  


4.  Gdy skończysz, kliknij pozycję **Zapisz zasady**.

Nowe zasady zostaną wyświetlone w obszarze roboczym **Zasady** i będzie można je teraz wdrożyć.

### Zadanie 3 — Tworzenie profilów certyfikatów protokołu SCEP lub PFX
Po utworzeniu profilu certyfikatu zaufanego urzędu certyfikacji należy utworzyć profile certyfikatów protokołu SCEP lub PFX dla wszystkich platform, które będą używane. Podczas tworzenia profilu certyfikatu protokołu SCEP należy wskazać profil certyfikatu zaufanego dla tej samej platformy. W ten sposób oba profile certyfikatów zostaną połączone; niemniej jednak każdy profil należy wdrożyć osobno.

##### Aby utworzyć profil certyfikatu protokołu SCEP

1.  Otwórz [konsolę administracyjną usługi Intune](https://manage.microsoft.com) i kliknij pozycje **Zasady** &gt; **Dodaj zasady**.

2.  Skonfiguruj jeden z następujących typów zasad:

    **Android &gt; Profil certyfikatu protokołu SCEP (system Android 4 i nowsze)**

    **iOS &gt; Profil certyfikatu protokołu SCEP (system iOS 7.1 i nowsze)**

    **Mac OS X &gt; Profil certyfikatu protokołu SCEP (system Mac OS X 10.9 i nowsze)**

    **Windows &gt; Profil certyfikatu protokołu SCEP (system Windows 8.1 i nowsze)**

    **Windows &gt; Profil certyfikatu protokołu SCEP (system Windows Phone 8.1 i nowsze)**

    Dowiedz się więcej: [Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Postępuj zgodnie z instrukcjami na stronie konfiguracji profilu, aby skonfigurować ustawienia profilu certyfikatu SCEP.
    > [!NOTE]
    > 
    > W obszarze **Format nazwy podmiotu** wybierz opcję **Niestandardowy**, aby podać niestandardowy format nazwy podmiotu.
    > 
    >  Aktualnie są obsługiwane dwie zmienne dla formatu niestandardowego: Nazwa pospolita (CN) i Adres e-mail (E). Przy użyciu kombinacji tych zmiennych i statycznych ciągów można utworzyć niestandardowy format nazwy podmiotu, na przykład taki, jaki podano w tym przykładzie:
    
    >     CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US
    
    >    W tym przykładzie administrator utworzył format nazwy podmiotu, który oprócz zmiennych *CN* i *E* używa ciągów dla jednostki organizacyjnej, organizacji, lokalizacji, stanu i kraju. Lista obsługiwanych ciągów znajduje się w temacie [Funkcja CertStrToName](https://msdn.microsoft.com/en-us/library/windows/desktop/aa377160.aspx).

4.  Gdy skończysz, kliknij pozycję **Zapisz zasady**.

Nowe zasady zostaną wyświetlone w obszarze roboczym **Zasady** i będzie można je teraz wdrożyć.

##### Aby utworzyć profil certyfikatu PFX

1.  Otwórz [konsolę administracyjną usługi Intune](https://manage.microsoft.com) i kliknij pozycje **Zasady** &gt; **Dodaj zasady**.

2.  Skonfiguruj jeden z następujących typów zasad:



-   **Android &gt; Profil certyfikatu PFX (system Android 4 i nowsze)**

    -   **Windows &gt; Profil certyfikatu PKCS #12 (PFX) (system Windows 10 i nowsze)**

    -   **Windows &gt; Profil certyfikatu PKCS #12 (PFX) (system Windows Phone 10 i nowsze)**

    -    **iOS > Profil certyfikatu PKCS #12 (PFX) (system iOS 7.1 i nowsze)**    

    Dowiedz się więcej: [Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Podaj informacje wymagane w formularzu zasad.

4.  Gdy skończysz, kliknij pozycję **Zapisz zasady**.

Nowe zasady zostaną wyświetlone w obszarze roboczym **Zasady** i będzie można je teraz wdrożyć.

## Wdrażanie profili certyfikatów
Podczas wdrażania profilów certyfikatów plik certyfikatu z profilu certyfikatu zaufanego urzędu certyfikacji jest instalowany na urządzeniu, natomiast profil certyfikatu protokołu SCEP lub PFX jest wykorzystywany przez to urządzenie do tworzenia żądania certyfikatu.

Profile certyfikatów mogą być instalowane wyłącznie na urządzeniach zgodnych z platformą użytą podczas tworzenia profilu.

-   Profile certyfikatów można również wdrażać dla kolekcji użytkowników lub kolekcji urządzeń.

    > [!TIP]
    > Aby umożliwić publikowanie certyfikatów dla urządzeń jak najszybciej po ich rejestracji, należy wdrożyć profil certyfikatu w grupie użytkowników (a nie w grupie urządzeń). W przypadku wdrożenia w grupie urządzeń konieczne jest zakończenie pełnej rejestracji urządzenia przed otrzymaniem przez nie zasad.

-   Mimo że wszystkie profile są wdrażane pojedynczo, konieczne jest wdrożenie zarówno profilu zaufanego certyfikatu głównego, jak i profilu protokołu SCEP/PFX — w przeciwnym razie zasady certyfikatu protokołu SCEP/PFX nie będą działać.

Sposób wdrażania profilów certyfikatów jest taki sam jak w przypadku innych zasad w usłudze Intune.

1.  W obszarze roboczym **Zasady** wybierz zasady do wdrożenia, a następnie kliknij pozycję **Zarządzaj wdrożeniem**.

2.  W oknie dialogowym **Zarządzanie wdrażaniem** :

    -   **Aby wdrożyć zasady** — wybierz co najmniej jedną grupę, w której chcesz wdrożyć zasady, a następnie kliknij pozycję **Dodaj** &gt; **OK**.

    -   **Aby zamknąć okno dialogowe bez wdrażania** — kliknij przycisk **Anuluj**.

Po wybraniu wdrożonych zasad można wyświetlić więcej informacji dotyczących wdrożenia w dolnej części listy zasad.
###  Następne kroki

Można teraz użyć certyfikatów do zabezpieczenia poczty e-mail, sieci Wi-Fi i profilów sieci VPN:

-  [Konfigurowanie dostępu do firmowej poczty e-mail przy użyciu profilów poczty e-mail](configure-access-to-corporate-email-using-email-profiles-with-Microsoft-Intune.md)
-  [Połączenia Wi-Fi w usłudze Microsoft Intune](wi-fi-connections-in-microsoft-intune.md)
-  [Połączenia VPN w usłudze Microsoft Intune](vpn-connections-in-microsoft-intune.md)



<!--HONumber=Jul16_HO4-->


