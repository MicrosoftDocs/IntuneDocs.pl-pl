---
title: Ustawienia zasad systemu Windows
description: "Ogólnych zasad konfiguracji systemu Windows (w systemie Windows 8.1 lub nowszym) w usłudze Intune można używać do konfigurowania ustawień zarejestrowanych urządzeń z systemami Windows 8 i Windows 8.1."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6982a2bc-aafa-475a-9236-4840b709e5a1
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ab39a1847dbba495b4946d12b96b6f8c724f38d8
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2017
---
# <a name="windows-policy-settings-in-microsoft-intune"></a>Ustawienia zasad systemu Windows w usłudze Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

**Ogólnych zasad konfiguracji systemu Windows (w systemie Windows 8.1 lub nowszym)** w usłudze Microsoft Intune można używać do konfigurowania następujących ustawień zarejestrowanych urządzeń z systemami Windows 8, Windows 8.1 i Windows RT 8.1:

## <a name="applicability-settings"></a>Ustawienia zastosowania

|Nazwa ustawienia|Szczegóły|
|----------------|----------------------------------|
|**Zastosuj wszystkie konfiguracje dla systemu Windows 10**|Umożliwia zastosowanie ustawień tych zasad również na urządzeniach z systemem Windows 10, a nie tylko na urządzeniach z systemami Windows 8 i Windows 8.1.|

## <a name="security-settings"></a>Ustawienia zabezpieczeń

|Nazwa ustawienia|Szczegóły|
|----------------|------|
|**Wymagany typ hasła**|Określa wymagany typ hasła, na przykład alfanumeryczne lub tylko liczbowe.|
|**Wymagany typ hasła — Minimalna liczba zestawów znaków**|Określa, z ilu różnych zestawów znaków muszą pochodzić znaki zawarte w haśle. Istnieją cztery zestawy znaków: małe litery, wielkie litery, cyfry oraz symbole. Jednak w przypadku urządzeń z systemem iOS to ustawienie określa liczbę symboli, które muszą być zawarte w haśle.|
|**Minimalna długość hasła**|Konfiguruje minimalną wymaganą długość (w znakach) hasła.|
|**Liczba dopuszczalnych nieudanych logowań przed wyczyszczeniem danych z urządzenia**|Czyści urządzenie, jeśli podana liczba prób logowania zakończy się niepowodzeniem.|
|**Czas braku aktywności (w minutach) przed wyłączeniem ekranu**|Określa liczbę minut, przez które urządzenie musi być bezczynne, zanim do jego odblokowania będzie wymagane hasło.|
|**Dni do wygaśnięcia hasła**|Określa liczbę dni, po której należy zmienić hasło urządzenia.|
|**Pamiętaj historię haseł**|Określa, czy użytkownik może skonfigurować uprzednio używane hasła.|
|**Pamiętaj historię haseł** — **Zapobiegaj ponownemu używaniu poprzednich haseł**|Określa liczbę poprzednich haseł, które są zapamiętywane przez urządzenie.|
|**Zezwalaj na hasło obrazkowe i numer PIN**|Umożliwia korzystanie z haseł obrazkowych i numerów PIN. Hasło obrazkowe umożliwia użytkownikowi logowanie za pomocą gestów na obrazie. Numer PIN umożliwia użytkownikowi szybkie logowanie za pomocą 4-cyfrowego kodu.|

## <a name="encryption-settings"></a>Ustawienia szyfrowania

|Nazwa ustawienia|Szczegóły|
|----------------|-----|
|**Wymagaj szyfrowania na urządzeniu przenośnym**<sup>1</sup>|Wymaga szyfrowania plików na urządzeniu.|
<sup>1</sup> Dodatkowe informacje dotyczące urządzeń z systemem Windows 8.1

