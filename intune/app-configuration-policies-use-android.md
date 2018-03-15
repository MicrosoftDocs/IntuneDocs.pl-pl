---
title: "Dodawanie zasad konfiguracji aplikacji dla zarządzanych urządzeń z systemem Android"
titlesuffix: Microsoft Intune
description: "Zasady konfiguracji aplikacji w usłudze Microsoft Intune umożliwiają określanie ustawień podczas uruchamiania aplikacji Android for Work przez użytkowników."
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 206e229e95633ce553637bcedef708ee5630864c
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/05/2018
---
# <a name="add-app-configuration-policies-for-managed-android-devices"></a>Dodawanie zasad konfiguracji aplikacji dla zarządzanych urządzeń z systemem Android

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Zasady konfiguracji aplikacji w usłudze Microsoft Intune umożliwiają określanie ustawień podczas uruchamiania aplikacji Android for Work przez użytkowników. Tych zasad nie można przypisywać bezpośrednio do użytkowników i urządzeń. W zamian należy skojarzyć je z aplikacją, a następnie przypisać tę aplikację. Ustawienia zasad są stosowane, gdy aplikacja je wyszukuje (zazwyczaj podczas pierwszego uruchomienia).

> [!Note]  
> Nie wszystkie aplikacje obsługują konfigurację aplikacji. Skontaktuj się z deweloperem aplikacji, aby dowiedzieć się, czy jego aplikacja obsługuje zasady konfiguracji aplikacji.

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie + zarządzanie**.
3. Wybierz obciążenie **Aplikacje mobilne**.
4. Wybierz pozycję **Zasady konfiguracji aplikacji** w grupie **Zarządzaj**, a następnie wybierz przycisk **Dodaj**.
5. Ustaw następujące szczegóły:
    - **Nazwa**  
      — nazwa profilu, która będzie wyświetlana w witrynie Azure Portal
    - **Opis**  
      — opis profilu, który będzie wyświetlany w witrynie Azure Portal
    - **Typ rejestracji urządzenia**  
      Wybierz pozycję **Urządzenia zarządzane**.
6. Wybierz pozycję **Android for Work** w obszarze **Platforma**.
7. Wybierz pozycję **Skojarzona aplikacja**, aby wybrać aplikację, dla której chcesz zdefiniować zasady konfiguracji. Wybierz z listy programu Android for Work aplikacje zatwierdzone i zsynchronizowane z usługą Intune.
8. Wybierz pozycję **Ustawienia konfiguracji**. Konfigurację możesz ustawić przy użyciu następujących narzędzi:
    - [projektant konfiguracji](#Use-the-configuration-designer)
    - [edytor JSON](#Enter-the-JSON-editor)
9. Wybierz **OK**, a następnie wybierz pozycję **Dodaj**.

## <a name="use-the-configuration-designer"></a>Korzystanie z projektanta konfiguracji

Projektanta konfiguracji można używać w przypadku aplikacji na urządzeniach zarejestrowanych lub niezarejestrowanych w usłudze Intune. Projektant umożliwia skonfigurowanie określonych kluczy i wartości konfiguracji. Dla każdej wartości należy również wskazać typ danych.

Dla każdego klucza i wartości konfiguracji ustaw następujące elementy:

  - **Klucz konfiguracji**  
     Klucz, który jednoznacznie identyfikuje konfigurację określonego ustawienia.
  - **Typ wartości**  
    Typ danych wartości konfiguracji. Typy obejmują liczby całkowite, liczby rzeczywiste, ciągi i wartości logiczne.
  - **Wartość konfiguracji**  
    Wartość konfiguracji. 

## <a name="enter-the-json-editor"></a>Edytor JSON

Nie jest możliwa konfiguracja niektórych ustawień konfiguracji aplikacji (np. typów pakietu) przy użyciu projektanta konfiguracji. W przypadku tych wartości niezbędne jest użycie edytora JSON. Ustawienia są dostarczane do aplikacji automatycznie po zainstalowaniu aplikacji.

1. Dla opcji **Format ustawień konfiguracji** wybierz opcję **Edytor JSON**.
2. W edytorze można zdefiniować wartości JSON dla ustawień konfiguracji. Możesz wybrać pozycję **Pobierz szablon JSON**, aby pobrać przykładowy plik, który można następnie skonfigurować.
3. Wybierz **OK**, a następnie wybierz pozycję **Dodaj**.

Zasady zostaną utworzone i wyświetlone w bloku listy zasad.

Po uruchomieniu przypisanej aplikacji na urządzeniu uruchamiane są ustawienia skonfigurowane w zasadach konfiguracji aplikacji.

## <a name="preconfigure-the-permissions-grant-state-for-apps"></a>Wstępna konfiguracja stanu uprawnień dla aplikacji

Możesz również wstępnie skonfigurować uprawnienia dla aplikacji pod kątem dostępu do funkcji urządzenia z systemem Android. Domyślnie aplikacje systemu Android, które wymagają uprawnień urządzenia, takich jak dostęp do lokalizacji lub aparatu urządzenia, wyświetlają monit o zaakceptowanie lub odrzucenie uprawnień przez użytkownika. Na przykład jeśli aplikacja używa mikrofonu urządzenia, użytkownik otrzyma monit o przyznanie aplikacji uprawnienia do użycia mikrofonu.

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie + zarządzanie**.
3. Wybierz pozycję **Mobile Apps**.
3. W obszarze **Zarządzaj** wybierz pozycję **Zasady konfiguracji** aplikacji, a następnie wybierz pozycję **Dodaj**.
4. Ustaw następujące szczegóły:
    - **Nazwa**. — nazwa profilu, która będzie wyświetlana w witrynie Azure Portal
    - **Opis**. — opis profilu, który będzie wyświetlany w witrynie Azure Portal
    - **Typ rejestracji urządzenia**. Wybierz pozycję **Urządzenia zarządzane**.
    - **Platforma**. Wybierz pozycję **Android for Work**.
5. Wybierz pozycję **Skojarzona aplikacja**, aby wybrać aplikację, dla której chcesz zdefiniować zasady konfiguracji. Wybierz z listy programu Android for Work aplikacje zatwierdzone i zsynchronizowane z usługą Intune.
6. Wybierz **Uprawnienia**, a następnie wybierz **Dodaj**.
7. Wybierz odpowiednie opcje z listy dostępnych uprawnień aplikacji, a następnie wybierz pozycję **OK**.
8. Wybierz opcję dla każdego uprawnienia, które ma zostać przyznane zgodnie z tymi zasadami:
    - **Monituj**. Wyświetlenie monitu o zaakceptowanie lub odrzucenie przez użytkownika.
    - **Automatyczne udzielaj**. Automatyczne zatwierdzenie bez powiadamiania użytkownika.
    - **Automatyczne odmawiaj**. Automatyczna odmowa bez powiadamiania użytkownika.
9. Aby przypisać zasady konfiguracji aplikacji, wybierz zasady konfiguracji aplikacji, wybierz pozycję **Przypisania**, a następnie wybierz pozycję **Wybierz grupy**.
10. Wybierz grupy użytkowników do przypisania, a następnie wybierz pozycję **Wybierz**.
11. Wybierz pozycję **Zapisz**, aby przypisać zasady.

## <a name="next-steps"></a>Następne kroki

Kontynuuj [przypisywanie](apps-deploy.md) i [monitorowanie](apps-monitor.md) aplikacji.

