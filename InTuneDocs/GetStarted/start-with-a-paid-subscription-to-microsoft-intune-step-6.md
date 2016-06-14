---
# required metadata

title: Tworzenie zasad i publikowanie aplikacji | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e0d8e98f-7dd8-4cbf-887c-a9af63ffe970

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Tworzenie zasad i publikowanie aplikacji
Zasady usługi Intune udostępniają ustawienia, które ułatwiają sterowanie ustawieniami zabezpieczeń na urządzeniach przenośnych, obsługę ustawień Zapory systemu Windows i programu Endpoint Protection dla komputerów oraz wdrażanie aplikacji. Aby dowiedzieć się więcej, zobacz [Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](/Intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) i [Zabezpieczanie komputerów z systemem Windows przy użyciu programu Endpoint Protection dla usługi Microsoft Intune](/Intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune).

Usługa Intune zapewnia dwa typy instalacji aplikacji. Pierwsza to **instalacja wymagana**, w przypadku której aplikacja jest wdrażana automatycznie na zarządzanych komputerach. Druga to **instalacja dostępna**, w przypadku której aplikacja lub link do aplikacji jest wdrażany w portalu firmy usługi Intune, dzięki czemu użytkownicy mogą zdecydować się na jej instalację na swoich urządzeniach przenośnych.

