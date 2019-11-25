---
title: Czyszczenie wyłącznie danych firmowych z aplikacji
titleSuffix: Microsoft Intune
description: Dowiedz się, jak selektywnie czyścić wyłącznie dane firmowe z aplikacji zarządzanych przez usługę Intune w usłudze Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 42605e6e-5b84-44ff-b86e-346ea123b53e
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0fafe7c17c698a5eb4e5ad6825bee0ae3fe874c2
ms.sourcegitcommit: 01fb3d844958a0e66c7b87623160982868e675b0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2019
ms.locfileid: "74199232"
---
# <a name="how-to-wipe-only-corporate-data-from-intune-managed-apps"></a>Jak czyścić z aplikacji usługi Intune tylko dane firmowe

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

W przypadku utraty lub kradzieży urządzenia lub jeśli pracownik odchodzi z firmy dane aplikacji firmowych powinny zostać usunięte z urządzenia. Jednak możesz nie chcieć usuwać osobistych danych znajdujących się na urządzeniu, zwłaszcza jeśli jest to urządzenie należące do pracownika.

>[!NOTE]
> Systemy iOS, Android i Windows 10 to jedyne platformy, które są obecnie obsługiwane pod kątem czyszczenia danych firmowych z poziomu aplikacji zarządzanych przez usługę Intune. Aplikacje zarządzane przez usługę Intune to aplikacje obejmujące zestaw SDK zasad ochrony aplikacji Intune i mające konto licencjonowanego użytkownika w Twojej organizacji. Wdrożenie zasad ochrony aplikacji nie jest wymagane do włączenia selektywnego czyszczenia aplikacji.

Aby selektywnie usunąć dane aplikacji firmowych, utwórz żądanie czyszczenia, wykonując instrukcje opisane w tym temacie. Po wysłaniu żądania czyszczenia dane firmowe zostaną usunięte z aplikacji przy następnym uruchomieniu tej aplikacji na urządzeniu. Oprócz utworzenia żądania czyszczenia możesz skonfigurować selektywne czyszczenie danych organizacji jako nową akcję, gdy nie są spełnione warunki ustawień dostępu zasad ochrony aplikacji. Ta funkcja pomaga automatycznie chronić i usuwać poufne dane organizacji z aplikacji na podstawie wstępnie skonfigurowanych kryteriów.

>[!IMPORTANT]
> Kontakty synchronizowane bezpośrednio z aplikacji do natywnej książki adresowej są usuwane. Nie można wyczyścić wszystkich kontaktów zsynchronizowanych z natywnej książki adresowej do innego źródła zewnętrznego. Obecnie dotyczy to tylko aplikacji Microsoft Outlook.

## <a name="deployed-wip-policies-without-user-enrollment"></a>Wdrożone zasady funkcji WIP bez rejestracji użytkownika
Zasady funkcji Windows Information Protection (WIP) można wdrożyć bez konieczności rejestracji urządzeń z systemem Windows 10 przez użytkowników zarządzania urządzeniami przenośnymi. Ta konfiguracja pozwala firmom na ochronę firmowych dokumentów na podstawie konfiguracji funkcji WIP, jednocześnie umożliwiając użytkownikom zarządzanie własnymi urządzeniami z systemem Windows. Gdy dokumenty są chronione za pomocą zasad funkcji WIP, chronione dane mogą być selektywnie czyszczone przez administratora usługi Intune. Wybierając użytkownika i urządzenie oraz wysyłając żądanie czyszczenia, wszystkie dane chronione za pomocą zasad funkcji WIP staną się bezużyteczne. Z usługi Intune w witrynie Azure Portal wybierz pozycję **Aplikacja kliencka** > **Selektywne czyszczenie aplikacji**. Aby uzyskać więcej informacji, zobacz [Tworzenie i wdrażanie zasad ochrony aplikacji w funkcji Windows Information Protection (WIP) za pomocą usługi Intune](windows-information-protection-policy-create.md).

## <a name="create-a-wipe-request"></a>Tworzenie żądania czyszczenia

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. W okienku usługi Intune wybierz pozycję **Aplikacje klienckie** > **Selektywne czyszczenie aplikacji** > **Utwórz żądanie czyszczenia**.<br>
   Zostanie wyświetlone okienko **Tworzenie żądania czyszczenia**.
3. Kliknij pozycję **Wybierz użytkownika**, wybierz użytkownika, którego dane aplikacji chcesz wyczyścić, a następnie kliknij pozycję **Wybierz** w dolnej części okienka **Użytkownik**.
4. Kliknij pozycję **Wybierz urządzenie**, wybierz urządzenie, a następnie kliknij pozycję **Wybierz** w dolnej części okienka **wybierania urządzenia**.
5. Kliknij pozycję **Utwórz**, aby wykonać żądanie czyszczenia.

Usługa tworzy i śledzi oddzielne żądanie czyszczenia dla każdej chronionej aplikacji na urządzeniu oraz użytkownika skojarzonego z żądaniem czyszczenia.

## <a name="monitor-your-wipe-requests"></a>Monitorowanie żądań czyszczenia

Można wygenerować sumaryczny raport informujący o ogólnym stanie żądania czyszczenia oraz o liczbie oczekujących żądań oraz niepowodzeń. Aby uzyskać więcej szczegółów, wykonaj następujące kroki:

1. W okienku **Aplikacje klienckie — Selektywne czyszczenie aplikacji** jest wyświetlana lista żądań pogrupowanych według użytkowników. System tworzy żądanie czyszczenia dla każdej chronionej aplikacji uruchomionej na urządzeniu, dlatego dla danego użytkownika może być wyświetlanych wiele żądań. Stan wskazuje, czy żądanie czyszczenia jest **oczekujące**, **zakończone niepowodzeniem** czy **zakończone pomyślnie**.

    ![Zrzut ekranu przedstawiający stan żądania czyszczenia w okienku Selektywne czyszczenie aplikacji](./media/apps-selective-wipe/wipe-request-status-1.png)

Ponadto można wyświetlić nazwę i typ urządzenia, co może być przydatne podczas odczytywania raportów.

>[!IMPORTANT]
> Użytkownicy muszą otworzyć aplikację w celu przeprowadzenia czyszczenia — może ono zająć do 30 minut od czasu utworzenia żądania.

## <a name="delete-a-wipe-request"></a>Usuwanie żądania czyszczenia

Czyszczenia ze stanem oczekującym są wyświetlane do czasu ich ręcznego usunięcia. Aby ręcznie usunąć żądanie czyszczenia:

1. W okienku **Aplikacje klienckie — Selektywne czyszczenie aplikacji**.

2. Na liście kliknij prawym przyciskiem myszy żądanie czyszczenia do usunięcia, a następnie wybierz pozycję **Usuń żądanie czyszczenia**.

    ![Zrzut ekranu przedstawiający listę żądań czyszczenia w okienku Selektywne czyszczenie aplikacji](./media/apps-selective-wipe/delete-wipe-request.png)

3. Zostanie wyświetlony monit o potwierdzenie usunięcia. Wybierz przycisk **Tak** lub **Nie**, następnie kliknij przycisk **OK**.

## <a name="see-also"></a>Zobacz także
[What's app protection policy](app-protection-policy.md) (Co to są zasady ochrony aplikacji)

[What's app management](app-management.md) (Co to jest zarządzanie aplikacjami)
