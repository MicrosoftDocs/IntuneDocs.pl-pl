---
title: "Resetowanie kodu dostępu na urządzeniach z systemem Windows przy użyciu usługi Intune"
titlesuffix: Azure portal
description: "Dowiedz się, jak za pomocą usługi Intune zresetować kod dostępu na urządzeniu z systemem Windows zintegrowanym z usługą resetowania numerów PIN firmy Microsoft."
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5027d012-d6c2-4971-a9ac-217f91d67d87
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b6149eeb3da2da3be3a137845eee5a0a515a4e39
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/25/2018
---
# <a name="reset-the-passcode-on-windows-devices-integrated-with-the-microsoft-pin-reset-service-using-intune"></a>Resetowanie kodu dostępu na urządzeniach z systemem Windows zintegrowanych z usługą resetowania numerów PIN firmy Microsoft przy użyciu usługi Intune

Integracja funkcji resetowania kodu dostępu w urządzeniach z systemem Windows z usługą resetowania numerów PIN firmy Microsoft pozwala wygenerować nowy kod dostępu dla urządzeń z systemem Windows 10 Mobile. Na urządzeniach musi być zainstalowana aktualizacja Windows 10 Creators Update lub jej nowsza wersja.

## <a name="supported-platforms"></a>Obsługiwane platformy

- Windows — obsługiwana dla aktualizacji systemu Windows 10 dla twórców i nowszej wersji (przyłączonej do usługi Azure AD)
- Windows Phone — nieobsługiwana
- iOS — nieobsługiwana
- macOS — nieobsługiwana
- Android — nieobsługiwana


## <a name="before-you-start"></a>Przed rozpoczęciem

Aby można było zdalnie zresetować kod dostępu na zarządzanych urządzeniach z systemem Windows, musisz udostępnić usługę resetowania numeru PIN w dzierżawie usługi Intune oraz skonfigurować zarządzane urządzenia. Wykonaj te instrukcje, aby uzyskać tę konfigurację:

### <a name="connect-intune-with-the-pin-reset-service"></a>Łączenie usługi Intune z usługą resetowania numeru PIN

1. Odwiedź [witrynę internetową integracji usługi resetowania numeru PIN firmy Microsoft](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=b8456c59-1230-44c7-a4a2-99b085333e84&resource=https%3A%2F%2Fgraph.windows.net&redirect_uri=https%3A%2F%2Fcred.microsoft.com&state=e9191523-6c2f-4f1d-a4f9-c36f26f89df0&prompt=admin_consent) i zaloguj się przy użyciu konta administratora dzierżawy używanego do zarządzania dzierżawą usługi Intune.
2. Po zalogowaniu kliknij pozycję **Akceptuj**, aby wyrazić zgodę na uzyskiwanie dostępu do konta przez usługę resetowania numeru PIN.<br>
![Strona uprawnień usługi resetowania numeru PIN](./media/pin-reset-service-application.png)
3. W witrynie Azure Portal można sprawdzić, czy usługa Intune i usługa resetowania numeru PIN zostały zintegrowane za pośrednictwem bloku Aplikacje w przedsiębiorstwie — wszystkie aplikacje, jak pokazano na poniższym zrzucie ekranu:<br>
![Aplikacja usługi resetowania numeru PIN na platformie Azure](./media/pin-reset-service-home-screen.png)
4. Zaloguj się do [tej witryny internetowej](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=9115dd05-fad5-4f9c-acc7-305d08b1b04e&resource=https%3A%2F%2Fcred.microsoft.com%2F&redirect_uri=ms-appx-web%3A%2F%2FMicrosoft.AAD.BrokerPlugin%2F9115dd05-fad5-4f9c-acc7-305d08b1b04e&state=6765f8c5-f4a7-4029-b667-46a6776ad611&prompt=admin_consent) za pomocą poświadczeń administratora dzierżawy usługi Intune i ponownie wybierz pozycję **Akceptuj**, aby wyrazić zgodę na uzyskiwanie przez usługę dostępu do konta.

### <a name="configure-windows-devices-to-use-pin-reset"></a>Konfigurowanie urządzeń z systemem Windows do użycia usługi resetowania numeru PIN

Aby skonfigurować resetowanie numeru PIN na zarządzanych urządzeniach z systemem Windows, włącz poszczególne funkcje przy użyciu [niestandardowych zasad usługi Intune dotyczących urządzeń z systemem Windows 10](custom-settings-windows-10.md). Skonfiguruj zasady za pomocą następującego dostawcy usługi konfiguracji zasad systemu Windows:


- **W przypadku urządzeń** - **./Device/Vendor/MSFT/PassportForWork/*identyfikator dzierżawy*/Policies/EnablePinRecovery**

*Identyfikator dzierżawy* odwołuje się do identyfikatora katalogi usługi Azure Active Directory, który możesz uzyskać na stronie **Właściwości** usługi Azure Active Directory.

Ustaw wartość dla tego dostawcy usług kryptograficznych na **Prawda**.

## <a name="steps-to-reset-the-passcode"></a>Instrukcje resetowania kodu dostępu

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Urządzenia**.
4. W bloku **Urządzenia** wybierz kolejno pozycje **Zarządzaj** > **Wszystkie urządzenia**.
5. Wybierz urządzenie, dla którego chcesz zresetować kod dostępu, a następnie w bloku właściwości urządzenia wybierz pozycję **Nowy kod dostępu**.
6. W wyświetlonym oknie z potwierdzeniem wybierz przycisk **Tak**. Wygenerowany kod dostępu będzie wyświetlany w portalu przez następne 7 dni.

## <a name="next-steps"></a>Następne kroki

Jeśli resetowanie kodu dostępu zakończy się niepowodzeniem, w portalu zostanie wyświetlony link umożliwiający uzyskanie dodatkowych informacji.