<!-- this section really isn't necessary and confuses a lot of people because most mobile device apps aren't licensed this way (and our licensing/reporting features aren't super helpful). I think it's best to avoid this during a quick start guide.

Before using Intune to deploy apps, make sure that you have the appropriate licenses to publish, distribute, and use the app. The Licenses workspace lets you add and manage license agreement information for apps or software purchased through Microsoft Volume Licensing agreements, and for Microsoft or non-Microsoft software that was purchased by other means. You can then create license reports that display managed license usage information throughout your company to stay informed of license usage activity.
-->

Poniższe kroki ułatwiają określenie zasad konfiguracji urządzeń przenośnych oraz zasad zapory komputerów z systemem Windows, jak również skonfigurowanie aplikacji Skype jako instalacji dostępnej dla urządzeń przenośnych po ich rejestracji.

> [!TIP]
> Po dodaniu i wdrożeniu nowej zasady wszyscy użytkownicy i urządzenia należący do grupy, dla której określono zasadę, dziedziczą ustawienia jako zasadę podstawową. W każdym momencie możesz sprawdzić i zmienić szczegóły tych zasad w obszarze roboczym Zasady.


## Tworzenie i wdrażanie zasad konfiguracji urządzeń przenośnych

1.  Otwórz [konsolę administracyjną usługi Intune](https://manage.microsoft.com/)..

2.  W lewym okienku wybierz ikonę **Zasady**.

    ![Obszar roboczy Zasady w konsoli administracyjnej](./media/policy.png)

3.  Na liście **Zadania** na stronie **Przegląd zasad** wybierz pozycję **Dodaj zasady**..

4.  Na liście zasad rozwiń platformę, dla której chcesz utworzyć zasadę, a następnie wybierz pozycje **Konfiguracja ogólna** > **Utwórz zasadę niestandardową i przeprowadź jej wdrożenie z zalecanymi ustawieniami** > **Utwórz zasady**..

5.  Po wyświetleniu monitu o treści **Wybierz grupy, do których te zasady mają zostać wdrożone** wybierz z listy dostępnych grup pozycję **Użytkownicy usługi Intune** (grupa utworzona w poprzednim kroku), a następnie wybierz pozycje **Dodaj** > **OK**..

Twoje zasady pojawią się na liście zasad konfiguracji i zostaną wdrożone do grupy **Użytkownicy usługi Intune**. Kliknij dwukrotnie zasadę, aby wyświetlić jej ustawienia.

## Publikowanie aplikacji Skype dla urządzeń przenośnych

1.  W [konsoli administracyjnej usługi Intune](https://manage.microsoft.com/) wybierz ikonę **Aplikacje**, a następnie wybierz pozycje **Aplikacje** > **Dodaj aplikację**. Jeśli zostanie wyświetlony monit, wprowadź swoje poświadczenia usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

    ![Obszar roboczy Aplikacje konsoli administracyjnej](./media/apps.png)

    > [!NOTE]
    > Po pierwszym uruchomieniu **Wydawcy oprogramowania usługi Intune** wystąpi krótkie opóźnienie podczas instalowania aplikacji.

2.  Przejrzyj ostrzeżenie o zabezpieczeniach, a następnie wybierz przycisk **Uruchom**..

3.  Na stronie **Przed rozpoczęciem** wybierz pozycję **Dalej**..

4.  Na stronie **Instalator oprogramowania** w obszarze **Wybierz, w jaki sposób to oprogramowanie ma zostać udostępnione urządzeniom**wybierz pozycję **Link zewnętrzny**..

5.  W polu **Określ adres URL** wprowadź link zewnętrzny dla oprogramowania, a następnie wybierz pozycję **Dalej**. Upewnij się, że adres URL jest poprzedzony prefiksem **http://**. Wybierz poniższy link aplikacji Skype odpowiadający platformie urządzenia przenośnego, z której korzystasz:

    -   **iOS:**   [https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8](https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8)

    -   **Android:**  [https://play.google.com/store/apps/details?id=com.skype.raider](https://play.google.com/store/apps/details?id=com.skype.raider)

    -   **Windows Phone 8 lub Windows Phone 8.1:**  [http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51](http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51)

6.  Na stronie **Opis oprogramowania** podaj informacje dotyczące oprogramowania, które mają być wyświetlane użytkownikom w Portalu firmy, a następnie wybierz przycisk **Dalej**. Dostępne są następujące ustawienia (ten przykład dotyczy programu Skype):

    -   **Wydawca:** Wprowadź nazwę wydawcy, „Microsoft”:

    -   **Nazwa:** Wprowadź **Skype**

    -   **Opis:** Wprowadź opis oprogramowania, na przykład **Aplikacja do komunikacji Skype**

    -   **Kategoria:** Wybierz kategorię, która najlepiej pasuje do tego oprogramowania, na przykład **Współpraca**

    -   **Wyświetlaj jako polecaną aplikację i wyróżnij w Portalu firmy:** Wybierz tę opcję, aby wyróżnić aplikację w Portalu firmy na urządzeniach przenośnych.

    -   **Ikona:** określ, czy z oprogramowaniem ma zostać skojarzona ikona. Maksymalny rozmiar opcjonalnej ikony to 250x250 pikseli, ale zalecany rozmiar to 32x32 piksele.

7.  Na stronie **Podsumowanie** zweryfikuj informacje o oprogramowaniu, a następnie wybierz pozycję **Przekaż**. Wybierz pozycję **Zamknij**, aby zakończyć działanie kreatora.

8.  W [konsoli administracyjnej usługi Intune](https://manage.microsoft.com/) wybierz pozycje **Aplikacje** > **Aplikacje** > **Skype** > **Zarządzaj wdrożeniem**..

9. Na stronie **Wybierz grupę** wybierz pozycję **Użytkownicy usługi Intune**, aby wdrożyć oprogramowanie dla tej grupy użytkowników, a następnie wybierz pozycje **Dodaj** > **Dalej**..

10. Na stronie **Akcja wdrażania** wybierz pozycję **Dostępna instalacja** w kolumnie **Zatwierdzenie** dla tej grupy.

11. Wybierz pozycję **Zakończ**.

Aplikacja Skype jest teraz dostępna do instalacji na urządzeniach przenośnych z portalu firmy, ale najpierw należy zainstalować oprogramowanie usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] na komputerach i urządzeniach przenośnych.


### Następne kroki
Gratulacje! Krok 6 *przewodnika Szybki start dotyczącego usługi Intune* został ukończony..

>[!div class="step-by-step"]

>[&larr; **Organizowanie użytkowników i urządzeń**](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)       [**Dostosowywanie Portalu firmy** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-7.md)  


<!--HONumber=May16_HO1-->

