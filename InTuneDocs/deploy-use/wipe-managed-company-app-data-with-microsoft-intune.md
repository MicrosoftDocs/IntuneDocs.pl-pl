---
title: "Czyszczenie danych zarządzanych aplikacji firmowych | Microsoft Docs"
description: "Dowiedz się, jak można selektywnie zdalnie usunąć dane firmy z urządzeń."
keywords: 
author: stabar
ms.author: staciebarker
manager: angrobe
ms.date: 01/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2742e1d5-d2d5-42cd-b719-665dd6e0a0e9
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b75d034b4540f93eb235729b1cdad52b4c463eb0
ms.openlocfilehash: 3417d2966dea166c96a2b727977e8c85a63af80c


---

# <a name="wipe-managed-company-app-data-with-microsoft-intune"></a>Czyszczenie danych zarządzanych aplikacji firmowych za pomocą usługi Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

W przypadku utraty lub kradzieży urządzenia lub jeśli pracownik odchodzi z firmy dane aplikacji firmowych powinny zostać usunięte z urządzenia. Jednak możesz nie chcieć usuwać osobistych danych znajdujących się na urządzeniu, zwłaszcza jeśli jest to urządzenie należące do pracownika.

Aby selektywnie usunąć dane aplikacji firmowych, utwórz żądanie czyszczenia, wykonując instrukcje opisane w tym temacie. Po wysłaniu żądania czyszczenia dane firmowe zostaną usunięte z aplikacji przy następnym uruchomieniu tej aplikacji na urządzeniu.
>[!NOTE]
> Kontakty synchronizowane bezpośrednio z aplikacji do natywnej książki adresowej są usuwane. Nie można wyczyścić wszystkich kontaktów zsynchronizowanych z natywnej książki adresowej do innego źródła zewnętrznego. Obecnie dotyczy to tylko aplikacji Microsoft Outlook.



## <a name="create-a-wipe-request"></a>Tworzenie żądania czyszczenia

1.  Zaloguj się do witryny Azure Portal, a następnie wybierz **Więcej usług** > **Inne** > **Intune**.

2.  W bloku usługi Intune wybierz opcję **Zarządzaj aplikacjami** > **Selektywne czyszczenie aplikacji**.

3.  Wybierz pozycję **Nowe żądanie czyszczenia**. Zostanie otwarty blok **Nowe żądanie czyszczenia**.

    ![Zrzut ekranu przedstawiający blok Nowe żądanie czyszczenia](../media/AppManagement/AzurePortal_MAM_NewWipeRequest.png)

4.  Wybierz pozycję **Użytkownik**, aby otworzyć blok **Użytkownik** i wybrać użytkownika, którego dane aplikacji chcesz wyczyścić.

5.  Wybierz pozycję **Urządzenie**.  Spowoduje to otwarcie bloku **Urządzenie** , który zawiera listę wszystkich urządzeń skojarzonych z wybranym użytkownikiem.  Wybierz urządzenie, którego dane chcesz wyczyścić.

6.  Zostanie ponownie wyświetlony blok **Nowe żądanie czyszczenia**. Wybierz pozycję **OK**, aby wykonać żądanie czyszczenia. Usługa tworzy i śledzi każde żądanie czyszczenia dla każdej chronionej aplikacji na urządzeniu.

![Zrzut ekranu przedstawiający kafelek Żądania czyszczenia ](../media/AppManagement/AzurePortal_MAM_WipeRequestsSummary.png)

## <a name="monitor-your-wipe-requests"></a>Monitorowanie żądań czyszczenia

Na kafelku **Żądanie czyszczenia** znajduje się sumaryczny raport informujący o ogólnym stanie żądania czyszczenia oraz o liczbie oczekujących żądań oraz niepowodzeń. Aby uzyskać więcej szczegółów, wykonaj następujące kroki:

1.  W bloku usługi Intune wybierz opcję **Zarządzaj aplikacjami**.

2.  W bloku **Żądanie czyszczenia** wybierz kafelek **Żądanie czyszczenia**, aby otworzyć blok **Żądanie czyszczenia**.

3.  W bloku **Żądanie czyszczenia** jest wyświetlana lista żądań pogrupowanych według użytkowników. System tworzy żądanie czyszczenia dla każdej chronionej aplikacji uruchomionej na urządzeniu, dlatego dla danego użytkownika może być wyświetlanych wiele żądań. Stan wskazuje, czy żądanie czyszczenia jest **oczekujące**, **zakończone niepowodzeniem** czy **zakończone pomyślnie**.

Użytkownicy muszą otworzyć aplikację w celu przeprowadzenia czyszczenia — może ono zająć do 30 minut od czasu utworzenia żądania.

Czyszczenia ze stanem oczekującym są wyświetlane do czasu ich ręcznego usunięcia.  Aby ręcznie usunąć żądanie czyszczenia, kliknij prawym przyciskiem myszy i wybierz pozycję Usuń.

### <a name="see-also"></a>Zobacz także
[Ochrona danych aplikacji przy użyciu zasad zarządzania aplikacjami mobilnymi](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

[Korzystanie z witryny Azure Portal](azure-portal-for-microsoft-intune-mam-policies.md)



<!--HONumber=Jan17_HO4-->


