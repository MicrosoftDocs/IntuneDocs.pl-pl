---
title: Przewodnik Szybki start — bezpłatna wersja próbna usługi Microsoft Intune
titlesuffix: ''
description: Ten przewodnik Szybki start obejmuje utworzenie bezpłatnej subskrypcji wersji próbnej, omówienie obsługiwanych konfiguracji i wymagań sieciowych oraz opcjonalne skonfigurowanie nazwy domeny.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/01/2018
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 195931c0-8208-43bd-b0af-b1f8e469a32c
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2f150db2e1d5fbc8e08bb7f7fcee50f0eda23ca7
ms.sourcegitcommit: 1134ecd733356277b40eb1c7f2b318b36d387e00
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/02/2018
ms.locfileid: "50915686"
---
# <a name="quickstart-try-microsoft-intune-for-free"></a>Przewodnik Szybki start: bezpłatna wersja próbna usługi Microsoft Intune 

Usługa Microsoft Intune pomaga w ochronie danych firmy i pracowników, umożliwiając zarządzanie urządzeniami i aplikacjami. W tym przewodniku Szybki start utworzysz bezpłatną subskrypcję w celu wypróbowania usługi Intune w środowisku testowym.

Usługa Intune umożliwia zarządzanie urządzeniami przenośnymi (MDM, mobile device management) oraz zarządzanie aplikacjami mobilnymi (MAM, mobile app management) z poziomu bezpiecznej usługi opartej na chmurze administrowanej za pomocą portalu platformy Microsoft Azure. Przy użyciu usługi Intune można zadbać o to, aby używane przez pracowników zasoby firmy (dane, urządzenia i aplikacje) były poprawnie skonfigurowane, otwierane i aktualizowane — stosownie do wymagań i zasad zgodności firmy. 

## <a name="prerequisites"></a>Wymagania wstępne
Przed skonfigurowaniem usługi Microsoft Intune przejrzyj poniższe wymagania:

   - [Obsługiwane systemy operacyjne i przeglądarki](supported-devices-browsers.md) 
   - [Przepustowość i wymagania dotyczące konfiguracji sieci](network-bandwidth-use.md)

## <a name="sign-up-for-a-microsoft-intune-free-trial"></a>Rejestrowanie w celu skorzystania z bezpłatnej wersji próbnej usługi Microsoft Intune

Usługę Intune można bezpłatnie testować przez 30 dni. Jeśli masz już konto firmowe, **zaloguj się** przy użyciu tego konta i dodaj usługę Intune do swojej subskrypcji. W przeciwnym razie **zarejestruj** nowe konto, aby korzystać z usługi Intune w swojej organizacji.

> [!IMPORTANT]
> Nie można połączyć istniejącego konta służbowego lub edukacyjnego po zarejestrowaniu nowego konta.

