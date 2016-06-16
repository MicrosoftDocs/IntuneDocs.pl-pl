---
# required metadata

title: Przygotowanie do rejestracji urządzeń | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 44fd4af0-f9b0-493a-b590-7825139d9d40

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Przygotowanie do rejestracji urządzeń w usłudze Microsoft Intune
Aby umożliwić pracownikom zarejestrowanie urządzeń przenośnych w usłudze Intune (w tym urządzeń z systemami [Android](set-up-android-management-with-microsoft-intune.md), [iOS, Mac](set-up-ios-and-mac-management-with-microsoft-intune.md) i [Windows Phone](set-up-windows-phone-management-with-microsoft-intune.md) oraz [komputerów z systemem Windows](set-up-windows-device-management-with-microsoft-intune.md)), należy włączyć rejestrowanie urządzeń. Aby zezwolić na rejestrowanie, należy ustawić urząd zarządzania urządzeniami przenośnymi, skonfigurować portal firmy usługi Intune, przypisać licencje i włączyć rejestrowanie dla platformy urządzeń.

## Ustawianie urzędu zarządzania urządzeniami przenośnymi
Urząd MDM definiuje usługę zarządzania z uprawnieniami do zarządzania zestawem urządzeń. Opcje przeznaczone dla urzędu zarządzania urządzeniami przenośnymi obejmują samą usługę Intune oraz program Configuration Manager z usługą Intune. Jeśli program Configuration Manager zostanie ustawiony jako urząd zarządzania, do zarządzania urządzeniami przenośnymi nie można używać żadnej innej usługi.

>[!IMPORTANT]
> Starannie rozważ, czy chcesz zarządzać urządzeniami przenośnymi za pomocą samej usługi Intune (usługa online) czy przy użyciu programu System Center Configuration Manager z usługą Intune (rozwiązanie oprogramowania lokalnego w połączeniu z usługą online). Po ustawieniu urzędu zarządzania urządzeniami przenośnymi tego urzędu nie będzie można zmienić.



1.  W [konsoli administracyjnej usługi Microsoft Intune](http://manage.microsoft.com) wybierz pozycję **Administracja** &gt;**Zarządzanie urządzeniami przenośnymi**.

2.  Na liście **Zadania** kliknij pozycję **Ustaw urząd zarządzania urządzeniami przenośnymi**. Zostanie otwarte okno dialogowe **Ustawianie urzędu zarządzania urządzeniami przenośnymi** .

    ![Okno dialogowe Ustawianie urzędu MDM](../media/intune-mdm-authority.png)

3.  Usługa Intune zażąda potwierdzenia zamiaru ustawienia usługi Intune jako urzędu zarządzania urządzeniami przenośnymi. Zaznacz pole wyboru, a następnie wybierz przycisk **Tak** , aby zarządzać urządzeniami przenośnymi przy użyciu usługi Microsoft Intune.

## Konfigurowanie portalu firmy usługi Intune

Portal firmy usługi Intune jest miejscem, w którym użytkownicy uzyskują dostęp do danych firmy i mogą wykonywać typowe zadania, takie jak rejestrowanie urządzeń, instalowanie aplikacji i znajdowanie informacji pomocy od działu IT.

> [!TIP] Podczas dostosowywania portalu firmy konfiguracje mają zastosowanie do witryny sieci Web portalu firmy i aplikacji portalu firmy.

Dostosowywanie portalu firmy ułatwia zapewnienie znanego i przydatnego środowiska dla użytkowników końcowych. Aby wykonać to zadanie, wystarczy zalogować się do [konsoli administratora usługi Microsoft Intune](https://manage.microsoft.com) jako administrator dzierżawy lub usługi, wybrać pozycje **Administrator** &gt;**Portal firmy**, a następnie skonfigurować ustawienia portalu firmy.

![Ustawienia portalu firmy w obszarze roboczym Administrator konsoli administracyjnej](../media/cp_sa_cpsetup.PNG)

#### Informacje kontaktowe i zasady zachowania poufności informacji firmy

Nazwa firmy jest wyświetlana jako tytuł portalu firmy. Informacje kontaktowe i szczegóły są wyświetlane na ekranie Kontakt z działem IT w portalu firmy na komputerach użytkowników. Zasady zachowania poufności są wyświetlane, gdy użytkownik kliknie odpowiedni link.

|Nazwa pola|Długość maksymalna|Więcej informacji|
    |----------|------------------------|----------------|
    |Nazwa firmy|40|Ta nazwa jest wyświetlana jako tytuł portalu firmy.|
    |Imię i nazwisko osoby kontaktowej w dziale IT|40|Ta nazwa jest wyświetlana na stronie **Kontakt z działem IT**.|
    |Numer telefonu działu IT|20|Ten numer kontaktowy jest wyświetlany na stronie **Kontakt z działem IT**.|
    |Adres e-mail działu IT|40|Ten adres kontaktowy jest wyświetlany na stronie **Kontakt z działem IT**. Należy wprowadzić prawidłowy adres e-mail w formacie **alias@nazwadomeny.com**.|
    |Dodatkowe informacje|120|Wyświetlane na stronie **Kontakt z działem IT**.|
    |Adres URL zasad zachowania poufności informacji firmy|79|Istnieje możliwość wprowadzenia własnych zasad zachowania poufności informacji, które będą wyświetlane, gdy użytkownik kliknie w portalu firmy linki do informacji o prywatności. Należy wprowadzić prawidłowy adres URL w formacie https://www.contoso.com.|

#### Kontakt z pomocą techniczną
Witryna sieci Web z pomocą techniczną wyświetlana w portalu firmy umożliwia użytkownikom dostęp do pomocy online.

|Nazwa pola|Długość maksymalna|Więcej informacji|
    |----------|------------------------|----------------|
    |Adres URL witryny sieci Web pomocy technicznej|150|Jeśli masz witrynę z pomocą techniczną, którą chcesz udostępnić użytkownikom, podaj tutaj jej adres URL. Adres URL należy wpisać w formacie https://www.contoso.com. Jeśli nie określisz adresu URL, w Portalu firmy w witrynie pomocy technicznej na stronie **Kontakt z działem IT** nie będą wyświetlane żadne informacje.|
    |Nazwa witryny sieci Web|40|Ta nazwa jest przyjazną nazwą wyświetlaną dla adresu URL witryny sieci Web pomocy technicznej. Jeśli zostanie określony tylko adres URL witryny sieci Web pomocy technicznej, ale nie zostanie podana przyjazna nazwa, w portalu firmy na stronie **Kontakt z działem IT** będzie wyświetlany komunikat **Przejdź do witryny sieci Web działu IT**.|


#### Dostosowywanie oznaczeń marki

Portal firmy można dostosować, wprowadzając logo i nazwę firmy, kolor motywu oraz tło.

|Nazwa pola|Więcej informacji|
    |----------|----------------|
    |Kolor motywu|Wybierz kolor motywu, który ma zostać zastosowany dla portalu firmy.|
    |Uwzględnij logo firmowe|Po włączeniu tej opcji możesz przekazać logo firmy, aby było wyświetlane w portalu firmy. Można przekazać dwa logo: jedno wyświetlane, gdy tło portalu firmy jest białe, i drugie — wyświetlane, gdy tło Portalu firmy ma wybrany przez użytkownika kolor motywu. Każdy plik logo musi być w formacie png lub jpg, mieć rozdzielczość maksymalnie 400 x 100 pikseli i mieć rozmiar nie większy niż 750 KB.|
    |Wybierz tło dla aplikacji Portal firmy dla systemu [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)]|To ustawienie ma wpływ wyłącznie na tło w aplikacji Portal firmy systemu [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)].|


