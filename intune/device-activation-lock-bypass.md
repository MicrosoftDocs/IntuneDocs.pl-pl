---
title: Obejście blokady aktywacji systemu iOS przy użyciu usługi Intune
titlesuffix: Microsoft Intune
description: Dowiedz się, jak za pomocą usługi Intune obejść blokadę aktywacji systemu iOS, by uzyskać dostęp do zablokowanych urządzeń.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9ca3b0ba-e41c-45fb-af28-119dff47c59f
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2a8c14e523d33c9e0994134ff1ef468b290b3992
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
ms.locfileid: "31022513"
---
# <a name="bypass-activation-lock-on-supervised-ios-devices-with-intune"></a>Obejście blokady aktywacji na nadzorowanych urządzeniach z systemem iOS przy użyciu usługi Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Usługa Microsoft Intune ułatwia zarządzanie blokadą aktywacji systemu iOS — funkcją aplikacji Znajdź mój iPhone dla urządzeń z systemem iOS 8.0 lub nowszym. Blokada aktywacji jest włączana automatycznie w przypadku otwarcia przez użytkownika aplikacji Znajdź mój iPhone na urządzeniu. Jeśli ta funkcja została włączona, należy podać identyfikator Apple ID i hasło użytkownika, aby można było wykonać następujące czynności:

- Wyłączenie aplikacji Znajdź mój iPhone
- Wymazanie urządzenia
- Ponowne uaktywnienie urządzenia

## <a name="how-activation-lock-affects-you"></a>Wpływ blokady aktywacji na Twoje działania

Blokada aktywacji pomaga w zabezpieczaniu urządzeń z systemem iOS i zwiększa szanse na odzyskanie urządzenia w razie jego zgubienia lub kradzieży, jednak może ona powodować problemy dla administratora systemu informatycznego. Przykład:

- Użytkownik konfiguruje blokadę aktywacji na urządzeniu. Następnie użytkownik odchodzi z firmy i zwraca urządzenie. Bez identyfikatora Apple ID i hasła użytkownika nie ma możliwości ponownego uaktywnienia urządzenia.
- Potrzebny jest raport ze wszystkimi urządzeniami, na których włączono blokadę aktywacji.
- Podczas odświeżania urządzenia w organizacji chcesz ponownie przypisać niektóre urządzenia do innego działu. Możesz przypisywać ponownie tylko urządzenia, na których nie włączono blokady aktywacji.

Aby pomóc w rozwiązaniu tych problemów, firma Apple wprowadziła obejście blokady aktywacji w systemie iOS 7.1. Obejście blokady aktywacji pozwala usunąć blokadę aktywacji z nadzorowanych urządzeń bez identyfikatora Apple ID i hasła użytkownika. Nadzorowane urządzenie może wygenerować unikatowy kod obejścia blokady aktywacji, który jest przechowywany na serwerze aktywacji firmy Apple.

>[!TIP]
>Tryb nadzorowany dla urządzeń z systemem iOS umożliwia zablokowanie urządzenia za pomocą programu Apple Configurator w celu ograniczenia funkcji urządzenia do określonych celów biznesowych. Tryb nadzorowany jest przeznaczony tylko dla urządzeń należących do firm.

Więcej informacji o blokadzie aktywacji można znaleźć w [witrynie internetowej firmy Apple](https://support.apple.com/HT201365).

## <a name="how-intune-helps-you-manage-activation-lock"></a>Jak usługa Intune pomaga w zarządzaniu blokadą aktywacji
Usługa Intune może wysłać żądanie dotyczące stanu blokady aktywacji na nadzorowanych urządzeniach z systemem iOS 8.0 lub nowszym. Tylko w przypadku urządzeń nadzorowanych usługa Intune może pobrać kod obejścia blokady aktywacji i wystawić go bezpośrednio na urządzeniu. Jeśli zawartość urządzenia została wyczyszczona, możesz bezpośrednio uzyskać dostęp do urządzenia, używając pustej nazwy użytkownika i kodu jako hasła.

**Korzyści biznesowe wynikające z zarządzania blokadą aktywacji za pomocą usługi Intune są następujące:**

- Użytkownik może korzystać z zabezpieczeń oferowanych przez aplikację Znajdź mój iPhone.
- Możesz umożliwić użytkownikom normalną pracę, wiedząc, że w razie konieczności zmiany przeznaczenia urządzenia można je wycofać lub odblokować.

## <a name="before-you-start"></a>Przed rozpoczęciem
Aby obejść blokadę aktywacji na urządzeniach, trzeba ją najpierw włączyć, postępując zgodnie z następującymi instrukcjami:

1. Skonfiguruj profil ograniczeń dotyczących urządzeń w usłudze Intune dla systemu iOS przy użyciu informacji w temacie [Jak skonfigurować ustawienia ograniczeń dotyczących urządzeń w usłudze Microsoft Intune](/intune-azure/configure-devices/how-to-configure-device-restrictions).
2. W [ustawieniach ograniczeń urządzenia dla systemu iOS](device-restrictions-ios.md) w sekcji ustawień **Ogólne** włącz opcję **Blokada aktywacji**.
3. Zapisz profil, a następnie [przypisz go](device-profile-assign.md) do urządzeń, na których chcesz zarządzać obejściem blokady aktywacji.


## <a name="how-to-use-activation-lock-bypass"></a>Jak korzystać z obejścia blokady aktywacji

>[!IMPORTANT]
>Po obejściu blokady aktywacji na urządzeniu, jeśli jest otwarta aplikacja Znajdź mój iPhone, zostanie automatycznie zastosowana nowa blokada aktywacji. Dlatego **musisz mieć fizyczny dostęp do urządzenia, aby móc wykonać tę procedurę**.

Akcja zdalna **Zastosuj obejście blokady aktywacji** dotycząca urządzenia w usłudze Intune powoduje usunięcie blokady aktywacji z urządzenia z systemem iOS bez identyfikatora Apple ID i hasła użytkownika. Po zastosowaniu obejścia blokady aktywacji urządzenie ponownie przejdzie w stan blokady aktywacji, gdy zostanie uruchomiona aplikacja Znajdź mój iPhone. Stosuj obejście blokady aktywacji tylko w sytuacji, gdy masz fizyczny dostęp do urządzenia.

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W bloku **Intune** wybierz opcję **Urządzenia**.
4. W bloku **Urządzenia** wybierz pozycję **Wszystkie urządzenia**.
5. Z listy zarządzanych urządzeń wybierz nadzorowane urządzenie z systemem iOS, wybierz pozycję **...Więcej**, a następnie wybierz akcję zdalną **Zastosuj obejście blokady aktywacji** dla urządzenia.

## <a name="next-steps"></a>Następne kroki

Stan żądania odblokowania można sprawdzić na stronie szczegółów urządzenia w obciążeniu **Zarządzaj urządzeniami**.
