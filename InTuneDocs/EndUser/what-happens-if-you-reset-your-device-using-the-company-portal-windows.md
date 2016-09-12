---
title: "Co się dzieje w przypadku zresetowania urządzenia z systemem Windows przy użyciu Portalu firmy? | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1ee6e275-d1ec-4da3-bbef-d5da2c61a02a
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 38301b4e6964550008b08e99bf7016f1cc2561c3
ms.openlocfilehash: 6942bd5653bcb0aa11cdab18055bda7b86d0eae2


---


# Co się dzieje w przypadku zresetowania urządzenia z systemem Windows przy użyciu Portalu firmy?

Zresetowanie urządzenia z systemem Windows przy użyciu aplikacji Portal firmy lub [witryny Portal firmy](reset-your-device-cpwebsite.md) powoduje przywrócenie na urządzeniu ustawień fabrycznych oraz usunięcie wszystkich aplikacji, ustawień i danych, łącznie z danymi osobistymi. Wpływ na poszczególne urządzenia zależy od typu urządzenia i sposobu korzystania z urządzenia, zgodnie z opisem w poniższej tabeli. Aby uzyskać instrukcje dotyczące resetowania utraconego lub skradzionego urządzenia, zobacz [Resetowanie (wymazywanie) danych w przypadku utraty lub kradzieży urządzenia](reset-erase-your-lost-or-stolen-device-windows.md).

|Konfiguracja urządzenia i zarządzanie nim|Typ urządzenia|
|---------------------------------------|---------------|
|Urządzeniem przenośnym zarządza administrator IT|**Windows 10, Windows Phone 8.1 i Windows Phone 8**</br>Urządzenie nie będzie dłużej wyświetlane w Portalu firmy, a Portal firmy podejmie próbę zresetowania urządzenia do domyślnych ustawień fabrycznych. Dane osobowe, aplikacje i ustawienia użytkownika zostaną usunięte. <br /><br />**Windows 10 Mobile**: jedyną metodą wyrejestrowania urządzenia jest jego zresetowanie.<br /><br />**Windows RT**<br />Można resetować tylko urządzenia z systemem Windows RT używane do obsługi poczty e-mail.|
|Urządzenie może uzyskiwać dostęp tylko do firmowej poczty e-mail|**Windows Phone 8.1 i Windows Phone 8**<br />Urządzenie nie będzie dłużej wyświetlane w Portalu firmy, a konto firmowej poczty e-mail oraz niezapisane wiadomości e-mail zostaną usunięte.<br /><br />**Windows RT**<br />Urządzenie nie będzie dłużej wyświetlane w Portalu firmy, a konto firmowej poczty e-mail oraz niezapisane wiadomości e-mail zostaną usunięte.<br /><br />**Komputery z systemem Windows 7 lub Windows Vista**<br />Nie można zresetować komputera z uruchomionym systemem Windows 7 lub starszym używanego tylko do obsługi poczty e-mail.<br /><br />**Komputery z systemami Windows 8.1 i Windows 8**<br />Urządzenie nie będzie dłużej wyświetlane w Portalu firmy, a konto firmowej poczty e-mail oraz niezapisane wiadomości e-mail zostaną usunięte.|
|Komputery osobiste i laptopy|**Komputery z systemami Windows 8.1 i Windows 8**<br />Można resetować tylko komputery z uruchomionym systemem Windows 8 lub Windows 8.1 używane do obsługi poczty e-mail.<br /><br />**Komputery z systemem Windows 7 lub Windows Vista**<br />Nie można zresetować komputera z uruchomionym systemem Windows 7 lub starszym.|

Jeśli masz pytania, skontaktuj się z administratorem IT. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](http://portal.manage.microsoft.com).





<!--HONumber=Aug16_HO5-->


