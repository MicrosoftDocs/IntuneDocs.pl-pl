---
title: "Korzystanie z zasad konfiguracji aplikacji usługi Intune w odniesieniu do programu Android for Work"
titlesuffix: Azure portal
description: "Informacje dotyczące korzystania z zasad konfiguracji aplikacji w celu przekazywania danych konfiguracyjnych do aplikacji Android for Work po jej uruchomieniu."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4b73202a1a68bd2dd3dcbfa86c21cb09ae00056c
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-use-microsoft-intune-app-configuration-policies-for-android-for-work"></a>Jak używać zasad konfiguracji aplikacji usługi Microsoft Intune w odniesieniu do programu Android for Work

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Zasady konfiguracji aplikacji w usłudze Microsoft Intune umożliwiają określanie wartości ustawień, które mogą być dostępne, jeśli użytkownicy uruchamiają aplikację Android for Work. Nie wszystkie aplikacje obsługują konfigurację aplikacji. Skontaktuj się z deweloperem aplikacji, aby dowiedzieć się, czy jego aplikacja obsługuje zasady konfiguracji aplikacji.

Zasady konfiguracji aplikacji pozwalają na wstępne skonfigurowanie dostępnych ustawień aplikacji przed jej uruchomieniem przez użytkowników. Niektóre aplikacje dla systemu Android obsługują opcje konfiguracji zarządzanych, które można skonfigurować w witrynie Azure Portal z użyciem [projektanta konfiguracji](#use-configuration-designer). Nie jest możliwa konfiguracja niektórych ustawień konfiguracji aplikacji (np. typów pakietu) przy użyciu projektanta konfiguracji.  W przypadku tych wartości niezbędne jest użycie [edytora JSON](#use-json-editor).   Ustawienia są dostarczane do aplikacji automatycznie po zainstalowaniu aplikacji.

Tych zasad nie można przypisywać bezpośrednio do użytkowników i urządzeń. W zamian należy skojarzyć je z aplikacją, a następnie przypisać tę aplikację. Ustawienia zasad są stosowane, gdy aplikacja je wyszukuje (zazwyczaj podczas pierwszego uruchomienia).

## <a name="use-configuration-designer"></a>Korzystanie z projektanta konfiguracji

1. W witrynie Azure Portal wybierz pozycję **Aplikacje mobilne**. W obszarze **Zarządzaj** wybierz pozycję **Zasady konfiguracji aplikacji**, a następnie kliknij przycisk **Dodaj**.
2. Ustaw następujące szczegóły:
    - **Nazwa** — nazwa profilu, która będzie wyświetlana w witrynie Azure Portal
    - **Opis** — opis profilu, który będzie wyświetlany w witrynie Azure Portal
    - **Platforma** — wybierz opcję **Android**
    - **Typ rejestracji urządzenia** -  wstępnie wybrana wartość to **Zarejestrowane w usłudze Intune**.
3. Wybierz pozycję **Skojarzona aplikacja**, aby wybrać aplikację, dla której chcesz zdefiniować zasady konfiguracji.  Wybierz z listy programu Android for Work aplikacje zatwierdzone i zsynchronizowane z usługą Intune
4. Wybierz pozycję **Ustawienia konfiguracji**.
5. Dla opcji **Format ustawień konfiguracji** wybierz pozycję **Użyj projektanta konfiguracji**.
6. Wybierz pozycję **Dodaj**. Zostanie wyświetlona lista dostępnych ustawień konfiguracji. Lista zawiera następujące pozycje:
    - **Klucze konfiguracji** — nazwa ustawienia.
    - **Typ wartości** — ustawienie, które może zostać skonfigurowane, na przykład **Wartość logiczna** lub **Ciąg**.
    - **Opis** — opis ustawienia konfiguracji.
7. Zaznacz pola wyboru obok ustawień, które chcesz skonfigurować w ramach tego profilu, a następnie kliknij przycisk **OK**.
8. Zostanie wyświetlona lista wybranych ustawień oraz dostępna **Wartość konfiguracji**. Określ wartość dla każdego ustawienia, a następnie kliknij przycisk **OK**.

## <a name="use-json-editor"></a>Korzystanie z edytora JSON

1. W witrynie Azure Portal wybierz pozycję **Aplikacje mobilne**. W obszarze **Zarządzaj** wybierz pozycję **Zasady konfiguracji aplikacji**, a następnie kliknij przycisk **Dodaj**.
2. Ustaw następujące szczegóły:
    - **Nazwa** — nazwa profilu, która będzie wyświetlana w witrynie Azure Portal
    - **Opis** — opis profilu, który będzie wyświetlany w witrynie Azure Portal
    - **Platforma** — wybierz opcję **Android**
    - **Typ rejestracji urządzenia** -  wstępnie wybrana wartość to **Zarejestrowane w usłudze Intune**.
3. Wybierz pozycję **Skojarzona aplikacja**, aby wybrać aplikację, dla której chcesz zdefiniować zasady konfiguracji.  Wybierz z listy programu Android for Work aplikacje zatwierdzone i zsynchronizowane z usługą Intune.
5. Wybierz pozycję **Ustawienia konfiguracji**.
6. Dla opcji **Format ustawień konfiguracji** wybierz opcję **Edytor JSON**.
7. W edytorze można zdefiniować wartości JSON dla ustawień konfiguracji. Możesz wybrać pozycję **Pobierz szablon JSON**, aby pobrać przykładowy plik, który można następnie skonfigurować.
8. Po wprowadzeniu niezbędnych zmian wybierz pozycję **OK**, a następnie kliknij przycisk **Dodaj**.

Zasady zostaną utworzone i wyświetlone w bloku listy zasad.



Po uruchomieniu przypisanej aplikacji na urządzeniu zostaną uruchomione ustawienia skonfigurowane w zasadach konfiguracji aplikacji.

## <a name="preconfigure-permissions-grant-state-for-apps"></a>Wstępna konfiguracja stanu uprawnień dla aplikacji

Możesz również wstępnie skonfigurować uprawnienia dla aplikacji pod kątem dostępu do funkcji urządzenia z systemem Android. Domyślnie aplikacje systemu Android, które wymagają uprawnień urządzenia, takich jak dostęp do lokalizacji lub aparatu urządzenia, wyświetlają monit o zaakceptowanie lub odrzucenie uprawnień przez użytkownika. Na przykład jeśli aplikacja używa mikrofonu urządzenia, użytkownik końcowy otrzyma monit o przyznanie aplikacji uprawnienia do użycia mikrofonu.

1. W witrynie Azure Portal wybierz pozycję **Aplikacje mobilne**. W obszarze **Zarządzaj** wybierz pozycję **Zasady konfiguracji aplikacji**, a następnie kliknij przycisk **Dodaj**.
2. Ustaw następujące szczegóły:
    - **Nazwa** — nazwa profilu, która będzie wyświetlana w witrynie Azure Portal
    - **Opis** — opis profilu, który będzie wyświetlany w witrynie Azure Portal
    - **Platforma** — wybierz opcję **Android**
    - **Typ rejestracji urządzenia** -  wstępnie wybrana wartość to **Zarejestrowane w usłudze Intune**.
3. Wybierz pozycję **Skojarzona aplikacja**, aby wybrać aplikację, dla której chcesz zdefiniować zasady konfiguracji.  Wybierz z listy programu Android for Work aplikacje zatwierdzone i zsynchronizowane z usługą Intune.
5. Wybierz **Uprawnienia**, a następnie wybierz **Dodaj**.
6. Wybierz odpowiednie opcje z listy dostępnych uprawnień aplikacji, a następnie wybierz pozycję **OK**.
7. Wybierz opcję dla każdego uprawnienia, które ma zostać przyznane zgodnie z tymi zasadami:
    - **Monit** — wyświetlenie monitu o zaakceptowanie lub odrzucenie przez użytkownika.
    - **Automatyczne udzielaj** — automatyczne zatwierdzenie bez powiadomienia użytkownika.
    - **Automatyczne odmawiaj** — automatyczna odmowa bez powiadomienia użytkownika.
8. Aby przypisać zasady konfiguracji aplikacji, wybierz zasady konfiguracji aplikacji, wybierz pozycję **Przypisania**, a następnie wybierz pozycję **Wybierz grupy**.
9. Wybierz grupy użytkowników do przypisania, a następnie wybierz pozycję **Wybierz**.
10. Wybierz pozycję **Zapisz**, aby przypisać zasady.

## <a name="next-steps"></a>Następne kroki

Kontynuuj [przypisywanie](apps-deploy.md) i [monitorowanie](apps-monitor.md) aplikacji tak jak dotychczas.

