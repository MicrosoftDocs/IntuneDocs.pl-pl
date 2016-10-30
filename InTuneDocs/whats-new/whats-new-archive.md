---
title: "Archiwum nowości | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ed2db991-4729-49a7-a1e6-be2ffa0d03d1
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ec77bc20bf429c804cb502bb46fc549d080a94ac
ms.openlocfilehash: 14698e5f40e76e370e178aeb6187d89fbc5cb2bd


---
## Wrzesień 2016
## Nowe funkcje, anonsy i informacje
* [Dostęp warunkowy w systemie Windows](#windows-conditional-access)
* [Obsługa systemu iOS 10](#ios-10-support)
* [Narzędzie opakowujące aplikacje obsługuje zarządzanie aplikacjami mobilnymi bez rejestrowania urządzeń dla systemów Android i iOS](#app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios)
* [Rozpoczęte we wrześniu przejście grup usługi Intune do grup usługi Azure Active Directory](#intune-groups-begin-transitioning-to-azure-active-directory-in-september)
* [Integracja aplikacji Lookout w celu ochrony urządzeń z systemem Android](#lookout-integration-to-protect-android-devices)
* [Aktualizacje aplikacji Portal firmy dla systemów Android, iOS i Windows](#company-portal-updates)
* [Słownik dotyczący usługi Intune](#intune-glossary)
* [Wkrótce](#whats-coming)

## Dostęp warunkowy w systemie Windows
Przy użyciu konsoli administracyjnej usługi Intune można teraz tworzyć zasady dostępu warunkowego, uniemożliwiając komputerom z systemem Windows dostęp do usług Exchange Online i SharePoint Online. Zasady dostępu warunkowego można też tworzyć w celu blokowania dostępu do aplikacji klasycznych pakietu Office oraz aplikacji uniwersalnych.

## Obsługa systemu iOS 10
Istniejące scenariusze dotyczące zarządzania urządzeniami przenośnymi i aplikacjami mobilnymi w usłudze Intune mają zastosowanie w systemie iOS 10. Aby uzyskać porady, zobacz [Blog zespołu pomocy technicznej usługi Intune](https://blogs.technet.microsoft.com/intunesupport/2016/09/13/support-tip-intune-support-for-ios-10/).

## Narzędzie opakowujące aplikacje obsługuje zarządzanie aplikacjami mobilnymi bez rejestrowania urządzeń dla systemów Android i iOS
Narzędzie opakowujące aplikacje dostępne w ramach usługi Intune to narzędzie wiersza polecenia służące do obsługi aplikacji biznesowych do zarządzania aplikacjami mobilnymi w usłudze Intune dla systemów iOS i Android. Jest to najprostszy sposób uwzględnienia w swojej aplikacji zestawu SDK do zarządzania aplikacjami mobilnymi w usłudze Intune. Dzięki temu aplikacja może wymuszać stosowanie zasad zarządzania aplikacjami mobilnymi wdrożonych za pomocą usługi Intune. Za pomocą zasad zarządzania aplikacjami mobilnymi można:

1. Szyfrować dane aplikacji.
2. Wymagać wprowadzania numeru PIN podczas uruchamiania aplikacji przez pracownika przetwarzającego informacje.
3. Zezwalać aplikacji na przesyłanie danych tylko do innych aplikacji zarządzanych.
4. Uniemożliwić aplikacji tworzenie kopii zapasowej danych w systemie Android oraz usługach iTunes i iCloud.
5. Zezwalać na wycinanie, kopiowanie i wklejanie wyłącznie do oraz z innych aplikacji zarządzanych.

Publiczna wersja zapoznawcza zaktualizowanego narzędzia opakowującego aplikacje w usłudze Intune obsługuje teraz zarządzanie aplikacjami mobilnymi bez rejestrowania urządzeń w wewnętrznych aplikacjach biznesowych w systemach iOS i Android. To znaczy, że użytkownicy końcowi nie muszą rejestrować swoich urządzeń za pomocą usługi Intune w celu używania aplikacji biznesowych obsługujących zarządzanie aplikacjami mobilnymi.

Każdy może wypróbować publiczną wersję zapoznawczą i przeczytać pomocną dokumentację. Wystarczy skorzystać z materiałów udostępnionych na koncie msintuneappsdk w usłudze GitHub:

http://www.github.com/msintuneappsdk/intune-app-wrapper-ios-preview

http://www.github.com/msintuneappsdk/intune-app-wrapper-android-preview

Przed zainstalowaniem i użyciem wersji wstępnej narzędzia opakowującego aplikacje w usłudze Microsoft Intune dla systemów Android i iOS trzeba:

* Zapoznać się z postanowieniami licencyjnymi firmy Microsoft dotyczącymi wersji wstępnej narzędzia opakowującego aplikacje w usłudze Microsoft Intune dla systemów Android i iOS.
* Wydrukować i zachować kopię postanowień licencyjnych. Pobranie i używanie wersji wstępnej narzędzia opakowującego aplikacje w usłudze Microsoft Intune dla systemu Android jest równoznaczne z akceptacją postanowień licencyjnych. Jeśli użytkownik nie akceptuje niniejszych postanowień, nie może używać tego oprogramowania.
<!---TFS 1235607--->

## Rozpoczęte we wrześniu przejście grup usługi Intune do grup usługi Azure Active Directory
W przypadku niektórych nowych kont usługi Intune będą używane grupy zabezpieczeń usługi Azure Active Directory, a nie grupy użytkowników usługi Intune. To, że praca odbywa się z grupami zabezpieczeń, jest sygnalizowane obecnością na stronie grup portalu Intune linku do portalu zarządzania Azure.

## Integracja aplikacji Lookout w celu ochrony urządzeń z systemem Android
Firma Microsoft przeprowadza integrację z rozwiązaniem firmy Lookout przeznaczonymi do ochrony urządzeń przenośnych w celu zabezpieczenia urządzeń przenośnych z systemem Android przez wykrywanie na urządzeniach złośliwego oprogramowania, ryzykownych aplikacji i innych zagrożeń. Rozwiązanie firmy Lookout pomaga w określeniu poziomu zagrożenia, który można skonfigurować. W usłudze Intune można utworzyć regułę zasad zgodności w celu określania zgodności urządzeń na podstawie oceny ryzyka uzyskanej z rozwiązania firmy Lookout. Za pomocą zasad dostępu warunkowego można umożliwić lub zablokować dostęp do zasobów firmy w zależności od stanu zgodności danego urządzenia.

W przypadku użytkowników końcowych korzystających z niezgodnych urządzeń zostanie wyświetlony monit o zarejestrowanie urządzeń. Aby uzyskać dostęp do zasobów firmy, użytkownicy będą musieli zainstalować aplikację Lookout for Work na urządzeniach z systemem Android, uaktywnić ją i podjąć środki zaradcze dotyczące zagrożeń zgłoszonych w aplikacji Lookout for Work. Aby uzyskać więcej informacji, zobacz [Ograniczanie dostępu do zasobów firmy oparte na ryzyku dotyczącym urządzeń, sieci i aplikacji](restrict-access-based-on-device-network-app-risk.md).


## Aktualizacje Portalu firmy

### Android

**Dodanie obszaru „Powiadomienia” do Portalu firmy dla systemu Android**<br/>
Na stronie głównej Portalu firmy dla systemu Android dodano nową ikonę Powiadomienia. Naciśnięcie tej ikony powoduje przejście na stronę Powiadomienia — przedstawia ona użytkownikowi końcowemu wszystkie elementy, które wymagają uwagi w aplikacji Portal firmy, takie jak brak zgodności urządzeń, aktualizacja rejestracji i aktywacja rejestracji. W aplikacji Portal firmy dla systemu iOS obszar powiadomień jest już dostępny. W wyniku wprowadzenia strony Powiadomienia nie będzie widoczna strona Konfigurowanie dostępu do zasobów firmy po uruchomieniu lub wznowieniu pracy w Portalu firmy, jeśli urządzenie zostało już zarejestrowane. W przypadku tworzenia własnych wskazówek dla użytkowników końcowych warto zaktualizować dokumentację, tak aby uwzględniała tę zmianę. Zaktualizowane zrzuty ekranu można znaleźć [tutaj](https://aka.ms/androidcpupdate).  
<!---TFS 1095560--->

**Przekazywanie opinii w Portalu firmy dla systemu Android**</br>
Do menu Portalu firmy dla systemu Android został dodany nowy element. Po naciśnięciu pozycji **Pomoc i opinie** dostępne są trzy akcje:
* Skorzystaj z pozycji **Uzyskaj pomoc**, aby zgłosić problemy z Portalem firmy do działu IT. Spowoduje to utworzenie wiadomości e-mail przy użyciu klienta poczty e-mail i dołączenie do niej dzienników Portalu firmy. Pozycja **Uzyskaj pomoc** zastępuje funkcję **Wyślij dane** na stronie **Ustawienia**.
* Skorzystaj z pozycji **Zgłoś opinię**, aby przekazać opinię do zespołu Portalu firmy.
* Skorzystaj z pozycji **Oceń naszą aplikację**, aby wystawić aplikacji Portal firmy ocenę lub recenzję w usłudze Google Play.

### iOS
**Zmiany w obsłudze aplikacji Portal firmy dla systemu iOS**<br/>
Wszyscy użytkownicy aplikacji Portal firmy usługi Microsoft Intune dla systemu iOS muszą obecnie używać jej najnowszej wersji. Nowi użytkownicy mogą pobrać tylko najnowszą wersję, a bieżący użytkownicy muszą przeprowadzić aktualizację do najnowszej wersji. Najnowsza wersja aplikacji wymaga systemu iOS 8.0 lub nowszego, dlatego urządzenia ze starszymi wersjami systemu iOS nie mogą korzystać z portalu firmy ani rejestrować się do czasu ich zaktualizowania do systemu iOS 8.0 lub nowszego oraz zaktualizowania aplikacji Portal firmy do najnowszej wersji. Zarejestrowane urządzenia z wersjami systemu iOS poniżej 8.0 będą nadal zarządzane i wyświetlane w konsoli administracyjnej usługi Intune.
<!---TFS 1283165--->

**Ulepszenia w sposobie uzyskiwania aplikacji przez użytkowników końcowych systemu iOS**<br/>
Wprowadzono następujące zmiany w odniesieniu do kafelków aplikacji w aplikacji Portal firmy dla systemu iOS. Zmiany mają na celu umożliwienie przechodzenia do różnych widoków w obrębie jednej lokalizacji — witryny sieci Web Portal firmy — dla wszystkich swoich aplikacji. Ograniczenia firmy Apple uniemożliwiają wyświetlanie w aplikacji Portal firmy aplikacji biznesowych oraz zarządzanych ze sklepu z aplikacjami, w związku z czym użytkownicy muszą korzystać z różnych widoków, aby znaleźć wszystkie swoje aplikacje.

- Kafelek **Aplikacje firmowe** pozwalał poprzednio przejść do listy wszystkich aplikacji na karcie WSZYSTKIE w witrynie sieci Web Portal firmy. Jego działanie nie ulegnie zmianie. Nazwa kafelka została zmieniona na **Wszystkie aplikacje**.
- Kafelek **Inne aplikacje** pozwalał poprzednio przejść do widoku zawierającego wszystkie aplikacje, których wyświetlanie w aplikacji Portal firmy jest możliwe zgodnie z zasadami firmy Apple. Nazwa kafelka została zmieniona na **Polecane aplikacje**, a jego naciśnięcie spowoduje przejście na kartę POLECANE w witrynie sieci Web Portal firmy.
-  Kafelek **Kategorie** pozwalał poprzednio przejść w ramach aplikacji Portal firmy do widoku zawierającego kategorie aplikacji. Nazwa kafelka nie uległa zmianie, ale jego naciśnięcie będzie teraz powodować przejście na kartę KATEGORIE w witrynie sieci Web Portal firmy.
Zaktualizowane zrzuty ekranu można znaleźć [tutaj](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186).
<!---TFS 1317133--->

**Wyświetlaj monit o instalację aplikacji Managed Browser dla systemu iOS, jeśli oprogramowanie IT Pro określiło taki wymóg dla aplikacji**<br/>
Ustawienie składnika Web Clip w taki sposób, aby otwierał się tylko w zarządzanej przeglądarce w przypadku, gdy zarządzana przeglądarka nie została zainstalowana na urządzeniu, spowoduje, że aplikacja Portal firmy na urządzeniu wyświetli monit o zainstalowanie zarządzanej przeglądarki przed zainstalowaniem składnika Web Clip.
<!---TFS 1228570--->

### Windows
**Dodanie przycisku wysyłania opinii do aplikacji Portal firmy dla systemu Windows Phone 8.1**<br/>
Aplikacja Portal firmy dla systemu Windows Phone 8.1 umożliwia użytkownikom końcowym przesyłanie opinii o aplikacji przy użyciu nowego przycisku „wyślij opinię”. Aby znaleźć przycisk, użytkownicy muszą nacisnąć oznaczone wielokropkiem menu w prawej dolnej części ekranu aplikacji Portal firmy, a następnie nacisnąć pozycję **wyślij opinię**. Zebrane anonimowe opinie pomogą firmie Microsoft w ulepszaniu środowiska aplikacji Portal firmy dla użytkowników.
<!---TFS 1317806--->

## Słownik dotyczący usługi Intune</br>
Dodano nowy [temat w słowniku](https://docs.microsoft.com/intune/understand-explore/intune-glossary) do biblioteki, aby ułatwić zrozumienie niektórych pojęć używanych w produkcie Intune.



<!--HONumber=Oct16_HO2-->

