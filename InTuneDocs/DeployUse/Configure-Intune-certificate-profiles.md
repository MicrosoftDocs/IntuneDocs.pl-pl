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
ms.sourcegitcommit: 8e3f7cac8eb3495aad3835ec4713d67a58383c66
ms.openlocfilehash: 8b08f8fde6136b8eca61f6ae7a8c21635f7d452e


---

# Konfigurowanie profilów certyfikatów usługi Intune
Po skonfigurowaniu infrastruktury oraz certyfikatów zgodnie z opisem w sekcji [Konfigurowanie infrastruktury certyfikatów dla profilu SCEP](configure-certificate-infrastructure-for-scep.md) lub [Konfigurowanie infrastruktury certyfikatów dla profilu PFX](configure-certificate-infrastructure-for-pfx.md) można utworzyć profile certyfikatów. Oto proces:

- **Zadanie 1** — Eksportowanie certyfikatu zaufanego głównego urzędu certyfikacji
- **Zadanie 2** — Tworzenie profilów zaufanych certyfikatów
- **Zadanie 3** — Tworzenie jednego z dwóch typów profilów certyfikatów:
  - profile certyfikatów protokołu SCEP
  - profile certyfikatów PFX

## **Zadanie 1** — Eksportowanie certyfikatu zaufanego głównego urzędu certyfikacji
Wyeksportuj certyfikat zaufanego głównego urzędu certyfikacji w formacie pliku **.cer** z wystawiającego urzędu certyfikacji lub dowolnego urządzenia traktującego wystawiający urząd certyfikacji jako zaufany. Nie należy eksportować klucza prywatnego.

Ten certyfikat zostanie zaimportowany podczas konfiguracji profilu zaufanego certyfikatu.

## **Zadanie 2** — Tworzenie profilów zaufanych certyfikatów
Przed utworzeniem profilu certyfikatu protokołu Simple Certificate Enrollment Protocol (SCEP) lub profilu certyfikatu PKCS #12 (PFX) należy utworzyć profil zaufanego certyfikatu. Wymagany jest profil zaufanego certyfikatu oraz profil SCEP lub PFX dla każdej platformy urządzeń przenośnych.

### Aby utworzyć profil zaufanego certyfikatu

