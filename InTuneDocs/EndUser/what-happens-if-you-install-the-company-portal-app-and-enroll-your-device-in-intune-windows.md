---
# required metadata

title: Co się dzieje w przypadku zainstalowania aplikacji Portal firmy i zarejestrowania urządzenia w usłudze Intune? | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: d65e3452-5bbf-4d26-a06e-401ddcc47f39

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: priyar
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Co się dzieje w przypadku zainstalowania aplikacji Portal firmy i zarejestrowania urządzenia w usłudze Intune?

Aby dowiedzieć się, co się dzieje podczas instalacji aplikacji Portal firmy i rejestracji urządzenia, użyj linku znajdującego się powyżej w sekcji „W tym artykule” odpowiedniego dla typu używanego urządzenia. Aby uzyskać informacje o urządzeniach z systemem Windows 10, zobacz [tę stronę](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows10.md).

## Windows 8.1 i Windows RT
Po zainstalowaniu aplikacji Portal firmy i następnie zarejestrowaniu urządzenia z systemem Windows 8.1 Enterprise lub Professional albo Windows RT w usłudze Intune przy użyciu tej aplikacji można używać aplikacji Portal firmy, aby:

-   Uzyskiwać dostęp do firmowej sieci, poczty e-mail i plików służbowych

-   Pobierać aplikacje firmowe z Portalu firmy

-   Automatycznie konfigurować firmowe konto e-mail

-   Przywracać ustawienia fabryczne telefonu w przypadku jego utraty lub kradzieży

Kroki rejestracji opisano w artykule [Rejestrowanie urządzenia z systemem Windows w usłudze Intune](enroll-your-device-in-intune-windows.md). Aby dowiedzieć się, co Twój administrator IT może zobaczyć na Twoim urządzeniu, zobacz [Jakie dane może wyświetlać mój administrator IT, gdy zarejestruję swoje urządzenie w usłudze Intune?](what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows.md).

W przypadku dodawania komputera:

-   Na komputerze zostanie zainstalowane oprogramowanie umożliwiające administratorowi IT zarządzanie komputerem oraz pozwalające użytkownikowi na uzyskanie dostępu do zasobów firmy, takich jak aplikacje czy informacje pomocy technicznej. Administrator IT może automatycznie aktualizować to oprogramowanie.

-   Na komputerze można zainstalować program Intune Endpoint Protection. To oprogramowanie, które wyszukuje wirusy i złośliwe oprogramowanie.

-   Administrator IT może pobrać spis wszystkich programów zainstalowanych na komputerze, włącznie z oprogramowaniem zainstalowanym przez użytkownika.

-   Konieczne może być zaakceptowanie warunków i postanowień.

-   Administrator IT może zbierać lub usuwać dane z dysku twardego komputera. Administrator IT może również usunąć cały dysk twardy.

-   Administrator IT może instalować na komputerze aplikacje i aktualizacje.

-   Administrator IT może wprowadzać zasady na komputerze. Od użytkownika może być na przykład wymagane, aby ustawił na komputerze hasło lub numer PIN, co w przypadku zbyt wielu prób z podaniem nieprawidłowego hasła może spowodować zablokowanie dostępu do komputera lub usunięcie wszystkich danych z dysku twardego.

## Windows Phone 8.1 i Windows Phone 8
Po zainstalowaniu aplikacji Portal firmy i następnie zarejestrowaniu urządzenia z systemem Windows Phone 8.1 lub Windows Phone 8 w usłudze Intune przy użyciu tej aplikacji można używać aplikacji Portal firmy, aby:

-   Uzyskiwać dostęp do firmowej sieci, poczty e-mail i plików służbowych

-   Pobierać aplikacje firmowe z Portalu firmy

-   Automatycznie konfigurować firmowe konto e-mail

-   Przywracać ustawienia fabryczne telefonu w przypadku jego utraty lub kradzieży

Kroki rejestracji opisano w artykule [Rejestrowanie urządzenia z systemem Windows w usłudze Intune](enroll-your-device-in-intune-windows.md). Aby dowiedzieć się, co Twój administrator IT może zobaczyć na Twoim urządzeniu, zobacz [Jakie dane może wyświetlać mój administrator IT, gdy zarejestruję swoje urządzenie w usłudze Intune?](what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows.md).

