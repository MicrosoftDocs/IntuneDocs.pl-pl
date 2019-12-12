---
title: Rozwiązywanie problemów z profilami poczty e-mail w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Poznaj typowe problemy dotyczące profilów poczty e-mail w usłudze Microsoft Intune oraz ich rozwiązania. Znajdziesz tu m.in. informacje o zduplikowanych profilach oraz błędach występujących na urządzeniach z systemem Android i funkcją Samsung KNOX Standard.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/05/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 38e8998d1720434b0fe866fc5cd41a0b733fc49b
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "74059839"
---
# <a name="common-issues-and-resolutions-with-email-profiles-in-microsoft-intune"></a>Typowe problemy dotyczące profilów poczty e-mail w usłudze Microsoft Intune i sposoby ich rozwiązania

Poznaj niektóre typowe problemy dotyczące profilów poczty e-mail oraz sposoby ich rozwiązywania.

## <a name="what-you-need-to-know"></a>Co musisz wiedzieć

- Profile poczty e-mail są wdrażane dla użytkownika, który zarejestrował urządzenie. Aby skonfigurować profil poczty e-mail, usługa Intune używa właściwości Azure Active Directory (AD) w profilu poczty e-mail użytkownika podczas rejestracji. [Dodawanie ustawień poczty e-mail do urządzeń](email-settings-configure.md) może być dobrym zasobem.
- W przypadku systemu Android Enterprise Wdróż usługę Gmail lub dziewięć do pracy przy użyciu zarządzanych Sklep Google Play. [Dodaj zarządzane Google Play aplikacje](../apps/apps-add-android-for-work.md) zawierają listę kroków.
- Program Microsoft Outlook dla systemów iOS i Android nie obsługuje profilów poczty e-mail. Zamiast tego Wdróż zasady konfiguracji aplikacji. Aby uzyskać więcej informacji, zobacz [ustawienie konfiguracji programu Outlook](../apps/app-configuration-policies-outlook.md).
- Profile poczty e-mail skierowane do grup urządzeń (nie grup użytkowników) mogą nie zostać dostarczone do urządzenia. Gdy urządzenie ma podstawowego użytkownika, urządzenie docelowe powinno funkcjonować. Jeśli profil poczty e-mail zawiera certyfikaty użytkowników, należy pamiętać o docelowych grupach użytkowników.
- Użytkownicy mogą powtarzać monit o wprowadzenie hasła dla profilu poczty e-mail. W tym scenariuszu Sprawdź wszystkie certyfikaty, do których odwołuje się profil poczty e-mail. Jeśli jeden z certyfikatów nie jest przeznaczony dla użytkownika, usługa Intune ponawia próbę wdrożenia profilu poczty e-mail.

## <a name="device-already-has-an-email-profile-installed"></a>Na urządzeniu jest już zainstalowany profil poczty e-mail

Jeśli użytkownicy tworzą profil poczty e-mail przed zarejestrowaniem w usłudze Intune lub Office 365 MDM, profil poczty e-mail wdrożony przez usługę Intune może nie funkcjonować zgodnie z oczekiwaniami:

- **iOS**: usługa Intune wykrywa istniejący, zduplikowany profil poczty e-mail na podstawie nazwy hosta i adresu e-mail. Profil poczty e-mail utworzony przez użytkownika blokuje wdrożenie profilu utworzonego przez usługę Intune. Jest to powszechny problem, ponieważ użytkownicy systemu iOS zwykle najpierw tworzą profil poczty e-mail, a potem rejestrują urządzenie. Aplikacja Portal firmy uznaje profil za niezgodny i może poprosić użytkownika o usunięcie profilu poczty e-mail.

  Użytkownik powinien usunąć swój profil poczty e-mail, aby można było wdrożyć profil usługi Intune. Aby uniknąć tego problemu, użytkownicy powinni zarejestrować urządzenie i pozwolić usłudze Intune na wdrożenie profilu poczty e-mail. Następnie użytkownicy mogą utworzyć własny profil poczty e-mail.

- **Windows**: usługa Intune wykrywa istniejący, zduplikowany profil poczty e-mail na podstawie nazwy hosta i adresu e-mail. Usługa Intune zastępuje istniejący profil poczty e-mail utworzony przez użytkownika.

- **Samsung KNOX Standard**: usługa Intune identyfikuje zduplikowane konto e-mail na podstawie adresu e-mail i zastępuje je profilem usługi Intune. Jeśli użytkownik skonfiguruje to konto, zostanie ono ponownie zastąpione przez profil usługi Intune. Może to powodować dezorientację użytkownika, którego konfiguracja konta zostaje zastąpiona.

Urządzenie Samsung KNOX nie używa nazwy hosta do identyfikowania profilu. Zalecamy nie tworzyć wielu profilów poczty w celu wdrożenia ich z tym samym adresem e-mail na różnych hostach, ponieważ spowoduje to ich wzajemne zastępowanie.

## <a name="error-0x87d1fde8-for-knox-standard-device"></a>Błąd 0x87D1FDE8 dotyczący urządzenia z funkcją KNOX Standard

**Problem**: kiedy zostanie utworzony i wdrożony profil poczty e-mail programu Exchange Active Sync dla funkcji Samsung KNOX Standard na różnych urządzeniach z systemem Android, na karcie Zasady we właściwościach urządzenia wyświetla się błąd **0x87D1FDE8** lub **Korygowanie nie powiodło się**.

Sprawdź konfigurację profilu EAS urządzenia Samsung KNOX i zasad źródłowych. Opcja synchronizacji aplikacji Samsung Notes nie jest już obsługiwana i opcja ta nie powinna być zaznaczona w profilu. Upewnij się, że urządzenia mają wystarczająco dużo czasu na przetwarzanie zasad, nawet do 24 godzin.

## <a name="unable-to-send-images-from--email-account"></a>Nie można wysyłać obrazów z konta e-mail

Użytkownicy, których konta e-mail zostały skonfigurowane automatycznie, nie mogą wysyłać zdjęć ani obrazów ze swoich urządzeń. Taka sytuacja może wystąpić, jeśli nie jest włączona opcja **Zezwalaj na wysyłanie wiadomości e-mail z aplikacji innych firm**.

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Urządzenia** > **Profile konfiguracji**.
3. Wybierz profil poczty e-mail, > **właściwości** > **Ustawienia**.
4. Ustaw ustawienie **Zezwalaj na wysyłanie wiadomości e-mail z aplikacji** innych firm, aby **włączyć**.

## <a name="next-steps"></a>Następne kroki

Uzyskaj [pomoc techniczną od firmy Microsoft](../fundamentals/get-support.md) lub skorzystaj z [forum społeczności](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).
