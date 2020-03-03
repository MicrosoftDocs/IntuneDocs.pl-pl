---
title: Czyszczenie danych przy użyciu akcji uruchamiania warunkowego zasad ochrony aplikacji
titleSuffix: Microsoft Intune
description: Dowiedz się, jak selektywnie czyścić dane przy użyciu akcji uruchamiania warunkowego zasad ochrony aplikacji w usłudze Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f5ca557e-a8e1-4720-b06e-837c4f0bc3ca
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0425b6a3f2c82f6ad2119286c8697f0eb0fc2f82
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77513914"
---
# <a name="selectively-wipe-data-using-app-protection-policy-conditional-launch-actions-in-intune"></a>Selektywne czyszczenie danych przy użyciu akcji uruchamiania warunkowego zasad ochrony aplikacji w usłudze Intune

Za pomocą zasad ochrony aplikacji usługi Intune można skonfigurować ustawienia służące do blokowania użytkownikom końcowym dostępu do aplikacji lub konta w firmie. Te ustawienia dotyczą relokacji danych i wymagań dostępu ustawianych w Twojej organizacji i mogą być na przykład związane z urządzeniami, w przypadku których wykonano jailbreak, i minimalnymi wersjami systemu operacyjnego.
 
Za pomocą tych ustawień możesz jawnie wyczyścić dane firmowe z urządzenia użytkownika końcowego w ramach akcji do wykonania w wyniku niezgodności. W przypadku niektórych ustawień możliwe będzie skonfigurowanie wielu akcji, takich jak blokowanie dostępu i czyszczenie danych na podstawie różnych określonych wartości.

## <a name="create-an-app-protection-policy-using-conditional-launch-actions"></a>Tworzenie zasad ochrony aplikacji przy użyciu akcji uruchamiania warunkowego

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz kolejno pozycje **Aplikacje** > **Zasady ochrony aplikacji**.
3. Kliknij pozycję **Utwórz zasady** i wybierz platformę urządzenia dla zasad. 
4. Kliknij pozycję **Skonfiguruj wymagane ustawienia**, aby wyświetlić listę ustawień dostępnych do skonfigurowania na potrzeby zasad. 
5. Przewinięcie w dół w okienku Ustawienia spowoduje wyświetlenie sekcji o nazwie **Uruchamianie warunkowe**, w której będzie się znajdowała edytowalna tabela.

    ![Zrzut ekranu przedstawiający akcje dostępu zasad ochrony aplikacji usługi Intune](./media/app-protection-policies-access-actions/apps-selective-wipe-access-actions01.png)

6. Wybierz pozycję w kolumnie **Ustawienie** i w kolumnie **Wartość** wprowadź wartość, która będzie wymagana od użytkowników, aby mogli zalogować się do aplikacji firmowej. 
7. W kolumnie **Akcja** wybierz akcję, którą chcesz wykonać, jeśli użytkownicy nie spełnili Twoich wymagań. W niektórych przypadkach dla pojedynczego ustawienia można skonfigurować wiele akcji. Aby uzyskać szczegółowe informacje, zobacz [Tworzenie i przypisywanie zasad ochrony aplikacji](app-protection-policies.md).

## <a name="policy-settings"></a>Ustawienia zasad 

Tabela ustawień zasad ochrony aplikacji zawiera kolumny **Ustawienie**, **Wartość** i **Akcja**.

### <a name="ios-policy-settings"></a>Ustawienia zasad systemu iOS
W przypadku systemu iOS/iPadOS za pomocą listy rozwijanej **Ustawienie** możliwe będzie skonfigurowanie akcji dla następujących ustawień:
- Maksymalna liczba prób wpisania numeru PIN
- Okres karencji w trybie offline
- Urządzenia, w przypadku których wykonano jailbreak lub zapewniono dostęp do konta root
- Minimalna wersja systemu operacyjnego
- Minimalna wersja aplikacji
- Minimalna wersja zestawu SDK
- Modele urządzeń
- Maksymalny dozwolony poziom zagrożenia urządzenia

