---
title: Selektywne czyszczenie danych przy użyciu akcji dostępu zasad ochrony aplikacji
titleSuffix: Microsoft Intune
description: Dowiedz się, jak selektywnie czyścić dane przy użyciu akcji dostępu zasad ochrony aplikacji w usłudze Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/03/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f5ca557e-a8e1-4720-b06e-837c4f0bc3ca
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2cfd426a0ae7165a7aae60a90d104852fd834db6
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/07/2018
ms.locfileid: "37909120"
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
6. Przewinięcie w dół w oknie **Ustawienia** spowoduje wyświetlenie sekcji o nazwie **Akcje dostępu**, w której będzie się znajdowała edytowalna tabela.

    ![Zrzut ekranu przedstawiający akcje dostępu zasad ochrony aplikacji usługi Intune](./media/apps-selective-wipe-access-actions01.png)

7. Wybierz pozycję w kolumnie **Ustawienie** i w kolumnie **Wartość** wprowadź wartość, która będzie wymagana od użytkowników, aby mogli zalogować się do aplikacji firmowej. 
8. W kolumnie **Akcja** wybierz akcję, którą chcesz wykonać, jeśli użytkownicy nie spełnili Twoich wymagań. W niektórych przypadkach dla pojedynczego ustawienia można skonfigurować wiele akcji. Aby uzyskać szczegółowe informacje, zobacz [Tworzenie i przypisywanie zasad ochrony aplikacji](app-protection-policies.md).

>[!NOTE]
> Aby użyć ustawienia **Modele urządzeń**, wprowadź rozdzielaną średnikami listę identyfikatorów modeli. 

## <a name="policy-settings"></a>Ustawienia zasad 

Tabela ustawień zasad ochrony aplikacji zawiera kolumny **Ustawienie**, **Wartość** i **Akcja**.

W przypadku systemu iOS za pomocą listy rozwijanej **Ustawienie** możliwe będzie skonfigurowanie akcji dla następujących ustawień:
-  Maksymalna liczba prób wpisania numeru PIN
-  Okres karencji w trybie offline
-  Urządzenia, w przypadku których wykonano jailbreak lub zapewniono dostęp do konta root
-  Minimalna wersja systemu operacyjnego
-  Minimalna wersja aplikacji
-  Minimalna wersja zestawu SDK
-  Modele urządzeń

W przypadku systemu Android za pomocą listy rozwijanej **Ustawienie** możliwe będzie skonfigurowanie akcji dla następujących ustawień:
-  Maksymalna liczba prób wpisania numeru PIN
-  Okres karencji w trybie offline
-  Urządzenia, w przypadku których wykonano jailbreak lub zapewniono dostęp do konta root
-  Minimalna wersja systemu operacyjnego
-  Minimalna wersja aplikacji
-  Minimalna wersja poprawki
-  Producenci urządzeń

Domyślnie w tabeli będą znajdowały się wypełnione wiersze jako ustawienia skonfigurowane dla wartości **Okres karencji w trybie offline** i **Maksymalna liczba prób wpisania numeru PIN**, jeśli ustawienie **Wymagaj numeru PIN w celu udzielenia dostępu** ma wartość **Tak**.
 
Aby skonfigurować ustawienie, wybierz ustawienie z listy rozwijanej w kolumnie **Ustawienie**. Po wybraniu ustawienia w tym samym wierszu w kolumnie **Wartość** zostanie włączone edytowalne pole tekstowe, jeśli wymagane jest ustawienie wartości. Zostanie również włączona lista rozwijana w kolumnie **Akcja** zawierająca zestaw warunkowo uruchamianych akcji mających zastosowanie dla danego ustawienia. 

Poniższa lista zawiera typowe akcje:
-  **Zablokuj dostęp** — zablokuj użytkownikowi końcowemu dostęp do aplikacji firmowej.
-  **Wyczyść dane** — wyczyść dane firmowe z urządzenia użytkownika końcowego.
-  **Ostrzegaj** — wyświetl okno dialogowe użytkownikowi końcowemu jako ostrzeżenie.

### <a name="additional-settings-and-actions"></a>Dodatkowe ustawienia i akcje 

W niektórych przypadkach, na przykład dla ustawienia **Minimalna wersja systemu operacyjnego**, można skonfigurować ustawienie w taki sposób, aby poszczególne odpowiednie akcje były wykonywane w zależności od numeru wersji. 

![Zrzut ekranu przedstawiający akcje dostępu zasad ochrony aplikacji usługi Intune — ustawienie Minimalna wersja systemu operacyjnego](./media/apps-selective-wipe-access-actions05.png)

Gdy ustawienie zostanie w pełni skonfigurowane, wiersz będzie wyświetlany w widoku tylko do odczytu i będzie go można edytować w dowolnym momencie. Ponadto wiersz zostanie wyświetlony z listą rozwijaną w kolumnie **Ustawienie**. Ustawienia, które zostały już skonfigurowane i nie zezwalają na wykonanie wielu akcji, nie będą dostępne na liście rozwijanej.

## <a name="next-steps"></a>Następne kroki

Aby uzyskać więcej informacji na temat zasad ochrony aplikacji usługi Intune, zobacz:
- [Tworzenie i przypisywanie zasad ochrony aplikacji](app-protection-policies.md)
- [Ustawienia zasad ochrony aplikacji dla systemu iOS](app-protection-policy-settings-ios.md)
- [Ustawienia zasad ochrony aplikacji systemu Android w usłudze Microsoft Intune](app-protection-policy-settings-android.md) 


