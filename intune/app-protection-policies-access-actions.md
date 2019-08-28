---
title: Czyszczenie danych przy użyciu akcji uruchamiania warunkowego zasad ochrony aplikacji
titleSuffix: Microsoft Intune
description: Dowiedz się, jak selektywnie czyścić dane przy użyciu akcji uruchamiania warunkowego zasad ochrony aplikacji w usłudze Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/27/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f5ca557e-a8e1-4720-b06e-837c4f0bc3ca
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8cf55084951c3a423b79e4588f8814b5e73ce8e8
ms.sourcegitcommit: 6c74ff568267d85fd1d44fda75e3e24ead87cb2b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/28/2019
ms.locfileid: "70063016"
---
# <a name="selectively-wipe-data-using-app-protection-policy-conditional-launch-actions-in-intune"></a>Selektywne czyszczenie danych przy użyciu akcji uruchamiania warunkowego zasad ochrony aplikacji w usłudze Intune

Za pomocą zasad ochrony aplikacji usługi Intune można skonfigurować ustawienia służące do blokowania użytkownikom końcowym dostępu do aplikacji lub konta w firmie. Te ustawienia dotyczą relokacji danych i wymagań dostępu ustawianych w Twojej organizacji i mogą być na przykład związane z urządzeniami, w przypadku których wykonano jailbreak, i minimalnymi wersjami systemu operacyjnego.
 
Za pomocą tych ustawień możesz jawnie wyczyścić dane firmowe z urządzenia użytkownika końcowego w ramach akcji do wykonania w wyniku niezgodności. W przypadku niektórych ustawień możliwe będzie skonfigurowanie wielu akcji, takich jak blokowanie dostępu i czyszczenie danych na podstawie różnych określonych wartości.

## <a name="create-an-app-protection-policy-using-conditional-launch-actions"></a>Tworzenie zasad ochrony aplikacji przy użyciu akcji uruchamiania warunkowego

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. W okienku **Intune** wybierz pozycję **Aplikacje klienckie** > **Zasady ochrony aplikacji**.
4. Kliknij pozycję **Dodaj zasady**. Możesz również edytować istniejące zasady. 
5. Kliknij pozycję **Skonfiguruj wymagane ustawienia**, aby wyświetlić listę ustawień dostępnych do skonfigurowania na potrzeby zasad. 
6. Przewinięcie w dół w okienku Ustawienia spowoduje wyświetlenie sekcji o nazwie **Uruchamianie warunkowe**, w której będzie się znajdowała edytowalna tabela.

    ![Zrzut ekranu przedstawiający akcje dostępu zasad ochrony aplikacji usługi Intune](./media/apps-selective-wipe-access-actions01.png)

7. Wybierz pozycję w kolumnie **Ustawienie** i w kolumnie **Wartość** wprowadź wartość, która będzie wymagana od użytkowników, aby mogli zalogować się do aplikacji firmowej. 
8. W kolumnie **Akcja** wybierz akcję, którą chcesz wykonać, jeśli użytkownicy nie spełnili Twoich wymagań. W niektórych przypadkach dla pojedynczego ustawienia można skonfigurować wiele akcji. Aby uzyskać szczegółowe informacje, zobacz [Tworzenie i przypisywanie zasad ochrony aplikacji](app-protection-policies.md).

>[!NOTE]
> Aby użyć ustawienia **Modele urządzeń lub Producenci urządzeń**, wprowadź rozdzielaną średnikami listę identyfikatorów modeli. Unikaj spacji na listach wielu wartości. Te wartości nie uwzględniają wielkości liter. 

## <a name="policy-settings"></a>Ustawienia zasad 

Tabela ustawień zasad ochrony aplikacji zawiera kolumny **Ustawienie**, **Wartość** i **Akcja**.

### <a name="ios-policy-settings"></a>Ustawienia zasad systemu iOS
W przypadku systemu iOS za pomocą listy rozwijanej **Ustawienie** możliwe będzie skonfigurowanie akcji dla następujących ustawień:
- Maksymalna liczba prób wpisania numeru PIN
- Okres karencji w trybie offline
- Urządzenia, w przypadku których wykonano jailbreak lub zapewniono dostęp do konta root
- Minimalna wersja systemu operacyjnego
- Minimalna wersja aplikacji
- Minimalna wersja zestawu SDK
- Modele urządzeń

