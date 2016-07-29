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
ms.sourcegitcommit: 6716a3d1fb53dc3de0189f637d5664d0a2023d05
ms.openlocfilehash: 809c8dc87e9b7c2f27e8015a55606e376c5319ab


---

# Ustawienia zasad systemu Windows w usłudze Microsoft Intune
**Ogólnych zasad konfiguracji systemu Windows (w systemie Windows 8.1 lub nowszym)** w usłudze Microsoft Intune można używać do konfigurowania następujących ustawień zarejestrowanych urządzeń z systemami Windows 8 i Windows 8.1:

## Ustawienia zastosowania

|Nazwa ustawienia|Szczegóły|
|----------------|----------------------------------|
|**Zastosuj wszystkie konfiguracje dla systemu Windows 10**|Umożliwia zastosowanie ustawień tych zasad na urządzeniach z systemem Windows 10 (dodatkowo do urządzeń z systemami Windows 8 i Windows 8.1).|

## Ustawienia zabezpieczeń

|Nazwa ustawienia|Szczegóły|Windows 8.1 i Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Wymagany typ hasła**|Określa typ hasła, które będzie wymagane, na przykład wyłącznie numeryczne lub alfanumeryczne.|Tak|Tak|
|**Wymagany typ hasła — Minimalna liczba zestawów znaków**|Istnieją cztery zestawów znaków: małe litery, wielkie litery, cyfry oraz symbole. To ustawienie określa, znaki z ilu zestawów znaków muszą być zawarte w haśle. Jednak w przypadku urządzeń z systemem iOS ustawienie określa liczbę znaków symbolicznych, które muszą być zawarte w haśle.|Tak|Tak|
|**Minimalna długość hasła**<sup>1</sup>|Konfiguruje minimalną wymaganą długość (w znakach) hasła na urządzeniach.|Tak|Tak|
|**Liczba dopuszczalnych nieudanych logowań przed wyczyszczeniem danych z urządzenia**|Czyści urządzenie po określonej liczbie prób logowania zakończonych niepowodzeniem.|Tak|Tak|
|**Czas braku aktywności (w minutach) przed wyłączeniem ekranu**|Wybierz liczbę minut, przez które urządzenie musi być bezczynne, zanim do jego odblokowania będzie wymagane hasło.| Tak|Tak|
|**Wygaśnięcie hasła w dniach**|Określa liczbę dni, po której należy zmienić hasło urządzenia.|Tak|Tak|
|**Pamiętaj historię haseł**|Określa, czy użytkownik może skonfigurować uprzednio używane hasła.|Tak|Tak|
|**Pamiętaj historię haseł** — **Zapobiegaj ponownemu używaniu poprzednich haseł**|Określa liczbę poprzednich haseł, które są zapamiętywane przez urządzenie.|Tak|Tak|
|**Zezwalaj na hasło obrazkowe i numer PIN**|Umożliwia korzystanie z haseł obrazkowych i numerów PIN na urządzeniu. Hasło obrazkowe umożliwia użytkownikowi logowanie za pomocą gestów na obrazie. Numer PIN umożliwia użytkownikowi szybkie logowanie za pomocą 4-cyfrowego kodu.|Tak|Tak|
<sup>1</sup> Po wdrożeniu zasad długości hasła na urządzeniach z systemem Windows RT użytkownicy będą zmuszeni do zresetowania swojego hasła nawet wtedy, gdy ich bieżące hasło spełnia wymagania zasad.

## Ustawienia szyfrowania

|Nazwa ustawienia|Szczegóły|Windows 8.1 i Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Wymagaj szyfrowania na urządzeniu przenośnym**<sup>1</sup>|Wymaga szyfrowania plików na urządzeniu.<br>Dla urządzeń z systemem Windows Phone 8 trzeba ustawić wartość **Tak**.|Tak|Nie|
<sup>1</sup> Dodatkowe informacje dotyczące urządzeń z systemem Windows 8.1

