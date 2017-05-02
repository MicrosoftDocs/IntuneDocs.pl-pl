---
title: "Zarządzanie urządzeniami w usłudze Intune"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: dowiedz się, jak wyświetlać urządzenia zarządzane za pomocą usługi Intune i wykonywać na nich różne operacje."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/13/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: 25a46754f6c7e44b3f4fef7e8eef015cf559e31f
ms.lasthandoff: 04/19/2017


---

# <a name="what-is-microsoft-intune-device-management"></a>Co to jest zarządzanie urządzeniami w usłudze Microsoft Intune?


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Obciążenie **Urządzenia** zapewnia wgląd w urządzenia zarządzane i umożliwia wykonywanie zadań zdalnych na tych urządzeniach. Aby uzyskać dostęp do obciążenia:

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Urządzenia**.

Wybierz jedną z następujących opcji:

- **Przegląd** Pobranie informacji o zarejestrowanych urządzeniach i systemach operacyjnych działających na każdym z nich.
- **Zarządzanie** — opcja **Wszystkie urządzenia** umożliwia wyświetlenie listy wszystkich zarządzanych urządzeń.
    Wybierz jedno z urządzeń na liście, aby otworzyć blok <*nazwa urządzenia*> **Przegląd**, w którym można wybrać jedną z opcji:
    - **Przegląd** — zobacz ogólne informacje dotyczące urządzenia, w tym informacje o jego nazwie, właścicielu, czy jest to urządzenie BYOD, kiedy ostatnio zostało zewidencjonowane itd.

    - **Sprzęt** — wyświetlenie szczegółowych informacji dotyczących urządzenia, w tym ilości wolnego miejsca, modelu i producenta oraz innych danych.
    ![Spis sprzętu zarządzanego urządzenia](./media/hardware-inventory.png)
    - **Wykryte aplikacje** — wyświetla listę wszystkich aplikacji, które zostały odnalezione na urządzeniu przez usługę Intune.
    ![Węzeł Wykryte aplikacje](./media/detected-applications.png)
- **Monitoruj** Wybranie opcji **Akcje urządzenia** umożliwia wyświetlenie listy akcji urządzenia, które mogły zostać wykonane na urządzeniach zarządzanych, oraz bieżącego stanu tych akcji.
![Monitoruj akcje urządzenia](./media/monitor-device-actions.png)
- **Pomoc i obsługa techniczna** — wyświetla linki do dokumentacji rozwiązywania problemów i pomocy technicznej.

## <a name="available-device-actions"></a>Dostępne akcje urządzenia

Ponadto można wykonać następujące akcje zdalne na urządzeniu (nie wszystkie akcje są obsługiwane przez wszystkie platformy urządzeń):

### <a name="remove-company-data"></a>**Usuń dane firmy**
Usuwa tylko dane firmy zarządzane przez usługę Intune. Nie usuwa z urządzenia danych osobistych. Urządzenie nie będzie już zarządzane przez usługę Intune i nie będzie mogło uzyskać dostępu do zasobów firmy (nieobsługiwane w przypadku urządzeń z systemem Windows, które są połączone z usługą Azure Active Directory).

### <a name="factory-reset"></a>**Resetuj do ustawień fabrycznych**
Przywraca na urządzeniu ustawienia domyślne. Urządzenie nie będzie już zarządzane przez usługę Intune i zarówno dane firmy, jak i dane osobiste są usuwane. Nie można cofnąć tej akcji.

### <a name="remote-lock"></a>**Zdalne blokowanie**
Blokuje urządzenie. W celu odblokowania urządzenia jego właściciel musi użyć swojego kodu dostępu. Można zdalnie zablokować tylko urządzenie, które ma ustawiony numer PIN lub hasło.

### <a name="reset-passcode"></a>**Zresetuj kod dostępu**
Generuje dla urządzenia nowy kod dostępu, który zostanie wyświetlony w bloku <*nazwa urządzenia*>  **— Przegląd**.

### <a name="bypass-activation-lock"></a>**Zastosowanie obejścia blokady aktywacji**
Powoduje usunięcie blokady aktywacji z urządzenia z systemem iOS bez identyfikatora Apple ID i hasła użytkownika. Po zastosowaniu obejścia blokady aktywacji urządzenie ponownie przejdzie w stan blokady aktywacji, gdy zostanie uruchomiona aplikacja Znajdź mój iPhone. Stosuj obejście blokady aktywacji tylko w sytuacji, gdy masz fizyczny dostęp do urządzenia.

