---
title: "Uzyskiwanie dostępu do firmowej poczty e-mail przy użyciu profilów poczty e-mail | Microsoft Docs"
description: "Ustawienia profilu poczty e-mail mogą służyć do konfiguracji ustawień dostępu do poczty e-mail dla określonych klientów poczty e-mail na urządzeniach przenośnych."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 10f0cd61-e514-4e44-b13e-aeb85a8e53ae
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e0ecc775f70703574c4e1adf0f0aa204f2745b72
ms.openlocfilehash: 21eee53a4e3674dc28b01311a61dda0d71f9f7fa
ms.lasthandoff: 04/20/2017


---

# <a name="configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune"></a>Konfigurowanie dostępu do firmowej poczty e-mail przy użyciu profilów poczty e-mail w usłudze Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Wiele platform mobilnych zawiera natywnego klienta poczty e-mail, który jest dostarczany jako część systemu operacyjnego. Niektórych z tych klientów można skonfigurować przy użyciu profilów poczty e-mail tak jak opisano w tym temacie.

Ustawienia profilu poczty e-mail mogą służyć do konfiguracji ustawień dostępu do poczty e-mail dla określonych klientów poczty e-mail na urządzeniach przenośnych. Na obsługiwanych platformach można konfigurować natywnych klientów poczty e-mail za pomocą usługi Microsoft Intune w celu umożliwienia użytkownikom dostępu do firmowej poczty e-mail na ich urządzeniach osobistych bez żadnej dodatkowej konfiguracji.

Jeśli potrzebujesz dodatkowej ochrony przed utratą danych, wybierz pozycję [Dostęp warunkowy](restrict-access-to-email-and-o365-services-with-microsoft-intune.md), która kontroluje dostęp do skrzynki pocztowej użytkownika przez dowolnego klienta poczty e-mail, w tym natywnych klientów poczty e-mail.

Administratorzy IT lub użytkownicy mają także możliwość instalowania alternatywnych klientów poczty e-mail (na przykład programu Microsoft Outlook dla systemu Android lub iOS). Ci klienci poczty e-mail mogą nie obsługiwać profilów poczty e-mail i nie można ich konfigurować przy użyciu profilów poczty e-mail usługi Intune.  

Profile poczty e-mail mogą służyć do konfigurowania klienta natywnego poczty e-mail na następujących typach urządzeń:
-    System Windows Phone 8.1 lub nowszy
-    Systemy Windows 10 (dla komputerów), Windows 10 Mobile i nowsze
-    System iOS 8.0 i nowsze
-    KNOX Samsung Standard (4.0 i nowsze)
-    Android for Work (aplikacje poczty e-mail innych firm, aplikacja macierzysta poczty e-mail jest powiązana tylko z profilem osobistym)

Oprócz skonfigurowania konta e-mail na urządzeniu możesz skonfigurować ilość poczty e-mail do synchronizowania, a także, w zależności od typu urządzenia, typy zawartości do synchronizowania.

Jeśli użytkownik zainstalował profil poczty e-mail przed skonfigurowaniem profilu przez usługę Intune, wynik wdrożenia profilu poczty e-mail usługi Intune zależy od platformy urządzenia:

**iOS**<br>Istniejące zduplikowane profile poczty e-mail są wykrywane na podstawie nazwy hosta i adresu e-mail. Zduplikowany profil poczty e-mail utworzony przez użytkownika blokuje wdrożenie profilu utworzonego przez administratora usługi Intune. Jest to powszechny problem, ponieważ użytkownicy systemu iOS zwykle najpierw tworzą profil poczty e-mail, a potem rejestrują urządzenie. Portal firmy informuje użytkownika, że nie jest on zgodny ze względu na ręcznie skonfigurowany profil poczty e-mail, i wyświetla monit o usunięcie tego profilu. Użytkownik powinien usunąć swój profil poczty e-mail, aby można było skonfigurować profil usługi Intune. Aby uniknąć problemu, poleć użytkownikom, aby dokonali rejestracji bez instalowania profilu poczty e-mail i pozwolili usłudze Intune na skonfigurowanie profilu.

**Windows**<br>Istniejące zduplikowane profile poczty e-mail są wykrywane na podstawie nazwy hosta i adresu e-mail. Usługa Intune zastępuje istniejący profil poczty e-mail utworzony przez użytkownika.

**Samsung KNOX**<br>Istniejące zduplikowane profile poczty e-mail są wykrywane na podstawie adresu e-mail i nadpisują je profilami usługi Intune. Jeśli użytkownik skonfiguruje to konto, zostanie ono ponownie zastąpione przez profil usługi Intune. Należy pamiętać, że może to być niejasne dla użytkownika.

Ponieważ system Samsung KNOX nie używa nazwy hosta do identyfikowania profilu, nie zalecamy tworzenia wielu profilów poczty e-mail do użycia dla tego samego adresu e-mail na różnych hostach, ponieważ będą one zastępować siebie nawzajem.

