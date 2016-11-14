---
title: Ustawienia zasad programu Exchange ActiveSync | Microsoft Intune
description: "Zasady programu Exchange ActiveSync w usłudze Intune pozwalają skonfigurować ustawienia umożliwiające sterowanie funkcjami na urządzeniach zarządzanych przez program Exchange ActiveSync."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9cbb826-b155-4df6-abf3-60c6f05b2783
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a4f7a503417938eabb4334757dcf12a63f082fd3
ms.openlocfilehash: 770871d8cc7a32fb54ef01fb9ac84b1fdee2ec90


---

# Ustawienia zasad programu Exchange ActiveSync w usłudze Microsoft Intune
Zasady programu **Exchange ActiveSync** w usłudze Microsoft Intune pozwalają skonfigurować ustawienia sterujące różnymi funkcjami na urządzeniach zarządzanych przez program Exchange ActiveSync.


## Ustawienia hasła

|Nazwa ustawienia|Szczegóły
|----------------|---|
|**Wymagaj hasła do odblokowania urządzeń przenośnych**|Określa, czy urządzenie musi być zablokowane przy użyciu hasła.<br>(Nie dotyczy urządzeń z systemami Windows RT).|
|**Wymagany typ hasła**|Określa typ hasła, które będzie wymagane, na przykład wyłącznie numeryczne lub alfanumeryczne.|
|**Minimalna długość hasła**|Określa minimalną wymaganą liczbę znaków w haśle urządzenia.|
|**Zezwalaj na proste hasła**|Określa, czy można używać prostych haseł, w tym „0000” i „1234”.|
|**Liczba dopuszczalnych nieudanych logowań przed wyczyszczeniem danych z urządzenia**|Określa, ile razy użytkownik może wprowadzić nieprawidłowe hasło, zanim zawartość urządzenia zostanie usunięta.|
|**Wygaśnięcie hasła (dni)**|Określa liczbę dni, po której należy zmienić hasło urządzenia.
|**Pamiętaj historię haseł**|Określa, czy można korzystać z uprzednio używanych haseł.|
|**Pamiętaj historię haseł** — **Zapobiegaj ponownemu używaniu poprzednich haseł**|Określa liczbę wcześniej używanych haseł, których nie można użyć ponownie.|
|**Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**|Określa czas bezczynności urządzenia, po upływie którego ekran jest blokowany.

## Ustawienia szyfrowania

|Nazwa ustawienia|Szczegóły|
|----------------|---|
|**Wymagaj szyfrowania na urządzeniu przenośnym**<sup>1</sup>|Wymaga szyfrowania danych na urządzeniu z obsługą tej funkcji.<br><br>Dla urządzeń z systemem Windows Phone 8 trzeba ustawić wartość **Tak**.<br /><br />Aby włączyć szyfrowanie na urządzeniach z systemem iOS, włącz ustawienie **Wymagaj hasła do odblokowania urządzeń przenośnych**.|
|**Wymagaj szyfrowania kart pamięci**|Wymaga szyfrowania danych przechowywanych w pamięci zewnętrznej, np. na kartach SD (w obsługiwanych urządzeniach).
<sup>1</sup> Dodatkowe informacje dotyczące urządzeń z systemem Windows 8.1

-   Aby wymusić szyfrowanie na urządzeniach z systemem Windows 8.1, trzeba zainstalować na każdym urządzeniu [aktualizację klienta MDM dla systemu Windows z grudnia 2014 r.](http://support.microsoft.com/kb/3013816)

-   W przypadku włączenia tego ustawienia dla urządzeń z systemem Windows 8.1 wszyscy użytkownicy urządzeń muszą mieć konto Microsoft.

-   Aby szyfrowanie działało dla urządzeń z systemem Windows 8.1, urządzenie musi spełniać wymagania dotyczące certyfikacji sprzętu [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) firmy Microsoft.

-   W przypadku wymuszania szyfrowania na urządzeniu z systemem Windows 8.1 klucz odzyskiwania jest dostępny tylko za pośrednictwem konta Microsoft użytkownika, do którego można uzyskać dostęp z konta usługi OneDrive użytkownika. Nie można odzyskać tego klucza w imieniu użytkownika.

## Ustawienia poczty e-mail

|Nazwa ustawienia|Szczegóły
|----------------|---|
|**Zezwalaj użytkownikom na pobieranie załączników wiadomości e-mail**|Określa, czy na urządzenie można pobierać załączniki wiadomości e-mail.|
|**Okres synchronizacji wiadomości e-mail**|Określa liczbę dni synchronizacji odebranych wiadomości e-mail na urządzeniu.
|**Zezwalaj urządzeniom przenośnym, które nie obsługują w pełni ustawień programu Exchange ActiveSync, na synchronizowanie z programem Exchange**|Określa, czy zezwalać na dostęp do programu Exchange na urządzeniach, które nie obsługują co najmniej jednego ustawienia programu Exchange ActiveSync.

## Ustawienia przeglądarki

|Nazwa ustawienia|Szczegóły
|----------------|---|
|**Zezwalaj na używanie przeglądarki sieci Web**|Określa, czy można używać przeglądarki sieci Web na urządzeniu.<br>(Niedostępne dla systemów Windows RT i Windows Phone).

## Ustawienia sprzętu

|Nazwa ustawienia|Szczegóły
|----------------|---|
|**Zezwalaj na używanie aparatu**|Określa, czy można używać aparatu w urządzeniu.<br>(Niedostępne dla systemów Windows RT i Windows Phone).



### Zobacz także
[Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Oct16_HO4-->