### <a name="fresh-start"></a>**Rozpoczęcie od nowa**

Usuwa wszystkie aplikacje, które zostały zainstalowane na komputerze z systemem Windows 10 z aktualizacją dla twórców, a następnie automatycznie aktualizuje komputer do najnowszej wersji systemu Windows.
Funkcja może być przydatna do usuwania wstępnie zainstalowanych aplikacji OEM, które są często dostarczane z nowymi komputerami. Możesz zdecydować, czy dane użytkownika zostaną zachowane w przypadku wykonania tej akcji dla urządzenia. W takim przypadku aplikacje i ustawienia są usuwane, ale zawartość folderów macierzystych zostaje zachowana.


### <a name="lost-mode"></a>**Tryb utraty**
W przypadku zgubienia lub kradzieży urządzenia z systemem iOS można włączyć tryb utraty. Dzięki niemu można określić komunikat i numer telefonu do wyświetlenia na ekranie blokady urządzenia. Wykonaj następujące czynności:
1.    W bloku właściwości urządzenia z systemem iOS wybierz kolejno opcje **Więcej** > **Tryb utraty**.
2.    W bloku **Tryb utraty** włącz tryb utraty, wprowadź komunikat, który będzie wyświetlany, i opcjonalnie podaj numer telefonu kontaktowego.
3.    Kliknij przycisk **OK**.
Po włączeniu trybu utraty wszystkie sposoby korzystania z urządzenia zostaną zablokowane. Użytkownik końcowy nie może uzyskać dostępu do urządzenia aż do momentu wyłączenia przez Ciebie trybu utraty. Przy włączonym trybie utraty można skorzystać z akcji **Zlokalizuj urządzenie**, aby dowiedzieć się, gdzie znajduje się urządzenie.
Aby skorzystać z trybu utraty, urządzenie musi być urządzeniem z systemem iOS,należącym do firmy, zarejestrowanym w usłudze DEP i objętym trybem nadzorowanym.

### <a name="locate-device"></a>**Zlokalizuj urządzenie**
Ta zdalna akcja umożliwia wyświetlenie na mapie lokalizacji zgubionego lub skradzionego urządzenia z systemem iOS. Urządzenie musi być urządzeniem z systemem iOS, należącym do firmy, zarejestrowanym w usłudze DEP i objętym trybem nadzorowanym. Przed użyciem tej akcji urządzenie musi znajdować się w trybie utraty.
1.    W bloku właściwości urządzenia z systemem iOS wybierz kolejno opcje **Więcej** > **Zlokalizuj urządzenie**.
2.    Po zlokalizowaniu urządzenia jego lokalizacja jest wyświetlana w bloku **Zlokalizuj urządzenie**.
    Blok ![Zlokalizuj urządzenie](./media/locate-device.png)

>[!NOTE]
>W celu zachowania prywatności stopień powiększenia mapy jest ograniczony.

### <a name="restart"></a>**Uruchom ponownie**
Powoduje ponowne uruchomienie urządzenia. Właściciel urządzenia nie jest automatycznie powiadamiany o ponownym uruchomieniu, dlatego ta akcja może doprowadzić do utraty wykonanej pracy.


## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Informacje o zabezpieczeniach i prywatności w trybie utraty oraz akcjach lokalizowania urządzenia
- Do momentu włączenia tej akcji informacje o lokalizacji urządzenia nie są wysyłane do usługi Intune.
- Po włączeniu akcji lokalizacji urządzenia współrzędne geograficzne urządzenia są wysyłane do usługi Intune i wyświetlane w portalu Azure.
- Dane są przechowywane przez 24 godziny, a następnie usuwane. Nie można ręcznie usunąć danych lokalizacji.
- Dane lokalizacji są szyfrowane zarówno podczas przechowywania, jak i podczas przesyłania.
- Zalecamy, aby wprowadzony podczas konfigurowania trybu utraty komunikat, który będzie wyświetlany na ekranie blokady, zawierał informacje o możliwości określenia lokalizacji urządzenia.

