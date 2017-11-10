---
title: "Dodawanie zasad konfiguracji aplikacji dla zarządzanych urządzeń z systemem Android | Microsoft Docs"
titlesuffix: Azure portal
description: "Informacje dotyczące korzystania z zasad konfiguracji aplikacji w celu przekazywania danych konfiguracyjnych do aplikacji Android for Work po jej uruchomieniu."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e56aff30b353a2c98eb7effbec3e02bde066804f
ms.sourcegitcommit: 67c037af31c1f167ec9b4f4baa754631c817e7d1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2017
---
# <a name="add-app-configuration-policies-for-managed-android-devices"></a>Dodawanie zasad konfiguracji aplikacji dla zarządzanych urządzeń z systemem Android

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Zasady konfiguracji aplikacji w usłudze Microsoft Intune umożliwiają określanie ustawień podczas uruchamiania aplikacji Android for Work przez użytkowników. Tych zasad nie można przypisywać bezpośrednio do użytkowników i urządzeń. W zamian należy skojarzyć je z aplikacją, a następnie przypisać tę aplikację. Ustawienia zasad są stosowane, gdy aplikacja je wyszukuje (zazwyczaj podczas pierwszego uruchomienia).

> [!Note]  
> Nie wszystkie aplikacje obsługują konfigurację aplikacji. Skontaktuj się z deweloperem aplikacji, aby dowiedzieć się, czy jego aplikacja obsługuje zasady konfiguracji aplikacji.

1. Zaloguj się do witryny Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** + **Intune**.
3. Wybierz obciążenie **Aplikacje mobilne**.
4. Kliknij pozycję **Zasady konfiguracji aplikacji** w grupie **Zarządzaj**, a następnie kliknij przycisk **Dodaj**.
5. Ustaw następujące szczegóły:
    - **Nazwa**  
      — nazwa profilu, która będzie wyświetlana w witrynie Azure Portal
    - **Opis**  
      — opis profilu, który będzie wyświetlany w witrynie Azure Portal
    - **Typ rejestracji urządzenia**  
      Wybierz pozycję **Urządzenia zarządzane**.
6. Dla opcji **Platforma** wybierz pozycję **Android**.
7. Wybierz pozycję **Skojarzona aplikacja**, aby wybrać aplikację, dla której chcesz zdefiniować zasady konfiguracji.  Wybierz z listy programu Android for Work aplikacje zatwierdzone i zsynchronizowane z usługą Intune.
8. Wybierz pozycję **Ustawienia konfiguracji**. Konfigurację możesz ustawić przy użyciu następujących narzędzi:
    - [Projektant konfiguracji](#Use-the-configuration-designer)
    - [Edytor JSON](#Use-the-JSON-editor)
9. Kliknij przycisk **OK**, a następnie pozycję **Dodaj**.

## <a name="use-the-configuration-designer"></a>Korzystanie z projektanta konfiguracji

Projektanta konfiguracji można używać w przypadku aplikacji na urządzeniach zarejestrowanych lub niezarejestrowanych w usłudze Intune. Projektant umożliwia skonfigurowanie określonych kluczy i wartości konfiguracji. Dla każdej wartości należy również wskazać typ danych.

Dla każdego klucza i wartości konfiguracji ustaw następujące elementy:

  - **Klucz konfiguracji**  
     Służy do jednoznacznego zidentyfikowania konfiguracji określonego ustawienia.
  - **Typ wartości**  
    Typ danych wartości konfiguracji. Typy obejmują liczby całkowite, liczby rzeczywiste, ciągi i wartości logiczne.
  - **Wartość konfiguracji**  
    Wartość konfiguracji. 

## <a name="enter-the-json-editor"></a>Edytor JSON

Nie jest możliwa konfiguracja niektórych ustawień konfiguracji aplikacji (np. typów pakietu) przy użyciu projektanta konfiguracji.  W przypadku tych wartości niezbędne jest użycie edytora JSON. Ustawienia są dostarczane do aplikacji automatycznie po zainstalowaniu aplikacji.

1. Dla opcji **Format ustawień konfiguracji** wybierz opcję **Edytor JSON**.
2. W edytorze można zdefiniować wartości JSON dla ustawień konfiguracji. Możesz wybrać pozycję **Pobierz szablon JSON**, aby pobrać przykładowy plik, który można następnie skonfigurować.
3. Po wprowadzeniu niezbędnych zmian wybierz pozycję **OK**, a następnie kliknij przycisk **Dodaj**.

Zasady zostaną utworzone i wyświetlone w bloku listy zasad.

Po uruchomieniu przypisanej aplikacji na urządzeniu uruchamiane są ustawienia skonfigurowane w zasadach konfiguracji aplikacji.

## <a name="preconfigure-permissions-grant-state-for-apps"></a>Wstępna konfiguracja stanu uprawnień dla aplikacji

Możesz również wstępnie skonfigurować uprawnienia dla aplikacji pod kątem dostępu do funkcji urządzenia z systemem Android. Domyślnie aplikacje systemu Android, które wymagają uprawnień urządzenia, takich jak dostęp do lokalizacji lub aparatu urządzenia, wyświetlają monit o zaakceptowanie lub odrzucenie uprawnień przez użytkownika. Na przykład jeśli aplikacja używa mikrofonu urządzenia, użytkownik końcowy otrzyma monit o przyznanie aplikacji uprawnienia do użycia mikrofonu.

1. Zaloguj się do witryny Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** + **Intune**.
3. Wybierz pozycję **Mobile Apps**. W obszarze **Zarządzaj** wybierz pozycję Zasady konfiguracji aplikacji, a następnie kliknij przycisk **Dodaj**.
4. Ustaw następujące szczegóły:
    - **Nazwa** — nazwa profilu, która będzie wyświetlana w witrynie Azure Portal
    - **Opis** — opis profilu, który będzie wyświetlany w witrynie Azure Portal
    - **Platforma** — wybierz opcję **Android**
    - **Typ rejestracji urządzenia** -  wstępnie wybrana wartość to *Urządzenia zarządzane**.
5. Wybierz pozycję **Skojarzona aplikacja**, aby wybrać aplikację, dla której chcesz zdefiniować zasady konfiguracji.  Wybierz z listy programu Android for Work aplikacje zatwierdzone i zsynchronizowane z usługą Intune.
6. Wybierz **Uprawnienia**, a następnie wybierz **Dodaj**.
7. Wybierz odpowiednie opcje z listy dostępnych uprawnień aplikacji, a następnie wybierz pozycję **OK**.
8. Wybierz opcję dla każdego uprawnienia, które ma zostać przyznane zgodnie z tymi zasadami:
    - **Monit** — wyświetlenie monitu o zaakceptowanie lub odrzucenie przez użytkownika.
    - **Automatyczne udzielaj** — automatyczne zatwierdzenie bez powiadomienia użytkownika.
    - **Automatyczne odmawiaj** — automatyczna odmowa bez powiadomienia użytkownika.
9. Aby przypisać zasady konfiguracji aplikacji, wybierz zasady konfiguracji aplikacji, wybierz pozycję **Przypisania**, a następnie wybierz pozycję **Wybierz grupy**.
10. Wybierz grupy użytkowników do przypisania, a następnie wybierz pozycję **Wybierz**.
11. Wybierz pozycję **Zapisz**, aby przypisać zasady.

## <a name="next-steps"></a>Następne kroki

Kontynuuj [przypisywanie](apps-deploy.md) i [monitorowanie](apps-monitor.md) aplikacji.

