---
title: "Uzyskiwanie dostępu do poczty e-mail przy użyciu profilów poczty e-mail | Microsoft Intune"
description: "Ustawienia profilu poczty e-mail mogą służyć do konfiguracji ustawień dostępu do poczty e-mail dla określonych klientów poczty e-mail na urządzeniach przenośnych."
keywords: 
author: Nbigman
manager: Arob98
ms.date: 07/021/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 10f0cd61-e514-4e44-b13e-aeb85a8e53ae
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 72288296d966b9b9fae4fd721b4460528213f626
ms.openlocfilehash: c7a3ca7b0390a001624871342c9aa04802be27ff


---

# Konfigurowanie dostępu do firmowej poczty e-mail przy użyciu profilów poczty e-mail w usłudze Microsoft Intune
Wiele platform urządzeń przenośnych zawiera *natywnego* klienta poczty e-mail, który jest dostarczany jako część systemu operacyjnego.  Niektórych z tych klientów można skonfigurować przy użyciu profilów poczty e-mail opisanych w tym temacie.

Jeśli potrzebujesz dodatkowej ochrony przed utratą danych, wybierz pozycję [Dostęp warunkowy](restrict-access-to-email-and-o365-services-with-microsoft-intune.md), która kontroluje dostęp do skrzynki pocztowej użytkownika dla dowolnego klienta poczty e-mail, w tym klientów natywnych poczty e-mail.

Ustawienia profilu poczty e-mail mogą służyć do konfiguracji ustawień dostępu do poczty e-mail dla określonych klientów poczty e-mail na urządzeniach przenośnych. Większość platform urządzeń przenośnych zawiera *natywnego* klienta poczty e-mail, który jest dostarczany jako część systemu operacyjnego.  Na obsługiwanych platformach można konfigurować klientów natywnych poczty e-mail za pomocą usługi Microsoft Intune w celu umożliwienia użytkownikom dostępu do firmowej poczty e-mail na urządzeniach osobistych bez żadnej konfiguracji.  

Administratorzy IT lub użytkownicy mają także możliwość instalowania alternatywnych klientów poczty e-mail, na przykład programu Microsoft Outlook dla systemu Android lub iOS.  Ci klienci poczty e-mail mogą nie obsługiwać profilów poczty e-mail i nie można ich konfigurować przy użyciu profilów poczty e-mail usługi Microsoft Intune.  

Profile poczty e-mail mogą służyć do konfigurowania klienta natywnego poczty e-mail na następujących typach urządzeń:
-   System Windows Phone 8 lub nowszy
-   Windows 10 Desktop, Windows 10 Mobile i nowsze
-   System iOS 7.1 lub nowszy
-   KNOX Samsung Standard (4.0 i nowsze)


Oprócz konfigurowania konta e-mail na urządzeniu możesz skonfigurować ustawienia synchronizacji, takie jak ilość poczty e-mail do synchronizowania, a także, w zależności od typu urządzenia, typy zawartości do synchronizowania.

## Zabezpieczanie profilów poczty e-mail
Profile poczty e-mail mogą być chronione przy użyciu jednej z dwóch metod:

### Certyfikaty
Podczas tworzenia profilu poczty e-mail wybierasz profil certyfikatu utworzony wcześniej w usłudze Intune. Jest on znany pod nazwą certyfikatu tożsamości i jest używany do uwierzytelniania względem profilu zaufanego certyfikatu (lub certyfikatu głównego) w celu określenia, czy urządzenie użytkownika może nawiązać połączenie. Zaufany certyfikat jest wdrażany na komputerze, który uwierzytelnia połączenie poczty e-mail — zwykle jest to natywny serwer poczty.

Aby uzyskać więcej informacji o sposobie tworzenia i używania profilów certyfikatów w usłudze Intune, zobacz [Bezpieczny dostęp do zasobów przy użyciu profilów certyfikatów](secure-resource-access-with-certificate-profiles.md).

### Nazwa użytkownika i hasło
Użytkownik jest uwierzytelniany na natywnym serwerze poczty przez podanie swojej nazwy użytkownika i hasła.

Hasło nie znajduje się w profilu poczty e-mail, więc użytkownik musi je podać podczas nawiązywania połączenia z kontem e-mail.

### Tworzenie profilu poczty e-mail

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) kliknij pozycje **Zasady** &gt; **Dodaj zasady**.

2.  Skonfiguruj jeden z następujących typów zasad:

    -   **Profil poczty e-mail dla systemu Samsung KNOX Standard (w wersji 4.0 lub nowszej)**

    -   **Profil poczty e-mail (system iOS 7.1 lub nowszy)**

    -   **Profil poczty e-mail (system Windows Phone 8 i nowsze)**

    -   **Profil poczty e-mail (system Windows 10 Desktop oraz Mobile i nowsze)**

    Tworzyć i wdrażać można tylko niestandardowe zasady profilu poczty e-mail. Zalecane ustawienia są niedostępne.

