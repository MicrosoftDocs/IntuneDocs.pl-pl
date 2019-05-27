---
title: Rozwiązywanie problemów z profilami poczty e-mail w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Problemy dotyczące profilów poczty e-mail oraz opisano sposoby ich rozwiązywania.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/14/2018
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: ef84241f72f34e0f00516702d0928e0395478929
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 05/23/2019
ms.locfileid: "66044662"
---
# <a name="troubleshoot-email-profiles-in-microsoft-intune"></a>Rozwiązywanie problemów z profilami poczty e-mail w usłudze Microsoft Intune

Poznaj niektóre typowe problemy dotyczące profilów poczty e-mail oraz sposoby ich rozwiązywania.

Jeśli te informacje nie pomogą w rozwiązaniu problemu, możesz również [uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](get-support.md).

## <a name="unable-to-send-images-from--email-account"></a>Nie można wysyłać obrazów z konta e-mail
Dotyczy usługi Intune w klasycznym portalu Azure.

Użytkownicy, którzy mają automatycznie skonfigurowane konta e-mail, nie mogą wysyłać obrazów ze swoich urządzeń. Taka sytuacja może wystąpić, jeśli nie jest włączona opcja **Zezwalaj na wysyłanie wiadomości e-mail z aplikacji innych firm**.

### <a name="intune-solution"></a>Rozwiązanie przy użyciu usługi Intune

1. Otwórz konsolę administracyjną usługi Microsoft Intune i wybierz obciążenie **Zasady**  > **Zasady konfiguracji**.

2. Wybierz profil poczty e-mail i wybierz polecenie **Edytuj**.

3. Wybierz pozycję **Zezwalaj na wysyłanie wiadomości e-mail z aplikacji innych firm**.

### <a name="configuration-manager-integrated-with-intune-solution"></a>Rozwiązanie przy użyciu programu Configuration Manager zintegrowanego z usługą Intune

1. Otwórz program Configuration Manager > **Zasoby i zgodność**.

2. Rozwiń węzeł **Przegląd** > **Ustawienia zgodności** > **Dostęp do zasobów firmy** i wybierz pozycję **Profile poczty e-mail**.

3. Kliknij prawym przyciskiem myszy profil poczty e-mail i otwórz pozycję **Właściwości**.

4. Na karcie **Ustawienia synchronizacji** wybierz pozycję **Zezwalaj na wysyłanie wiadomości e-mail z aplikacji innych firm**.

## <a name="device-already-has-an-email-profile-installed"></a>Na urządzeniu jest już zainstalowany profil poczty e-mail

Jeśli użytkownik zainstalował profil poczty e-mail przed aprowizowaniem profilu usługi Intune, wynik wdrożenia profilu poczty e-mail usługi Intune zależy od platformy urządzenia:

- **iOS**: usługa Intune wykrywa istniejący, zduplikowany profil poczty e-mail na podstawie nazwy hosta i adresu e-mail. Zduplikowany profil poczty e-mail utworzony przez użytkownika blokuje wdrożenie profilu utworzonego przez administratora usługi Intune. Jest to powszechny problem, ponieważ użytkownicy systemu iOS zwykle najpierw tworzą profil poczty e-mail, a potem rejestrują urządzenie. Portal firmy informuje użytkownika, że nie jest on zgodny ze względu na ręcznie skonfigurowany profil poczty e-mail, i wyświetla monit o usunięcie tego profilu. Użytkownik powinien usunąć swój profil poczty e-mail, aby można było wdrożyć profil usługi Intune. Aby uniknąć tego problemu, poproś użytkownika o przeprowadzenie rejestracji i pozwól usłudze Intune na wdrożenie profilu. Następnie zainstaluj profil poczty e-mail utworzony przez użytkownika.

- **Windows**: usługa Intune wykrywa istniejący, zduplikowany profil poczty e-mail na podstawie nazwy hosta i adresu e-mail. Usługa Intune zastępuje istniejący profil poczty e-mail utworzony przez użytkownika.

- **Samsung KNOX Standard**: usługa Intune identyfikuje zduplikowane konto e-mail na podstawie adresu e-mail i zastępuje je profilem usługi Intune. Jeśli użytkownik skonfiguruje to konto, zostanie ono ponownie zastąpione przez profil usługi Intune. Może to powodować dezorientację użytkownika, którego konfiguracja konta zostaje zastąpiona.

Urządzenie Samsung KNOX nie używa nazwy hosta do identyfikowania profilu. Zalecamy, aby nie tworzyć wielu profilów poczty e-mail do wdrożenia z tym samym adresem e-mail na różnych hostach, ponieważ będą one zastępowane wzajemnie.

## <a name="error--0x87d1fde8-for-knox-standard-device"></a>Błąd 0x87D1FDE8 dla urządzenia KNOX Standard
**Problem**: po utworzeniu i wdrożeniu profilu poczty e-mail programu Exchange Active Sync dla urządzenia Samsung KNOX Standard w przypadku różnych urządzeń z systemem Android zgłaszany jest błąd **0x87D1FDE8** lub **korygowanie nie powiodło się** na karcie Zasady we właściwościach urządzenia.

Sprawdź konfigurację profilu EAS urządzenia Samsung KNOX i zasad źródłowych. Opcja synchronizacji notatek urządzenia Samsung nie jest już obsługiwana i ta opcja nie powinna być wybrana w Twoim profilu. Upewnij się, że urządzenia mają wystarczająco dużo czasu na przetwarzanie zasad, nawet do 24 godzin.

## <a name="next-steps"></a>Następne kroki
Jeśli te informacje nie pomogą w rozwiązaniu problemu, możesz również [uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](get-support.md).