**Android for Work**<br>Usługa Intune udostępnia dwa profile poczty e-mail programu Android for Work, jeden dla aplikacji poczty e-mail Gmail i drugi dla aplikacji poczty e-mail Nine Work. Aplikacje te, dostępne w sklepie Google Play, są instalowane w profilu służbowym urządzenia, dlatego powstanie zduplikowanych profilów jest wykluczone. Obie aplikacje obsługują połączenia z programem Exchange. Aby włączyć łączność za pośrednictwem poczty e-mail, wdróż jedną z tych aplikacji na urządzeniach użytkowników, a następnie utwórz i wdróż odpowiedni profil poczty e-mail. Aplikacje poczty e-mail, takie jak Nine Work, mogą nie być bezpłatne. Sprawdź szczegóły licencji aplikacji lub skontaktuj się z producentem aplikacji, jeśli masz jakieś pytania.

## <a name="secure-email-profiles"></a>Zabezpieczanie profilów poczty e-mail
Profile poczty e-mail można zabezpieczyć przy użyciu certyfikatu lub hasła.

### <a name="certificates"></a>Certyfikaty
Podczas tworzenia profilu poczty e-mail wybierasz profil certyfikatu utworzony wcześniej w usłudze Intune. Jest on znany jako certyfikat tożsamości i jest używany do uwierzytelniania względem profilu zaufanego certyfikatu (lub certyfikatu głównego) w celu określenia, czy urządzenie użytkownika może nawiązać połączenie. Zaufany certyfikat jest wdrażany na komputerze, który uwierzytelnia połączenie poczty e-mail — zwykle jest to natywny serwer poczty.

Aby uzyskać więcej informacji o sposobie tworzenia i używania profilów certyfikatów w usłudze Intune, zobacz [Bezpieczny dostęp do zasobów przy użyciu profilów certyfikatów](secure-resource-access-with-certificate-profiles.md).

### <a name="user-name-and-password"></a>Nazwa użytkownika i hasło
Użytkownik jest uwierzytelniany na natywnym serwerze poczty e-mail przez podanie nazwy użytkownika i hasła.

Hasło nie znajduje się w profilu poczty e-mail, więc użytkownik musi je podać podczas łączenia z kontem e-mail.

### <a name="create-an-email-profile"></a>Tworzenie profilu poczty e-mail

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) wybierz kolejno pozycje **Zasady** &gt; **Dodaj zasady**.

2.  Skonfiguruj jeden z następujących typów zasad:

    -   **Profil poczty e-mail dla systemu Samsung KNOX Standard (w wersji 4.0 lub nowszej)**

    -   **Profil poczty e-mail (system iOS 8.0 i nowsze)**

    -   **Profil poczty e-mail (system Windows Phone 8.1 i nowsze)**

    -   **Profil poczty e-mail (system Windows 10 Desktop oraz Mobile i nowsze)**

    -   **Profil poczty e-mail (program Android for Work — Gmail)**

    -    **Profil poczty e-mail (program Android for Work — Nine Work)**

    Tworzyć i wdrażać można tylko niestandardowe zasady profilu poczty e-mail. Zalecane ustawienia są niedostępne.

3.  Skorzystaj z poniższej tabeli, aby skonfigurować ustawienia profilu poczty e-mail:

