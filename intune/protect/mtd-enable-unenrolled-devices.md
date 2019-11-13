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
ms.openlocfilehash: b2744a27a733824bab9d920f4de0b49e951c1c34
ms.sourcegitcommit: a4c7339ec9ff5b1b846cb3cca887cf91b5cd4baa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627638"
---
# <a name="enable-the-mobile-threat-defense-connector-in-intune-for-unenrolled-devices"></a>Włączanie łącznika usługi Mobile Threat Defense dla niezarejestrowanych urządzeń w usłudze Intune

Podczas konfigurowania usługi Mobile Threat Defense (MTD) skonfigurowano zasady służące do klasyfikowania zagrożeń w konsoli partnera usługi Mobile Threat Defense i utworzono zasady ochrony aplikacji w usłudze Intune. Jeśli łącznik usługi Intune został już skonfigurowany w konsoli partnera usługi MTD, możesz teraz włączyć połączenie z usługą MTD dla aplikacji partnera usługi MTD.

> [!NOTE] 
> Ten artykuł dotyczy wszystkich partnerów usługi Mobile Threat Defense, którzy obsługują zasady ochrony aplikacji: Better Mobile (Android), Zimperium (iOS), Lookout for Work (Android/iOS).

## <a name="to-enable-the-mtd-connector"></a>Aby włączyć łącznik MTD

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).

2. Na stronie **Pulpit nawigacyjny usługi Intune** wybierz opcję **Zgodność urządzeń**, a następnie wybierz opcję **Mobile Threat Defense** pod sekcją **Instalator**.

3. W okienku **Mobile Threat Defense** wybierz pozycję **Dodaj**.

4. Z listy rozwijanej wybierz rozwiązanie MTD jako wartość pola **Łącznik usługi Mobile Threat Defense do instalacji**.

    <!-- ![MTD setup in Intune](PLACEHOLDER, need a new screenshot of this page) -->

5. Włącz opcje przełącznika zgodnie z wymaganiami organizacji. Wyświetlane opcje przełącznika są zależne od partnera MTD.

## <a name="mtd-toggle-options"></a>Opcje przełącznika usługi MTD

Zgodnie z wymaganiami danej organizacji można określić, które opcje przełącznika usługi MTD należy włączyć. Poniżej przedstawiono więcej informacji:

**Ustawienia zasad ochrony aplikacji**
- **Połącz urządzenia z systemem Android w wersji 4.4 lub nowszej z łącznikiem *\<nazwa partnera usługi MTD>* na potrzeby oceny zasad ochrony aplikacji**: Po włączeniu tej opcji zasady ochrony aplikacji korzystające z reguły poziomu zagrożenia urządzenia będą oceniać urządzenia z uwzględnieniem danych z tego łącznika.
- **Połącz urządzenia z systemem iOS w wersji 11 lub nowszej z łącznikiem *\<nazwa partnera usługi MTD>* na potrzeby oceny zasad ochrony aplikacji**: Po włączeniu tej opcji zasady ochrony aplikacji korzystające z reguły poziomu zagrożenia urządzenia będą oceniać urządzenia z uwzględnieniem danych z tego łącznika.

**Wspólne ustawienia współużytkowane**
- **Liczba dni, po których partner otrzyma stan „brak odpowiedzi”** : liczba dni braku aktywności, zanim usługa Intune uzna partnera za nieodpowiadającego z powodu utraty połączenia. Usługa Intune ignoruje stan zgodności dla partnerów MTD w stanie „brak odpowiedzi”.

> [!TIP]
> W okienku usługi Mobile Threat Defense wyświetlany jest **stan połączenia** i czas **ostatniej synchronizacji** między usługą Intune a partnerem usługi MTD.

> [!NOTE] 
> Po włączeniu połączenia usługi Mobile Threat Defense z usługą Intune usługa Intune tworzy klasyczne zasady dostępu warunkowego w usłudze Azure Active Directory. Każda zintegrowana aplikacja MTD, w tym [Defender ATP](advanced-threat-protection.md) lub dowolny z naszych dodatkowych [partnerów MTD](mobile-threat-defense.md#mobile-threat-defense-partners), tworzy nowe klasyczne zasady dostępu warunkowego. **Te zasady można ignorować, ale nie należy ich edytować, usuwać ani wyłączać.**
> 
> Klasyczne zasady dostępu warunkowego dla aplikacji MTD mają następujące cechy: 
> - Są używane przez usługę Intune MTD do żądania zarejestrowania urządzeń w usłudze Azure AD, dzięki czemu mają one identyfikator urządzenia przed rozpoczęciem komunikacji z partnerami MTD. Ten identyfikator jest wymagany, aby urządzenia mogły pomyślnie zgłaszać swój stan do usługi Intune.  
> - Nie mają wpływu na żadne inne aplikacje lub zasoby w chmurze.  
> - Różnią się od zasad dostępu warunkowego, które można utworzyć, aby ułatwić sobie zarządzanie usługą MTD lub na potrzeby żądania urzędu certyfikacji dla ochrony aplikacji.
> - Domyślnie nie wchodzą w interakcje z innymi zasadami dostępu warunkowego używanymi na potrzeby oceny.  
>
> Aby wyświetlić klasyczne zasady dostępu warunkowego, w witrynie [Azure Portal](https://portal.azure.com/#home) przejdź do pozycji **Azure Active Directory** > **Dostęp warunkowy** > **Zasady klasyczne**.

## <a name="next-steps"></a>Następne kroki

- [Tworzenie zasad ochrony aplikacji usługi Mobile Threat Defense za pomocą usługi Intune](~/protect/mtd-app-protection-policy.md).