Aby użyć ustawienia **Modele urządzeń**, wprowadź rozdzielaną średnikami listę identyfikatorów modeli urządzeń z systemem iOS. Identyfikator modelu urządzenia z systemem iOS można znaleźć w kolumnie Typ urządzenia w [dokumentacji pomocy technicznej usługi HockeyApp](https://support.hockeyapp.net/kb/client-integration-ios-mac-os-x-tvos/ios-device-types).<br>
Przykładowe dane wejściowe: *iPhone5,2; iPhone5,3*

Na urządzeniach użytkowników końcowych klient usługi Intune wykonuje akcję w oparciu o proste dopasowywanie ciągów modelu urządzenia określonych w usłudze Intune dla zasad ochrony aplikacji. Dopasowywanie całkowicie zależy od danych zgłoszonych przez urządzenie. Zachęcamy, aby administrator IT upewnił się, że faktyczne zachowanie odpowiada zamierzonemu przez przetestowanie tego ustawienia z użyciem różnych producentów i modeli urządzeń w ramach małej grupy użytkowników. Wartość domyślna to **Nie skonfigurowano**.<br>
Ustaw jedną z następujących akcji: 
- Zezwalaj na określone (blokuj nieokreślone)
- Zezwalaj na określone (wyczyść nieokreślone)

**Co się stanie, jeśli administrator IT wprowadzi różne listy identyfikatorów modeli urządzeń z systemem iOS w zasadach przeznaczonych dla tych samych aplikacji i dla tego samego użytkownika usługi Intune?**<br>
W przypadku wystąpienia konfliktu wartości skonfigurowanych dla dwóch zasad ochrony aplikacji usługa Intune zwykle przyjmuje najbardziej restrykcyjne podejście. W związku z tym wynikowe zasady wysłane do aplikacji docelowej otwieranej przez docelowego użytkownika usługi Intune byłyby częścią wspólną identyfikatorów modeli urządzeń z systemem iOS wymienionych w *zasadach A* i *zasadach B* przeznaczonych dla tej samej kombinacji aplikacja/użytkownik. Jeśli na przykład *zasady A* określają listę „iPhone5,2; iPhone5,3”, natomiast *zasady B* określają wartość „iPhone5,3”, wynikowe zasady dotyczące użytkownika usługi Intune, dla którego mają zastosowanie zarówno *zasady A*, jak i *zasady B*, będą zawierały wartość „iPhone5,3”. 

### <a name="android-policy-settings"></a>Ustawienia zasad systemu Android

W przypadku systemu Android za pomocą listy rozwijanej **Ustawienie** możliwe będzie skonfigurowanie akcji dla następujących ustawień:
- Maksymalna liczba prób wpisania numeru PIN
- Okres karencji w trybie offline
- Urządzenia, w przypadku których wykonano jailbreak lub zapewniono dostęp do konta root
- Minimalna wersja systemu operacyjnego
- Minimalna wersja aplikacji
- Minimalna wersja poprawki
- Producenci urządzeń
- Zaświadczanie urządzeń SafetyNet
- Skanowanie aplikacji pod kątem zagrożeń

Aby użyć ustawienia **Producenci urządzeń**, wprowadź rozdzielaną średnikami listę producentów urządzeń z systemem Android. Producenta urządzenia z systemem Android można znaleźć w ustawieniach urządzenia.<br>
Przykładowe dane wejściowe: *Producent A;Producent B* 

>[!NOTE]
> Oto niektórzy popularni producenci raportowani z urządzeń używających usługi Intune. Można ich użyć jako danych wejściowych: Asus;Blackberry;Bq;Gionee;Google;Hmd global;Htc;Huawei;Infinix;Kyocera;Lemobile;Lenovo;Lge;Motorola;Oneplus;Oppo;Samsung;Sharp;Sony;Tecno;Vivo;Vodafone;Xiaomi;Zte;Zuk

Na urządzeniach użytkowników końcowych klient usługi Intune wykonuje akcję w oparciu o proste dopasowywanie ciągów modelu urządzenia określonych w usłudze Intune dla zasad ochrony aplikacji. Dopasowywanie całkowicie zależy od danych zgłoszonych przez urządzenie. Zachęcamy, aby administrator IT upewnił się, że faktyczne zachowanie odpowiada zamierzonemu przez przetestowanie tego ustawienia z użyciem różnych producentów i modeli urządzeń w ramach małej grupy użytkowników. Wartość domyślna to **Nie skonfigurowano**.<br>
Ustaw jedną z następujących akcji: 
- Zezwalaj na określone (blokuj, jeśli nieokreślone)
- Zezwalaj na określone (wyczyść, jeśli nieokreślone)

**Co się stanie, jeśli administrator IT wprowadzi różne listy producentów urządzeń z systemem Android w zasadach przeznaczonych dla tych samych aplikacji i dla tego samego użytkownika usługi Intune?**<br>
W przypadku wystąpienia konfliktu wartości skonfigurowanych dla dwóch zasad ochrony aplikacji usługa Intune zwykle przyjmuje najbardziej restrykcyjne podejście. W związku z tym wynikowe zasady wysłane do aplikacji docelowej otwieranej przez docelowego użytkownika usługi Intune byłyby częścią wspólną producentów urządzeń z systemem Android wymienionych w *zasadach A* i *zasadach B* przeznaczonych dla tej samej kombinacji aplikacja/użytkownik. Jeśli na przykład *zasady A* określają listę „Google; Samsung”, natomiast *zasady B* określają wartość „Google”, wynikowe zasady dotyczące użytkownika usługi Intune, dla którego mają zastosowanie zarówno *zasady A*, jak i *zasady B*, będą zawierały wartość „Google”. 

### <a name="additional-settings-and-actions"></a>Dodatkowe ustawienia i akcje 

Domyślnie w tabeli będą znajdowały się wypełnione wiersze jako ustawienia skonfigurowane dla wartości **Okres karencji w trybie offline** i **Maksymalna liczba prób wpisania numeru PIN**, jeśli ustawienie **Wymagaj numeru PIN w celu udzielenia dostępu** ma wartość **Tak**.
 
Aby skonfigurować ustawienie, wybierz ustawienie z listy rozwijanej w kolumnie **Ustawienie**. Po wybraniu ustawienia w tym samym wierszu w kolumnie **Wartość** zostanie włączone edytowalne pole tekstowe, jeśli wymagane jest ustawienie wartości. Zostanie również włączona lista rozwijana w kolumnie **Akcja** zawierająca zestaw warunkowo uruchamianych akcji mających zastosowanie dla danego ustawienia. 

Poniższa lista zawiera typowe akcje:
- **Zablokuj dostęp** — zablokuj użytkownikowi końcowemu dostęp do aplikacji firmowej.
- **Wyczyść dane** — wyczyść dane firmowe z urządzenia użytkownika końcowego.
- **Ostrzegaj** — wyświetl okno dialogowe użytkownikowi końcowemu jako ostrzeżenie.

W niektórych przypadkach, na przykład dla ustawienia **Minimalna wersja systemu operacyjnego**, można skonfigurować ustawienie w taki sposób, aby poszczególne odpowiednie akcje były wykonywane w zależności od numeru wersji. 

![Zrzut ekranu przedstawiający akcje dostępu ochrony aplikacji — ustawienie Minimalna wersja systemu operacyjnego](./media/apps-selective-wipe-access-actions05.png)

Gdy ustawienie zostanie w pełni skonfigurowane, wiersz będzie wyświetlany w widoku tylko do odczytu i będzie go można edytować w dowolnym momencie. Ponadto wiersz zostanie wyświetlony z listą rozwijaną w kolumnie **Ustawienie**. Ustawienia, które zostały już skonfigurowane i nie zezwalają na wykonanie wielu akcji, nie będą dostępne na liście rozwijanej.

## <a name="next-steps"></a>Następne kroki

Aby uzyskać więcej informacji na temat zasad ochrony aplikacji usługi Intune, zobacz:
- [Tworzenie i przypisywanie zasad ochrony aplikacji](app-protection-policies.md)
- [Ustawienia zasad ochrony aplikacji dla systemu iOS](app-protection-policy-settings-ios.md)
- [Ustawienia zasad ochrony aplikacji systemu Android w usłudze Microsoft Intune](app-protection-policy-settings-android.md) 
