---
title: Rozwiązywanie problemów z profilami poczty e-mail w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Poznaj typowe problemy dotyczące profilów poczty e-mail w usłudze Microsoft Intune oraz ich rozwiązania. Znajdziesz tu m.in. informacje o zduplikowanych profilach oraz błędach występujących na urządzeniach z systemem Android i funkcją Samsung KNOX Standard.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/29/2019
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
ms.openlocfilehash: e0fe37deb63457fef869df0f7263970a4e53cb29
ms.sourcegitcommit: a97b6139770719afbd713501f8e50f39636bc202
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 05/30/2019
ms.locfileid: "66402718"
---
# <a name="common-issues-and-resolutions-with-email-profiles-in-microsoft-intune"></a>Typowe problemy dotyczące profilów poczty e-mail w usłudze Microsoft Intune i sposoby ich rozwiązania

Poznaj niektóre typowe problemy dotyczące profilów poczty e-mail oraz sposoby ich rozwiązywania.

## <a name="device-already-has-an-email-profile-installed"></a>Na urządzeniu jest już zainstalowany profil poczty e-mail

Jeśli użytkownicy utworzą profil poczty e-mail przed zarejestrowaniem urządzenia w usłudze Intune, profil poczty e-mail w usłudze Intune może nie działać zgodnie z oczekiwaniami:

- **iOS**: usługa Intune wykrywa istniejący, zduplikowany profil poczty e-mail na podstawie nazwy hosta i adresu e-mail. Profil poczty e-mail utworzony przez użytkownika blokuje wdrożenie profilu utworzonego przez usługę Intune. Jest to powszechny problem, ponieważ użytkownicy systemu iOS zwykle najpierw tworzą profil poczty e-mail, a potem rejestrują urządzenie. Aplikacja Portal firmy uznaje profil za niezgodny i może poprosić użytkownika o usunięcie profilu poczty e-mail.

  Użytkownik powinien usunąć swój profil poczty e-mail, aby można było wdrożyć profil usługi Intune. Aby uniknąć tego problemu, użytkownicy powinni zarejestrować urządzenie i pozwolić usłudze Intune na wdrożenie profilu poczty e-mail. Następnie użytkownicy mogą utworzyć własny profil poczty e-mail.

- **Windows**: usługa Intune wykrywa istniejący, zduplikowany profil poczty e-mail na podstawie nazwy hosta i adresu e-mail. Usługa Intune zastępuje istniejący profil poczty e-mail utworzony przez użytkownika.

- **Samsung KNOX Standard**: usługa Intune identyfikuje zduplikowane konto e-mail na podstawie adresu e-mail i zastępuje je profilem usługi Intune. Jeśli użytkownik skonfiguruje to konto, zostanie ono ponownie zastąpione przez profil usługi Intune. Może to powodować dezorientację użytkownika, którego konfiguracja konta zostaje zastąpiona.

Urządzenie Samsung KNOX nie używa nazwy hosta do identyfikowania profilu. Zalecamy nie tworzyć wielu profilów poczty w celu wdrożenia ich z tym samym adresem e-mail na różnych hostach, ponieważ spowoduje to ich wzajemne zastępowanie.

## <a name="error-0x87d1fde8-for-knox-standard-device"></a>Błąd 0x87D1FDE8 dotyczący urządzenia z funkcją KNOX Standard

**Problem**: kiedy zostanie utworzony i wdrożony profil poczty e-mail programu Exchange Active Sync dla funkcji Samsung KNOX Standard na różnych urządzeniach z systemem Android, na karcie Zasady we właściwościach urządzenia wyświetla się błąd **0x87D1FDE8** lub **Korygowanie nie powiodło się**.

Sprawdź konfigurację profilu EAS urządzenia Samsung KNOX i zasad źródłowych. Opcja synchronizacji aplikacji Samsung Notes nie jest już obsługiwana i opcja ta nie powinna być zaznaczona w profilu. Upewnij się, że urządzenia mają wystarczająco dużo czasu na przetwarzanie zasad, nawet do 24 godzin.

## <a name="unable-to-send-images-from--email-account"></a>Nie można wysyłać obrazów z konta e-mail

Dotyczy usługi Intune w klasycznym portalu Azure.

Użytkownicy, których konta e-mail zostały skonfigurowane automatycznie, nie mogą wysyłać zdjęć ani obrazów ze swoich urządzeń. Taka sytuacja może wystąpić, jeśli nie jest włączona opcja **Zezwalaj na wysyłanie wiadomości e-mail z aplikacji innych firm**.

### <a name="intune-solution"></a>Rozwiązanie przy użyciu usługi Intune

1. Otwórz konsolę administracyjną usługi Microsoft Intune i wybierz obciążenie **Zasady**  > **Zasady konfiguracji**.

2. Wybierz profil poczty e-mail i wybierz polecenie **Edytuj**.

3. Wybierz pozycję **Zezwalaj na wysyłanie wiadomości e-mail z aplikacji innych firm**.

### <a name="configuration-manager-integrated-with-intune-solution"></a>Rozwiązanie przy użyciu programu Configuration Manager zintegrowanego z usługą Intune

1. Otwórz program Configuration Manager > **Zasoby i zgodność**.

2. Rozwiń węzeł **Przegląd** > **Ustawienia zgodności** > **Dostęp do zasobów firmy** i wybierz pozycję **Profile poczty e-mail**.

3. Kliknij prawym przyciskiem myszy profil poczty e-mail i otwórz pozycję **Właściwości**.

4. Na karcie **Ustawienia synchronizacji** wybierz pozycję **Zezwalaj na wysyłanie wiadomości e-mail z aplikacji innych firm**.

## <a name="next-steps"></a>Następne kroki

Uzyskaj [pomoc techniczną od firmy Microsoft](get-support.md) lub skorzystaj z [forum społeczności](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).