---
title: Selektywne czyszczenie danych przy użyciu akcji dostępu zasad ochrony aplikacji
titleSuffix: Microsoft Intune
description: Dowiedz się, jak selektywnie czyścić dane przy użyciu akcji dostępu zasad ochrony aplikacji w usłudze Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f5ca557e-a8e1-4720-b06e-837c4f0bc3ca
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 00f422b5619115b44b8d39c2d735f2163c22167f
ms.sourcegitcommit: dc8b6f802cca7895a19ec38bec283d4b3150d213
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/19/2018
ms.locfileid: "39138700"
---
# <a name="selectively-wipe-data-using-app-protection-policy-access-actions-in-intune"></a>Selektywne czyszczenie danych przy użyciu akcji dostępu zasad ochrony aplikacji w usłudze Intune

Za pomocą zasad ochrony aplikacji usługi Intune można skonfigurować ustawienia służące do blokowania użytkownikom końcowym dostępu do aplikacji lub konta w firmie. Te ustawienia dotyczą relokacji danych i wymagań dostępu ustawianych w Twojej organizacji i mogą być na przykład związane z urządzeniami, w przypadku których wykonano jailbreak, i minimalnymi wersjami systemu operacyjnego.
 
Za pomocą tych ustawień możesz jawnie wyczyścić dane firmowe z urządzenia użytkownika końcowego w ramach akcji do wykonania w wyniku niezgodności. W przypadku niektórych ustawień możliwe będzie skonfigurowanie wielu akcji, takich jak blokowanie dostępu i czyszczenie danych na podstawie różnych określonych wartości.

## <a name="create-an-app-protection-policy-using-access-actions"></a>Tworzenie zasad ochrony aplikacji przy użyciu akcji dostępu

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi** > **Intune**.  
    Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Aplikacje mobilne** > **Zasady ochrony aplikacji**.
4. Kliknij pozycję **Dodaj zasady**. Możesz również edytować istniejące zasady. 
5. Kliknij pozycję **Skonfiguruj wymagane ustawienia**, aby wyświetlić listę ustawień dostępnych do skonfigurowania na potrzeby zasad. 
6. Przewinięcie w dół w oknie Ustawienia spowoduje wyświetlenie sekcji o nazwie **Akcje dostępu**, w której będzie się znajdowała edytowalna tabela.

    ![Zrzut ekranu przedstawiający akcje dostępu zasad ochrony aplikacji usługi Intune](./media/apps-selective-wipe-access-actions01.png)

7. Wybierz pozycję w kolumnie **Ustawienie** i w kolumnie **Wartość** wprowadź wartość, która będzie wymagana od użytkowników, aby mogli zalogować się do aplikacji firmowej. 
8. W kolumnie **Akcja** wybierz akcję, którą chcesz wykonać, jeśli użytkownicy nie spełnili Twoich wymagań. W niektórych przypadkach dla pojedynczego ustawienia można skonfigurować wiele akcji. Aby uzyskać szczegółowe informacje, zobacz [Tworzenie i przypisywanie zasad ochrony aplikacji](app-protection-policies.md).

>[!NOTE]
> Aby użyć ustawienia **Modele urządzeń**, wprowadź rozdzielaną średnikami listę identyfikatorów modeli. 

## <a name="policy-settings"></a>Ustawienia zasad 

Tabela ustawień zasad ochrony aplikacji zawiera kolumny **Ustawienie**, **Wartość** i **Akcja**.

### <a name="ios-policy-settings"></a>Ustawienia zasad systemu iOS
W przypadku systemu iOS za pomocą listy rozwijanej **Ustawienie** możliwe będzie skonfigurowanie akcji dla następujących ustawień:
-  Maksymalna liczba prób wpisania numeru PIN
-  Okres karencji w trybie offline
-  Urządzenia, w przypadku których wykonano jailbreak lub zapewniono dostęp do konta root
-  Minimalna wersja systemu operacyjnego
-  Minimalna wersja aplikacji
-  Minimalna wersja zestawu SDK
-  Modele urządzeń

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
-  Maksymalna liczba prób wpisania numeru PIN
-  Okres karencji w trybie offline
-  Urządzenia, w przypadku których wykonano jailbreak lub zapewniono dostęp do konta root
-  Minimalna wersja systemu operacyjnego
-  Minimalna wersja aplikacji
-  Minimalna wersja poprawki
-  Producenci urządzeń

Aby użyć ustawienia **Producenci urządzeń**, wprowadź rozdzielaną średnikami listę producentów urządzeń z systemem Android. Producenta urządzenia z systemem Android można znaleźć w ustawieniach urządzenia.<br>
Przykładowe dane wejściowe: *Producent A; Producent B; Google* 

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
-  **Zablokuj dostęp** — zablokuj użytkownikowi końcowemu dostęp do aplikacji firmowej.
-  **Wyczyść dane** — wyczyść dane firmowe z urządzenia użytkownika końcowego.
-  **Ostrzegaj** — wyświetl okno dialogowe użytkownikowi końcowemu jako ostrzeżenie.

W niektórych przypadkach, na przykład dla ustawienia **Minimalna wersja systemu operacyjnego**, można skonfigurować ustawienie w taki sposób, aby poszczególne odpowiednie akcje były wykonywane w zależności od numeru wersji. 

![Zrzut ekranu przedstawiający akcje dostępu zasad ochrony aplikacji usługi Intune — ustawienie Minimalna wersja systemu operacyjnego](./media/apps-selective-wipe-access-actions05.png)

Gdy ustawienie zostanie w pełni skonfigurowane, wiersz będzie wyświetlany w widoku tylko do odczytu i będzie go można edytować w dowolnym momencie. Ponadto wiersz zostanie wyświetlony z listą rozwijaną w kolumnie **Ustawienie**. Ustawienia, które zostały już skonfigurowane i nie zezwalają na wykonanie wielu akcji, nie będą dostępne na liście rozwijanej.

## <a name="next-steps"></a>Następne kroki

Aby uzyskać więcej informacji na temat zasad ochrony aplikacji usługi Intune, zobacz:
- [Tworzenie i przypisywanie zasad ochrony aplikacji](app-protection-policies.md)
- [Ustawienia zasad ochrony aplikacji dla systemu iOS](app-protection-policy-settings-ios.md)
- [Ustawienia zasad ochrony aplikacji systemu Android w usłudze Microsoft Intune](app-protection-policy-settings-android.md) 


