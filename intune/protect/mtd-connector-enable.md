---
title: Włączanie łącznika Mobile Threat Defense w usłudze Microsoft Intune
titleSuffix: Microsoft Intune
description: Włącz łącznik między partnerem usługi Mobile Threat Defense (MTD) i usługą Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: dbb6a37e-ba47-4b69-922c-d25e66c279f6
ms.reviewer: davidra
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b8243ae4014660a76c6327afd9c970ce8a9eae58
ms.sourcegitcommit: 960ffb2214c35d75ad219fa2571a999529a0abd4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2019
ms.locfileid: "74478848"
---
# <a name="enable-the-mobile-threat-defense-connector-in-intune"></a>Włączanie łącznika Mobile Threat Defense w usłudze Intune

Podczas konfigurowania usługi Mobile Threat Defense (MTD) skonfigurowano zasady służące do klasyfikowania zagrożeń w konsoli partnera usługi Mobile Threat Defense i utworzono zasady zgodności urządzenia w usłudze Intune. Jeśli łącznik usługi Intune został już skonfigurowany w konsoli partnera usługi MTD, możesz teraz włączyć połączenie z usługą MTD dla aplikacji partnera usługi MTD.

> [!NOTE]
> Niniejszy temat dotyczy wszystkich partnerów usługi Mobile Threat Defense.

## <a name="classic-conditional-access-policies-for-mtd-apps"></a>Klasyczne zasady dostępu warunkowego dla aplikacji MTD

