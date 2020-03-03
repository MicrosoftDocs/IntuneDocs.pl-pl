---
title: Obejście blokady aktywacji systemu iOS/iPadOS przy użyciu usługi Intune
titleSuffix: Microsoft Intune
description: Dowiedz się, jak za pomocą usługi Intune obejść blokadę aktywacji systemu iOS/iPadOS, aby uzyskać dostęp do zablokowanych urządzeń.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 9ca3b0ba-e41c-45fb-af28-119dff47c59f
ms.reviewer: coferro
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 65a13c2690f08c2244f31854556a88b6301c6ac5
ms.sourcegitcommit: 47c9af81c385c7e893fe5a85eb79cf08e69e6831
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/25/2020
ms.locfileid: "77576013"
---
# <a name="disable-activation-lock-on-supervised-iosipados-devices-with-intune"></a>Wyłączanie blokady aktywacji na nadzorowanych urządzeniach z systemem iOS/iPadOS przy użyciu usługi Intune


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Usługa Microsoft Intune ułatwia zarządzanie blokadą aktywacji systemu iOS/iPadOS — funkcją aplikacji Znajdź mój iPhone dla urządzeń z systemem iOS/iPadOS 8.0 lub nowszym. Blokada aktywacji jest włączana automatycznie w przypadku otwarcia przez użytkownika aplikacji Znajdź mój iPhone na urządzeniu. Jeśli ta funkcja została włączona, należy podać identyfikator Apple ID i hasło użytkownika, aby można było wykonać następujące czynności:

- Wyłączenie aplikacji Znajdź mój iPhone
- Wymazanie urządzenia
- Ponowne uaktywnienie urządzenia

## <a name="how-activation-lock-affects-you"></a>Wpływ blokady aktywacji na Twoje działania

Blokada aktywacji pomaga w zabezpieczaniu urządzeń z systemem iOS/iPadOS i zwiększa szanse na odzyskanie urządzenia w razie jego zgubienia lub kradzieży, jednak może ona powodować problemy dla administratora systemu informatycznego. Przykład:

- Użytkownik konfiguruje blokadę aktywacji na urządzeniu. Następnie użytkownik odchodzi z firmy i zwraca urządzenie. Bez identyfikatora Apple ID i hasła użytkownika nie ma możliwości ponownego uaktywnienia urządzenia.
- Potrzebny jest raport ze wszystkimi urządzeniami, na których włączono blokadę aktywacji.
- Podczas odświeżania urządzenia w organizacji chcesz ponownie przypisać niektóre urządzenia do innego działu. Możesz przypisywać ponownie tylko urządzenia, na których nie włączono blokady aktywacji.

Aby pomóc w rozwiązaniu tych problemów, firma Apple wprowadziła funkcję wyłączania blokady aktywacji w systemie iOS/iPadOS 7.1. Wyłączanie blokady aktywacji pozwala usunąć blokadę aktywacji z nadzorowanych urządzeń bez identyfikatora Apple ID i hasła użytkownika. Nadzorowane urządzenie może wygenerować unikatowy kod obejścia blokady aktywacji, który jest przechowywany na serwerze aktywacji firmy Apple.

>[!TIP]
>Tryb nadzorowany dla urządzeń z systemem iOS/iPadOS umożliwia zablokowanie urządzenia za pomocą programu Apple Configurator w celu ograniczenia funkcji urządzenia do określonych celów biznesowych. Tryb nadzorowany jest przeznaczony tylko dla urządzeń należących do firm.

