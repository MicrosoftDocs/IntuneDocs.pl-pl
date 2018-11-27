---
title: Włączanie łącznika Mobile Threat Defense w usłudze Microsoft Intune
titleSuffix: ''
description: Włącz łącznik między partnerem usługi Mobile Threat Defense (MTD) i usługą Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: dbb6a37e-ba47-4b69-922c-d25e66c279f6
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 2937814ae5ceb6c7d8b3def4e954c8eec9337126
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52180480"
---
# <a name="enable-the-mobile-threat-defense-connector-in-intune"></a>Włączanie łącznika Mobile Threat Defense w usłudze Intune

> [!NOTE] 
> Niniejszy temat dotyczy wszystkich partnerów usługi Mobile Threat Defense.

Podczas konfiguracji usługi Mobile Threat Defense (MTD) skonfigurowano zasady służące do klasyfikowania zagrożeń w konsoli partnera usługi MTD i utworzono zasady zgodności urządzeń w usłudze Intune. Jeśli łącznik usługi Intune został już skonfigurowany w konsoli partnera usługi MTD, możesz teraz włączyć połączenie z usługą MTD w usłudze Intune.

## <a name="to-enable-the-mtd-connector"></a>Aby włączyć łącznik MTD

1. Przejdź do witryny [Azure Portal](https://portal.azure.com) i zaloguj się przy użyciu swoich poświadczeń usługi Intune. Po pomyślnym zalogowaniu zostanie wyświetlona strona **Pulpit nawigacyjny Azure**.

2. Na stronie **Pulpit nawigacyjny platformy Azure** w menu po lewej stronie wybierz pozycję **Wszystkie usługi**, a następnie w filtrze pola tekstowego wpisz wartość **Intune**.

3. Wybierz pozycję **Intune**. Zostanie otwarta strona **Pulpit nawigacyjny platformy Azure**.

4. Na stronie **Pulpit nawigacyjny usługi Intune** wybierz opcję **Zgodność urządzeń**, a następnie wybierz opcję **Mobile Threat Defense** pod sekcją **Instalator**.

5. W okienku **Mobile Threat Defense** wybierz pozycję **Dodaj**.

6. Z listy rozwijanej wybierz rozwiązanie MTD jako wartość pola **Łącznik usługi Mobile Threat Defense do instalacji**.

    ![Konfiguracja usługi MTD w witrynie Azure Portal usługi Intune](./media/enable-mtd-connector-1.png)

7. Włącz opcje przełącznika zgodnie z wymaganiami organizacji. Wyświetlane opcje przełącznika są zależne od partnera MTD.

## <a name="mtd-toggle-options"></a>Opcje przełącznika usługi MTD

Zgodnie z wymaganiami danej organizacji można określić, które opcje przełącznika usługi MTD należy włączyć. Poniżej przedstawiono więcej informacji:

- **Połącz urządzenia z systemem Android 4.1 lub nowszym z usługą [nazwa partnera MTD]**: po włączeniu tej opcji urządzenia z systemem Android 4.1 lub nowszym mogą zgłaszać zagrożenie bezpieczeństwa do usługi Intune.
    - **Oznacz jako niezgodne w przypadku nieodebrania żadnych danych**: jeśli usługa Intune nie odbiera danych dotyczących urządzenia na tej platformie od partnera MTD, należy uznać to urządzenie za niezgodne.
<br></br>
- **Połącz urządzenia z systemem iOS 8.0 lub nowszym z usługą [nazwa partnera MTD]**: po włączeniu tej opcji urządzenia z systemem iOS 8.0 lub nowszym mogą zgłaszać zagrożenie bezpieczeństwa do usługi Intune.
    - **Oznacz jako niezgodne w przypadku nieodebrania żadnych danych**: jeśli usługa Intune nie odbiera danych dotyczących urządzenia na tej platformie od partnera MTD, należy uznać to urządzenie za niezgodne.
<br></br>
- **Włącz synchronizację aplikacji dla urządzeń z systemem iOS**: zezwala temu partnerowi usługi Mobile Threat Defense na żądanie metadanych aplikacji systemu iOS kierowane do usługi Intune w celu użycia ich dla celów analizy zagrożeń.

- **Blokuj nieobsługiwane wersje systemu operacyjnego**: blokowanie, gdy na urządzeniu jest zainstalowany system operacyjny o niższym numerze wersji niż minimalna obsługiwana wersja.

- **Liczba dni, po których partner otrzyma stan „brak odpowiedzi”** : liczba dni braku aktywności, zanim usługa Intune uzna partnera za nieodpowiadającego z powodu utraty połączenia. Usługa Intune ignoruje stan zgodności dla partnerów MTD w stanie „brak odpowiedzi”.

> [!IMPORTANT] 
> Aplikacje MTD należy dodać i przypisać przed utworzeniem reguł zasad dotyczących zgodności urządzeń oraz dostępu warunkowego. Dzięki temu dana aplikacja MTD będzie gotowa i dostępna do zainstalowania dla użytkowników końcowych, zanim będą oni mogli uzyskać dostęp do poczty e-mail lub innych zasobów firmy.

> [!TIP]
> W okienku usługi Mobile Threat Defense wyświetlany jest **stan połączenia** i czas **ostatniej synchronizacji** między usługą Intune a partnerem usługi MTD.