Po zintegrowaniu nowej aplikacji z usługą Intune Mobile Threat Defense (MTD) i włączeniu połączenia z usługą Intune usługa ta tworzy klasyczne zasady dostępu warunkowego w usłudze Azure Active Directory. Każda zintegrowana aplikacja MTD, w tym [Defender ATP](advanced-threat-protection.md) lub dowolny z naszych dodatkowych [partnerów MTD](mobile-threat-defense.md#mobile-threat-defense-partners), tworzy nowe klasyczne zasady dostępu warunkowego. Te zasady można ignorować, ale nie należy ich edytować, usuwać ani wyłączać.

Jeśli zasady klasyczne zostaną usunięte, należy usunąć połączenie z usługą Intune, które było odpowiedzialne za ich tworzenie, a następnie skonfigurować je ponownie. Ten proces spowoduje ponowne utworzenie zasad klasycznych. Migrowanie zasad klasycznych dla aplikacji MTD do nowego typu zasad w celu uzyskania dostępu warunkowego nie jest obsługiwane.

Klasyczne zasady dostępu warunkowego dla aplikacji MTD mają następujące cechy:

- Są używane przez usługę Intune MTD do żądania zarejestrowania urządzeń w usłudze Azure AD, dzięki czemu mają one identyfikator urządzenia przed rozpoczęciem komunikacji z partnerami MTD. Ten identyfikator jest wymagany, aby urządzenia mogły pomyślnie zgłaszać swój stan do usługi Intune.

- Nie mają wpływu na żadne inne aplikacje lub zasoby w chmurze.

- Różnią się od zasad dostępu warunkowego, które można utworzyć, aby ułatwić sobie zarządzanie usługą MTD.

- Domyślnie nie wchodzą w interakcje z innymi zasadami dostępu warunkowego używanymi na potrzeby oceny.

Aby wyświetlić klasyczne zasady dostępu warunkowego, w witrynie [Azure Portal](https://portal.azure.com/#home) przejdź do pozycji **Azure Active Directory** > **Dostęp warunkowy** > **Zasady klasyczne**.

## <a name="to-enable-the-mobile-threat-defense-connector"></a>Włączanie łącznika Mobile Threat Defense w usłudze Intune

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Wybierz pozycję **Administracja dzierżawą** > **Łączniki i tokeny** > **Mobile Threat Defense**.

3. W okienku **Mobile Threat Defense** wybierz pozycję **Dodaj**.

4. Z listy rozwijanej w polu **Łącznik usługi Mobile Threat Defense do instalacji** wybierz swoje rozwiązanie MTD.

5. Włącz opcje przełącznika zgodnie z wymaganiami organizacji. Wyświetlane opcje przełącznika są zależne od partnera MTD.  Na przykład na poniższej ilustracji przedstawiono opcje dostępne dla rozwiązania Symantec Endpoint Protection:

   ![Konfiguracja usługi MTD w witrynie Azure Portal usługi Intune](./media/mtd-connector-enable/enable-mtd-connector-1.png)

## <a name="mobile-threat-defense-toggle-options"></a>Opcje przełączania usługi Mobile Threat Defense

Zgodnie z wymaganiami danej organizacji można określić, które opcje przełącznika usługi MTD należy włączyć. Nie wszystkie z następujących opcji są obsługiwane przez wszystkich partnerów usługi Mobile Thread Defense:

**Ustawienia zasad zgodności rozwiązania MDM**

- **Połącz urządzenia z systemem Android w wersji _\<obsługiwane wersje >_ z łącznikiem _\<nazwa partnera usługi MTD>_** : po włączeniu tej opcji urządzenia z systemem Android 4.1 lub nowszym mogą zgłaszać zagrożenie bezpieczeństwa do usługi Intune.

- **Połącz urządzenia z systemem iOS w wersji _\<obsługiwane wersje >_ z łącznikiem _\<nazwa partnera usługi MTD>_** : po włączeniu tej opcji urządzenia z systemem iOS 8.0 lub nowszym mogą zgłaszać zagrożenie bezpieczeństwa do usługi Intune.

- **Włącz synchronizację aplikacji dla urządzeń z systemem iOS**: zezwala temu partnerowi usługi Mobile Threat Defense na żądanie metadanych aplikacji systemu iOS kierowane do usługi Intune w celu użycia ich dla celów analizy zagrożeń.

- **Blokuj nieobsługiwane wersje systemu operacyjnego**: blokowanie, gdy na urządzeniu jest zainstalowany system operacyjny o niższym numerze wersji niż minimalna obsługiwana wersja.

**Ustawienia zasad ochrony aplikacji**

- **Połącz urządzenia z systemem Android w wersji *\<obsługiwane wersje >* z łącznikiem *\<nazwa partnera usługi MTD>* na potrzeby oceny zasad ochrony aplikacji**: Po włączeniu tej opcji zasady ochrony aplikacji korzystające z reguły poziomu zagrożenia urządzenia będą oceniać urządzenia z uwzględnieniem danych z tego łącznika.

- **Połącz urządzenia z systemem iOS w wersji *\<obsługiwane wersje >* z łącznikiem *\<nazwa partnera usługi MTD>* na potrzeby oceny zasad ochrony aplikacji**: Po włączeniu tej opcji zasady ochrony aplikacji korzystające z reguły poziomu zagrożenia urządzenia będą oceniać urządzenia z uwzględnieniem danych z tego łącznika.

Aby dowiedzieć się więcej o używaniu łączników usługi Mobile Threat Defense do oceny zasad ochrony aplikacji w usłudze Intune, zobacz [Konfigurowanie usługi Mobile Threat Defense dla niezarejestrowanych urządzeń](~/protect/mtd-enable-unenrolled-devices.md).

**Typowe ustawienia współużytkowane**

- **Liczba dni, po których partner otrzyma stan „brak odpowiedzi”** : liczba dni braku aktywności, zanim usługa Intune uzna partnera za nieodpowiadającego z powodu utraty połączenia. Usługa Intune ignoruje stan zgodności dla partnerów MTD w stanie „brak odpowiedzi”.

> [!IMPORTANT]
> Jeśli to możliwe, zalecamy dodać i przypisać aplikacje MTD przed utworzeniem reguł zasad dotyczących zgodności urządzeń oraz dostępu warunkowego. Dzięki temu dana aplikacja MTD będzie gotowa i dostępna do zainstalowania dla użytkowników końcowych, zanim będą oni mogli uzyskać dostęp do poczty e-mail lub innych zasobów firmy.

> [!TIP]
> W okienku usługi Mobile Threat Defense wyświetlany jest **stan połączenia** i czas **ostatniej synchronizacji** między usługą Intune a partnerem usługi MTD.

## <a name="next-steps"></a>Następne kroki

- [Tworzenie zasad ochrony aplikacji usługi Mobile Threat Defense za pomocą usługi Intune](~/protect/mtd-app-protection-policy.md).
