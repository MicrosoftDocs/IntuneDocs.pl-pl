---
title: "Konfigurowanie profilów certyfikatów | Microsoft Intune"
description: "Dowiedz się, jak utworzyć profil certyfikatu usługi Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 679a20a1-e66f-4b6b-bd8f-896daf1f8175
ms.reviewer: kmyrup
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: bafb86b1e388163c07110559e2a51bbe0dadc5ed


---

# <a name="configure-intune-certificate-profiles"></a>Konfigurowanie profilów certyfikatów usługi Intune
Po skonfigurowaniu infrastruktury oraz certyfikatów zgodnie z opisem w sekcji [Konfigurowanie infrastruktury certyfikatów dla profilu SCEP](configure-certificate-infrastructure-for-scep.md) lub [Konfigurowanie infrastruktury certyfikatów dla profilu PFX](configure-certificate-infrastructure-for-pfx.md) można utworzyć profile certyfikatów. Oto proces:

- **Zadanie 1** — Eksportowanie certyfikatu zaufanego głównego urzędu certyfikacji
- **Zadanie 2** — Tworzenie profilów zaufanych certyfikatów
- **Zadanie 3** — Tworzenie jednego z dwóch typów profilów certyfikatów:
  - profile certyfikatów protokołu SCEP
  - profile certyfikatów PFX

## <a name="task-1-export-the-trusted-root-ca-certificate"></a>**Zadanie 1** — Eksportowanie certyfikatu zaufanego głównego urzędu certyfikacji
Wyeksportuj certyfikat zaufanego głównego urzędu certyfikacji w formacie pliku **.cer** z wystawiającego urzędu certyfikacji lub dowolnego urządzenia traktującego wystawiający urząd certyfikacji jako zaufany. Nie należy eksportować klucza prywatnego.

Ten certyfikat zostanie zaimportowany podczas konfiguracji profilu zaufanego certyfikatu.

## <a name="task-2-create-trusted-certificate-profiles"></a>**Zadanie 2** — Tworzenie profilów zaufanych certyfikatów
Przed utworzeniem profilu certyfikatu protokołu Simple Certificate Enrollment Protocol (SCEP) lub profilu certyfikatu PKCS #12 (PFX) należy utworzyć profil zaufanego certyfikatu. Wymagany jest profil zaufanego certyfikatu oraz profil SCEP lub PFX dla każdej platformy urządzeń przenośnych.

### <a name="to-create-a-trusted-certificate-profile"></a>Aby utworzyć profil zaufanego certyfikatu

