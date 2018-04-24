---
title: Konfigurowanie programu Android for Work
description: Włączanie zarządzania urządzeniami przenośnymi (MDM) dla urządzeń z programem Android for Work w usłudze Microsoft Intune.
keywords: ''
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/29/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: b2fdcea9-9ad7-4d73-88e2-854b7a774bb2
ROBOTS: NOINDEX,NOFOLLOW
ms.custom: intune-classic
ms.openlocfilehash: 366e2b281c05e1233c61f7f35a50700677ad4b79
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="enable-enrollment-of-android-for-work-devices"></a>Włączanie rejestracji urządzeń z programem Android for Work

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Aby włączyć zarządzanie urządzeniami z programem Android for Work, należy dodać powiązanie programu Android for Work do usługi Intune. Aby zarejestrować urządzenia, które obsługują program Android for Work, ale zostały wcześniej zarejestrowane jako zwykłe urządzenia z systemem Android, urządzenia muszą zostać wyrejestrowane i ponownie zarejestrowane.

## <a name="add-android-for-work-binding-for-intune"></a>Dodawanie powiązania programu Android for Work dla usługi Intune

1. **Skonfiguruj usługę**<br>
Jeśli usługa ta nie została jeszcze skonfigurowana, przygotuj się do zarządzania urządzeniami przenośnymi, [ustawiając urząd zarządzania urządzeniami przenośnymi](/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-8#enable-device-enrollment) na usługę **Microsoft Intune** i konfigurując zarządzanie urządzeniami przenośnymi.

2. **Konfigurowanie powiązania programu Android for Work**<br>
    Jako administrator usługi Intune otwórz konsolę administracyjną usługi [Microsoft Intune](https://manage.microsoft.com) i wybierz kolejno pozycje **Administracja** &gt; **Zarządzanie urządzeniami przenośnymi** &gt; **Android for Work**, a następnie kliknij pozycję **Konfiguruj**, aby otworzyć witrynę programu Android for Work w usłudze Google Play. Spowoduje to otwarcie nowej karty w przeglądarce.

3. **Logowanie do usługi Google**<br>
   Na stronie logowania do usługi Google wprowadź konto Google, które zostanie skojarzone ze wszystkimi zadaniami zarządzania programu Android for Work dla tej dzierżawy. Jest to konto Google udostępnione administratorom IT Twojej organizacji, które jest używane do zarządzania aplikacjami i ich publikowania w konsoli Play for Work.

4. **Podawanie szczegółów dotyczących organizacji**<br>
   Podaj nazwę firmy w polu **Organization name** (Nazwa organizacji). W polu **Enterprise mobility management (EMM) provider** (Dostawca usługi zarządzania mobilnością w przedsiębiorstwie (EMM)) powinna być wyświetlona wartość *Microsoft Intune*. Wyraź zgodę na umowę programu Android for Work, a następnie kliknij pozycję **Confirm** (Potwierdź). Twoje żądanie zostanie przetworzone.

## <a name="specify-android-for-work-enrollment-settings"></a>Określanie ustawień rejestracji programu Android for Work
   Program Android for Work jest obsługiwany tylko na niektórych urządzeniach z systemem Android. Zobacz temat [Wymagania Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window") (program Google).  Każde urządzenie, które obsługuje program Android for Work, będzie także obsługiwać konwencjonalne zarządzanie systemem Android.  Usługa Intune pozwala określić, jak powinny być zarządzane urządzenia, które obsługują program Android for Work:

   - **Zarządzaj wszystkimi urządzeniami jako urządzeniami z systemem Android** — wszystkie urządzenia z systemem Android, w tym urządzenia, które obsługują program Android for Work, zostaną zarejestrowane jako konwencjonalne urządzenia z systemem Android.
   - **Zarządzaj obsługiwanymi urządzeniami jako urządzeniami z programem Android for Work** — wszystkie urządzenia, które obsługują program Android for Work, zostaną zarejestrowane jako urządzenia z programem Android for Work. Każde urządzenie z systemem Android, które nie obsługuje programu Android for Work, zostanie zarejestrowane jako konwencjonalne urządzenie z systemem Android.
   - **Zarządzaj obsługiwanymi urządzeniami jako urządzeniami z programem Android for Work tylko w tych grupach użytkowników** — umożliwia zastosowanie zarządzania programem Android for Work do ograniczonego zestawu użytkowników. Tylko urządzenia z programem Android for Work rejestrowane przez członków wybranych grup zostaną zarejestrowane jako urządzenia z programem Android for Work. Wszystkie inne zostaną zarejestrowane jako urządzenia z systemem Android. Jest to przydatne podczas etapów pilotażowych programu Android for Work.

## <a name="next-steps-for-android-for-work"></a>Kolejne kroki dla programu Android for Work
Po skonfigurowaniu wiązania programu Android for Work i ustawień można wykonać następujące czynności:
- [Wdrażanie aplikacji programu Android for Work](android-for-work-apps.md)
- [Dodawanie zasad konfiguracji programu Android for Work](android-for-work-policy-settings-in-microsoft-intune.md)

## <a name="unbinding-your-android-for-work-administrative-account"></a>Usuwanie powiązania konta administracyjnego programu Android for Work

Możesz wyłączyć rejestrację programu Android for Work i zarządzanie nim. Kliknięcie pozycji **Usuń powiązanie** w konsoli administracyjnej usługi Intune usuwa wszystkie zarejestrowane urządzenia z programem Android for Work z rejestracji i spowoduje usunięcie relacji między kontem programu Android for Work a usługą Intune.

### <a name="how-to-unbind-an-android-for-work-account"></a>Jak usunąć powiązanie konta programu Android for Work

1. **Usuwanie powiązania programu Android for Work**<br>
    Jako administrator otwórz [konsolę administracyjną usługi Microsoft Intune](https://manage.microsoft.com), wybierz pozycje **Administracja** &gt; **Zarządzanie urządzeniami przenośnymi** &gt; **Android for Work** i kliknij pozycję **Usuń powiązanie**.

2. **Wyrażanie zgody na usunięcie powiązania programu Android for Work**<br>
  Kliknij przycisk **Tak**, aby usunąć powiązanie i wyrejestrować wszystkie urządzenia z programem Android for Work z usługi Intune.
