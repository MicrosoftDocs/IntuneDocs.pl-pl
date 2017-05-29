---
title: Ustawienia zasad programu Exchange ActiveSync | Microsoft Docs
description: "Zasady programu Exchange ActiveSync w usłudze Intune pozwalają skonfigurować ustawienia umożliwiające sterowanie funkcjami na urządzeniach zarządzanych przez program Exchange ActiveSync."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9cbb826-b155-4df6-abf3-60c6f05b2783
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: c4023007f993436e0d7628cce52f78a1127c88f8
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---

# <a name="exchange-activesync-policy-settings-in-microsoft-intune"></a>Ustawienia zasad programu Exchange ActiveSync w usłudze Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Zasady programu **Exchange ActiveSync** w usłudze Microsoft Intune pozwalają skonfigurować ustawienia sterujące różnymi funkcjami na urządzeniach zarządzanych przez program Exchange ActiveSync.


## <a name="password-settings"></a>Ustawienia hasła

|Nazwa ustawienia|Szczegóły
|----------------|---|
|**Wymagaj hasła do odblokowania urządzeń przenośnych**|Określa, czy urządzenie musi być zablokowane przy użyciu hasła.<br>(Nie dotyczy urządzeń z systemami Windows RT).|
|**Wymagany typ hasła**|Określa typ hasła, które będzie wymagane, na przykład wyłącznie numeryczne lub alfanumeryczne.|
|**Minimalna długość hasła**|Określa minimalną wymaganą liczbę znaków w haśle urządzenia.|
|**Zezwalaj na proste hasła**|Określa, czy można używać prostych haseł, w tym „0000” i „1234”.|
|**Liczba dopuszczalnych nieudanych logowań przed wyczyszczeniem danych z urządzenia**|Określa, ile razy użytkownik może wprowadzić nieprawidłowe hasło, zanim zawartość urządzenia zostanie usunięta.|
|**Dni do wygaśnięcia hasła**|Określa liczbę dni, po której należy zmienić hasło urządzenia.
|**Pamiętaj historię haseł**|Określa, czy można korzystać z uprzednio używanych haseł.|
|**Pamiętaj historię haseł** — **Zapobiegaj ponownemu używaniu poprzednich haseł**|Określa liczbę wcześniej używanych haseł, których nie można użyć ponownie.|
|**Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**|Określa czas bezczynności urządzenia, po upływie którego ekran jest blokowany.

## <a name="encryption-settings"></a>Ustawienia szyfrowania

|Nazwa ustawienia|Szczegóły|
|----------------|---|
|**Wymagaj szyfrowania na urządzeniu przenośnym**<sup>1</sup>|Wymaga szyfrowania danych na urządzeniu z obsługą tej funkcji.<br><br>Dla urządzeń z systemem Windows Phone 8 trzeba ustawić wartość **Tak**.<br /><br />Aby włączyć szyfrowanie na urządzeniach z systemem iOS, włącz ustawienie **Wymagaj hasła do odblokowania urządzeń przenośnych**.|
|**Wymagaj szyfrowania na kartach pamięci**|Wymaga szyfrowania danych przechowywanych w pamięci zewnętrznej, np. na kartach SD (w obsługiwanych urządzeniach).
<sup>1</sup> Dodatkowe informacje dotyczące urządzeń z systemem Windows 8.1

-   Aby wymusić szyfrowanie na urządzeniach z systemem Windows 8.1, trzeba zainstalować na każdym urządzeniu [aktualizację klienta MDM dla systemu Windows z grudnia 2014 r.](https://support.microsoft.com/kb/3013816)

-   W przypadku włączenia tego ustawienia dla urządzeń z systemem Windows 8.1 wszyscy użytkownicy urządzeń muszą mieć konto Microsoft.

-   Aby szyfrowanie działało dla urządzeń z systemem Windows 8.1, urządzenie musi spełniać wymagania dotyczące certyfikacji sprzętu [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) firmy Microsoft.

-   W przypadku wymuszania szyfrowania na urządzeniu z systemem Windows 8.1 klucz odzyskiwania jest dostępny tylko za pośrednictwem konta Microsoft użytkownika, do którego można uzyskać dostęp z konta usługi OneDrive użytkownika. Nie można odzyskać tego klucza w imieniu użytkownika.

## <a name="email-settings"></a>Ustawienia poczty e-mail

|Nazwa ustawienia|Szczegóły
|----------------|---|
|**Zezwalaj użytkownikom na pobieranie załączników wiadomości e-mail**|Określa, czy na urządzenie można pobierać załączniki wiadomości e-mail.|
|**Okres synchronizacji wiadomości e-mail**|Określa liczbę dni synchronizacji odebranych wiadomości e-mail na urządzeniu.
|**Zezwalaj urządzeniom przenośnym, które nie obsługują w pełni ustawień programu Exchange ActiveSync, na synchronizowanie z programem Exchange**|Określa, czy zezwalać na dostęp do programu Exchange na urządzeniach, które nie obsługują co najmniej jednego ustawienia programu Exchange ActiveSync.

## <a name="browser-settings"></a>Ustawienia przeglądarki

|Nazwa ustawienia|Szczegóły
|----------------|---|
|**Zezwalaj na używanie przeglądarki sieci Web**|Określa, czy można używać przeglądarki sieci Web na urządzeniu.<br>(Niedostępne dla systemów Windows RT i Windows Phone).

## <a name="hardware-settings"></a>Ustawienia sprzętu

|Nazwa ustawienia|Szczegóły
|----------------|---|
|**Zezwalaj na używanie aparatu**|Określa, czy można używać aparatu w urządzeniu.<br>(Niedostępne dla systemów Windows RT i Windows Phone).



### <a name="see-also"></a>Zobacz także
[Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

