---
title: "Archiwum nowości | Microsoft Intune"
description: 
keywords: 
author: Lindavr
manager: jeffgilb
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ed2db991-4729-49a7-a1e6-be2ffa0d03d1
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 805dfa1eeb81f4407066e27f203f315451937f8b
ms.openlocfilehash: acf502bdf73176450157535577047c9428aabfd1


---
## Grudzień 2015
### Zmiany i aktualizacje Portalu firmy oferowanego przez firmę Microsoft
W Portalu firmy w tej wersji wprowadzono następujące zmiany:

**Aplikacja Portal firmy dla systemu Android**

Następujące zmiany wprowadzono w celu zapewnienia zgodności z nowymi wymaganiami firmy Google. Na urządzeniach z systemem Android w wersji 6.0 lub nowszym zostaną wyświetlone dwa następujące komunikaty:
* Zezwolić aplikacji Portal firmy na połączenia telefoniczne i zarządzanie nimi?
* Zezwolić aplikacji Portal firmy na dostęp do zdjęć, multimediów i plików na Twoim urządzeniu?

Następująca tabela zawiera szczegółowe informacje dotyczące tych dwóch komunikatów.



Tekst komunikatu  |Zezwolić aplikacji Portal firmy na połączenia telefoniczne i zarządzanie nimi?  
---------|---------
Znaczenie komunikatu     |  Umożliwia wysłanie numeru telefonu i kodu IMEI urządzenia użytkownika do usługi Intune, gdzie są następnie wyświetlane w konsoli administracyjnej na stronie Sprzęt.   </br></br>**UWAGA: Aplikacja Portal firmy nigdy nie wykonuje połączeń telefonicznych ani nie zarządza nimi.** Tekst komunikatu jest kontrolowany przez firmę Google i nie można go zmienić. </br></br>Aby wyświetlić stronę **Sprzęt**, wybierz pozycję **Grupy** > **Wszystkie urządzenia przenośne** > **Urządzenia**. Wybierz urządzenie użytkownika, a następnie wybierz pozycje **Wyświetl właściwości** > **Sprzęt**.    
Gdzie i kiedy pojawi się komunikat  | Komunikat jest wyświetlany, gdy użytkownik zaloguje się do aplikacji Portal firmy po raz pierwszy w celu rozpoczęcia rejestrowania urządzenia.|         
Co się stanie, gdy użytkownik zezwoli na dostęp  |  Numer telefonu i kod IMEI urządzenia będą wyświetlane na stronie Sprzęt w konsoli administracyjnej. |         
Co się stanie, gdy użytkownik nie zezwoli na dostęp     | Może nadal używać aplikacji Portal firmy i zarejestrować urządzenie, lecz pola numeru telefonu i kodu IMEI urządzenia użytkownika na stronie Sprzęt konsoli administracyjnej będą puste.       </br></br> Podczas drugiego logowania użytkownika do aplikacji Portal firmy po odmowie dostępu w komunikacie zostanie wyświetlone pole wyboru **Nigdy nie pytaj ponownie**. Jego zaznaczenie spowoduje, że komunikat nigdy nie zostanie wyświetlony ponownie.</br></br>Jeśli użytkownik zezwoli na dostęp, lecz potem go odmówi, komunikat zostanie wyświetlony podczas następnego logowania użytkownika do aplikacji Portal firmy po rejestracji.</br></br>Jeśli później użytkownik zdecyduje się zezwolić na dostęp, może wybrać pozycję **Ustawienia** > **Aplikacje** > **Portal firmy** > **Uprawnienia** > **Telefon** i włączyć uprawnienie.
Więcej informacji     |  Dla użytkowników: [Logowanie do aplikacji Portal firmy](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_signin_cp)  </br></br>Dla profesjonalistów IT: informacje w poniższej tabeli znajdują się również w sekcji [Pomaganie użytkownikom w zrozumieniu komunikatów aplikacji Portal firmy](https://technet.microsoft.com/library/dn948527.aspx#BKMK_help_users_understd_msgs)   

Tekst komunikatu  |Zezwolić aplikacji Portal firmy na dostęp do zdjęć, multimediów i plików na Twoim urządzeniu?  
---------|---------
Znaczenie komunikatu     |  Umożliwia urządzeniu zapisywanie dzienników danych na karcie SD urządzenia, co umożliwia przenoszenie dzienników przy użyciu kabla USB.   </br></br>**UWAGA: Aplikacja Portal firmy nigdy nie uzyskuje dostępu do zdjęć, multimediów ani plików użytkownika.** Tekst komunikatu jest kontrolowany przez firmę Google i nie można go zmienić.     
Gdzie i kiedy pojawi się komunikat  | Komunikat jest wyświetlany, gdy użytkownik naciśnie polecenie **Wyślij dane** w celu wysłania dzienników danych do administratora IT.|         
Co się stanie, gdy użytkownik zezwoli na dostęp  |  Dzienniki będą kopiowane na kartę SD. |         
Co się stanie, gdy użytkownik nie zezwoli na dostęp     | Nadal może wysyłać dzienniki danych, ale dzienniki nie będą kopiowane na kartę SD urządzenia.       </br></br> Podczas drugiego logowania użytkownika do aplikacji Portal firmy po odmowie dostępu w komunikacie zostanie wyświetlone pole wyboru **Nigdy nie pytaj ponownie**. Jego zaznaczenie spowoduje, że komunikat nigdy nie zostanie wyświetlony ponownie.</br></br>Jeśli użytkownik zezwoli na dostęp, lecz potem go odmówi, komunikat zostanie wyświetlony podczas następnej próby wysłania dzienników przez użytkownika.</br></br>Jeśli później użytkownik zdecyduje się zezwolić na dostęp, może wybrać pozycję **Ustawienia** > **Aplikacje** > **Portal firmy** > **Uprawnienia** > **Pamięć** i włączyć uprawnienie.
Więcej informacji     |  Dla użytkowników: [wysyłanie diagnostycznych dzienników danych do administratora IT przy użyciu poczty e-mail](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_send_diag_logs)  </br></br>Dla profesjonalistów IT: informacje w poniższej tabeli znajdują się również w sekcji [Pomaganie użytkownikom w zrozumieniu komunikatów aplikacji Portal firmy](https://technet.microsoft.com/library/dn948527.aspx#BKMK_help_users_understd_msgs)   


**Aplikacja Portal firmy dla systemu iOS**
* Użytkownicy mogą teraz używać programu Microsoft Outlook lub innych aplikacji do obsługi poczty e-mail na potrzeby wysyłania dzienników diagnostycznych do administratora IT. Wcześniej można było używać tylko aplikacji natywnej.
* Udoskonalono obsługę programu Device Enrollment Program (DEP) firmy Apple i urządzeń rejestrowanych przez firmę. Aby uzyskać szczegółowe informacje, zobacz [Prośba o identyfikację urządzenia przy próbie jego zarejestrowania](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_id_your_device).
* Lista zarejestrowanych urządzeń użytkownika zawiera zielony znacznik obok urządzenia, które jest aktualnie używane przez użytkownika. Przed dodaniem tego znacznika użytkownik nie mógł stwierdzić, którego urządzenia używa.

**Aplikacja Portal firmy dla systemu Windows**

Firma Microsoft automatycznie zbiera anonimowe dane dotyczące wydajności i korzystania z portalu firmy w celu ulepszania swoich produktów i usług. Użytkownicy końcowi mogą wyłączyć zbieranie danych za pomocą ustawienia Użycie danych na urządzeniu, lecz administratorzy nie kontrolują gromadzenia danych i nie mogą zmienić tego ustawienia określonego przez użytkownika końcowego.



## Listopad 2015
### Zarządzanie aplikacjami
Usługa Intune obsługuje zasady zarządzania aplikacjami mobilnymi, które uniemożliwiają wyciek danych firmowych do aplikacji lub usług konsumenckich. W przeszłości te zasady były wymuszane tylko względem aplikacji mobilnych uruchomionych na urządzeniach, które zostały zarejestrowane również do zarządzania urządzeniami przenośnymi (MDM) w usłudze Intune.

Aktualizacja z tego miesiąca powoduje rozszerzenie funkcji zarządzania aplikacjami mobilnymi w usłudze Intune na nowe klasy urządzeń. Obok urządzeń, które są już zarejestrowane w usłudze Intune, zasady zarządzania aplikacjami mobilnymi można również wymuszać względem:
* urządzeń zarządzanych przez inne rozwiązanie do zarządzania urządzeniami przenośnymi;
* urządzeń, które nie są rejestrowane w żadnym systemie zarządzania urządzeniami — zwykle są to urządzenia BYOD (ang. Bring Your Own Device, „przynieś własne urządzenie”).

Więcej informacji na temat nowych funkcji zarządzania aplikacjami mobilnymi można znaleźć w następujących wpisach w blogu:
* [Zwiększanie wydajności przenośnych urządzeń zarządzanych](http://blogs.technet.com/b/microsoftintune/archive/2015/11/17/enhancing-managed-mobile-productivity.aspx)
* [Przedstawiamy nowe funkcje rozwiązań Enterprise Mobility firmy Microsoft](http://blogs.technet.com/b/microsoftintune/archive/2015/11/17/enhancing-managed-mobile-productivity.aspx)

Oto niektóre najważniejsze funkcje i dodatkowe informacje na temat funkcji zarządzania aplikacjami mobilnymi usługi Intune:
* Dane firmowe są odizolowane od danych konsumentów w ramach aplikacji obsługujących usługę Intune, do których należą aplikacje pakietu Office Mobile, aplikacje innych firm, które obsługują pakiet SDK usługi Intune, a także aplikacje biznesowe opakowane w usłudze Intune.
* Dane firmowe można udostępniać (**wycinanie/kopiowanie/wklejanie**) w aplikacjach firmowych, a jednocześnie można zapobiegać udostępnianiu danych firmowych do aplikacji osobistych. Aby uzyskać więcej informacji, przeczytaj temat [Jak zasady MAM chronią dane aplikacji](https://technet.microsoft.com/library/mt627825.aspx). Ten przykładowy scenariusz — [Korzystanie z programu Microsoft Word w pracy i do wykonywania zadań osobistych](https://technet.microsoft.com/library/mt627827.aspx)— pokazuje, jak zapobiegać udostępnianiu danych firmowych aplikacjom osobistym.
* Zasady zapobiegania utracie kluczowych danych, takich jak numery PIN do poszczególnych aplikacji, kontrolki „zapisz jako”, a także dane zarządzane udostępniane między aplikacjami. Listę wszystkich zasad zawiera temat [Tworzenie i wdrażanie zasad zarządzania aplikacjami mobilnymi przy użyciu usługi Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx).
* Wszystkie nowe możliwości są dostępne w programach i usługach Word, Excel, PowerPoint, Outlook, OneNote oraz OneDrive dla Firm, które mogą być zarządzane zarówno po zarejestrowaniu urządzenia, jak i bez jego rejestracji. Funkcje ochrony przed utratą danych są natywnie wbudowane w standardowe aplikacje pakietu Office w sklepie Apple Store oraz sklepie Google Play i nie wymagają opakowywania aplikacji ani pobierania lokalnego.
* Aby dowiedzieć się, jak rozpocząć, zapoznaj się z tematem [Rozpoczynanie pracy z zasadami zarządzania aplikacjami mobilnymi w portalu Azure](https://technet.microsoft.com/library/mt627830.aspx). Aby dowiedzieć się, jak skonfigurować i wdrożyć zasady zarządzania aplikacjami mobilnymi, zapoznaj się z tematem [Tworzenie i wdrażanie zasad zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx).
* Podczas uwierzytelniania użytkowników końcowych w aplikacji przy użyciu poświadczeń firmowych następuje automatyczne skonfigurowanie funkcji ochrony przed utratą danych. Temat [Środowisko pracy użytkownika końcowego w przypadku aplikacji skojarzonych z zasadami zarządzania aplikacjami mobilnymi usługi Microsoft Intune](https://technet.microsoft.com/library/mt627827.aspx) zawiera przykładowe scenariusze dostępu do usługi OneDrive na urządzeniach z systemem iOS i urządzeniach z systemem Android.
* Funkcje te działają na urządzeniach z systemem Android i urządzeniach z systemem iOS.

Lista [Aplikacje firmy Microsoft, których można używać z zasadami zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune](https://technet.microsoft.com/library/dn708489.aspx) została zaktualizowana i zawiera teraz najnowsze aplikacje.

### Zarządzanie urządzeniami
 **Zarządzanie urządzeniami z systemem Mac OS X** Za pomocą usługi Intune można rejestrować urządzenia z systemem Mac OS X i zarządzać nimi. Możesz wykonywać następujące operacje dotyczące urządzeń z systemem Mac OS X:
* Rejestrować urządzenia przeznaczone do zarządzania przez usługę Intune. Zobacz [Konfigurowanie zarządzania systemem iOS i komputerami Mac przez usługę Microsoft Intune](https://technet.microsoft.com/library/dn408185.aspx).
* Kontrolować ustawienia urządzenia za pomocą zasad konfiguracji ogólnej. Zobacz [Ustawienia zasad konfiguracji systemu Mac OS X w usłudze Microsoft Intune](https://technet.microsoft.com/library/mt627823.aspx).
* Wdrażać ustawienia systemu Mac OS X utworzone za pomocą programu Apple Configurator. Zobacz [Ustawienia zasad niestandardowych systemu Mac OS X w usłudze Microsoft Intune](https://technet.microsoft.com/library/mt627820.aspx).
* Gromadzić spisy oprogramowania i sprzętu z urządzeń z systemem Mac OS X. Zobacz [Zrozumienie informacji o urządzeniach dzięki spisowi w usłudze Microsoft Intune](https://technet.microsoft.com/library/jj733634.aspx).
* Uruchamiać nowe raporty zawierające szczegółowe informacje o urządzeniach z systemem Mac OS X, którymi zarządzasz. Zobacz [Informacje o operacjach usługi Microsoft Intune — korzystanie z raportów](https://technet.microsoft.com/library/dn646977.aspx).

**Nowe ustawienia przeglądarki Edge dla urządzeń z systemem Windows 10** Do ogólnych zasad konfiguracji systemu Windows 10 zostały dodane nowe ustawienia, które umożliwiają zarządzanie ustawieniami i funkcjami przeglądarki Microsoft Edge. Zobacz [Ustawienia zasad konfiguracji systemu Windows 10 w usłudze Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx).

**Profile poczty e-mail** Do urządzeń z systemem Windows 10 Desktop i systemem Windows 10 Mobile zostały dodane nowe zasady profilów poczty e-mail. Zobacz [Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](https://technet.microsoft.com/library/dn646984.aspx).

**Nowe ustawienia zasad zgodności** Do listy zasad zgodności zostały dodane następujące nowe ustawienia zasad zabezpieczeń i systemowych:
* Aby upewnić się, że urządzenia z systemem Windows 8.1 lub z nowszymi wersjami, które uzyskują dostęp do zasobów firmy, mają zainstalowane najnowsze aktualizacje, należy użyć ustawienia **Wymagaj automatycznych aktualizacji**. Można również określić typ aktualizacji, które będą instalowane automatycznie — mogą to być wszystkie aktualizacje oznaczone jako ważne albo wszystkie aktualizacje oznaczone jako ważne lub zalecane. Pełną listę ustawień zasad zachowania zgodności zawiera temat [Zarządzanie zasadami zgodności urządzeń w usłudze Microsoft Intune](https://technet.microsoft.com/library/dn705843.aspx).
* Nowe ustawienie **Wymagaj hasła, gdy urządzenie powraca ze stanu bezczynności** w połączeniu z istniejącym ustawieniem **Liczba minut braku aktywności, zanim będzie wymagane hasło** umożliwia utworzenie ustawienia zgodności, które wymaga, aby użytkownik końcowy wprowadził hasło w celu korzystania z urządzenia, które było nieaktywne przez pewien czas.

**Nowe opcje zasad dostępu warunkowego** Zasady dostępu warunkowego można stosować do **wszystkich użytkowników** w ramach nowych albo istniejących zasad dostępu warunkowego. Wszyscy użytkownicy posiadający licencje na usługę Intune i usługi Office 365 będzie musieli zarejestrować swoje urządzenia, a jeśli platforma urządzenia nie jest obsługiwana przez usługę Intune, wówczas dostęp będzie zablokowany dla aplikacji klienckich, które korzystają z [logowania opartego na uwierzytelnianiu w usłudze Active Directory (nowoczesnego uwierzytelniania)](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/).

Można również określić, że zasady dostępu warunkowego będą obowiązywać dla **wszystkich platform**.  Każda aplikacja kliencka korzystająca z [logowania opartego na uwierzytelnianiu w usłudze Active Directory (nowoczesne uwierzytelnianie)](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/) będzie podlegała zasadom dostępu warunkowego, a jeśli dana platforma nie jest aktualnie obsługiwana w usłudze Intune, wówczas będzie ona zablokowana.

### Zmiany i aktualizacje Portalu firmy oferowanego przez firmę Microsoft
W aplikacjach Portalu firmy w tej wersji wprowadzono następujące zmiany:

* **Android**: do aplikacji Portal firmy dla systemu Android został dodany ekran powitalny, aby ułatwić użytkownikom zrozumienie przeznaczenia aplikacji Portal firmy. Ten ekran ma na celu zmniejszenie liczby pobrań aplikacji przez użytkowników, których przedsiębiorstwa nie są subskrybentami usługi Intune.

* **iOS**: usługa Intune obsługuje teraz rejestrowanie urządzeń z systemem Mac OS X przy użyciu [witryny sieci Web portalu firmy](https://portal.manage.microsoft.com). Instrukcje zawiera temat [Rejestrowanie urządzenia z systemem Mac OS X w usłudze Intune](https://technet.microsoft.com/library/mt598622.aspx).

* **Witryna sieci Web portalu firmy**: użytkownicy, którzy zarejestrowali urządzenie w usłudze Intune, mogą teraz zresetować kod dostępu za pomocą opcji **Resetuj kod dostępu** w witrynie sieci Web Portal firmy. Wcześniej tylko administratorzy IT mogli resetować kody dostępu użytkowników. Opcja Resetuj kod dostępu nie jest obsługiwana na urządzeniach z systemami Windows 8.1 i Windows RT i jest dostępna tylko wtedy, gdy urządzenia zostały zarejestrowane za pomocą oprogramowania do zarządzania urządzeniami przenośnymi (MDM) lub oprogramowania MDM programu Exchange ActiveSync. Instrukcje użytkownika zawiera temat [Resetowanie kodu dostępu](https://technet.microsoft.com/library/mt590895.aspx).

### Zmiany dotyczące licencjonowania administratorów globalnych
W październiku poinformowaliśmy, że administratorzy globalni (nazywani także administratorami dzierżawy) mogą nadal wykonywać administracyjne zadania bieżące bez oddzielnej licencji na usługę Intune ani pakiet Enterprise Mobility Suite (EMS). Jeśli jednak administratorzy globalni zechcą korzystać z tej usługi na przykład w celu zarejestrowania swoich własnych urządzeń lub urządzeń firmowych albo zechcą korzystać z Portalu firmy w usłudze Intune, wówczas będą potrzebować licencji na usługę Intune lub pakiet EMS, podobnie jak każdy inny użytkownik. Poniżej przedstawiono kilka dodatkowych informacji.
* Portal firmy w usłudze Intune to miejsce, w którym użytkownicy mogą:
    * rejestrować swoje urządzenia,
    * wyświetlać stan swoich urządzeń,
    * pobierać oprogramowanie wdrożone przez administratora globalnego w organizacji,
    * znajdować linki opublikowane przez administratora globalnego dotyczące sposobu kontaktu z działem IT w organizacji.

    [Dowiedz się więcej o Portalu firmy](https://technet.microsoft.com/library/dn646966.aspx#BKMK_CompanyPortal) i o sposobach [dostosowywania Portalu firmy](https://technet.microsoft.com/library/dn646983.aspx#BKMK_ConfigureCompanyPortal).
* Osoba, która zarejestruje się w celu zakupu usługi Intune lub pakietu EMS w imieniu organizacji automatycznie staje się pierwszym administratorem globalnym w danej dzierżawie. Minionej jesieni usługa Intune rozpoczęła automatyczne przypisywanie licencji na usługę Intune lub pakiet EMS temu pierwszemu administratorowi globalnemu w ramach przejścia na [Portal usługi Office 365](http://portal.office.com/) i wycofania [Portalu konta usługi Microsoft Intune](http://account.manage.microsoft.com/). Każdy dodatkowo dodany administrator globalny może nadal wykonywać codzienne zadania administracyjne bez osobnej licencji na usługę Intune i pakiet EMS. Jeśli taki administrator zachowa się jako użytkownik końcowy i zarejestruje własne (albo firmowe) urządzenie lub pobierze oprogramowanie z portalu firmy, wówczas będzie potrzebował licencji, tak jak każdy inny użytkownik.
* Ta zmiana będzie wprowadzana fazami i zacznie obowiązywać od stycznia 2016 r.
* Dla partnerów firmy Microsoft ta zmiana nie powinna wpłynąć na możliwość administrowania usługą w imieniu klientów. W celu wykonywania zadań użytkownika końcowego użytkownik będzie potrzebował licencji na usługę Intune lub pakiet EMS, która pozwoli na zarejestrowanie urządzenia oraz dostęp do oprogramowania lub pobranie oprogramowania z Portalu firmy.

Jeśli masz pytania dotyczące tej zmiany, możesz skontaktować się z zespołem pomocy technicznej usługi Intune:
* [Kanały pomocy technicznej dla usługi Microsoft Intune](https://technet.microsoft.com/library/jj839713.aspx)
* [Pomoc techniczna ze strony społeczności](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod)

W celu przekazania ogólnej opinii dotyczącej usługi Microsoft Intune, co może obejmować składanie wniosków o zmianę projektu (DCR) i zgłaszanie usterek, odwiedź [witrynę UserVoice dotyczącą usługi Intune](https://microsoftintune.uservoice.com/).


### Co nowego w dokumentacji usługi Intune — listopad 2015 r.
**Nowa zawartość**
* [Ustawienia zasad konfiguracji systemu Mac OS X w usłudze Microsoft Intune](https://technet.microsoft.com/library/mt627823.aspx): kontrola ustawień i funkcji urządzenia dla urządzeń z systemem Mac OS X.
* [Ustawienia zasad niestandardowych systemu Mac OS X w usłudze Microsoft Intune](https://technet.microsoft.com/library/mt627820.aspx): sposób wdrażania ustawień urządzenia z systemem Mac OS X, które zostały utworzone przy użyciu narzędzia Apple Configurator.
* [Konfigurowanie zasad aplikacji związanych z zapobieganiem utracie danych w usłudze Microsoft Intune](https://technet.microsoft.com/library/mt627825.aspx): zawiera informacje o scenariuszach obsługiwanych przez zasady zarządzania aplikacjami mobilnymi, a także informacje o tym, w jaki sposób zasady chronią dane.
* [Rozpoczynanie pracy z zasadami zarządzania aplikacjami mobilnymi w portalu Azure](https://technet.microsoft.com/library/mt627830.aspx): czego potrzeba, aby rozpocząć korzystanie z portalu Azure w wersji zapoznawczej na potrzeby zasad zarządzania aplikacjami mobilnymi.
* [Tworzenie i wdrażanie zasad zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx): zawiera przewodnik krok po kroku na temat sposobu tworzenia zasad zarządzania aplikacjami mobilnymi w portalu Azure w wersji zapoznawczej.
* [Monitorowanie zasad zarządzania aplikacjami mobilnymi przy użyciu usługi Microsoft Intune](https://technet.microsoft.com/library/mt627824.aspx): informacje dotyczące sposobów monitorowania zasad zarządzania aplikacjami mobilnymi za pomocą portalu Azure w wersji zapoznawczej.
* [Zasady zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune i funkcja „Otwórz w” w systemie iOS](https://technet.microsoft.com/library/mt627821.aspx): informacje o tym, jak zasady zarządzania aplikacjami mobilnymi działają z funkcją „Otwórz w” w systemie iOS.
* [Środowisko pracy użytkownika końcowego w przypadku aplikacji skojarzonych z zasadami zarządzania aplikacjami mobilnymi usługi Microsoft Intune](https://technet.microsoft.com/library/mt627827.aspx): poznaj środowisko pracy użytkownika końcowego, który korzysta z aplikacji powiązanych z zasadami zarządzania aplikacjami mobilnymi.
* [Czyszczenie danych zarządzanych aplikacji firmowych za pomocą usługi Microsoft Intune](https://technet.microsoft.com/library/mt627826.aspx): jak usunąć dane aplikacji firmowych.

**Zawartość zaktualizowana**
* [Ustawienia zasad konfiguracji systemu Windows 10 w usłudze Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx): dodano nowe ustawienia przeglądarki Edge.
* [Konfigurowanie zarządzania systemem iOS i komputerami Mac za pomocą usługi Microsoft Intune](http://technet.microsoft.com/library/dn408185.aspx): dodano informacje o sposobie rejestrowania urządzeń z systemem Mac OS X.
* [Zrozumienie informacji o urządzeniach dzięki spisowi w usłudze Microsoft Intune](https://technet.microsoft.com/library/jj733634.aspx): dodano informacje o spisie gromadzonym z urządzeń z systemem Mac OS X. Ponadto zaktualizowano temat o najnowsze informacje dla wszystkich platform urządzeń.
* [Informacje o operacjach usługi Microsoft Intune — korzystanie z raportów](https://technet.microsoft.com/library/dn646977.aspx): dodano informacje dotyczące dwóch nowych raportów, które służą do wyświetlania informacji o zarządzanych urządzeniach z systemem Mac OS X.
* [Zarządzanie zasadami zgodności urządzeń w usłudze Microsoft Intune](https://technet.microsoft.com/library/dn705843.aspx): dodano informacje o nowych zasadach zgodności wymagających aktualizacji automatycznych i podania hasła, gdy urządzenie powraca ze stanu bezczynności.
* [Zarządzanie dostępem do poczty e-mail za pomocą usługi Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx): dodano informacje o możliwość stosowania zasad dostępu warunkowego dla wszystkich platform i wszystkich użytkowników.
* [Zarządzanie dostępem do usługi SharePoint Online w usłudze Microsoft Intune](https://technet.microsoft.com/library/dn705844.aspx): dodano informacje o możliwość stosowania zasad dostępu warunkowego dla wszystkich platform i wszystkich użytkowników.

## Październik 2015

### Aktualizacje dostępu warunkowego dla lokalnego programu Exchange
**Teraz można zezwolić na dostęp do poczty e-mail w programie Exchange Active Sync zgodnym urządzeniom zarejestrowanym w usłudze Intune, gdy ustawiono globalną regułę programu Exchange na wartość Blokuj lub Kwarantanna** — do chwili obecnej, aby umożliwić dostęp do poczty e-mail na urządzeniach zarejestrowanych i zgodnych, trzeba było ustawić wartość domyślną globalnej reguły programu Exchange na wartość **Zezwalaj**.

Ta aktualizacja usługi usuwa wymóg stosowania wymienionego ustawienia na potrzeby dostępu warunkowego. Jeśli środowisko programu Exchange wymaga, aby domyślna reguła globalna miała wartość **Blokuj/Kwarantanna**, po prostu zaznacz pole wyboru **Przesłoń regułę domyślną** na stronie zasad dostępu warunkowego lokalnego programu Exchange. Temat [Zarządzanie dostępem do poczty e-mail za pomocą usługi Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx) zawiera dodatkowe informacje na temat reguł i wynikających z nich powiadomień dla użytkownika końcowego.

**Nowa obsługa kwarantanny za pomocą jednego kliknięcia** — uprościliśmy obsługę wiadomości e-mail kwarantanny, umożliwiając rejestrowanie za pomocą jednego kliknięcia. Dzięki tej aktualizacji usługi użytkownicy końcowi mogą kliknąć pojedynczy link w wiadomości e-mail kwarantanny, aby zakończyć proces rejestracji w aplikacji Portal firmy.
### Aktualizacje zarządzania urządzeniami przenośnymi i aplikacjami
**Android** — wszystkie funkcje zarządzania usługi Intune obsługują teraz system Android 6.0 (Marshmallow) w sposób przedstawiony w następującym wpisie w blogu: [Microsoft Intune Provides Day 0 Support for Android Marshmallow](http://blogs.technet.com/b/microsoftintune/archive/2015/10/09/microsoft-intune-to-provide-day-0-support-for-android-marshmallow.aspx) (Usługa Microsoft Intune świadczy pomoc techniczną „Day 0” dla systemu Android Marshmallow)

**iOS** — nie możesz już tworzyć nowych wdrożeń aplikacji dla urządzeń z systemem iOS w wersji starszej niż iOS 7.1. Wszystkie istniejące wdrożenia aplikacji na urządzeniach z systemem w wersji starszej niż iOS 7.1 będą w dalszym ciągu działać i będą dostępne do zarządzania za pomocą usługi Intune.

**Windows 10** — usługa Intune teraz obsługuje wdrażanie aplikacji uniwersalnych systemu Windows 10 za pomocą instalatora oprogramowania typu **Pakiet aplikacji systemu Windows**. Szczegółowe informacje i wymagania zawiera temat [Wprowadzenie do wdrażania aplikacji w usłudze Microsoft Intune](http://technet.microsoft.com/en-US/library/dn646955.aspx).


### Zmiany i aktualizacje aplikacji Portalu firmy oferowanych przez firmę Microsoft
W aplikacjach Portal firmy w tej wersji wprowadzono następujące zmiany: **iOS** Dodano nowe przyciski do aplikacji Portal firmy, aby ułatwić użytkownikom wysyłanie dzienników diagnostycznych do administratorów IT:

|Nazwa przycisku|Gdzie jest dostępny|
|------------|---------------|
|Raport|Komunikaty alertów o błędzie|
|Wyślij raport diagnostyczny|Ekran Informacje aplikacji Portal firmy|



## Wrzesień 2015
### Aktualizacje zarządzania urządzeniami przenośnymi i aplikacjami
**Wszystkie funkcje zarządzania systemem iOS obsługują teraz system iOS 9** — aby uzyskać szczegółowe informacje na temat możliwości zarządzania systemem iOS 9, zobacz [ten wpis w blogu](http://blogs.technet.com/b/microsoftintune/archive/2015/09/09/day-zero-support-for-ios-9-with-intune.aspx).

**Nowe zasady konfiguracji aplikacji mobilnych dla systemu iOS** — użyj nowych zasad konfigurowania aplikacji mobilnych, aby automatycznie określić ustawienia, których aplikacja systemu iOS może potrzebować w przypadku jej uruchomienia. Na przykład możesz podać port sieci lub nazwę użytkownika. Aby uzyskać więcej informacji, zobacz [Konfigurowanie aplikacji przy użyciu zasad konfiguracji aplikacji mobilnych w usłudze Microsoft Intune](https://technet.microsoft.com/library/mt481447.aspx).

**Łatwiejsze zarządzanie aplikacjami dla użytkowników systemu iOS 9**
 — w tej wersji możesz objąć zarządzaniem za pomocą usługi Intune już wdrożone aplikacje w przypadku użytkowników systemu iOS 9. W przypadku wcześniejszych wersji systemu iOS po wdrożeniu aplikacji, gdy jej niezarządzana wersja jest już zainstalowana na urządzeniu, nadal jest konieczne monitowanie użytkownika o ręczne odinstalowanie aplikacji, aby usługa Intune mogła zainstalować zarządzaną aplikację.

 Począwszy jednak od tej wersji usługi Intune możesz monitować użytkowników urządzeń z systemem iOS 9 o zezwolenie na przejęcie przez usługę Intune zarządzania aplikacją i zastosowanie przez tę usługę wszelkich odpowiednich zasad zarządzania aplikacjami mobilnymi.

 **Zarządzanie systemem Windows 10** — użyj nowych [ogólnych zasad konfiguracji systemu Windows 10](https://technet.microsoft.com/library/mt404697.aspx), aby skonfigurować hasło, urządzenie, przeglądarkę i inne ustawienia zarejestrowanych urządzeń z systemem Windows 10 i Windows 10 Mobile

 **Tworzenie i wdrażanie aplikacji na zarejestrowanych urządzeniach z systemem Windows 10** — nowy typ instalatora oprogramowania, Instalator Windows korzystający z zarządzania urządzeniami przenośnymi (&#42;.msi), umożliwia tworzenie i wdrażanie aplikacji Instalatora Windows na zarejestrowanych urządzeniach z systemem Windows 10. Szczegółowe informacje zawiera temat [Wprowadzenie do wdrażania aplikacji w usłudze Microsoft Intune](https://technet.microsoft.com/library/dn646955.aspx).

### Zmiany i aktualizacje aplikacji Portalu firmy oferowanych przez firmę Microsoft
W aplikacjach Portalu firmy w tej wersji wprowadzono następujące zmiany:

**iOS**
* Firma Microsoft automatycznie zbiera anonimowe dane dotyczące wydajności i korzystania z portalu firmy w celu ulepszania swoich produktów i usług. Użytkownicy końcowi mogą wyłączyć zbieranie danych za pomocą ustawienia Użycie danych na urządzeniu, lecz administratorzy nie kontrolują gromadzenia danych i nie mogą zmienić tego ustawienia określonego przez użytkownika końcowego.
* Obsługa pełnej rozdzielczości ekranu na telefonach iPhone 6 i 6 Plus.
* Wprowadzono poprawki błędów zwiększające bezpieczeństwo

### Co nowego w dokumentacji usługi Intune — wrzesień 2015
**Nowe tematy**

|Nazwa|Szczegóły|
|----|--------|
|[Ustawienia zasad konfiguracji systemu Windows 10 w usłudze Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx)|Są to nowe zasady konfiguracji, które umożliwiają zarządzanie ustawieniami i funkcjami na urządzeniach z systemem Windows 10 i Windows 10 Mobile.
| [Konfigurowanie aplikacji przy użyciu zasad konfiguracji aplikacji mobilnych w usłudze Microsoft Intune](https://technet.microsoft.com/library/mt481447.aspx)|To nowy typ zasad, który pozwala na automatyczne określanie ustawień, które mogą być wymagane, gdy użytkownik uruchomi aplikację systemu iOS. |

**Zaktualizowane tematy**

|Nazwa|Szczegóły|
|----|-------|
|[Używanie zasad do zarządzania komputerami i urządzeniami przenośnymi w usłudze Microsoft Intune](https://technet.microsoft.com/library/dn743712.aspx)|Zaktualizowano o najnowsze informacje ułatwiające poznanie i tworzenie zasad.|

## Sierpień 2015
### Aktualizacje zarządzania urządzeniami przenośnymi i aplikacjami
* **Warunki i postanowienia** dotyczące rejestracji w usłudze Intune i dostępu do firmy są [teraz zarządzane za pomocą zasad](https://technet.microsoft.com/library/mt405893.aspx). Możesz zastosować różne zestawy warunków i postanowień w celu spełnienia wymagań konkretnej grupy użytkowników. Na przykład możesz wdrożyć warunki i postanowienia w różnych językach dla grup użytkowników zdefiniowanych za pomocą lokalizacji geograficznych. Możesz także [zmodyfikować warunki i postanowienia](https://technet.microsoft.com/library/mt405893.aspx#BKMK_TCVers) , określając, czy numer wersji ma zostać zwiększony, co powoduje, że użytkownicy będą musieli się zgodzić na nowe warunki i postanowienia zanim będą mogli używać portalu firmy.
* **Nazwy pewnej liczby zasad usługi Intune zostały zmienione** , aby zwiększyć ich spójność w ramach produktu i ułatwić wyszukiwanie. Listę wszystkich dostępnych zasad usługi Intune zawiera temat [Używanie zasad do zarządzania komputerami i urządzeniami przenośnymi w usłudze Microsoft Intune](https://technet.microsoft.com/library/dn743712.aspx).
* **Profile certyfikatu PKCS #12 (PFX)** są dostępne dla systemu Android 4.0 lub nowszych oraz systemu Windows 10 (Desktop i Mobile) lub nowszych. Użycie pliku .PFX nie wymaga serwera NDES. Informacje na temat sposobów użycia profilów certyfikatu PFX zawiera temat [Zapewnianie dostępu do zasobów firmy przy użyciu profilów certyfikatów w usłudze Microsoft Intune](http://technet.microsoft.com/library/dn818904.aspx)
* **Ustawienia granic firmowych w systemie Windows 10 Desktop i Mobile** umożliwia szczegółowe konfigurowanie ustawień VPN, zgodnie z opisem w temacie [Pomaganie użytkownikom w nawiązywaniu połączenia z siecią firmową za pomocą profilów sieci VPN](https://technet.microsoft.com/library/dn818905.aspx).
* **Aplikacja usługi OneDrive dla systemu Android teraz obsługuje wiele tożsamości**. Ta i inne aktualizacje zasad zarządzania aplikacjami mobilnymi są opisane na [liście zarządzalnych aplikacji firmy Microsoft](https://technet.microsoft.com/library/dn708489.aspx).
* **Obejście funkcji blokady aktywacji w systemie iOS**. Jeśli urządzenia z systemem iOS należące do firmy są chronione przy użyciu funkcji blokady aktywacji, to przed wymazaniem lub ponownym uaktywnieniem urządzenia będzie konieczne podanie identyfikatora Apple ID i hasła. Może to stanowić problem, gdy użytkownicy odchodzą z firmy i zwracają urządzenia należące do firmy bez wyłączania blokady aktywacji. Aby rozwiązać ten problem, można użyć [obejścia blokady aktywacji w usłudze Intune](https://technet.microsoft.com/library/mt414176.aspx).

### Dostęp warunkowy dla komputerów
Teraz możesz skonfigurować zasady dostępu warunkowego dla komputerów. Umożliwia to aplikacjom komputerowym pakietu Office dostęp do usług Exchange Online i SharePoint Online.
Aby włączyć zasady dostępu warunkowego dla komputerów, komputer musi być przyłączony do domeny lub zgodny.
* Aby uzyskać pełną listę wymagań dotyczących włączania dostępu warunkowego dla komputerów, zobacz sekcję **Wprowadzenie** w temacie [Zarządzanie dostępem do poczty e-mail i programu SharePoint w usłudze Microsoft Intune](http://technet.microsoft.com/library/dn818907).aspx).
* Artykuł [Zarządzanie dostępem do poczty e-mail za pomocą usługi Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx) zawiera opcje, które można skonfigurować, aby włączyć dostęp warunkowy do poczty e-mail.
* Artykuł [Zarządzanie dostępem do usługi SharePoint Online za pomocą usługi Microsoft Intune](https://technet.microsoft.com/library/dn705844.aspx) zawiera opcje, które można skonfigurować, aby włączyć dostęp warunkowy do poczty e-mail.

### Zmiany i aktualizacje aplikacji Portalu firmy oferowanych przez firmę Microsoft
W aplikacjach Portalu firmy w tej wersji wprowadzono następujące zmiany:

**Android**

Użytkownicy teraz będą widzieć instrukcje dotyczące rejestracji po zalogowaniu, jeśli jeszcze nie zarejestrowali swoich urządzeń w funkcji zarządzania.

### Co nowego w dokumentacji usługi Intune — sierpień 2015
**Nowe tematy**

|Tytuł|Szczegóły|
|-----|-------|
|[Ochrona urządzeń z systemem iOS przez obejście blokady aktywacji w usłudze Microsoft Intune](https://technet.microsoft.com/library/mt414176.aspx)|Informacje o sposobie korzystania z usługi Intune do obejścia blokady aktywacji systemu iOS, gdy użytkownik opuści firmę i zwróci zablokowane urządzenie.|

**Zaktualizowane tematy**

|Tytuł|Szczegóły|
|-----|-------|
|[Aplikacje firmy Microsoft, których można używać z zasadami zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune](https://technet.microsoft.com/library/dn708489.aspx)|Zaktualizowano o najnowsze informacje o aplikacjach, które mogą być zarządzane za pomocą zasad zarządzania aplikacjami mobilnymi.
|[Używanie zasad do zarządzania komputerami i urządzeniami przenośnymi w usłudze Microsoft Intune](http://technet.microsoft.com/library/dn743712.aspx)|Zaktualizowano o najnowsze zasady dodane do usługi Intune.|
<!---
## July 2015
July updates for Intune are limited to behind-the-scenes enhancements that allow us to continue providing you with a high-quality service experience. New features are not included in this service update.

### Intune Onboarding benefit
Microsoft offers the Intune Onboarding benefit for eligible plans. The Onboarding benefit lets you work remotely with Microsoft specialists to get your Intune environment ready for use. For more information, see [Microsoft Intune Onboarding benefit description](https://technet.microsoft.com/library/mt228266.aspx)
### Changes and updates to Microsoft Company Portal apps
The following changes have been made to the company portal apps in this release.

**Android**

Microsoft automatically collects anonymous data about the performance and use of the company portal to improve Microsoft products and services. End users can turn off data collection by using the Usage Data setting on their device, but administrators have no control over the data collection and cannot change the end user’s selection for this setting.--->



<!--HONumber=Jul16_HO3-->


