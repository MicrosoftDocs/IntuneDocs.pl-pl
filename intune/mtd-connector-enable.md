---
title: Włączanie łącznika Mobile Threat Defense w usłudze Microsoft Intune
titleSuffix: Microsoft Intune
description: Włącz łącznik między partnerem usługi Mobile Threat Defense (MTD) i usługą Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: dbb6a37e-ba47-4b69-922c-d25e66c279f6
ms.reviewer: davidra
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e7272ddb502075f071b03925c47993c97e447bce
ms.sourcegitcommit: ec22a186a9cfa489a8490698e387624e480892d8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/13/2019
ms.locfileid: "68960674"
---
# <a name="enable-the-mobile-threat-defense-connector-in-intune"></a>Włączanie łącznika Mobile Threat Defense w usłudze Intune

> [!NOTE] 
> Niniejszy temat dotyczy wszystkich partnerów usługi Mobile Threat Defense.

Podczas konfiguracji usługi Mobile Threat Defense (MTD) skonfigurowano zasady służące do klasyfikowania zagrożeń w konsoli partnera usługi MTD i utworzono zasady zgodności urządzeń w usłudze Intune. Jeśli łącznik usługi Intune został już skonfigurowany w konsoli partnera usługi MTD, możesz teraz włączyć połączenie z usługą MTD dla aplikacji partnera usługi MTD.

Po zintegrowaniu nowej aplikacji z usługą Intune Mobile Threat Defense (MTD) i włączeniu połączenia z usługą Intune usługa ta tworzy klasyczne zasady dostępu warunkowego w usłudze Azure Active Directory. Każda zintegrowana aplikacja MTD, w tym [Defender ATP](advanced-threat-protection.md) lub dowolny z naszych dodatkowych [partnerów MTD](mobile-threat-defense.md#mobile-threat-defense-partners), tworzy nowe klasyczne zasady dostępu warunkowego. Te zasady można ignorować, ale nie należy ich edytować, usuwać ani wyłączać.

Klasyczne zasady dostępu warunkowego dla aplikacji MTD mają następujące cechy: 

- Są używane przez usługę Intune MTD do żądania zarejestrowania urządzeń w usłudze Azure AD, dzięki czemu mają one identyfikator urządzenia przed rozpoczęciem komunikacji z partnerami MTD. Ten identyfikator jest wymagany, aby urządzenia mogły pomyślnie zgłaszać swój stan do usługi Intune.  
- Nie mają wpływu na żadne inne aplikacje lub zasoby w chmurze.  
- Różnią się od zasad dostępu warunkowego, które można utworzyć, aby ułatwić sobie zarządzanie usługą MTD.
- Domyślnie nie wchodzą w interakcje z innymi zasadami dostępu warunkowego używanymi na potrzeby oceny.  

Aby wyświetlić klasyczne zasady dostępu warunkowego, w witrynie [Azure Portal](https://portal.azure.com/#home) przejdź do pozycji **Azure Active Directory** > **Dostęp warunkowy** > **Zasady klasyczne**.


## <a name="to-enable-the-mtd-connector"></a>Aby włączyć łącznik MTD

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).

4. Na stronie **Pulpit nawigacyjny usługi Intune** wybierz opcję **Zgodność urządzeń**, a następnie wybierz opcję **Mobile Threat Defense** pod sekcją **Instalator**.

5. W okienku **Mobile Threat Defense** wybierz pozycję **Dodaj**.

6. Z listy rozwijanej wybierz rozwiązanie MTD jako wartość pola **Łącznik usługi Mobile Threat Defense do instalacji**.

    ![Konfiguracja usługi MTD w witrynie Azure Portal usługi Intune](./media/enable-mtd-connector-1.png)

7. Włącz opcje przełącznika zgodnie z wymaganiami organizacji. Wyświetlane opcje przełącznika są zależne od partnera MTD.

## <a name="mtd-toggle-options"></a>Opcje przełącznika usługi MTD

Zgodnie z wymaganiami danej organizacji można określić, które opcje przełącznika usługi MTD należy włączyć. Poniżej przedstawiono więcej informacji:

- **Połącz urządzenia z systemem Android 4.1 lub nowszym z usługą [nazwa partnera MTD] for Work MTD**: po włączeniu tej opcji urządzenia z systemem Android 4.1 lub nowszym mogą zgłaszać zagrożenie bezpieczeństwa do usługi Intune.
  - **Oznacz jako niezgodne w przypadku nieodebrania żadnych danych**: jeśli usługa Intune nie odbiera danych dotyczących urządzenia na tej platformie od partnera MTD, należy uznać to urządzenie za niezgodne.
<br></br>
- **Połącz urządzenia z systemem iOS 8.0 lub nowszym z usługą [nazwa partnera MTD] for Work MTD**: po włączeniu tej opcji urządzenia z systemem iOS 8.0 lub nowszym mogą zgłaszać zagrożenie bezpieczeństwa do usługi Intune.
  - **Oznacz jako niezgodne w przypadku nieodebrania żadnych danych**: jeśli usługa Intune nie odbiera danych dotyczących urządzenia na tej platformie od partnera MTD, należy uznać to urządzenie za niezgodne.
<br></br>
- **Włącz synchronizację aplikacji dla urządzeń z systemem iOS**: zezwala temu partnerowi usługi Mobile Threat Defense na żądanie metadanych aplikacji systemu iOS kierowane do usługi Intune w celu użycia ich dla celów analizy zagrożeń.

- **Blokuj nieobsługiwane wersje systemu operacyjnego**: blokowanie, gdy na urządzeniu jest zainstalowany system operacyjny o niższym numerze wersji niż minimalna obsługiwana wersja.

- **Liczba dni, po których partner otrzyma stan „brak odpowiedzi”** : liczba dni braku aktywności, zanim usługa Intune uzna partnera za nieodpowiadającego z powodu utraty połączenia. Usługa Intune ignoruje stan zgodności dla partnerów MTD w stanie „brak odpowiedzi”.

> [!IMPORTANT] 
> Jeśli to możliwe, zalecamy dodać i przypisać aplikacje MTD przed utworzeniem reguł zasad dotyczących zgodności urządzeń oraz dostępu warunkowego. Dzięki temu dana aplikacja MTD będzie gotowa i dostępna do zainstalowania dla użytkowników końcowych, zanim będą oni mogli uzyskać dostęp do poczty e-mail lub innych zasobów firmy.

> [!TIP]
> W okienku usługi Mobile Threat Defense wyświetlany jest **stan połączenia** i czas **ostatniej synchronizacji** między usługą Intune a partnerem usługi MTD.