Więcej informacji o blokadzie aktywacji można znaleźć w [witrynie internetowej firmy Apple](https://support.apple.com/HT201365).

## <a name="how-intune-helps-you-manage-activation-lock"></a>Jak usługa Intune pomaga w zarządzaniu blokadą aktywacji
Usługa Intune może wysłać żądanie dotyczące stanu blokady aktywacji na nadzorowanych urządzeniach z systemem iOS/iPadOS 8.0 lub nowszym. Tylko w przypadku urządzeń nadzorowanych usługa Intune może pobrać kod wyłączania blokady aktywacji i wystawić go bezpośrednio na urządzeniu. Jeśli zawartość urządzenia została wyczyszczona, możesz bezpośrednio uzyskać dostęp do urządzenia, używając pustej nazwy użytkownika i kodu jako hasła.

**Korzyści biznesowe wynikające z zarządzania blokadą aktywacji za pomocą usługi Intune są następujące:**

- Użytkownik może korzystać z zabezpieczeń oferowanych przez aplikację Znajdź mój iPhone.
- Możesz umożliwić użytkownikom normalną pracę, wiedząc, że w razie konieczności zmiany przeznaczenia urządzenia można je wycofać lub odblokować.

## <a name="before-you-start"></a>Przed rozpoczęciem
Aby wyłączyć blokadę aktywacji na urządzeniach, trzeba ją najpierw włączyć, postępując zgodnie z następującymi instrukcjami:

1. Skonfiguruj profil ograniczeń dotyczących urządzeń w usłudze Intune dla systemu iOS/iPadOS przy użyciu informacji w temacie [Jak skonfigurować ustawienia ograniczeń dotyczących urządzeń w usłudze Microsoft Intune](/intune-azure/configure-devices/how-to-configure-device-restrictions).
2. W [ustawieniach ograniczeń urządzenia dla systemu iOS/iPadOS](../configuration/device-restrictions-ios.md) w sekcji ustawień **Ogólne** włącz opcję **Blokada aktywacji**.
3. Zapisz profil, a następnie [przypisz go](../configuration/device-profile-assign.md) do urządzeń, na których chcesz zarządzać wyłączaniem blokady aktywacji.


## <a name="how-to-use-disable-activation-lock"></a>Jak wyłączyć blokadę aktywacji

>[!IMPORTANT]
>Po wyłączeniu blokady aktywacji na urządzeniu, jeśli jest uruchomiona aplikacja Znajdź mój iPhone, zostanie automatycznie zastosowana nowa blokada aktywacji. Dlatego **musisz mieć fizyczny dostęp do urządzenia, aby móc wykonać tę procedurę**.

Akcja zdalna **Wyłącz blokadę aktywacji** dotycząca urządzenia w usłudze Intune powoduje usunięcie blokady aktywacji z urządzenia z systemem iOS/iPadOS bez konieczności podania identyfikatora Apple ID i hasła użytkownika. Po zastosowaniu wyłączania blokady aktywacji urządzenie ponownie przejdzie w stan blokady aktywacji, gdy zostanie uruchomiona aplikacja Znajdź mój iPhone. Stosuj wyłączanie blokady aktywacji tylko w sytuacji, gdy masz fizyczny dostęp do urządzenia.

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
3. W bloku **Intune** wybierz pozycję **Urządzenia**.
4. W bloku **Urządzenia** wybierz pozycję **Wszystkie urządzenia**.
5. Na liście zarządzanych urządzeń wybierz zdalną akcję urządzenia**Wyłącz blokadę aktywacji**.
6. Przejdź do sekcji „Sprzęt”, a następnie skopiuj wartość **kodu obejścia blokady aktywacji** w obszarze **Dostęp warunkowy**.

    >[!NOTE]
    >Skopiuj kod obejścia przed wyczyszczeniem urządzenia. Jeśli zresetujesz ustawienia urządzenia przed skopiowaniem kodu, kod zostanie usunięty z platformy Azure.

7. Przejdź do bloku **Przegląd** urządzenia, a następnie wybierz pozycję **Wyczyść**.
8. Po zresetowaniu urządzenia zostanie wyświetlony monit o podanie *identyfikatora Apple ID* i *hasła*. Pozostaw pole *ID* puste, a następnie wprowadź **kod obejścia***hasła*. Spowoduje to usunięcie konta z urządzenia. 


## <a name="next-steps"></a>Następne kroki

Stan żądania odblokowania można sprawdzić na stronie szczegółów urządzenia w obciążeniu **Zarządzaj urządzeniami**.
