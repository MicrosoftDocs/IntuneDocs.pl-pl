---
title: Konfigurowanie dostępu do zasobów firmy | Microsoft Docs
description: Opisuje sposób udostępniania urządzenia z systemem iOS do zarządzania przez usługę Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6eeec7aa-1b07-4ce3-894c-13e09b89bdd4
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: c29c01169483b408528db71b1e9bb2b718220ddc
ms.sourcegitcommit: 7f46e9990797bdfa669ccba2077721f1bc70c07e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/04/2018
ms.locfileid: "30755253"
---
# <a name="set-up-access-to-your-company-resources"></a>Konfigurowanie dostępu do zasobów firmy

Twoja firma jest w posiadaniu wielu zastrzeżonych informacji pochodzących z poczty e-mail, plików, sieci i innych źródeł. W celu ochrony tych informacji podczas uzyskiwania przez pracowników dostępu z urządzeń z systemem iOS firma korzysta z programu Microsoft Intune. Pozwala to jej na zarządzanie tymi zasobami, ulepszanie ich zabezpieczeń oraz umożliwianie użytkownikom korzystania z preferowanych urządzeń do wykonania ich pracy.

> [!NOTE]
> Jeśli próbujesz uzyskać dostęp do firmowej poczty e-mail w aplikacji Mail, prawdopodobnie został wyświetlony monit o objęcie urządzenia zarządzaniem w celu jego zabezpieczenia. Aby uzyskać dostęp do poczty e-mail i innych zasobów firmy na swoim urządzeniu z systemem iOS, postępuj zgodnie z poniższymi instrukcjami.

## <a name="before-you-start"></a>Przed rozpoczęciem

- Zadbaj o to, aby zakończyć cały proces niezwłocznie po rozpoczęciu. Wstrzymywanie go przez okres dłuższy niż kilka minut zwykle zatrzymuje postęp i powoduje konieczność ponownego rozpoczęcia.
- Jeśli ten proces zakończy się niepowodzeniem, musisz powrócić do aplikacji Portal firmy, aby spróbować ponownie.
- Upewnij się, że Twoja sieć Wi-Fi działa i że na Twoim urządzeniu działa program Safari.
- Pobierz i zainstaluj aplikację [Portal firmy w usłudze Intune](install-and-sign-in-to-the-intune-company-portal-app-ios.md).


## <a name="using-the-company-portal-app-to-set-up-access-to-company-resources"></a>Korzystanie z aplikacji Portal firmy w celu konfigurowania dostępu do zasobów firmy

