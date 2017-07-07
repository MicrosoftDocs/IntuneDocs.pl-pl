---
title: "Czyszczenie wyłącznie danych firmowych z aplikacji"
titleSuffix: Intune on Azure
description: "Informacje dotyczące selektywnego czyszczenia aplikacji w usłudze Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 02/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42605e6e-5b84-44ff-b86e-346ea123b53e
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bfebc391997ac4e63466eb3a09044318cf807dbc
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-wipe-only-corporate-data-from-intune-managed-apps"></a>Jak czyścić z aplikacji usługi Intune tylko dane firmowe

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

W przypadku utraty lub kradzieży urządzenia lub jeśli pracownik odchodzi z firmy dane aplikacji firmowych powinny zostać usunięte z urządzenia. Jednak możesz nie chcieć usuwać osobistych danych znajdujących się na urządzeniu, zwłaszcza jeśli jest to urządzenie należące do pracownika.

Aby selektywnie usunąć dane aplikacji firmowych, utwórz żądanie czyszczenia, wykonując instrukcje opisane w tym temacie. Po wysłaniu żądania czyszczenia dane firmowe zostaną usunięte z aplikacji przy następnym uruchomieniu tej aplikacji na urządzeniu.

>[!IMPORTANT]
> Kontakty synchronizowane bezpośrednio z aplikacji do natywnej książki adresowej są usuwane. Nie można wyczyścić wszystkich kontaktów zsynchronizowanych z natywnej książki adresowej do innego źródła zewnętrznego. Obecnie dotyczy to tylko aplikacji Microsoft Outlook.

## <a name="create-a-wipe-request"></a>Tworzenie żądania czyszczenia

1.  Zaloguj się do [portalu Azure](https://portal.azure.com).

2.  Wybierz pozycję **Więcej usług**, wpisz **Intune** w polu tekstowym filtru i wybierz pozycję **Usługa Intune**. Zostanie otwarty blok usługi Intune. Wybierz blok **Zarządzaj aplikacjami**.

    ![Zrzut ekranu przedstawiający blok Nowe żądanie czyszczenia](./media/intune-azure-preview-blade.png)

3.  W **bloku Aplikacje mobilne** wybierz pozycję **Nowe żądanie czyszczenia**. Zostanie otwarty blok **Nowe żądanie czyszczenia**.

4.  Wybierz pozycję **Nowe żądanie czyszczenia**. Zostanie otwarty blok **Nowe żądanie czyszczenia**.

    ![Zrzut ekranu przedstawiający blok Nowe żądanie czyszczenia](./media/AzurePortal_MAM_NewWipeRequest.png)

5.  Wybierz pozycję **Użytkownik**, aby otworzyć blok **Użytkownik** i wybrać użytkownika, którego dane aplikacji chcesz wyczyścić.

6.  Wybierz pozycję **Urządzenie**. Spowoduje to otwarcie bloku **Urządzenie**, który zawiera listę wszystkich urządzeń skojarzonych z wybranym użytkownikiem, a także dwie kolumny: nazwę urządzenia, którą jest przyjazna nazwa zdefiniowana przez użytkownika, oraz typ urządzenia, czyli jego platformę. Wybierz urządzenie, którego dane chcesz wyczyścić.

7.  Zostanie ponownie wyświetlony blok **Nowe żądanie czyszczenia**. Wybierz pozycję **OK**, aby wykonać żądanie czyszczenia. 

Usługa tworzy i śledzi oddzielne żądanie czyszczenia dla każdej chronionej aplikacji na urządzeniu oraz użytkownika skojarzonego z żądaniem czyszczenia.

## <a name="monitor-your-wipe-requests"></a>Monitorowanie żądań czyszczenia

Można wygenerować sumaryczny raport informujący o ogólnym stanie żądania czyszczenia oraz o liczbie oczekujących żądań oraz niepowodzeń. Aby uzyskać więcej szczegółów, wykonaj następujące kroki:

1.  W bloku **Aplikacje mobilne — Selektywne czyszczenie aplikacji** jest wyświetlana lista żądań pogrupowanych według użytkowników. System tworzy żądanie czyszczenia dla każdej chronionej aplikacji uruchomionej na urządzeniu, dlatego dla danego użytkownika może być wyświetlanych wiele żądań. Stan wskazuje, czy żądanie czyszczenia jest **oczekujące**, **zakończone niepowodzeniem** czy **zakończone pomyślnie**.

    ![Zrzut ekranu przedstawiający blok Nowe żądanie czyszczenia](./media/wipe-request-status-1.png)

Ponadto można wyświetlić nazwę i typ urządzenia, co może być przydatne podczas odczytywania raportów.

>[!IMPORTANT]
> Użytkownicy muszą otworzyć aplikację w celu przeprowadzenia czyszczenia — może ono zająć do 30 minut od czasu utworzenia żądania.

## <a name="delete-a-wipe-request"></a>Usuwanie żądania czyszczenia

Czyszczenia ze stanem oczekującym są wyświetlane do czasu ich ręcznego usunięcia.  Aby ręcznie usunąć żądanie czyszczenia:

1.  W bloku **Żądanie czyszczenia** wybierz kafelek **Żądanie czyszczenia**, aby otworzyć blok **Żądanie czyszczenia**.

2.  Kliknij prawym przyciskiem myszy żądanie czyszczenia do usunięcia, a następnie wybierz pozycję **Usuń żądanie czyszczenia**.

    ![Zrzut ekranu przedstawiający blok Nowe żądanie czyszczenia](./media/delete-wipe-request.png)

3.  Zostanie wyświetlony monit o potwierdzenie usunięcia. Wybierz przycisk **Tak** lub **Nie**, następnie kliknij przycisk **OK**.

### <a name="see-also"></a>Zobacz także
[What's app protection policy](app-protection-policy.md) (Co to są zasady ochrony aplikacji)

[What's app management](app-management.md) (Co to jest zarządzanie aplikacjami)