1.  W [konsoli administracyjnej usługi Intune](https://manage.microsoft.com) wybierz kolejno pozycje **Zasady** &gt; **Dodaj zasady**, a następnie wybierz platformę urządzeń. Profil zaufanego certyfikatu można utworzyć dla poniższych urządzeń:

-  System Android 4 lub nowszy

-  Program Android for Work

-  System iOS 7.1 lub nowszy

-  System Mac OS X 10.9 lub nowszy

-  Windows 8.1 i nowsze

-  System Windows Phone 8.1 lub nowszy

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

2.  Dodaj zasady **profilu zaufanego certyfikatu**.

    Dowiedz się więcej: [Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Podaj wymagane informacje, aby skonfigurować ustawienia profilu zaufanego certyfikatu dla systemów Android, iOS, Mac OS X, Windows 8.1 lub Windows Phone 8.1.
4.  W ustawieniu **Plik certyfikatu** zaimportuj certyfikat zaufanego głównego urzędu certyfikacji (plik cer) wyeksportowany z urzędu wystawiającego certyfikaty. Ustawienie **Magazyn docelowy** dotyczy tylko urządzeń z systemem Windows 8.1 oraz nowszymi i tylko wtedy, gdy urządzenie ma więcej niż jeden magazyn certyfikatów.

4.  Wybierz pozycję **Zapisz zasady**.

Nowe zasady zostaną wyświetlone w obszarze roboczym **Zasady**. Teraz możesz je wdrożyć.

> [!NOTE]
>
> Na urządzeniach z systemem Android i urządzeniach biorących udział programie Android for Work zostanie wyświetlone powiadomienie, że miało miejsce zainstalowanie zaufanego certyfikatu przez inną firmę.


## <a name="task-3-create-scep-or-pfx-certificate-profiles"></a>**Zadanie 3** — Tworzenie profilów certyfikatów protokołu SCEP lub PFX
Po utworzeniu profilu certyfikatu zaufanego urzędu certyfikacji należy utworzyć profile certyfikatów protokołu SCEP lub PFX dla wszystkich platform, które będą używane. Podczas tworzenia profilu certyfikatu protokołu SCEP należy wskazać profil certyfikatu zaufanego dla tej samej platformy. W ten sposób oba profile certyfikatów zostaną połączone, niemniej jednak każdy profil należy wdrożyć osobno.

### <a name="to-create-an-scep-certificate-profile"></a>Aby utworzyć profil certyfikatu protokołu SCEP

1.  W [konsoli administracyjnej usługi Intune](https://manage.microsoft.com) wybierz kolejno pozycje **Zasady** &gt; **Dodaj zasady**, a następnie wybierz platformę urządzeń.  Profil certyfikatu protokołu SCEP można utworzyć dla poniższych urządzeń:

-  System Android 4 lub nowszy

-  Program Android for Work

-  System iOS 7.1 lub nowszy

-  System Mac OS X 10.9 lub nowszy

-  Windows 8.1 i nowsze

-  System Windows Phone 8.1 lub nowszy

2.  Dodaj zasady **profilu certyfikatu protokołu SCEP**.

    Dowiedz się więcej: [Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Postępuj zgodnie z instrukcjami na stronie konfiguracji profilu, aby skonfigurować ustawienia profilu certyfikatu SCEP.
    > [!NOTE]
    >
    > W obszarze **Format nazwy podmiotu** wybierz opcję **Niestandardowy**, aby wprowadzić niestandardowy format nazwy podmiotu (tylko w profilach systemu iOS).
    >
    > Aktualnie są obsługiwane dwie zmienne dla formatu niestandardowego: `Common Name (CN)` i `Email (E)`. Przy użyciu kombinacji tych zmiennych i statycznych ciągów można utworzyć niestandardowy format nazwy podmiotu, na przykład taki:

    >     CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US

    > W tym przykładzie administrator utworzył format nazwy podmiotu, który oprócz zmiennych `CN` i `E` używa ciągów dla wartości jednostki organizacyjnej, organizacji, lokalizacji, stanu i kraju. [Funkcja CertStrToName](https://msdn.microsoft.com/en-us/library/windows/desktop/aa377160.aspx) wyświetla listę obsługiwanych ciągów.

4.  Wybierz pozycję **Zapisz zasady**.

Nowe zasady zostaną wyświetlone w obszarze roboczym **Zasady**. Teraz możesz je wdrożyć.

### <a name="to-create-a-pfx-certificate-profile"></a>Aby utworzyć profil certyfikatu PFX

1.  W [konsoli administracyjnej usługi Intune](https://manage.microsoft.com) wybierz kolejno pozycje **Zasady** &gt; **Dodaj zasady**, a następnie wybierz platformę urządzeń. Certyfikaty PFX są obsługiwane na poniższych platformach urządzeń:
  - System Android 4 lub nowszy
  - Program Android for Work
  - System Windows 10 lub nowszy
  - System Windows Phone 10 lub nowszy
  - System iOS 8.0 i nowsze    


2.  Dodaj zasady **profilu certyfikatu PFX**.
      Dowiedz się więcej: [Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).
3.  Wprowadź informacje wymagane w formularzu zasad.
4.  Wybierz pozycję **Zapisz zasady**.

Nowe zasady zostaną wyświetlone w obszarze roboczym **Zasady**. Teraz możesz je wdrożyć.

## <a name="deploy-certificate-profiles"></a>Wdrażanie profili certyfikatów
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

### <a name="next-steps"></a>Następne kroki

Dowiedz się, jak używać certyfikatów do zabezpieczenia poczty e-mail, sieci Wi-Fi i profilów sieci VPN.

-  [Konfigurowanie dostępu do firmowej poczty e-mail przy użyciu profilów poczty e-mail](configure-access-to-corporate-email-using-email-profiles-with-Microsoft-Intune.md)
-  [Połączenia Wi-Fi w usłudze Microsoft Intune](wi-fi-connections-in-microsoft-intune.md)
-  [Połączenia VPN w usłudze Microsoft Intune](vpn-connections-in-microsoft-intune.md)



<!--HONumber=Nov16_HO1-->