|Wyświetlany ekran|Objaśnienie|
|---|---|
|![Ekran logowania aplikacji Portal firmy z przyciskiem „Zaloguj się” w dolnej części.](./media/ios-01-cp-enroll-1802.png)|Otwórz aplikację Portal firmy i naciśnij przycisk **Zaloguj się**.|
|![Monit o zalogowanie się do usługi Azure Active Directory.](./media/ios-02-cp-enroll-1802.png)|Wpisz adres e-mail firmy i hasło, a następnie naciśnij przycisk **Dalej**.|
|![Monit wprowadzenia hasła usługi Azure Active Directory.](./media/ios-03-cp-enroll-1802.png)|Wprowadź hasło, a następnie naciśnij przycisk **Zaloguj się**.|
|![Ekran powitalny ładowania zasobów firmy.](./media/ios-04-cp-enroll-1802.png)|Poczekaj na załadowanie.|
|![Strona warunków i postanowień.](./media/ios-05-cp-enroll-1802.png)|Przeczytaj warunki i postanowienia i naciśnij przycisk **Zaakceptuj wszystkie**.|
|![Ekran konfigurowania dostępu do zasobów firmy. Zarządzanie i ustawienia wymagają obecnie rozpoznania.](./media/ios-06-cp-enroll-1802.png)|Naciśnij opcję **Rozpocznij**, aby rozpocząć proces dopuszczenia urządzenia do uzyskania dostępu do zasobów firmy. Jeśli nie możesz zrobić tego teraz, możesz **odłożyć** proces, jednak oznacza to, że nie będzie można pobrać wiadomości e-mail, dokumentów i innych elementów.|
|![Ekran Elementy widoczne dla firmy.](./media/ios-07-cp-enroll-1802.png)|Możesz **dowiedzieć się więcej** o tym, co jest widoczne dla Twojej firmy, naciskając link na dole ekranu. Jeśli nie chcesz, naciśnij opcję **Kontynuuj**.|
|![Ekran Co dalej.](./media/ios-08-cp-enroll-1802.png)|Na tym ekranie wyświetlony jest opis wszystkich kroków konfiguracji. Aby dokończyć ten proces, musisz wykonać pewne czynności w programie Safari, aplikacji Ustawienia i aplikacji Portal firmy. Naciśnij przycisk **Kontynuuj**.|
|![Ekran ładowania po naciśnięciu opcji Dalej na ekranie Co dalej.](./media/ios-09-cp-enroll-1802.png)|Poczekaj na załadowanie.|
|![Przełączenie do programu Safari w celu dokonania rejestracji.](./media/ios-7-cp-enroll-1711.png)|Nastąpiło przekierowanie do programu Safari w celu uzyskania informacji dotyczących zarządzania dla Twojego urządzenia.|
|![Monit systemowy o zgodę na otwarcie aplikacji Ustawienia.](./media/ios-8-cp-enroll-1711.png)|Naciśnij opcję **Zezwól**, aby otworzyć aplikację Ustawienia w celu pobrania profilu konfiguracji. Ta instalacja ma na celu umożliwienie firmie zarządzanie informacjami firmowymi na Twoim urządzeniu.|
|![Otwarcie profilu w ustawieniach.](./media/ios-9-cp-enroll-1711.png)|Naciśnij przycisk **Zainstaluj**.|
|![Modalne okno dialogowe instalowania profilu u dołu ekranu.](./media/ios-10-cp-enroll-1711.png)|Naciśnij przycisk **Zainstaluj**.|
|![Ekran ładowania w trakcie instalowania profilu.](./media/ios-11-cp-enroll-1711.png)|Poczekaj na załadowanie.|
|![Ekran ostrzegawczy profilu zarządzania.](./media/ios-12-cp-enroll-1711.png)|To ostrzeżenie, napisane przez firmę Apple, pozwala dowiedzieć się więcej na temat typów akcji, które mogą być wykonywane na urządzeniu ze względu na potrzeby zarządzania. Dowiedz się więcej na temat [informacji, które firma może zobaczyć](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md).|
|![Monit systemowy dotyczący zaufania w zarządzaniu zdalnym.](./media/ios-13-cp-enroll-1711.png)|Naciśnij opcję **Ufaj**, aby umożliwić firmie zarządzanie informacjami firmowymi i ustawieniami na Twoim urządzeniu.|
|![Ekran ładowania w trakcie kończenia instalowania profilu.](./media/ios-14-cp-enroll-1711.png)|Poczekaj na załadowanie.|
|![Ekran Profil zainstalowany.](./media/ios-15-cp-enroll-1711.png)|Twój profil jest zainstalowany, a informacje firmowe i ustawienia w Twoim urządzeniu są znacznie bliższe udostępnienia w celu zarządzania nimi.|
|![Przełączenie do programu Safari w celu dokonania rejestracji.](./media/ios-16-cp-enroll-1711.png)|Nastąpiło ponowne przekierowanie do programu Safari, aby zakończyć uzyskiwanie informacji dotyczących zarządzania dla Twojego urządzenia. |
|![Monit systemowy o otwarcie portalu firmy.](./media/ios-17-cp-enroll-1711.png)|Naciśnij pozycję **Otwórz**.|
|![Ekran ładowania zasobów firmy.](./media/ios-21-cp-enroll-1802.png)|Poczekaj na załadowanie.|
|![Wybierz kategorię urządzenia w aplikacji Portal firmy.](./media/ios-22-cp-enroll-1802.png)|Wybierz najlepszą kategorię dla swojego urządzenia. Ma to zazwyczaj związek z osobą, która jest właścicielem tego urządzenia, lub z miejscem, w którym urządzenie znajduje się przez większość czasu.|
|![Kategoria wybrana.](./media/ios-23-cp-enroll-1802.png)||
|![Zarządzanie urządzeniem zakończone powodzeniem; teraz należy zaktualizować ustawienia.](./media/ios-24-cp-enroll-1802.png)|Twoje urządzenie zostało pomyślnie udostępnione do zarządzania. Prawdopodobnie wciąż istnieją ustawienia, takie jak długość hasła, których aktualizacja może być wymagana przez Twoją firmę. Aby kontynuować, naciśnij przycisk **Kontynuuj**.|
|![Potwierdzanie ustawień urządzenia.](./media/ios-25-cp-enroll-1802.png)|Aplikacja Portal firmy sprawdzi, czy jakiekolwiek z Twoich ustawień wymaga zaktualizowania.|
|![Sprawdzanie ustawień zakończone, z nieprawidłową wersją systemu operacyjnego](./media/ios-26-cp-enroll-1802.png)|Aplikacja Portal firmy udostępni instrukcje dotyczące sposobu rozwiązywania wszelkich problemów z ustawieniami. Po zakończeniu rozwiązywania tych problemów, naciśnij opcję **Sprawdź ustawienia**.|
|![Ekran ładowania potwierdzania ustawień urządzenia](./media/ios-27-cp-enroll-1802.png)|Twoje urządzenie będzie sprawdzać, czy Twoje ustawienia zapewniają wystarczający poziom bezpieczeństwa w dostępie do zasobów firmy.|
|![Pomyślnie zarejestrowano i zaktualizowano ustawienia](./media/ios-28-cp-enroll-1802.png)|Gratulacje! Urządzenie jest teraz zarejestrowane w usłudze Intune.|

> [!Note]
> Zanim Twoje urządzenie będzie w pełni zarządzane, może pozostać jeszcze kilka kroków do wykonania. Dowiedz się więcej o [rejestrowaniu urządzenia przy użyciu zarządzania kosztami telekomunikacyjnymi](enroll-your-device-with-telecom-expense-management-ios.md). Jeśli organizacja korzysta z programu Device Enrollment Program firmy Apple, dowiedz się więcej [tutaj](enroll-your-device-dep-ios.md).

Nadal potrzebujesz pomocy? Skontaktuj się z pomocą techniczną Twojej firmy. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://portal.manage.microsoft.com#HelpDeskDialog).
