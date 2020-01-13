---
title: Włączanie łącznika usługi Mobile Threat Defense dla niezarejestrowanych urządzeń
titleSuffix: Microsoft Intune
description: Włączanie łącznika usługi Mobile Threat Defense dla niezarejestrowanych urządzeń w usłudze Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9571f7d0ae10f33007d5ae50b403580232c2e870
ms.sourcegitcommit: 06dce5c8111592ad774247e86e539dd3128117e5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/30/2019
ms.locfileid: "75545939"
---
# <a name="enable-the-mobile-threat-defense-connector-in-intune-for-unenrolled-devices"></a>Włączanie łącznika usługi Mobile Threat Defense dla niezarejestrowanych urządzeń w usłudze Intune

Podczas konfigurowania usługi Mobile Threat Defense (MTD) skonfigurowano zasady służące do klasyfikowania zagrożeń w konsoli partnera usługi Mobile Threat Defense i utworzono zasady ochrony aplikacji w usłudze Intune. Jeśli łącznik usługi Intune został już skonfigurowany w konsoli partnera usługi MTD, możesz teraz włączyć połączenie z usługą MTD dla aplikacji partnera usługi MTD.

> [!NOTE]
> Ten artykuł dotyczy wszystkich partnerów usługi Mobile Threat Defense, którzy obsługują zasady ochrony aplikacji: Better Mobile (Android), Zimperium (Android/iOS), Lookout for Work (Android/iOS).

## <a name="classic-conditional-access-policies-for-mtd-apps"></a>Klasyczne zasady dostępu warunkowego dla aplikacji MTD

Po zintegrowaniu nowej aplikacji z usługą Intune Mobile Threat Defense (MTD) i włączeniu połączenia z usługą Intune usługa ta tworzy klasyczne zasady dostępu warunkowego w usłudze Azure Active Directory. Każda zintegrowana aplikacja MTD, w tym [Defender ATP](advanced-threat-protection.md) lub dowolny z naszych dodatkowych [partnerów MTD](mobile-threat-defense.md#mobile-threat-defense-partners), tworzy nowe klasyczne zasady dostępu warunkowego. Te zasady można ignorować, ale nie należy ich edytować, usuwać ani wyłączać.

Jeśli zasady klasyczne zostaną usunięte, należy usunąć połączenie z usługą Intune, które było odpowiedzialne za ich tworzenie, a następnie skonfigurować je ponownie. Ten proces spowoduje ponowne utworzenie zasad klasycznych. Migrowanie zasad klasycznych dla aplikacji MTD do nowego typu zasad w celu uzyskania dostępu warunkowego nie jest obsługiwane.

Klasyczne zasady dostępu warunkowego dla aplikacji MTD mają następujące cechy:

- Są używane przez usługę Intune MTD do żądania zarejestrowania urządzeń w usłudze Azure AD, dzięki czemu mają one identyfikator urządzenia przed rozpoczęciem komunikacji z partnerami MTD. Ten identyfikator jest wymagany, aby urządzenia mogły pomyślnie zgłaszać swój stan do usługi Intune.

- Nie mają wpływu na żadne inne aplikacje lub zasoby w chmurze.

- Różnią się od zasad dostępu warunkowego, które można utworzyć, aby ułatwić sobie zarządzanie usługą MTD.

- Domyślnie nie wchodzą w interakcje z innymi zasadami dostępu warunkowego używanymi na potrzeby oceny.

Aby wyświetlić klasyczne zasady dostępu warunkowego, w witrynie [Azure Portal](https://portal.azure.com/#home) przejdź do pozycji **Azure Active Directory** > **Dostęp warunkowy** > **Zasady klasyczne**.

## <a name="to-enable-the-mtd-connector"></a>Aby włączyć łącznik MTD

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Wybierz pozycję **Administracja dzierżawą** > **Łączniki i tokeny** > **Mobile Threat Defense**.

3. W okienku **Mobile Threat Defense** wybierz pozycję **Dodaj**.

4. Z listy rozwijanej wybierz rozwiązanie MTD jako wartość pola **Łącznik usługi Mobile Threat Defense do instalacji**.

    <!-- ![MTD setup in Intune](PLACEHOLDER, need a new screenshot of this page) -->

5. Włącz opcje przełącznika zgodnie z wymaganiami organizacji. Wyświetlane opcje przełącznika są zależne od partnera MTD.

## <a name="mobile-threat-defense-toggle-options"></a>Opcje przełączania usługi Mobile Threat Defense

Zgodnie z wymaganiami danej organizacji można określić, które opcje przełącznika usługi MTD należy włączyć. Poniżej przedstawiono więcej informacji:

**Ustawienia zasad ochrony aplikacji**

- **Połącz urządzenia z systemem Android w wersji 4.4 lub nowszej z łącznikiem *\<nazwa partnera usługi MTD>* na potrzeby oceny zasad ochrony aplikacji**: Po włączeniu tej opcji zasady ochrony aplikacji korzystające z reguły poziomu zagrożenia urządzenia będą oceniać urządzenia z uwzględnieniem danych z tego łącznika.

- **Połącz urządzenia z systemem iOS w wersji 11 lub nowszej z łącznikiem *\<nazwa partnera usługi MTD>* na potrzeby oceny zasad ochrony aplikacji**: Po włączeniu tej opcji zasady ochrony aplikacji korzystające z reguły poziomu zagrożenia urządzenia będą oceniać urządzenia z uwzględnieniem danych z tego łącznika.

**Wspólne ustawienia współużytkowane**

- **Liczba dni, po których partner otrzyma stan „brak odpowiedzi”** : liczba dni braku aktywności, zanim usługa Intune uzna partnera za nieodpowiadającego z powodu utraty połączenia. Usługa Intune ignoruje stan zgodności dla partnerów MTD w stanie „brak odpowiedzi”.

> [!TIP]
> W okienku usługi Mobile Threat Defense wyświetlany jest **stan połączenia** i czas **ostatniej synchronizacji** między usługą Intune a partnerem usługi MTD.

## <a name="next-steps"></a>Następne kroki

- [Tworzenie zasad ochrony aplikacji usługi Mobile Threat Defense za pomocą usługi Intune](~/protect/mtd-app-protection-policy.md).
