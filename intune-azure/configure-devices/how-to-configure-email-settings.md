---
title: "Konfigurowanie ustawień poczty e-mail przy użyciu usługi Intune | Wersja zapoznawcza usługi Intune Azure | Dokumentacja firmy Microsoft"
description: "Wersja zapoznawcza usługi Intune Azure: informacje dotyczące konfigurowania usługi Intune pod kątem tworzenia połączeń z firmowymi serwerami poczty e-mail na zarządzanych urządzeniach."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 484bd9b0-fbf1-4f4f-940c-6b12fa07e228
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3ee87c8f6104b06c8a9492566ff160540624f17e
ms.openlocfilehash: 79faa771a9af0761703ca3e72b937fab1a83a81f


---

# <a name="how-to-configure-email-settings"></a>Konfigurowanie ustawień poczty e-mail 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Ustawień profilu poczty e-mail można użyć do skonfigurowania zarządzanych urządzeń przy użyciu ustawień niezbędnych do połączenia się z firmową pocztą e-maili i synchronizowania się z nią. Stanowi to gwarancję, że ustawienia są standardowe dla wszystkich urządzeń, a także pomaga zmniejszyć liczbę telefonów od użytkowników końcowych, którzy nie znają prawidłowych ustawień poczty e-mail.

Wbudowany klient poczty e-mail jest obsługiwany w przypadku większości platform. Większość aplikacji poczty e-mail innych firm nie jest obecnie obsługiwana.

Profile poczty e-mail mogą służyć do konfigurowania klienta natywnego poczty e-mail na następujących typach urządzeń:

- Android 4.0 i nowsze
- System iOS 8.0 i nowsze
- System Windows Phone 8.1 lub nowszy
- System Windows 10 Mobile Desktop i Windows 10 Mobile

Skorzystaj z informacji zawartych w tym temacie, aby uzyskać podstawową wiedzę z zakresu konfigurowania profilów poczty e-mail, a następnie zapoznaj się z tematami dotyczącymi poszczególnych platform, aby dowiedzieć się więcej o charakterystyce urządzeń.

## <a name="create-a-device-profile-containing-email-settings"></a>Tworzenie profilu urządzenia zawierającego ustawienia poczty e-mail

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno pozycje **Więcej usług** > **Inne** > **Intune**.
3. W bloku **Intune** wybierz pozycję **Konfiguruj urządzenia**.
2. W bloku **Konfiguracja urządzeń** wybierz kolejno pozycje **Zarządzaj** > **Profile**.
3. W bloku profilów wybierz pozycję **Utwórz profil**.
4. W bloku **Utwórz profil** uzupełnij pola **Nazwa** i **Opis** odnoszące się do profilu poczty e-mail.
5. Z listy rozwijanej **Platforma** wybierz platformę urządzenia, do której chcesz zastosować ustawienia poczty e-mail. Obecnie dla ustawień poczty e-mail urządzenia można wybrać jedną z następujących platform:
    - **Android**
    - **iOS**
    - **Windows Phone 8.1**
    - **Windows 10 lub nowszy**
6. Z listy rozwijanej **Typ profilu** wybierz pozycję **Poczta e-mail**.
7. Ustawienia, które można skonfigurować, różnią się w zależności od wybranej platformy. Szczegółowe informacje na temat ustawień każdej z platform podano w następujących tematach:
    - [Ustawienia systemu Android](email-profile-settings-for-android.md)
    - [Ustawienia systemu iOS](email-profile-settings-for-ios.md)
    - [Ustawienia systemu Windows Phone 8.1](email-profile-settings-for-windows-phone-8-1.md)
    - [Windows 10 settings](email-profile-settings-for-windows-10.md) (Ustawienia systemu Windows 10)
8. Gdy skończysz, wróć do bloku **Utwórz profil** i wybierz pozycję **Utwórz**.

Profil zostanie utworzony i wyświetlony w bloku listy profilów.
Wskazówki umożliwiające przypisanie tego profilu do grup znajdują się w artykule [How to assign device profiles](how-to-assign-device-profiles.md) (Sposoby przypisywania profilów urządzeń).

## <a name="further-information"></a>Dodatkowe informacje

### <a name="remove-an-email-profile"></a>Usuwanie profilu poczty e-mail

Jeśli chcesz usunąć profil poczty e-mail z urządzenia, zmodyfikuj przypisanie i usuń wszystkie grupy, których urządzenie jest członkiem. Pamiętaj, że nie można usunąć profilu poczty e-mail w ten sposób w przypadku, gdy jest to jedyny profil poczty e-mail na urządzeniu.

### <a name="securing-email-access"></a>Zabezpieczenie dostępu do poczty e-mail

Profile poczty e-mail mogą być chronione przy użyciu jednej z dwóch metod:

1. **Certyfikaty** — podczas tworzenia profilu poczty e-mail wybierasz profil certyfikatu utworzony wcześniej w usłudze Intune. Jest on znany jako certyfikat tożsamości i jest używany do uwierzytelniania względem profilu zaufanego certyfikatu (lub certyfikatu głównego) w celu określenia, czy urządzenie użytkownika może nawiązać połączenie. Zaufany certyfikat jest wdrażany na komputerze, który uwierzytelnia połączenie poczty e-mail — zwykle jest to natywny serwer poczty.
Aby uzyskać więcej informacji o sposobie tworzenia i używania profilów certyfikatów w usłudze Intune, zobacz artykuł [How to configure certificates with Intune](/intune-azure/configure-devices/how-to-configure-certificates) (Jak skonfigurować certyfikaty z użyciem usługi Intune).
2. **Nazwa użytkownika i hasło** — użytkownik jest uwierzytelniany na natywnym serwerze poczty e-mail przez podanie nazwy użytkownika i hasła.
Hasło nie znajduje się w profilu poczty e-mail, więc użytkownik musi je podać podczas łączenia z kontem e-mail.


### <a name="how-intune-handles-existing-email-accounts"></a>Obsługa istniejących kont poczty e-mail przez usługę Intune

Jeśli użytkownik skonfigurował już konto e-mail, wynik przypisania profilu poczty e-mail usługi Intune zależy od platformy urządzeń:

- **iOS**: istniejące zduplikowane profile poczty e-mail są wykrywane na podstawie nazwy hosta i adresu e-mail. Duplikat profilu poczty e-mail zablokuje możliwość przypisywania profilu usługi Intune. W takim przypadku w witrynie Portal firmy zostanie wyświetlony komunikat dla użytkownika z informacją, że profil nie jest zgodny, oraz monitem o usunięcie ręcznie skonfigurowanego profilu. Aby uniknąć takich sytuacji, poleć użytkownikom, aby dokonali rejestracji przed zainstalowaniem profilu poczty e-mail — dzięki temu usługa Intune będzie mogła samodzielnie skonfigurować profil.
- **Windows**: istniejące zduplikowane profile poczty e-mail są wykrywane na podstawie nazwy hosta i adresu e-mail. Usługa Intune zastępuje istniejący profil poczty e-mail utworzony przez użytkownika.
- **Android**: istniejące zduplikowane profile poczty e-mail są wykrywane na podstawie adresu e-mail i zastępowane przez profil usługi Intune.
Ponieważ system Android nie używa nazwy hosta do identyfikowania profilu, nie zalecamy tworzenia wielu profilów poczty e-mail do użycia dla tego samego adresu e-mail na różnych hostach, ponieważ będą one się nawzajem zastępować.



<!--HONumber=Feb17_HO2-->


