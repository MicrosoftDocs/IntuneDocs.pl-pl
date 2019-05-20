---
title: Sprawdzanie powodzenia lub niepowodzenia punktów odniesienia zabezpieczeń w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Sprawdzaj stan błędów, konfliktów i powodzenia podczas wdrażania punktów odniesienia zabezpieczeń dla użytkowników i urządzeń w oprogramowaniu MDM w usłudze Microsoft Intune. Zobacz, jak rozwiązywać problemy przy użyciu dzienników klienta i funkcji raportowania w usłudze Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/19/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a013698e56b342953e52296270e7571a257db860
ms.sourcegitcommit: dde4b8788e96563edeab63f612347fa222d8ced0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/06/2019
ms.locfileid: "65135094"
---
# <a name="monitor-security-baseline-and-profiles-in-microsoft-intune"></a>Monitorowanie profilów i punktu odniesienia zabezpieczeń w usłudze Microsoft Intune  

Usługa Intune oferuje kilka opcji monitorowania punktów odniesienia zabezpieczeń. Można monitorować profil punktu odniesienia zabezpieczeń, który ma zastosowanie do użytkowników i urządzeń. Można również monitorować rzeczywisty punkt odniesienia i wszystkie urządzenia, które są zgodne (lub nie) z zalecanymi wartościami.

W tym artykule przedstawiono szczegóły obydwu opcji monitorowania.

Więcej szczegółów funkcji punktów odniesienia zabezpieczeń w usłudze Microsoft Intune można znaleźć w temacie [Security baselines in Intune](security-baselines.md) (Punkty odniesienia zabezpieczeń w usłudze Intune).

## <a name="monitor-the-baseline-and-your-devices"></a>Monitorowanie punktów odniesienia i urządzeń  

W przypadku monitorowania punktu odniesienia uzyskujesz szczegółowe informacje na temat stanu zabezpieczeń urządzeń na podstawie rekomendacji firmy Microsoft. Możesz wyświetlić te szczegółowe informacje w okienku Przegląd punktu odniesienia zabezpieczeń w konsoli usługi Intune.  Wyświetlenie danych po pierwszym przypisaniu punktu odniesienia może potrwać do 24 godzin. Późniejsze zmiany pojawiają się w ciągu sześciu godzin.  