Po zapisaniu zmian można użyć linków dostępnych na dole strony **Portal firmy** w konsoli administracyjnej, aby wyświetlić witrynę sieci Web Portal firmy. Tych linków nie można zmienić. Po zalogowaniu użytkownika wyświetlane linki odpowiadają subskrypcjom w portalu firmy.

## Przypisywanie licencji użytkownika usługi Intune

**Portal zarządzania usługi Office 365** umożliwia ręczne dodawanie użytkowników w chmurze oraz przypisywanie licencji do kont użytkowników w chmurze i kont synchronizowanych z lokalnej usługi Active Directory do usługi Azure AD.

1.  Zaloguj się do [portalu zarządzania usługi Office 365](https://portal.office.com/Admin/Default.aspx) przy użyciu poświadczeń administratora dzierżawy.

2.  Wybierz konto użytkownika, do którego chcesz przypisać licencję użytkownika usługi Intune, i zaznacz pole wyboru **Microsoft Intune** we właściwościach konta użytkownika.

3.  Konto użytkownika zostanie dodane do grupy użytkowników usługi Microsoft Intune uprawnionych do korzystania z usługi i rejestrowania urządzeń w systemie zarządzania.

## Konfigurowanie zarządzania urządzeniami
Po skonfigurowaniu urzędu zarządzania urządzeniami przenośnymi należy skonfigurować zarządzanie urządzeniami dla systemów operacyjnych, które chce obsługiwać organizacja. Kroki wymagane do skonfigurowania zarządzania urządzeniami różnią się zależnie od systemu operacyjnego. Na przykład system operacyjny Android nie wymaga wykonywania żadnych czynności w konsoli administracyjnej usługi Intune. Jednak systemy Windows i iOS wymagają relacji zaufania między urządzeniami a usługą Intune, ponieważ tylko wówczas możliwe jest zarządzanie.

> [!div class="op_single_selector"]
- [Konfigurowanie zarządzania systemem Android przy użyciu usługi Microsoft Intune](set-up-android-management-with-microsoft-intune.md)
- [Set up iOS and Mac management with Microsoft Intune](set-up-ios-and-mac-management-with-microsoft-intune.md)
- [Konfigurowanie zarządzania systemem Windows Phone przy użyciu usługi Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md)
- [Konfigurowanie zarządzania urządzeniami z systemem Windows przy użyciu usługi Microsoft Intune](set-up-windows-device-management-with-microsoft-intune.md)

Możesz również:
 - Używanie [konta menedżera rejestracji urządzeń](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) w celu rejestrowania wielu urządzeń
 - [Określanie urządzeń firmowych według numerów IMEI](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) w celu sprawniejszego rejestrowania urządzeń i zasad docelowych


<!--HONumber=Jun16_HO1-->


