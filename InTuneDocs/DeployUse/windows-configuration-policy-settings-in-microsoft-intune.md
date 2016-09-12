---
title: Ustawienia zasad systemu Windows | Microsoft Intune
description: "Ogólnych zasad konfiguracji systemu Windows (w systemie Windows 8.1 lub nowszym) w usłudze Intune można używać do konfigurowania ustawień zarejestrowanych urządzeń z systemami Windows 8 i Windows 8.1."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6982a2bc-aafa-475a-9236-4840b709e5a1
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 073e3df63a5de9cf92c739c1ced858e21a9ac351
ms.openlocfilehash: 6b2d805561067d2dc0de70d93c45622a951e5981


---

# Ustawienia zasad systemu Windows w usłudze Microsoft Intune
**Ogólnych zasad konfiguracji systemu Windows (w systemie Windows 8.1 lub nowszym)** w usłudze Microsoft Intune można używać do konfigurowania następujących ustawień zarejestrowanych urządzeń z systemami Windows 8 i Windows 8.1:

## Ustawienia zastosowania

|Nazwa ustawienia|Szczegóły|
|----------------|----------------------------------|
|**Zastosuj wszystkie konfiguracje dla systemu Windows 10**|Umożliwia zastosowanie ustawień tych zasad również na urządzeniach z systemem Windows 10, a nie tylko na urządzeniach z systemami Windows 8 i Windows 8.1.|

## Ustawienia zabezpieczeń

|Nazwa ustawienia|Szczegóły|Windows 8.1 i Windows RT 8.1|Windows RT|
|----------------|------|----------------------------|--------------|
|**Wymagany typ hasła**|Określa wymagany typ hasła, na przykład alfanumeryczne lub tylko liczbowe.|Tak|Tak|
|**Wymagany typ hasła — Minimalna liczba zestawów znaków**|Określa, z ilu różnych zestawów znaków muszą pochodzić znaki zawarte w haśle. Istnieją cztery zestawy znaków: małe litery, wielkie litery, cyfry oraz symbole. Jednak w przypadku urządzeń z systemem iOS to ustawienie określa liczbę symboli, które muszą być zawarte w haśle.|Tak|Tak|
|**Minimalna długość hasła**<sup>1</sup>|Konfiguruje minimalną wymaganą długość (w znakach) hasła.|Tak|Tak|
|**Liczba dopuszczalnych nieudanych logowań przed wyczyszczeniem danych z urządzenia**|Czyści urządzenie, jeśli podana liczba prób logowania zakończy się niepowodzeniem.|Tak|Tak|
|**Czas braku aktywności (w minutach) przed wyłączeniem ekranu**|Określa liczbę minut, przez które urządzenie musi być bezczynne, zanim do jego odblokowania będzie wymagane hasło.| Tak|Tak|
|**Wygaśnięcie hasła w dniach**|Określa liczbę dni, po której należy zmienić hasło urządzenia.|Tak|Tak|
|**Pamiętaj historię haseł**|Określa, czy użytkownik może skonfigurować uprzednio używane hasła.|Tak|Tak|
|**Pamiętaj historię haseł** — **Zapobiegaj ponownemu używaniu poprzednich haseł**|Określa liczbę poprzednich haseł, które są zapamiętywane przez urządzenie.|Tak|Tak|
|**Zezwalaj na hasło obrazkowe i numer PIN**|Umożliwia korzystanie z haseł obrazkowych i numerów PIN. Hasło obrazkowe umożliwia użytkownikowi logowanie za pomocą gestów na obrazie. Numer PIN umożliwia użytkownikowi szybkie logowanie za pomocą 4-cyfrowego kodu.|Tak|Tak|
<sup>1</sup> Po wdrożeniu zasad długości hasła na urządzeniach z systemem Windows RT użytkownicy będą zmuszeni do zresetowania hasła nawet wtedy, gdy ich bieżące hasło spełnia wymagania zasad.

## Ustawienia szyfrowania

|Nazwa ustawienia|Szczegóły|Windows 8.1 i Windows RT 8.1|Windows RT|
|----------------|-----|-----------------------------|--------------|
|**Wymagaj szyfrowania na urządzeniu przenośnym**<sup>1</sup>|Wymaga szyfrowania plików na urządzeniu.<br>Dla urządzeń z systemem Windows Phone 8 trzeba ustawić wartość **Tak**.|Tak|Nie|
<sup>1</sup> Dodatkowe informacje dotyczące urządzeń z systemem Windows 8.1