Aby wyświetlić dane monitorowania dotyczące punktu odniesienia i urządzeń, zaloguj się do [portalu usługi Intune](https://go.microsoft.com/fwlink/?linkid=2090973). Następnie wybierz pozycję **Zabezpieczenia urządzenia** > **Punkty odniesienia zabezpieczeń (wersja zapoznawcza)**, wybierz punkt odniesienia i wyświetl okienko **Przegląd**.

Okienko **Przegląd** udostępnia dwie metody monitorowania stanu:
- **Widok urządzenia** — podsumowanie liczby urządzeń znajdujących się w każdej kategorii stanu dla punktu odniesienia.  
- **Według kategorii** — widok poszczególnych kategorii w punkcie odniesienia. Zawiera wartość procentową liczby urządzeń dla każdej grupy stanu dla poszczególnych kategorii punktu odniesienia. 

Każde urządzenie jest reprezentowane przez jeden z następujących stanów. Są one używane zarówno w widoku *urządzenia*, jak i w widoku *według kategorii*:  
- **Zgodne z punktem odniesienia** — wszystkie ustawienia w punkcie odniesienia są zgodne z zalecanymi ustawieniami.
- **Niezgodne z punktem odniesienia** — co najmniej jedno ustawienie w punkcie odniesienia jest niezgodne z zalecanymi ustawieniami.
- **Błędna konfiguracja** — co najmniej jedno ustawienie nie zostało prawidłowo skonfigurowane. Ten stan oznacza, że ustawienie znajduje się w stanie konfliktu, błędu lub oczekiwania.
- **Nie dotyczy** — co najmniej jedno ustawienie nie ma zastosowania i nie jest stosowane.


### <a name="device-view"></a>Widok urządzenia
W okienku Przegląd jest wyświetlane podsumowanie w postaci wykresu. Widać na nim, ile urządzeń ma konkretny stan względem punktu odniesienia — **Stan punktu odniesienia zabezpieczeń dla przypisanych urządzeń z systemem Windows 10**.  

![Sprawdzanie stanu urządzeń](./media/security-baselines-monitor/overview.png)

Jeśli urządzenie ma inny stan niż w pozostałych kategoriach punktu odniesienia, to urządzenie jest reprezentowane przez pojedynczy stan. Stan, który reprezentuje urządzenie, jest pobierany w następującej kolejności: **Błędna konfiguracja**, **Niezgodne z punktem odniesienia**, **Nie dotyczy**, **Zgodne z punktem odniesienia**.  

Jeśli na przykład urządzenie ma ustawienie sklasyfikowane jako *Błędna konfiguracja* i co najmniej jedno ustawienie sklasyfikowane jako *Niezgodne z punktem odniesienia*, urządzenie zostanie sklasyfikowane jako *Błędna konfiguracja*.  

Jeśli klikniesz wykres, możesz przeglądać szczegóły i wyświetlać listę urządzeń mających różne stany. Kliknięcie konkretnego urządzenia na tej liście powoduje wyświetlenie szczegółowych informacji o tym urządzeniu. Przykład:
- Wybierz pozycję **Konfiguracja urządzenia**, a następnie wybierz profil ze stanem błędu:

  ![Sprawdzanie stanu urządzeń](./media/security-baselines-monitor/device-configuration-profile-list.png)

- Wybierz profil ze stanem Błąd. Zostanie wyświetlona lista wszystkich ustawień w profilu oraz ich stan. Teraz możesz przewinąć, aby znaleźć ustawienie powodujące błąd:

  ![Wyświetlanie ustawienia powodującego błąd](./media/security-baselines-monitor/profile-with-error-status.png)

Ta funkcja raportowania umożliwia wyświetlanie wszystkich ustawień w profilu, które są przyczyną problemu. Można również uzyskać więcej szczegółów dotyczących zasad i profilów wdrażanych na urządzeniach.

> [!NOTE]
> Jeśli właściwość zostanie ustawiona na **Nieskonfigurowane** w punkcie odniesienia, ustawienie zostanie ignorowane, a żadne ograniczenia nie będą wymuszane. Właściwość nie jest wyświetlana w raportach.

### <a name="per-category-view"></a>Widok według kategorii
W okienku Przegląd jest wyświetlany wykres według kategorii względem punktu odniesienia — **Stan punktu odniesienia zabezpieczeń według kategorii**.  W tym widoku są wyświetlane poszczególne kategorie punktów odniesienia oraz przedstawiony jest odsetek urządzeń mających odpowiedni stan klasyfikacji w każdej z tych kategorii. 
 
![Widok stanu według kategorii](./media/security-baselines-monitor/monitor-baseline-per-category.png)

Stan **Zgodne z punktem odniesienia** nie jest wyświetlany do momentu, aż 100% urządzeń zgłosi ten stan w kategorii.   

Widok według kategorii można sortować względem każdej kolumny, wybierając ikonę strzałki w górę i w dół w górnej części kolumny.  


## <a name="monitor-the-profile"></a>Monitorowanie profilu

Monitorowanie profilu umożliwia uzyskiwanie szczegółowych informacji na temat stanu wdrożenia urządzeń, ale nie stanu zabezpieczeń w oparciu o rekomendacje.

1. W usłudze Intune wybierz pozycję **Punkty odniesienia zabezpieczeń** > wybierz punkt odniesienia > **Utworzone profile**.

2. Wybierz profil. Obraz w obszarze **omówienia** pokazuje, do ilu urządzeń i użytkowników przypisano ten profil:

    ![Wyświetlanie liczby urządzeń i użytkowników z przypisanym profilem punktów odniesienia zabezpieczeń](./media/security-baselines-monitor/existing-profile-overview.png)

3. W obszarze **Zarządzaj** > **Właściwości** jest wyświetlana lista wszystkich ustawień w danym punkcie odniesienia. Możesz również zmienić dowolne z poniższych ustawień:

    ![Wyświetlanie i aktualizowanie ustawień w profilu punktów odniesienia zabezpieczeń](./media/security-baselines-monitor/manage-settings.png)

4. W obszarze **Monitor** możesz wyświetlić stan wdrożenia profilu na poszczególnych urządzeniach, stan dla każdego użytkownika i stan dla każdego ustawienia w punkcie odniesienia:

    ![Wyświetlanie różnych opcji monitorowania dla profilu punktów odniesienia zabezpieczeń](./media/security-baselines-monitor/monitor-status-options.png)

## <a name="troubleshoot-using-per-setting-status"></a>Rozwiązywanie problemów przy użyciu stanu poszczególnych ustawień

Wdrożono punkt odniesienia zabezpieczeń, ale stan wdrożenia wskazuje błąd. Poniższe kroki oferują wskazówki na temat rozwiązywania problemu powodującego błąd.

1. W usłudze Intune wybierz pozycję **Punkty odniesienia zabezpieczeń** > wybierz punkt odniesienia > **Utworzone profile**.
2. Wybierz profil > w obszarze **Monitor** > **Stan na ustawienie**.
3. W tabeli przedstawiono wszystkie ustawienia i stan każdego z nich. Wybierz kolumnę **Błąd** lub kolumnę **Konflikt**, aby wyświetlić ustawienie powoduje błąd.

### <a name="mdm-diagnostic-information"></a>Informacje diagnostyczne oprogramowania MDM

Teraz już wiesz, które ustawienie powoduje problem. W następnym kroku dowiesz się, dlaczego to ustawienie powoduje błąd lub konflikt. 

Na urządzeniach z systemem Windows 10 istnieje wbudowany raport zawierający informacje diagnostyczne oprogramowania MDM. Raport ten zawiera wartości domyślne, wartości bieżące, listę zasad, informacje na temat wdrożenia do urządzenia i użytkownika oraz inne dane. Użyj tego raportu, aby łatwiej określić, dlaczego ustawienie powoduje konflikt lub błąd.

1. Na urządzeniu przejdź kolejno do pozycji **Ustawienia** > **Konta** > **Uzyskaj dostęp do miejsca pracy lub nauki**.
2. Wybierz konto > **Informacje** > **Zaawansowany raport diagnostyczny** > **Utwórz raport**.
3. Wybierz pozycję **Eksportuj**, a następnie otwórz wygenerowany plik.
4. W różnych sekcjach raportu wyszukaj ustawienie powodujące błąd lub konflikt.

  Na przykład wyszukaj je w sekcji **Zarejestrowane źródła konfiguracji i zasoby docelowe** lub **Zasady niezarządzane**. W ten sposób możesz odkryć, dlaczego ustawienie powoduje błąd lub konflikt.

Artykuł [Diagnose MDM failures in Windows 10](https://docs.microsoft.com/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10) (Diagnozowanie błędów oprogramowania MDM w systemie Windows 10) zawiera dalsze informacje na tego wbudowanego raportu.

> [!TIP]
> - Niektóre ustawienia na liście zawierają również identyfikator GUID. Możesz wyszukać ten identyfikator GUID w rejestrze lokalnym (regedit) dla każdej ustawionej wartości.
> - Dzienniki Podglądu zdarzeń mogą zawierać informacje o błędach problematycznego ustawienia (**Podgląd zdarzeń** > **Dzienniki aplikacji i usług** > **Microsoft** > **Windows** > **DeviceManagement-Enterprise-Diagnostics-Provider** > **Administrator**).

## <a name="next-steps"></a>Następne kroki

[Monitoruj profile urządzeń](device-profile-monitor.md) oraz [zapoznaj się z niektórymi typowymi problemami i rozwiązaniami](device-profile-troubleshoot.md).