1.  W [konsoli administracyjnej usługi Intune](https://manage.microsoft.com) wybierz kolejno pozycje **Zasady** &gt; **Dodaj zasady**.
2.  Dodaj jeden z następujących typów zasad:
    - **Android &gt; Profil zaufanego certyfikatu (system Android 4 i nowsze)**
    - **iOS &gt; Profil zaufanego certyfikatu (system iOS 7.1 i nowsze)**
    - **Mac OS X &gt; Profil zaufanego certyfikatu (system Mac OS X 10.9 i nowsze)**
    - **Windows &gt; Profil zaufanego certyfikatu (system Windows 8.1 i nowsze)**
    - **Windows &gt; Profil zaufanego certyfikatu (system Windows Phone 8.1 i nowsze)**

    Dowiedz się więcej: [Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Podaj wymagane informacje, aby skonfigurować ustawienia profilu zaufanego certyfikatu dla systemów Android, iOS, Mac OS X, Windows 8.1 lub Windows Phone 8.1.

    - W ustawieniu **Plik certyfikatu** zaimportuj certyfikat zaufanego głównego urzędu certyfikacji (plik cer) wyeksportowany z urzędu wystawiającego certyfikaty. Ustawienie **Magazyn docelowy** dotyczy tylko urządzeń z systemem Windows 8.1 oraz nowszymi i tylko wtedy, gdy urządzenie ma więcej niż jeden magazyn certyfikatów.
    -  W obszarze **Format nazwy podmiotu** wybierz opcję **Niestandardowy**, aby wprowadzić niestandardowy format nazwy podmiotu.  
        Aktualnie są obsługiwane dwie zmienne dla formatu niestandardowego: `Common Name (CN)` i `Email (E)`. Przy użyciu kombinacji tych zmiennych i statycznych ciągów można utworzyć niestandardowy format nazwy podmiotu, na przykład taki:  

        `CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US`  

        W tym przykładzie administrator utworzył format nazwy podmiotu, który oprócz zmiennych `CN` i `E` używa ciągów dla wartości jednostki organizacyjnej, organizacji, lokalizacji, stanu i kraju. [Funkcja CertStrToName](https://msdn.microsoft.com/en-us/library/windows/desktop/aa377160.aspx) wyświetla listę obsługiwanych ciągów.  
4.  Wybierz pozycję **Zapisz zasady**.

Nowe zasady zostaną wyświetlone w obszarze roboczym **Zasady**. Teraz możesz je wdrożyć.

## **Zadanie 3** — Tworzenie profilów certyfikatów protokołu SCEP lub PFX
Po utworzeniu profilu certyfikatu zaufanego urzędu certyfikacji należy utworzyć profile certyfikatów protokołu SCEP lub PFX dla wszystkich platform, które będą używane. Podczas tworzenia profilu certyfikatu protokołu SCEP należy wskazać profil certyfikatu zaufanego dla tej samej platformy. W ten sposób oba profile certyfikatów zostaną połączone, niemniej jednak każdy profil należy wdrożyć osobno.

### Aby utworzyć profil certyfikatu protokołu SCEP

1.  W [konsoli administracyjnej usługi Intune](https://manage.microsoft.com) wybierz kolejno pozycje **Zasady** &gt; **Dodaj zasady**.
2.  Dodaj jeden z następujących typów zasad:
    - **Android &gt; Profil certyfikatu protokołu SCEP (system Android 4 i nowsze)**
    - **iOS &gt; Profil certyfikatu protokołu SCEP (system iOS 7.1 i nowsze)**
    - **Mac OS X &gt; Profil certyfikatu protokołu SCEP (system Mac OS X 10.9 i nowsze)**
    - **Windows &gt; Profil certyfikatu protokołu SCEP (system Windows 8.1 i nowsze)**
    - **Windows &gt; Profil certyfikatu protokołu SCEP (system Windows Phone 8.1 i nowsze)**

    Dowiedz się więcej: [Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Postępuj zgodnie z instrukcjami na stronie konfiguracji profilu, aby skonfigurować ustawienia profilu certyfikatu SCEP.
    > [!NOTE]
    >
    > W obszarze **Format nazwy podmiotu** wybierz opcję **Niestandardowy**, aby wprowadzić niestandardowy format nazwy podmiotu.
    >
    > Aktualnie są obsługiwane dwie zmienne dla formatu niestandardowego: `Common Name (CN)` i `Email (E)`. Przy użyciu kombinacji tych zmiennych i statycznych ciągów można utworzyć niestandardowy format nazwy podmiotu, na przykład taki:

    >     CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US

    > W tym przykładzie administrator utworzył format nazwy podmiotu, który oprócz zmiennych `CN` i `E` używa ciągów dla wartości jednostki organizacyjnej, organizacji, lokalizacji, stanu i kraju. [Funkcja CertStrToName](https://msdn.microsoft.com/en-us/library/windows/desktop/aa377160.aspx) wyświetla listę obsługiwanych ciągów.

4.  Wybierz pozycję **Zapisz zasady**.

Nowe zasady zostaną wyświetlone w obszarze roboczym **Zasady**. Teraz możesz je wdrożyć.

### Aby utworzyć profil certyfikatu PFX

1.  W [konsoli administracyjnej usługi Intune](https://manage.microsoft.com) wybierz kolejno pozycje **Zasady** &gt; **Dodaj zasady**.
2.  Dodaj jeden z następujących typów zasad:
  - **Android &gt; Profil certyfikatu PFX (system Android 4 i nowsze)**
  - **Windows &gt; Profil certyfikatu PKCS #12 (PFX) (system Windows 10 i nowsze)**
  - **Windows &gt; Profil certyfikatu PKCS #12 (PFX) (system Windows Phone 10 i nowsze)**
  - **iOS > Profil certyfikatu PKCS #12 (PFX) (system iOS 7.1 i nowsze)**    
    Dowiedz się więcej: [Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).
3.  Wprowadź informacje wymagane w formularzu zasad.
4.  Wybierz pozycję **Zapisz zasady**.

Nowe zasady zostaną wyświetlone w obszarze roboczym **Zasady**. Teraz możesz je wdrożyć.

## Wdrażanie profili certyfikatów
Podczas wdrażania profilów certyfikatów plik certyfikatu z profilu certyfikatu zaufanego urzędu certyfikacji jest instalowany na urządzeniu. Profil certyfikatu protokołu SCEP lub PFX jest wykorzystywany przez to urządzenie do tworzenia żądania certyfikatu.

Profile certyfikatów mogą być instalowane wyłącznie na urządzeniach z platformą użytą podczas tworzenia profilu.

-   Profile certyfikatów można również wdrażać dla kolekcji użytkowników lub kolekcji urządzeń.

    > [!TIP]
    > Aby opublikować certyfikaty dla urządzenia jak najszybciej po jego rejestracji, należy wdrożyć profil certyfikatu w grupie użytkowników, a nie w grupie urządzeń. W przypadku wdrożenia w grupie urządzeń wymagana jest pełna rejestracja urządzenia przed otrzymaniem przez nie zasad.

-   Mimo że każdy profil należy wdrożyć osobno, konieczne jest również wdrożenie profilu zaufanego certyfikatu głównego urzędu certyfikacji oraz profilu protokołu SCEP lub PFX. W przeciwnym razie zasady certyfikatu protokołu SCEP lub PFX nie będą działać.

Wdróż profile certyfikatów w taki sam sposób jak w przypadku innych zasad w usłudze Intune:

1.  W obszarze roboczym **Zasady** wybierz zasady do wdrożenia, a następnie wybierz pozycję **Zarządzaj wdrożeniem**.
2.  W oknie dialogowym **Zarządzanie wdrażaniem** :
    -   **Aby wdrożyć zasady**, wybierz co najmniej jedną grupę, w której chcesz wdrożyć zasady, a następnie wybierz pozycję **Dodaj** &gt; **OK**.
    -   **Aby zamknąć okno dialogowe bez wdrażania**, wybierz pozycję **Anuluj**.

Po wybraniu wdrożonych zasad można zobaczyć więcej informacji dotyczących wdrożenia w dolnej części listy zasad.

### Następne kroki

Dowiedz się, jak używać certyfikatów do zabezpieczenia poczty e-mail, sieci Wi-Fi i profilów sieci VPN.

-  [Konfigurowanie dostępu do firmowej poczty e-mail przy użyciu profilów poczty e-mail](configure-access-to-corporate-email-using-email-profiles-with-Microsoft-Intune.md)
-  [Połączenia Wi-Fi w usłudze Microsoft Intune](wi-fi-connections-in-microsoft-intune.md)
-  [Połączenia VPN w usłudze Microsoft Intune](vpn-connections-in-microsoft-intune.md)



<!--HONumber=Aug16_HO5-->