Dodanie urządzenia z systemem Windows Phone spowoduje nadanie administratorowi IT uprawnień dostępu do tego urządzenia. Administratorzy mogą wykonywać następujące czynności:

-   Resetować urządzenie do domyślnych ustawień fabrycznych. Jest to przydatne w przypadku utracenia lub kradzieży urządzenia.

-   Usuń wszystkie dane dotyczące firmy oraz zainstalowane aplikacje biznesowe. Dane osobowe oraz ustawienia użytkownika nie zostaną usunięte.

-   Wymagać ustawienia na urządzeniu hasła lub numeru PIN, co w przypadku zbyt wielu prób z podaniem nieprawidłowego hasła może spowodować zablokowanie dostępu do urządzenia lub jego zresetowanie do domyślnych ustawień fabrycznych (co może obejmować usunięcie danych).

-   Wymusić zaszyfrowanie wszystkich danych na urządzeniu. Pozwala to chronić dane w przypadku utracenia lub kradzieży urządzenia.

-   Wymagać od użytkownika zaakceptowania postanowień.

-   Wyłączyć kartę SD.

-   Instalować na urządzeniu aktualizacje aplikacji. Dotyczy to tylko aktualizacji. Administrator IT nie może wymusić zainstalowania na urządzeniu nowych aplikacji, ale użytkownik może zainstalować aplikacje dostępne w portalu firmy.

-   Po dodaniu urządzenia do portalu firmy co około 8 godzin będą wykonywane następujące czynności:

    -   Pobieranie wszystkich aktualizacji aplikacji lub zasad udostępnionych przez administratora IT.

    -   Wysyłanie wszystkich aktualizacji spisu sprzętu.

    -   Wysyłanie wszystkich aktualizacji spisu aplikacji firmowych.

## Windows 7 i Vista
Po zainstalowaniu aplikacji Portal firmy i następnie zarejestrowaniu urządzenia z systemem Windows 7 lub Vista w usłudze Intune przy użyciu tej aplikacji, można używać aplikacji Portal firmy, aby:

-   Uzyskiwać dostęp do firmowej sieci, poczty e-mail i plików służbowych

-   Pobierać aplikacje firmowe z Portalu firmy

-   Automatycznie konfigurować firmowe konto e-mail

-   Przywracać ustawienia fabryczne telefonu w przypadku jego utraty lub kradzieży

Aby dowiedzieć się, co Twój administrator IT może zobaczyć na Twoim urządzeniu, zobacz [Jakie dane może wyświetlać mój administrator IT, gdy zarejestruję swoje urządzenie w usłudze Intune?](what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows.md).

W przypadku dodawania komputera:

-   Na komputerze zostanie zainstalowane oprogramowanie umożliwiające administratorowi IT zarządzanie komputerem oraz pozwalające użytkownikowi na uzyskanie dostępu do zasobów firmy, takich jak aplikacje czy informacje pomocy technicznej. Administrator IT może automatycznie aktualizować to oprogramowanie.

-   Na komputerze można zainstalować program Intune Endpoint Protection. To oprogramowanie, które wyszukuje wirusy i złośliwe oprogramowanie.

-   Administrator IT może pobrać spis wszystkich programów zainstalowanych na komputerze, włącznie z oprogramowaniem zainstalowanym przez użytkownika.

-   Konieczne może być zaakceptowanie warunków i postanowień.

-   Administrator IT może zbierać lub usuwać dane z dysku twardego komputera. Administrator IT może również usunąć cały dysk twardy.

-   Administrator IT może instalować na komputerze aplikacje i aktualizacje.

-   Administrator IT może wprowadzać zasady na komputerze. Od użytkownika może być na przykład wymagane, aby ustawił na komputerze hasło lub numer PIN, co w przypadku zbyt wielu prób z podaniem nieprawidłowego hasła może spowodować zablokowanie dostępu do komputera lub usunięcie wszystkich danych z dysku twardego.

Jeśli masz pytania i nie możesz znaleźć informacji kontaktowych administratora IT, sprawdź, czy są one dostępne w [witrynie sieci Web Portal firmy](http://portal.manage.microsoft.com).

### Zobacz także
[Korzystanie z urządzenia z systemem Windows i usługi Intune](using-your-windows-device-with-intune.md)


<!--HONumber=Jun16_HO1-->


