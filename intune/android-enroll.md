---
title: "Rejestrowanie urządzeń z systemem Android w usłudze Intune | Microsoft Docs"
titlesuffix: Azure portal
description: "Informacje o sposobie rejestrowania urządzeń z systemem Android w usłudze Intune."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/31/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e137da3ad4121f4b9cdfbb765ee00f71beca610a
ms.sourcegitcommit: a6fd6b3df8e96673bc2ea48a2b9bda0cf0a875ae
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2018
---
# <a name="enroll-android-devices"></a>Rejestrowanie urządzeń z systemem Android

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Jako administrator usługi Intune możesz zarządzać urządzeniami z systemem Android, w tym urządzeniami z systemem Samsung Knox Standard. Możesz również zarządzać profilem służbowym [na urządzeniach z programem Android for Work](#enable-enrollment-of-android-for-work-devices).

Urządzenia z systemem Samsung Knox Standard są obsługiwane w przypadku zarządzania wieloma użytkownikami za pomocą usługi Intune. Oznacza to, że użytkownicy mogą zalogować się na urządzeniu i wylogować się z niego przy użyciu swoich poświadczeń usługi Azure AD. Urządzenie jest zarządzane centralnie niezależnie od tego, czy jest używane. Po zalogowaniu się użytkownicy otrzymują dostęp do aplikacji oraz zostają wobec nich zastosowane zasady. Gdy użytkownicy się wylogują, wszystkie dane aplikacji są usuwane.

## <a name="prerequisite"></a>Wymaganie wstępne

Aby przygotować się do zarządzania urządzeniami przenośnymi, należy ustawić urząd zarządzania urządzeniami przenośnymi (MDM) na wartość **Microsoft Intune**. Instrukcje znajdują się w artykule [Set the MDM authority](mdm-authority-set.md) (Ustawianie urzędu MDM). Element ten ustawia się tylko raz podczas pierwszej konfiguracji usługi Intune do zarządzania urządzeniami przenośnymi.

## <a name="set-up-android-enrollment"></a>Konfiguracja rejestrowania urządzeń z systemem Android

Domyślnie usługa Intune zezwala na rejestrację urządzeń z systemem Android i Samsung Knox Standard.

Aby zablokować rejestrowanie urządzeń z systemem Android lub tylko urządzeń z systemem Android będących własnością użytkowników, zobacz [Ustawianie ograniczeń typu urządzeń](enrollment-restrictions-set.md).

Aby włączyć zarządzanie urządzeniami, użytkownicy muszą zarejestrować urządzenia, pobierając aplikację Portal firmy usługi Intune (dostępną w usłudze Google Play), a następnie otwierając aplikację i postępując zgodnie z instrukcjami. W odniesieniu do zarządzanych urządzeń z systemem Android możesz [przypisywać zasady zgodności](compliance-policy-create-android.md), [zarządzać aplikacjami](app-management.md) i wykonywać inne czynności.

## <a name="enable-enrollment-of-android-for-work-devices"></a>Włączanie rejestracji urządzeń z programem Android for Work

Aby włączyć zarządzanie profilem służbowym na urządzeniach [obsługujących program Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012), dodaj powiązanie programu Android for Work do usługi Intune. Aby zarejestrować urządzenia, które obsługują program Android for Work, ale zostały wcześniej zarejestrowane jako zwykłe urządzenia z systemem Android, musisz wyrejestrować urządzenia i ponownie je zarejestrować.

W przypadku rejestrowania urządzeń z programem Android for Work za pomocą konta [menedżera rejestracji urządzeń](device-enrollment-manager-enroll.md) na jednym koncie można zarejestrować maksymalnie 10 urządzeń.

## <a name="add-android-for-work-binding-for-intune"></a>Dodawanie powiązania programu Android for Work dla usługi Intune

> [!NOTE]
> Ze względu na interakcję między domenami firm Google i Microsoft ten krok może wymagać dostosowania ustawień przeglądarki, aby pomyślnie zakończyć akcję.  Upewnij się, że witryny „portal.azure.com” i „play.google.com” znajdują się w tej samej strefie zabezpieczeń w przeglądarce.

1. **Konfigurowanie funkcji zarządzania urządzeniami mobilnymi w usłudze Intune**<br>
Jeśli nie zostało to jeszcze zrobione, przygotuj się do zarządzania urządzeniami mobilnymi przez [skonfigurowanie jako urzędu zarządzania urządzeniami mobilnymi](mdm-authority-set.md) usługi **Microsoft Intune**.
2. **Konfigurowanie powiązania programu Android for Work**<br>
    Jako administrator usługi Intune wybierz w witrynie Azure Portal pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.

   a. W bloku **Intune** wybierz kolejno pozycje **Rejestrowanie urządzenia** > **Rejestracja w programie Android for Work** i wybierz pozycję **Konfiguruj**, aby otworzyć witrynę internetową sklepu Google Play dotyczącą programu Android for Work. Witryna internetowa jest otwierana w nowej karcie w przeglądarce.
   ![Zrzut ekranu przedstawiający link do konfiguracji powiązania programu Android for Work](./media/android-work-bind.png)

   b. **Logowanie do usługi Google**<br>
   Na stronie logowania do usługi Google wprowadź konto Google, które zostanie skojarzone ze wszystkimi zadaniami zarządzania programu Android for Work dla tej dzierżawy. Jest to konto Google używane przez administratorów IT organizacji do zarządzania aplikacjami i ich publikowania w konsoli Play for Work. Możesz użyć istniejącego konta Google lub utworzyć nowe konto.  Wybrane konto nie może być skojarzone z domeną G-Suite.

   c. **Podawanie szczegółów dotyczących organizacji**<br>
   Podaj nazwę firmy w polu **Organization name** (Nazwa organizacji). W polu **Enterprise mobility management (EMM) provider** (Dostawca usługi zarządzania mobilnością w przedsiębiorstwie (EMM)) powinna być wyświetlona wartość **Microsoft Intune**. Wyraź zgodę na umowę programu Android for Work, a następnie wybierz pozycję **Confirm** (Potwierdź). Twoje żądanie zostanie przetworzone.

## <a name="specify-android-for-work-enrollment-settings"></a>Określanie ustawień rejestracji programu Android for Work
Program Android for Work jest obsługiwany tylko na niektórych urządzeniach z systemem Android. Zobacz temat [Wymagania Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012%20style=%22target=new_window%22) (program Google). Każde urządzenie, które obsługuje program Android for Work, obsługuje także konwencjonalne zarządzanie systemem Android. Usługa Intune pozwala określić, jak w ramach [ograniczeń rejestracji](enrollment-restrictions-set.md) powinny być zarządzane urządzenia, które obsługują program Android for Work.

- **Blokuj (ustawienie domyślne)**: wszystkie urządzenia z systemem Android, w tym urządzenia, które obsługują program Android for Work, zostaną zarejestrowane jako konwencjonalne urządzenia z systemem Android.
- **Zezwalaj**: wszystkie urządzenia, które obsługują program Android for Work, zostaną zarejestrowane jako urządzenia z programem Android for Work. Każde urządzenie z systemem Android, które nie obsługuje programu Android for Work, zostanie zarejestrowane jako konwencjonalne urządzenie z systemem Android.

## <a name="approve-the-company-portal-app-in-the-managed-google-play-store"></a>Zatwierdzanie aplikacji Portal firmy w zarządzanym sklepie Google Play
Należy najpierw zatwierdzić aplikację Portal firmy dla systemu Android w zarządzanym sklepie Google Play, aby zapewnić, że będzie ona otrzymywać automatyczne aktualizacje aplikacji. Jeśli ta aplikacja nie zostanie zatwierdzona, aplikacja Portal firmy po pewnym czasie stanie się nieaktualna i może nie otrzymywać ważnych poprawek błędów i nowych funkcji wydawanych przez firmę Microsoft.

Wykonaj następujące kroki, aby zatwierdzić aplikację Portal firmy usługi Intune:

1.  Przejdź do aplikacji Portal firmy w [zarządzanym sklepie Google Play](https://play.google.com/work/apps/details?id=com.microsoft.windowsintune.companyportal).
2.  Zaloguj się do zarządzanego sklepu Google Play za pomocą tego samego konta, którego użyto do skonfigurowania powiązania na potrzeby programu Android for Work.
3.  Kliknij pozycję **Zatwierdź**.  Spowoduje to otwarcie nowego okna dialogowego.
4.  Przejrzyj uprawnienia w tym oknie dialogowym, a następnie kliknij przycisk **Zatwierdź**. Jest to konieczne, aby zezwolić na te uprawnienia w celu umożliwienia aplikacji Portal firmy zarządzanie profilem służbowym na urządzeniu.
5.  Wybierz pozycję **Utrzymuj zatwierdzenie, gdy aplikacja żąda nowych uprawnień**, a następnie kliknij przycisk **Zapisz**.

<!--  ## Next steps for Android for Work
After configuring the Android for Work binding and settings, you can do the following:
- [Deploy Android for Work apps](android-for-work-apps.md)
- [Add Android for Work configuration policies](android-for-work-policy-settings-in-microsoft-intune.md)  -->

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Poinformuj użytkowników, jak mogą zarejestrować swoje urządzenia w celu uzyskania dostępu do zasobów firmy

Poinformuj użytkowników, aby przeszli do usługi Google Play, aby pobrać aplikację Portal firmy usługi Intune, a następnie otworzyli aplikację i postępowali zgodnie z instrukcjami w celu zarejestrowania urządzenia. W trakcie procesu rejestracji użytkownicy są informowani, czego mogą oczekiwać, a także co administratorzy IT mogą i czego nie mogą wyświetlać na swoich urządzeniach.

Można także wysłać im link do kroków rejestracji online: [Rejestrowanie urządzenia z systemem Android w usłudze Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android).

Aby uzyskać informacje o innych zadaniach użytkowników, zobacz następujące artykuły:

- [Zasoby dotyczące środowiska użytkownika końcowego w usłudze Microsoft Intune](end-user-educate.md)
- [Korzystanie z urządzenia z systemem Android i usługi Intune](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

## <a name="unbind-your-android-for-work-administrative-account"></a>Usuwanie powiązania konta administracyjnego programu Android for Work

Możesz wyłączyć rejestrację programu Android for Work i zarządzanie nim. Wybranie pozycji **Usuń powiązanie** w konsoli administracyjnej usługi Intune usuwa wszystkie zarejestrowane urządzenia z programem Android for Work z rejestracji. Usuwa także relacje między kontem programu Android for Work a usługą Intune.

### <a name="to-unbind-an-android-for-work-account"></a>Jak usunąć powiązanie konta programu Android for Work

1. **Usuwanie powiązania programu Android for Work**<br>
    Jako administrator usługi Intune wybierz w witrynie Azure Portal pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.  W bloku **Intune** wybierz kolejno pozycje **Rejestrowanie urządzenia** > **Rejestracja w programie Android for Work**, a następnie wybierz pozycję **Usuń powiązanie**.

2. **Wyrażanie zgody na usunięcie powiązania programu Android for Work**<br>
  Wybierz pozycję **Tak**, aby usunąć powiązanie i wyrejestrować wszystkie urządzenia z programem Android for Work z usługi Intune.
