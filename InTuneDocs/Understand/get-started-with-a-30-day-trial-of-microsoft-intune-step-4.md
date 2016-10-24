---
title: "Tworzenie zasad i publikowanie aplikacji dla użytkowników | Microsoft Intune"
description: "Tworzenie zasad i publikowanie aplikacji w przypadku rejestracji w celu skorzystania z bezpłatnej, 30-dniowej wersji ewaluacyjnej usługi Intune"
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 08/09/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c3a17884-442a-44f5-bc81-4589e823f65e
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 581e880fa4308ec627f5b2c1242fb5b30b713743
ms.openlocfilehash: 0fbc8fc23ce65987e4694bce0748362d8ce10153


---


# Tworzenie zasad i publikowanie aplikacji dla użytkowników wersji ewaluacyjnej
Zasady usługi Intune udostępniają ustawienia, które ułatwiają sterowanie ustawieniami zabezpieczeń na urządzeniach przenośnych, obsługę ustawień Zapory systemu Windows i programu Endpoint Protection dla komputerów oraz wdrażanie aplikacji. Jeśli planujesz używać usługi Intune z urządzeniami skonfigurowanymi do użycia w środowisku produkcyjnym po okresie ewaluacyjnym, absolutnie niezbędne jest postępowanie zgodnie z instrukcjami podanymi w tematach [Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) i [Zabezpieczanie komputerów z systemem Windows przy użyciu programu Endpoint Protection dla usługi Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune).

Usługa Intune zapewnia dwa typy instalacji aplikacji. Pierwsza to **instalacja wymagana**, w przypadku której aplikacja jest wdrażana automatycznie na zarządzanych komputerach. Druga to **instalacja dostępna**, w przypadku której aplikacja (lub link do niej) jest wdrażana w Portalu firmy usługi Intune, dzięki czemu użytkownicy mogą wybrać, czy zainstalować aplikację na swoich komputerach lub urządzeniach przenośnych.

Przed użyciem usługi Intune do wdrożenia aplikacji upewnij się, że masz odpowiednie licencje do publikowania, rozpowszechniania i korzystania z aplikacji. Obszar roboczy **Licencje** umożliwia dodawanie informacji o umowach licencyjnych i zarządzanie umowami licencyjnymi dotyczącymi aplikacji oraz oprogramowania zakupionego w ramach umów licencjonowania zbiorowego firmy Microsoft, a także aplikacji lub oprogramowania firmy Microsoft i innych firm zakupionego w inny sposób. Następnie możesz utworzyć raporty licencji, które zawierają informacje na temat wykorzystania licencji w firmie i pozwalają określić działania związane z licencjami.

Poniższe kroki obejmują określenie zasad konfiguracji urządzeń przenośnych oraz zasad zapory komputerów z systemem Windows, jak również skonfigurowanie aplikacji Skype jako instalacji dostępnej dla urządzeń przenośnych po ich rejestracji. Po dodaniu i wdrożeniu nowej zasady wszyscy użytkownicy i urządzenia należący do grupy, dla której określono zasadę, dziedziczą ustawienia jako zasadę podstawową. W każdym momencie możesz sprawdzić i zmienić szczegóły tych zasad w obszarze roboczym **Zasady** w konsoli administracyjnej.

## Tworzenie i wdrażanie zasad konfiguracji urządzeń przenośnych

