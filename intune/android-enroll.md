---
title: "Rejestrowanie urządzeń z systemem Android w usłudze Intune"
titleSuffix: Intune on Azure
description: "Informacje o sposobie rejestrowania urządzeń z systemem Android w usłudze Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 295315dae52662c386055747862717b85ed4b877
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2017
---
# <a name="enroll-android-devices"></a>Rejestrowanie urządzeń z systemem Android

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Jako administrator usługi Intune możesz zarządzać urządzeniami z systemem Android, w tym urządzeniami z systemem Samsung Knox Standard. Możesz również zarządzać profilem służbowym na urządzeniach [z programem Android for Work](#enable-enrollment-of-android-for-work-devices).

Urządzenia z systemem Samsung KNOX Standard są obsługiwane w przypadku zarządzania wieloma użytkownikami za pomocą usługi Intune. Oznacza to, że użytkownicy końcowi mogą zalogować się na urządzeniu lub wylogować się z niego przy użyciu poświadczeń usługi Azure AD, a urządzenie jest zarządzane centralnie niezależnie od tego, czy jest używane. Użytkownicy końcowi po zalogowaniu otrzymują dostęp do aplikacji, a także są stosowane wobec nich zasady. Gdy użytkownicy się wylogują, wszystkie dane aplikacji są usuwane.

## <a name="prerequisite"></a>Wymaganie wstępne

Należy ustawić urząd MDM na wartość **Microsoft Intune**, aby przygotować się do zarządzania urządzeniami przenośnymi. Instrukcje znajdują się w artykule [Set the MDM authority](mdm-authority-set.md) (Ustawianie urzędu MDM). Element ten ustawia się tylko raz podczas pierwszej konfiguracji usługi Intune do zarządzania urządzeniami przenośnymi.

## <a name="set-up-android-enrollment"></a>Konfiguracja rejestrowania urządzeń z systemem Android

Domyślnie usługa Intune zezwala na rejestrację urządzeń z systemem Android i Samsung Knox Standard.

Aby zablokować rejestrowanie urządzeń z systemem Android lub tylko urządzeń z systemem Android będących własnością użytkowników, zobacz [Ustawianie ograniczeń typu urządzeń](enrollment-restrictions-set.md).

Aby włączyć zarządzanie urządzeniami, użytkownicy muszą zarejestrować urządzenia, pobierając aplikację Portal firmy usługi Intune, która jest dostępna w usłudze Google Play, a następnie otwierając aplikację i postępując zgodnie z instrukcjami w celu zarejestrowania. W odniesieniu do zarządzanych urządzeń z systemem Android możesz [przypisywać zasady zgodności](compliance-policy-create-android.md), [zarządzać aplikacjami](app-management.md) i wykonywać inne czynności.

## <a name="enable-enrollment-of-android-for-work-devices"></a>Włączanie rejestracji urządzeń z programem Android for Work

Aby włączyć zarządzanie profilem służbowym na urządzeniach [obsługujących program Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012), dodaj powiązanie programu Android for Work do usługi Intune. Aby zarejestrować urządzenia, które obsługują program Android for Work, ale zostały wcześniej zarejestrowane jako zwykłe urządzenia z systemem Android, urządzenia muszą zostać wyrejestrowane i ponownie zarejestrowane.

## <a name="add-android-for-work-binding-for-intune"></a>Dodawanie powiązania programu Android for Work dla usługi Intune

1. **Konfigurowanie funkcji zarządzania urządzeniami mobilnymi w usłudze Intune**<br>
Jeśli nie zostało to jeszcze zrobione, przygotuj się do zarządzania urządzeniami mobilnymi przez [skonfigurowanie jako urzędu zarządzania urządzeniami mobilnymi](mdm-authority-set.md) usługi **Microsoft Intune**.

2. **Konfigurowanie powiązania programu Android for Work**<br>
    Jako administrator usługi Intune wybierz w witrynie Azure Portal pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.

    1. W bloku **Intune** wybierz kolejno pozycje **Rejestrowanie urządzenia** > **Rejestracja w programie Android for Work** i kliknij pozycję **Konfiguruj**, aby otworzyć witrynę sieci Web sklepu Google Play dotyczącą programu Android for Work. Spowoduje to otwarcie nowej karty w przeglądarce.
  ![Zrzut ekranu przedstawiający link do konfiguracji powiązania programu Android for Work](./media/android-work-bind.png)

    2. **Logowanie do usługi Google**<br>
   Na stronie logowania do usługi Google wprowadź konto Google, które zostanie skojarzone ze wszystkimi zadaniami zarządzania programu Android for Work dla tej dzierżawy. Jest to konto Google udostępnione administratorom IT Twojej organizacji, które jest używane do zarządzania aplikacjami i ich publikowania w konsoli Play for Work.

    3. **Podawanie szczegółów dotyczących organizacji**<br>
   Podaj nazwę firmy w polu **Organization name** (Nazwa organizacji). W polu **Enterprise mobility management (EMM) provider** (Dostawca usługi zarządzania mobilnością w przedsiębiorstwie (EMM)) powinna być wyświetlona wartość *Microsoft Intune*. Wyraź zgodę na umowę programu Android for Work, a następnie kliknij pozycję **Confirm** (Potwierdź). Twoje żądanie zostanie przetworzone.

## <a name="specify-android-for-work-enrollment-settings"></a>Określanie ustawień rejestracji programu Android for Work
   Program Android for Work jest obsługiwany tylko na niektórych urządzeniach z systemem Android. Zobacz temat [Wymagania Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window") (program Google). Każde urządzenie, które obsługuje program Android for Work, będzie także obsługiwać konwencjonalne zarządzanie systemem Android.  Usługa Intune pozwala określić, jak powinny być zarządzane urządzenia, które obsługują program Android for Work:

   - **Zarządzaj wszystkimi urządzeniami jako urządzeniami z systemem Android** — wszystkie urządzenia z systemem Android, w tym urządzenia, które obsługują program Android for Work, zostaną zarejestrowane jako konwencjonalne urządzenia z systemem Android.
   - **Zarządzaj obsługiwanymi urządzeniami jako urządzeniami z programem Android for Work** — wszystkie urządzenia, które obsługują program Android for Work, zostaną zarejestrowane jako urządzenia z programem Android for Work. Każde urządzenie z systemem Android, które nie obsługuje programu Android for Work, zostanie zarejestrowane jako konwencjonalne urządzenie z systemem Android.
   - **Zarządzaj obsługiwanymi urządzeniami jako urządzeniami z programem Android for Work tylko w tych grupach użytkowników** — umożliwia zastosowanie zarządzania programem Android for Work do ograniczonego zestawu użytkowników. Tylko urządzenia z programem Android for Work rejestrowane przez członków wybranych grup zostaną zarejestrowane jako urządzenia z programem Android for Work. Wszystkie inne zostaną zarejestrowane jako urządzenia z systemem Android. Jest to przydatne podczas etapów pilotażowych programu Android for Work.

<!--  ## Next steps for Android for Work
After configuring the Android for Work binding and settings, you can do the following:
- [Deploy Android for Work apps](android-for-work-apps.md)
- [Add Android for Work configuration policies](android-for-work-policy-settings-in-microsoft-intune.md)  -->

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Poinformuj użytkowników, jak mogą zarejestrować swoje urządzenia w celu uzyskania dostępu do zasobów firmy

Należy poinformować użytkowników, aby przeszli do usługi Google Play, aby pobrać aplikację Portal firmy usługi Intune, a następnie otworzyli aplikację i postępowali zgodnie z instrukcjami w celu zarejestrowania urządzenia. W trakcie procesu rejestracji użytkownicy są informowani, czego mogą oczekiwać, a także co administratorzy IT mogą i czego nie mogą wyświetlać na swoich urządzeniach.

Można także wysłać im link do kroków rejestracji online: [Rejestrowanie urządzenia z systemem Android w usłudze Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android).

Aby uzyskać informacje o innych zadaniach użytkownika końcowego, zobacz następujące artykuły:

- [Zasoby dotyczące środowiska użytkownika końcowego w usłudze Microsoft Intune](end-user-educate.md)
- [Korzystanie z urządzenia z systemem Android i usługi Intune](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

## <a name="unbinding-your-android-for-work-administrative-account"></a>Usuwanie powiązania konta administracyjnego programu Android for Work

Możesz wyłączyć rejestrację programu Android for Work i zarządzanie nim. Kliknięcie pozycji **Usuń powiązanie** w konsoli administracyjnej usługi Intune usuwa wszystkie zarejestrowane urządzenia z programem Android for Work z rejestracji i spowoduje usunięcie relacji między kontem programu Android for Work a usługą Intune.

### <a name="how-to-unbind-an-android-for-work-account"></a>Jak usunąć powiązanie konta programu Android for Work

1. **Usuwanie powiązania programu Android for Work**<br>
    Jako administrator usługi Intune wybierz w witrynie Azure Portal pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.  W bloku **Intune** wybierz kolejno pozycje **Rejestrowanie urządzenia** > **Rejestracja w programie Android for Work** i kliknij pozycję **Usuń powiązanie**.

2. **Wyrażanie zgody na usunięcie powiązania programu Android for Work**<br>
  Kliknij przycisk **Tak**, aby usunąć powiązanie i wyrejestrować wszystkie urządzenia z programem Android for Work z usługi Intune.