1. Przejdź do strony [wersji próbnej usługi Microsoft Intune](https://go.microsoft.com/fwlink/?linkid=2019088) i wypełnij formularz.

    ![Zrzut ekranu strony internetowej tworzenia konta próbnego usługi Microsoft Intune](./media/account-sign-up-site-full-browser.png)

    Jeśli większość operacji informatycznych i użytkowników korzysta z innych ustawień regionalnych niż Ty, możesz wybrać odpowiednie ustawienia regionalne w obszarze **Kraj lub region**. Platforma Azure używa informacji o ustawieniach regionalnych do udostępniania odpowiednich usług. Tego ustawienia nie można później zmienić.

2. Utwórz konto, używając nazwy swojej firmy z dołączonym tekstem **.onmicrosoft.com**. 

    ![Zrzut ekranu strony internetowej tworzenia konta próbnego usługi Microsoft Intune](./media/account-sign-up-site-user-id.png)

    Jeśli Twoja organizacja ma własną domenę niestandardową, której chcesz używać (bez końcówki **.onmicrosoft.com**), możesz to zmienić w portalu administracyjnym usługi Office 365 zgodnie z opisem w dalszej części tego artykułu.

3. Na końcu procesu rejestracji przejrzyj informacje o swoim nowym koncie.

    ![Obraz przedstawiający informacje o koncie](./media/intune-end-of-sign-up-process.png) 

## <a name="sign-in-to-the-azure-portal"></a>Logowanie się w witrynie Azure Portal

1. Otwórz nowe okno przeglądarki i na pasku adresu wpisz adres **https://portal.azure.com**. 
2. Zaloguj się przy użyciu poświadczeń podanych w procedurze powyżej.

    ![Obraz przedstawiający stronę logowania witryny Azure Portal](./media/azure-portal-signin.png)

3. Aby wyświetlić usługę Microsoft Intune w porcie platformy Azure, wybierz pozycję **Wszystkie usługi** z paska bocznego w lewej części strony.
4. Wyszukaj usługę **Microsoft Intune** w polu filtrowania i wybierz ją.
5. Wybierz ikonę **gwiazdki**, aby dodać usługę Intune na końcu listy ulubionych usług, i otwórz jej pulpit nawigacyjny.

Po utworzeniu konta w celu korzystania z wersji próbnej na adres e-mail podany w procesie tworzenia konta zostanie wysłana wiadomość e-mail zawierająca informacje o koncie. Stanowi ona potwierdzenie, że Twoja wersja próbna jest aktywna.

> [!TIP]
> Praca z witryną Azure Portal może być efektywniejsza w trybie normalnym niż w trybie prywatnym.

## <a name="set-the-mdm-authority-to-intune"></a>Ustawianie usługi Intune jako urzędu MDM

Po zarejestrowaniu się w witrynie Azure Portal i wybraniu usługi Intune może pojawić się pomarańczowy baner wskazujący, że nie ustawiono jeszcze urzędu MDM. Ustawienie urzędu zarządzania urządzeniami przenośnymi (MDM) określa metodę zarządzania urządzeniami. Urząd MDM musi być ustawiony, aby użytkownicy mogli zarejestrować urządzenia na potrzeby zarządzania.

Aby ustawić usługę Intune jako urząd MDM, wykonaj następujące czynności.

1. Otwórz nowe okno przeglądarki i na pasku adresu wpisz adres **https://portal.azure.com**. 
2. Wybierz pozycję **Wszystkie usługi** > **Microsoft Intune**.
3. Wybierz baner wskazujący, że zarządzanie urządzeniami nie zostało włączone, lub, jeśli baner nie zostanie wyświetlony natychmiast, wybierz pozycję **Rejestracja urządzeń**. Blok **Wybór urzędu MDM** zostanie wyświetlony, jeśli zarządzanie urządzeniami nie zostało jeszcze włączone.

    > [!NOTE]
    > Pomarańczowy baner jest wyświetlany tylko wtedy, gdy nie ustawiono jeszcze urzędu MDM.

    ![Obraz bloku Wybór urzędu MDM](./media/choose-mdm-authority.png) 

4. W obszarze **Wybór urzędu MDM** ustaw jako urząd MDM **Urząd MDM usługi Intune**.

Aby uzyskać więcej informacji na temat urzędu MDM, zobacz [Ustawianie urzędu zarządzania urządzeniami mobilnymi](mdm-authority-set.md).

## <a name="configure-your-custom-domain-name-optional"></a>Konfigurowanie niestandardowej nazwy domeny (opcjonalnie)

Jak wspomniano powyżej, jeśli Twoja organizacja ma własną domenę niestandardową, której chcesz używać (bez końcówki **.onmicrosoft.com**), możesz to zmienić w portalu administracyjnym usługi Office 365. Dodasz, zweryfikujesz i skonfigurujesz niestandardową nazwę domeny.  

> [!IMPORTANT]
> Początkowej nazwy domeny **onmicrosoft.com** nie można zmienić ani usunąć. Można dodać, zmienić lub usunąć niestandardowe nazwy domen używane z usługą Intune, aby zapewnić wyraźną tożsamość firmy.

1. Przejdź do [portalu zarządzania usługi Office 365](https://portal.office.com/Admin/Default.aspx) i zaloguj się za pomocą konta administratora.

2. W okienku nawigacji wybierz pozycję **Konfiguracja** > **Domeny** > **Dodaj domenę**.

3. Wpisz niestandardową nazwę domeny. Następnie wybierz pozycję **Dalej**.

   ![Zrzut ekranu z centrum administracji Office 365 z wybranymi opcjami Ustawienia > Domeny oraz dodawaną nową nazwą domeny](./media/domain-custom-add.png)

4. Zweryfikuj swoje prawo własności do wprowadzonej w poprzedniej części domeny. 
    
    Wybranie pozycji **wyślij kod pocztą e-mail** spowoduje wysłanie wiadomości e-mail do zarejestrowanego dla domeny kontaktu. Po otrzymaniu wiadomości e-mail skopiuj kod i wprowadź go w polu z etykietą **Tutaj wprowadź kod weryfikacyjny**. Jeśli kod weryfikacyjny będzie zgodny, domena zostanie dodana do dzierżawy. Wyświetlony adres e-mail może nie wyglądać znajomo. Niektórzy rejestratorzy ukrywają prawdziwy adres e-mail podany podczas rejestrowania domeny.

   ![Zrzut ekranu przedstawiający centrum administracyjne usługi Office 365 — weryfikowanie dodawanej nazwy domeny](./media/domain-custom-verify.png)

   > [!NOTE]
   > Aby uzyskać szczegółowe informacje dotyczące weryfikowania za pomocą rekordu TXT, zobacz [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/Create-DNS-records-at-any-DNS-hosting-provider-for-Office-365-7B7B075D-79F9-4E37-8A9E-FB60C1D95166) (Tworzenie rekordów DNS u dowolnego dostawcy hostingu DNS dla usługi Office 365).

## <a name="admin-experiences"></a>Środowiska pracy administratora

Istnieją dwa portale, których można użyć:
- Pulpit nawigacyjny usługi Intune na platformie Azure ([portal.azure.com](https://portal.azure.com)) umożliwia zapoznanie się z [możliwościami usługi Intune](what-is-intune.md). Zazwyczaj praca odbywa się na pulpicie nawigacyjnym usługi Intune.
- Centrum administracyjne usługi Office 365 ([portal.office.com](https://portal.office.com)) umożliwia dodawanie użytkowników i zarządzanie nimi, jeśli nie używa się w tym celu usługi Azure Active Directory. Możesz również zarządzać innymi aspektami konta, w tym rozliczeniami i pomocą techniczną.

## <a name="next-steps"></a>Następne kroki

W tym przewodniku Szybki start utworzono bezpłatną subskrypcję w celu wypróbowania usługi Intune w środowisku testowym i opcjonalnie skonfigurowano niestandardową nazwę domeny. Aby dowiedzieć się więcej na temat usługi Microsoft Intune, przejdź do kolejnego przewodnika Szybki start w celu dodania użytkowników i przypisania licencji.

> [!div class="nextstepaction"]
> [Tworzenie użytkownika](quickstart-create-user.md)
