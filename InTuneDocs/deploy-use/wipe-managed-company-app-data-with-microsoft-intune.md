---
title: "Czyszczenie danych zarządzanych aplikacji firmowych | Microsoft Docs"
description: "Dowiedz się, jak można selektywnie zdalnie usunąć dane firmy z urządzeń."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2742e1d5-d2d5-42cd-b719-665dd6e0a0e9
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8a3e8634769b05e6639f7efb6394b7333d998f06
ms.openlocfilehash: 5d5cde748aa8fa464526d0dc2b2ef9ee460fff9d


---

# <a name="wipe-company-app-data-with-intune-mam"></a>Czyszczenie danych aplikacji firmowych za pomocą funkcji MAM usługi Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

W przypadku utraty lub kradzieży urządzenia lub jeśli pracownik odchodzi z firmy dane aplikacji firmowych powinny zostać usunięte z urządzenia. Jednak możesz nie chcieć usuwać osobistych danych znajdujących się na urządzeniu, zwłaszcza jeśli jest to urządzenie należące do pracownika.

Aby selektywnie usunąć dane aplikacji firmowych, utwórz żądanie czyszczenia, wykonując instrukcje opisane w tym temacie. Po wysłaniu żądania czyszczenia dane firmowe zostaną usunięte z aplikacji przy następnym uruchomieniu tej aplikacji na urządzeniu.

>[!IMPORTANT]
> Kontakty synchronizowane bezpośrednio z aplikacji do natywnej książki adresowej są usuwane. Nie można wyczyścić wszystkich kontaktów zsynchronizowanych z natywnej książki adresowej do innego źródła zewnętrznego. Obecnie dotyczy to tylko aplikacji Microsoft Outlook.

## <a name="create-a-wipe-request"></a>Tworzenie żądania czyszczenia

1.  Zaloguj się do [portalu Azure](https://portal.azure.com).

2.  Wybierz pozycję **Więcej usług**, wpisz **Intune** w polu tekstowym filtru i wybierz pozycję **Ochrona aplikacji w usłudze Intune**. Zostanie otwarty blok zarządzania aplikacjami mobilnymi usługi Intune.

    ![Zrzut ekranu przedstawiający blok Nowe żądanie czyszczenia](../media/AppManagement/wipe-request-mam-main-blade.png)

2.  W bloku **Ustawienia** wybierz pozycję **Żądania czyszczenia**.

3.  Wybierz pozycję **Nowe żądanie czyszczenia**. Zostanie otwarty blok **Nowe żądanie czyszczenia**.

    ![Zrzut ekranu przedstawiający blok Nowe żądanie czyszczenia](../media/AppManagement/AzurePortal_MAM_NewWipeRequest.png)

4.  Wybierz pozycję **Użytkownik**, aby otworzyć blok **Użytkownik** i wybrać użytkownika, którego dane aplikacji chcesz wyczyścić.

5.  Wybierz pozycję **Urządzenie**. Spowoduje to otwarcie bloku **Urządzenie**, który zawiera listę wszystkich urządzeń skojarzonych z wybranym użytkownikiem, a także dwie kolumny: nazwę urządzenia, którą jest przyjazna nazwa zdefiniowana przez użytkownika, oraz typ urządzenia, czyli jego platformę. Wybierz urządzenie, którego dane chcesz wyczyścić.

6.  Zostanie ponownie wyświetlony blok **Nowe żądanie czyszczenia**. Wybierz pozycję **OK**, aby wykonać żądanie czyszczenia. 

Usługa tworzy i śledzi oddzielne żądanie czyszczenia dla każdej chronionej aplikacji na urządzeniu oraz użytkownika skojarzonego z żądaniem czyszczenia.

>[!NOTE]
> Można również utworzyć **Żądania czyszczenia**, klikając **kafelek Żądanie czyszczenia** w bloku Zarządzanie aplikacjami mobilnymi w usłudze Intune.

## <a name="monitor-your-wipe-requests"></a>Monitorowanie żądań czyszczenia

Można wygenerować sumaryczny raport informujący o ogólnym stanie żądania czyszczenia oraz o liczbie oczekujących żądań oraz niepowodzeń. Aby uzyskać więcej szczegółów, wykonaj następujące kroki:

1.  W bloku Zarządzanie aplikacjami mobilnymi w usłudze Intune kliknij kafelek **Żądania czyszczenia**.

2.  W bloku **Żądanie czyszczenia** wybierz kafelek **Żądanie czyszczenia**, aby otworzyć blok **Żądanie czyszczenia**.

3.  W bloku **Żądanie czyszczenia** jest wyświetlana lista żądań pogrupowanych według użytkowników. System tworzy żądanie czyszczenia dla każdej chronionej aplikacji uruchomionej na urządzeniu, dlatego dla danego użytkownika może być wyświetlanych wiele żądań. Stan wskazuje, czy żądanie czyszczenia jest **oczekujące**, **zakończone niepowodzeniem** czy **zakończone pomyślnie**.

    ![Zrzut ekranu przedstawiający blok Nowe żądanie czyszczenia](../media/AppManagement/wipe-request-status-1.png)

Ponadto można wyświetlić nazwę i typ urządzenia, co może być przydatne podczas odczytywania raportów.

>[!IMPORTANT]
> Użytkownicy muszą otworzyć aplikację w celu przeprowadzenia czyszczenia — może ono zająć do 30 minut od czasu utworzenia żądania.

## <a name="delete-a-wipe-request"></a>Usuwanie żądania czyszczenia

Czyszczenia ze stanem oczekującym są wyświetlane do czasu ich ręcznego usunięcia.  Aby ręcznie usunąć żądanie czyszczenia

1.  W bloku Zarządzanie aplikacjami mobilnymi w usłudze Intune kliknij kafelek **Żądania czyszczenia**.

2.  W bloku **Żądanie czyszczenia** wybierz kafelek **Żądanie czyszczenia**, aby otworzyć blok **Żądanie czyszczenia**.

3.  Kliknij prawym przyciskiem myszy żądanie czyszczenia do usunięcia, a następnie wybierz pozycję **Usuń żądanie czyszczenia**.

    ![Zrzut ekranu przedstawiający blok Nowe żądanie czyszczenia](../media/AppManagement/delete-wipe-request.png)

4.  Zostanie wyświetlony monit o potwierdzenie usunięcia. Wybierz przycisk **Tak** lub **Nie**, następnie kliknij przycisk **OK**.


### <a name="see-also"></a>Zobacz także
[Ochrona danych aplikacji przy użyciu zasad zarządzania aplikacjami mobilnymi](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

[Korzystanie z witryny Azure Portal](azure-portal-for-microsoft-intune-mam-policies.md)



<!--HONumber=Feb17_HO1-->


