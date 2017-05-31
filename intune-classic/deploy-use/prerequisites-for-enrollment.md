---
title: "Wymagania wstępne dotyczące rejestracji urządzeń przenośnych | Microsoft Docs"
description: "Skonfiguruj wymagania wstępne dotyczące zarządzania urządzeniami przenośnymi (MDM, mobile device management) i przygotuj się do rejestrowania różnych systemów operacyjnych."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 44fd4af0-f9b0-493a-b590-7825139d9d40
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 6877c5263f3c97b9cff295d62d39a365027151eb
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---

# <a name="prerequisites-for-mobile-device-management-in-intune"></a>Wymagania wstępne dotyczące zarządzania urządzeniami przenośnymi w usłudze Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Wykonanie poniższych czynności pozwala umożliwić pracownikom rejestrowanie ich urządzeń przenośnych w usłudze Intune. Te same kroki umożliwiają zarządzanie urządzeniami należącymi do firmy.

|Kroki|Szczegóły|  
|-----------|-------------|  
|**Krok 1.** [Włączanie połączeń](#step-1-enable-connections)|Upewnienie się, że skonfigurowano niestandardową nazwę domeny i komunikację sieciową|  
|**Krok 2.** [Ustawianie urzędu zarządzania urządzeniami przenośnymi](#step-2-set-mdm-authority)|Urząd zarządzania urządzeniami przenośnymi definiuje usługę przypisaną do urządzeń|
|**Krok 3.** [Tworzenie grup](#step-3-create-groups)|Skonfigurowanie dla użytkownika ustawień dotyczących aplikacji Portal firmy|  
|**Krok 4.** [Konfigurowanie aplikacji Portal firmy](#step-4-configure-company-portal)|Skonfigurowanie dla użytkownika ustawień dotyczących aplikacji Portal firmy|  
|**Krok 5.** [Przypisywanie licencji użytkownika](#step-5-assign-user-licenses)|Przypisanie użytkownikom licencji usługi Intune umożliwiających zarejestrowanie urządzeń|
|**Krok 6.** [Włączanie rejestracji](#step-6-enable-enrollment)|Włączenie specyficznych dla platformy ustawień dotyczących zarządzania w systemach iOS oraz Windows. Urządzenia z systemem Android nie wymagają dodatkowej konfiguracji.|
|**Krok 7.** [Następne kroki](#step-7-next-steps)|Włączenie specyficznych dla platformy ustawień dotyczących zarządzania w systemach iOS oraz Windows. Urządzenia z systemem Android nie wymagają dodatkowej konfiguracji.|

Szukasz usługi Intune z programem Configuration Manager?
> [!div class="button"]
[Zobacz dokumentację programu SCCM >](https://docs.microsoft.com/sccm/mdm/deploy-use/setup-hybrid-mdm)

## <a name="step-1-enable-connections"></a>Krok 1. Włączanie połączeń

Przed włączeniem rejestrowania urządzeń przenośnych należy wykonać następujące czynności:
- [Przegląd wymaganych sieciowych adresów URL i portów](../get-started/network-bandwidth-use.md)
- [Dodanie i zweryfikowanie nazwy domeny](../get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2.md)

## <a name="step-2-set-mdm-authority"></a>Krok 2. Ustawianie urzędu zarządzania urządzeniami przenośnymi
Urząd MDM definiuje usługę zarządzania z uprawnieniami do zarządzania zestawem urządzeń. Opcje przeznaczone dla urzędu zarządzania urządzeniami przenośnymi obejmują samą usługę Intune oraz program Configuration Manager z usługą Intune. Jeśli program Configuration Manager zostanie ustawiony jako urząd zarządzania, do zarządzania urządzeniami przenośnymi nie można używać żadnej innej usługi.

>[!IMPORTANT]
> Starannie rozważ, czy chcesz zarządzać urządzeniami przenośnymi za pomocą samej usługi Intune (usługa online) czy przy użyciu programu System Center Configuration Manager z usługą Intune (rozwiązanie oprogramowania lokalnego w połączeniu z usługą online). Po ustawieniu urzędu zarządzania urządzeniami przenośnymi nie możesz go zmienić bez kontaktu z pomocą techniczną firmy Microsoft. Instrukcje znajdziesz w sekcji [Co należy zrobić, jeśli wybrano błędne ustawienie urzędu certyfikacji MDM](#what-to-do-if-you-choose-the-wrong-mdm-authority-setting).


1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) wybierz pozycję **Administracja** &gt; **Zarządzanie urządzeniami przenośnymi**.

2.  Na liście **Zadania** kliknij pozycję **Ustaw urząd zarządzania urządzeniami przenośnymi**. Zostanie otwarte okno dialogowe **Ustawianie urzędu zarządzania urządzeniami przenośnymi** .

    ![Okno dialogowe Ustawianie urzędu MDM](../media/intune-mdm-authority.png)

3.  Usługa Intune zażąda potwierdzenia zamiaru ustawienia usługi Intune jako urzędu zarządzania urządzeniami przenośnymi. Zaznacz pole wyboru, a następnie wybierz przycisk **Tak**, aby zarządzać urządzeniami przenośnymi przy użyciu usługi Microsoft Intune.

## <a name="step-3-create-groups"></a>Krok 3. Tworzenie grup

Za pomocą utworzonych grup użytkowników i urządzeń można uprościć zarządzanie wdrożonymi aplikacjami, zasadami i zasobami firmy oraz usprawnić tworzenie grup docelowych dla nich. [Dowiedz się, jak utworzyć grupy](use-groups-to-manage-users-and-devices-with-microsoft-intune.md#create-groups).

## <a name="step-4-configure-company-portal"></a>Krok 4. Konfigurowanie aplikacji Portal firmy

Portal firmy usługi Intune jest miejscem, w którym użytkownicy uzyskują dostęp do danych firmy i mogą wykonywać typowe zadania, takie jak rejestrowanie urządzeń, instalowanie aplikacji i znajdowanie informacji pomocy od działu IT.

> [!TIP]
> Podczas dostosowywania Portalu firmy konfiguracje mają zastosowanie do witryny sieci Web Portal firmy i aplikacji Portal firmy.

Dostosowywanie portalu firmy ułatwia zapewnienie znanego i przydatnego środowiska dla użytkowników końcowych. Aby wykonać to zadanie, wystarczy zalogować się do [konsoli administratora usługi Microsoft Intune](https://manage.microsoft.com) jako administrator dzierżawy lub usługi, wybrać pozycje **Administrator** &gt; **Portal firmy**, a następnie skonfigurować ustawienia portalu firmy.

![Ustawienia portalu firmy w obszarze roboczym Administrator konsoli administracyjnej](../media/cp_sa_cpsetup.PNG)

### <a name="company-contact-information-and-privacy-statement"></a>Informacje kontaktowe i zasady zachowania poufności informacji firmy

Nazwa firmy jest wyświetlana jako tytuł portalu firmy. Informacje kontaktowe i szczegóły są wyświetlane na ekranie Kontakt z działem IT w portalu firmy na komputerach użytkowników. Zasady zachowania poufności informacji są wyświetlane, gdy użytkownik kliknie odpowiedni link.

|Nazwa pola|Długość maksymalna|Więcej informacji|
    |----------|------------------------|----------------|
    |Nazwa firmy|40|Ta nazwa jest wyświetlana jako tytuł portalu firmy. **Uwaga**: tylko znaki alfanumeryczne. To pole nie obsługuje znaków specjalnych.|
    |Imię i nazwisko osoby kontaktowej w dziale IT|40|Ta nazwa jest wyświetlana na stronie **Kontakt z działem IT**.|
    |Numer telefonu działu IT|20|Ten numer kontaktowy jest wyświetlany na stronie **Kontakt z działem IT**.|
    |Adres e-mail działu IT|40|Ten adres kontaktowy jest wyświetlany na stronie **Kontakt z działem IT**. Należy wprowadzić prawidłowy adres e-mail w formacie **alias@domainname.com**.|
    |Dodatkowe informacje|120|Te informacje są wyświetlane na stronie **Kontakt z działem IT**.|
    |Adres URL zasad zachowania poufności informacji firmy|79|Istnieje możliwość wprowadzenia własnych zasad zachowania poufności informacji, które będą wyświetlane, gdy użytkownik kliknie w portalu firmy linki do informacji o prywatności. Należy wprowadzić prawidłowy adres URL w formacie https://www.contoso.com.|

### <a name="support-contacts"></a>Kontakt z pomocą techniczną
Witryna sieci Web z pomocą techniczną wyświetlana w portalu firmy umożliwia użytkownikom dostęp do pomocy online.

|Nazwa pola|Długość maksymalna|Więcej informacji|
    |----------|------------------------|----------------|
    |Adres URL witryny sieci Web pomocy technicznej|150|Jeśli masz witrynę z pomocą techniczną, którą chcesz udostępnić użytkownikom, podaj tutaj jej adres URL. Adres URL należy wpisać w formacie https://www.contoso.com. Jeśli nie określisz adresu URL, w Portalu firmy w witrynie pomocy technicznej na stronie **Kontakt z działem IT** nie będą wyświetlane żadne informacje.|
    |Nazwa witryny sieci Web|40|Ta nazwa jest przyjazną nazwą wyświetlaną dla adresu URL witryny sieci Web pomocy technicznej. Jeśli zostanie określony tylko adres URL witryny sieci Web pomocy technicznej, ale nie zostanie podana przyjazna nazwa, w portalu firmy na stronie **Kontakt z działem IT** będzie wyświetlany komunikat **Przejdź do witryny sieci Web działu IT**.|


### <a name="company-branding-customization"></a>Dostosowywanie oznaczeń marki

Portal firmy można dostosować, wprowadzając logo i nazwę firmy, kolor motywu oraz tło.

|Nazwa pola|Więcej informacji|
    |----------|----------------|
    |Kolor motywu|Wybierz kolor motywu, który ma zostać zastosowany dla portalu firmy.|
    |Uwzględnij logo firmowe|Po włączeniu tej opcji możesz przekazać logo firmy, aby było wyświetlane w portalu firmy. Można przekazać dwa logo: jedno wyświetlane, gdy tło portalu firmy jest białe, i drugie — wyświetlane, gdy tło Portalu firmy ma wybrany przez użytkownika kolor motywu. Każdy plik logo musi być w formacie png lub jpg, mieć rozdzielczość maksymalnie 400 x 100 pikseli i mieć rozmiar nie większy niż 750 KB.|
    |Wybierz tło dla aplikacji Portal firmy|To ustawienie ma wpływ wyłącznie na tło w aplikacji Portal firmy systemu.|


Po zapisaniu zmian można użyć linków dostępnych na dole strony **Portal firmy** w konsoli administracyjnej, aby wyświetlić witrynę sieci Web Portal firmy. Tych linków nie można zmienić. Po zalogowaniu użytkownika wyświetlane linki odpowiadają subskrypcjom w portalu firmy.

## <a name="step-5-assign-user-licenses"></a>Krok 5. Przypisywanie licencji użytkownika

**Portal zarządzania usługi Office 365** umożliwia ręczne dodawanie użytkowników w chmurze oraz przypisywanie licencji do kont użytkowników w chmurze i kont synchronizowanych z lokalnej usługi Active Directory do usługi Azure Active Directory (Azure AD). [Lokalnych użytkowników można zsynchronizować z usługą Azure AD](../get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3.md#how-to-sync-on-premises-users-with-azure-ad).

1.  Zaloguj się do [portalu zarządzania usługi Office 365](https://portal.office.com/Admin/Default.aspx) przy użyciu poświadczeń administratora dzierżawy.

2.  Wybierz konto użytkownika, do którego chcesz przypisać licencję użytkownika usługi Intune, i zaznacz pole wyboru **Microsoft Intune** we właściwościach konta użytkownika.

3.  Konto użytkownika zostanie dodane do grupy użytkowników usługi Microsoft Intune uprawnionych do korzystania z usługi i rejestrowania urządzeń w systemie zarządzania.

### <a name="to-synchronize-on-premises-users-with-azure-ad"></a>Aby zsynchronizować lokalnych użytkowników z usługą Azure AD

1. [Dodaj sufiks nazwy UPN](https://technet.microsoft.com/library/cc772007.aspx) dla domeny niestandardowej w lokalnej usłudze Active Directory.
2. Ustaw nowy sufiks nazwy UPN dla użytkowników lokalnych, których chcesz zaimportować.
3. Uruchom [synchronizację programu Azure AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) w celu zintegrowania lokalnych użytkowników z usługą Azure AD.
4. Po pomyślnym zsynchronizowaniu informacji o kontach użytkowników można przypisać licencje usługi Microsoft Intune przy użyciu [portalu zarządzania usługi Office 365](https://portal.office.com/Admin/Default.aspx).

## <a name="step-6-enable-enrollment"></a>Krok 6. Włączanie rejestracji
Po skonfigurowaniu urzędu zarządzania urządzeniami przenośnymi należy skonfigurować zarządzanie urządzeniami dla systemów operacyjnych, które chce obsługiwać organizacja. Kroki wymagane do skonfigurowania zarządzania urządzeniami różnią się zależnie od systemu operacyjnego. Na przykład system operacyjny Android nie wymaga wykonywania żadnych czynności w konsoli administracyjnej usługi Intune. Jednak systemy Windows i iOS wymagają relacji zaufania między urządzeniami a usługą Intune, ponieważ tylko wówczas możliwe jest zarządzanie.

Skonfiguruj zarządzanie dla następujących platform:
- [iOS i Mac](set-up-ios-and-mac-management-with-microsoft-intune.md)
- [Android](set-up-android-management-with-microsoft-intune.md)
- [Android for Work](set-up-android-for-work.md)
- [Windows 10 Mobile i Windows Phone](set-up-windows-device-management-with-microsoft-intune.md)
- [Komputery PC i laptopy z systemem Windows](manage-windows-pcs-with-microsoft-intune.md) (oprogramowanie klienckie usługi Intune)

Można również włączyć [rejestrację firmowych urządzeń](manage-corporate-owned-devices.md).

## <a name="step-7-next-steps"></a>Krok 7. Następne kroki

Po włączeniu rejestracji należy skonfigurować zarządzanie pod kątem potrzeb firmy. Poniżej przedstawiono wybrane opcje zarządzania:

- [Wdrażanie zasad umożliwiających zarządzanie ustawieniami i funkcjami urządzeń](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
- [Zapewnianie dostępu do zasobów firmy, takich jak poczta e-mail, sieci Wi-Fi i sieci VPN](enable-access-to-company-resources-with-microsoft-intune.md)
- [Dodawanie aplikacji](add-apps.md) i [wdrażanie aplikacji](deploy-apps.md) na zarządzanych urządzeniach
- [Tworzenie zasad zgodności urządzeń](introduction-to-device-compliance-policies-in-microsoft-intune.md) i [ograniczanie dostępu na podstawie zgodności](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)

## <a name="what-to-do-if-you-choose-the-wrong-mdm-authority-setting"></a>Co należy zrobić, jeśli wybrano błędne ustawienie urzędu certyfikacji MDM

Jeśli zdecydujesz, że wybrane ustawienie urzędu certyfikacji MDM jest nieprawidłowe i trzeba go zmienić, musisz skontaktować się z pomocą techniczną firmy Microsoft. Ustawień nie można zmienić samodzielnie. Przed skontaktowaniem się z pomocą techniczną firmy Microsoft przejrzyj następujące informacje, aby dowiedzieć się, jakich danych będą potrzebować w celu dokonania zmiany.

Urząd certyfikacji MDM można zresetować na trzy możliwe sposoby. W żądaniu pomocy technicznej wybierz metodę najlepiej pasującą do swojej sytuacji. Jeśli wybrany prze Ciebie scenariusz nie znajduje się na liście, zwróć się do pomocy technicznej firmy Microsoft.

Pomoc techniczna firmy Microsoft poprosi Cię o potwierdzenie następujących informacji:

- Identyfikator dzierżawy: domena używana do logowania do usługi (na przykład intune.onmicrosoft.com)
- Urząd certyfikacji MDM, który ma zastąpić poprzedni
- Potwierdzenie wykonania kroków dotyczących wymagań wstępnych wymienionych poniżej

Jeśli korzystasz z rozwiązania umożliwiającego współistnienie, sprawdź listy kontrolne zarówno usługi Intune, jak i Office 365.

### <a name="reset-mdm-authority-from-intune-to-configuration-manager"></a>Resetowanie urzędu certyfikacji MDM z poziomu usługi Intune do programu Configuration Manager

Przed skontaktowaniem się z pomocą techniczną firmy Microsoft w celu zresetowania urzędu certyfikacji MDM wykonaj przedstawione kroki.

- Wycofaj wszystkie urządzenia z konsoli administracyjnej usługi Intune. Nie należy wycofywać urządzenia, na którym przeprowadza się opisane czynności. 
- Usuń łącznik Service To Service Connector (w obszarze **Administracja** > **Zarządzanie urządzeniami przenośnymi** > **Microsoft Exchange**) lub wyłącz łącznik programu Exchange, jeśli został skonfigurowany.
- Usuń rolę Menedżer rejestracji urządzeń, wybierając kolejno pozycje **Administracja** > **Menedżer rejestracji urządzeń**.
- Wyłącz mapowanie grup urządzeń, wybierając kolejno pozycje **Administracja** > **Zarządzanie urządzeniami przenośnymi** > **Mapowanie grup urządzeń**.
- Usuń klucze pobierania lokalnego, wybierając kolejno pozycje **Administracja** > **Zarządzanie urządzeniami przenośnymi** > **Windows** > **Klucze ładowania bezpośredniego**.
- Usuń certyfikat APNs systemu iOS na stronie **Administracja** > **Zarządzanie urządzeniami przenośnymi** > **iOS**.
- Usuń token DEP systemu iOS na stronie **Administracja** > **Zarządzanie urządzeniami przenośnymi** > **iOS**.
- Usuń wszystkie zasady dla urządzeń MDM w obszarze **Zasady** > **Zasady konfiguracji**.
- Usuń wszystkie opublikowane aplikacje dla urządzeń MDM w obszarze **Aplikacje** > **Zarządzane oprogramowanie**.

### <a name="reset-mdm-authority-from-configuration-manager-to-intune"></a>Resetowanie urzędu certyfikacji MDM z poziomu programu Configuration Manager do usługi Intune

Przed skontaktowaniem się z pomocą techniczną firmy Microsoft w celu zresetowania urzędu certyfikacji MDM wykonaj przedstawione kroki.

- Wycofaj wszystkiej urządzenia (zarządzane jako urządzenia przenośne) z konsoli programu Configuration Manager. Nie należy wycofywać urządzenia, na którym przeprowadza się opisane czynności. 
- Usuń wszystkich użytkowników z grupy użytkowników usługi Intune. Wskaż subskrypcji usługi Intune pustą kolekcję użytkowników lub usuń wszystkich użytkowników z kolekcji docelowej.  W pliku CloudUserSync.log sprawdź, że użytkownicy zostali usunięci. 
- Usuń zaznaczenie platformy systemu iOS, aby przeczyścić certyfikat APNs.
- Usuń wszystkie opublikowane aplikacje dla urządzeń MDM.
- Usuń wszystkie zasady dla urządzeń MDM.
- Usuń łącznik usługi Windows Intune z konsoli programu Configuration Manager (dotyczy wyłącznie wersji R2 SP1 lub starszej).
Usuń subskrypcję usługi Intune, klikając prawym przyciskiem myszy subskrypcję i wybierając polecenie **Usuń**.
- Uruchom ponownie usługę programu SMS Executive.
- Prześlij nam dane kilku przykładowych użytkowników, abyśmy mogli zweryfikować czy licencje programu Configuration Manager zostały usunięte po zakończeniu procesu.

### <a name="reset-mdm-authority-from-office-365-to-configuration-manager"></a>Resetowanie urzędu certyfikacji MDM z poziomu usługi Office 365 do programu Configuration Manager

1. Przejdź do witryny [https://protection.office.com](https://protection.office.com).
2. Wybierz kartę **Zasady zabezpieczeń**, a następnie wybierz pozycję **Zarządzanie urządzeniami**.
3. Wycofaj wszystkie urządzenia, wybierając polecenie **Selektywne czyszczenie**. Nie należy wycofywać urządzenia, na którym przeprowadza się opisane czynności. Jeśli selektywne czyszczenie jest wyłączone, nie są wymagane dalsze działania.
4. Wybierz kartę **Zasady zabezpieczeń**, a następnie wybierz pozycję **Zasady zabezpieczeń urządzeń**.
5. Wybierz polecenie **Usuń** dla wszystkich istniejących zasad. Jeśli zasady są w stanie oczekiwania, nie są wymagane dalsze działania.

>[!NOTE]
>Certyfikat usługi APNs dla systemu iOS nie może zostać usunięty i nadal jest dołączony do konta.

### <a name="next-steps-for-mdm-authority-resets"></a>Kolejne kroki związane z resetowaniem urzędu certyfikacji MDM

Po zweryfikowaniu przez pomoc techniczną firmy Microsoft elementów znajdujących się na odpowiedniej liście kontrolnej resetowanie urzędu certyfikacji MDM może potrwać do trzech dni roboczych, ale zazwyczaj jest przeprowadzane w ciągu jednego dnia.

>[!IMPORTANT]
>Nie należy konfigurować subskrypcji, dopóki pomoc techniczna firmy Microsoft nie potwierdzi, że resetowanie zostało zakończone pomyślnie! Przedwczesna konfiguracja może spowodować uszkodzenie i/lub mieć wpływ na możliwości korzystania z usługi Intune.