-   Aby wymusić szyfrowanie na urządzeniach z systemem Windows 8.1, trzeba zainstalować na wszystkich urządzeniach [aktualizację klienta MDM dla systemu Windows z grudnia 2014 r.](http://support.microsoft.com/kb/3013816) 

-   W przypadku włączenia tego ustawienia dla urządzeń z systemem Windows 8.1 wszyscy użytkownicy urządzeń muszą mieć konto Microsoft.

-   Aby szyfrowanie działało, urządzenie musi spełniać wymagania dotyczące certyfikacji sprzętu [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) firmy Microsoft.

-   W przypadku wymuszania szyfrowania na urządzeniu klucz odzyskiwania jest dostępny tylko za pośrednictwem konta Microsoft użytkownika, do którego można uzyskać dostęp z konta usługi OneDrive. Nie można odzyskać tego klucza w imieniu użytkownika.

## <a name="malware-settings"></a>Ustawienia złośliwego oprogramowania

|Nazwa ustawienia|Szczegóły|
|----------------|-----|
|**Wymagaj zapory sieciowej**|Wymaga włączenia Zapory systemu Windows.|
|**Włącz filtr SmartScreen**|Wymaga używania filtru Windows SmartScreen.|

## <a name="system-settings"></a>Ustawienia systemowe

|Nazwa ustawienia|Szczegóły|
|----------------|-------|
|**Wymagaj aktualizacji automatycznych**|Włącza ustawienie aktualizacji automatycznych na urządzeniach.|
|**Wymagaj aktualizacji automatycznych — minimalna klasyfikacja aktualizacji do instalacji automatycznej**|Wybiera klasyfikację aktualizacji, które będą instalowane automatycznie:<br /><br />-   **Ważne** — instaluje wszystkie aktualizacje sklasyfikowane jako ważne.<br />-   **Zalecane** — instaluje wszystkie aktualizacje sklasyfikowane jako ważne lub zalecane.|
|**Kontrola konta użytkownika**|Wymaga używania Kontroli konta użytkownika na urządzeniach.|
|**Zezwalaj na przesyłanie danych diagnostycznych**|Umożliwia urządzeniu przesyłanie danych diagnostycznych do firmy Microsoft.|


## <a name="cloud-settings--documents-and-data"></a>Ustawienia chmury — dokumenty i dane

|Nazwa ustawienia|Szczegóły|
|----------------|------|
|**Adres URL folderów roboczych**|Ustawia adres URL folderu roboczego, aby umożliwić synchronizację dokumentów między urządzeniami.|

## <a name="email-settings"></a>Ustawienia poczty e-mail

|Nazwa ustawienia|Szczegóły|
|----------------|-----|
|**Ustaw konto Microsoft jako opcjonalne w aplikacji Windows Mail**|Umożliwia dostęp do aplikacji Poczta systemu Windows bez konta Microsoft.|

## <a name="application-settings---browser"></a>Ustawienia aplikacji — przeglądarka

|Nazwa ustawienia|Szczegóły|
|----------------|-----|
|**Zezwalaj na automatyczne uzupełnianie**|Umożliwia użytkownikom zmianę ustawień autouzupełniania w przeglądarce.|
|**Zezwalaj na blokowanie wyskakujących okienek**|Włącza lub wyłącza blokowanie wyskakujących okienek w przeglądarce.|
|**Zezwalaj na używanie dodatków**|Umożliwia użytkownikom dodawanie wtyczek do programu Internet Explorer.|
|**Zezwalaj na wykonywanie aktywnych skryptów**|Umożliwia przeglądarce uruchamianie skryptów, takich jak skrypty ActiveX.|
|**Zezwalaj na ostrzeganie o oszustwach**|Włącza lub wyłącza ostrzeżenia o potencjalnie oszukańczych witrynach sieci Web.|
|**Zezwalaj na przejście do witryny intranetowej po wpisaniu jednego słowa**|Umożliwia korzystanie z pojedynczego wyrazu w celu przekierowania programu Internet Explorer do witryny sieci Web, np. „Bing”.|
|**Zezwalaj na automatyczne wykrywanie sieci intranet**|Pomaga konfigurować zabezpieczenia witryn intranetowych w przeglądarce Internet Explorer.|
|**Poziom zabezpieczeń Internetu**|Ustawia poziom zabezpieczeń przeglądarki Internet Explorer dla witryn w Internecie.|
|**Poziom zabezpieczeń intranetu**|Ustawia poziom zabezpieczeń przeglądarki Internet Explorer dla witryn intranetowych.|
|**Poziom zabezpieczeń zaufanych witryn**|Konfiguruje poziom zabezpieczeń strefy zaufanych witryn.|
|**Poziom zabezpieczeń witryn z ograniczeniami**|Konfiguruje poziom zabezpieczeń strefy witryn z ograniczeniami.|
|**Wysyłaj nagłówek Nie śledź**|Wysyła odwiedzanym witrynom nagłówek Nie śledź w przeglądarce Internet Explorer.|
|**Zezwalaj na dostęp do menu trybu przedsiębiorstwa**|Umożliwia użytkownikom dostęp do poleceń menu Tryb przedsiębiorstwa z programu Internet Explorer.<br>Jeśli to ustawienie jest wybrane, możesz również określić opcję **Lokalizacja raportu rejestrowania**, która zawiera adres URL do raportu przedstawiającego witryny sieci Web, dla których użytkownicy włączyli dostęp w trybie przedsiębiorstwa.|
|**Lokalizacja listy witryn trybu przedsiębiorstwa**|Określa lokalizację listy witryn sieci Web, które będą używać trybu przedsiębiorstwa, gdy ten jest aktywny.|

## <a name="device-capabilities-settings---cellular"></a>Ustawienia możliwości urządzenia — połączenie komórkowe

|Nazwa ustawienia|Szczegóły|
|----------------|----|
|**Zezwalaj na roaming danych**|Umożliwia roaming danych, gdy urządzenie jest w sieci komórkowej.|



### <a name="see-also"></a>Zobacz także
[Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