-   Aby wymusić szyfrowanie na urządzeniach z systemem Windows 8.1, trzeba zainstalować na wszystkich urządzeniach [aktualizację klienta MDM dla systemu Windows z grudnia 2014 r.](http://support.microsoft.com/kb/3013816) 

-   W przypadku włączenia tego ustawienia dla urządzeń z systemem Windows 8.1 wszyscy użytkownicy urządzeń muszą mieć konto Microsoft.

-   Aby szyfrowanie działało, urządzenie musi spełniać wymagania dotyczące certyfikacji sprzętu [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) firmy Microsoft.

-   W przypadku wymuszania szyfrowania na urządzeniu klucz odzyskiwania jest dostępny tylko za pośrednictwem konta Microsoft użytkownika, do którego można uzyskać dostęp z konta usługi OneDrive. Nie można odzyskać tego klucza w imieniu użytkownika.

## Ustawienia złośliwego oprogramowania

|Nazwa ustawienia|Szczegóły|Windows 8.1 i Windows RT 8.1|Windows RT|
|----------------|-----|-----------------------------|--------------|
|**Wymagaj zapory sieciowej**|Wymaga włączenia Zapory systemu Windows.|Tak|Nie|
|**Włącz filtr SmartScreen**|Wymaga używania filtru Windows SmartScreen.|Tak|Nie|

## Ustawienia systemowe

|Nazwa ustawienia|Szczegóły|Windows 8.1 i Windows RT 8.1|Windows RT|
|----------------|-------|---------------------------|--------------|
|**Wymagaj aktualizacji automatycznych**|Włącza ustawienie aktualizacji automatycznych na urządzeniach.|Tak|Nie|
|**Wymagaj aktualizacji automatycznych — minimalna klasyfikacja aktualizacji do instalacji automatycznej**|Wybiera klasyfikację aktualizacji, które będą instalowane automatycznie:<br /><br />-   **Ważne** — instaluje wszystkie aktualizacje sklasyfikowane jako ważne.<br />-   **Zalecane** — instaluje wszystkie aktualizacje sklasyfikowane jako ważne lub zalecane.|Tak|Nie|
|**Kontrola konta użytkownika**|Wymaga używania Kontroli konta użytkownika na urządzeniach.|Tak|Nie|
|**Zezwalaj na przesłanie danych diagnostycznych**|Umożliwia urządzeniu przesyłanie danych diagnostycznych do firmy Microsoft.|Tak|Nie|


## Ustawienia chmury — dokumenty i dane

|Nazwa ustawienia|Szczegóły|Windows 8.1 i Windows RT 8.1|Windows RT|
|----------------|------|----------------------------|--------------|
|**Adres URL folderów roboczych**|Ustawia adres URL folderu roboczego, aby umożliwić synchronizację dokumentów między urządzeniami.|Tak|Nie|

## Ustawienia poczty e-mail

|Nazwa ustawienia|Szczegóły|Windows 8.1 i Windows RT 8.1|Windows RT|
|----------------|-----|-----------------------------|--------------|
|**Ustaw konto Microsoft jako opcjonalne w aplikacji Windows Mail**|Umożliwia dostęp do aplikacji Poczta systemu Windows bez konta Microsoft.|Tak|Nie|

## Ustawienia aplikacji — przeglądarka

|Nazwa ustawienia|Szczegóły|Windows 8.1 i Windows RT 8.1|Windows RT|
|----------------|-----|-----------------------------|--------------|
|**Zezwalaj na automatyczne uzupełnianie**|Umożliwia użytkownikom zmianę ustawień autouzupełniania w przeglądarce.|Tak|Nie|
|**Zezwalaj na blokowanie wyskakujących okienek**|Włącza lub wyłącza blokowanie wyskakujących okienek w przeglądarce.|Tak|Nie|
|**Zezwalaj na używanie dodatków**|Umożliwia użytkownikom dodawanie wtyczek do programu Internet Explorer.|Tak|Nie|
|**Zezwalaj na wykonywanie aktywnych skryptów**|Umożliwia przeglądarce uruchamianie skryptów, takich jak skrypty ActiveX.|Tak|Nie|
|**Zezwalaj na ostrzeżenia o oszustwie**|Włącza lub wyłącza ostrzeżenia o potencjalnie oszukańczych witrynach sieci Web.|Tak|Nie|
|**Zezwalaj na przejście do witryny intranetowej po wpisaniu jednego słowa**|Umożliwia korzystanie z pojedynczego wyrazu w celu przekierowania programu Internet Explorer do witryny sieci Web, np. „Bing”.|Tak|Nie|
|**Zezwalaj na automatyczne wykrywanie sieci intranet**|Pomaga konfigurować zabezpieczenia witryn intranetowych w przeglądarce Internet Explorer.|Tak|Nie|
|**Poziom zabezpieczeń Internetu**|Ustawia poziom zabezpieczeń przeglądarki Internet Explorer dla witryn w Internecie.|Tak|Nie|
|**Poziom zabezpieczeń sieci intranet**|Ustawia poziom zabezpieczeń przeglądarki Internet Explorer dla witryn intranetowych.|Tak|Nie|
|**Poziom zabezpieczeń zaufanych witryn**|Konfiguruje poziom zabezpieczeń strefy zaufanych witryn.|Tak|Nie|
|**Poziom zabezpieczeń witryn z ograniczeniami**|Konfiguruje poziom zabezpieczeń strefy witryn z ograniczeniami.|Tak|Nie|
|**Wysyłaj nagłówek Nie śledź**|Wysyła odwiedzanym witrynom nagłówek Nie śledź w przeglądarce Internet Explorer.|Tak|Nie|
|**Zezwalaj na dostęp do menu trybu przedsiębiorstwa**|Umożliwia użytkownikom dostęp do poleceń menu Tryb przedsiębiorstwa z programu Internet Explorer.<br>Jeśli to ustawienie jest wybrane, możesz również określić opcję **Lokalizacja raportu rejestrowania**, która zawiera adres URL do raportu przedstawiającego witryny sieci Web, dla których użytkownicy włączyli dostęp w trybie przedsiębiorstwa.|Tak|Nie|
|**Lokalizacja listy witryn trybu przedsiębiorstwa**|Określa lokalizację listy witryn sieci Web, które będą używać trybu przedsiębiorstwa, gdy ten jest aktywny.|Tak|Nie|

## Ustawienia możliwości urządzenia — połączenie komórkowe

|Nazwa ustawienia|Szczegóły|Windows 8.1 i Windows RT 8.1|Windows RT|
|----------------|----|------------------------------|--------------|
|**Zezwalaj na roaming danych**|Umożliwia roaming danych, gdy urządzenie jest w sieci komórkowej.|Tak|Nie|



### Zobacz także
[Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Sep16_HO2-->