Aby użyć ustawienia **Modele urządzeń**, wprowadź rozdzielaną średnikami listę identyfikatorów modeli urządzeń z systemem iOS/iPadOS. Te wartości nie uwzględniają wielkości liter. Poza obszarem raportowania usługi Intune dla danych wejściowych „Modele urządzeń” identyfikator modelu systemu iOS/iPadOS można znaleźć w kolumnie Typ urządzenia w [dokumentacji pomocy technicznej usługi HockeyApp](https://support.hockeyapp.net/kb/client-integration-ios-mac-os-x-tvos/ios-device-types) lub w tym [repozytorium GitHub firmy zewnętrznej](https://gist.github.com/adamawolf/3048717).<br>
Przykładowe dane wejściowe: *iPhone5,2; iPhone5,3*

Na urządzeniach użytkowników końcowych klient usługi Intune wykonuje akcję w oparciu o proste dopasowywanie ciągów modelu urządzenia określonych w usłudze Intune dla zasad ochrony aplikacji. Dopasowywanie całkowicie zależy od danych zgłoszonych przez urządzenie. Zachęcamy, aby administrator IT upewnił się, że faktyczne zachowanie odpowiada zamierzonemu przez przetestowanie tego ustawienia z użyciem różnych producentów i modeli urządzeń w ramach małej grupy użytkowników. Wartość domyślna to **Nie skonfigurowano**.<br>
Ustaw jedną z następujących akcji: 
- Zezwalaj na określone (blokuj nieokreślone)
- Zezwalaj na określone (wyczyść nieokreślone)

**Co się stanie, jeśli administrator IT wprowadzi różne listy identyfikatorów modeli urządzeń z systemem iOS/iPadOS w zasadach przeznaczonych dla tych samych aplikacji i dla tego samego użytkownika usługi Intune?**<br>
W przypadku wystąpienia konfliktu wartości skonfigurowanych dla dwóch zasad ochrony aplikacji usługa Intune zwykle przyjmuje najbardziej restrykcyjne podejście. W związku z tym wynikowe zasady wysłane do aplikacji docelowej otwieranej przez docelowego użytkownika usługi Intune byłyby częścią wspólną identyfikatorów modeli urządzeń z systemem iOS/iPadOS wymienionych w *zasadach A* i *zasadach B* przeznaczonych dla tej samej kombinacji aplikacja/użytkownik. Jeśli na przykład *zasady A* określają listę „iPhone5,2; iPhone5,3”, natomiast *zasady B* określają wartość „iPhone5,3”, wynikowe zasady dotyczące użytkownika usługi Intune, dla którego mają zastosowanie zarówno *zasady A*, jak i *zasady B*, będą zawierały wartość „iPhone5,3”. 

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
- Wymagaj skanowania zagrożeń w aplikacjach
- Minimalna wersja Portalu firmy
- Maksymalny dozwolony poziom zagrożenia urządzenia

Korzystając z ustawienia **Minimalna wersja Portalu firmy**, można określić konkretną minimalną zdefiniowaną wersję aplikacji Portal firmy, która jest wymuszana na urządzeniu użytkownika końcowego. To ustawienie uruchamiania warunkowego umożliwia ustawienie wartości **Blokuj dostęp**, **Wyczyść dane** i **Ostrzegaj** jako możliwych akcji, kiedy każda wartość nie zostanie spełniona. Możliwe formaty dla tej wartości są zgodne ze wzorcem *[Wersja główna].[Wersja pomocnicza]* , *[Wersja główna].[Wersja pomocnicza].[Kompilacja]* lub *[Wersja główna].[Wersja pomocnicza].[Kompilacja].[Poprawka]* . Ponieważ niektórzy użytkownicy końcowi mogą nie chcieć natychmiastowej wymuszonej aktualizacji, opcja „Ostrzegaj” może być idealna podczas konfigurowania tego ustawienia. Sklep Google Play wysyła tylko bajty delta dla aktualizacji aplikacji, jednak nadal może to być duża ilość danych, których użytkownik może nie chcieć wykorzystywać, jeśli w czasie aktualizacji korzysta z danych komórkowych. Wymuszenie aktualizacji, a tym samym pobranie zaktualizowanej aplikacji, może spowodować naliczenie nieoczekiwanych opłat za przesył danych w czasie aktualizacji. Jeśli ustawienie **Minimalna wersja Portalu firmy** zostanie skonfigurowane, będzie miało wpływ na wszystkich użytkowników końcowych, którzy będą korzystać z wersji 5.0.4560.0 aplikacji Portal firmy i z wszystkich kolejnych wersji. To ustawienie nie będzie miało wpływu na użytkowników korzystających z wersji aplikacji Portal firmy, które są starsze niż wersja, z którą ta funkcja została wydana. Użytkownikom końcowym, którzy na swoich urządzeniach korzystają z automatycznych aktualizacji aplikacji, prawdopodobnie nie zostanie wyświetlone żadne okno dialogowe dotyczące tej funkcji, ponieważ prawdopodobnie będą oni używać najnowszej wersji aplikacji Portal firmy. To ustawienie dotyczy tylko systemu Android z ochroną aplikacji dla zarejestrowanych i niezarejestrowanych urządzeń.

Aby użyć ustawienia **Producenci urządzeń**, wprowadź rozdzielaną średnikami listę producentów urządzeń z systemem Android. Te wartości nie uwzględniają wielkości liter. Poza obszarem raportowania usługi Intune producenta urządzenia z systemem Android można znaleźć w ustawieniach urządzenia. <br>
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

![Zrzut ekranu przedstawiający akcje dostępu ochrony aplikacji — ustawienie Minimalna wersja systemu operacyjnego](./media/app-protection-policies-access-actions/apps-selective-wipe-access-actions05.png)

Gdy ustawienie zostanie w pełni skonfigurowane, wiersz będzie wyświetlany w widoku tylko do odczytu i będzie go można edytować w dowolnym momencie. Ponadto wiersz zostanie wyświetlony z listą rozwijaną w kolumnie **Ustawienie**. Ustawienia, które zostały już skonfigurowane i nie zezwalają na wykonanie wielu akcji, nie będą dostępne na liście rozwijanej.

## <a name="next-steps"></a>Następne kroki

Aby uzyskać więcej informacji na temat zasad ochrony aplikacji usługi Intune, zobacz:
- [Tworzenie i przypisywanie zasad ochrony aplikacji](app-protection-policies.md)
- [Ustawienia zasad ochrony aplikacji dla systemu iOS/iPadOS](app-protection-policy-settings-ios.md)
- [Ustawienia zasad ochrony aplikacji systemu Android w usłudze Microsoft Intune](app-protection-policy-settings-android.md) 
