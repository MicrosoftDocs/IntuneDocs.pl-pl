---
title: Resetowanie kodu dostępu na urządzeniach z systemem Windows przy użyciu usługi Microsoft Intune — Azure | Microsoft Docs
description: Aby zresetować kod dostępu na urządzeniach z systemem Windows, zainstaluj usługę resetowania numerów PIN firmy Microsoft oraz klienta usługi resetowania numerów PIN firmy Microsoft, utwórz zasady urządzeń przy użyciu identyfikatora usługi Azure Active Directory, a następnie zresetuj kod dostępu w witrynie Azure Portal przy użyciu usługi Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/07/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5027d012-d6c2-4971-a9ac-217f91d67d87
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b643ed41d01b70376dac32c26a66dcf9f9735ceb
ms.sourcegitcommit: ec69e7ccc6e6183862a48c1b03ca6a3bf573f354
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/07/2019
ms.locfileid: "74907223"
---
# <a name="reset-the-passcode-on-windows-devices-using-intune"></a>Resetowanie kodu dostępu na urządzeniach z systemem Windows przy użyciu usługi Intune

Możesz zresetować kod dostępu dla urządzeń z systemem Windows. Funkcja resetowania kodów dostępu używa usługi resetowania numerów PIN firmy Microsoft do wygenerowania nowego kodu dostępu dla urządzeń z systemem Windows 10 Mobile. 

## <a name="supported-platforms"></a>Obsługiwane platformy

- Windows 10 Mobile z aktualizacją dla twórców i nowszymi (z przyłączeniem do usługi Azure AD).

Następujące platformy **nie są** obsługiwane:
- Windows
- iOS
- macOS
- Android

## <a name="authorize-the-pin-reset-services"></a>Autoryzacja usług resetowania numeru PIN

Aby zresetować kod dostępu na urządzeniach z systemem Windows, dołącz usługę resetowania numerów PIN do dzierżawy usługi Intune.

1. Przejdź do obszaru [produkcji usługi resetowania numerów PIN firmy Microsoft](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=b8456c59-1230-44c7-a4a2-99b085333e84&resource=https%3A%2F%2Fgraph.windows.net&redirect_uri=https%3A%2F%2Fcred.microsoft.com&state=e9191523-6c2f-4f1d-a4f9-c36f26f89df0&prompt=admin_consent), a następnie zaloguj się przy użyciu konta administratora dzierżawy.
2. **Wyraź** zgodę na uzyskiwanie dostępu do Twojego konta przez usługę resetowania numerów PIN: ![Akceptowanie żądania uprawnień serwera resetowania numerów PIN](./media/device-windows-pin-reset/pin-reset-service-home-screen.png)
3. Przejdź do obszaru [produkcji klienta usługi resetowania numerów PIN firmy Microsoft](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=9115dd05-fad5-4f9c-acc7-305d08b1b04e&resource=https%3A%2F%2Fcred.microsoft.com%2F&redirect_uri=ms-appx-web%3A%2F%2FMicrosoft.AAD.BrokerPlugin%2F9115dd05-fad5-4f9c-acc7-305d08b1b04e&state=6765f8c5-f4a7-4029-b667-46a6776ad611&prompt=admin_consent), a następnie zaloguj się przy użyciu konta administratora dzierżawy. **Zaakceptuj** zgodę, aby klient usługi resetowania numerów PIN mógł uzyskać dostęp do Twojego konta.
4. W witrynie [Azure Portal](https://portal.azure.com) potwierdź, że usługi resetowania numerów PIN są widoczne na liście aplikacji dla przedsiębiorstw (Wszystkie aplikacje): ![Strona uprawnień usługi resetowania numeru PIN](./media/device-windows-pin-reset/pin-reset-service-application.png)

> [!NOTE]
> Po zaakceptowaniu żądań usługi resetowania numerów PIN możesz otrzymać komunikat `Page not found`. Może też wydawać się, że nic się nie stało. To zachowanie jest normalne. Pamiętaj, aby upewnić się, że dwie aplikacje resetowania numerów PIN znajdują się na liście dla Twojej dzierżawy.

## <a name="configure-windows-devices-to-use-pin-reset"></a>Konfigurowanie urządzeń z systemem Windows do użycia usługi resetowania numeru PIN

Aby skonfigurować resetowanie numeru PIN na zarządzanych urządzeniach z systemem Windows, użyj [niestandardowych zasad usługi Intune dotyczących urządzeń z systemem Windows 10](../configuration/custom-settings-windows-10.md). Skonfiguruj zasady za pomocą następującego dostawcy usługi konfiguracji zasad systemu Windows:

**Użyj zasad urządzeń** - `./Device/Vendor/MSFT/PassportForWork/*tenant ID*/Policies/EnablePinRecovery`

Zastąp *identyfikator dzierżawy* identyfikatorem usługi Azure AD, który znajduje się na liście **Właściwości** usługi Azure Active Directory w witrynie [Azure Portal](https://portal.azure.com).

Ustaw wartość dla tego dostawcy usług kryptograficznych na **Prawda**.

> [!TIP]
> Po utworzeniu zasad możesz przypisać (lub wdrożyć) je do grupy. Zasady można przypisać do grup użytkowników lub grup urządzeń. Jeśli zostaną przypisane do grupy użytkowników, następnie grupa będzie mogła uwzględnić użytkowników posiadających inne urządzenia, np. z systemem iOS. Z technicznego punktu widzenia zasady nie będą mieć zastosowania, ale te urządzenia nadal będą uwzględniane w szczegółach dotyczących stanu.

## <a name="reset-the-passcode"></a>Resetowanie kodu dostępu

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431). 
2. Wybierz pozycję **Urządzenia**, a następnie wybierz pozycję **Wszystkie urządzenia**.
3. Wybierz urządzenie, dla którego chcesz zresetować kod dostępu. We właściwościach urządzenia wybierz pozycję **Resetuj kod dostępu**.
4. Kliknij przycisk **Tak**, aby potwierdzić. Wygenerowany kod dostępu będzie wyświetlany w portalu przez następne 7 dni.

## <a name="next-step"></a>Następny krok

Jeśli resetowanie kodu dostępu zakończy się niepowodzeniem, w portalu zostaną wyświetlone dodatkowe informacje.