1.  Otwórz [konsolę administracyjną usługi Intune](https://manage.microsoft.com/).

2.  W lewym okienku wybierz ikonę **Zasady**.

3.  Na liście **Zadania** na stronie **Przegląd zasad** wybierz pozycję **Dodaj zasady**.

4.  Na liście zasad rozwiń platformę, dla której chcesz utworzyć zasady, wybierz pozycję **Konfiguracja ogólna**, wybierz pozycję **Utwórz zasady i przeprowadź ich wdrożenie z zalecanymi ustawieniami**, a następnie wybierz pozycję **Utwórz zasady**.

5.  Po wyświetleniu monitu o treści **Wybierz grupy, do których te zasady mają zostać wdrożone** wybierz z listy pozycję **Moi użytkownicy próbni**, a następnie wybierz pozycje **Dodaj** &gt; **OK**.

Twoje zasady pojawią się na liście zasad konfiguracji i zostaną wdrożone do grupy **Moi użytkownicy próbni** . Kliknij dwukrotnie zasadę, aby wyświetlić jej ustawienia.

## Publikowanie aplikacji Skype dla urządzeń przenośnych

1.  W [konsoli administracyjnej usługi Intune](https://manage.microsoft.com/) wybierz ikonę **Aplikacje**, a następnie wybierz pozycje **Aplikacje** &gt; **Dodaj aplikację**. Jeśli zostanie wyświetlony monit, wprowadź swoje poświadczenia usługi Intune.

    > [!NOTE]
    > Po pierwszym uruchomieniu **Wydawcy oprogramowania usługi Intune** wystąpi krótkie opóźnienie podczas instalowania aplikacji.

2.  Przejrzyj ostrzeżenie o zabezpieczeniach, a następnie wybierz pozycję **Uruchom**.

3.  Na stronie **Przed rozpoczęciem** wybierz pozycję **Dalej**.

4.  Na stronie **Instalator oprogramowania** w obszarze **Wybierz, w jaki sposób to oprogramowanie ma zostać udostępnione urządzeniom**wybierz pozycję **Link zewnętrzny**.

5.  W polu **Określ adres URL** wprowadź link zewnętrzny dla oprogramowania, a następnie wybierz pozycję **Dalej**. Upewnij się, że adres URL jest poprzedzony prefiksem **https://**. Wybierz poniższy link aplikacji Skype odpowiadający platformie urządzenia przenośnego, z której korzystasz:

    -   **iOS:** [https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8](https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8)

    -   **Android:** [https://play.google.com/store/apps/details?id=com.skype.raider](https://play.google.com/store/apps/details?id=com.skype.raider)

    -   **Windows Phone 8.1:** [http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51](http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51)

6.  Na stronie **Opis oprogramowania** podaj informacje dotyczące oprogramowania, które mają być wyświetlane użytkownikom w Portalu firmy, a następnie wybierz pozycję **Dalej**. Dostępne są następujące ustawienia (ten przykład dotyczy programu Skype):

    -   **Wydawca**: Wprowadź nazwę wydawcy — **Microsoft**

    -   **Nazwa:** Wprowadź **Skype**

    -   **Opis:** Wprowadź opis oprogramowania, na przykład **Aplikacja do komunikacji Skype**

    -   **Kategoria:** Wybierz kategorię, która najlepiej pasuje do tego oprogramowania, na przykład **Współpraca**

    -   **Wyświetlaj jako polecaną aplikację i wyróżnij w Portalu firmy**: Wybierz tę opcję, aby wyróżnić aplikację w Portalu firmy na urządzeniach przenośnych.

    -   **Ikona:**  (Opcjonalnie) Określ, czy z oprogramowaniem ma zostać skojarzona ikona. Maksymalny rozmiar ikony to 250x250 pikseli, ale zalecany rozmiar ikon to 32x32 piksele.

7.  Na stronie **Podsumowanie** zweryfikuj informacje o oprogramowaniu, a następnie wybierz pozycję **Przekaż**. Wybierz pozycję **Zamknij**, aby zakończyć działanie kreatora.

8.  W [konsoli administracyjnej usługi Intune](https://manage.microsoft.com/) kliknij pozycje **Aplikacje** &gt; **Aplikacje** &gt; **Skype** &gt; **Zarządzaj wdrożeniem**.

9. Na stronie **Wybieranie grup** wybierz pozycję **Moi użytkownicy próbni**, aby wdrożyć oprogramowanie dla tej grupy użytkowników, a następnie wybierz pozycje **Dodaj** &gt; **Dalej**.

10. Na stronie **Akcja wdrażania** wybierz pozycję **Dostępna instalacja** w kolumnie **Zatwierdzenie** dla tej grupy.

11. Wybierz pozycję **Zakończ**.

Aplikacja Skype jest teraz dostępna do instalacji na urządzeniach przenośnych z poziomu Portalu firmy, ale najpierw należy zainstalować oprogramowanie usługi Intune na komputerach i urządzeniach przenośnych.

### Następne kroki
Gratulacje! Krok 4 przewodnika *wersji ewaluacyjnej usługi Microsoft Intune* właśnie został ukończony.

>[!div class="step-by-step"]

>[&larr; **Tworzenie grup**](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-3.md)     [**Rejestrowanie urządzeń** &rarr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-5.md)  



<!--HONumber=Oct16_HO2-->