-   Aby wymusić szyfrowanie na urządzeniach z systemem Windows 8.1, trzeba zainstalować na wszystkich urządzeniach [aktualizację klienta MDM dla systemu Windows z grudnia 2014 r.](http://support.microsoft.com/kb/3013816) 

-   W przypadku włączenia tego ustawienia dla urządzeń z systemem Windows 8.1 wszyscy użytkownicy urządzeń muszą mieć konto Microsoft.

-   Aby szyfrowanie działało, urządzenie musi spełniać wymagania dotyczące certyfikacji sprzętu [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) firmy Microsoft.

-   W przypadku wymuszania szyfrowania na urządzeniu klucz odzyskiwania jest dostępny tylko za pośrednictwem konta Microsoft użytkowników, do którego można uzyskać dostęp z konta usługi OneDrive. Nie można odzyskać tego klucza w imieniu użytkownika.

## Ustawienia złośliwego oprogramowania

|Nazwa ustawienia|Szczegóły|Windows 8.1 i Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Wymagaj zapory sieciowej**|Wymagaj włączenia zapory systemu Windows.|Tak|Nie|
|**Włącz filtr SmartScreen**|Wymagaj użycia filtru Windows SmartScreen na urządzeniach.|Tak|Nie|

## Ustawienia systemowe

|Nazwa ustawienia|Szczegóły|Windows 8.1 i Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Wymagaj aktualizacji automatycznych**|Włącz ustawienie aktualizacji automatycznych na urządzeniach.|Tak|Nie|
|**Wymagaj aktualizacji automatycznych — minimalna klasyfikacja aktualizacji do instalacji automatycznej**|Wybierz klasyfikację aktualizacji, które zostaną zainstalowane automatycznie:<br /><br />-   **Ważne** — instaluje wszystkie aktualizacje sklasyfikowane jako ważne.<br />-   **Zalecane** — instaluje wszystkie aktualizacje sklasyfikowane jako ważne lub zalecane.|Tak|Nie|
|**Kontrola konta użytkownika**|Wymagaj używania Kontroli konta użytkownika na urządzeniach.|Tak|Nie|
|**Zezwalaj na przesłanie danych diagnostycznych**|Zezwalaj urządzeniu na przesyłanie danych diagnostycznych do firmy Microsoft.|Tak|Nie|


## Ustawienia chmury — dokumenty i dane

|Nazwa ustawienia|Szczegóły|Windows 8.1 i Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Adres URL folderów roboczych**|Ustawia adres URL folderu roboczego, aby umożliwić synchronizację dokumentów między urządzeniami.|Tak|Nie|

## Ustawienia poczty e-mail

|Nazwa ustawienia|Szczegóły|Windows 8.1 i Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Ustaw konto Microsoft jako opcjonalne w aplikacji Windows Mail**|Zezwala na dostęp do aplikacji Poczta systemu Windows bez konta Microsoft.|Tak|Nie|

## Ustawienia aplikacji — przeglądarka

|Nazwa ustawienia|Szczegóły|Windows 8.1 i Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Zezwalaj na automatyczne uzupełnianie**|Użytkownik może zmienić ustawienia autowypełniania w przeglądarce.|Tak|Nie|
|**Zezwalaj na blokowanie wyskakujących okienek**|Włącza lub wyłącza blokowanie wyskakujących okienek w przeglądarce.|Tak|Nie|
|**Zezwalaj na używanie dodatków**|Użytkownik może dodać dodatki plug-in do programu Internet Explorer.|Tak|Nie|
|**Zezwalaj na wykonywanie aktywnych skryptów**|Przeglądarka może uruchamiać skrypty, takie jak skrypty kontrolek ActiveX.|Tak|Nie|
|**Zezwalaj na ostrzeżenia o oszustwie**|Włącz lub wyłącz ostrzeżenia o potencjalnych fałszywych witrynach sieci Web.|Tak|Nie|
|**Zezwalaj na przejście do witryny intranetowej po wpisaniu jednego słowa**|Umożliwia korzystanie z pojedynczego wyrazu w celu przekierowania programu Internet Explorer do witryny sieci Web, np. „Bing”.|Tak|Nie|
|**Zezwalaj na automatyczne wykrywanie sieci intranet**|Pomaga konfigurować zabezpieczenia witryn intranetowych w przeglądarce Internet Explorer.|Tak|Nie|
|**Poziom zabezpieczeń Internetu**|Ustaw poziom zabezpieczeń przeglądarki Internet Explorer dla witryn internetowych.|Tak|Nie|
|**Poziom zabezpieczeń sieci intranet**|Ustaw poziom zabezpieczeń przeglądarki Internet Explorer dla witryn intranetowych.|Tak|Nie|
|**Poziom zabezpieczeń zaufanych witryn**|Konfiguruje poziom zabezpieczeń strefy zaufanych witryn.|Tak|Nie|
|**Poziom zabezpieczeń witryn z ograniczeniami**|Konfiguruje poziom zabezpieczeń strefy witryn z ograniczeniami.|Tak|Nie|
|**Wysyłaj nagłówek Nie śledź**|Wysyłaj odwiedzanym witrynom nagłówek Nie śledź w przeglądarce Internet Explorer.|Tak|Nie|
|**Zezwalaj na dostęp do menu trybu przedsiębiorstwa**|Umożliwia użytkownikom dostęp do poleceń menu Tryb przedsiębiorstwa z programu Internet Explorer.<br>Jeśli opcja jest wybrana, możesz również określić opcję **Lokalizacja raportu rejestrowania**, która zawiera adres URL do raportu przedstawiającego witryny sieci Web, dla których użytkownicy włączyli dostęp w trybie przedsiębiorstwa.|Tak|Nie|
|**Lokalizacja listy witryn trybu przedsiębiorstwa**|Określ lokalizację listy witryn sieci Web, które będą używać trybu przedsiębiorstwa, gdy będzie aktywny.|Tak|Nie|

## Ustawienia możliwości urządzenia — połączenie komórkowe

|Nazwa ustawienia|Szczegóły|Windows 8.1 i Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Zezwalaj na roaming danych**|Zezwalaj na roaming danych, gdy urządzenie korzysta z sieci komórkowej.|Tak|Nie|



### Zobacz także
[Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)




<!--HONumber=Jul16_HO4-->


