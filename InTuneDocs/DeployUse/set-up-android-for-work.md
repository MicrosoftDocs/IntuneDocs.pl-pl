---
title: "Konfigurowanie zarządzania programem Android for Work | Microsoft Intune"
description: "Włączanie zarządzania urządzeniami przenośnymi (MDM) dla urządzeń z programem Android for Work w usłudze Microsoft Intune."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b2fdcea9-9ad7-4d73-88e2-854b7a774bb2
translationtype: Human Translation
ms.sourcegitcommit: 519b66c94f3d056e060ed11e1a3d7d6d118a94fb
ms.openlocfilehash: 5f48303dd28627f961f8c2cfd38f8977354e2724


---

# Włączanie rejestracji urządzeń z programem Android for Work

Aby włączyć zarządzanie urządzeniami z programem Android for Work, należy dodać powiązanie programu Android for Work do usługi Intune. Aby zarejestrować urządzenia, które obsługują program Android for Work, ale zostały wcześniej zarejestrowane jako zwykłe urządzenia z systemem Android, urządzenia muszą zostać wyrejestrowane i ponownie zarejestrowane.

## Dodawanie powiązania programu Android for Work dla usługi Intune

1. **Konfigurowanie usługi Intune**<br>
Jeśli usługa ta nie została jeszcze skonfigurowana, przygotuj się do zarządzania urządzeniami przenośnymi, [ustawiając urząd zarządzania urządzeniami przenośnymi](prerequisites-for-enrollment.md#set-mobile-device-management-authority) na usługę **Microsoft Intune** i konfigurując zarządzanie urządzeniami przenośnymi.

2. **Konfigurowanie powiązania programu Android for Work**<br>
    Jako administrator otwórz [konsolę administracyjną usługi Microsoft Intune](http://manage.microsoft.com), wybierz pozycje **Administracja** &gt; **Zarządzanie urządzeniami przenośnymi** &gt; **Android for Work** i kliknij pozycję **Konfiguruj**, aby otworzyć stronę programu Android for Work w witrynie Google Play. Spowoduje to otwarcie nowej karty w przeglądarce.

3. **Logowanie do usługi Google**<br>
   Na stronie logowania do usługi Google zaloguj się do konta Google, które zostanie skojarzone z wszystkimi zadaniami zarządzania programu Android for Work dla tej dzierżawy. Może to być konto Google współużytkowane przez administratorów, którzy zarządzają usługą Intune. Jest to konto Google, które jest używane przez organizację do zarządzania aplikacjami i ich publikowania w konsoli Play for Work.

4. **Podawanie szczegółów dotyczących organizacji**<br>
   Podaj nazwę firmy w polu **Organization name** (Nazwa organizacji). W polu **Enterprise mobility management (EMM) provider** (Dostawca usługi zarządzania mobilnością w przedsiębiorstwie (EMM)) powinna być wyświetlona wartość *Microsoft Intune*. Wyraź zgodę na umowę programu Android for Work, a następnie kliknij pozycję **Confirm** (Potwierdź). Twoje żądanie zostanie przetworzone.

## Określanie ustawień rejestracji programu Android for Work
   Program Android for Work jest obsługiwany tylko na niektórych urządzeniach z systemem Android. Zobacz temat [Wymagania Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window") (program Google).  Każde urządzenie, które obsługuje program Android for Work, będzie także obsługiwać konwencjonalne zarządzanie systemem Android.  Usługa Intune pozwala określić, jak powinny być zarządzane urządzenia, które obsługują program Android for Work:

   - **Zarządzaj wszystkimi urządzeniami jak urządzeniami z systemem Android** — (wyłączone) wszystkie urządzenia z systemem Android, w tym urządzenia, które obsługują program Android for Work, zostaną zarejestrowane jako konwencjonalne urządzenia z systemem Android.
   - **Zarządzaj obsługiwanymi urządzeniami jak urządzeniami z programem Android for Work** — (włączone) wszystkie urządzenia, które obsługują program Android for Work, zostaną zarejestrowane jako urządzenia z programem Android for Work. Każde urządzenie z systemem Android, które nie obsługuje programu Android for Work, zostanie zarejestrowane jako konwencjonalne urządzenie z systemem Android.
   - **Zarządzaj obsługiwanymi urządzeniami jak urządzeniami z programem Android for Work tylko w tych grupach użytkowników** — (testowanie) umożliwia zastosowanie zarządzania programem Android for Work do ograniczonego zestawu użytkowników. Tylko urządzenia z programem Android for Work rejestrowane przez członków wybranych grup zostaną zarejestrowane jako urządzenia z programem Android for Work. Wszystkie inne zostaną zarejestrowane jako urządzenia z systemem Android.

## Kolejne kroki dla programu Android for Work
Po skonfigurowaniu wiązania programu Android for Work i ustawień można wykonać następujące czynności:
- [Wdrażanie aplikacji programu Android for Work](android-for-work-apps.md)
- [Dodawanie zasad konfiguracji programu Android for Work](android-for-work-policy-settings-in-microsoft-intune.md)

## Usuwanie powiązania konta administracyjnego programu Android for Work

Możesz wyłączyć rejestrację programu Android for Work i zarządzanie nim. Kliknięcie pozycji **Usuń powiązanie** usuwa wszystkie zarejestrowane urządzenia z programem Android for Work z rejestracji i spowoduje usunięcie relacji między kontem programu Android for Work a usługą Intune.

### Jak usunąć powiązanie konta programu Android for Work

1. **Usuwanie powiązania programu Android for Work**<br>
    Jako administrator otwórz [konsolę administracyjną usługi Microsoft Intune](http://manage.microsoft.com), wybierz pozycje **Administracja** &gt; **Zarządzanie urządzeniami przenośnymi** &gt; **Android for Work** i kliknij pozycję **Usuń powiązanie**.

2. **Wyrażanie zgody na usunięcie powiązania programu Android for Work**<br>
  Kliknij przycisk **Tak**, aby usunąć powiązanie i wyrejestrować wszystkie urządzenia z programem Android for Work z usługi Intune.



<!--HONumber=Oct16_HO2-->