|Nazwa ustawienia | Więcej informacji|
| ----------- | --------------- |
    |**Nazwa**|Unikatowa nazwa profilu poczty e-mail.|
    |**Opis**|Opis, który pomaga zidentyfikować ten profil.|
    |**Host**|Nazwa hosta serwera firmy udostępniającego natywną usługę poczty e-mail.|
    |**Nazwa konta**|Nazwa wyświetlana konta e-mail, która będzie wyświetlana użytkownikom na ich urządzeniach.|
    |**Nazwa użytkownika**|Jest to atrybut usługi Active Directory (AD) lub Azure AD, który będzie używany do generowania nazwy użytkownika dla tego profilu poczty e-mail. Wybierz podstawowy adres SMTP, taki jak *user1@contoso.com* lub główną nazwę użytkownika, na przykład *użytkownik1* lub *user1@contoso.com*.|
    |**Adres e-mail**|Wybierz, jak jest generowany adres e-mail użytkownika na poszczególnych urządzeniach. Wybierz pozycję **Podstawowy adres SMTP**, aby użyć podstawowego adresu SMTP użytkownika do logowania do programu Exchange, lub wybierz pozycję **Główna nazwa użytkownika**, aby użyć pełnej głównej nazwy jako adresu e-mail.|
    |**Metoda uwierzytelniania** (program Android for Work, systemy Samsung KNOX i iOS)|Wybierz metodę uwierzytelniania stosowaną w profilu poczty e-mail: **Certyfikaty** lub **Nazwa użytkownika i hasło**.|
    |**Wybierz certyfikat klienta na potrzeby uwierzytelniania klienta (certyfikat tożsamości)** (program Android for Work, systemy Samsung KNOX i iOS)|Wybierz wcześniej utworzony certyfikat SCEP klienta, który będzie używany do uwierzytelniania połączenia z serwerem Exchange. Aby uzyskać więcej informacji o sposobie używania profilów certyfikatów w usłudze Intune, zobacz [Bezpieczny dostęp do zasobów przy użyciu profilów certyfikatów](secure-resource-access-with-certificate-profiles.md). Ta opcja jest wyświetlana tylko wtedy, gdy metoda uwierzytelniania to **Certyfikaty**.|
    |**Użyj szyfrowania S/MIME** (systemy Samsung KNOX i iOS)|Wysyłanie wychodzącej poczty e-mail przy użyciu podpisywania S/MIME.|
    |**Certyfikat podpisywania** (systemy Samsung KNOX i iOS)|Wybierz certyfikat podpisywania, który będzie używany do podpisywania wychodzących wiadomości e-mail. Ta opcja jest wyświetlana tylko wtedy, gdy jest wybrana opcja **Użyj szyfrowania S/MIME**.|
    |**Liczba dni do synchronizowania poczty e-mail**|Wybierz liczbę dni okresu, z którego chcesz synchronizować pocztę e-mail, lub wybierz pozycję **Nieograniczone**, aby synchronizować wszystkie dostępne wiadomości e-mail.|
    |**Harmonogram synchronizacji** (program Android for Work, systemy Samsung KNOX, Windows Phone 8 i nowsze, Windows 10)|Wybierz harmonogram, według którego urządzenia synchronizują dane z serwera programu Exchange. Możesz również wybrać pozycję **W momencie nadejścia nowych wiadomości**, która powoduje synchronizowanie zaraz po odebraniu, lub pozycję **Ręcznie**, jeśli użytkownik urządzenia ma inicjować synchronizację.|
    |**Użyj protokołu SSL**|Użyj komunikacji SSL (Secure Sockets Layer) podczas wysyłania wiadomości e-mail, otrzymywania wiadomości e-mail i komunikacji z serwerem programu Exchange. W przypadku urządzeń z systemem Samsung KNOX 4.0 lub nowszym należy wyeksportować certyfikat SSL serwera programu Exchange i wdrożyć go jako profil zaufanego certyfikatu systemu Android w usłudze Intune. Usługa Intune nie obsługuje uzyskiwania dostępu do tego certyfikatu, jeśli zostanie on zainstalowany na serwerze programu Exchange w inny sposób.|
    |**Typ zawartości do synchronizowania** (wszystkie platformy z wyjątkiem programu Android for Work — Gmail)|Wybierz typy zawartości, które chcesz synchronizować z urządzeniami.|
    |**Zezwalaj na wysyłanie wiadomości e-mail z aplikacji innych firm** (tylko system iOS)|Zezwalaj użytkownikowi na wybranie jego profilu jako domyślnego konta wysyłania poczty e-mail i zezwalaj aplikacjom innych firm na otwieranie poczty e-mail w natywnej aplikacji poczty e-mail, na przykład w celu dołączania plików do wiadomości e-mail.|

> [!IMPORTANT]
>
> Jeśli wdrożono profil poczty e-mail i chcesz zmienić wartości ustawień **Host** lub **Adres e-mail**, usuń istniejący profil poczty e-mail i utwórz nowy z wymaganymi wartościami.

4.  Gdy skończysz, kliknij pozycję **Zapisz zasady**.

Nowe zasady zostaną wyświetlone w węźle **Zasady konfiguracji** w obszarze roboczym **Zasady**.

## <a name="deploy-the-policy"></a>Wdrożenie zasad

1.  W obszarze roboczym **Zasady** wybierz zasady do wdrożenia, a następnie wybierz pozycję **Zarządzaj wdrożeniem**.

2.  W oknie dialogowym **Zarządzanie wdrażaniem** :

    -   **Aby wdrożyć zasady**, wybierz co najmniej jedną grupę, w której chcesz wdrożyć zasady, a następnie wybierz pozycje **Dodaj** &gt; **OK**.

    -   **Aby zamknąć okno dialogowe bez wdrażania** — wybierz pozycję **Anuluj**.

W podsumowaniu stanu i alertach na stronie **Przegląd** obszaru roboczego **Zasady** są pokazane problemy z zasadami, które wymagają Twojej uwagi. Ponadto w obszarze roboczym Pulpit nawigacyjny jest wyświetlane podsumowanie stanu.

> [!NOTE]
> - W przypadku systemu Android for Work upewnij się również, że poza odpowiednim profilem poczty e-mail wdrożono również aplikacje Gmail lub Nine Work.
> - Jeśli chcesz usunąć profil poczty e-mail z urządzenia, zmodyfikuj wdrożenie i usuń wszystkie grupy, których urządzenie jest członkiem. Pamiętaj, że nie można usunąć profilu poczty e-mail w ten sposób w przypadku, gdy jest to jedyny profil poczty e-mail na urządzeniu.
> - W przypadku wprowadzenia zmian w zakresie wdrożonego wcześniej profilu poczty e-mail użytkownicy końcowi mogą zobaczyć monit o zatwierdzenie nowej konfiguracji ich ustawień poczty e-mail.

