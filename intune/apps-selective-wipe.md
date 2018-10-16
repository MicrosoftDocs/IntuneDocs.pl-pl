---
title: Czyszczenie wyłącznie danych firmowych z aplikacji
titleSuffix: Microsoft Intune
description: Informacje dotyczące selektywnego czyszczenia aplikacji w usłudze Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/09/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 42605e6e-5b84-44ff-b86e-346ea123b53e
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7881e117893ec01098c13f79e00a2b5388652155
ms.sourcegitcommit: 11bd3dbbc9dd762df7c6d20143f2171799712547
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2018
ms.locfileid: "48903560"
---
# <a name="how-to-wipe-only-corporate-data-from-intune-managed-apps"></a>Jak czyścić z aplikacji usługi Intune tylko dane firmowe

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

W przypadku utraty lub kradzieży urządzenia lub jeśli pracownik odchodzi z firmy dane aplikacji firmowych powinny zostać usunięte z urządzenia. Jednak możesz nie chcieć usuwać osobistych danych znajdujących się na urządzeniu, zwłaszcza jeśli jest to urządzenie należące do pracownika.

>[!NOTE]
> Systemy iOS i Android to dwie platformy, które są obecnie obsługiwane pod kątem czyszczenia danych firmowych z poziomu aplikacji zarządzanych przez usługę Intune.

Aby selektywnie usunąć dane aplikacji firmowych, utwórz żądanie czyszczenia, wykonując instrukcje opisane w tym temacie. Po wysłaniu żądania czyszczenia dane firmowe zostaną usunięte z aplikacji przy następnym uruchomieniu tej aplikacji na urządzeniu. Oprócz utworzenia żądania czyszczenia możesz skonfigurować selektywne czyszczenie danych organizacji jako nową akcję, gdy nie są spełnione warunki ustawień dostępu zasad ochrony aplikacji. Ta funkcja pomaga automatycznie chronić i usuwać poufne dane organizacji z aplikacji na podstawie wstępnie skonfigurowanych kryteriów.

>[!IMPORTANT]
> Kontakty synchronizowane bezpośrednio z aplikacji do natywnej książki adresowej są usuwane. Nie można wyczyścić wszystkich kontaktów zsynchronizowanych z natywnej książki adresowej do innego źródła zewnętrznego. Obecnie dotyczy to tylko aplikacji Microsoft Outlook.

## <a name="create-a-wipe-request"></a>Tworzenie żądania czyszczenia

1.  Zaloguj się do [portalu Azure](https://portal.azure.com).

2.  Wybierz pozycję **Wszystkie usługi**, wpisz **Intune** w polu tekstowym filtru i wybierz pozycję **Usługa Intune**. Zostanie otwarte okienko usługi Intune. Wybierz okienko **Aplikacje klienckie**.

    ![Zrzut ekranu przedstawiający okienko usługi Microsoft Intune](./media/apps-selective-wipe01.png)

3.  W okienku **Aplikacje klienckie** wybierz pozycję **Selektywne czyszczenie aplikacji**.

4.  Wybierz pozycję **Nowe żądanie czyszczenia**. Zostanie otwarte okienko **Nowe żądanie czyszczenia**.

    ![Zrzut ekranu przedstawiający okienko Nowe żądanie czyszczenia](./media/AzurePortal_MAM_NewWipeRequest.png)

5.  Wybierz użytkownika, a następnie pozycję **Wybierz**, aby wybrać użytkownika, którego dane aplikacji chcesz wyczyścić.

6.  Następnie wybierz pozycję **Urządzenie** z okienka **Nowe żądanie czyszczenia**. Spowoduje to otwarcie okienka **Wybieranie urządzenia**, które zawiera listę wszystkich urządzeń skojarzonych z wybranym użytkownikiem, a także dwie kolumny: nazwę urządzenia, którą jest przyjazna nazwa zdefiniowana przez użytkownika, oraz typ urządzenia, czyli jego platformę. Wybierz urządzenie, którego dane chcesz wyczyścić.

7.  Zostanie ponownie wyświetlone okienko **Nowe żądanie czyszczenia**. Wybierz pozycję **OK**, aby wykonać żądanie czyszczenia.

Usługa tworzy i śledzi oddzielne żądanie czyszczenia dla każdej chronionej aplikacji na urządzeniu oraz użytkownika skojarzonego z żądaniem czyszczenia.

## <a name="monitor-your-wipe-requests"></a>Monitorowanie żądań czyszczenia

Można wygenerować sumaryczny raport informujący o ogólnym stanie żądania czyszczenia oraz o liczbie oczekujących żądań oraz niepowodzeń. Aby uzyskać więcej szczegółów, wykonaj następujące kroki:

1.  W okienku **Aplikacje klienckie — Selektywne czyszczenie aplikacji** jest wyświetlana lista żądań pogrupowanych według użytkowników. System tworzy żądanie czyszczenia dla każdej chronionej aplikacji uruchomionej na urządzeniu, dlatego dla danego użytkownika może być wyświetlanych wiele żądań. Stan wskazuje, czy żądanie czyszczenia jest **oczekujące**, **zakończone niepowodzeniem** czy **zakończone pomyślnie**.

    ![Zrzut ekranu przedstawiający stan żądania czyszczenia w okienku Selektywne czyszczenie aplikacji](./media/wipe-request-status-1.png)

Ponadto można wyświetlić nazwę i typ urządzenia, co może być przydatne podczas odczytywania raportów.

>[!IMPORTANT]
> Użytkownicy muszą otworzyć aplikację w celu przeprowadzenia czyszczenia — może ono zająć do 30 minut od czasu utworzenia żądania.

## <a name="delete-a-wipe-request"></a>Usuwanie żądania czyszczenia

Czyszczenia ze stanem oczekującym są wyświetlane do czasu ich ręcznego usunięcia. Aby ręcznie usunąć żądanie czyszczenia:

1.  W okienku **Aplikacje klienckie — Selektywne czyszczenie aplikacji**.

2.  Na liście kliknij prawym przyciskiem myszy żądanie czyszczenia do usunięcia, a następnie wybierz pozycję **Usuń żądanie czyszczenia**.

    ![Zrzut ekranu przedstawiający listę żądań czyszczenia w okienku Selektywne czyszczenie aplikacji](./media/delete-wipe-request.png)

3.  Zostanie wyświetlony monit o potwierdzenie usunięcia. Wybierz przycisk **Tak** lub **Nie**, następnie kliknij przycisk **OK**.

### <a name="see-also"></a>Zobacz też
[What's app protection policy](app-protection-policy.md) (Co to są zasady ochrony aplikacji)

[What's app management](app-management.md) (Co to jest zarządzanie aplikacjami)