3.  Skorzystaj z poniższej tabeli, aby skonfigurować ustawienia profilu poczty e-mail:
    |Nazwa ustawienia|Więcej informacji|
    |----------------|-----------------------------------------------------------------------------|
    |**Nazwa**|Unikatowa nazwa profilu poczty e-mail.|
    |**Opis**|Opis, który pomaga zidentyfikować ten profil.|
    |**Host**|Nazwa hosta serwera firmy obsługującego usługę natywnej usługi poczty e-mail.|
    |**Nazwa konta**|Nazwa wyświetlana konta e-mail, która będzie wyświetlana użytkownikom na ich urządzeniach.|
    |**Nazwa użytkownika**|Wybierz, jak można uzyskać nazwę użytkownika konta e-mail. Wybierz pozycję **Nazwa użytkownika** w przypadku lokalnego serwera programu Exchange lub pozycję **Nazwa główna użytkownika** w przypadku usługi Office 365.|
    |**Adres e-mail**|Wybierz, jak jest generowany adres e-mail użytkownika na poszczególnych urządzeniach. Wybierz pozycję **Podstawowy adres SMTP**, aby użyć podstawowego adresu SMTP użytkownika do logowania do programu Exchange, lub wybierz pozycję **Główna nazwa użytkownika**, aby użyć pełnej głównej nazwy jako adresu e-mail.|
    |**Metoda uwierzytelniania** (systemy Samsung KNOX i iOS)|Wybierz metodę uwierzytelniania stosowaną w profilu poczty e-mail: **Certyfikaty** lub **Nazwa użytkownika i hasło**.|
    |**Wybierz certyfikat klienta na potrzeby uwierzytelniania klienta (certyfikat tożsamości)** (systemy Samsung KNOX i iOS)|Wybierz wcześniej utworzony certyfikat SCEP klienta, który będzie używany do uwierzytelniania połączenia z serwerem Exchange. Aby uzyskać więcej informacji o sposobie używania profilów certyfikatów w usłudze Intune, zobacz [Bezpieczny dostęp do zasobów przy użyciu profilów certyfikatów](secure-resource-access-with-certificate-profiles.md).<br /><br />Ta opcja jest wyświetlana tylko wtedy, gdy metoda uwierzytelniania to **Certyfikaty**.|
    |**Użyj szyfrowania S/MIME** (systemy Samsung KNOX i iOS)|Wyślij pocztę wychodzącą przy użyciu szyfrowania S/MIME.|
    |**Certyfikat podpisywania** (systemy Samsung KNOX i iOS)|Wybierz certyfikat podpisywania, który będzie używany do podpisywania wychodzących wiadomości e-mail.<br /><br />Ta opcja jest wyświetlana tylko wtedy, gdy jest wybrana opcja **Użyj szyfrowania S/MIME**.|
    |**Liczba dni do synchronizowania poczty e-mail**|Wybierz liczbę dni, z których chcesz zsynchronizować pocztę e-mail, lub wybierz pozycję **Nieograniczone**, aby synchronizować wszystkie dostępne wiadomości e-mail.|
    |**Harmonogram synchronizacji** (systemy Samsung KNOX, Windows Phone 8 i nowsze, Windows 10)|Wybierz harmonogram, według którego urządzenia synchronizują dane z programu Exchange Server. Można również wybrać pozycję **W momencie nadejścia nowych wiadomości**, która powoduje synchronizowanie zaraz po odebraniu, lub pozycję **Ręcznie**, jeśli użytkownik urządzenia ma inicjować synchronizację.|
    |**Użyj protokołu SSL**|Użyj komunikacji SSL (Secure Sockets Layer) podczas wysyłania wiadomości e-mail, otrzymywania wiadomości e-mail i komunikacji z serwerem Exchange.<br /><br />W przypadku urządzeń z systemem Samsung KNOX 4.0 lub nowszym należy wyeksportować certyfikat SSL serwera Exchange i wdrożyć go jako profil zaufanego certyfikatu systemu Android w usłudze Intune. Usługa Intune nie obsługuje uzyskiwania dostępu do tego certyfikatu, jeśli zostanie on zainstalowany na serwerze Exchange w inny sposób.|
    |**Typ zawartości do synchronizowania**|Wybierz typy zawartości, które chcesz synchronizować z urządzeniami.| 
    |**Zezwalaj na wysyłanie wiadomości e-mail z aplikacji innych firm** (tylko system iOS)|Zezwalaj użytkownikowi na wybranie jego profilu jako domyślnego konta wysyłania poczty e-mail i zezwalaj aplikacjom innych firm na otwieranie poczty e-mail w natywnej aplikacji poczty e-mail, na przykład w celu dołączania plików do wiadomości e-mail.|

    > [!IMPORTANT]
    > Jeśli wdrożono profil poczty e-mail i chcesz zmienić wartości ustawień **Host** lub **Adres e-mail**, usuń istniejący profil poczty e-mail i utwórz nowy z wymaganymi wartościami.

4.  Gdy skończysz, kliknij pozycję **Zapisz zasady**.

Nowe zasady zostaną wyświetlone w węźle **Zasady konfiguracji** w obszarze roboczym **Zasady** .

## Wdrożenie zasad

1.  W obszarze roboczym **Zasady** wybierz zasady do wdrożenia, a następnie kliknij pozycję **Zarządzaj wdrożeniem**.

2.  W oknie dialogowym **Zarządzanie wdrażaniem** :

    -   **Aby wdrożyć zasady** — wybierz co najmniej jedną grupę, w której chcesz wdrożyć zasady, a następnie kliknij pozycję **Dodaj** &gt; **OK**.

    -   **Aby zamknąć okno dialogowe bez wdrażania** — kliknij przycisk **Anuluj**.

W podsumowaniu stanu i alertach na stronie **Przegląd** obszaru roboczego **Zasady** są pokazane problemy z zasadami, które wymagają Twojej uwagi. Ponadto w obszarze roboczym Pulpit nawigacyjny jest wyświetlane podsumowanie stanu.

> [!NOTE]
> Jeśli chcesz usunąć profil poczty e-mail z urządzenia, zmodyfikuj wdrożenie i usuń wszystkie grupy, których urządzenie jest członkiem.





<!--HONumber=Jul16_HO3-->


